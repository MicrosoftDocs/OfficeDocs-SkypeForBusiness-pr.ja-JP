---
title: 'Lync Server 2013: 既存のネットワーク領域の削除'
description: 'Lync Server 2013: 既存のネットワーク地域の削除。'
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
ms.openlocfilehash: b148f0bd92ad398ab7057a5a291bf3245df3e47e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552673"
---
# <a name="deleting-existing-network-regions-in-lync-server-2013"></a><span data-ttu-id="96c8d-103">Lync Server 2013 の既存のネットワーク領域の削除</span><span class="sxs-lookup"><span data-stu-id="96c8d-103">Deleting existing network regions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96c8d-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="96c8d-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="96c8d-105">ネットワーク地域は、複数の地理的な領域にまたがるネットワークのさまざまな部分を相互接続します。</span><span class="sxs-lookup"><span data-stu-id="96c8d-105">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="96c8d-106">すべてのネットワーク地域は、セントラル サイトと関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c8d-106">Every network region must be associated with a central site.</span></span> <span data-ttu-id="96c8d-107">このセントラル サイトは、通話受付管理 (CAC) 帯域幅ポリシー サービスが実行されているデータ センター サイトです。</span><span class="sxs-lookup"><span data-stu-id="96c8d-107">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="96c8d-108">Lync Server コントロールパネルを使用して、ネットワーク地域を構成できます。</span><span class="sxs-lookup"><span data-stu-id="96c8d-108">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="96c8d-109">ネットワーク地域には、オーディオとビデオの接続でインターネット経由の代替パスを許可するかどうかを決定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="96c8d-109">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="96c8d-110">Lync Server コントロールパネルから、ネットワーク地域を作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="96c8d-110">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="96c8d-111">既存のネットワーク地域を削除するには、このトピックを参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="96c8d-111">Use this topic to delete existing network regions.</span></span> <span data-ttu-id="96c8d-112">既存のネットワーク地域の作成または変更の詳細については、「 [Lync Server 2013 でのネットワーク地域の作成または変更](lync-server-2013-creating-or-modifying-network-regions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c8d-112">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-delete-a-network-region"></a><span data-ttu-id="96c8d-113">ネットワーク地域を削除するには</span><span class="sxs-lookup"><span data-stu-id="96c8d-113">To delete a network region</span></span>

1.  <span data-ttu-id="96c8d-114">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="96c8d-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="96c8d-115">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="96c8d-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="96c8d-116">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c8d-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="96c8d-117">左側のナビゲーション バーで [**ネットワーク構成**]、[**地域**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="96c8d-117">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="96c8d-118">[**地域**] ページで、削除する地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96c8d-118">On the **Region** page, click the region you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96c8d-p103">一度に複数の地域を削除できます。これを実行するには、Ctrl キーを押しながら複数の地域を選択します。また、すべての地域を選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96c8d-p103">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="96c8d-122">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96c8d-122">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="96c8d-123">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96c8d-123">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="96c8d-p104">ネットワーク地域がネットワーク サイトに関連付けられている場合は、削除することはできません。サイトに関連付けられている地域を削除しようとすると、エラー メッセージが表示されます。地域がサイトに関連付けられているかどうかを確認するには、その地域を選択して [<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96c8d-p104">A network region cannot be removed if it is associated with a network site. If you attempt to remove a region associated with a site you will receive an error message. To see if a region is associated with any sites, select the region and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="96c8d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="96c8d-127">See Also</span></span>


[<span data-ttu-id="96c8d-128">Lync Server 2013 でのネットワーク地域の作成または変更</span><span class="sxs-lookup"><span data-stu-id="96c8d-128">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

