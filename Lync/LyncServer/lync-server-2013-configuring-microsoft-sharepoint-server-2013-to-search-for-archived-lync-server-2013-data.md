---
title: 'Lync Server 2013: アーカイブされた Lync Server 2013 データを検索するように Microsoft SharePoint Server 2013 を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 381db352aae635358dfd62cc1965ea238960bf8a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a><span data-ttu-id="2d64b-102">Microsoft SharePoint Server 2013 を構成してアーカイブされた Microsoft Lync Server 2013 データを検索する</span><span class="sxs-lookup"><span data-stu-id="2d64b-102">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d64b-103">_**最終更新日:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="2d64b-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="2d64b-104">Microsoft Lync Server 2013 ではなく、Microsoft Exchange Server 2013 でインスタントメッセージングと Web 会議のトランスクリプトを保存する主な利点の1つは、同じ場所にデータを保存することで、管理者が単一のツールを使用して検索できるようになることです。アーカイブされた Exchange データやアーカイブされた Lync Server データの場合。</span><span class="sxs-lookup"><span data-stu-id="2d64b-104">One of the major advantages to storing instant messaging and Web conferencing transcripts in Microsoft Exchange Server 2013 instead of Microsoft Lync Server 2013 is the fact that storing data in the same location enables administrators to use a single tool to search for archived Exchange data and/or archived Lync Server data.</span></span> <span data-ttu-id="2d64b-105">すべてのデータは同じ場所に保存されるため (Exchange) アーカイブされた Exchange データを検索できるすべてのツールは、アーカイブされた Lync Server データを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d64b-105">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Lync Server data.</span></span>

<span data-ttu-id="2d64b-106">アーカイブデータを検索しやすくするツールの1つは、Microsoft SharePoint Server 2013 です。</span><span class="sxs-lookup"><span data-stu-id="2d64b-106">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="2d64b-107">SharePoint を使って Lync Server データを検索する場合は、まず、Lync Server での Exchange アーカイブの構成に関連するすべての手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d64b-107">If you would like to use SharePoint to search for Lync Server data, you must first complete all the steps involved in configuring Exchange archiving in Lync Server.</span></span> <span data-ttu-id="2d64b-108">Exchange 2013 と Lync Server 2013 の統合が正常に完了したら、Exchange Web Services Managed API バージョン2.0 を SharePoint サーバーにインストールする必要があります。その API のセットアッププログラムは、Microsoft ダウンロードセンター ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)) からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="2d64b-108">After Exchange 2013 and Lync Server 2013 have been successfully integrated you must then install the Exchange Web Services Managed API Version 2.0 on your SharePoint Server; the setup program for that API can be downloaded from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)).</span></span> <span data-ttu-id="2d64b-109">ダウンロードしたファイル (EWSManagedAPI.msi) は、SharePoint サーバーのどのフォルダーにでも保存できます。</span><span class="sxs-lookup"><span data-stu-id="2d64b-109">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>

<span data-ttu-id="2d64b-110">ファイルをダウンロードした後、SharePoint サーバー上で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-110">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>

1.  <span data-ttu-id="2d64b-111">[**スタート**]、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックして、コマンド ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d64b-111">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>

2.  <span data-ttu-id="2d64b-112">コマンド ウィンドウで、**cd** コマンドを使用して、EWSManagedAPI.msi ファイルが保存されているフォルダーに現在のディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-112">In the command window, use the **cd** command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="2d64b-113">たとえば、ファイルを C\\に保存した場合は、コマンドウィンドウに次のコマンドを入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-113">For example, if you have saved the file to C:\\Downloads type the following command in the command window and then press ENTER:</span></span>
    
        cd C:\Downloads

3.  <span data-ttu-id="2d64b-114">API をインストールするには、次のコマンドを入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-114">To install the API, type the following command then press ENTER:</span></span>
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  <span data-ttu-id="2d64b-115">API がインストールされたら、次のコマンドを入力して Enter キーを押して、IIS をリセットします。</span><span class="sxs-lookup"><span data-stu-id="2d64b-115">After the API has been installed, reset IIS by typing the following command and pressing ENTER:</span></span>
    
        iisreset

<span data-ttu-id="2d64b-116">Exchange Web Services がインストールされたら、SharePoint Server 2013 と Exchange 2013 の間のサーバー間認証を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d64b-116">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="2d64b-117">これを行うには、まず SharePoint 2013 管理シェルを開き、次のコマンドセットを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-117">To do this, first open the SharePoint 2013 Management Shell and run the following set of command:</span></span>

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> <span data-ttu-id="2d64b-118">自動検出サービスの URI を使用してください。</span><span class="sxs-lookup"><span data-stu-id="2d64b-118">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="2d64b-119">サンプル URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2d64b-119">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span>



</div>

<span data-ttu-id="2d64b-120">トークン発行者を作成し、トークンサービスを構成したら、次のコマンドを実行します。 SharePoint サイトの URL は、サンプル URL に置き換えてください。http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="2d64b-120">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

<span data-ttu-id="2d64b-121">Exchange 2013 のサーバー間認証を構成するには、exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange がドライブ C にインストールされていること、および既定のフォルダーパスを使用していることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="2d64b-121">To configure server-to-server authentication for Exchange 2013, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

