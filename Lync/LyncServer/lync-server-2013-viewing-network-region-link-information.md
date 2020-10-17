---
title: 'Lync Server 2013: ネットワーク地域リンク情報の表示'
description: 'Lync Server 2013: ネットワーク地域リンク情報の表示。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0134ded9942ebda91050c1f7b0bbcfef018451a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565363"
---
# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="4cbc5-103">Lync Server 2013 でのネットワーク地域リンク情報の表示</span><span class="sxs-lookup"><span data-stu-id="4cbc5-103">Viewing network region link information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cbc5-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4cbc5-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4cbc5-105">通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-105">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4cbc5-106">ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="4cbc5-107">Lync Server コントロールパネルを使用して、2つのネットワーク地域間の既存のリンクを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-107">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="4cbc5-108">ネットワーク地域リンクの作成または変更の詳細については、「 [Lync Server 2013 でのネットワーク地域リンクの構成](lync-server-2013-configuring-network-region-links.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-108">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="4cbc5-109">Lync Server コントロールパネルでネットワーク地域リンクを表示するには</span><span class="sxs-lookup"><span data-stu-id="4cbc5-109">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4cbc5-110">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4cbc5-111">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4cbc5-112">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4cbc5-113">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域リンク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4cbc5-114">[**地域リンク**] ページで、表示する地域リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4cbc5-115">一度に情報を表示できる地域リンクは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-115">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="4cbc5-116">[**編集**] メニューの [**詳細の表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-116">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4cbc5-117">Windows PowerShell コマンドレットを使用してネットワーク地域リンク情報を表示する</span><span class="sxs-lookup"><span data-stu-id="4cbc5-117">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4cbc5-118">Windows PowerShell と **Get-CsNetworkRegionLink** コマンドレットを使用して、ネットワーク地域リンクを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="4cbc5-119">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-119">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4cbc5-120">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="4cbc5-121">ネットワーク地域リンク情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="4cbc5-121">To view network region link information</span></span>

  - <span data-ttu-id="4cbc5-122">すべてのネットワーク地域リンクに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-122">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="4cbc5-123">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-123">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="4cbc5-124">詳細については、「[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cbc5-124">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4cbc5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cbc5-125">See Also</span></span>


[<span data-ttu-id="4cbc5-126">Lync Server 2013 でのネットワークサイトリンクの構成</span><span class="sxs-lookup"><span data-stu-id="4cbc5-126">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

