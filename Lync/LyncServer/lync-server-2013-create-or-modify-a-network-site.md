---
title: 'Lync Server 2013: ネットワークサイトを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60119e137851bbaa8dc7b6735202132085bb8d34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506124"
---
# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="a1bd4-102">Lync Server 2013 でのネットワークサイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="a1bd4-102">Create or modify a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1bd4-103">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="a1bd4-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="a1bd4-104">通話受付管理 (CAC)、E9-1-1、およびメディアバイパスの展開は、で定義され、常にネットワーク地域に関連付けられている *ネットワークサイト* の構成に依存します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-104">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="a1bd4-105">ネットワークサイトは、ブランチオフィスの場所、建物のセット、またはキャンパスを表します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-105">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="a1bd4-106">ネットワークサイトは、帯域幅が類似しているサブネットの集合を表します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-106">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="a1bd4-p102">ネットワーク サイトを作成または変更するには、以下の手順を使用します。 たとえば、1 つの音声機能について既にネットワーク サイトを作成している場合は、新しいネットワーク サイトを作成する必要はありません。他の音声機能も既存の同じサイトを使用します。 ただし、既存のネットワーク サイトの定義を変更して機能固有の設定を適用しなければならない場合があります。 たとえば、E9-1-1 用のネットワーク サイトを作成している場合、通話受付管理の展開時にネットワーク サイトを変更して、帯域幅ポリシー プロファイルを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-p102">Use the following procedures to create or modify network sites. For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites. You may, however, need to modify an existing network site definition to apply feature-specific settings. For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a1bd4-111">機能固有の設定が存在する場合、機能ごとに「展開」のドキュメントに記載されている高度な音声機能に関連するネットワーク サイトの具体的な例と要件については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-111">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="a1bd4-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Lync Server 2013 で CAC のネットワークサイトを構成する</A></span><span class="sxs-lookup"><span data-stu-id="a1bd4-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="a1bd4-113">ネットワークサイトの使用の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-113">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="a1bd4-114">新しい-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="a1bd4-114">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="a1bd4-115">-CsNetworkSite の取得</span><span class="sxs-lookup"><span data-stu-id="a1bd4-115">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="a1bd4-116">設定-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="a1bd4-116">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="a1bd4-117">-CsNetworkSite の削除</span><span class="sxs-lookup"><span data-stu-id="a1bd4-117">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="a1bd4-118">ネットワーク サイトの作成</span><span class="sxs-lookup"><span data-stu-id="a1bd4-118">Create a Network Site</span></span>

<span data-ttu-id="a1bd4-119">通話受付管理、E9-1-1、またはメディア バイパスで使用できるネットワーク地域を作成します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-119">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="a1bd4-120">管理シェルを使用して、ネットワーク サイトを作成するには</span><span class="sxs-lookup"><span data-stu-id="a1bd4-120">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="a1bd4-121">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a1bd4-122">New-CsNetworkSite コマンドレットを実行して、ネットワーク サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-122">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="a1bd4-123">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-123">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="a1bd4-124">この例では、"NorthAmerica" ネットワーク地域に "Chicago" という名前のネットワーク サイトが作成されました。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-124">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1bd4-125">このコマンドを正常に実行するには、NorthAmerica ネットワーク地域があらかじめ存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-125">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="a1bd4-126">トポロジのネットワーク サイトを作成するには、他のサイトの設定に関してステップ 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-126">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="a1bd4-127">Lync Server コントロール パネルを使用して、ネットワーク サイトを作成するには</span><span class="sxs-lookup"><span data-stu-id="a1bd4-127">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a1bd4-128">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a1bd4-129">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a1bd4-130">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-130">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="a1bd4-131">[**サイト**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-131">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="a1bd4-132">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-132">Click **New**.</span></span>

5.  <span data-ttu-id="a1bd4-133">[**新しいサイト**] ページで、[**名前**] をクリックしてネットワーク サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-133">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="a1bd4-134">[**地域**] をクリックして、リストで地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-134">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="a1bd4-135">オプションで、[**帯域幅ポリシー**] をクリックして、リストで帯域幅ポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-135">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1bd4-136">帯域幅ポリシーが必要なのは、サイトで通話受付管理を展開する場合だけです。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-136">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="a1bd4-137">オプションで、[**場所のポリシー**] をクリックして、リストで場所のポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-137">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1bd4-138">場所のポリシーが必要なのは、サイトで E9-1-1 を展開する場合だけです。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-138">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="a1bd4-139">オプションで、[**説明**] をクリックして、このネットワーク サイトを説明する追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-139">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="a1bd4-140">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-140">Click **Commit**.</span></span>

11. <span data-ttu-id="a1bd4-141">他のサイトについての設定に関してステップ 4 ～ 10 を繰り返し、ご使用のトポロジのネットワーク サイトの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-141">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="a1bd4-142">ネットワーク サイトの変更</span><span class="sxs-lookup"><span data-stu-id="a1bd4-142">Modify a Network Site</span></span>

<span data-ttu-id="a1bd4-143">通話受付管理、E9-1-1、またはメディア バイパスで使用できるネットワーク地域を変更します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-143">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="a1bd4-144">ネットワーク サイトを変更するには</span><span class="sxs-lookup"><span data-stu-id="a1bd4-144">To modify a network site</span></span>

1.  <span data-ttu-id="a1bd4-145">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a1bd4-146">Set-CsNetworkSite コマンドレットを実行して、ネットワーク サイトを変更します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-146">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="a1bd4-147">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-147">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="a1bd4-p104">この例では、"Albuquerque" という名前のサイトが "NorthAmerica" ネットワーク地域に移動されます。 ネットワーク サイトの構成を変更して、通話受付管理、E9-1-1、またはメディア バイパスを展開するには、Set-CsNetworkSite コマンドレットをそれぞれ BWPolicyProfileID または LocationPolicy パラメーターと組み合わせて実行し、ネットワーク サイトの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-p104">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region. To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1bd4-p105">メディア バイパス用に BypassID パラメーターが用意されていますが、自動生成されるバイパス ID を無効にしないことを強くお勧めします。 メディア バイパス用にネットワーク サイトを構成するために、追加パラメーターを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-p105">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="a1bd4-152">他のサイトについての設定に関してステップ 2 を繰り返し、ご使用のトポロジのネットワーク サイトの変更を完了します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-152">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="a1bd4-153">Lync Server コントロール パネルを使用して、ネットワーク サイトを変更するには</span><span class="sxs-lookup"><span data-stu-id="a1bd4-153">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a1bd4-154">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-154">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a1bd4-155">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-155">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a1bd4-156">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-156">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="a1bd4-157">[**サイト**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-157">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="a1bd4-158">表内で、変更するネットワーク サイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-158">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="a1bd4-159">[**編集**] をクリックして、[**詳細の表示...**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-159">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="a1bd4-160">[**サイトの編集**] ページで、このネットワーク サイトの設定値を必要に応じて変更します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-160">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="a1bd4-161">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-161">Click **Commit**.</span></span>

8.  <span data-ttu-id="a1bd4-162">他のサイトについての設定に関してステップ 4 ～ 7 を繰り返し、ネットワーク サイトの変更を完了します。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-162">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

