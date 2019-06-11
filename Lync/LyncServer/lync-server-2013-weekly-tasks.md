---
title: 'Lync Server 2013: 週次タスク'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3128780c456c3f38f306d31f258ce903eb50a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="d94b2-102">Lync Server 2013 での週次タスク</span><span class="sxs-lookup"><span data-stu-id="d94b2-102">Weekly tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d94b2-103">_**最終更新日:** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="d94b2-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="d94b2-104">週単位のタスクは、通常、ログとレポートの収集と分析に関連しています。</span><span class="sxs-lookup"><span data-stu-id="d94b2-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="d94b2-105">アーカイブイベントログ</span><span class="sxs-lookup"><span data-stu-id="d94b2-105">Archive event logs</span></span>

<span data-ttu-id="d94b2-106">イベントログが、必要に応じてイベントを上書きするように構成されていない場合は、定期的にアーカイブして削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d94b2-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="d94b2-107">この操作は、セキュリティログについて特に重要です。これは、試行されたセキュリティ違反を調査するときに必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d94b2-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="d94b2-108">組織では、ログアーカイブのポリシーと手順を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d94b2-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="d94b2-109">レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="d94b2-109">Create reports</span></span>

<span data-ttu-id="d94b2-110">キャパシティ計画、SLA レビュー、パフォーマンス分析に役立つ進捗レポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="d94b2-111">イベントログとシステムモニターから毎日のデータを使って、ディスク、メモリ、CPU の使用状況に関するレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="d94b2-112">System Center Operations Manager を使用して、稼働時間と可用性のレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="d94b2-113">組織では、進捗レポートのポリシーと手順を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d94b2-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="d94b2-114">インシデントレポート</span><span class="sxs-lookup"><span data-stu-id="d94b2-114">Incident reports</span></span>

<span data-ttu-id="d94b2-115">Lync Server に関連する組織のインシデントレポートを毎週監査します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="d94b2-116">この監査には、次の情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d94b2-116">This audit should include the following:</span></span>

  - <span data-ttu-id="d94b2-117">上位の生成、解決、保留中のインシデント。</span><span class="sxs-lookup"><span data-stu-id="d94b2-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="d94b2-118">未解決の問題に対する解決策。</span><span class="sxs-lookup"><span data-stu-id="d94b2-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="d94b2-119">新しいトラブルチケットを含めるようにレポートを更新する。</span><span class="sxs-lookup"><span data-stu-id="d94b2-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="d94b2-120">トラブルシューティングガイドのドキュメントリポジトリを更新し、停止に関する事後を投稿します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="d94b2-121">組織のインシデント追跡システムは、Lync Server に依存しない選択であるため、具体的な手順やポインターは利用できません。</span><span class="sxs-lookup"><span data-stu-id="d94b2-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="d94b2-122">組織が選んだシステムのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d94b2-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="d94b2-123">IIS のログとパフォーマンスを確認する</span><span class="sxs-lookup"><span data-stu-id="d94b2-123">Check IIS logs and performance</span></span>

