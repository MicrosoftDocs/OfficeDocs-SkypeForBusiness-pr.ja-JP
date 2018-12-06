---
title: 'Lync Server 2013: フロント エンド プールのペアリングの計画'
TOCTitle: フロント エンド プールのペアリングの計画
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48273595
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのフロント エンド プールのペアリングの計画

 

_**トピックの最終更新日:** 2012-09-28_

Lync Server 2013 での障害復旧機能を最善にするには、フロントエンド プールのペアを地理的に離れた 2 つのサイトに展開します。各サイトのフロントエンド プールは、他のサイトの対応するフロントエンド プールとペアになっています。両方のサイトがアクティブになっており、 Lync Server のバックアップ サービスが提供するリアルタイムのデータ レプリケーションによってプールの同期が維持されます。バックアップ サービスは Lync Server 2013 の新機能であり、障害復旧ソリューションをサポートするように設計されています。プールを別のフロントエンド プールとペアにすると、バックアップ サービスがフロントエンド プールにインストールされます

一方のサイトのプールで障害が発生した場合は、そのプールから他のサイトのプールにユーザーをフェールオーバーでき、それ以降はそのサイトが両方のプールのすべてのユーザーに対応します。容量計画では、障害発生時に両方のプールの全ユーザーのワークロードを処理するように各プールを設計する必要があります。

## このセクション中

  - [Lync Server 2013 でサポートされているプール ペアリング オプションとベスト プラクティス](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Lync Server 2013 のバックアップ レジストラー関係](lync-server-2013-backup-registrar-relationships.md)

  - [Lync Server 2013 のプールのフェールオーバーおよびフェールバックの復旧時間](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Lync Server 2013 の中央管理ストアのフェールオーバー](lync-server-2013-central-management-store-failover.md)

  - [Lync Server 2013 でのフロントエンド プールのペアリング データのセキュリティ](lync-server-2013-front-end-pool-pairing-data-security.md)

