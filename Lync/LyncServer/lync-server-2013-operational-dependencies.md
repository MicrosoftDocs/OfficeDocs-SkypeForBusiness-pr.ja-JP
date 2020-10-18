---
title: 'Lync Server 2013: 運用上の依存関係'
description: 'Lync Server 2013: 運用上の依存関係。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e240981f5dfded7c27f123c8483794ea3ffedff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579193"
---
# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="1903b-103">Lync Server 2013 の運用上の依存関係</span><span class="sxs-lookup"><span data-stu-id="1903b-103">Operational dependencies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1903b-104">_**トピックの最終更新日:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="1903b-104">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="1903b-105">このドキュメントで説明されている参照アーキテクチャにより、組織の要件に合わせて拡張できるだけでなく、Microsoft のベストプラクティスに従って設計された Lync Server 2013 の展開を確実に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1903b-105">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="1903b-106">Lync Server 2013 の実装は動的なサービスであり、エンタープライズのその他のサービスと同様に、サービスの可用性とサービスの品質をビジネスに維持するために、監視および予防的な管理が必要になります。</span><span class="sxs-lookup"><span data-stu-id="1903b-106">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="1903b-107">Lync Server 2013 が組織の日常業務で深く ingrained されるため、サービスを正確かつ有形のサービスレベル管理によって管理することが重要になります。</span><span class="sxs-lookup"><span data-stu-id="1903b-107">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="1903b-108">Lync システムアーキテクチャは複雑で統合されており、効果的なサービスレベル管理を維持し、Lync Server 2013 の Sla を確立するために、他のプラットフォームおよびサーバーに対するシステムの依存関係を理解する上で不可欠となります。</span><span class="sxs-lookup"><span data-stu-id="1903b-108">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="1903b-109">音声や UC 統合アプリケーションなどのビジネスサービスが Lync に依存していることに注意することも重要です。</span><span class="sxs-lookup"><span data-stu-id="1903b-109">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="1903b-110">「Lync Server 2013 を確立して、すべての依存関係を記録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1903b-110">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="1903b-111">サービスマップを使用すると、Lync とその依存サービスの間の SLA を策定し、SLA ネゴシエーションの開始位置を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="1903b-111">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="1903b-112">次の表に、Lync インフラストラクチャの一般的な依存関係サービスを示します。</span><span class="sxs-lookup"><span data-stu-id="1903b-112">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="1903b-113">これらの各テクノロジには、独自の事前監視を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1903b-113">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="1903b-114">一般的な依存関係サービス</span><span class="sxs-lookup"><span data-stu-id="1903b-114">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1903b-115">依存関係サービス</span><span class="sxs-lookup"><span data-stu-id="1903b-115">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1903b-116">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="1903b-116">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1903b-117">サーバーハードウェア</span><span class="sxs-lookup"><span data-stu-id="1903b-117">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1903b-118">Active Directory</span><span class="sxs-lookup"><span data-stu-id="1903b-118">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1903b-119">公開キー基盤</span><span class="sxs-lookup"><span data-stu-id="1903b-119">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1903b-120">ドメインネームサービス</span><span class="sxs-lookup"><span data-stu-id="1903b-120">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1903b-121">データベースサービス</span><span class="sxs-lookup"><span data-stu-id="1903b-121">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1903b-122">ストレージサービス</span><span class="sxs-lookup"><span data-stu-id="1903b-122">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1903b-123">システム管理–監視と配布</span><span class="sxs-lookup"><span data-stu-id="1903b-123">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1903b-124">セキュリティサービス-ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="1903b-124">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1903b-125">ネットワークインフラストラクチャ-インターネット</span><span class="sxs-lookup"><span data-stu-id="1903b-125">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1903b-126">ネットワークインフラストラクチャ–内部 (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="1903b-126">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1903b-127">テレフォニーインフラストラクチャ– ip-pbx およびゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="1903b-127">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1903b-128">クラウドサービス</span><span class="sxs-lookup"><span data-stu-id="1903b-128">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1903b-129">MOF で規定されているように、変更、インシデント、リリース管理などの基本的なサービスレベル管理機能を行使するには、組織が運用されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="1903b-129">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="1903b-130">Lync ソリューションは、これらの機能によって採用され、同じ運用管理プロセスの対象となります。</span><span class="sxs-lookup"><span data-stu-id="1903b-130">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="1903b-131">上で取得した情報に基づいて、企業の Lync サービスに影響を与える可能性をより深く理解できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1903b-131">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="1903b-132">Lync Server 2013 サービスの可用性と品質を確実にするために、以下の監視ツールが参照アーキテクチャの展開に付随する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1903b-132">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="1903b-133">監視ツール</span><span class="sxs-lookup"><span data-stu-id="1903b-133">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1903b-134">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1903b-134">Component</span></span></th>
<th><span data-ttu-id="1903b-135">説明</span><span class="sxs-lookup"><span data-stu-id="1903b-135">Description</span></span></th>
<th><span data-ttu-id="1903b-136">適用可能なサイト</span><span class="sxs-lookup"><span data-stu-id="1903b-136">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1903b-137">Lync Server 2013 監視サーバー</span><span class="sxs-lookup"><span data-stu-id="1903b-137">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="1903b-138">中央サイトごとに少なくとも1つの Lync Server 2013 監視サーバーの役割を展開し、QoE (Quality of Experience) Reporting Pack を構成します。</span><span class="sxs-lookup"><span data-stu-id="1903b-138">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="1903b-139">詳細については、「Lync Server 2013 の展開に関するドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1903b-139">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="1903b-140"><a href="lync-server-2013-deploying-monitoring.md">Lync Server 2013 での監視の展開</a></span><span class="sxs-lookup"><span data-stu-id="1903b-140"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1903b-141">中央サイト</span><span class="sxs-lookup"><span data-stu-id="1903b-141">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="1903b-142">各プールを監視サーバーの役割の最も近いインスタンスに指定します。</span><span class="sxs-lookup"><span data-stu-id="1903b-142">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="1903b-143">中央サイト</span><span class="sxs-lookup"><span data-stu-id="1903b-143">Central sites</span></span></p>
<p><span data-ttu-id="1903b-144">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="1903b-144">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1903b-145">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="1903b-145">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="1903b-146">Microsoft Lync Server 2013 管理パック (MP) がインポートされた System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="1903b-146">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="1903b-147">管理パックは従来のイベントログとパフォーマンスカウンターベースのインストルメンテーションを実装するだけでなく、Lync Server 2013 で新しく使用可能なインストルメンテーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1903b-147">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="1903b-148">中央サイト</span><span class="sxs-lookup"><span data-stu-id="1903b-148">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="1903b-149">中央管理データベースに公開されているトポロジドキュメントを読み取る中央探索スクリプトに基づいて、監視する必要がある役割およびコンポーネントの検出に対する中央検出が自動的に完了するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1903b-149">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="1903b-150">中央サイト</span><span class="sxs-lookup"><span data-stu-id="1903b-150">Central Site</span></span></p>
<p><span data-ttu-id="1903b-151">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="1903b-151">Branch Site</span></span></p>
<p><span data-ttu-id="1903b-152">エッジサイト</span><span class="sxs-lookup"><span data-stu-id="1903b-152">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="1903b-153">Lync Server を実行しているすべての展開済みサーバーに System Centre Operations Manager 2007 エージェントを展開します。</span><span class="sxs-lookup"><span data-stu-id="1903b-153">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="1903b-154">中央サイト</span><span class="sxs-lookup"><span data-stu-id="1903b-154">Central Site</span></span></p>
<p><span data-ttu-id="1903b-155">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="1903b-155">Branch Site</span></span></p>
<p><span data-ttu-id="1903b-156">エッジサイト</span><span class="sxs-lookup"><span data-stu-id="1903b-156">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="1903b-157">通知用に優先度を設定した通知を構成してください。</span><span class="sxs-lookup"><span data-stu-id="1903b-157">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="1903b-158">高優先度のアラート</span><span class="sxs-lookup"><span data-stu-id="1903b-158">High Priority Alerts</span></span></p>
<p><span data-ttu-id="1903b-159">中優先度の警告</span><span class="sxs-lookup"><span data-stu-id="1903b-159">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="1903b-160">その他のアラート。</span><span class="sxs-lookup"><span data-stu-id="1903b-160">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="1903b-161">中央サイト</span><span class="sxs-lookup"><span data-stu-id="1903b-161">Central Site</span></span></p>
<p><span data-ttu-id="1903b-162">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="1903b-162">Branch Site</span></span></p>
<p><span data-ttu-id="1903b-163">エッジサイト</span><span class="sxs-lookup"><span data-stu-id="1903b-163">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="1903b-164">展開のポート監視を構成します。</span><span class="sxs-lookup"><span data-stu-id="1903b-164">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="1903b-165">中央サイト</span><span class="sxs-lookup"><span data-stu-id="1903b-165">Central Site</span></span></p>
<p><span data-ttu-id="1903b-166">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="1903b-166">Branch Site</span></span></p>
<p><span data-ttu-id="1903b-167">エッジサイト</span><span class="sxs-lookup"><span data-stu-id="1903b-167">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="1903b-168">展開の URL 監視を構成する</span><span class="sxs-lookup"><span data-stu-id="1903b-168">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="1903b-169">中央サイト</span><span class="sxs-lookup"><span data-stu-id="1903b-169">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1903b-170">Lync および System Center Operations Manager の統合</span><span class="sxs-lookup"><span data-stu-id="1903b-170">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="1903b-171">展開通話の信頼性とメディア品質監視呼び出しの信頼性とメディア品質監視 Lync Server の通話の信頼性とメディア品質を監視する監視ノードとして、監視サーバーコンピューターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1903b-171">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="1903b-172">これらの機能はどちらも、分析を行うために監視サーバーデータベースに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="1903b-172">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="1903b-173">中央サイト</span><span class="sxs-lookup"><span data-stu-id="1903b-173">Central Site</span></span></p>
<p><span data-ttu-id="1903b-174">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="1903b-174">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="1903b-175">メディア品質の警告しきい値が正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1903b-175">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="1903b-176">次の表は、コーデックによる最大ネットワーク平均意見のスコアを示しています。</span><span class="sxs-lookup"><span data-stu-id="1903b-176">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="1903b-177">運用環境では、これらのスコアは、設定された期間に対して監視する必要があり、組織固有の NMOS スコアに基づいて許容されるしきい値を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1903b-177">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="1903b-178">中央サイト</span><span class="sxs-lookup"><span data-stu-id="1903b-178">Central Site</span></span></p>
<p><span data-ttu-id="1903b-179">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="1903b-179">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1903b-180">Lync Server 2013 代理トランザクション監視</span><span class="sxs-lookup"><span data-stu-id="1903b-180">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="1903b-181">代理トランザクション監視用に専用の Lync Server を展開します。</span><span class="sxs-lookup"><span data-stu-id="1903b-181">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="1903b-182">代理トランザクションは、事前定義された間隔で管理パックによって自動的にトリガーされる Lync Server 2013 Windows PowerShell コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="1903b-182">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="1903b-183">これらは、代理トランザクション監視ノードで実行されます。これは、管理者が指定したサーバーで、各プールの STs の検出と実行を担当します。</span><span class="sxs-lookup"><span data-stu-id="1903b-183">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="1903b-184">既存の Microsoft Lync Server 2013 サーバーを代理トランザクション監視ノードとして使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="1903b-184">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="1903b-185">これは、STs を実行するための CPU またはメモリの使用要件が高くなるためです。</span><span class="sxs-lookup"><span data-stu-id="1903b-185">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="1903b-186">代理トランザクション監視ノードには、新しいサーバーコンピューター (または仮想サーバー) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1903b-186">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="1903b-187">中央サイト</span><span class="sxs-lookup"><span data-stu-id="1903b-187">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="1903b-188">代理トランザクション監視ノードの展開。</span><span class="sxs-lookup"><span data-stu-id="1903b-188">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="1903b-189">「UCTAP connect documentation」から「MonitoringCS_withSCOM.docx ドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1903b-189">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="1903b-190">中央サイト</span><span class="sxs-lookup"><span data-stu-id="1903b-190">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="1903b-191">コーデックあたりの最大ネットワーク MOS スコア</span><span class="sxs-lookup"><span data-stu-id="1903b-191">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1903b-192">シナリオ</span><span class="sxs-lookup"><span data-stu-id="1903b-192">Scenario</span></span></th>
<th><span data-ttu-id="1903b-193">コーデック</span><span class="sxs-lookup"><span data-stu-id="1903b-193">Codec</span></span></th>
<th><span data-ttu-id="1903b-194">Max NMOS</span><span class="sxs-lookup"><span data-stu-id="1903b-194">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1903b-195">UC-UC 通話</span><span class="sxs-lookup"><span data-stu-id="1903b-195">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="1903b-196">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="1903b-196">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="1903b-197">4.10</span><span class="sxs-lookup"><span data-stu-id="1903b-197">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1903b-198">UC-UC 通話</span><span class="sxs-lookup"><span data-stu-id="1903b-198">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="1903b-199">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="1903b-199">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="1903b-200">2.95</span><span class="sxs-lookup"><span data-stu-id="1903b-200">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1903b-201">電話会議</span><span class="sxs-lookup"><span data-stu-id="1903b-201">Conference call</span></span></p></td>
<td><p><span data-ttu-id="1903b-202">Siren</span><span class="sxs-lookup"><span data-stu-id="1903b-202">Siren</span></span></p></td>
<td><p><span data-ttu-id="1903b-203">3.72</span><span class="sxs-lookup"><span data-stu-id="1903b-203">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1903b-204">UC-PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="1903b-204">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="1903b-205">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="1903b-205">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="1903b-206">2.95</span><span class="sxs-lookup"><span data-stu-id="1903b-206">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1903b-207">UC-PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="1903b-207">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="1903b-208">G-711</span><span class="sxs-lookup"><span data-stu-id="1903b-208">G-711</span></span></p></td>
<td><p><span data-ttu-id="1903b-209">3.61</span><span class="sxs-lookup"><span data-stu-id="1903b-209">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1903b-210">以前のプロアクティブな監視アクティビティの前後に、「Lync RA Operations Guide」で定義されているように、毎日、毎週、および毎月定期的に、定期的に、エッジサイトとブランチサイトに対してメンテナンスタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1903b-210">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

