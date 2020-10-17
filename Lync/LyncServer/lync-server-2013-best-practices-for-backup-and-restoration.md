---
title: 'Lync Server 2013: バックアップと復元のベストプラクティス'
description: 'Lync Server 2013: バックアップと復元のベストプラクティス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e8875f03a7b4445af8274ef059f3abad4d21ff8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552173"
---
# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Lync Server 2013 のバックアップと復元のベストプラクティス

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

このセクションでは、次の 2 種類のベスト プラクティスを説明します。

  - バックアップと復元のベストプラクティス。

  - 障害の影響を最小限に抑えるためのベストプラクティス。

<div>

## <a name="best-practices-for-backup-and-restoration"></a>バックアップと復元のベスト プラクティス

バックアップと復元のプロセスを円滑に行うには、データをバックアップまたは復元するときに、次のベストプラクティスを適用します。

  - 定期的なバックアップを適切な間隔で遂行する。 一番簡単で、特によく使われるバックアップの種類とローテーションのスケジュールは、SQL Server データベース全体を夜間に毎日完全バックアップするというものです。 その後、復元が必要な場合、復元プロセスでは1つのバックアップのみが必要であり、1日あたりのデータが失われることはありません。

  - コマンドレットまたは Lync Server コントロールパネルを使用して構成を変更する場合は、この **コマンドレットを使用して** 、変更を行った後にトポロジ構成ファイル (Xds) のスナップショットバックアップを取得し、データベースを復元する必要がある場合に変更が失われないようにします。 この構成は、XML 形式でバックアップされ、ZIP ファイルとして圧縮されることに注意してください。

  - Lync Server のバックアップに使用する予定の共有フォルダーに、バックアップされたすべてのデータを保持するのに十分なディスク容量があることを確認します。

  - 通常、Lync Server の使用率が低いときにバックアップをスケジュールして、サーバーのパフォーマンスとユーザーの作業を改善します。

  - データをバックアップする場所が安全であることを確認してください (リモートの場所をお勧めします)。

  - データの復元が必要になった場合に備えて、バックアップファイルを保持しておくことができます。

  - 組織でサポートされている復元プロセスの定期的なテストを計画し、スケジュールを設定します。

  - バックアップと復元のプロセスを事前に検証して、意図したとおりに動作することを確認してください。

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>障害の影響を最小限に抑えるベスト プラクティス

重大なサービス中断 (停電や突然のハードウェア障害など) に対処するための最善の戦略は、それらが発生することを前提とし、それに応じて計画することです。

停止と停止を最小限に抑えた Lync services が組織にとってビジネスに不可欠な場合は、「 [Planning for high availability and disaster recovery In Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」で説明されているように、フロントエンドサーバーのペアプールの実装を検討する必要があります。 次に、これらのプールのいずれかに障害がある場合、管理者は、そのプールのユーザーが他のプールによって提供されるように切り替え、ダウンタイムを最小限にすることができます。

バックアップと復元の戦略の一環として開発する障害管理プランには、次のものが含まれます。

  - ソフトウェアメディアとソフトウェアおよびファームウェアの更新をすぐに利用できるようにします。

  - ハードウェアおよびソフトウェアに関する記録を残しておく。

  - データを定期的にバックアップし、バックアップの整合性を監視します。

  - 障害回復のスタッフを訓練し、手順を文書化し、障害回復シミュレーション演習を実施する。

  - 予備ハードウェアの保持、またはサービスレベル契約 (SLA) を使用している場合は、ハードウェアベンダーおよびサプライヤーと契約している場合は、メッセージ交換を行います。

  - トランザクション ログ ファイル (.ldf ファイル) とデータベース ファイル (.mdf ファイル) を別の場所に保存する。

</div>

</div>

<span> </span>

</div>

</div>

</div>

