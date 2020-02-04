---
title: 'Lync Server 2013: バックアップと復元のベストプラクティス'
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
ms.openlocfilehash: e51f846d92f5d8cfecbbface31df6543c5c9ac23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="ebcc8-102">Lync Server 2013 のバックアップと復元に関するベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="ebcc8-102">Best practices for backup and restoration for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebcc8-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ebcc8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ebcc8-104">このセクションには、2種類のベストプラクティスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="ebcc8-105">バックアップと復元に関するベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="ebcc8-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="ebcc8-106">障害の影響を最小限に抑えるためのベストプラクティス。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="ebcc8-107">バックアップと復元に関するベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="ebcc8-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="ebcc8-108">バックアップと復元のプロセスを容易にするために、データをバックアップまたは復元するときに、次のベストプラクティスを適用します。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="ebcc8-109">適切な間隔で定期的にバックアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="ebcc8-110">最も簡単かつ一般的に使用されるバックアップの種類とローテーションスケジュールは、完全な夜間の SQL Server データベースのバックアップです。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="ebcc8-111">復元が必要な場合は、復元プロセスでバックアップを1つだけ行う必要があり、1日分のデータを失うことはありません。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="ebcc8-112">コマンドレットまたは Lync Server コントロールパネルを使用して構成を変更する場合は、**エクスポート-csconfiguration**コマンドレットを使用して、変更を行った後にトポロジ構成ファイル (Xds) のスナップショットバックアップを取得します。これにより、データベースを復元する必要がある場合に変更が失われることはありません。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="ebcc8-113">この構成は XML 形式でバックアップされ、ZIP ファイルとして圧縮されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="ebcc8-114">Lync Server のバックアップに使用する共有フォルダーに、バックアップされたすべてのデータを保持する十分なディスク領域があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="ebcc8-115">Lync Server の使用量が少なく、サーバーのパフォーマンスとユーザーエクスペリエンスを向上させるために、バックアップのスケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="ebcc8-116">データをバックアップする場所がセキュリティで保護されていることを確認します (リモートの場所をお勧めします)。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="ebcc8-117">データを復元する必要がある場合に備えて、バックアップファイルを保存しておきます。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="ebcc8-118">組織でサポートされている復元プロセスの定期的なテストを計画してスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="ebcc8-119">バックアップと復元のプロセスを事前に検証して、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="ebcc8-120">障害の影響を最小限に抑えるためのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="ebcc8-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="ebcc8-121">重大なサービス中断 (停電や突然のハードウェア障害などの問題が発生したため) を処理するための最善の戦略は、それらが発生することを前提とし、それに応じて計画することです。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="ebcc8-122">中断と停止を最小限に抑えた Lync サービスが組織にとってビジネスにとって重要な場合は、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」で説明されているように、フロントエンドサーバーのペアプールの実装を検討してください。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="ebcc8-123">次に、これらのプールのいずれかに障害がある場合、管理者は、そのプールのユーザーを他のプールによって提供されるように切り替えることができます。これには、最小限のダウンタイムがあります。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="ebcc8-124">バックアップと復元の戦略の一部として開発した障害管理計画には、次のものが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="ebcc8-125">ソフトウェアメディアとソフトウェアおよびファームウェアの更新プログラムをすぐに利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="ebcc8-126">ハードウェアとソフトウェアの記録を管理する。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="ebcc8-127">データを定期的にバックアップし、バックアップの整合性を監視します。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="ebcc8-128">障害の回復、手順の文書化、障害回復シミュレーションの訓練の実装など、スタッフのトレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="ebcc8-129">予備のハードウェアを利用できるようにする。または、サービスレベル契約 (SLA) を利用している場合は、ハードウェアベンダーとサプライヤーとの契約を締結して、メッセージを交換してください。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="ebcc8-130">トランザクションログファイル (.ldf ファイル) とデータベースファイル (.mdf ファイル) の場所を分離します。</span><span class="sxs-lookup"><span data-stu-id="ebcc8-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

