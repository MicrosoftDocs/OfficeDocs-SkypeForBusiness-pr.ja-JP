---
title: "アーカイブされた Lync Server 2013 データを検索するための SharePoint Server 2013 の構成"
TOCTitle: "アーカイブされた Lync Server 2013 データを検索するための SharePoint Server 2013 の構成"
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49886856
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アーカイブされた Microsoft Lync Server 2013 データを検索するための Microsoft SharePoint Server 2013 の構成

 

_**トピックの最終更新日:** 2016-12-08_

インスタント メッセージングと Web 会議のトランスクリプトを Microsoft Lync Server 2013 ではなく Microsoft Exchange Server 2013 に格納する主要な利点の 1 つは、データを同じ場所に格納すると、管理者が 1 つのツールを使用して、アーカイブされた Exchange データおよびアーカイブされた Lync Server データを検索できることです。すべてのデータが同じ場所 (Exchange) に格納されているため、アーカイブされた Exchange データを検索できるツールであれば、アーカイブされた Lync Server データも検索できます。

アーカイブ データを簡単に検索できるツールの 1 つが、Microsoft SharePoint Server 2013 です。SharePoint を使用して Lync Server データを検索するには、最初に、Lync Server における Exchange アーカイブの構成に関するすべての手順を実行する必要があります。Exchange 2013 と Lync Server 2013 の統合が行われたら、SharePoint Server に Exchange Web Services Managed API v2.0 をインストールする必要があります。この API のセットアップ プログラムは、Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/?linkid=258305\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=258305%26clcid=0x411)) からダウンロードできます。ダウンロードしたファイル (EWSManagedAPI.msi) は、SharePoint サーバー上の任意のフォルダーに保存できます。

ファイルをダウンロードした後、SharePoint サーバー上で次の手順を実行します。

1.  \[**スタート**\]、\[**すべてのプログラム**\]、\[**アクセサリ**\] の順にクリックし、\[**コマンド プロンプト**\] を右クリックし、\[**管理者として実行**\] をクリックして、コマンド ウィンドウを開きます。

2.  コマンド ウィンドウで、**cd** コマンドを使用して、EWSManagedAPI.msi ファイルが保存されているフォルダーに現在のディレクトリを変更します。たとえば、ファイルが C:\\Downloads に保存されている場合は、コマンド ウィンドウで次のコマンドを入力して、Enter キーを押します。
    
        cd C:\Downloads

3.  API をインストールするには、次のコマンドを入力して、Enter キーを押します。
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  API がインストールされたら、次のコマンドを入力して Enter キーを押して、IIS をリセットします。
    
        iisreset

Exchange Web サービスがインストールされた後、SharePoint Server 2013 と Exchange 2013 の間でサーバー間認証を構成する必要があります。これを行うには、まず SharePoint 2013 管理シェルを開き、次の一連のコマンドを実行します。

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

> [!NOTE]
> 自動検出サービスの URI を使用してください。サンプル URI の https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 は使用しないでください。


トークン発行元を作成し、トークン サービスを構成した後、次のコマンドを実行します。このとき、自分の SharePoint サイトの URL をサンプル URL http://atl-sharepoint-001 に置き換えます。

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Exchange 2013 に対してサーバー間認証を構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (ここでは、Exchange がドライブ C: にインストールされており、既定のフォルダー パスを使用するものとしています)。

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

パートナー アプリケーションを構成した後、すべての Exchange メールボックスおよびクライアント アクセス サーバーでインターネット インフォメーション サービス (IIS) を停止し、再起動することをお勧めします。IIS は、次のようなコマンドを使用して再起動できます。このコマンドでは、コンピューター atl-exchange-001 上のサービスを再起動します。

    iisreset atl-exchange-001

このコマンドは、Exchange 管理シェルまたは他の任意のコマンド ウィンドウから実行できます。

次に、以下のようなコマンドを実行します。このコマンドでは、指定のユーザー (この例では kenmyer) に Exchange で検出を行う権限を付与します。

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

Exchange と SharePoint の間のサーバー間認証が確立された後、SharePoint 内に電子情報開示サイトを作成します。これは、SharePoint 管理シェルから次のようなコマンドを実行することで行うことができます。

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

> [!NOTE]
> &quot;電子情報開示&quot; とは、通常、訴訟において &quot;証拠になり得ると合理的に判断できる&quot; 項目の電子的アーカイブを参照するプロセスを表します。


新しいサイトの準備ができたら、Exchange 2013 が SharePoint の検索先として動作するように構成します。これは、SharePoint 2013 サーバーの全体管理ページで次の手順を実行することによって行うことができます。

1.  サーバーの全体管理ページで、\[**サービス アプリケーションの管理**\]、\[**Search Service アプリケーション**\] の順にクリックします。

2.  \[Search Service アプリケーション: 検索管理\] ページで、\[**検索先**\]、\[**新しい結果ソース**\] の順にクリックします。

3.  \[**新しい結果ソース**\] ウィンドウで、\[**名前**\] ボックスに新しい検索先の名前 (たとえば、**Microsoft Exchange**) を入力します。検索先の \[**プロトコル**\] として \[**Exchange**\] を選択し、\[**Exchange のソース URL**\] ボックスに Exchange サーバーの Web サービスのソース URL を入力します。ソース URL は次のような形式です。
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  \[**自動検出を使用する**\] がオンでないことを確認して、\[**OK**\] をクリックします。

最後に、SharePoint 情報開示サイト (たとえば、https://atl-sharepoint-001/sites/discovery) から次の手順を実行して、新しい電子情報ケースと新しい電子情報開示セットを作成します。

1.  \[サイト コンテンツ\] ページで、\[**新しいケースを作成します**\] をクリックします。

2.  \[サイト コンテンツ: 新しい SharePoint サイト\] ページで、\[**タイトル**\] ボックスにユーザーの電子メール エイリアス (たとえば、**kenmyer**) を入力し、同じその URL を \[**Web サイトのアドレス**\] に追加します。次のような URL になります。
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  \[**作成**\] をクリックします。

4.  \[電子情報開示セット\] ページが表示されたら、\[**識別と保存: 情報開示セット**\] の下の \[**新しいアイテム**\] をクリックします。

5.  \[新規: 情報開示セット\] ページで、\[**情報開示セット名**\] ボックスにユーザーの電子メール エイリアスを入力します。\[**フィルター**\] ボックスに「**eDiscovery Lync\***」と入力し、\[**ソースの追加/管理**\] をクリックします。

6.  \[ソースの追加/管理\] ページで、\[**メールボックス**\] の下の最初のテキスト ボックスにユーザーの電子メール エイリアスを入力します。テキスト ボックスの横にある \[メールボックスの確認\] アイコンをクリックして、SharePoint が指定のメールボックスに接続できることを確認します。

7.  \[**OK**\] をクリックします。

8.  \[電子情報開示セット\] ページで、\[**保存**\] をクリックして新しい電子情報開示セットを保存します。

これで、他の SharePoint コンテンツ ソースまたは検索先に対して行うのと同じように、指定のメールボックス (kenmyer) を検索したり、インプレース保持を有効にしたりできます。

