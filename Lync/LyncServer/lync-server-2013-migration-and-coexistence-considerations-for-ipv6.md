---
title: 'Lync Server 2013: IPv6 の移行および共存の検討事項'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8adf81df14d5c87eb2b54b63d9a58fc1b6f5b97e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Lync Server 2013 における IPv6 の移行および共存の検討事項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-14_

IP version 6 (IPv6) は、Lync Server 2010 または Office Communications Server ではサポートされていません。 パイロットのために、Lync Server 2010 および Lync Server 2013 の2つのスタックを共存させることができます。 いずれかのプールで IPv6 (デュアルスタックネットワーク) を有効にする前に、特定のセントラルサイトのすべてのプールを Lync Server 2013 にアップグレードすることをお勧めします。 IPv6 に対応したプールのみを構成する必要がある場合は、テスト用のラボ環境に IPv6 専用のプールを設定することをお勧めします。

次のシナリオは、移行と共存でサポートされます。

  - Lync server 2013、Lync Server 2010、Office Communications Server 2007 R2 プール (IPv4 モード) では、Lync Server 2013 とデュアルスタックモードを共存させることができます。

  - Ipv6 専用プールが孤立している場合は、IPv6 専用モードの Lync Server 2013 プール。

</div>

<span> </span>

</div>

</div>

</div>

