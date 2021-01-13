---
title: アーカイブされた Skype for Business データを検索する SharePoint Server を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: '概要: SharePoint Server を構成して、Exchange Server Skype for Business Server によってアーカイブされたデータを検索します。'
ms.openlocfilehash: 406e0a713c65bc147ce6eb492f251a25ea2a3afc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833947"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>アーカイブされた Skype for Business データを検索する SharePoint Server を構成する
 
**概要:** Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server によってアーカイブされたデータを検索する SharePoint Server を構成します。
  
Skype for Business Server ではなく Exchange Server にインスタント メッセージングと Web 会議のトランスクリプトを保存する主な利点の 1 つは、管理者が 1 つのツールを使用してアーカイブされた Exchange データやアーカイブされた Skype for Business Server データを検索できるという方法です。 すべてのデータは同じ場所 (Exchange) に格納されます。アーカイブされた Exchange データを検索できるツールは、アーカイブされた Skype for Business Server データも検索できます。
  
アーカイブされたデータを簡単に検索できるツールの 1 つは、Microsoft SharePoint Server 2013 です。 SharePoint を使用して Skype for Business Server データを検索する場合は、最初に Skype for Business Server での Exchange アーカイブの構成に関連する手順を完了する必要があります。 Exchange Exchange Server Skype for Business Server が正常に統合された後、Exchange Web [サービスマネージ API](https://go.microsoft.com/fwlink/p/?LinkId=258305) を SharePoint Server にインストールする必要があります。 ダウンロードしたファイル (EWSManagedAPI.msi) は、SharePoint サーバー上の任意のフォルダーに保存できます。
  
ファイルをダウンロードした後、SharePoint サーバー上で次の手順を実行します。
  
1. [**スタート**]、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックして、コマンド ウィンドウを開きます。
    
2. コマンド ウィンドウで、cd コマンドを使用して、EWSManagedAPI.msi ファイルが保存されているフォルダーに現在のディレクトリを変更します。 たとえば、ファイルを C:\Downloads に保存した場合、コマンド ウィンドウに次のコマンドを入力し、Enter キーを押します。
    
   ```console
   cd C:\Downloads
   ```

3. API をインストールするには、次のコマンドを入力し、Enter キーを押します。
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. API がインストールされた後、次のコマンドを入力して Enter キーを押して IIS をリセットします。
    
   ```console
   iisreset
   ```

Exchange Web サービスをインストールした後、SharePoint Server とサーバー間のサーバー間認証を構成Exchange Server。 これを行うには、まず SharePoint 管理シェルを開き、次の一連のコマンドを実行します。
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> 自動検出サービスの URI を使用してください。 サンプル URI は使用しない https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 。 
  
トークン発行者を作成し、トークン サービスを構成したら、次のコマンドを実行して、SharePoint サイトの URL をサンプル URL に置き換える必要があります。 http://atl-sharepoint-001:
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Exchange Server のサーバー間認証を構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange が C ドライブにインストールされ、既定のフォルダー パスが使用されている場合)。
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

パートナー アプリケーションを構成した後、すべての Exchange メールボックスサーバーとクライアント アクセス サーバーでインターネット インフォメーション サービス (IIS) を停止して再起動してください。 次のようなコマンドを使用して IIS を再起動できます。これにより、コンピューター atl-exchange-001 上のサービスが再起動されます。
  
```powershell
iisreset atl-exchange-001
```

このコマンドは、Exchange 管理シェル 内または他のコマンド ウィンドウから実行できます。
  
次に、次のようなコマンドを実行します。これにより、指定したユーザー (この例では kenmyer) が Exchange で検出を行う権限を与えます。
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Exchange と SharePoint の間でサーバー間認証が確立された後、次の手順は SharePoint で電子情報開示サイトを作成することです。 これは、SharePoint 管理シェルから次のようなコマンドを実行することで実行できます。
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> "電子情報開示" とは、通常、訴訟において "証拠になり得ると合理的に判断できる" 項目の電子的アーカイブを参照するプロセスを表します。 
  
新しいサイトの準備ができたら、次の手順では、SharePoint のExchange Serverソースとして機能するサイトを構成します。 これを行うには、[SharePoint サーバーの全体管理] ページから次の手順を実行します。
  
1. サーバーの全体管理ページで、[**サービス アプリケーションの管理**]、[**Search Service アプリケーション**] の順にクリックします。
    
2. [Search Service アプリケーション: 検索管理] ページで、[**検索先**]、[**新しい結果ソース**] の順にクリックします。
    
3. [**新しい結果ソース**] ウィンドウで、[**名前**] ボックスに新しい検索先の名前 (たとえば、**Microsoft Exchange**) を入力します。 検索 **先プロトコルとして [Exchange]** **を選択し**、[Exchange ソース URL] ボックスに Exchange サーバーの Web サービス ソース **URL を入力** します。 ソース URL は次のような形式です。
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. [**自動検出を使用する**] がオンでないことを確認して、[**OK**] をクリックします。
    
最後に、SharePoint 探索サイトから次の手順を実行して、新しい電子情報開示ケースと新しい電子情報開示セットを作成します (例: https://atl-sharepoint-001/sites/discovery):
  
1. [サイト コンテンツ] ページで、[**新しいケースを作成します**] をクリックします。
    
2. [サイト コンテンツ: 新しい SharePoint サイト] ページで、[**タイトル**] ボックスにユーザーの電子メール エイリアス (たとえば、**kenmyer**) を入力し、同じその URL を [**Web サイトのアドレス**] に追加します。次のような URL になります。
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. [**作成**] をクリックします。
    
4. [電子情報開示セット] ページが表示されたら、[**識別と保存: 情報開示セット**] の下の [**新しいアイテム**] をクリックします。
    
5. [新規: 情報開示セット] ページで、[**情報開示セット名**] ボックスにユーザーの電子メール エイリアスを入力します。 Enter **eDiscovery \\ Lync** _ in the _ *Filter** box and then click Add **Manage &amp; Sources**.
    
6. [ソースの管理の追加] ページで、[メールボックス] の下の最初のテキスト ボックスにユーザーの電子メール エイリアス &amp; **を入力します**。 テキスト ボックスの横にある [メールボックスの確認] アイコンをクリックして、SharePoint が指定のメールボックスに接続できることを確認します。
    
7. [**OK**] をクリックします。
    
8. [電子情報開示セット] ページで、[**保存**] をクリックして新しい電子情報開示セットを保存します。
    
この時点で、指定したメールボックス (kenmyer) を検索したり、他の SharePoint コンテンツまたは検索ソースと同じ方法で In-Place の保持を有効にできます。
  

