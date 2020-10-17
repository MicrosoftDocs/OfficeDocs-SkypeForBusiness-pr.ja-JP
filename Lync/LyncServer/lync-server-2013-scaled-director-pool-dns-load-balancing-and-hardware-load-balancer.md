---
title: 拡張ディレクタープール-DNS 負荷分散とロードバランサー機器
description: 拡張ディレクタープール-DNS 負荷分散とロードバランサー機器。
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
ms.openlocfilehash: b30dfcc3515420ffb34343e4653e9518b1b9c3ed
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563463"
---
# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>拡張ディレクタープール-Lync Server 2013 での DNS 負荷分散とロードバランサー機器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

拡張ディレクタープール。追加容量を処理し、高可用性を実現するために複数のディレクターが展開されている場合、負荷分散によってプールのすべてのメンバーにクライアントとサーバーの通信を分散する必要があります。 ディレクターは、フロントエンドプールによく似た web サービスをホストします。 負荷分散を実現するには、ハードウェア負荷分散またはドメインネームシステム (DNS) 負荷分散とハードウェア負荷分散のどちらかを使用できます。 Web サービスにはハードウェア負荷分散が必要であり、DNS 負荷分散だけでは web サービスに必要な機能が提供されません。

次のトピックでは、DNS 負荷分散を使用してディレクタープールをハードウェア負荷分散と共に展開する際の考慮事項について説明します。 ディレクタープールでハードウェア負荷分散を使用し、DNS 負荷分散を使用しない場合については、「 [拡張ディレクタープール-Lync Server 2013 のハードウェアロードバランサー](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) 」を参照してください。このトポロジの計画要件について説明します。

![拡張ディレクター プール](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "拡張ディレクター プール")

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [証明書の概要-Lync Server 2013 での DNS および HLB の負荷分散](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [ポートの概要-Lync Server 2013 での DNS および HLB の負荷分散](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [DNS の概要-Lync Server 2013 での DNS および HLB の負荷分散](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

