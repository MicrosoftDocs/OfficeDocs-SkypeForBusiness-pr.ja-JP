---
title: 'Lync Server 2013: ネットワーク地域ルートの作成または変更'
description: 'Lync Server 2013: ネットワーク地域ルートを作成または変更しています。'
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
ms.openlocfilehash: 89106c905419778776ea16341f247027d49f1195
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544093"
---
# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="ce4be-103">Lync Server 2013 でのネットワーク地域ルートの作成または変更</span><span class="sxs-lookup"><span data-stu-id="ce4be-103">Creating or modifying network region routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce4be-104">_**トピックの最終更新日:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="ce4be-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="ce4be-105">通話受付管理 (CAC) 構成内のすべての地域には、他のすべての地域へのアクセス方法がいくつかある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce4be-105">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="ce4be-106">地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。</span><span class="sxs-lookup"><span data-stu-id="ce4be-106">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="ce4be-107">Lync Server コントロールパネルを使用して、ネットワーク地域ルートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ce4be-107">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="ce4be-108">Lync Server コントロールパネルから、ネットワーク地域ルートを作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ce4be-108">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="ce4be-109">このトピックでは、ネットワーク地域ルートの作成または変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce4be-109">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="ce4be-110">既存のネットワーク地域ルートの削除の詳細については、「 [Lync Server 2013 で既存のネットワーク地域ルートを削除](lync-server-2013-deleting-existing-network-region-routes.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce4be-110">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="ce4be-111">ネットワーク地域ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="ce4be-111">To create a network region route</span></span>

1.  <span data-ttu-id="ce4be-112">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ce4be-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ce4be-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ce4be-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ce4be-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce4be-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ce4be-115">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce4be-115">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="ce4be-116">[**地域ルート**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce4be-116">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="ce4be-117">[**新しい地域ルート**] で、[**名前**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ce4be-117">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ce4be-118">この値は、Microsoft Lync Server 2013 展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce4be-118">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="ce4be-119">[ **ネットワーク地域 \# 1** ] ドロップダウンリストから、このルートによって接続する2つの地域のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ce4be-119">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="ce4be-120">[ **ネットワーク地域 \# 2** ] ドロップダウンリストから、このルートの他の地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce4be-120">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="ce4be-121">この地域は、[ネットワーク地域1に選択した地域とは別のものにする必要があり \# ます。</span><span class="sxs-lookup"><span data-stu-id="ce4be-121">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="ce4be-p104">[**ネットワーク地域リンク**] リスト ボックスを使用して、地域リンクをルートに追加します。 [**追加**] ボタンをクリックし、[**地域リンク**] ページを表示します。 このルートに追加する地域リンクをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce4be-p104">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ce4be-125">[<STRONG>追加</STRONG>] ボタンのクリックを続けて、さらにリンクを追加できます。また、リンクを選択して [<STRONG>削除</STRONG>] をクリックすると、リンクを削除できます。</span><span class="sxs-lookup"><span data-stu-id="ce4be-125">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="ce4be-126">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce4be-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="ce4be-127">ネットワーク地域ルートを変更するには</span><span class="sxs-lookup"><span data-stu-id="ce4be-127">To modify a network region route</span></span>

1.  <span data-ttu-id="ce4be-128">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ce4be-128">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ce4be-129">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ce4be-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ce4be-130">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce4be-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ce4be-131">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce4be-131">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="ce4be-132">[**地域ルート**] ページで、変更する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce4be-132">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="ce4be-133">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce4be-133">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="ce4be-134">[**地域ルートの編集**] で、このルートが接続する地域やこのルートに関連付ける地域リンクを変更できます。</span><span class="sxs-lookup"><span data-stu-id="ce4be-134">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="ce4be-135">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce4be-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce4be-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce4be-136">See Also</span></span>


[<span data-ttu-id="ce4be-137">Lync Server 2013 での既存のネットワーク地域ルートの削除</span><span class="sxs-lookup"><span data-stu-id="ce4be-137">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

