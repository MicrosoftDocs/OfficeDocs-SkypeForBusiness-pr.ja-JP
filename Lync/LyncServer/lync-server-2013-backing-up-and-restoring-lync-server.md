---
title: 'Lync Server 2013: Lync Server のバックアップと復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2dd48b7a4357fef2f848210a52313ae334b608b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>Lync Server 2013 のバックアップと復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

このセクションでは、Lync Server 2013 データをバックアップするためのベストプラクティスと、障害が発生した場合に復元するためのベストプラクティスについて説明します。 これらのベストプラクティスは、次の状況に適用されます。

  - すべての種類の Lync Server プール (フロントエンドサーバー、エッジサーバー、仲介サーバー、常設チャットサーバー、またはディレクター)、またはこれらのプールのいずれかの個々のサーバー。

  - 中央管理サーバー

  - Standard Edition サーバー

  - Enterprise Edition バックエンドサーバー

  - ファイルストア

  - アーカイブデータベース、監視データベース、または常設チャットデータベース

このセクションには、サイト全体の復元、またはスタンバイサイトの開発に関する情報は含まれていません。 ペアのフロントエンドプールを使用する障害復旧ソリューションの開発の詳細については、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。 これは、障害復旧の計画に推奨される方法です。

ペアになったフロントエンドプールを展開した場合、これらのプールのいずれかが失敗して回復不能になった場合は、そのプールから新しい完全修飾ドメイン名 (FQDN) を使用して、このプールを復元できます。 この回復を実行する手順の詳細については、「 [Lync Server 2013 でプールをフェールオーバー](lync-server-2013-failing-over-a-pool.md)する」を参照してください。 さらに、フロントエンドペアに含まれていた、障害が発生した回復不能なプールを再作成する必要がある場合は、「 [Lync Server 2013 で ABC フロントエンドプールのフェールオーバーを実行](lync-server-2013-performing-an-abc-front-end-pool-failover.md)する」の手順を使用できます。

このドキュメントで説明する方法論には、計画フェーズでの特別な考慮事項が含まれます。 詳細については、「 [Lync Server 2013 のバックアップと復元の計画](lync-server-2013-establishing-a-backup-and-restoration-plan.md)を立てる」を参照してください。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 のバックアップと復元の準備](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Lync Server 2013 でのデータと設定のバックアップ](lync-server-2013-backing-up-data-and-settings.md)

  - [Lync Server 2013 でのデータと設定の復元](lync-server-2013-restoring-data-and-settings.md)

  - [Lync Server 2013 のバックアップと復元のワークシート](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

