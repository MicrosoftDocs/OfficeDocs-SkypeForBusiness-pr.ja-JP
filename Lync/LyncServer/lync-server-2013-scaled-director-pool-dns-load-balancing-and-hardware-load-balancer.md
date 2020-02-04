---
title: 拡張ディレクター プール - DNS 負荷分散とロード バランサー機器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16203f7e291b7957793e71872483c93f2d1d04d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>拡張ディレクター プール - Lync Server 2013 の DNS 負荷分散とロード バランサー機器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

スケーリングされたディレクタープール。追加の容量を処理し、高可用性を実現するために複数のディレクターが展開されている場合は、プールのすべてのメンバーにクライアントとサーバーの通信を配布するために負荷分散を行う必要があります。 ディレクターは、フロントエンドプールのような web サービスをホストします。 負荷分散を実現するには、ハードウェア負荷分散またはドメインネームシステム (DNS) の負荷分散とハードウェアの負荷分散のいずれかを使用できます。 Web サービスにはハードウェア負荷分散が必要であり、DNS 負荷分散単体では、web サービスに必要な機能が提供されません。

次のトピックでは、DNS の負荷分散とハードウェアの負荷分散を使用して、ディレクタープールを展開する場合の計画に関する考慮事項について説明します。 ハードウェアの負荷分散は使用するが、ディレクタープールでは DNS の負荷分散を使用しない場合は、そのトポロジの計画要件について説明している「 [Lync Server 2013 のスケーリングされたディレクタープール-ハードウェアロードバランサー](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) 」を参照してください。

![スケーリングされたディレクタープール](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "スケーリングされたディレクタープール")

<div>

## <a name="in-this-section"></a>このセクション中

  - [証明書の概要 - Lync Server 2013 の DNS および HLB による負荷分散](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [ポートの概要 - Lync Server 2013 における DNS および HLB による負荷分散](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [DNS の概要 - Lync Server 2013 での DNS と HLB 負荷分散](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

