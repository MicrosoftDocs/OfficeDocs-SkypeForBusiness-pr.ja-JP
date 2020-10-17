---
title: Lync Server の障害復旧、高可用性、およびバックアップサービスの管理
description: Lync Server の障害復旧、高可用性、およびバックアップサービスの管理。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e440c8c72ab5e66d27a86dfce963368dff804bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569413"
---
# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Lync Server 2013 の障害復旧、高可用性、およびバックアップサービスの管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-12_

このセクションには、障害復旧操作のほか、ペアになったフロントエンドプール内のデータを同期するバックアップサービスの保守の手順が記載されています。

障害回復の手順は、フェールオーバーとフェールバックのどちらも、手動によるものです。障害が発生した場合、管理者はフェールオーバーの手順を手動で開始する必要があります。プール修復後のフェールバックにも同じことが当てはまります。

このセクションの以降の部分における障害回復の手順では、以下のことを前提としています。

  - 「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」で説明されているように、別のサイトにある、ペアのフロントエンドプールを備えた展開を使用している。 バックアップ サービスは、ペアになったプールの同期を保つためにこれらのプール上で実行されています。

  - 中央管理ストアがどちらのプールでホストされている場合でも、その中の両方のプールにインストールされて実行されており、アクティブなマスターとスタンバイをホストしている他のプールのどちらかによってホストされます。

<div>


> [!IMPORTANT]
> 以下の手順では、影響を受けるユーザーのリダイレクト元になるプールではなく、障害の影響を受けるプールの完全修飾 FQDN を PoolFQDN<EM></EM> パラメーターが参照しています。影響を受ける同じユーザー群が同じ場合、このパラメーターはフェールオーバーとフェールバックの各コマンドレットで同じプール (つまり、ユーザーがフェールオーバー前に最初に所属していたプール) を参照します。<BR>たとえば、プール P1 に所属していたすべてのユーザーがバックアップ プール P2 にフェールオーバーされた場合を想定します。 管理者が、P2 でサービスを提供しているすべてのユーザーを P1 によって処理するように移行する場合は、管理者は次の手順を実行する必要があります。 
> <OL>
> <LI>
> <P>フェールバックコマンドレットを使用して、最初に P1 に所属していたすべてのユーザーを P2 から P1 にフェールバックします。 この場合、PoolFQDN<EM></EM> は P1 の FQDN になります。</P>
> <LI>
> <P>フェールオーバーコマンドレットを使用して、最初に P2 に所属していたすべてのユーザーを P1 にフェールオーバーします。 この場合、PoolFQDN<EM></EM> は P2 の FQDN になります。</P>
> <LI>
> <P>後で管理者がこれらの P2 ユーザーを P2 にフェールバックする場合、 <EM>Poolfqdn</EM> は p2 fqdn になります。</P></LI></OL>手順1を実行してから、プールの整合性を保持する必要があることに注意してください。 手順1の前に手順2を実行すると、手順2のコマンドレットは失敗します。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのバックアップサービスの構成と監視](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Lync Server 2013 でのプールのフェールオーバー](lync-server-2013-failing-over-a-pool.md)

  - [Lync Server 2013 でのプールのフェールバック](lync-server-2013-failing-back-a-pool.md)

  - [Lync Server 2013 でのミラー化されたデータベースのフェールオーバー](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Lync Server 2013 での Lync Server フェデレーションに使用するエッジプールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Lync Server 2013 での XMPP フェデレーションに使用するエッジプールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Lync server 2013 での Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジプールのフェールバック](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Lync Server 2013 のフロントエンドプールに関連付けられたエッジプールの変更](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Lync Server 2013 でのバックアップサービスを使用した会議コンテンツの復元](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での高可用性および障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

