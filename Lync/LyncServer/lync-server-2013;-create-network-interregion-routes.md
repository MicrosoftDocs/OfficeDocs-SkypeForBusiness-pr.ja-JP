---
title: Lync Server 2013;ネットワーク間の領域ルートを作成する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 9d234d959f434e9e2b96850add488ecd4eac952c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="94c5c-102">Lync Server 2013 でのネットワーク間通信領域ルートの作成</span><span class="sxs-lookup"><span data-stu-id="94c5c-102">Create network interregion routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94c5c-103">_**最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="94c5c-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="94c5c-104">*ネットワークインター領域ルート*は、ネットワーク領域のペア間のルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="94c5c-104">A *network interregion route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="94c5c-105">通話受付制御の展開におけるネットワーク領域の各ペアには、ネットワークインター領域ルートが必要です。</span><span class="sxs-lookup"><span data-stu-id="94c5c-105">Each pair of network regions in your call admission control deployment requires a network interregion route.</span></span> <span data-ttu-id="94c5c-106">これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="94c5c-106">This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="94c5c-107">地域のリンクでは、領域間の接続に帯域幅の制限を設定していますが、相互領域ルートによって、接続が1つの領域から別の領域に移動するリンク先のパスが決定されます。</span><span class="sxs-lookup"><span data-stu-id="94c5c-107">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="94c5c-108">ネットワークインターセクションルートの操作の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94c5c-108">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="94c5c-109">新しい (CsNetworkInterRegionRoute)</span><span class="sxs-lookup"><span data-stu-id="94c5c-109">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="94c5c-110">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="94c5c-110">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="94c5c-111">設定-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="94c5c-111">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="94c5c-112">CsNetworkInterRegionRoute の削除</span><span class="sxs-lookup"><span data-stu-id="94c5c-112">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="94c5c-113">このトポロジの例では、北米、EMEA、EMEA、APAC、北米/APAC という3つの地域のペアのそれぞれに対して、ネットワークの interregion ルートを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94c5c-113">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="94c5c-114">Lync Server 管理シェルを使用してネットワーク間の領域ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="94c5c-114">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="94c5c-115">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="94c5c-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="94c5c-116">**New-CsNetworkInterRegionRoute** コマンドレットを実行して、必要なルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="94c5c-116">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="94c5c-117">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="94c5c-117">For example, run:</span></span>
    
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
    > <span data-ttu-id="94c5c-118">北米/APAC ネットワーク interregion ルートには、ネットワーク領域間の直接リンクがないため、2つのネットワークリージョンリンクが必要です。</span><span class="sxs-lookup"><span data-stu-id="94c5c-118">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="94c5c-119">Lync Server コントロールパネルを使用してネットワーク間の領域ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="94c5c-119">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="94c5c-120">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="94c5c-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="94c5c-121">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="94c5c-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="94c5c-122">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94c5c-122">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="94c5c-123">[**地域ルート**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="94c5c-123">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="94c5c-124">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94c5c-124">Click **New**.</span></span>

5.  <span data-ttu-id="94c5c-125">[**新しい地域ルート**] ページで、[**名前**] をクリックし、ネットワークインターセクションルートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="94c5c-125">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="94c5c-126">[**ネットワーク領域\#1**] をクリックし、ネットワーク領域\#2 にルーティングするリスト内のネットワーク領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94c5c-126">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="94c5c-127">[**ネットワーク領域\#2**] をクリックし、ネットワーク領域\#1 にルーティングするリスト内のネットワーク領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94c5c-127">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="94c5c-128">[**ネットワークの領域リンク**] フィールドの横にある [**追加**] をクリックし、ネットワークのインターセクションルートで使用されるネットワーク領域のリンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="94c5c-128">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="94c5c-129">2 つのネットワーク地域のルートを作成する場合、その間に直接のネットワーク地域リンクがなければ、必要なすべてのリンクを追加してルートを完成させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="94c5c-129">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="94c5c-130">たとえば、北米/APAC ネットワーク interregion ルートには、2つのネットワーク領域リンクが必要です。これには、その間にネットワークの直接リンクがありません。</span><span class="sxs-lookup"><span data-stu-id="94c5c-130">For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="94c5c-131">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94c5c-131">Click **Commit**.</span></span>

10. <span data-ttu-id="94c5c-132">トポロジのネットワークでのネットワーク間ルートの作成を完了するには、他のネットワークインターセクションルートの設定を使用して、手順4から9を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="94c5c-132">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