<span data-ttu-id="d94b2-124">インターネットインフォメーションサービス (IIS) のログとパフォーマンスの毎週のレビューを実行します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="d94b2-125">IIS のログとパフォーマンスを監視する方法の詳細については、「 [Windows Server 2003 インターネットインフォメーションサービス (IIS) イベントログの概要](http://go.microsoft.com/fwlink/?linkid=36077)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d94b2-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](http://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="d94b2-126">レビューには、次の内容が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d94b2-126">The review should include the following:</span></span>

  - <span data-ttu-id="d94b2-127">WWW サービスキャッシュを監視するための Web サービスキャッシュカウンター。</span><span class="sxs-lookup"><span data-stu-id="d94b2-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="d94b2-128">Asp として実行されるアプリケーションを監視するための Active Server Pages (Asp) カウンター。</span><span class="sxs-lookup"><span data-stu-id="d94b2-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="d94b2-129">データベースレポートを生成する</span><span class="sxs-lookup"><span data-stu-id="d94b2-129">Generate database reports</span></span>

<span data-ttu-id="d94b2-130">**SQL データベースでレポートを生成するには**</span><span class="sxs-lookup"><span data-stu-id="d94b2-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="d94b2-131">Lync Server 2013 を開きます。</span><span class="sxs-lookup"><span data-stu-id="d94b2-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="d94b2-132">コンソールツリーで、[フォレスト] ノードを展開し、[**エンタープライズプール**] を展開して、データベースレポートを生成するプールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d94b2-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="d94b2-133">詳細ウィンドウで、[**データベース**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d94b2-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="d94b2-134">[**データベース**] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d94b2-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="d94b2-135">データベースの名前を表示するには、 **[全般設定**] を展開し、データベース名を表示します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="d94b2-136">プールの現在のユーザー概要の統計情報を取得するには、[**ユーザーの概要レポート**] を展開し、[**移動**] をクリックして結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="d94b2-137">プールの1人のユーザーに対して現在のユーザーごとのデータを取得するには、[**ユーザーごとのレポート**] を展開し、ユーザーの SIP URI を入力し、[**検索**] をクリックして結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="d94b2-138">プールの現在の会議の概要の統計情報を取得するには、[**会議のサマリーレポート**] を展開し、[**検索**] をクリックして結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="d94b2-139">セキュリティと Lync Server の更新プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="d94b2-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="d94b2-140">新しいサービスパック、修正プログラム、更新プログラムを特定します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="d94b2-141">必要に応じて、テストラボでそれらをテストし、変更制御の手順を使用して運用サーバーへの展開を配置します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="d94b2-142">また、Windows update の一部として Lync Server コンポーネントの更新プログラムを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d94b2-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="d94b2-143">すべての Lync Server コンポーネント更新プログラムは、更新プログラムを適用できる Lync Server を実行しているすべてのサーバーで同時に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d94b2-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="d94b2-144">Lync Server 2013 ベストプラクティスアナライザーを実行する</span><span class="sxs-lookup"><span data-stu-id="d94b2-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="d94b2-145">Lync Server 2013 ベストプラクティスアナライザーツールは、構成情報を収集し、Microsoft のベストプラクティスに従って構成が設定されているかどうかを判断する診断ツールです。</span><span class="sxs-lookup"><span data-stu-id="d94b2-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="d94b2-146">このツールのドキュメントは、 [Lync Server 2013 ベストプラクティスアナライザー](lync-server-2013-lync-server-best-practices-analyzer.md)にあります。</span><span class="sxs-lookup"><span data-stu-id="d94b2-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="d94b2-147">このツールは、展開の構成データを、Lync Server 用に定義済みのルールのセットと比較し、潜在的な問題を報告します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="d94b2-148">報告されるすべての問題について、ツールは Lync Server 環境で現在の構成を提供し、推奨される構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="d94b2-149">このツールでは、適切なネットワークアクセスを利用して、AD DS と Lync Server 2013 を実行しているサーバーで次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d94b2-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="d94b2-150">事前に正常性チェックを実行し、推奨されるベストプラクティスに従って構成が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="d94b2-151">最適な構成の設定やサポートされていない、または推奨されないオプションなどの問題のリストを生成する</span><span class="sxs-lookup"><span data-stu-id="d94b2-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="d94b2-152">システムの全般的な正常性を判断する</span><span class="sxs-lookup"><span data-stu-id="d94b2-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="d94b2-153">特定の問題のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="d94b2-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="d94b2-154">利用可能な場合に更新プログラムをダウンロードするかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="d94b2-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="d94b2-155">報告された問題についてのオンラインおよびローカルなドキュメントを提供し、トラブルシューティングのヒントを含める</span><span class="sxs-lookup"><span data-stu-id="d94b2-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="d94b2-156">後で確認するためにキャプチャできる構成情報を生成する</span><span class="sxs-lookup"><span data-stu-id="d94b2-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="d94b2-157">すべての Lync Server 2013 サーバーに RTCBPA .msi がインストールされていることを確認し、週間正常性チェックレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="d94b2-158">必要に応じて、結果と正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="d94b2-159">SLA のパフォーマンスの指標を確認する</span><span class="sxs-lookup"><span data-stu-id="d94b2-159">Review SLA performance figures</span></span>

<span data-ttu-id="d94b2-160">前週の主要業績データを確認します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="d94b2-161">SLA の要件に対してパフォーマンスを確認します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="d94b2-162">目標を満たしていない傾向と項目を特定します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="d94b2-163">System Center Operations Manager 管理パックとエクスペリエンスの品質レポートを確認する</span><span class="sxs-lookup"><span data-stu-id="d94b2-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="d94b2-164">Lync Server 2013 管理パックおよび品質経験レポートを入手して確認します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="d94b2-165">エンタープライズプールのデータベースレポートを生成して表示する</span><span class="sxs-lookup"><span data-stu-id="d94b2-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="d94b2-166">**プールレポートを生成するには**</span><span class="sxs-lookup"><span data-stu-id="d94b2-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="d94b2-167">Lync Server 2013 を開きます。</span><span class="sxs-lookup"><span data-stu-id="d94b2-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="d94b2-168">コンソールツリーで、[フォレスト] ノードを展開し、[**エンタープライズプール**] を展開して、データベースレポートを生成するプールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d94b2-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="d94b2-169">詳細ウィンドウで、[**データベース**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d94b2-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="d94b2-170">[**データベース**] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d94b2-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="d94b2-171">データベースの名前を表示するには、 **[全般設定**] を展開し、データベース名を表示します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="d94b2-172">プールの現在のユーザー概要の統計情報を取得するには、[**ユーザーの概要レポート**] を展開し、[**移動**] をクリックして結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="d94b2-173">プールの1人のユーザーに対して現在のユーザーごとのデータを取得するには、[**ユーザーごとのレポート**] を展開し、ユーザーの SIP URI を入力し、[**検索**] をクリックして結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="d94b2-174">プールの現在の会議の概要の統計情報を取得するには、[**会議のサマリーレポート**] を展開し、[**検索**] をクリックして結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="d94b2-175">各エンタープライズプールでは、管理者は [**データベース**] タブを使ってデータベース名を表示し、データベースからレポートを取得して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d94b2-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="d94b2-176">データベースのレポートと説明</span><span class="sxs-lookup"><span data-stu-id="d94b2-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d94b2-177">セクション</span><span class="sxs-lookup"><span data-stu-id="d94b2-177">Section</span></span></th>
<th><span data-ttu-id="d94b2-178">説明</span><span class="sxs-lookup"><span data-stu-id="d94b2-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d94b2-179">ユーザーの概要レポート</span><span class="sxs-lookup"><span data-stu-id="d94b2-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="d94b2-180">Dbanalyze/v/report: diag [/sqlserver: value]</span><span class="sxs-lookup"><span data-stu-id="d94b2-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="d94b2-181">このセクションには、有効になっているユーザーの数、ユーザーあたりの連絡先の平均数、特定の機能のユーザー数など、プール内のユーザーに関する集計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d94b2-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="d94b2-182">これらのレポートを使用すると、次の情報が役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="d94b2-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="d94b2-183">有効なユーザーとは、[Active Directory ユーザーとコンピューター] スナップインを使用して、Lync Server 2013 用に有効になっているユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="d94b2-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="d94b2-184">アクティブなユーザーとは、ログオンまたは登録されているユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="d94b2-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="d94b2-185">概要レポートには、連絡先に関する統計情報のセットも用意されています。</span><span class="sxs-lookup"><span data-stu-id="d94b2-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="d94b2-186">これらの統計情報は、少なくとも1回ログオンしていて、少なくとも1人の連絡先を持っているユーザーの人口に対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="d94b2-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="d94b2-187">その結果、少なくとも0個の連絡先が表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d94b2-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="d94b2-188">この動作により、ユーザーが連絡先を持っていない場合 (ユーザーが登録されている場合) は、次の&lt;よう&gt;に表示されることがあります。一部の統計情報フィールドでは空です。</span><span class="sxs-lookup"><span data-stu-id="d94b2-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d94b2-189">ユーザーごとのレポート</span><span class="sxs-lookup"><span data-stu-id="d94b2-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="d94b2-190">Dbanalyze/v/report: disk [/sqlserver: value]</span><span class="sxs-lookup"><span data-stu-id="d94b2-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="d94b2-191">ユーザー人口を通じて計算されるサマリーレポートとは異なり、これらは特定のユーザーに関するレポートです。</span><span class="sxs-lookup"><span data-stu-id="d94b2-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d94b2-192">会議の概要レポート</span><span class="sxs-lookup"><span data-stu-id="d94b2-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="d94b2-193">Dbanalyze/v/report: conf [/sqlserver: value]</span><span class="sxs-lookup"><span data-stu-id="d94b2-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="d94b2-194">このセクションには、アクティブな会議の数、参加者の合計数など、プールの会議の概要の統計情報の集計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d94b2-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="d94b2-195">帯域幅使用率アナライザーの実行</span><span class="sxs-lookup"><span data-stu-id="d94b2-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="d94b2-196">Bandwidth Utilization Analyzer は、エンタープライズ ネットワークの WAN リンク全体の UC エンドポイントで消費される帯域幅を、さまざまな観点から確認できるレポートを作成するツールです。</span><span class="sxs-lookup"><span data-stu-id="d94b2-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="d94b2-197">これらのレポートを使用して、現在の帯域幅消費パターンを把握し、帯域幅のキャパシティ計画を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d94b2-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="d94b2-198">また、さまざまなリンクに割り当てられた帯域幅容量を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="d94b2-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="d94b2-199">このツールでは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d94b2-199">This tool does the following:</span></span>

  - <span data-ttu-id="d94b2-200">ネットワーク経由のオーディオ使用に関する特定のレポートを生成します</span><span class="sxs-lookup"><span data-stu-id="d94b2-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="d94b2-201">より効果的な容量計画の立案と、さまざまなリンクに割り当てられた帯域幅容量の反復処理をサポートする</span><span class="sxs-lookup"><span data-stu-id="d94b2-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="d94b2-202">帯域幅使用率のアナライザーは、帯域幅の容量と使用状況レポートのグラフィカルプロットを生成できます。</span><span class="sxs-lookup"><span data-stu-id="d94b2-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="d94b2-203">これらは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d94b2-203">They are as follows:</span></span>

  - <span data-ttu-id="d94b2-204">エンタープライズ ネットワーク内のすべての WAN リンク</span><span class="sxs-lookup"><span data-stu-id="d94b2-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="d94b2-205">選択された WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="d94b2-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="d94b2-206">リンク容量を超過した WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="d94b2-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="d94b2-207">プロビジョニングされた帯域幅を使用していた WAN リンクでフィルター処理された場合</span><span class="sxs-lookup"><span data-stu-id="d94b2-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="d94b2-208">重要なレベルに到達していた WAN リンクをフィルター処理する (WAN リンクの帯域幅の 90% を超える帯域幅使用量)</span><span class="sxs-lookup"><span data-stu-id="d94b2-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="d94b2-209">WAN のリンクの種類によってフィルター処理: ネットワークサイトリンク、地域間のリンク、サイト内のリンク</span><span class="sxs-lookup"><span data-stu-id="d94b2-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="d94b2-210">ネットワーク地域でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="d94b2-210">Filtered by network region</span></span>

<span data-ttu-id="d94b2-211">このツールのマニュアルは、 [Lync Server 2013 リソースキットツールのマニュアル](http://go.microsoft.com/fwlink/?linkid=623245)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="d94b2-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](http://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d94b2-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="d94b2-212">See Also</span></span>


[<span data-ttu-id="d94b2-213">毎週のタスクチェックリスト</span><span class="sxs-lookup"><span data-stu-id="d94b2-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

