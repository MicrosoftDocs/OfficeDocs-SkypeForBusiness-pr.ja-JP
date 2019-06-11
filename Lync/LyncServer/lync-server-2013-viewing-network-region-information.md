---
title: 'Lync Server 2013: ネットワークの地域情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52baf7c9dca4d663630bbf0cb17384916f5a953e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a><span data-ttu-id="28c0e-102">Lync Server 2013 でのネットワークの地域情報の表示</span><span class="sxs-lookup"><span data-stu-id="28c0e-102">Viewing network region information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28c0e-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="28c0e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="28c0e-104">ネットワーク領域は、ネットワークのさまざまな部分を複数の地域で相互接続します。</span><span class="sxs-lookup"><span data-stu-id="28c0e-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="28c0e-105">すべてのネットワーク領域はセントラルサイトと関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="28c0e-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="28c0e-106">セントラルサイトは、通話受付制御 (CAC) 帯域幅ポリシーサービスが実行されているデータセンターサイトです。</span><span class="sxs-lookup"><span data-stu-id="28c0e-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="28c0e-107">Lync Server コントロールパネルを使用して、ネットワークの領域を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="28c0e-107">You can use Lync Server Control Panel to view network regions.</span></span> <span data-ttu-id="28c0e-108">[ネットワーク] 領域には、インターネット経由の代替パスが音声とビデオに接続できるかどうかを決定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="28c0e-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="28c0e-109">既存のネットワーク領域を表示するには、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c0e-109">Use this topic to view existing network regions.</span></span> <span data-ttu-id="28c0e-110">既存のネットワーク領域の作成または変更の詳細については、「 [Lync Server 2013 でネットワーク領域を作成または変更](lync-server-2013-creating-or-modifying-network-regions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c0e-110">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a><span data-ttu-id="28c0e-111">Lync Server コントロールパネルを使用してネットワーク領域に関する情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="28c0e-111">To view information about a network region with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="28c0e-112">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="28c0e-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="28c0e-113">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="28c0e-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="28c0e-114">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="28c0e-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="28c0e-115">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28c0e-115">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="28c0e-116">[**領域**] ページで、表示する地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28c0e-116">On the **Region** page, click the region you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28c0e-117">表示できる領域は一度に1つだけです。</span><span class="sxs-lookup"><span data-stu-id="28c0e-117">You can only view one region at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="28c0e-118">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28c0e-118">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="28c0e-119">Windows PowerShell コマンドレットを使用したネットワーク領域情報の表示</span><span class="sxs-lookup"><span data-stu-id="28c0e-119">Viewing Network Region Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="28c0e-120">ネットワークの地域情報は、Windows PowerShell と、ユーザーの**入手用の Networkregion**コマンドレットを使って表示できます。</span><span class="sxs-lookup"><span data-stu-id="28c0e-120">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="28c0e-121">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="28c0e-121">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="28c0e-122">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c0e-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-information"></a><span data-ttu-id="28c0e-123">ネットワークの地域情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="28c0e-123">To view network region information</span></span>

  - <span data-ttu-id="28c0e-124">すべてのネットワーク領域に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="28c0e-124">To view information about all your network regions, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="28c0e-125">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="28c0e-125">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

<span data-ttu-id="28c0e-126">詳細については、「 [CsNetworkRegion の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c0e-126">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28c0e-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="28c0e-127">See Also</span></span>


[<span data-ttu-id="28c0e-128">Lync Server 2013 でのネットワーク領域の作成または変更</span><span class="sxs-lookup"><span data-stu-id="28c0e-128">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
[<span data-ttu-id="28c0e-129">Lync Server 2013 で既存のネットワーク領域を削除する</span><span class="sxs-lookup"><span data-stu-id="28c0e-129">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

