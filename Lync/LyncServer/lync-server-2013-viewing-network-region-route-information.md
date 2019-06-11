---
title: 'Lync Server 2013: ネットワーク領域ルート情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4438a3af4a9bfbdaf88d4412b769cdaaba9d3d43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a><span data-ttu-id="1715b-102">Lync Server 2013 でのネットワーク領域ルート情報の表示</span><span class="sxs-lookup"><span data-stu-id="1715b-102">Viewing network region route information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1715b-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1715b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1715b-104">通話受付制御 (CAC) 構成内のすべての領域は、他のすべての領域にアクセスするための何らかの手段を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1715b-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="1715b-105">地域のリンクでは、地域間の接続について帯域幅の制限を設定していますが、物理的なリンクも示しています。ルートによって、ある領域から別の領域に接続するリンク先のパスが決定されます。</span><span class="sxs-lookup"><span data-stu-id="1715b-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="1715b-106">次の手順を使用して、Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルで既存のネットワーク領域ルートを表示します。</span><span class="sxs-lookup"><span data-stu-id="1715b-106">Use the following procedures to view existing network region routes in Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="1715b-107">ネットワーク領域ルートの作成または変更の詳細については、「 [Lync Server 2013 でネットワーク領域ルートを作成または変更する](lync-server-2013-creating-or-modifying-network-region-routes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1715b-107">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a><span data-ttu-id="1715b-108">Lync Server コントロールパネルのネットワーク領域ルート情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="1715b-108">To view network region route information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1715b-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1715b-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1715b-110">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1715b-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1715b-111">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1715b-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1715b-112">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1715b-112">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="1715b-113">[**地域ルート**] ページで、表示する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1715b-113">On the **Region Route** page, click the region route that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1715b-114">表示できる地域ルートは一度に1つだけです。</span><span class="sxs-lookup"><span data-stu-id="1715b-114">You can only view one region route at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="1715b-115">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1715b-115">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1715b-116">Windows PowerShell コマンドレットを使用したネットワーク領域ルート情報の表示</span><span class="sxs-lookup"><span data-stu-id="1715b-116">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1715b-117">ネットワーク領域のルート情報を表示するには、Windows PowerShell を使用するか、または CsNetworkInterRegionRoute コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1715b-117">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="1715b-118">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="1715b-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1715b-119">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1715b-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-route-information"></a><span data-ttu-id="1715b-120">ネットワーク領域ルート情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="1715b-120">To view network region route information</span></span>

  - <span data-ttu-id="1715b-121">すべてのネットワーク領域のルートに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1715b-121">To view information about all your network region routes, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="1715b-122">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1715b-122">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

<span data-ttu-id="1715b-123">詳細については、「 [CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1715b-123">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1715b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="1715b-124">See Also</span></span>


[<span data-ttu-id="1715b-125">Lync Server 2013 でのネットワーク領域ルートの作成または変更</span><span class="sxs-lookup"><span data-stu-id="1715b-125">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[<span data-ttu-id="1715b-126">Lync Server 2013 での既存のネットワーク領域ルートの削除</span><span class="sxs-lookup"><span data-stu-id="1715b-126">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

