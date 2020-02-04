---
title: 'Lync Server 2013: 既存のネットワーク領域を削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57af552f82dfb3ca30943fd68c348cd5315b969b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a><span data-ttu-id="bd74c-102">Lync Server 2013 で既存のネットワーク領域を削除する</span><span class="sxs-lookup"><span data-stu-id="bd74c-102">Deleting existing network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd74c-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="bd74c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="bd74c-104">ネットワーク領域は、ネットワークのさまざまな部分を複数の地域で相互接続します。</span><span class="sxs-lookup"><span data-stu-id="bd74c-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="bd74c-105">すべてのネットワーク領域はセントラルサイトと関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd74c-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="bd74c-106">セントラルサイトは、通話受付制御 (CAC) 帯域幅ポリシーサービスが実行されているデータセンターサイトです。</span><span class="sxs-lookup"><span data-stu-id="bd74c-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="bd74c-107">Lync Server コントロールパネルを使用して、ネットワークの領域を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="bd74c-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="bd74c-108">[ネットワーク] 領域には、インターネット経由の代替パスが音声とビデオに接続できるかどうかを決定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd74c-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="bd74c-109">Lync Server コントロールパネルから、ネットワークの領域を作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bd74c-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="bd74c-110">既存のネットワーク領域を削除するには、このトピックを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd74c-110">Use this topic to delete existing network regions.</span></span> <span data-ttu-id="bd74c-111">既存のネットワーク領域の作成または変更の詳細については、「 [Lync Server 2013 でネットワーク領域を作成または変更](lync-server-2013-creating-or-modifying-network-regions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd74c-111">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-delete-a-network-region"></a><span data-ttu-id="bd74c-112">ネットワークの領域を削除するには</span><span class="sxs-lookup"><span data-stu-id="bd74c-112">To delete a network region</span></span>

1.  <span data-ttu-id="bd74c-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bd74c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bd74c-114">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bd74c-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bd74c-115">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd74c-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bd74c-116">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd74c-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="bd74c-117">[**領域**] ページで、削除する地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd74c-117">On the **Region** page, click the region you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd74c-118">一度に複数の領域を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bd74c-118">You can delete more than one region at a time.</span></span> <span data-ttu-id="bd74c-119">これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数の領域を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd74c-119">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="bd74c-120">または、すべての領域を選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd74c-120">Or, to select all regions, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="bd74c-121">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd74c-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="bd74c-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd74c-122">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="bd74c-123">ネットワーク領域がネットワークサイトに関連付けられている場合、その領域を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd74c-123">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="bd74c-124">サイトに関連付けられている領域を削除しようとすると、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd74c-124">If you attempt to remove a region associated with a site you will receive an error message.</span></span> <span data-ttu-id="bd74c-125">領域がいずれかのサイトに関連付けられているかどうかを確認するには、地域を選択し、[<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd74c-125">To see if a region is associated with any sites, select the region and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd74c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd74c-126">See Also</span></span>


[<span data-ttu-id="bd74c-127">Lync Server 2013 でのネットワーク領域の作成または変更</span><span class="sxs-lookup"><span data-stu-id="bd74c-127">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

