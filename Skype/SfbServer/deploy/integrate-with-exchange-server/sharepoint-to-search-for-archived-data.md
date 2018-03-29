---
title: アーカイブされた Skype for Business データを検索するための SharePoint Server の構成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: '概要: ビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 と Skype でアーカイブ データを検索するのには SharePoint サーバーを構成します。'
ms.openlocfilehash: 161e4dd530490d22d14f5392539e2cc3d788d6bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>アーカイブされた Skype for Business データを検索するための SharePoint Server の構成
 
**の概要:**ビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 と Skype でアーカイブされたデータを検索するのには SharePoint サーバーを構成します。
  
ビジネス サーバー 2015 の Exchange Server 2016 または Skype ではなく、Exchange Server 2013 でインスタント メッセージング、Web 会議の議事録を保存するための大きな利点の 1 つは、同じ場所にデータを格納できる管理者を 1 つのツールを使用するにはExchange のアーカイブ ・ データとアーカイブ済みの Skype ビジネス サーバーのデータを検索します。 (交換) するために同じデータが保存されているすべて、Exchange のアーカイブ ・ データを検索できるツールがビジネスのサーバーのデータのアーカイブされた Skype の検索もできます。
  
アーカイブされたデータを検索しやすい 1 つのツールは、Microsoft SharePoint Server 2013 です。 Skype のビジネス サーバーのデータを検索する SharePoint を使用する場合は、Exchange が Skype のビジネス サーバーのアーカイブを構成するのに関連するすべての手順を完了してする必要があります。 Exchange Server と Skype のビジネス サーバーが正常に統合された後、し、SharePoint サーバー上で Exchange [Web サービスの管理 API](https://go.microsoft.com/fwlink/p/?LinkId=258305)をインストールしてください。 ダウンロードしたファイル (EWSManagedAPI.msi) は、SharePoint サーバーのどのフォルダーにでも保存できます。
  
ファイルをダウンロードした後、SharePoint サーバー上で次の手順を実行します。
  
1. [**スタート**]、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックして、コマンド ウィンドウを開きます。
    
2. [コマンド] ウィンドウで、EWSManagedAPI.msi ファイルが保存されているフォルダーに現在のディレクトリを変更するのには、cd コマンドを使用します。 、C:\Downloads にファイルを保存した場合コマンド ウィンドウで次のコマンドを入力して Enter キーを押します。
    
   ```
   cd C:\Downloads
   ```

3. API をインストールするには、次のコマンドを入力し、Enter キーを押します。
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. API をインストールすると、次のコマンドを入力し、Enter キーを押して、IIS をリセットします。
    
   ```
   iisreset
   ```

Exchange Web サービスをインストールした後は、SharePoint Server と Exchange Server 間でサーバーからサーバーへの認証を構成する必要があります。 これを行うには、まず SharePoint 管理シェルを開くし、次の一連のコマンドを実行します。
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> 自動検出サービスの URI を使用してください。 サンプル URI を使用しないhttps://autodiscover.litwareinc.com/autodiscover/metadata/json/1。 
  
トークンの発行元を作成して、トークン サービスを構成することが後、は、SharePoint サイトの URL の代わりにサンプルの URL を確認するこれらのコマンドを実行します。http://atl-sharepoint-001:
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Exchange Server のサーバーからサーバーへの認証を構成するには、Exchange 管理シェルを開くし、(と仮定すると、Exchange は、ドライブ c: にインストールされているし、既定のフォルダーのパスを使用する) は、次のようなコマンドを実行します。
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

パートナー アプリケーションを構成した後、停止し、すべての Exchange メールボックスおよびクライアント アクセス サーバーのインターネット インフォメーション サービス (IIS) を再起動することをお勧めします。 コマンドを使用して、次のようなコンピューター atl-exchange-001 のサービスを再起動する、IIS を再起動することができます。
  
```
iisreset atl-exchange-001
```

このコマンドは、Exchange 管理シェル内でまたは他の任意のコマンド ウィンドウから実行できます。
  
次に、Exchange 上での検出を実行する権限 (kenmyer など) で指定されたユーザーは、次のようなコマンドを実行します。
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Exchange と SharePoint のサーバーからサーバーへの認証が確立された後、次に、SharePoint で、電子的証拠開示のサイトを作成します。 SharePoint 管理シェルから以下のようなコマンドを実行することによって行えます。
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> "電子情報開示" とは、通常、訴訟において "証拠になり得ると合理的に判断できる" 項目の電子的アーカイブを参照するプロセスを表します。 
  
新しいサイトの準備ができたら、次に、SharePoint の結果としてソースを動作するように Exchange Server を構成します。 SharePoint サーバーの全体管理ページから次の手順を完了しているを行うことができます。
  
1. サーバーの全体管理ページで、[**サービス アプリケーションの管理**]、[**Search Service アプリケーション**] の順にクリックします。
    
2. [Search Service アプリケーション: 検索管理] ページで、[**検索先**]、[**新しい結果ソース**] の順にクリックします。
    
3. [**新しい結果ソース**] ウィンドウで、[**名前**] ボックスに新しい検索先の名前 (たとえば、**Microsoft Exchange**) を入力します。 **交換****プロトコル**では、結果のソースとして] を選択し、 **Exchange ソースの URL** ] ボックスに Exchange サーバーの web サービスのソースの URL を入力します。 ソース URL は次のような形式です。
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. [**自動検出を使用する**] がオンでないことを確認して、[**OK**] をクリックします。
    
最後に、新しい電子的証拠開示のケースと、新しい電子的証拠開示 (たとえば、SharePoint 検索サイトから次の手順を実行して設定を作成します。https://atl-sharepoint-001/sites/discovery):
  
1. [サイト コンテンツ] ページで、[**新しいケースを作成します**] をクリックします。
    
2. [サイト コンテンツ: 新しい SharePoint サイト] ページで、[**タイトル**] ボックスにユーザーの電子メール エイリアス (たとえば、**kenmyer**) を入力し、同じその URL を [**Web サイトのアドレス**] ボックスに追加します。次のような URL になります。
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. [**作成**] をクリックします。
    
4. [電子情報開示セット] ページが表示されたら、[**識別と保存: 情報開示セット**] の下の [**新しいアイテム**] をクリックします。
    
5. [新規: 情報開示セット] ページで、[**情報開示セット名**] ボックスにユーザーの電子メール エイリアスを入力します。 入力**電子的証拠開示 Lync\* ** [**フィルター** ] ボックスをクリック**追加&amp;ソースの管理**です。
    
6. 追加&amp;ソースの管理] ページで、[**メールボックス]**の最初のテキスト ボックスにユーザーの電子メール エイリアスを入力します。 テキスト ボックスの横にある [メールボックスの確認] アイコンをクリックして、SharePoint が指定のメールボックスに接続できることを確認します。
    
7. [**OK**] をクリックします。
    
8. [電子情報開示セット] ページで、[**保存**] をクリックして新しい電子情報開示セットを保存します。
    
この時点で指定したメールボックス (kenmyer) を検索することや、場で有効にするが、他の SharePoint コンテンツまたは結果ソースの場合と同じ方法を保持しています。
  

