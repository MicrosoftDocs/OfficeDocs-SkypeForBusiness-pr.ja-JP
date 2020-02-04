---
title: 'Lync Server 2013: コール パーク アプリケーションの新機能'
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
ms.openlocfilehash: ed681497eee3033ea18cdac0487257f02052491c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-call-park-application-features-in-lync-server-2013"></a><span data-ttu-id="8e0bb-102">Lync Server 2013 のコール パーク アプリケーションの新機能</span><span class="sxs-lookup"><span data-stu-id="8e0bb-102">New Call Park application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e0bb-103">_**最終更新日:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="8e0bb-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="8e0bb-104">コールパークアプリケーションを使用すると、エンタープライズボイスユーザーは通話を保留にしてから、どの電話からでも通話を受信することができます。</span><span class="sxs-lookup"><span data-stu-id="8e0bb-104">The Call Park application makes it possible for Enterprise Voice users to put a call on hold and then retrieve it later from any phone.</span></span> <span data-ttu-id="8e0bb-105">通話を保留にしたユーザーは、コールパークによって提供された軌道番号をダイヤルして、保留中の通話を取得したり、インスタントメッセージング (IM) やページングシステムなどの外部メカニズムを使って、他の人に通話を取得するように指示することができます。</span><span class="sxs-lookup"><span data-stu-id="8e0bb-105">The user who parked the call can either dial the orbit number provided by Call Park to retrieve the parked call or use an external mechanism, such as instant messaging (IM) or a paging system, to ask someone else to retrieve the call.</span></span>

<span data-ttu-id="8e0bb-106">Lync Server 2013 には、フェールオーバーとフェールバックのプロセスの形式での新しい障害回復メカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8e0bb-106">Lync Server 2013 provides new disaster recovery mechanisms in the form of failover and failback processes.</span></span> <span data-ttu-id="8e0bb-107">これらのフェイルオーバーおよびフェイルバック処理は、プライマリプールをホームにしているユーザーが、プライマリプールで停止したときにバックアッププールのコールパークアプリケーションを利用できるようにすることによって、コールパーク機能の回復をサポートします。</span><span class="sxs-lookup"><span data-stu-id="8e0bb-107">These failover and failback processes support recovery of Call Park functionality by allowing users who are homed in the primary pool to leverage the Call Park application of the backup pool when an outage occurs in the primary pool.</span></span> <span data-ttu-id="8e0bb-108">コールパークアプリケーションのディザスタリカバリのサポートは、ペアリングされたフロントエンドプールの構成と展開の一環として有効になります。</span><span class="sxs-lookup"><span data-stu-id="8e0bb-108">Support for disaster recovery of the Call Park application is enabled as part of the configuration and deployment of paired Front End pools.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8e0bb-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e0bb-109">See Also</span></span>


[<span data-ttu-id="8e0bb-110">Lync Server 2013 でのコール パークの計画</span><span class="sxs-lookup"><span data-stu-id="8e0bb-110">Planning for Call Park in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-park.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

