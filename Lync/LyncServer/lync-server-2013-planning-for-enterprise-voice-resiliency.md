---
title: 'Lync Server 2013: エンタープライズ Voip の復元の計画'
description: 'Lync Server 2013: エンタープライズ Voip の復元の計画。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice resiliency
ms:assetid: ca116700-1055-4ca5-9b87-4c7f380c3655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398840(v=OCS.15)
ms:contentKeyID: 48185408
ms.date: 10/17/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2adcf09b87264666924a16543a1b21e8e3cae39f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567263"
---
# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="3ca19-103">Lync Server 2013 でのエンタープライズ Voip の復元の計画</span><span class="sxs-lookup"><span data-stu-id="3ca19-103">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ca19-104">_**トピックの最終更新日:** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="3ca19-104">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="3ca19-105">音声の復元とは、WAN (ワイドエリアネットワーク) 障害またはその他の原因によって、Lync Server 2013 をホストするセントラルサイトが使用できなくなった場合に、ユーザーが通話を継続することができるかどうかを表します。</span><span class="sxs-lookup"><span data-stu-id="3ca19-105">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="3ca19-106">中央サイトで障害が発生した場合、エンタープライズ VoIP サービスでは、バックアップ サイトへの円滑なフェールオーバーにより中断せずにサービスを提供し続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca19-106">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="3ca19-107">WAN 障害の場合は、ブランチ サイトの通話をローカルの PSTN ゲートウェイにリダイレクトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca19-107">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="3ca19-108">ここでは、中央サイトまたは WAN で障害が発生した場合の音声の復元の計画について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ca19-108">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3ca19-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3ca19-109">In This Section</span></span>

  - [<span data-ttu-id="3ca19-110">Lync Server 2013 での中央サイトの音声の復元の計画</span><span class="sxs-lookup"><span data-stu-id="3ca19-110">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="3ca19-111">Lync Server 2013 でのブランチサイトの音声の復元の計画</span><span class="sxs-lookup"><span data-stu-id="3ca19-111">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

