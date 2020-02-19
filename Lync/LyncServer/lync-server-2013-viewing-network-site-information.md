---
title: 'Lync Server 2013: ネットワークサイト情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0908520a0eeb6d34c49a0b7f0caaf5583b33a6b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-site-information-in-lync-server-2013"></a><span data-ttu-id="a5010-102">Lync Server 2013 でのネットワークサイト情報の表示</span><span class="sxs-lookup"><span data-stu-id="a5010-102">Viewing network site information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5010-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a5010-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a5010-104">ネットワーク サイトは、通話受付管理 (CAC) または Enhanced 9-1-1 展開の各地域内で構成されるオフィスまたは拠点です。</span><span class="sxs-lookup"><span data-stu-id="a5010-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="a5010-105">ネットワークサイトの情報は、Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルで確認できます。</span><span class="sxs-lookup"><span data-stu-id="a5010-105">You can view network site information in either Lync Server 2013 Control Panel or Lync Server Management Shell .</span></span> <span data-ttu-id="a5010-106">ネットワークサイトの作成または変更の詳細については、「 [Lync Server 2013 でのネットワークサイトの作成または変更](lync-server-2013-creating-or-modifying-network-sites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5010-106">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a><span data-ttu-id="a5010-107">Lync Server コントロールパネルでネットワークサイト情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="a5010-107">To view network site information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a5010-108">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a5010-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a5010-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a5010-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a5010-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5010-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a5010-111">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5010-111">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="a5010-112">[**サイト**] ページで、表示するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5010-112">On the **Site** page, click the site that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a5010-113">一度に表示できるのは 1 つのサイトの情報だけです。</span><span class="sxs-lookup"><span data-stu-id="a5010-113">You can only view information for one site at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="a5010-114">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5010-114">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a5010-115">Windows PowerShell コマンドレットを使用したネットワークサイト情報の表示</span><span class="sxs-lookup"><span data-stu-id="a5010-115">Viewing Network Site Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a5010-116">Windows PowerShell と Get-help Networksite コマンドレットを使用して、ネットワークサイトの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a5010-116">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="a5010-117">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5010-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a5010-118">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5010-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-site-information"></a><span data-ttu-id="a5010-119">ネットワーク サイトの情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="a5010-119">To view network site information</span></span>

  - <span data-ttu-id="a5010-120">すべてのネットワークサイトに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a5010-120">To view information about all your network sites, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="a5010-121">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5010-121">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

<span data-ttu-id="a5010-122">詳細については、[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5010-122">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a5010-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5010-123">See Also</span></span>


[<span data-ttu-id="a5010-124">Lync Server 2013 でのネットワークサイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="a5010-124">Creating or modifying network sites in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-sites.md)  
[<span data-ttu-id="a5010-125">Lync Server 2013 での既存のネットワークサイトの削除</span><span class="sxs-lookup"><span data-stu-id="a5010-125">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

