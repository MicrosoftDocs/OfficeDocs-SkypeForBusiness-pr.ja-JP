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
ms.openlocfilehash: 4c0995c81554073a8d10039f2f95673f013569e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="24e97-102">Lync Server 2013 のバックアップと復元のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="24e97-102">Best practices for backup and restoration for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24e97-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="24e97-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="24e97-104">このセクションでは、次の 2 種類のベスト プラクティスを説明します。</span><span class="sxs-lookup"><span data-stu-id="24e97-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="24e97-105">バックアップと復元のベストプラクティス。</span><span class="sxs-lookup"><span data-stu-id="24e97-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="24e97-106">障害の影響を最小限に抑えるためのベストプラクティス。</span><span class="sxs-lookup"><span data-stu-id="24e97-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="24e97-107">バックアップと復元のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="24e97-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="24e97-108">バックアップと復元のプロセスを円滑に行うには、データをバックアップまたは復元するときに、次のベストプラクティスを適用します。</span><span class="sxs-lookup"><span data-stu-id="24e97-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="24e97-109">定期的なバックアップを適切な間隔で遂行する。</span><span class="sxs-lookup"><span data-stu-id="24e97-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="24e97-110">一番簡単で、特によく使われるバックアップの種類とローテーションのスケジュールは、SQL Server データベース全体を夜間に毎日完全バックアップするというものです。</span><span class="sxs-lookup"><span data-stu-id="24e97-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="24e97-111">その後、復元が必要な場合、復元プロセスでは1つのバックアップのみが必要であり、1日あたりのデータが失われることはありません。</span><span class="sxs-lookup"><span data-stu-id="24e97-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="24e97-112">コマンドレットまたは Lync Server コントロールパネルを使用して構成を変更する場合は、この**コマンドレットを使用して**、変更を行った後にトポロジ構成ファイル (Xds) のスナップショットバックアップを取得し、データベースを復元する必要がある場合に変更が失われないようにします。</span><span class="sxs-lookup"><span data-stu-id="24e97-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="24e97-113">この構成は、XML 形式でバックアップされ、ZIP ファイルとして圧縮されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="24e97-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="24e97-114">Lync Server のバックアップに使用する予定の共有フォルダーに、バックアップされたすべてのデータを保持するのに十分なディスク容量があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24e97-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="24e97-115">通常、Lync Server の使用率が低いときにバックアップをスケジュールして、サーバーのパフォーマンスとユーザーの作業を改善します。</span><span class="sxs-lookup"><span data-stu-id="24e97-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="24e97-116">データをバックアップする場所が安全であることを確認してください (リモートの場所をお勧めします)。</span><span class="sxs-lookup"><span data-stu-id="24e97-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="24e97-117">データの復元が必要になった場合に備えて、バックアップファイルを保持しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="24e97-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="24e97-118">組織でサポートされている復元プロセスの定期的なテストを計画し、スケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="24e97-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="24e97-119">バックアップと復元のプロセスを事前に検証して、意図したとおりに動作することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="24e97-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="24e97-120">障害の影響を最小限に抑えるベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="24e97-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="24e97-121">重大なサービス中断 (停電や突然のハードウェア障害など) に対処するための最善の戦略は、それらが発生することを前提とし、それに応じて計画することです。</span><span class="sxs-lookup"><span data-stu-id="24e97-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="24e97-122">停止と停止を最小限に抑えた Lync services が組織にとってビジネスに不可欠な場合は、「 [Planning for high availability and disaster recovery In Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」で説明されているように、フロントエンドサーバーのペアプールの実装を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24e97-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="24e97-123">次に、これらのプールのいずれかに障害がある場合、管理者は、そのプールのユーザーが他のプールによって提供されるように切り替え、ダウンタイムを最小限にすることができます。</span><span class="sxs-lookup"><span data-stu-id="24e97-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="24e97-124">バックアップと復元の戦略の一環として開発する障害管理プランには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="24e97-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="24e97-125">ソフトウェアメディアとソフトウェアおよびファームウェアの更新をすぐに利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="24e97-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="24e97-126">ハードウェアおよびソフトウェアに関する記録を残しておく。</span><span class="sxs-lookup"><span data-stu-id="24e97-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="24e97-127">データを定期的にバックアップし、バックアップの整合性を監視します。</span><span class="sxs-lookup"><span data-stu-id="24e97-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="24e97-128">障害回復のスタッフを訓練し、手順を文書化し、障害回復シミュレーション演習を実施する。</span><span class="sxs-lookup"><span data-stu-id="24e97-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="24e97-129">予備ハードウェアの保持、またはサービスレベル契約 (SLA) を使用している場合は、ハードウェアベンダーおよびサプライヤーと契約している場合は、メッセージ交換を行います。</span><span class="sxs-lookup"><span data-stu-id="24e97-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="24e97-130">トランザクション ログ ファイル (.ldf ファイル) とデータベース ファイル (.mdf ファイル) を別の場所に保存する。</span><span class="sxs-lookup"><span data-stu-id="24e97-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

