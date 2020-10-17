---
title: 'Lync Server 2013: 毎週のタスク'
description: 'Lync Server 2013: 毎週のタスク。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d818e1140141a470bb57a1471bb04931f505a6bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546143"
---
# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="c0a88-103">Lync Server 2013 の週次タスク</span><span class="sxs-lookup"><span data-stu-id="c0a88-103">Weekly tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0a88-104">_**トピックの最終更新日:** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="c0a88-104">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="c0a88-105">週単位のタスクは、通常、ログとレポートの収集と分析に関連しています。</span><span class="sxs-lookup"><span data-stu-id="c0a88-105">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="c0a88-106">アーカイブイベントログ</span><span class="sxs-lookup"><span data-stu-id="c0a88-106">Archive event logs</span></span>

<span data-ttu-id="c0a88-107">イベントログが必要に応じてイベントを上書きするように構成されていない場合は、定期的にアーカイブして削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a88-107">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="c0a88-108">このアクションはセキュリティログにとって特に重要です。これは、試行されたセキュリティ侵害を調査する際に必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c0a88-108">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="c0a88-109">組織では、ログアーカイブのポリシーと手順を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a88-109">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="c0a88-110">レポートの作成</span><span class="sxs-lookup"><span data-stu-id="c0a88-110">Create reports</span></span>

<span data-ttu-id="c0a88-111">キャパシティ計画、SLA レビュー、およびパフォーマンス分析に役立つ進捗レポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-111">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="c0a88-112">イベントログとシステムモニターの毎日のデータを使用して、ディスク、メモリ、CPU の使用状況に関するレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-112">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="c0a88-113">System Center Operations Manager を使用して、稼働時間および可用性レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-113">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="c0a88-114">組織では、進捗レポートのポリシーと手順を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a88-114">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="c0a88-115">インシデント レポート</span><span class="sxs-lookup"><span data-stu-id="c0a88-115">Incident reports</span></span>

<span data-ttu-id="c0a88-116">Lync Server に関連する組織のインシデントレポートの監査を毎週実行します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-116">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="c0a88-117">この監査には、次のものを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a88-117">This audit should include the following:</span></span>

  - <span data-ttu-id="c0a88-118">上位で生成、解決、および保留中のインシデント。</span><span class="sxs-lookup"><span data-stu-id="c0a88-118">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="c0a88-119">解決できないインシデントの解決策。</span><span class="sxs-lookup"><span data-stu-id="c0a88-119">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="c0a88-120">新しいトラブルチケットを含めるようにレポートを更新します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-120">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="c0a88-121">トラブルシューティングガイドのドキュメントリポジトリの更新と、停止に関する mortems の投稿。</span><span class="sxs-lookup"><span data-stu-id="c0a88-121">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="c0a88-122">組織のインシデント追跡システムは Lync Server に依存しない選択であるため、特定の手順またはポイントは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c0a88-122">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="c0a88-123">組織が選択したシステムのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0a88-123">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="c0a88-124">IIS のログとパフォーマンスを確認する</span><span class="sxs-lookup"><span data-stu-id="c0a88-124">Check IIS logs and performance</span></span>

