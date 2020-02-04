---
title: 'Lync Server 2013: ネットワーク領域のリンク情報の表示'
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
ms.openlocfilehash: 935d1a98bd4f446ec8861ae8382eb724611a945f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="89395-102">Lync Server 2013 でのネットワーク領域のリンク情報の表示</span><span class="sxs-lookup"><span data-stu-id="89395-102">Viewing network region link information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89395-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="89395-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="89395-104">通話受付制御 (CAC) の一部として、2つのネットワーク領域間のリンクを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="89395-104">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="89395-105">ネットワーク内の領域は、物理ワイドエリアネットワーク (WAN) 接続によってリンクされています。</span><span class="sxs-lookup"><span data-stu-id="89395-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="89395-106">Lync Server コントロールパネルを使用して、2つのネットワーク領域間の既存のリンクを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="89395-106">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="89395-107">ネットワーク領域へのリンクの作成または変更の詳細については、「 [Lync Server 2013 でのネットワーク領域のリンクの構成](lync-server-2013-configuring-network-region-links.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89395-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="89395-108">Lync Server コントロールパネルでネットワーク領域のリンクを表示するには</span><span class="sxs-lookup"><span data-stu-id="89395-108">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="89395-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="89395-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="89395-110">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="89395-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="89395-111">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="89395-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="89395-112">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域] リンク**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89395-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="89395-113">[**地域] リンク**ページで、表示する地域のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="89395-113">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="89395-114">一度に表示できるのは、1つの地域のリンクに関する情報だけです。</span><span class="sxs-lookup"><span data-stu-id="89395-114">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="89395-115">[**編集**] メニューの [**詳細の表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="89395-115">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="89395-116">Windows PowerShell コマンドレットを使用したネットワーク領域のリンク情報の表示</span><span class="sxs-lookup"><span data-stu-id="89395-116">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="89395-117">ネットワークの領域のリンクを表示するには、Windows PowerShell を使用するか、または**CsNetworkRegionLink**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="89395-117">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="89395-118">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="89395-118">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="89395-119">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="89395-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="89395-120">ネットワーク領域のリンク情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="89395-120">To view network region link information</span></span>

  - <span data-ttu-id="89395-121">すべてのネットワーク領域のリンクに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="89395-121">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="89395-122">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="89395-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="89395-123">詳細については、「 [CsNetworkRegionLink の入手](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89395-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="89395-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="89395-124">See Also</span></span>


[<span data-ttu-id="89395-125">Lync Server 2013 でネットワークサイトリンクを構成する</span><span class="sxs-lookup"><span data-stu-id="89395-125">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

