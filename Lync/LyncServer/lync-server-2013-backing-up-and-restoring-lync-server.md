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
ms.openlocfilehash: 43a96f47bfe9d28fdbc37eea0ae62ef6cd763098
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>Lync Server 2013 のバックアップと復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

このセクションでは、Lync Server 2013 データをバックアップするためのベストプラクティスと、エラーが発生した場合に復元するためのベストプラクティスについて説明します。 このベストプラクティスは、次のような場合に適用されます。

  - 任意の種類の Lync Server プール全体 (フロントエンドサーバー、エッジサーバー、仲介サーバー、常設チャットサーバー、またはディレクター)、またはこれらのいずれかのプールの個々のサーバー。

  - 中央管理サーバー

  - Standard Edition サーバー

  - Enterprise Edition バックエンドサーバー

  - ファイルストア

  - アーカイブデータベース、監視データベース、または常設チャットデータベース

このセクションには、サイト全体の復元、またはスタンバイサイトの開発に関する情報は含まれていません。 ペアリングされたフロントエンドプールでの障害回復ソリューションの開発について詳しくは、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」をご覧ください。 これは、障害回復を計画するための推奨される方法です。

ペアリングされたフロントエンドプールを展開している場合、これらのプールのいずれかが失敗して回復不能になった場合は、そのペアのプールから新しい完全修飾ドメイン名 (FQDN) を使用して、このプールを復元することができます。 この回復を実行する手順の詳細については、「 [Lync Server 2013 でのプールのフェールオーバー](lync-server-2013-failing-over-a-pool.md)」を参照してください。 さらに、フロントエンドペアの一部であった失敗した回復可能なプールを後で再作成する必要がある場合は、「 [Lync Server 2013 で ABC フロントエンドプールフェールオーバーを実行](lync-server-2013-performing-an-abc-front-end-pool-failover.md)する」の手順を使用できます。

このドキュメントで説明する方法には、計画フェーズでの特別な考慮事項が含まれます。 詳細については、「 [Lync Server 2013 のバックアップと復元計画を立てる](lync-server-2013-establishing-a-backup-and-restoration-plan.md)」を参照してください。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 のバックアップと復元の準備](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Lync Server 2013 でのデータと設定のバックアップ](lync-server-2013-backing-up-data-and-settings.md)

  - [Lync Server 2013 でのデータと設定の復元](lync-server-2013-restoring-data-and-settings.md)

  - [Lync Server 2013 のバックアップと復元ワークシート](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