<span data-ttu-id="2d64b-122">パートナーアプリケーションを構成した後、すべての Exchange メールボックスとクライアントアクセスサーバーでインターネットインフォメーションサービス (IIS) を停止して再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2d64b-122">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="2d64b-123">次のようなコマンドを使用して、IIS を再起動することができます。これは、コンピューターの atl-exchange-001 のサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-123">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="2d64b-124">このコマンドは、Exchange 管理シェルから、または他の任意のコマンドウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="2d64b-124">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>

<span data-ttu-id="2d64b-125">次に、次のようなコマンドを実行します。これにより、指定したユーザー (この例では、kenmyer) が Exchange で検出する権利を付与します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-125">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

<span data-ttu-id="2d64b-126">Exchange と SharePoint の間でサーバー間認証が確立されたら、次の手順は SharePoint で電子情報開示サイトを作成することです。</span><span class="sxs-lookup"><span data-stu-id="2d64b-126">After server-to-server authentication has been established between Exchange and SharePoint your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="2d64b-127">そのためには、SharePoint 管理シェルと同じようにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-127">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> <span data-ttu-id="2d64b-128">"電子情報開示" とは、通常、訴訟において "証拠になり得ると合理的に判断できる" 項目の電子的アーカイブを参照するプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-128">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span>



</div>

<span data-ttu-id="2d64b-129">新しいサイトの準備ができたら、次の手順では、SharePoint の検索先として動作するように Exchange 2013 を構成します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-129">When the new site is ready, the next step is to configure Exchange 2013 to act as a result source for SharePoint.</span></span> <span data-ttu-id="2d64b-130">そのためには、SharePoint 2013 の [サーバーの全体管理] ページで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-130">You can do that by completing the following procedure from the SharePoint 2013 Central Administration page:</span></span>

1.  <span data-ttu-id="2d64b-131">サーバーの全体管理ページで、[**サービス アプリケーションの管理**]、[**Search Service アプリケーション**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d64b-131">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>

2.  <span data-ttu-id="2d64b-132">[Search Service アプリケーション: 検索管理] ページで、[**検索先**]、[**新しい結果ソース**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d64b-132">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>

3.  <span data-ttu-id="2d64b-133">[**新しい結果ソース**] ウィンドウで、[**名前**] ボックスに新しい検索先の名前 (たとえば、**Microsoft Exchange**) を入力します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-133">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="2d64b-134">検索先**プロトコル**として [ **exchange** ] を選択し、[exchange の**ソース url** ] ボックスに exchange SERVER の web サービスのソース url を入力します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-134">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="2d64b-135">ソース URL は次のような形式です。</span><span class="sxs-lookup"><span data-stu-id="2d64b-135">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  <span data-ttu-id="2d64b-136">[**自動検出を使用する**] がオンでないことを確認して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d64b-136">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>

<span data-ttu-id="2d64b-137">最後に、SharePoint 検出サイトから次の手順を実行して、新しい電子情報開示ケースと新しい電子情報開示セットを作成します (たとえば、https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="2d64b-137">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>

1.  <span data-ttu-id="2d64b-138">[サイト コンテンツ] ページで、[**新しいケースを作成します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d64b-138">On the Site Contents page click **Create a new case**.</span></span>

2.  <span data-ttu-id="2d64b-p110">[サイト コンテンツ: 新しい SharePoint サイト] ページで、[**タイトル**] ボックスにユーザーの電子メール エイリアス (たとえば、**kenmyer**) を入力し、同じその URL を [**Web サイトのアドレス**] ボックスに追加します。次のような URL になります。</span><span class="sxs-lookup"><span data-stu-id="2d64b-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  <span data-ttu-id="2d64b-141">[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d64b-141">Click **Create**.</span></span>

4.  <span data-ttu-id="2d64b-142">[電子情報開示セット] ページが表示されたら、[**識別と保存: 情報開示セット**] の下の [**新しいアイテム**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d64b-142">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>

5.  <span data-ttu-id="2d64b-143">[新規: 情報開示セット] ページで、[**情報開示セット名**] ボックスにユーザーの電子メール エイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-143">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="2d64b-144">[**フィルター** ] ボックスに**電子情報開示 Lync\* **を入力し、[追加] をクリックして [ソースの**管理 &** ます。</span><span class="sxs-lookup"><span data-stu-id="2d64b-144">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add & Manage Sources**.</span></span>

6.  <span data-ttu-id="2d64b-p112">[ソースの追加/管理] ページで、[**メールボックス**] の下の最初のテキスト ボックスにユーザーの電子メール エイリアスを入力します。テキスト ボックスの横にある [メールボックスの確認] アイコンをクリックして、SharePoint が指定のメールボックスに接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-p112">On the Add & Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**. Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>

7.  <span data-ttu-id="2d64b-147">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d64b-147">Click **OK**.</span></span>

8.  <span data-ttu-id="2d64b-148">[電子情報開示セット] ページで、[**保存**] をクリックして新しい電子情報開示セットを保存します。</span><span class="sxs-lookup"><span data-stu-id="2d64b-148">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>

<span data-ttu-id="2d64b-149">この時点で、指定したメールボックス (kenmyer) を検索し、他の SharePoint コンテンツや検索先と同じ方法でインプレース保持を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2d64b-149">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

