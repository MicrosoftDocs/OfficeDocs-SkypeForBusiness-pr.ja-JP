---
title: 'Lync Server 2013: アーカイブされた Lync Server 2013 データを検索するように Microsoft SharePoint Server 2013 を構成する'
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
ms.openlocfilehash: 1e000f6116b112b3de9840c22c29510745303035
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>Microsoft SharePoint Server 2013 を構成してアーカイブされた Microsoft Lync Server 2013 データを検索する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-04_

Microsoft Lync Server 2013 ではなく、Microsoft Exchange Server 2013 でインスタントメッセージングと Web 会議のトランスクリプトを保存する主な利点の1つは、同じ場所にデータを保存することで、管理者が単一のツールを使用してアーカイブされた Exchange データやアーカイブされた Lync Server データを検索できることです。 すべてのデータは同じ場所に保存されるため (Exchange) アーカイブされた Exchange データを検索できるすべてのツールは、アーカイブされた Lync Server データを検索することもできます。

アーカイブデータを検索しやすくするツールの1つは、Microsoft SharePoint Server 2013 です。 SharePoint を使って Lync Server データを検索する場合は、まず、Lync Server での Exchange アーカイブの構成に関連するすべての手順を完了する必要があります。 Exchange 2013 と Lync Server 2013 の統合が正常に完了したら、Exchange Web Services Managed API バージョン2.0 を SharePoint サーバーにインストールする必要があります。その API のセットアッププログラムは、Microsoft ダウンロードセンター ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)) からダウンロードできます。 ダウンロードしたファイル (EWSManagedAPI.msi) は、SharePoint サーバーのどのフォルダーにでも保存できます。

ファイルをダウンロードした後、SharePoint サーバー上で次の手順を実行します。

1.  [**スタート**]、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックして、コマンド ウィンドウを開きます。

2.  コマンド ウィンドウで、**cd** コマンドを使用して、EWSManagedAPI.msi ファイルが保存されているフォルダーに現在のディレクトリを変更します。 たとえば、ファイルを C\\に保存した場合は、コマンドウィンドウに次のコマンドを入力して、enter キーを押します。
    
        cd C:\Downloads

3.  API をインストールするには、次のコマンドを入力して、Enter キーを押します。
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  API がインストールされたら、次のコマンドを入力して Enter キーを押して、IIS をリセットします。
    
        iisreset

Exchange Web Services がインストールされたら、SharePoint Server 2013 と Exchange 2013 の間のサーバー間認証を構成する必要があります。 これを行うには、まず SharePoint 2013 管理シェルを開き、次のコマンドセットを実行します。

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> 自動検出サービスの URI を使用してください。 サンプル URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1は使用しないでください。



</div>

トークン発行者を作成し、トークンサービスを構成したら、次のコマンドを実行します。 SharePoint サイトの URL は、サンプル URL に置き換えてください。http://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Exchange 2013 のサーバー間認証を構成するには、exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange がドライブ C にインストールされていること、および既定のフォルダーパスを使用していることを前提としています)。

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

パートナーアプリケーションを構成した後、すべての Exchange メールボックスとクライアントアクセスサーバーでインターネットインフォメーションサービス (IIS) を停止して再起動することをお勧めします。 次のようなコマンドを使用して、IIS を再起動することができます。これは、コンピューターの atl-exchange-001 のサービスを再起動します。

    iisreset atl-exchange-001

このコマンドは、Exchange 管理シェルから、または他の任意のコマンドウィンドウから実行できます。

次に、次のようなコマンドを実行します。これにより、指定したユーザー (この例では、kenmyer) が Exchange で検出する権利を付与します。

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

Exchange と SharePoint の間でサーバー間認証が確立されたら、次の手順は SharePoint で電子情報開示サイトを作成することです。 そのためには、SharePoint 管理シェルと同じようにコマンドを実行します。

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> "電子情報開示" とは、通常、訴訟において "証拠になり得ると合理的に判断できる" 項目の電子的アーカイブを参照するプロセスを表します。



</div>

新しいサイトの準備ができたら、次の手順では、SharePoint の検索先として動作するように Exchange 2013 を構成します。 そのためには、SharePoint 2013 の [サーバーの全体管理] ページで次の手順を実行します。

1.  サーバーの全体管理ページで、[**サービス アプリケーションの管理**]、[**Search Service アプリケーション**] の順にクリックします。

2.  [Search Service アプリケーション: 検索管理] ページで、[**検索先**]、[**新しい結果ソース**] の順にクリックします。

3.  [**新しい結果ソース**] ウィンドウで、[**名前**] ボックスに新しい検索先の名前 (たとえば、**Microsoft Exchange**) を入力します。 検索先**プロトコル**として [ **exchange** ] を選択し、[exchange の**ソース url** ] ボックスに exchange SERVER の web サービスのソース url を入力します。 ソース URL は次のような形式です。
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  [**自動検出を使用する**] がオンでないことを確認して、[**OK**] をクリックします。

最後に、SharePoint 検出サイトから次の手順を実行して、新しい電子情報開示ケースと新しい電子情報開示セットを作成します (たとえば、https://atl-sharepoint-001/sites/discovery):

1.  [サイト コンテンツ] ページで、[**新しいケースを作成します**] をクリックします。

2.  [サイト コンテンツ: 新しい SharePoint サイト] ページで、[**タイトル**] ボックスにユーザーの電子メール エイリアス (たとえば、**kenmyer**) を入力し、同じその URL を [**Web サイトのアドレス**] ボックスに追加します。次のような URL になります。
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  [**作成**] をクリックします。

4.  [電子情報開示セット] ページが表示されたら、[**識別と保存: 情報開示セット**] の下の [**新しいアイテム**] をクリックします。

5.  [新規: 情報開示セット] ページで、[**情報開示セット名**] ボックスにユーザーの電子メール エイリアスを入力します。 [**フィルター** ] ボックスに**電子情報開示 Lync\* **を入力し、[追加] をクリックして [ソースの**管理 &** ます。

6.  [ソースの追加/管理] ページで、[**メールボックス**] の下の最初のテキスト ボックスにユーザーの電子メール エイリアスを入力します。テキスト ボックスの横にある [メールボックスの確認] アイコンをクリックして、SharePoint が指定のメールボックスに接続できることを確認します。

7.  [**OK**] をクリックします。

8.  [電子情報開示セット] ページで、[**保存**] をクリックして新しい電子情報開示セットを保存します。

この時点で、指定したメールボックス (kenmyer) を検索し、他の SharePoint コンテンツや検索先と同じ方法でインプレース保持を有効にすることができます。

</div>

<span> </span>

</div>

</div>

</div>

