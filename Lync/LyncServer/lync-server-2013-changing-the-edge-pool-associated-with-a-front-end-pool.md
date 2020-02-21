---
title: 'Lync Server 2013: フロントエンドプールに関連付けられたエッジプールの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73d28a6641df35ac1de29fb1f6668e628e8e0ec9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="c2ecc-102">Lync Server 2013 のフロントエンドプールに関連付けられたエッジプールの変更</span><span class="sxs-lookup"><span data-stu-id="c2ecc-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2ecc-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c2ecc-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c2ecc-104">エッジ プールがダウンして同じサイトのフロントエンド プールがまだ実行中の場合、問題の発生したエッジ プールが復元されるまで、別のサイトのエッジ プールを使用するようにフロントエンド プールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2ecc-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="c2ecc-105">フロントエンド プールに関連付けられたエッジ プールを変更する</span><span class="sxs-lookup"><span data-stu-id="c2ecc-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="c2ecc-106">トポロジ ビルダーで、変更するフロントエンド プールの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="c2ecc-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="c2ecc-107">プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2ecc-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="c2ecc-108">[**関連付け**] セクションの、[**エッジ プールの関連付け (メディア コンポーネント用) の**] 下のドロップダウン ボックスを使用して、このフロントエンド プールを関連付けるエッジ プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="c2ecc-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="c2ecc-109">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2ecc-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c2ecc-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2ecc-110">See Also</span></span>


[<span data-ttu-id="c2ecc-111">Lync Server 2013 でのエッジサーバーの障害復旧</span><span class="sxs-lookup"><span data-stu-id="c2ecc-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

