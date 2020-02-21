---
title: Lync Server 2013 サポートされているプールのペアのオプションとベストプラクティス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d33bc5e9622728fb4ee9c2a6a566e6010466d577
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Lync Server 2013 でサポートされているプールのペアのオプションとベストプラクティス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-03-09_

相互にペアとなるフロントエンド プールが含まれる 2 つのデータ センター間の距離に制限はありません。同一地域内の 2 つのデータ センターを高速リンクで接続して使用することをお勧めします。2 つのデータ センターが両方とも同時に同じ障害の影響を受けないように、両者を十分に分離することをお勧めします。

異なる地域にある 2 つのデータ センターを使用することもできますが、データ レプリケーションの待ち時間が原因でデータ損失が発生する可能性が高くなります。

どのプールをペアにするかを計画するときは、次の組み合わせのみがサポートされることに注意してください。

  - Enterprise Edition プールとペアにできるのは他の Enterprise Edition プールのみです。同様に、Standard Edition プールとペアにできるのは他の Standard Edition プールのみです。

  - 物理プールとペアにできるのは他の物理プールのみです。同様に、仮想プールとペアにできるのは他の仮想プールのみです。

  - ペアになっているプールは、同じオペレーティングシステムを実行している必要があります。

トポロジ ビルダーでもトポロジ検証でも、この推奨事項に従わない方法で 2 つのプールをペアにする操作は阻止されません。 たとえば、トポロジ ビルダーでは、Enterprise Edition プールと Standard Edition プールをペアにできます。 ただし、これらの種類の組み合わせはサポートされていません。

ペアにするどちらのプールにも、障害発生時に備えて、両方のプールのすべてのユーザーに機能を提供できる処理能力が必要です。

Enterprise Edition プールをペアにする場合、バックエンド サーバーに高可用性も実装できますが、Standard Edition プールのペアの場合に使用できるのは障害復旧手段のみです。

</div>

<span> </span>

</div>

</div>

</div>

