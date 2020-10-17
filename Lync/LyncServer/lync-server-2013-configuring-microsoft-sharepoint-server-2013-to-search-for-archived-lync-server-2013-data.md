---
title: 'Lync Server 2013: Microsoft SharePoint Server 2013 を構成して、アーカイブされた Lync Server の2013データを検索する'
description: 'Lync Server 2013: Microsoft SharePoint Server 2013 を構成して、アーカイブされた Lync Server の2013データを検索します。'
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
ms.openlocfilehash: aeabe49bb4f4e71bac7017497f3aadd9799bf515
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542763"
---
# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a><span data-ttu-id="6b558-103">Microsoft SharePoint Server 2013 を構成して、アーカイブされた Microsoft Lync Server 2013 データを検索する</span><span class="sxs-lookup"><span data-stu-id="6b558-103">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b558-104">_**トピックの最終更新日:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="6b558-104">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="6b558-105">Microsoft Lync Server 2013 ではなく、Microsoft Exchange Server 2013 でインスタントメッセージングと Web 会議のトランスクリプトを格納する主な利点の1つは、管理者が1つのツールを使用して、アーカイブされた Exchange データやアーカイブされた Lync Server データを検索できることです。</span><span class="sxs-lookup"><span data-stu-id="6b558-105">One of the major advantages to storing instant messaging and Web conferencing transcripts in Microsoft Exchange Server 2013 instead of Microsoft Lync Server 2013 is the fact that storing data in the same location enables administrators to use a single tool to search for archived Exchange data and/or archived Lync Server data.</span></span> <span data-ttu-id="6b558-106">すべてのデータが同じ場所 (Exchange) に保存されるため、アーカイブされた Exchange データを検索できるツールも、アーカイブされた Lync Server データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="6b558-106">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Lync Server data.</span></span>

<span data-ttu-id="6b558-107">アーカイブされたデータを簡単に検索できるようにするツールの1つは、Microsoft SharePoint Server 2013 です。</span><span class="sxs-lookup"><span data-stu-id="6b558-107">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="6b558-108">SharePoint を使用して Lync Server データを検索する場合は、まず、「Lync Server での Exchange アーカイブの構成に必要な手順」に記載されているすべての手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b558-108">If you would like to use SharePoint to search for Lync Server data, you must first complete all the steps involved in configuring Exchange archiving in Lync Server.</span></span> <span data-ttu-id="6b558-109">Exchange 2013 と Lync Server 2013 が正常に統合された後で、Exchange Web Services Managed API Version 2.0 を SharePoint サーバーにインストールする必要があります。その API のセットアッププログラムは、Microsoft ダウンロードセンター () からダウンロードでき [https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305) ます。</span><span class="sxs-lookup"><span data-stu-id="6b558-109">After Exchange 2013 and Lync Server 2013 have been successfully integrated you must then install the Exchange Web Services Managed API Version 2.0 on your SharePoint Server; the setup program for that API can be downloaded from the Microsoft Downloads Center ([https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305)).</span></span> <span data-ttu-id="6b558-110">ダウンロードしたファイル (EWSManagedAPI.msi) は、SharePoint サーバー上の任意のフォルダーに保存できます。</span><span class="sxs-lookup"><span data-stu-id="6b558-110">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>

<span data-ttu-id="6b558-111">ファイルをダウンロードした後、SharePoint サーバー上で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b558-111">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>

1.  <span data-ttu-id="6b558-112">[**スタート**]、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックして、コマンド ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="6b558-112">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>

2.  <span data-ttu-id="6b558-113">コマンド ウィンドウで、**cd** コマンドを使用して、EWSManagedAPI.msi ファイルが保存されているフォルダーに現在のディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="6b558-113">In the command window, use the **cd** command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="6b558-114">たとえば、ファイルを C: ダウンロードに保存した場合は、 \\ コマンドウィンドウに次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6b558-114">For example, if you have saved the file to C:\\Downloads type the following command in the command window and then press ENTER:</span></span>
    
        cd C:\Downloads

3.  <span data-ttu-id="6b558-115">API をインストールするには、次のコマンドを入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6b558-115">To install the API, type the following command then press ENTER:</span></span>
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  <span data-ttu-id="6b558-116">API がインストールされたら、次のコマンドを入力して Enter キーを押して、IIS をリセットします。</span><span class="sxs-lookup"><span data-stu-id="6b558-116">After the API has been installed, reset IIS by typing the following command and pressing ENTER:</span></span>
    
        iisreset

<span data-ttu-id="6b558-117">Exchange Web サービスがインストールされたら、SharePoint Server 2013 と Exchange 2013 の間のサーバー間認証を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b558-117">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="6b558-118">これを行うには、まず SharePoint 2013 管理シェルを開き、次のコマンドセットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b558-118">To do this, first open the SharePoint 2013 Management Shell and run the following set of command:</span></span>

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> <span data-ttu-id="6b558-119">自動検出サービスの URI を使用してください。</span><span class="sxs-lookup"><span data-stu-id="6b558-119">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="6b558-120">サンプル URI は使用しないでください https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 。</span><span class="sxs-lookup"><span data-stu-id="6b558-120">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span>



</div>

<span data-ttu-id="6b558-121">トークン発行元を作成し、トークンサービスを構成した後、次のコマンドを実行して、サンプル URL の SharePoint サイトの URL に置き換えられていることを確認してください。 http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="6b558-121">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

