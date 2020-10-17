---
title: 'Lync Server 2013: ネットワーク地域ルート情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e671bb8f714e2444cc2f271f6ad7ecebc74f7ddb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535684"
---
# <a name="viewing-network-region-route-information-in-lync-server-2013"></a><span data-ttu-id="1b2be-102">Lync Server 2013 でのネットワーク地域ルート情報の表示</span><span class="sxs-lookup"><span data-stu-id="1b2be-102">Viewing network region route information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b2be-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1b2be-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1b2be-104">通話受付管理 (CAC) 構成内のすべての地域には、他のすべての地域へのアクセス方法がいくつかある必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b2be-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="1b2be-105">地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。</span><span class="sxs-lookup"><span data-stu-id="1b2be-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="1b2be-106">Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルで既存のネットワーク地域ルートを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b2be-106">Use the following procedures to view existing network region routes in Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="1b2be-107">ネットワーク地域ルートの作成または変更の詳細については、「 [Lync Server 2013 でのネットワーク地域ルートの作成または変更](lync-server-2013-creating-or-modifying-network-region-routes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b2be-107">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a><span data-ttu-id="1b2be-108">Lync Server コントロールパネルでネットワーク地域ルート情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="1b2be-108">To view network region route information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1b2be-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1b2be-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1b2be-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1b2be-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1b2be-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b2be-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1b2be-112">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b2be-112">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="1b2be-113">[**地域ルート**] ページで、変更する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b2be-113">On the **Region Route** page, click the region route that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1b2be-114">一度に表示できる地域ルートは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="1b2be-114">You can only view one region route at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="1b2be-115">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b2be-115">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1b2be-116">Windows PowerShell コマンドレットを使用してネットワーク地域ルート情報を表示する</span><span class="sxs-lookup"><span data-stu-id="1b2be-116">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1b2be-117">ネットワーク地域ルート情報は、Windows PowerShell と Get-CsNetworkInterRegionRoute コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="1b2be-117">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="1b2be-118">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="1b2be-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1b2be-119">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b2be-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-route-information"></a><span data-ttu-id="1b2be-120">ネットワーク地域ルート情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="1b2be-120">To view network region route information</span></span>

  - <span data-ttu-id="1b2be-121">すべてのネットワーク地域ルートに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1b2be-121">To view information about all your network region routes, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="1b2be-122">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b2be-122">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

<span data-ttu-id="1b2be-123">詳細については、[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b2be-123">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1b2be-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b2be-124">See Also</span></span>


[<span data-ttu-id="1b2be-125">Lync Server 2013 でのネットワーク地域ルートの作成または変更</span><span class="sxs-lookup"><span data-stu-id="1b2be-125">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[<span data-ttu-id="1b2be-126">Lync Server 2013 での既存のネットワーク地域ルートの削除</span><span class="sxs-lookup"><span data-stu-id="1b2be-126">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

