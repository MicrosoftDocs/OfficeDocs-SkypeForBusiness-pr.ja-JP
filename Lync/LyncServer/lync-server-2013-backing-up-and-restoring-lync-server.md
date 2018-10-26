---
title: Lync Server 2013 のバックアップと復元
TOCTitle: Lync Server 2013 のバックアップと復元
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202160(v=OCS.15)
ms:contentKeyID: 52056531
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のバックアップと復元

 

_**トピックの最終更新日:** 2013-02-21_

このセクションでは、Lync Server 2013 データのバックアップに関するベスト プラクティス、および障害が発生した場合のそのデータの復元に関するベスト プラクティスについて説明します。これらのベスト プラクティスは以下の状況に適用されます。

  - 任意の種類の Lync Server プール全体 (フロント エンド サーバー、エッジ サーバー、仲介サーバー、常設チャット サーバー、または ディレクター) またはこれらのプールの 1 つに含まれる個々のサーバーに障害が発生。

  - 中央管理サーバーに障害が発生。

  - Standard Edition に障害が発生。

  - Enterprise Editionバック エンド サーバーに障害が発生。

  - ファイル ストアに障害が発生。

  - アーカイブ データベース、監視データベース、または常設チャット データベースに障害が発生。

このセクションでは、サイト全体の復元またはスタンバイ サイトの開発に関する情報については説明しません。ペアになったフロント エンド プールを使用する障害復旧ソリューションの開発に関する詳細については、「[Lync Server 2013 での高可用性および障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。障害復旧の計画にはこの方法をお勧めします。

ペアとなったフロント エンド プールを展開しており、そのうちの 1 つのプールが失敗して回復不可能な状態になった場合、新しい完全修飾ドメイン名 (FQDN) を使用し、ペアの相手のプールからこのプールを復元できます。この復旧の実行手順の詳細については、「[Lync Server 2013 でのプールのフェールオーバー](lync-server-2013-failing-over-a-pool.md)」を参照してください。また、後で、フロント エンド ペアの一部であった、失敗して回復不可能となったプールを再作成する場合は、「[ABC フロントエンド プール フェールオーバーを実行する](lync-server-2013-performing-an-abc-front-end-pool-failover.md)」の手順を使用できます。

このドキュメントで説明する方法論には、計画フェーズでの特別な考慮事項が含まれます。詳細については、「[バックアップと復元の計画の策定](lync-server-2013-establishing-a-backup-and-restoration-plan.md)」を参照してください。

## このセクション中

  - [Lync Server のバックアップと復元の準備](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [データと設定のバックアップ](lync-server-2013-backing-up-data-and-settings.md)

  - [データと設定の復元](lync-server-2013-restoring-data-and-settings.md)

  - [バックアップと復元のワークシート](lync-server-2013-backup-and-restoration-worksheets.md)

