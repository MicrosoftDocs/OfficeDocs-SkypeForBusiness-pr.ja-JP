---
title: 'Lync Server 2013: フロントエンドプールのペアリングの計画'
description: 'Lync Server 2013: フロントエンドプールのペアリングの計画。'
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
ms.openlocfilehash: ac235cf682e286132836e13b34b457adf2bfc233
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562793"
---
# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>Lync Server 2013 でのフロントエンドプールのペアリングの計画

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

Lync Server 2013 で最高の障害復旧機能を使用するには、2つの地理的に分散したサイト間でフロントエンドプールのペアを展開します。 各サイトのフロントエンド プールは、他のサイトの対応するフロントエンド プールとペアになっています。 両方のサイトがアクティブであり、Lync Server バックアップサービスは、プールの同期を維持するためのリアルタイムデータレプリケーションを提供します。 バックアップサービスは、Lync Server 2013 の新機能で、障害復旧ソリューションをサポートするように設計されています。 プールを別のフロントエンド プールとペアにすると、バックアップ サービスがフロントエンド プールにインストールされます

一方のサイトのプールで障害が発生した場合は、そのプールから他のサイトのプールにユーザーをフェールオーバーでき、それ以降はそのサイトが両方のプールのすべてのユーザーに対応します。容量計画では、障害発生時に両方のプールの全ユーザーのワークロードを処理するように各プールを設計する必要があります。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でサポートされているプールのペアのオプションとベストプラクティス](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Lync Server 2013 のバックアップレジストラーの関係](lync-server-2013-backup-registrar-relationships.md)

  - [Lync Server 2013 でのプールのフェールオーバーおよびプールのフェールバックの復旧時間](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Lync Server 2013 での中央管理ストアのフェールオーバー](lync-server-2013-central-management-store-failover.md)

  - [Lync Server 2013 でのフロントエンドプールのペアリングデータのセキュリティ](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

