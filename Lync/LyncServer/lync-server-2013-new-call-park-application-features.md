---
title: 'Lync Server 2013: コールパークアプリケーションの新機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Call Park application features
ms:assetid: bddff13c-92cc-47fd-bfd4-6e8bfbfed11b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412927(v=OCS.15)
ms:contentKeyID: 48185277
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38053645858c2fcec52f94259485184801236240
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-call-park-application-features-in-lync-server-2013"></a><span data-ttu-id="a36b3-102">Lync Server 2013 のコールパークアプリケーションの新機能</span><span class="sxs-lookup"><span data-stu-id="a36b3-102">New Call Park application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a36b3-103">_**トピックの最終更新日:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="a36b3-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="a36b3-104">コールパークアプリケーションを使用すると、エンタープライズ Voip ユーザーは通話を保留にしてから、後で電話で取得することができます。</span><span class="sxs-lookup"><span data-stu-id="a36b3-104">The Call Park application makes it possible for Enterprise Voice users to put a call on hold and then retrieve it later from any phone.</span></span> <span data-ttu-id="a36b3-105">呼び出しを保留したユーザーは、コールパークによって提供されたオービット番号にダイヤルして、保留中の通話を取得するか、インスタントメッセージング (IM) やページングシステムなどの外部メカニズムを使用して、他のユーザーに呼び出しを取得するように要求できます。</span><span class="sxs-lookup"><span data-stu-id="a36b3-105">The user who parked the call can either dial the orbit number provided by Call Park to retrieve the parked call or use an external mechanism, such as instant messaging (IM) or a paging system, to ask someone else to retrieve the call.</span></span>

<span data-ttu-id="a36b3-106">Lync Server 2013 は、フェールオーバーおよびフェールバックプロセスの形式で、新しい障害回復メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="a36b3-106">Lync Server 2013 provides new disaster recovery mechanisms in the form of failover and failback processes.</span></span> <span data-ttu-id="a36b3-107">プライマリプールで停止が発生したときに、プライマリプールに所属しているユーザーがバックアッププールのコールパークアプリケーションを利用できるようにするには、これらのフェールオーバーおよびフェールバックプロセスでコールパーク機能の回復がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a36b3-107">These failover and failback processes support recovery of Call Park functionality by allowing users who are homed in the primary pool to leverage the Call Park application of the backup pool when an outage occurs in the primary pool.</span></span> <span data-ttu-id="a36b3-108">コールパークアプリケーションの障害復旧のサポートは、ペアになったフロントエンドプールの構成と展開の一環として有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a36b3-108">Support for disaster recovery of the Call Park application is enabled as part of the configuration and deployment of paired Front End pools.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a36b3-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="a36b3-109">See Also</span></span>


[<span data-ttu-id="a36b3-110">Lync Server 2013 でのコールパークの計画</span><span class="sxs-lookup"><span data-stu-id="a36b3-110">Planning for Call Park in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-park.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

