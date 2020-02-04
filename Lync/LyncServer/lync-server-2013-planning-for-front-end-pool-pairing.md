---
title: 'Lync Server 2013: フロント エンド プールのペアリングの計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d85f6e19f3aa74c09a522e737d1223095f17d7c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>Lync Server 2013 でのフロント エンド プールのペアリングの計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

Lync Server 2013 で最高の障害回復機能を使用するには、地理的に分散した2つのサイトにフロントエンドプールのペアを展開します。 各サイトには、他のサイトで対応するフロントエンドプールとペアリングされたフロントエンドプールが含まれています。 両方のサイトがアクティブになり、Lync Server バックアップサービスはリアルタイムのデータレプリケーションを提供して、プールの同期を維持します。 バックアップサービスは、Lync Server 2013 の新機能であり、障害回復ソリューションをサポートするように設計されています。 プールを別のフロントエンドプールとペアリングすると、フロントエンドプールにインストールされます。

1つのサイトのプールで障害が発生した場合は、そのプールのユーザーを他のサイトのプールにフェイルオーバーすることができます。これにより、両方のプールのすべてのユーザーにサービスが提供されます。 容量の計画を立てるために、各プールは、障害が発生した場合に両方のプールのすべてのユーザーの作業負荷を処理するように設計する必要があります。

<div>

## <a name="in-this-section"></a>このセクション中

  - [サポートされているプールペアリングオプションと Lync Server 2013 のベストプラクティス](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Lync Server 2013 のバックアップ レジストラー関係](lync-server-2013-backup-registrar-relationships.md)

  - [Lync Server 2013 のプールのフェールオーバーおよびフェールバックの復旧時間](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Lync Server 2013 の中央管理ストアのフェールオーバー](lync-server-2013-central-management-store-failover.md)

  - [Lync Server 2013 でのフロントエンド プールのペアリング データのセキュリティ](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

