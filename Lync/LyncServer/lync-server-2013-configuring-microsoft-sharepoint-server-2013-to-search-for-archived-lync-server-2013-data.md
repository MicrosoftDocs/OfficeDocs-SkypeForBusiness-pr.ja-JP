---
title: 'Lync Server 2013: Microsoft SharePoint Server 2013 を構成して、アーカイブされた Lync Server の2013データを検索する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d831638cf25df4f9c1b792c34815e8bed8c15e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525874"
---
# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>Microsoft SharePoint Server 2013 を構成して、アーカイブされた Microsoft Lync Server 2013 データを検索する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-04_

Microsoft Lync Server 2013 ではなく、Microsoft Exchange Server 2013 でインスタントメッセージングと Web 会議のトランスクリプトを格納する主な利点の1つは、管理者が1つのツールを使用して、アーカイブされた Exchange データやアーカイブされた Lync Server データを検索できることです。 すべてのデータが同じ場所 (Exchange) に保存されるため、アーカイブされた Exchange データを検索できるツールも、アーカイブされた Lync Server データを検索できます。

アーカイブされたデータを簡単に検索できるようにするツールの1つは、Microsoft SharePoint Server 2013 です。 SharePoint を使用して Lync Server データを検索する場合は、まず、「Lync Server での Exchange アーカイブの構成に必要な手順」に記載されているすべての手順を完了する必要があります。 Exchange 2013 と Lync Server 2013 が正常に統合された後で、Exchange Web Services Managed API Version 2.0 を SharePoint サーバーにインストールする必要があります。その API のセットアッププログラムは、Microsoft ダウンロードセンター () からダウンロードでき [https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305) ます。 ダウンロードしたファイル (EWSManagedAPI.msi) は、SharePoint サーバー上の任意のフォルダーに保存できます。

ファイルをダウンロードした後、SharePoint サーバー上で次の手順を実行します。

1.  [**スタート**]、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックして、コマンド ウィンドウを開きます。

2.  コマンド ウィンドウで、**cd** コマンドを使用して、EWSManagedAPI.msi ファイルが保存されているフォルダーに現在のディレクトリを変更します。 たとえば、ファイルを C: ダウンロードに保存した場合は、 \\ コマンドウィンドウに次のコマンドを入力し、enter キーを押します。
    
        cd C:\Downloads

3.  API をインストールするには、次のコマンドを入力して、Enter キーを押します。
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  API がインストールされたら、次のコマンドを入力して Enter キーを押して、IIS をリセットします。
    
        iisreset

Exchange Web サービスがインストールされたら、SharePoint Server 2013 と Exchange 2013 の間のサーバー間認証を構成する必要があります。 これを行うには、まず SharePoint 2013 管理シェルを開き、次のコマンドセットを実行します。

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> 自動検出サービスの URI を使用してください。 サンプル URI は使用しないでください https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 。



</div>

トークン発行元を作成し、トークンサービスを構成した後、次のコマンドを実行して、サンプル URL の SharePoint サイトの URL に置き換えられていることを確認してください。 http://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Exchange 2013 のサーバー間認証を構成するには、exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange がドライブ C: にインストールされており、既定のフォルダーパスを使用していることを前提としています)。

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

パートナーアプリケーションを構成した後、すべての Exchange メールボックスサーバーおよびクライアントアクセスサーバー上でインターネットインフォメーションサービス (IIS) を停止および再起動することをお勧めします。 IIS を再起動するには、次のようなコマンドを使用します。これにより、コンピュータ atl-fs-01 でサービスが再起動されます。

    iisreset atl-exchange-001

このコマンドは、Exchange 管理シェルまたは他の任意のコマンドウィンドウから実行できます。

次に、次のようなコマンドを実行します。指定されたユーザー (この例では kenmyer) は、Exchange での検出を実行する権限を付与します。

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

Exchange と SharePoint の間でサーバー間の認証が確立されたら、次の手順では、SharePoint で電子情報開示サイトを作成します。 これを行うには、SharePoint 管理シェルから次のようなコマンドを実行します。

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> "電子情報開示" とは、通常、訴訟において "証拠になり得ると合理的に判断できる" 項目の電子的アーカイブを参照するプロセスを表します。



</div>

新しいサイトの準備が整ったら、次の手順では、SharePoint の検索先として機能するように Exchange 2013 を構成します。 これを行うには、SharePoint 2013 の [サーバーの全体管理] ページで次の手順を実行します。

1.  サーバーの全体管理ページで、[**サービス アプリケーションの管理**]、[**Search Service アプリケーション**] の順にクリックします。

2.  [Search Service アプリケーション: 検索管理] ページで、[**検索先**]、[**新しい結果ソース**] の順にクリックします。

3.  [**新しい結果ソース**] ウィンドウで、[**名前**] ボックスに新しい検索先の名前 (たとえば、**Microsoft Exchange**) を入力します。 検索先**プロトコル**として [ **exchange** ] を選択し、exchange サーバーの WEB サービスのソース Url を [ **exchange ソース url** ] ボックスに入力します。 ソース URL は次のような形式です。
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  [**自動検出を使用する**] がオンでないことを確認して、[**OK**] をクリックします。

最後に、SharePoint 探索サイトから以下の手順を実行して、新しい電子情報開示ケースと新しい電子情報開示セットを作成します (例: https://atl-sharepoint-001/sites/discovery):

1.  [サイト コンテンツ] ページで、[**新しいケースを作成します**] をクリックします。

2.  [サイト コンテンツ: 新しい SharePoint サイト] ページで、[**タイトル**] ボックスにユーザーの電子メール エイリアス (たとえば、**kenmyer**) を入力し、同じその URL を [**Web サイトのアドレス**] に追加します。次のような URL になります。
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  [**作成**] をクリックします。

4.  [電子情報開示セット] ページが表示されたら、[**識別と保存: 情報開示セット**] の下の [**新しいアイテム**] をクリックします。

5.  [新規: 情報開示セット] ページで、[**情報開示セット名**] ボックスにユーザーの電子メール エイリアスを入力します。 [**フィルター** ] ボックスに「**電子情報開示 Lync \* ** 」と入力し、[追加] をクリックして [ソースの**管理 &** します。

6.  [ソースの追加/管理] ページで、[**メールボックス**] の下の最初のテキスト ボックスにユーザーの電子メール エイリアスを入力します。テキスト ボックスの横にある [メールボックスの確認] アイコンをクリックして、SharePoint が指定のメールボックスに接続できることを確認します。

7.  [**OK**] をクリックします。

8.  [電子情報開示セット] ページで、[**保存**] をクリックして新しい電子情報開示セットを保存します。

この時点で、指定されたメールボックス (kenmyer) を検索したり、他の SharePoint コンテンツまたは検索先に対して行うのと同じ方法で In-Place 保持を有効にしたりすることができます。

</div>

<span> </span>

</div>

</div>

</div>

