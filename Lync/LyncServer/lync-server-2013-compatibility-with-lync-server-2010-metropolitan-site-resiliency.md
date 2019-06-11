---
title: Lync Server 2013 と Lync Server 2010 大都市サイト復元の互換性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3079f05d9860fd659d19df7b71ee633c0cea3fe2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a>Lync Server 2010 大都市サイト復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-03-19_

Lync Server 2010 でサポートされているメトロポリタンサイトの復元ソリューションは、Lync Server 2013 ではサポートされていません。 このソリューションは、同じメトロポリタンエリア内の2つのデータセンターにわたる単一のフロントエンドプールに関連しています。

メトロポリタンサイトの復元ソリューションは、データセンターの損失から回復するように設計されています。 2つのデータセンターでプールをスパンしている場合、通常は、1つのデータセンターと2番目のデータセンターの残りの半分にフロントエンドの半分を配置します。 データセンター全体が失われた場合は、フロントエンドサーバーの半分が失われます。 これにより、Lync Server 2013 のフロントエンドプールの新しい分散システムモデルで問題が発生する可能性があります。 詳細については、「 [Lync Server 2013 のフロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント」を](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)参照してください。

</div>

<span> </span>

</div>

</div>

</div>

