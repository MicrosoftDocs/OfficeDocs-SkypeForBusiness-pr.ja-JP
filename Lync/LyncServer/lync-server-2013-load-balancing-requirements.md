---
title: Lync Server 2013 のロードバランシングの要件
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
ms.openlocfilehash: 8081ba60d826f0f765533abdb6c0f548045a7fa8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a>Lync Server 2013 の負荷分散の要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-05_

フロントエンドプール、ディレクタープール、またはエッジサーバープールを使用している場合は、これらのプールの負荷分散を展開する必要があります。 負荷分散によって、プール内のすべてのサーバーにトラフィックが分散されます。

Lync Server 2013 は、クライアント間トラフィック用に2種類の負荷分散ソリューション (ドメインネームシステム (DNS) 負荷分散とハードウェアの負荷分散) をサポートしています。 DNS ロードバランシングには、管理の簡素化、効率的なトラブルシューティング、Lync サーバートラフィックの多くを潜在的なハードウェアロードバランサーの問題から切り分ける機能など、いくつかの利点があります。

以下の制限事項を考慮して、展開内のプールごとに適切な負荷分散ソリューションを決定します。

  - 内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類の負荷分散を使用する必要があります。1 つのインターフェイスで DNS 負荷分散を使用し、もう 1 つのインターフェイスでロード バランサー機器を使用することはできません。

  - 一部の種類のトラフィックでは、ロード バランサー機器が必要です。たとえば、HTTP トラフィックでは、DNS 負荷分散ではなくロード バランサー機器が必要です。クライアントとサーバー間の Web トラフィックでは、DNS 負荷分散は正常に機能しません。

ハードウェアロードバランサーソリューションの選択の詳細については、「 [Lync Server 2013 のハードウェアロードバランサーの要件](lync-server-2013-hardware-load-balancer-requirements.md)」を参照してください。

プールで DNS 負荷分散を使用するように選択し、HTTP トラフィックなどのトラフィック用にロード バランサー機器も実装する必要がある場合、ロード バランサー機器の管理は非常に簡素化されます。 たとえば、ロード バランサー機器の構成は、他のすべてのプロトコルが DNS 負荷分散によって管理されるのに対して、HTTP および HTTPS のトラフィックを管理するのみであるため簡素になります。 詳細については、「 [Lync Server 2013 の DNS の負荷分散](lync-server-2013-dns-load-balancing.md)」を参照してください。

サーバー間トラフィックの場合、Lync Server 2013 はトポロジに対応した負荷分散を使用します。 サーバーは、中央管理ストアで公開されているトポロジを読み取り、トポロジ内のサーバーの Fqdn を取得し、サーバー間でトラフィックを自動的に分散します。 この種の負荷分散では、管理者が設定または管理を行う必要はありません。

DNS 負荷分散を使用していて、特定のコンピューターへのトラフィックを遮断する必要がある場合は、プールの FQDN から IP アドレス エントリを削除するだけでは十分ではありません。コンピューターの DNS エントリも削除する必要があります。

</div>

<span> </span>

</div>

</div>

</div>

