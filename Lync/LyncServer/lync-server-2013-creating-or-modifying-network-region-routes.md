---
title: 'Lync Server 2013: ネットワーク領域ルートの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d877de116cc2cf3e0c3354bb6e53d69c211cb482
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="6d4ab-102">Lync Server 2013 でのネットワーク領域ルートの作成または変更</span><span class="sxs-lookup"><span data-stu-id="6d4ab-102">Creating or modifying network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d4ab-103">_**最終更新日:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="6d4ab-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="6d4ab-104">通話受付制御 (CAC) 構成内のすべての領域は、他のすべての領域にアクセスするための何らかの手段を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="6d4ab-105">地域のリンクでは、地域間の接続について帯域幅の制限を設定していますが、物理的なリンクも示しています。ルートによって、ある領域から別の領域に接続するリンク先のパスが決定されます。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="6d4ab-106">Lync Server コントロールパネルを使用して、ネットワーク領域ルートを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="6d4ab-107">Lync Server コントロールパネルでは、ネットワーク領域ルートの作成、変更、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="6d4ab-108">ネットワーク領域ルートを作成または変更するには、このトピックを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-108">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="6d4ab-109">既存のネットワーク領域ルートの削除の詳細については、「 [Lync Server 2013 で既存のネットワーク領域ルートを削除](lync-server-2013-deleting-existing-network-region-routes.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-109">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="6d4ab-110">ネットワーク領域ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="6d4ab-110">To create a network region route</span></span>

1.  <span data-ttu-id="6d4ab-111">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d4ab-112">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6d4ab-113">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6d4ab-114">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="6d4ab-115">[**地域ルート**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-115">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="6d4ab-116">[**新しい地域ルート**] で、[**名前**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-116">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d4ab-117">この値は、Microsoft Lync Server 2013 の展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-117">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="6d4ab-118">[ **Network region \#1** ] ドロップダウンリストから、このルートによって接続される2つの領域のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-118">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="6d4ab-119">[ **Network region \#2** ] ドロップダウンリストから、このルートの他の地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-119">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="6d4ab-120">この領域は、ネットワーク領域\#1 で選択した地域とは異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-120">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="6d4ab-121">[**ネットワークの領域のリンク**] リストボックスを使って、そのルートに地域のリンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-121">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="6d4ab-122">[**追加**] ボタンをクリックして、[**地域] リンク**ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-122">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="6d4ab-123">このルートに追加する地域のリンクをクリックして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-123">Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d4ab-124">[<STRONG>追加</STRONG>] ボタンをクリックして、さらにリンクを追加するか、リンクを選択して [<STRONG>削除</STRONG>] をクリックし、リンクを削除します。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-124">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="6d4ab-125">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="6d4ab-126">ネットワークの領域ルートを変更するには</span><span class="sxs-lookup"><span data-stu-id="6d4ab-126">To modify a network region route</span></span>

1.  <span data-ttu-id="6d4ab-127">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d4ab-128">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6d4ab-129">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6d4ab-130">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-130">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="6d4ab-131">[**地域ルート**] ページで、変更する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-131">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="6d4ab-132">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="6d4ab-133">[**範囲ルートの編集**] で、このルートによって参加している地域と、ルートに関連付けられている地域リンクを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-133">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="6d4ab-134">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d4ab-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6d4ab-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d4ab-135">See Also</span></span>


[<span data-ttu-id="6d4ab-136">Lync Server 2013 での既存のネットワーク領域ルートの削除</span><span class="sxs-lookup"><span data-stu-id="6d4ab-136">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

