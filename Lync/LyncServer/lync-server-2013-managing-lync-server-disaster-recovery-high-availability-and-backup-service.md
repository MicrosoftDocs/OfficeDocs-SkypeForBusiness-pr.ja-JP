---
title: 'Lync Server 2013: Lync Server の障害復旧、高可用性およびバックアップ サービスの管理'
TOCTitle: Lync Server 2013 の障害復旧、高可用性およびバックアップ サービスの管理
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49887220
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の障害復旧、高可用性およびバックアップ サービスの管理

 

_**トピックの最終更新日:** 2012-11-12_

このセクションには、障害復旧操作のほか、ペアになったフロントエンド プール内のデータを同期するバックアップ サービスの保守を行う手順が含まれています。

障害復旧の手順は、フェールオーバーとフェールバックのどちらも、手動によるものです。障害が発生した場合、管理者はフェールオーバーの手順を手動で開始する必要があります。プール修復後のフェールバックにも同じことが当てはまります。

このセクションの以降の部分における障害復旧の手順では、以下のことを前提としています。

  - ペアになったフロントエンド プールが別々のサイトに配置された展開が存在します (「[Lync Server 2013 での高可用性および障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」の説明を参照)。バックアップ サービスは、ペアになったプールの同期を保つためにこれらのプール上で実行されています。

  - 中央管理ストアは、どちらかのプールでホストされていても、そのインストールと実行はペアになったプールの双方で行われ、一方のプールではアクティブなマスター側を、他方のプールではスタンバイ側をそれぞれホストします。


> [!IMPORTANT]
> 以下の手順では、影響を受けるユーザーのリダイレクト元になるプールではなく、障害の影響を受けるプールの完全修飾 FQDN を PoolFQDN パラメーターが参照しています。影響を受ける同じユーザー群が同じ場合、このパラメーターはフェールオーバーとフェールバックの各コマンドレットで同じプール (つまり、ユーザーがフェールオーバー前に最初に所属していたプール) を参照します。<BR>たとえば、プール P1 に所属していたすべてのユーザーがバックアップ プール P2 にフェールオーバーされた場合を想定します。現在 P2 によるサービス提供を受けているすべてのユーザーを移動して P1 によるサービス提供を受けるようにする場合、管理者は、以下の手順を実行する必要があります。 
> <OL>
> <LI>
> <P>フェールバック用コマンドレットを使用して、当初 P1 に所属していたすべてのユーザーを P2 から P1 にフェールバックします。この場合、PoolFQDN は P1 の FQDN になります。</P>
> <LI>
> <P>フェールオーバー用コマンドレットを使用して、当初 P2 に所属していたすべてのユーザーを P1 にフェールオーバーします。この場合、PoolFQDN は P2 の FQDN になります。</P>
> <LI>
> <P>後で管理者がこれらの P2 ユーザーを P2 にフェールバックする場合、PoolFQDN は P2 の FQDN になります。</P></LI></OL>上記の手順 1. は、プールの整合性を保持するために手順 2. の前に実行する必要があります。手順 1. の前に手順 2. を行おうとすると、手順 2. のコマンドレットは失敗します。



## このセクション中

  - [Lync Server 2013 でのバックアップ サービスの構成と監視](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Lync Server 2013 でのプールのフェールオーバー](lync-server-2013-failing-over-a-pool.md)

  - [Lync Server 2013 でのプールのフェールバック](lync-server-2013-failing-back-a-pool.md)

  - [Lync Server 2013 でのミラー化データベースのフェールオーバー](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Lync Server 2013 での Lync Server フェデレーションに使用するエッジ プールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Lync Server 2013 での、XMPP フェデレーションに使用するエッジ プールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Lync Server 2013 での Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジ プールのフェールバック](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Lync Server 2013 でのフロント エンド プールに関連付けられたエッジ プールの変更](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Lync Server 2013 でのバックアップ サービスを使用した会議コンテンツの復元](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

## 関連項目

#### 概念

[Lync Server 2013 での高可用性および障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

