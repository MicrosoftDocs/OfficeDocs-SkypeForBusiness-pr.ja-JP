---
title: 'Lync Server 2013: バックアップと復元のベストプラクティス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc7a926bd8fd5c61f87d5e8252c30f40e5a6a69
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Lync Server 2013 のバックアップと復元に関するベストプラクティス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

このセクションには、2種類のベストプラクティスが用意されています。

  - バックアップと復元に関するベストプラクティス

  - 障害の影響を最小限に抑えるためのベストプラクティス。

<div>

## <a name="best-practices-for-backup-and-restoration"></a>バックアップと復元に関するベストプラクティス

バックアップと復元のプロセスを容易にするために、データをバックアップまたは復元するときに、次のベストプラクティスを適用します。

  - 適切な間隔で定期的にバックアップを実行します。 最も簡単かつ一般的に使用されるバックアップの種類とローテーションスケジュールは、完全な夜間の SQL Server データベースのバックアップです。 復元が必要な場合は、復元プロセスでバックアップを1つだけ行う必要があり、1日分のデータを失うことはありません。

  - コマンドレットまたは Lync Server コントロールパネルを使用して構成を変更する場合は、**エクスポート-csconfiguration**コマンドレットを使用して、変更を行った後にトポロジ構成ファイル (Xds) のスナップショットバックアップを取得し、変更が失われないようにします。データベースを復元する必要があります。 この構成は XML 形式でバックアップされ、ZIP ファイルとして圧縮されていることに注意してください。

  - Lync Server のバックアップに使用する共有フォルダーに、バックアップされたすべてのデータを保持する十分なディスク領域があることを確認します。

  - Lync Server の使用量が少なく、サーバーのパフォーマンスとユーザーエクスペリエンスを向上させるために、バックアップのスケジュールを設定します。

  - データをバックアップする場所がセキュリティで保護されていることを確認します (リモートの場所をお勧めします)。

  - データを復元する必要がある場合に備えて、バックアップファイルを保存しておきます。

  - 組織でサポートされている復元プロセスの定期的なテストを計画してスケジュールします。

  - バックアップと復元のプロセスを事前に検証して、期待どおりに動作することを確認します。

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>障害の影響を最小限に抑えるためのベストプラクティス

重大なサービス中断 (停電や突然のハードウェア障害などの問題が発生したため) を処理するための最善の戦略は、それらが発生することを前提とし、それに応じて計画することです。

中断と停止を最小限に抑えた Lync サービスが組織にとってビジネスにとって重要である場合は、「[高可用性の計画」および「Lync Server の障害回復」で説明されているように、フロントエンドサーバーのペアプールの実装を検討してください。2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。 次に、これらのプールのいずれかに障害がある場合、管理者は、そのプールのユーザーを他のプールによって提供されるように切り替えることができます。これには、最小限のダウンタイムがあります。

バックアップと復元の戦略の一部として開発した障害管理計画には、次のものが含まれている必要があります。

  - ソフトウェアメディアとソフトウェアおよびファームウェアの更新プログラムをすぐに利用できるようにします。

  - ハードウェアとソフトウェアの記録を管理する。

  - データを定期的にバックアップし、バックアップの整合性を監視します。

  - 障害の回復、手順の文書化、障害回復シミュレーションの訓練の実装など、スタッフのトレーニングを行います。

  - 予備のハードウェアを利用できるようにする。または、サービスレベル契約 (SLA) を利用している場合は、ハードウェアベンダーとサプライヤーとの契約を締結して、メッセージを交換してください。

  - トランザクションログファイル (.ldf ファイル) とデータベースファイル (.mdf ファイル) の場所を分離します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

