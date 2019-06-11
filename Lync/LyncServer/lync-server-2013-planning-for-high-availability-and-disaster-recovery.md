---
title: 'Lync Server 2013: 高可用性および障害復旧の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 092e59813f76690233a950cd8ce914df47146d37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 での高可用性および障害復旧の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-31_

Lync server 2010 の場合と同様に、Lync Server 2013 のほとんどのサーバーの役割に関する高可用性の主要なスキームは、プールによるサーバーの冗長性に基づいています。 特定のサーバーの役割を実行するサーバーで障害が発生した場合は、プール内の同じ役割を実行する他のサーバーがそのサーバーの負荷を引き受けます。 同じことが、フロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターでも実行されます。

Lync Server 2013 では、サーバーの地理的な dispersement を2つのデータセンターに導入して、1つのプールまたはサイトを停止する必要がある場合に、フロントエンドプール用の新しい障害回復手段を追加します。

また、バックエンドデータベースの同期 SQL ミラーリングをサポートすることにより、バックエンドサーバーの高可用性が強化されています。2013

このセクションでは、これらの主要な高可用性および障害回復機能について説明し、他のサーバーの役割に対して高可用性と障害回復を実現するための手順についても説明します。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でのフロントエンド プールの障害復旧](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Lync Server 2013 でのエッジ サーバーの障害復旧](lync-server-2013-edge-server-disaster-recovery.md)

  - [Lync Server 2013 でのエンタープライズ VoIP の復旧の計画](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Lync Server 2013 の障害復旧用の通話管理機能](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Lync Server 2013 の高可用性と障害復旧に対応した常設チャット サーバーの構成](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2010 大都市サイト復元](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