<span data-ttu-id="c0a88-125">インターネットインフォメーションサービス (IIS) のログとパフォーマンスの週次の確認を行います。</span><span class="sxs-lookup"><span data-stu-id="c0a88-125">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="c0a88-126">IIS のログとパフォーマンスを監視する方法の詳細については、「 [Windows Server 2003 インターネットインフォメーションサービス (iis) のイベントログの概要](https://go.microsoft.com/fwlink/?linkid=36077)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0a88-126">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](https://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="c0a88-127">レビューには次のものが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a88-127">The review should include the following:</span></span>

  - <span data-ttu-id="c0a88-128">WWW サービスキャッシュを監視するための Web サービスキャッシュカウンター。</span><span class="sxs-lookup"><span data-stu-id="c0a88-128">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="c0a88-129">Asp として実行されるアプリケーションを監視するための Active Server Pages (Asp) カウンター。</span><span class="sxs-lookup"><span data-stu-id="c0a88-129">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="c0a88-130">データベースレポートを生成する</span><span class="sxs-lookup"><span data-stu-id="c0a88-130">Generate database reports</span></span>

<span data-ttu-id="c0a88-131">**SQL データベースでレポートを生成するには**</span><span class="sxs-lookup"><span data-stu-id="c0a88-131">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="c0a88-132">Lync Server 2013 を開きます。</span><span class="sxs-lookup"><span data-stu-id="c0a88-132">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="c0a88-133">コンソールツリーで、[フォレスト] ノードを展開し、[ **エンタープライズプール**] を展開して、データベースレポートを生成するプールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0a88-133">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="c0a88-134">詳細ウィンドウで、[ **データベース** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0a88-134">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="c0a88-135">[ **データベース** ] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c0a88-135">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="c0a88-136">データベースの名前を表示するには、 **[全般設定**] を展開し、データベース名を表示します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-136">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="c0a88-137">プールの現在のユーザーサマリー統計情報を取得するには、[ **ユーザー概要レポート**] を展開し、[ **移動**] をクリックして結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-137">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="c0a88-138">プールの1人のユーザーについて現在のユーザーごとのデータを取得するには、[ **ユーザーごとのレポート**] を展開し、ユーザーの SIP URI を入力して [ **移動**] をクリックし、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-138">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="c0a88-139">プールの現在の電話会議の概要統計情報を取得するには、[ **電話会議の概要レポート**] を展開し、[ **移動**] をクリックして結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-139">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="c0a88-140">セキュリティと Lync Server の更新プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="c0a88-140">Check for security and Lync Server updates</span></span>

<span data-ttu-id="c0a88-141">新しいサービスパック、修正プログラム、または更新プログラムを特定します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-141">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="c0a88-142">該当する場合は、テストラボでテストし、変更管理の手順を使用して運用サーバーへの展開を手配します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-142">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="c0a88-143">また、Lync Server コンポーネントの更新プログラムを Windows update の一部として利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c0a88-143">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="c0a88-144">すべての Lync Server コンポーネントの更新プログラムは、更新プログラムが適用可能な Lync Server を実行しているすべてのサーバー上で同時に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a88-144">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="c0a88-145">Lync Server 2013 ベストプラクティスアナライザーを実行する</span><span class="sxs-lookup"><span data-stu-id="c0a88-145">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="c0a88-146">Lync Server 2013 ベストプラクティスアナライザーツールは、構成情報を収集し、構成が Microsoft のベストプラクティスに従って設定されているかどうかを判断する診断ツールです。</span><span class="sxs-lookup"><span data-stu-id="c0a88-146">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="c0a88-147">このツールの詳細については、「 [Lync Server 2013 ベストプラクティスアナライザー](lync-server-2013-lync-server-best-practices-analyzer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0a88-147">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="c0a88-148">このツールは、Lync Server の事前に定義されたルールのセットと展開の構成データを比較し、潜在的な問題を報告します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-148">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="c0a88-149">報告されるすべての問題について、このツールは Lync Server 環境での現在の構成と推奨構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-149">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="c0a88-150">適切なネットワークアクセスにより、ツールは、次の作業を実行するために、AD DS と Lync Server 2013 を実行しているサーバーを調査することができます。</span><span class="sxs-lookup"><span data-stu-id="c0a88-150">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="c0a88-151">推奨ベストプラクティスに従って構成が設定されていることを確認して、正常性チェックを積極的に実行する</span><span class="sxs-lookup"><span data-stu-id="c0a88-151">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="c0a88-152">最適でない構成設定、サポートされていない、推奨されないオプションなど、問題の一覧を生成する</span><span class="sxs-lookup"><span data-stu-id="c0a88-152">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="c0a88-153">システムの全般的な状態を判断する</span><span class="sxs-lookup"><span data-stu-id="c0a88-153">Judge the general health of a system</span></span>

  - <span data-ttu-id="c0a88-154">特定の問題のトラブルシューティングに役立つ情報</span><span class="sxs-lookup"><span data-stu-id="c0a88-154">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="c0a88-155">更新プログラムが入手可能な場合にダウンロードするように求めるメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="c0a88-155">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="c0a88-156">報告される問題に関するオンラインおよびローカルのドキュメントを提供し、トラブルシューティングのヒントを含める</span><span class="sxs-lookup"><span data-stu-id="c0a88-156">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="c0a88-157">後で確認するためにキャプチャできる構成情報を生成する</span><span class="sxs-lookup"><span data-stu-id="c0a88-157">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="c0a88-158">すべての Lync Server 2013 サーバーに RTCBPA.msi がインストールされていることを確認し、1週間正常性チェックレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-158">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="c0a88-159">結果を確認し、必要に応じて修正します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-159">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="c0a88-160">SLA パフォーマンスの図を確認する</span><span class="sxs-lookup"><span data-stu-id="c0a88-160">Review SLA performance figures</span></span>

<span data-ttu-id="c0a88-161">前の週の主要なパフォーマンスデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-161">Check the key performance data for the previous week.</span></span> <span data-ttu-id="c0a88-162">SLA の要件に照らしてパフォーマンスを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-162">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="c0a88-163">目標を満たしていない傾向とアイテムを識別します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-163">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="c0a88-164">System Center Operations Manager 管理パックと qoe (quality of experience) レポートを確認する</span><span class="sxs-lookup"><span data-stu-id="c0a88-164">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="c0a88-165">Lync Server 2013 管理パックと品質の実績レポートを入手して確認します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-165">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="c0a88-166">エンタープライズプールのデータベースレポートの生成と表示</span><span class="sxs-lookup"><span data-stu-id="c0a88-166">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="c0a88-167">**プールレポートを生成するには**</span><span class="sxs-lookup"><span data-stu-id="c0a88-167">**To generate pool reports**</span></span>

1.  <span data-ttu-id="c0a88-168">Lync Server 2013 を開きます。</span><span class="sxs-lookup"><span data-stu-id="c0a88-168">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="c0a88-169">コンソールツリーで、[フォレスト] ノードを展開し、[ **エンタープライズプール**] を展開して、データベースレポートを生成するプールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0a88-169">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="c0a88-170">詳細ウィンドウで、[ **データベース** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0a88-170">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="c0a88-171">[ **データベース** ] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c0a88-171">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="c0a88-172">データベースの名前を表示するには、 **[全般設定**] を展開し、データベース名を表示します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-172">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="c0a88-173">プールの現在のユーザーサマリー統計情報を取得するには、[ **ユーザー概要レポート**] を展開し、[ **移動**] をクリックして結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-173">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="c0a88-174">プールの1人のユーザーについて現在のユーザーごとのデータを取得するには、[ **ユーザーごとのレポート**] を展開し、ユーザーの SIP URI を入力して [ **移動**] をクリックし、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-174">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="c0a88-175">プールの現在の電話会議の概要統計情報を取得するには、[ **電話会議の概要レポート**] を展開し、[ **移動**] をクリックして結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-175">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="c0a88-176">エンタープライズプールごとに、管理者は [ **データベース** ] タブを使用してデータベース名を表示し、データベースからレポートを取得して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c0a88-176">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="c0a88-177">データベースレポートと説明</span><span class="sxs-lookup"><span data-stu-id="c0a88-177">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0a88-178">Section</span><span class="sxs-lookup"><span data-stu-id="c0a88-178">Section</span></span></th>
<th><span data-ttu-id="c0a88-179">説明</span><span class="sxs-lookup"><span data-stu-id="c0a88-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0a88-180">ユーザー概要レポート</span><span class="sxs-lookup"><span data-stu-id="c0a88-180">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="c0a88-181">Dbanalyze/v/report: diag [/sqlserver: value]</span><span class="sxs-lookup"><span data-stu-id="c0a88-181">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="c0a88-182">このセクションには、有効になっているユーザー数、ユーザーあたりの連絡先の平均数、特定の機能のユーザー数など、プール内のユーザーに関する集計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0a88-182">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="c0a88-183">これらのレポートを使用する場合、次の情報が役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="c0a88-183">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="c0a88-184">有効なユーザーとは、[Active Directory ユーザーとコンピューター] スナップインを使用して Lync Server 2013 が有効になっているユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="c0a88-184">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="c0a88-185">アクティブなユーザーとは、ログオンまたは登録したユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="c0a88-185">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="c0a88-186">要約レポートでは、連絡先に関する統計情報のセットも提供されます。</span><span class="sxs-lookup"><span data-stu-id="c0a88-186">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="c0a88-187">これらの統計情報は、少なくとも1回ログオンしていて、少なくとも1人の連絡先を持つユーザーの作成に対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="c0a88-187">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="c0a88-188">そのため、通常、少なくとも0の連絡先が表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c0a88-188">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="c0a88-189">この動作により、ユーザーが連絡先を持たない (ただし、ユーザーが登録されている) 場合は、次のように表示されることがあります。 &lt; 統計フィールドには empty があります &gt; 。</span><span class="sxs-lookup"><span data-stu-id="c0a88-189">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0a88-190">Per-User レポート</span><span class="sxs-lookup"><span data-stu-id="c0a88-190">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="c0a88-191">Dbanalyze/v/report: disk [/sqlserver: value]</span><span class="sxs-lookup"><span data-stu-id="c0a88-191">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="c0a88-192">ユーザーの作成に関して計算される概要レポートとは異なり、これらは特定のユーザーに関するレポートです。</span><span class="sxs-lookup"><span data-stu-id="c0a88-192">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0a88-193">電話会議の概要レポート</span><span class="sxs-lookup"><span data-stu-id="c0a88-193">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="c0a88-194">Dbanalyze/v/report: conf [/sqlserver: value]</span><span class="sxs-lookup"><span data-stu-id="c0a88-194">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="c0a88-195">このセクションには、アクティブな会議数や参加者の総数など、プールの会議の概要統計情報に関する集計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0a88-195">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="c0a88-196">帯域幅使用率アナライザーの実行</span><span class="sxs-lookup"><span data-stu-id="c0a88-196">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="c0a88-197">帯域幅使用率アナライザーは、エンタープライズネットワーク内の WAN リンク全体にわたる UC エンドポイントによる帯域幅消費量のさまざまな表示に関するレポートを作成するツールです。</span><span class="sxs-lookup"><span data-stu-id="c0a88-197">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="c0a88-198">これらのレポートを使用して、現在の帯域幅の使用パターンを理解し、帯域幅の容量計画に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="c0a88-198">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="c0a88-199">また、さまざまなリンクに割り当てられている帯域幅容量を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-199">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="c0a88-200">このツールは、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="c0a88-200">This tool does the following:</span></span>

  - <span data-ttu-id="c0a88-201">ネットワーク経由で音声使用率に関する特定のレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-201">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="c0a88-202">さまざまなリンクに割り当てられている帯域幅容量に対して、さらに効果的な容量計画と反復処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c0a88-202">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="c0a88-203">帯域幅使用率アナライザーは、帯域幅容量と使用状況レポートをグラフィカルにプロットすることができます。</span><span class="sxs-lookup"><span data-stu-id="c0a88-203">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="c0a88-204">それらを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c0a88-204">They are as follows:</span></span>

  - <span data-ttu-id="c0a88-205">エンタープライズネットワーク内のすべての WAN リンク</span><span class="sxs-lookup"><span data-stu-id="c0a88-205">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="c0a88-206">選択された WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="c0a88-206">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="c0a88-207">リンク容量を超過した WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="c0a88-207">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="c0a88-208">プロビジョニングされた帯域幅を使用している WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="c0a88-208">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="c0a88-209">重大レベルに達していた WAN リンクでフィルター処理します (WAN リンクの帯域幅容量の90% を超える帯域幅使用法)</span><span class="sxs-lookup"><span data-stu-id="c0a88-209">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="c0a88-210">WAN リンクの種類別にフィルター処理—ネットワークサイトリンク、地域間リンク、サイト内のリンク</span><span class="sxs-lookup"><span data-stu-id="c0a88-210">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="c0a88-211">ネットワーク地域でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="c0a88-211">Filtered by network region</span></span>

<span data-ttu-id="c0a88-212">このツールのドキュメントは、 [Lync Server 2013 リソースキットツールのドキュメント](https://go.microsoft.com/fwlink/?linkid=623245)から入手できます。</span><span class="sxs-lookup"><span data-stu-id="c0a88-212">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](https://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c0a88-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0a88-213">See Also</span></span>


[<span data-ttu-id="c0a88-214">毎週のタスクチェックリスト</span><span class="sxs-lookup"><span data-stu-id="c0a88-214">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

