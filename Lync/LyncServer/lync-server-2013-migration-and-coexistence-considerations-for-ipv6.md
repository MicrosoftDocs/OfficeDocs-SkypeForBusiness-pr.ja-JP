---
title: 'Lync Server 2013: IPv6 の移行と共存の考慮事項'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f091b12b12913af107991c86b87d1d738bf88bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513614"
---
# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Lync Server 2013 での IPv6 の移行と共存の考慮事項

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-14_

IP version 6 (IPv6) は、Lync Server 2010 または Office Communications Server ではサポートされていません。 パイロット目的で、Lync Server 2010 と Lync Server 2013 のデュアルスタック共存をテストできます。 任意のプールに対して IPv6 (デュアルスタックネットワーク) を有効にする前に、特定の中央サイトのすべてのプールを Lync Server 2013 にアップグレードすることをお勧めします。 IPv6 に対応したプールのみを構成する必要がある場合は、テスト用のラボ環境に IPv6 専用のプールを設定することをお勧めします。

次のシナリオは、移行と共存でサポートされます。

  - Lync server 2013、Lync Server 2010、および Office Communications Server 2007 R2 プールを IPv4 モードで使用すると、デュアルスタックモードで Lync Server 2013 と共存させることができます。

  - Ipv6 専用のプールが孤立している場合は、Lync Server 2013 プールを IPv6 専用モードにします。

</div>

<span> </span>

</div>

</div>

</div>

