---
title: 'Lync Server 2013: 高可用性および障害復旧の計画'
TOCTitle: 高可用性および障害復旧の計画
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48271365
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での高可用性および障害復旧の計画

 

_**トピックの最終更新日:** 2013-10-31_

Lync Server 2010 と同様に、Lync Server 2013 のほとんどのサーバーの役割の主要な高可用性スキームは、プーリングによるサーバー冗長性に基づいています。あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。

Lync Server 2013 では、1 つのプールまたはサイト全体がダウンした場合に備えて、サーバーを 2 つのデータ センターに地理的に分散してサービスを続行する、フロントエンド プール用の新しい障害復旧手段が追加されました。

Lync Server 2013 では、バックエンド データベースの同期 SQL ミラーリングをサポートすることによってバックエンド サーバーの高可用性も強化されました。

このセクションでは、これらの主要な高可用性機能と障害復旧機能について説明し、別のサーバーの役割の高可用性と障害復旧に使用できる手順についても説明します。

## このセクション中

  - [Lync Server 2013 でのフロントエンド プールの障害復旧](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Lync Server 2013 でのエッジ サーバーの障害復旧](lync-server-2013-edge-server-disaster-recovery.md)

  - [Lync Server 2013 でのエンタープライズ VoIP の復旧の計画](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Lync Server 2013 の障害復旧用の通話管理機能](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Lync Server 2013 の高可用性と障害復旧に対応した常設チャット サーバーの構成](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2010 大都市サイト復元](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

