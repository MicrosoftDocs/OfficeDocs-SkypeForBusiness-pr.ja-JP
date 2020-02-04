---
title: 'Lync Server 2013: 操作の依存関係'
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
ms.openlocfilehash: 26e7de821dee778d4b0b1e9aa105669635abaf6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="dccb7-102">Lync Server 2013 での操作の依存関係</span><span class="sxs-lookup"><span data-stu-id="dccb7-102">Operational dependencies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dccb7-103">_**最終更新日:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="dccb7-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="dccb7-104">このドキュメントで説明されているリファレンスアーキテクチャでは、組織の要件を満たしているだけでなく、Microsoft のベストプラクティスに従って設計された Lync Server 2013 の展開を確実に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dccb7-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="dccb7-105">Lync Server 2013 の実装は動的サービスであり、エンタープライズ内の他のサービスと同様、高レベルのサービスの可用性とサービス品質をビジネスに維持するためには、監視と予防的な管理が必要であると考えてください。</span><span class="sxs-lookup"><span data-stu-id="dccb7-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="dccb7-106">Lync Server 2013 は組織の日常業務の ingrained になるため、サービスを正確かつ有形のサービスレベル管理によって管理することが重要です。</span><span class="sxs-lookup"><span data-stu-id="dccb7-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="dccb7-107">Lync システムアーキテクチャは複雑で、非常に統合され、効果的なサービスレベル管理を維持し、Lync Server 2013 の Sla を確立するために、その他のプラットフォームやサーバーに対するシステムの依存関係を理解することが重要になります。</span><span class="sxs-lookup"><span data-stu-id="dccb7-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="dccb7-108">音声や UC に統合されたアプリケーションなど、どのビジネスサービスが Lync に依存しているかを確認することも重要です。</span><span class="sxs-lookup"><span data-stu-id="dccb7-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="dccb7-109">すべての依存関係をメモするため、Lync Server 2013 を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dccb7-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="dccb7-110">Service map を使用すると、Lync とその依存サービスの間で SLA を策定し、SLA ネゴシエーションの開始位置を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="dccb7-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="dccb7-111">次の表に、Lync インフラストラクチャの一般的な依存関係サービスを示します。</span><span class="sxs-lookup"><span data-stu-id="dccb7-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="dccb7-112">これらの各テクノロジには、独自の事前監視を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dccb7-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="dccb7-113">一般的な依存関係サービス</span><span class="sxs-lookup"><span data-stu-id="dccb7-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dccb7-114">依存関係サービス</span><span class="sxs-lookup"><span data-stu-id="dccb7-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-115">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="dccb7-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dccb7-116">サーバーハードウェア</span><span class="sxs-lookup"><span data-stu-id="dccb7-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="dccb7-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dccb7-118">公開キー基盤</span><span class="sxs-lookup"><span data-stu-id="dccb7-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-119">ドメインネーミングサービス</span><span class="sxs-lookup"><span data-stu-id="dccb7-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dccb7-120">データベースサービス</span><span class="sxs-lookup"><span data-stu-id="dccb7-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-121">ストレージサービス</span><span class="sxs-lookup"><span data-stu-id="dccb7-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dccb7-122">システム管理–監視と配布</span><span class="sxs-lookup"><span data-stu-id="dccb7-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-123">セキュリティサービス-ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="dccb7-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dccb7-124">ネットワークインフラストラクチャ-インターネット</span><span class="sxs-lookup"><span data-stu-id="dccb7-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-125">ネットワークインフラストラクチャ–内部 (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="dccb7-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dccb7-126">テレフォニーインフラストラクチャ– IP PBX とゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="dccb7-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-127">クラウドサービス</span><span class="sxs-lookup"><span data-stu-id="dccb7-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dccb7-128">MOF で規定されている変更、インシデント、リリース管理などの基本的なサービスレベル管理機能を利用するために、組織が運用されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="dccb7-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="dccb7-129">Lync ソリューションは、これらの機能によって採用され、同じ運用管理プロセスの対象となります。</span><span class="sxs-lookup"><span data-stu-id="dccb7-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="dccb7-130">上に記載された情報に基づいて構築することで、企業の Lync サービスに影響を与える可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="dccb7-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="dccb7-131">Lync Server 2013 サービスの可用性と品質を確保するために、次の監視ツールを参照アーキテクチャの展開に付随させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dccb7-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="dccb7-132">監視ツール</span><span class="sxs-lookup"><span data-stu-id="dccb7-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dccb7-133">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dccb7-133">Component</span></span></th>
<th><span data-ttu-id="dccb7-134">説明</span><span class="sxs-lookup"><span data-stu-id="dccb7-134">Description</span></span></th>
<th><span data-ttu-id="dccb7-135">該当するサイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-136">Lync Server 2013 Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="dccb7-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="dccb7-137">中央サイトあたり少なくとも1つの Lync Server 2013 監視サーバーロールを展開して、Quality of Experience (QoE) レポートパックを構成します。</span><span class="sxs-lookup"><span data-stu-id="dccb7-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="dccb7-138">詳細については、Lync Server 2013 展開に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dccb7-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="dccb7-139"><a href="lync-server-2013-deploying-monitoring.md">Lync Server 2013 での監視の展開</a></span><span class="sxs-lookup"><span data-stu-id="dccb7-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dccb7-140">セントラルサイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="dccb7-141">各プールを監視サーバーの役割の最も近いインスタンスにします。</span><span class="sxs-lookup"><span data-stu-id="dccb7-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="dccb7-142">セントラルサイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-142">Central sites</span></span></p>
<p><span data-ttu-id="dccb7-143">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="dccb7-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="dccb7-145">System Center Operations Manager 2012 (Microsoft Lync Server 2013 管理パック (MP) をインポートしました。</span><span class="sxs-lookup"><span data-stu-id="dccb7-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="dccb7-146">管理パックは、従来のイベントログとパフォーマンスカウンターベースのインストルメンテーションを実装するだけでなく、Lync Server 2013 で新しく利用可能なインストルメンテーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="dccb7-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="dccb7-147">セントラルサイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="dccb7-148">監視する必要がある役割やコンポーネントの検出に対する集中検出が、全体管理データベースで公開されているトポロジドキュメントを読み取るセントラル検出スクリプトに基づいて、自動的に完了するようにします。</span><span class="sxs-lookup"><span data-stu-id="dccb7-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="dccb7-149">中央サイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-149">Central Site</span></span></p>
<p><span data-ttu-id="dccb7-150">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-150">Branch Site</span></span></p>
<p><span data-ttu-id="dccb7-151">Edge サイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="dccb7-152">Lync Server を実行しているすべての展開されたサーバーに System Centre Operations Manager 2007 エージェントを展開します。</span><span class="sxs-lookup"><span data-stu-id="dccb7-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="dccb7-153">中央サイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-153">Central Site</span></span></p>
<p><span data-ttu-id="dccb7-154">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-154">Branch Site</span></span></p>
<p><span data-ttu-id="dccb7-155">Edge サイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="dccb7-156">優先順位付きのアラートが通知用に構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dccb7-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="dccb7-157">優先度の高い警告</span><span class="sxs-lookup"><span data-stu-id="dccb7-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="dccb7-158">中程度の優先度の警告</span><span class="sxs-lookup"><span data-stu-id="dccb7-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="dccb7-159">その他のアラート。</span><span class="sxs-lookup"><span data-stu-id="dccb7-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="dccb7-160">中央サイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-160">Central Site</span></span></p>
<p><span data-ttu-id="dccb7-161">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-161">Branch Site</span></span></p>
<p><span data-ttu-id="dccb7-162">Edge サイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="dccb7-163">展開のポート監視を構成します。</span><span class="sxs-lookup"><span data-stu-id="dccb7-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="dccb7-164">中央サイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-164">Central Site</span></span></p>
<p><span data-ttu-id="dccb7-165">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-165">Branch Site</span></span></p>
<p><span data-ttu-id="dccb7-166">Edge サイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="dccb7-167">展開のための URL 監視を構成する</span><span class="sxs-lookup"><span data-stu-id="dccb7-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="dccb7-168">中央サイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-169">Lync と System Center Operations Manager の統合</span><span class="sxs-lookup"><span data-stu-id="dccb7-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="dccb7-170">通話の信頼性とメディア品質監視通話の信頼性とメディアの品質監視監視ノードとして監視サーバーコンピューターを使用して、通話の信頼性とメディア品質を監視します。</span><span class="sxs-lookup"><span data-stu-id="dccb7-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="dccb7-171">どちらの機能でも、監視サーバーのデータベースに対して分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="dccb7-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="dccb7-172">中央サイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-172">Central Site</span></span></p>
<p><span data-ttu-id="dccb7-173">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="dccb7-174">メディア品質の警告しきい値が正確に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dccb7-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="dccb7-175">次の表は、コーデックによる最大ネットワーク平均の意見スコアを示しています。</span><span class="sxs-lookup"><span data-stu-id="dccb7-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="dccb7-176">実稼働環境では、これらのスコアは設定された期間に対して監視する必要があり、許容されるしきい値は、組織固有の NMOS スコアに基づいて確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dccb7-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="dccb7-177">中央サイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-177">Central Site</span></span></p>
<p><span data-ttu-id="dccb7-178">ブランチサイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-179">Lync Server 2013 の代理トランザクションウォッチャー</span><span class="sxs-lookup"><span data-stu-id="dccb7-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="dccb7-180">専用の Lync サーバーを代理トランザクションウォッチャーとして展開します。</span><span class="sxs-lookup"><span data-stu-id="dccb7-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="dccb7-181">代理トランザクションは、事前に定義された間隔で管理パックによって自動的にトリガーされる Lync Server 2013 Windows PowerShell コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="dccb7-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="dccb7-182">これらは、各プールの STs の検出と実行を担当する管理者指定のサーバーである代理トランザクションウォッチャーノードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="dccb7-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="dccb7-183">既存の Microsoft Lync Server 2013 サーバーを代理トランザクションウォッチャーノードとして使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="dccb7-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="dccb7-184">これは、STs を実行するための CPU またはメモリ使用量の高い要件が原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="dccb7-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="dccb7-185">代理トランザクションウォッチャーノードには、新しいサーバーコンピューター (または仮想サーバー) を使います。</span><span class="sxs-lookup"><span data-stu-id="dccb7-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="dccb7-186">中央サイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="dccb7-187">代理トランザクションウォッチャーノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="dccb7-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="dccb7-188">「ドキュメントの接続」をタップして MonitoringCS_withSCOM .docx ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dccb7-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="dccb7-189">中央サイト</span><span class="sxs-lookup"><span data-stu-id="dccb7-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="dccb7-190">コーデックあたりの最大ネットワーク MOS スコア</span><span class="sxs-lookup"><span data-stu-id="dccb7-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dccb7-191">シナリオ</span><span class="sxs-lookup"><span data-stu-id="dccb7-191">Scenario</span></span></th>
<th><span data-ttu-id="dccb7-192">コーデック</span><span class="sxs-lookup"><span data-stu-id="dccb7-192">Codec</span></span></th>
<th><span data-ttu-id="dccb7-193">最大 NMOS</span><span class="sxs-lookup"><span data-stu-id="dccb7-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-194">UC-UC 通話</span><span class="sxs-lookup"><span data-stu-id="dccb7-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="dccb7-195">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="dccb7-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="dccb7-196">4.10</span><span class="sxs-lookup"><span data-stu-id="dccb7-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dccb7-197">UC-UC 通話</span><span class="sxs-lookup"><span data-stu-id="dccb7-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="dccb7-198">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="dccb7-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="dccb7-199">2.95</span><span class="sxs-lookup"><span data-stu-id="dccb7-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-200">電話会議</span><span class="sxs-lookup"><span data-stu-id="dccb7-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="dccb7-201">Siren</span><span class="sxs-lookup"><span data-stu-id="dccb7-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="dccb7-202">3.72</span><span class="sxs-lookup"><span data-stu-id="dccb7-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dccb7-203">UC-PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="dccb7-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="dccb7-204">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="dccb7-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="dccb7-205">2.95</span><span class="sxs-lookup"><span data-stu-id="dccb7-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dccb7-206">UC-PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="dccb7-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="dccb7-207">G-711</span><span class="sxs-lookup"><span data-stu-id="dccb7-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="dccb7-208">3.61</span><span class="sxs-lookup"><span data-stu-id="dccb7-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dccb7-209">以前のプロアクティブな監視アクティビティの前後に、メンテナンスタスクは、Lync RA 運用ガイドで定義されているように、毎日、毎週、および毎月の定期的、エッジサイトとブランチサイトに対して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dccb7-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

