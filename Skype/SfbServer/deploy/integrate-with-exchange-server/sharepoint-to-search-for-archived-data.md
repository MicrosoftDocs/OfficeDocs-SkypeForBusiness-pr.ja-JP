---
title: アーカイブSharePointデータを検索するサーバーをSkype for Businessする
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: '概要: サーバー SharePointサーバーでアーカイブされたデータを検索Exchange Server構成Skype for Business Server。'
ms.openlocfilehash: 081b32ad57d97a793867e56f85ad36d62424bacb
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013571"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>アーカイブSharePointデータを検索するサーバーをSkype for Businessする
 
**概要:** 2016 SharePoint 2016 または Exchange Server 2013 および Exchange Serverによってアーカイブされたデータを検索Skype for Business Server。
  
Skype for Business Server ではなく Exchange Server にインスタント メッセージングと Web 会議トランスクリプトを格納する大きな利点の 1 つは、管理者が 1 つのツールを使用してアーカイブされた Exchange データやアーカイブされた Skype for Business Server データを検索できるという方法です。 すべてのデータは同じ場所 (Exchange) に格納されますので、アーカイブされた Exchange データを検索できるツールは、アーカイブされたデータSkype for Business Serverすることもできます。
  
アーカイブされたデータを簡単に検索できるツールの 1 つは、2013 Microsoft SharePoint Serverです。 SharePoint を使用して Skype for Business Server データを検索する場合は、まず、Skype for Business Server での Exchange アーカイブの構成に関連するすべての手順を完了する必要があります。 サーバー Exchange Server Skype for Business Server統合が完了したら、Exchange [Web Services マネージ API](https://go.microsoft.com/fwlink/p/?LinkId=258305)を SharePoint サーバーにインストールする必要があります。 ダウンロードしたファイル (EWSManagedAPI.msi) は、サーバー上の任意のフォルダー SharePointできます。
  
ファイルをダウンロードした後、SharePoint サーバー上で次の手順を実行します。
  
1. [**スタート**]、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックして、コマンド ウィンドウを開きます。
    
2. コマンド ウィンドウで、cd コマンドを使用して、EWSManagedAPI.msi ファイルが保存されているフォルダーに現在のディレクトリを変更します。 たとえば、ファイルを C:\Downloads に保存した場合は、コマンド ウィンドウに次のコマンドを入力し、Enter キーを押します。
    
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

Web Exchangeがインストールされた後、サーバーとサーバー間のサーバー間認証を構成SharePoint必要Exchange Server。 これを行うには、まず管理シェルSharePoint開き、次の一連のコマンドを実行します。
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> 自動検出サービスの URI を使用してください。 サンプル URI を使用しない https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 。 
  
トークン発行者を作成してトークン サービスを構成したら、次のコマンドを実行し、SharePoint サイトの URL をサンプル URL に置き換える必要があります `http://atl-sharepoint-001` 。
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Exchange Server のサーバー間認証を構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange がドライブ C にインストールされ、既定のフォルダー パスが使用されている場合)。
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

パートナー アプリケーションを構成した後は、すべてのメールボックス およびクライアント アクセス サーバーで インターネット インフォメーション サービス (IIS) を停止して再起動Exchangeをお勧めします。 次のようなコマンドを使用して IIS を再起動すると、コンピューター atl-exchange-001 でサービスが再起動されます。
  
```powershell
iisreset atl-exchange-001
```

このコマンドは、管理シェル内Exchange他のコマンド ウィンドウから実行できます。
  
次に、次のようなコマンドを実行し、指定したユーザー (この例では kenmyer) に対して検出を実行する権限を与Exchange。
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

サーバー間認証が Exchange と SharePoint の間で確立された後、次に、電子情報開示サイトを SharePoint で作成します。 これは、次のようなコマンドを管理シェルから実行SharePoint実行できます。
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> "電子情報開示" とは、通常、訴訟において "証拠になり得ると合理的に判断できる" 項目の電子的アーカイブを参照するプロセスを表します。 
  
新しいサイトの準備ができたら、次の手順では、Exchange Serverの結果のソースとして機能SharePoint。 これを行うには、[サーバーの全体管理] ページで次SharePointを実行します。
  
1. サーバーの全体管理ページで、[**サービス アプリケーションの管理**]、[**Search Service アプリケーション**] の順にクリックします。
    
2. [Search Service アプリケーション: 検索管理] ページで、[**検索先**]、[**新しい結果ソース**] の順にクリックします。
    
3. [**新しい結果ソース**] ウィンドウで、[**名前**] ボックスに新しい検索先の名前 (たとえば、**Microsoft Exchange**) を入力します。 **[Exchange]** を選択し、[ソースURL] ボックスに Exchange サーバーの Web サービス ソース **URL を入力Exchangeします**。 ソース URL は次のような形式です。
    
    `https://atl-exchange-001.litwareinc.com/ews/exchange.asmx`
    
4. [**自動検出を使用する**] がオンでないことを確認して、[**OK**] をクリックします。
    
最後に、新しい電子情報開示ケースと新しい電子情報開示セットを作成するには、SharePoint検出サイト (たとえば) から次の手順を実行します `https://atl-sharepoint-001/sites/discovery` 。
  
1. [サイト コンテンツ] ページで、[**新しいケースを作成します**] をクリックします。
    
2. [サイト コンテンツ: 新しい SharePoint サイト] ページで、[**タイトル**] ボックスにユーザーの電子メール エイリアス (たとえば、**kenmyer**) を入力し、同じその URL を [**Web サイトのアドレス**] に追加します。次のような URL になります。
    
    `https://atl-sharepoint-001/sites/eDiscovery/kenmyer`
    
3. [**作成**] をクリックします。
    
4. [電子情報開示セット] ページが表示されたら、[**識別と保存: 情報開示セット**] の下の [**新しいアイテム**] をクリックします。
    
5. [新規: 情報開示セット] ページで、[**情報開示セット名**] ボックスにユーザーの電子メール エイリアスを入力します。 [_ Filter *]ボックスに「電子情報開示 **Lync \\** _」と入力し、[ソースの管理 **の追加 &amp; ] をクリックします**。
    
6. [ソースの管理の追加] ページで、[メールボックス] の下の最初のテキスト ボックスにユーザーのメール &amp; エイリアス **を入力します**。 テキスト ボックスの横にある [メールボックスの確認] アイコンをクリックして、SharePoint が指定のメールボックスに接続できることを確認します。
    
7. [**OK**] をクリックします。
    
8. [電子情報開示セット] ページで、[**保存**] をクリックして新しい電子情報開示セットを保存します。
    
この時点で、指定したメールボックス (kenmyer) を検索したり、In-Place が他の SharePoint コンテンツまたは結果ソースと同じ方法で保持を有効にしたりできます。
  

