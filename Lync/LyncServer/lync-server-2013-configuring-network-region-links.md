---
title: 'Lync Server 2013: ネットワーク地域リンクの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13204945482c130c65aea7725db5e06a1eb5a3da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="53d68-102">Lync Server 2013 でのネットワーク地域リンクの構成</span><span class="sxs-lookup"><span data-stu-id="53d68-102">Configuring network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53d68-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="53d68-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="53d68-104">通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを公正できます。</span><span class="sxs-lookup"><span data-stu-id="53d68-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="53d68-105">ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。</span><span class="sxs-lookup"><span data-stu-id="53d68-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="53d68-106">Lync Server コントロールパネルを使用して、2つのネットワーク地域間のリンクを定義し、これらの地域間の音声およびビデオ接続に対する帯域幅制限を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="53d68-106">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="53d68-107">既存のネットワーク地域リンクの削除の詳細については、「 [Lync Server 2013 でのネットワーク地域リンクの削除](lync-server-2013-deleting-network-region-links.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53d68-107">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="53d68-108">ネットワーク地域リンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="53d68-108">To create a network region link</span></span>

1.  <span data-ttu-id="53d68-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="53d68-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="53d68-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="53d68-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="53d68-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53d68-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="53d68-112">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域リンク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53d68-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="53d68-113">[**地域リンク**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53d68-113">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="53d68-114">[**新しい地域] リンク**で、[**名前**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="53d68-114">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53d68-115">この値は、Lync Server 2013 展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="53d68-115">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="53d68-116">[**ネットワーク地域\#1** ] ドロップダウンリストから、リンクする2つの地域のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="53d68-116">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="53d68-117">[**ネットワーク地域\#2** ] ドロップダウンリストから、リンクする他の地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="53d68-117">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="53d68-118">この地域は、[ネットワーク地域\#1 に選択した地域とは別のものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="53d68-118">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="53d68-119">オプションこれらの地域間の音声またはビデオ通話に帯域幅制限を設定する場合は、[**帯域幅ポリシー** ] ドロップダウンリストから帯域幅ポリシーのプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="53d68-119">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="53d68-120">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53d68-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="53d68-121">ネットワーク地域リンクを変更するには</span><span class="sxs-lookup"><span data-stu-id="53d68-121">To modify a network region link</span></span>

1.  <span data-ttu-id="53d68-122">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="53d68-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="53d68-123">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="53d68-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="53d68-124">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53d68-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="53d68-125">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域リンク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53d68-125">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="53d68-126">[**地域リンク**] ページで、変更する地域リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="53d68-126">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="53d68-127">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53d68-127">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="53d68-128">[**地域の編集] リンク**では、リンクされている地域またはこのリンクの帯域幅ポリシープロファイルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="53d68-128">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="53d68-129">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53d68-129">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="53d68-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="53d68-130">See Also</span></span>


[<span data-ttu-id="53d68-131">Lync Server 2013 でのネットワーク地域リンクの削除</span><span class="sxs-lookup"><span data-stu-id="53d68-131">Deleting network region links in Lync Server 2013</span></span>](lync-server-2013-deleting-network-region-links.md)  


[<span data-ttu-id="53d68-132">新しい-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="53d68-132">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="53d68-133">設定-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="53d68-133">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="53d68-134">-CsNetworkRegionLink の削除</span><span class="sxs-lookup"><span data-stu-id="53d68-134">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="53d68-135">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="53d68-135">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
