---
title: Lync Server 2013 の負荷分散の要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 016ace11375483fbeaa59199e9f1cdae23654cd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513824"
---
# <a name="load-balancing-requirements-for-lync-server-2013"></a>Lync Server 2013 の負荷分散の要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-05_

フロントエンドプール、ディレクタープール、またはエッジサーバープールを使用している場合は、これらのプールの負荷分散を展開する必要があります。 ロード バランシングによって、プール内のすべてのサーバーにトラフィックが分散されます。

Lync Server 2013 は、クライアントとサーバー間のトラフィックに対して、ドメインネームシステム (DNS) 負荷分散とハードウェア負荷分散という2種類の負荷分散ソリューションをサポートしています。 DNS 負荷分散には、管理の簡素化、効率的なトラブルシューティング、および潜在的なハードウェアロードバランサーの問題からの Lync Server のトラフィックの大部分を分離する機能など、いくつかの利点があります。

以下の制限事項を考慮して、展開内のプールごとに適切なロード バランシング ソリューションを決定します。

  - 内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。1 つのインターフェイスで DNS ロード バランシングを使用し、もう 1 つのインターフェイスでロード バランサー機器を使用することはできません。

  - 一部の種類のトラフィックでは、ハードウェア ロード バランサーが必要です。たとえば、HTTP トラフィックでは、DNS ロード バランシングではなくハードウェア ロード バランサーが必要です。クライアントとサーバー間の Web トラフィックでは、DNS ロード バランシングは正常に機能しません。

ロードバランサー機器ソリューションの選択の詳細については、「 [Lync Server 2013 のハードウェアロードバランサーの要件](lync-server-2013-hardware-load-balancer-requirements.md)」を参照してください。

プールで DNS ロード バランシングを使用するように選択し、HTTP トラフィックなどのトラフィック用にハードウェア ロード バランサーも実装する必要がある場合、ハードウェア ロード バランサーの管理は非常に簡素化されます。 たとえば、HTTP トラフィックと HTTPS トラフィックのみが管理され、他のすべてのプロトコルは DNS 負荷分散によって管理されるため、ハードウェアロードバランサーの構成はより簡単になります。 詳細については、「 [Lync Server 2013 の DNS 負荷分散](lync-server-2013-dns-load-balancing.md)」を参照してください。

サーバー間トラフィックの場合、Lync Server 2013 ではトポロジに対応した負荷分散が使用されます。 サーバーは、中央管理ストアで公開されているトポロジを読み取り、トポロジ内のサーバーの Fqdn を取得し、そのトラフィックをサーバー間で自動的に分配します。 管理者はこの種の負荷分散を設定または管理する必要はありません。

DNS 負荷分散を使用していて、特定のコンピューターへのトラフィックをブロックする必要がある場合は、IP アドレスエントリをプールの FQDN から削除するだけで十分ではありません。 コンピューターの DNS エントリも削除する必要があります。

</div>

<span> </span>

</div>

</div>

</div>