<span data-ttu-id="6b558-122">Exchange 2013 のサーバー間認証を構成するには、exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange がドライブ C: にインストールされており、既定のフォルダーパスを使用していることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="6b558-122">To configure server-to-server authentication for Exchange 2013, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

<span data-ttu-id="6b558-123">パートナーアプリケーションを構成した後、すべての Exchange メールボックスサーバーおよびクライアントアクセスサーバー上でインターネットインフォメーションサービス (IIS) を停止および再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b558-123">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="6b558-124">IIS を再起動するには、次のようなコマンドを使用します。これにより、コンピュータ atl-fs-01 でサービスが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="6b558-124">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="6b558-125">このコマンドは、Exchange 管理シェルまたは他の任意のコマンドウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="6b558-125">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>

<span data-ttu-id="6b558-126">次に、次のようなコマンドを実行します。指定されたユーザー (この例では kenmyer) は、Exchange での検出を実行する権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="6b558-126">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

<span data-ttu-id="6b558-127">Exchange と SharePoint の間でサーバー間の認証が確立されたら、次の手順では、SharePoint で電子情報開示サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b558-127">After server-to-server authentication has been established between Exchange and SharePoint your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="6b558-128">これを行うには、SharePoint 管理シェルから次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b558-128">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> <span data-ttu-id="6b558-129">"電子情報開示" とは、通常、訴訟において "証拠になり得ると合理的に判断できる" 項目の電子的アーカイブを参照するプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="6b558-129">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span>



</div>

<span data-ttu-id="6b558-130">新しいサイトの準備が整ったら、次の手順では、SharePoint の検索先として機能するように Exchange 2013 を構成します。</span><span class="sxs-lookup"><span data-stu-id="6b558-130">When the new site is ready, the next step is to configure Exchange 2013 to act as a result source for SharePoint.</span></span> <span data-ttu-id="6b558-131">これを行うには、SharePoint 2013 の [サーバーの全体管理] ページで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b558-131">You can do that by completing the following procedure from the SharePoint 2013 Central Administration page:</span></span>

1.  <span data-ttu-id="6b558-132">サーバーの全体管理ページで、[**サービス アプリケーションの管理**]、[**Search Service アプリケーション**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b558-132">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>

2.  <span data-ttu-id="6b558-133">[Search Service アプリケーション: 検索管理] ページで、[**検索先**]、[**新しい結果ソース**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b558-133">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>

3.  <span data-ttu-id="6b558-134">[**新しい結果ソース**] ウィンドウで、[**名前**] ボックスに新しい検索先の名前 (たとえば、**Microsoft Exchange**) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6b558-134">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="6b558-135">検索先**プロトコル**として [ **exchange** ] を選択し、exchange サーバーの WEB サービスのソース Url を [ **exchange ソース url** ] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="6b558-135">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="6b558-136">ソース URL は次のような形式です。</span><span class="sxs-lookup"><span data-stu-id="6b558-136">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  <span data-ttu-id="6b558-137">[**自動検出を使用する**] がオンでないことを確認して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b558-137">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>

<span data-ttu-id="6b558-138">最後に、SharePoint 探索サイトから以下の手順を実行して、新しい電子情報開示ケースと新しい電子情報開示セットを作成します (例: https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="6b558-138">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>

1.  <span data-ttu-id="6b558-139">[サイト コンテンツ] ページで、[**新しいケースを作成します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b558-139">On the Site Contents page click **Create a new case**.</span></span>

2.  <span data-ttu-id="6b558-p110">[サイト コンテンツ: 新しい SharePoint サイト] ページで、[**タイトル**] ボックスにユーザーの電子メール エイリアス (たとえば、**kenmyer**) を入力し、同じその URL を [**Web サイトのアドレス**] に追加します。次のような URL になります。</span><span class="sxs-lookup"><span data-stu-id="6b558-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  <span data-ttu-id="6b558-142">[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b558-142">Click **Create**.</span></span>

4.  <span data-ttu-id="6b558-143">[電子情報開示セット] ページが表示されたら、[**識別と保存: 情報開示セット**] の下の [**新しいアイテム**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b558-143">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>

5.  <span data-ttu-id="6b558-144">[新規: 情報開示セット] ページで、[**情報開示セット名**] ボックスにユーザーの電子メール エイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="6b558-144">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="6b558-145">[**フィルター** ] ボックスに「**電子情報開示 Lync \* \*\* 」と入力し、[追加] をクリックして [ソースの**管理 &\*\* します。</span><span class="sxs-lookup"><span data-stu-id="6b558-145">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add & Manage Sources**.</span></span>

6.  <span data-ttu-id="6b558-p112">[ソースの追加/管理] ページで、[**メールボックス**] の下の最初のテキスト ボックスにユーザーの電子メール エイリアスを入力します。テキスト ボックスの横にある [メールボックスの確認] アイコンをクリックして、SharePoint が指定のメールボックスに接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b558-p112">On the Add & Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**. Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>

7.  <span data-ttu-id="6b558-148">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b558-148">Click **OK**.</span></span>

8.  <span data-ttu-id="6b558-149">[電子情報開示セット] ページで、[**保存**] をクリックして新しい電子情報開示セットを保存します。</span><span class="sxs-lookup"><span data-stu-id="6b558-149">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>

<span data-ttu-id="6b558-150">この時点で、指定されたメールボックス (kenmyer) を検索したり、他の SharePoint コンテンツまたは検索先に対して行うのと同じ方法で In-Place 保持を有効にしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b558-150">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

