---
title: Lync Server の災害復旧、高可用性、バックアップサービスの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cada393fca28895ee5f23a12fdd55eabd211128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Lync Server 2013 の障害復旧、高可用性およびバックアップ サービスの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-12_

このセクションには、障害回復操作の手順、およびペアリングされたフロントエンドプールのデータを同期するバックアップサービスの保守の手順が含まれています。

フェールオーバーとフェールバックの両方の障害回復手順は手動で行うことができます。 障害が発生した場合、管理者はフェールオーバー手順を手動で呼び出す必要があります。 プールが修復された後も、フェイルバックにも同じことが適用されます。

このセクションの残りの部分では、次のような障害回復手順について説明します。

  - 「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」で説明されているように、複数のフロントエンドプールを使用して展開を行うことができます。 これらのペアのプールでバックアップサービスが実行されているため、同期されません。

  - 中央管理ストアがいずれかのプールでホストされている場合は、これらのペアのプールの両方にインストールされて実行され、アクティブなマスターをホストしているプールと、スタンバイをホストしている他のプールのどちらかになります。

<div>


> [!IMPORTANT]
> 次の手順では、 <EM>Poolfqdn</EM>パラメーターが、障害によって影響を受けるプールの fqdn を示しますが、影響を受けるユーザーがリダイレクトされるプールには関係ありません。 影響を受けているユーザーの同じセットの場合、フェールオーバーとフェールバックの両方のコマンドレット (つまり、フェールオーバー前に最初にユーザーをホームにしたプール) で同じプールを参照します。<BR>たとえば、プール P1 に所属しているすべてのユーザーがバックアッププール (P2) にフェールオーバーした場合を想定します。 管理者が、現在 P2 で処理されているすべてのユーザーを P1 で処理するようにする場合は、管理者は次の手順を実行する必要があります。 
> <OL>
> <LI>
> <P>フェールバックコマンドレットを使用して、最初に P1 をホームにしたユーザーをすべて P2 から P1 にフェールバックします。 この場合、 <EM>Poolfqdn</EM>は P1's fqdn です。</P>
> <LI>
> <P>フェールオーバーコマンドレットを使用して、最初に P2 でホームに所属していたすべてのユーザーをフェールオーバーします。 この場合、 <EM>Poolfqdn</EM>は P2's fqdn です。</P>
> <LI>
> <P>後で管理者が p2 に戻すようにしたい場合は、 <EM>Poolfqdn</EM>は P2's fqdn です。</P></LI></OL>上記の手順1では、手順2を実行してプールの整合性を維持する必要があります。 手順1より前の手順2を実行した場合は、手順2のコマンドレットが失敗します。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でのバックアップ サービスの構成と監視](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Lync Server 2013 でのプールのフェールオーバー](lync-server-2013-failing-over-a-pool.md)

  - [Lync Server 2013 でのプールのフェールバック](lync-server-2013-failing-back-a-pool.md)

  - [Lync Server 2013 でのミラー化データベースのフェールオーバー](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Lync Server 2013 での Lync Server フェデレーションに使用するエッジ プールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Lync Server 2013 での、XMPP フェデレーションに使用するエッジ プールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Lync Server 2013 での Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジ プールのフェールバック](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Lync Server 2013 でのフロント エンド プールに関連付けられたエッジ プールの変更](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Lync Server 2013 でのバックアップ サービスを使用した会議コンテンツの復元](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

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

