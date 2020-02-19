---
title: 'Lync Server 2013: 既存のネットワーク地域ルートの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b58d8899b0b794dc378e30c0c35fb37af397e16
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="a766a-102">Lync Server 2013 での既存のネットワーク地域ルートの削除</span><span class="sxs-lookup"><span data-stu-id="a766a-102">Deleting existing network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a766a-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a766a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a766a-104">通話受付管理 (CAC) 構成内のすべての地域には、他のすべての地域へのアクセス方法がいくつかある必要があります。</span><span class="sxs-lookup"><span data-stu-id="a766a-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="a766a-105">地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。</span><span class="sxs-lookup"><span data-stu-id="a766a-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="a766a-106">Lync Server コントロールパネルを使用して、ネットワーク地域ルートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a766a-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="a766a-107">Lync Server コントロールパネルから、ネットワーク地域ルートを作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a766a-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="a766a-108">このトピックを使用して、既存のネットワーク地域ルートを削除できます。</span><span class="sxs-lookup"><span data-stu-id="a766a-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="a766a-109">ネットワーク地域ルートの作成または変更の詳細については、「 [Lync Server 2013 でのネットワーク地域ルートの作成または変更](lync-server-2013-creating-or-modifying-network-region-routes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a766a-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="a766a-110">ネットワーク地域ルートを削除するには</span><span class="sxs-lookup"><span data-stu-id="a766a-110">To delete a network region route</span></span>

1.  <span data-ttu-id="a766a-111">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a766a-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a766a-112">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a766a-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a766a-113">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a766a-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a766a-114">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a766a-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="a766a-115">[**地域ルート**] ページで、削除する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a766a-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a766a-p103">1 つ以上の地域ルートを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数のルートを選択します。また、すべての地域ルートを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a766a-p103">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="a766a-119">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a766a-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="a766a-120">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a766a-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a766a-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a766a-121">See Also</span></span>


[<span data-ttu-id="a766a-122">Lync Server 2013 でのネットワーク地域ルートの作成または変更</span><span class="sxs-lookup"><span data-stu-id="a766a-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="a766a-123">[ネットワーク地域ルートの構成](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a766a-123">[Configure a Network Region Route](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="a766a-124">新しい-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a766a-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="a766a-125">設定-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a766a-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="a766a-126">-CsNetworkInterRegionRoute の削除</span><span class="sxs-lookup"><span data-stu-id="a766a-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="a766a-127">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a766a-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

