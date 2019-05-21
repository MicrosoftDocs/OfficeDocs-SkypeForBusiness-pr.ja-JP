---
title: アーカイブされた Skype for Business データを検索するための SharePoint Server の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: '概要: Exchange Server および Skype for Business Server によってアーカイブされたデータを検索するように SharePoint Server を構成します。'
ms.openlocfilehash: 2fb4b601e594ca48105afcf2e0c75107b2c6bceb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278078"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>アーカイブされた Skype for Business データを検索するための SharePoint Server の構成
 
**概要:** Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server によってアーカイブされたデータを検索するように SharePoint Server を構成します。
  
Skype for Business Server の代わりに Exchange Server でインスタントメッセージングと Web 会議のトランスクリプトを保存する主な利点の1つは、同じ場所にデータを保存することで、管理者が単一のツールを使用してアーカイブされた Exchange データを検索できることです。または、アーカイブされた Skype for Business Server データ。 すべてのデータが同じ場所に保存されるため (Exchange) アーカイブされた Exchange データを検索できるすべてのツールは、アーカイブされた Skype for Business Server データを検索することもできます。
  
アーカイブデータを検索しやすくするツールの1つは、Microsoft SharePoint Server 2013 です。 SharePoint を使って Skype for Business Server データを検索する場合は、まず、「Skype for Business Server で Exchange アーカイブを構成する」に記載されているすべての手順を実行する必要があります。 Exchange Server と Skype for Business Server が正常に統合されたら、SharePoint Server に Exchange [Web Services 管理 API](https://go.microsoft.com/fwlink/p/?LinkId=258305)をインストールする必要があります。 ダウンロードしたファイル (EWSManagedAPI.msi) は、SharePoint サーバーのどのフォルダーにでも保存できます。
  
ファイルをダウンロードした後、SharePoint サーバー上で次の手順を実行します。
  
1. [**スタート**]、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックして、コマンド ウィンドウを開きます。
    
2. コマンド ウィンドウで、cd コマンドを使用して、EWSManagedAPI.msi ファイルが保存されているフォルダーに現在のディレクトリを変更します。 たとえば、ファイルを c: に保存した場合は、コマンドウィンドウに次のコマンドを入力し、enter キーを押します。
    
   ```
   cd C:\Downloads
   ```

3. API をインストールするには、次のコマンドを入力し、enter キーを押します。
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. API をインストールした後、次のコマンドを入力し、Enter キーを押して、IIS をリセットします。
    
   ```
   iisreset
   ```

Exchange Web サービスのインストールが完了したら、SharePoint Server と Exchange Server の間のサーバー間認証を構成する必要があります。 これを行うには、まず SharePoint 管理シェルを開き、次のコマンドを実行します。
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> 自動検出サービスの URI を使用してください。 サンプル URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1は使用しないでください。 
  
トークン発行者を作成し、トークンサービスを構成したら、次のコマンドを実行します。 SharePoint サイトの URL は、サンプル URL に置き換えてください。http://atl-sharepoint-001:
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Exchange Server のサーバー間認証を構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange がドライブ C にインストールされていること、および既定のフォルダーパスを使用していることを前提としています)。
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

パートナーアプリケーションを構成した後、すべての Exchange メールボックスとクライアントアクセスサーバーでインターネットインフォメーションサービス (IIS) を停止して再起動することをお勧めします。 次のようなコマンドを使用して、IIS を再起動することができます。これは、コンピューターの atl-exchange-001 のサービスを再起動します。
  
```
iisreset atl-exchange-001
```

このコマンドは、Exchange 管理シェルから、または他の任意のコマンドウィンドウから実行できます。
  
次に、次のようなコマンドを実行します。これにより、指定したユーザー (この例では、kenmyer) が Exchange で検出する権利を付与します。
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Exchange と SharePoint の間でサーバー間の認証が確立されたら、次の手順として、SharePoint で電子情報開示サイトを作成します。 そのためには、SharePoint 管理シェルと同じようにコマンドを実行します。
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> "電子情報開示" とは、通常、訴訟において "証拠になり得ると合理的に判断できる" 項目の電子的アーカイブを参照するプロセスを表します。 
  
新しいサイトの準備ができたら、次の手順として、SharePoint の検索先として動作するように Exchange Server を構成します。 そのためには、SharePoint サーバーの全体管理ページで次の手順を実行します。
  
1. サーバーの全体管理ページで、[**サービス アプリケーションの管理**]、[**Search Service アプリケーション**] の順にクリックします。
    
2. [Search Service アプリケーション: 検索管理] ページで、[**検索先**]、[**新しい結果ソース**] の順にクリックします。
    
3. [**新しい結果ソース**] ウィンドウで、[**名前**] ボックスに新しい検索先の名前 (たとえば、**Microsoft Exchange**) を入力します。 検索先**プロトコル**として [ **exchange** ] を選択し、[exchange の**ソース url** ] ボックスに exchange SERVER の web サービスのソース url を入力します。 ソース URL は次のような形式です。
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. [**自動検出を使用する**] がオンでないことを確認して、[**OK**] をクリックします。
    
最後に、SharePoint 検出サイトから次の手順を実行して、新しい電子情報開示ケースと新しい電子情報開示セットを作成します (たとえば、https://atl-sharepoint-001/sites/discovery):
  
1. [サイト コンテンツ] ページで、[**新しいケースを作成します**] をクリックします。
    
2. [サイト コンテンツ: 新しい SharePoint サイト] ページで、[**タイトル**] ボックスにユーザーの電子メール エイリアス (たとえば、**kenmyer**) を入力し、同じその URL を [**Web サイトのアドレス**] ボックスに追加します。次のような URL になります。
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. [**作成**] をクリックします。
    
4. [電子情報開示セット] ページが表示されたら、[**識別と保存: 情報開示セット**] の下の [**新しいアイテム**] をクリックします。
    
5. [新規: 情報開示セット] ページで、[**情報開示セット名**] ボックスにユーザーの電子メール エイリアスを入力します。 [**フィルター** ] ボックスに**電子情報開示\\Lync*** と入力し、[**ソースの&amp;管理**] をクリックします。
    
6. [ソースの&amp;管理] ページで、[**メールボックス**] の最初のテキストボックスにユーザーのメールエイリアスを入力します。 テキスト ボックスの横にある [メールボックスの確認] アイコンをクリックして、SharePoint が指定のメールボックスに接続できることを確認します。
    
7. [**OK**] をクリックします。
    
8. [電子情報開示セット] ページで、[**保存**] をクリックして新しい電子情報開示セットを保存します。
    
この時点で、指定したメールボックス (kenmyer) を検索し、他の SharePoint コンテンツや検索先と同じ方法でインプレース保持を有効にすることができます。
  

