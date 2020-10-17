---
title: Lync Server 2013;ネットワーク地域間ルートを作成する
description: Lync Server 2013;ネットワーク地域間ルートを作成します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 44c8c62a86f7cfb6ca5b1148dc097c1d7786ad29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546053"
---
# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="bfecb-103">Lync Server 2013 でのネットワーク地域間ルートの作成</span><span class="sxs-lookup"><span data-stu-id="bfecb-103">Create network interregion routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfecb-104">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="bfecb-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="bfecb-p101">*ネットワーク地域間ルート*では、ネットワーク地域のペア間のルートを定義します。 通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域間ルートが必要です。 これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="bfecb-p101">A *network interregion route* defines the route between a pair of network regions. Each pair of network regions in your call admission control deployment requires a network interregion route. This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="bfecb-108">地域のリンクが地域間の接続に対する帯域幅制限を設定し、地域間ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。</span><span class="sxs-lookup"><span data-stu-id="bfecb-108">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="bfecb-109">ネットワーク地域間ルートの使用の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfecb-109">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="bfecb-110">新しい-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="bfecb-110">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="bfecb-111">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="bfecb-111">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="bfecb-112">設定-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="bfecb-112">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="bfecb-113">-CsNetworkInterRegionRoute の削除</span><span class="sxs-lookup"><span data-stu-id="bfecb-113">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="bfecb-114">トポロジの例では、北アメリカ/EMEA、EMEA/APAC、および北アメリカ/APAC の 3 つの各地域ペアにネットワーク地域間ルートを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfecb-114">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="bfecb-115">Lync Server 管理シェルを使用してネットワーク地域間ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="bfecb-115">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="bfecb-116">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfecb-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bfecb-117">**New-CsNetworkInterRegionRoute** コマンドレットを実行して、必要なルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="bfecb-117">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="bfecb-118">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfecb-118">For example, run:</span></span>
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="bfecb-119">北アメリカ/APAC 間には直接のネットワーク地域リンクがないため、このネットワーク地域間ルートには 2 つのネットワーク地域リンクが必要です。</span><span class="sxs-lookup"><span data-stu-id="bfecb-119">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="bfecb-120">Lync Server コントロールパネルを使用してネットワーク地域間ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="bfecb-120">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="bfecb-121">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bfecb-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bfecb-122">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfecb-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="bfecb-123">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfecb-123">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="bfecb-124">[**地域ルート**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfecb-124">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="bfecb-125">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfecb-125">Click **New**.</span></span>

5.  <span data-ttu-id="bfecb-126">[**新しい地域ルート**] ページで、[**名前**] をクリックし、ネットワーク地域間ルートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="bfecb-126">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="bfecb-127">[ **ネットワーク地域 \# 1**] をクリックし、一覧でネットワーク地域2にルーティングするネットワーク地域をクリックし \# ます。</span><span class="sxs-lookup"><span data-stu-id="bfecb-127">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="bfecb-128">[ **ネットワーク地域 \# 2**] をクリックし、一覧でネットワーク地域1にルーティングするネットワーク地域をクリックし \# ます。</span><span class="sxs-lookup"><span data-stu-id="bfecb-128">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="bfecb-129">[**ネットワーク地域リンク**] フィールドの横の [**追加**] をクリックし、ネットワーク地域間ルートで使用するネットワーク地域リンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="bfecb-129">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="bfecb-p104">2 つのネットワーク地域のルートを作成する場合、その間に直接のネットワーク地域リンクがなければ、必要なすべてのリンクを追加してルートを完成させる必要があります。 たとえば、北アメリカ/APAC 間には直接のネットワーク地域リンクがないため、このネットワーク地域間ルートには 2 つのネットワーク地域リンクが必要です。</span><span class="sxs-lookup"><span data-stu-id="bfecb-p104">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="bfecb-132">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfecb-132">Click **Commit**.</span></span>

10. <span data-ttu-id="bfecb-133">トポロジのネットワーク地域間ルートを作成するには、他のネットワーク地域間ルートに関してステップ 4 ～ 9 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="bfecb-133">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

