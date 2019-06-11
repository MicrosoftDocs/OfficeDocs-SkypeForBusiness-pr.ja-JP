---
title: 'Lync Server 2013: ネットワークサイト情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 788440d02a3f41198a870f8419cece4dc8e66900
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-site-information-in-lync-server-2013"></a><span data-ttu-id="50d02-102">Lync Server 2013 でのネットワークサイト情報の表示</span><span class="sxs-lookup"><span data-stu-id="50d02-102">Viewing network site information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50d02-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="50d02-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="50d02-104">[ネットワークサイト] は、通話受付制御 (CAC) または拡張9-1-1 展開の各領域内に構成されているオフィスまたは場所です。</span><span class="sxs-lookup"><span data-stu-id="50d02-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="50d02-105">ネットワークサイトの情報は、Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルで確認できます。</span><span class="sxs-lookup"><span data-stu-id="50d02-105">You can view network site information in either Lync Server 2013 Control Panel or Lync Server Management Shell .</span></span> <span data-ttu-id="50d02-106">ネットワークサイトの作成または変更の詳細については、「 [Lync Server 2013 でネットワークサイトを作成または変更する](lync-server-2013-creating-or-modifying-network-sites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50d02-106">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a><span data-ttu-id="50d02-107">Lync Server コントロールパネルでネットワークサイト情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="50d02-107">To view network site information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="50d02-108">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="50d02-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50d02-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="50d02-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="50d02-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="50d02-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="50d02-111">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50d02-111">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="50d02-112">[**サイト**] ページで、表示するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="50d02-112">On the **Site** page, click the site that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50d02-113">一度に1つのサイトの情報のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="50d02-113">You can only view information for one site at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="50d02-114">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50d02-114">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="50d02-115">Windows PowerShell コマンドレットを使用したネットワークサイト情報の表示</span><span class="sxs-lookup"><span data-stu-id="50d02-115">Viewing Network Site Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="50d02-116">ネットワークサイトの情報を表示するには、Windows PowerShell を使用するか、または CsNetworkSite コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="50d02-116">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="50d02-117">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="50d02-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="50d02-118">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50d02-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-site-information"></a><span data-ttu-id="50d02-119">ネットワークサイトの情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="50d02-119">To view network site information</span></span>

  - <span data-ttu-id="50d02-120">すべてのネットワークサイトに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="50d02-120">To view information about all your network sites, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="50d02-121">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="50d02-121">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

<span data-ttu-id="50d02-122">詳細については、「 [CsNetworkSite site](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) 」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="50d02-122">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50d02-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="50d02-123">See Also</span></span>


[<span data-ttu-id="50d02-124">Lync Server 2013 でのネットワークサイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="50d02-124">Creating or modifying network sites in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-sites.md)  
[<span data-ttu-id="50d02-125">Lync Server 2013 で既存のネットワークサイトを削除する</span><span class="sxs-lookup"><span data-stu-id="50d02-125">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

