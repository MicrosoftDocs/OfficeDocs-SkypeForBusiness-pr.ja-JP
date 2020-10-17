---
title: 'Lync Server 2013: ネットワーク地域リンクの削除'
description: 'Lync Server 2013: ネットワーク地域リンクの削除。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a17c1ec64460e0f7cb447597f94aadd7fd2a9ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545333"
---
# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="ac3e2-103">Lync Server 2013 でのネットワーク地域リンクの削除</span><span class="sxs-lookup"><span data-stu-id="ac3e2-103">Deleting network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac3e2-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ac3e2-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ac3e2-105">通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを公正できます。</span><span class="sxs-lookup"><span data-stu-id="ac3e2-105">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="ac3e2-106">ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。</span><span class="sxs-lookup"><span data-stu-id="ac3e2-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="ac3e2-107">Lync Server コントロールパネルを使用して、2つのネットワーク地域間の既存のリンクを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ac3e2-107">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="ac3e2-108">ネットワーク地域リンクの作成または変更の詳細については、「 [Lync Server 2013 でのネットワーク地域リンクの構成](lync-server-2013-configuring-network-region-links.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac3e2-108">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="ac3e2-109">ネットワーク地域リンクを削除するには</span><span class="sxs-lookup"><span data-stu-id="ac3e2-109">To delete a network region link</span></span>

1.  <span data-ttu-id="ac3e2-110">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ac3e2-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ac3e2-111">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac3e2-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ac3e2-112">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac3e2-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ac3e2-113">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域リンク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac3e2-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="ac3e2-114">[**地域リンク**] ページで、削除する地域リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac3e2-114">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac3e2-p103">1 つ以上の地域リンクを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数の地域リンクを選択します。また、すべての地域リンクを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac3e2-p103">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="ac3e2-118">[**編集**] メニューの [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac3e2-118">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="ac3e2-119">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac3e2-119">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ac3e2-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac3e2-120">See Also</span></span>


[<span data-ttu-id="ac3e2-121">Lync Server 2013 でのネットワーク地域リンクの構成</span><span class="sxs-lookup"><span data-stu-id="ac3e2-121">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

