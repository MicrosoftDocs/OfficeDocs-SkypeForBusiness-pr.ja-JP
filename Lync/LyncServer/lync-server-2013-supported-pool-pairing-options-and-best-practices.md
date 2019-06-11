---
title: Lync Server 2013 でサポートされているプールペアリングオプションとベストプラクティス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00202aeb4db74ec81671e557a0679a9f41046b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>サポートされているプールペアリングオプションと Lync Server 2013 のベストプラクティス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2017-03-09_

2つのデータセンター間の距離には制限はありません。これによって、フロントエンドプールが互いにペアリングされます。 同じワールドリージョンの2つのデータセンターを使用して、その間に高速リンクを使用することをお勧めします。 この2つのデータセンターは、1つの災害が同時に発生するのを避けるために、十分に分離されていることをお勧めします。

世界各地の2つのデータセンターを使用することは可能ですが、データレプリケーションの遅延によるデータ損失の増加につながる可能性があります。

どのプールをペアにするかを計画する場合、サポートされるのは次の組み合わせのみであることに注意してください。

  - Enterprise Edition プールとペアにできるのは他の Enterprise Edition プールのみです。 同様に、Standard Edition プールとペアにできるのは他の Standard Edition プールのみです。

  - 物理プールとペアにできるのは他の物理プールのみです。 同様に、仮想プールとペアにできるのは他の仮想プールのみです。

  - ペアリングされているプールは、同じオペレーティングシステムを実行している必要があります。

トポロジ ビルダーでもトポロジ検証でも、この推奨事項に従わない方法で 2 つのプールをペアにする操作は阻止されません。たとえば、トポロジ ビルダーでは、Enterprise Edition プールと Standard Edition プールをペアにできます。ただし、そのような組み合わせのペアはサポートされません。

1組の各プールには、障害が発生した場合に両方のプールのすべてのユーザーに対してサービスを提供する能力が必要です。

Enterprise Edition プールをペアとして使用する場合は、バックエンドサーバーに高可用性を実装することもできますが、Standard Edition プールのペアには、障害回復の手段のみが用意されています。

</div>

<span> </span>

</div>

</div>

</div>

