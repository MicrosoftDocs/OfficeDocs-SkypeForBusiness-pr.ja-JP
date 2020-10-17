---
title: 'Lync Server 2013: Lync Server の正常性構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa0164a9e3003c130bc7b14a4312397a4559843c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528244"
---
# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="2a432-102">Lync Server 2013 の正常性構成</span><span class="sxs-lookup"><span data-stu-id="2a432-102">Health configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a432-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="2a432-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="2a432-104">さまざまな web サイト、Microsoft サポート技術情報の記事、Lync Server リソースキットツールの間では、Lync Server の実行時に問題が発生した管理者は、これらの問題を解決する方法については、それほどのものではありません。</span><span class="sxs-lookup"><span data-stu-id="2a432-104">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="2a432-105">Lync server は、ネットワーククラッシュやハードウェア障害などの多くの要因によっては、製品自体が制御できないため、lync server 2013 で問題が発生しないことを保証する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="2a432-105">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="2a432-106">正常性の監視を実装することで、管理者は、実際の問題になる前に潜在的な問題を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="2a432-106">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="2a432-107">たとえば、管理者は Lync Server 監視を使用して、傾向と tendencies を識別できます。</span><span class="sxs-lookup"><span data-stu-id="2a432-107">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="2a432-108">たとえば、音声ビデオ会議の数が着実に増加した場合は、システムが過負荷になる前に容量を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a432-108">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="2a432-109">同様の方法で、管理者は System Center Operations Manager を使用して、指定したイベントが発生したときにリアルタイムでの通知を発行したり、システムを事前にテストする代理トランザクションを実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2a432-109">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="2a432-110">代理トランザクションは、ユーザーがシステムへのログオン、インスタントメッセージの交換、または公衆交換電話網 (PSTN) に配置された電話機への通話の作成などの一般的なタスクを正常に完了できることを確認するために、Lync Server で使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a432-110">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="2a432-111">たとえば、このようなテストを定期的に実行することで、Lync Server にログオンしているユーザーに関する潜在的な問題について警告し、ユーザーからの呼び出しによってサポートチームがあふれて、接続を確立できないという問題を解決できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2a432-111">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="2a432-112">System Center Operations Manager を使用してこれらの代理トランザクションを実行することにより、管理者は、発行される可能性のあるアラートに対する応答を超えることなく、毎日24時間で Lync Server の展開を継続的に監視することができます。</span><span class="sxs-lookup"><span data-stu-id="2a432-112">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a432-113">Lync Server 2013 の場合、System Center Operations Manager 用の管理パックは、Lync Server に悪影響を及ぼす可能性のある "外部" 問題を検出することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a432-113">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="2a432-114">たとえば、インターネットインフォメーションサービス (IIS) がオフラインになった場合、Lync Server コンピューターのシステムリソースが指定した値を下回った場合、または Lync Server コンピューターでハードウェア障害が発生した場合に、管理者に通知することができます。</span><span class="sxs-lookup"><span data-stu-id="2a432-114">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="2a432-115">Lync Server 2013 の正常性構成は、System Center Operations Manager および Lync Server 管理パックの使用に基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="2a432-115">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="2a432-116">これらの管理パックには、次のような新機能と機能拡張が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2a432-116">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="2a432-117">**場所を問わないシナリオの可用性。**</span><span class="sxs-lookup"><span data-stu-id="2a432-117">**Scenario availability from any location.**</span></span> <span data-ttu-id="2a432-118">Lync Server 2010 管理パックでは、代理トランザクションを使用したエンドユーザーシナリオの可用性を監視する概念が導入されています。</span><span class="sxs-lookup"><span data-stu-id="2a432-118">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="2a432-119">Lync Server 2013 では、これらのエージェントは、より多くの代理トランザクションを持っており、企業の外部の地理的な場所からブランチオフィスアプライアンスおよび Lync Server 2010 展開に対して、従来のエッジ展開に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="2a432-119">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="2a432-120">**代理トランザクション ログ。**</span><span class="sxs-lookup"><span data-stu-id="2a432-120">**Synthetic transaction logs.**</span></span> <span data-ttu-id="2a432-121">代理トランザクションが失敗したとき、管理者は HTML ログを参照して、失敗の内容を判断するのに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="2a432-121">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="2a432-122">これには、失敗したアクション、各アクションの待機時間、テストの実行に使用されたコマンド ライン、発生したエラーを把握することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2a432-122">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="2a432-123">**通話の信頼性のカバレッジの拡大。**</span><span class="sxs-lookup"><span data-stu-id="2a432-123">**Increased call reliability coverage.**</span></span> <span data-ttu-id="2a432-124">Lync Server 2010 管理パックでは、エンドユーザーの音声呼び出しに影響する重大な接続の問題を検出するために、通話の信頼性に関する警告が導入されました。</span><span class="sxs-lookup"><span data-stu-id="2a432-124">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="2a432-125">Lync Server 2013 管理パックは、ピアツーピアのインスタントメッセージング (IM) およびその他の基本的な会議機能の対象を追加して、ノイズを軽減しながら、処理範囲を最大化します。</span><span class="sxs-lookup"><span data-stu-id="2a432-125">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="2a432-126">**依存関係の監視。**</span><span class="sxs-lookup"><span data-stu-id="2a432-126">**Dependency monitoring.**</span></span> <span data-ttu-id="2a432-127">Lync Server のシナリオは、IIS がオフラインになっている、CPU およびメモリリソースが限られている、ディスクの問題などのさまざまな外部要因によって失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="2a432-127">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="2a432-128">新しい管理パックでは、管理者が影響を認識しておけるように、一部の重要な依存関係をチェックします。</span><span class="sxs-lookup"><span data-stu-id="2a432-128">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="2a432-129">**レポート機能の拡張。**</span><span class="sxs-lookup"><span data-stu-id="2a432-129">**Enhanced reporting.**</span></span> <span data-ttu-id="2a432-130">シナリオの可用性、容量に関する計画、問題の発生が最も多いコンポーネントの把握などについて管理者が役立てることができる、一連のレポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="2a432-130">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="2a432-131">管理パックには、Lync Server 展開の正常性を検出して診断するのに役立つさまざまな機能も含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a432-131">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="2a432-132">これらの機能を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="2a432-132">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="2a432-133">管理パックの機能</span><span class="sxs-lookup"><span data-stu-id="2a432-133">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a432-134">機能</span><span class="sxs-lookup"><span data-stu-id="2a432-134">Feature</span></span></th>
<th><span data-ttu-id="2a432-135">説明</span><span class="sxs-lookup"><span data-stu-id="2a432-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a432-136">代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="2a432-136">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="2a432-137">さまざまな場所から実行できる Windows PowerShell コマンドレットを使用して、エンドユーザーがサインイン、プレゼンス、IM、会議などのエンドユーザーシナリオを簡単に利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2a432-137">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a432-138">通話の信頼性のアラート</span><span class="sxs-lookup"><span data-stu-id="2a432-138">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="2a432-139">詳細な通話の記録 (CDR) を対象とするデータベース クエリです。</span><span class="sxs-lookup"><span data-stu-id="2a432-139">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="2a432-140">これらのレコードはフロントエンドサーバーによって書き込まれ、エンドユーザーが通話に接続できたかどうか、または通話が終了した理由が反映されます。</span><span class="sxs-lookup"><span data-stu-id="2a432-140">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="2a432-141">これらの記録は、幅広いエンド ユーザーでピアツーピア通話または基本的な会議機能に関して接続の問題が発生しているときに、それを示すアラートとなります。</span><span class="sxs-lookup"><span data-stu-id="2a432-141">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a432-142">メディア品質のアラート</span><span class="sxs-lookup"><span data-stu-id="2a432-142">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="2a432-p112">個々の通話の終了時にクライアントが発行する Quality of Experience (QoE) レポートを参照するデータベース クエリです。これらのクエリは、通話中および電話会議中のメディア品質が悪い状態と考えられる場合のシナリオに特化したアラートとなります。このデータは、パケットの遅延や損失などの主要な指標、通話品質に直接影響することで知られる指標に基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="2a432-p112">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call. These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences. The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a432-146">コンポーネントの正常性</span><span class="sxs-lookup"><span data-stu-id="2a432-146">Component Health</span></span></p></td>
<td><p><span data-ttu-id="2a432-p113">個別のサーバ コンポーネントは、イベント ログおよびパフォーマンス カウンターを使用してアラートを発行します。これらのアラートは、1 つ以上のエンド ユーザー シナリオに重大な影響を与える可能性があるエラー状態を示します。また、サービスが実行されていない、エラー率が高い、メッセージの遅延が大きい、閲属性の問題など、その他のさまざまなエラー状態を示す場合もあります。</span><span class="sxs-lookup"><span data-stu-id="2a432-p113">Individual server components raise alerts by using event logs and performance counters. These alerts indicate failure conditions that can severely impact one or more end user scenarios. These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a432-150">依存関係の状態</span><span class="sxs-lookup"><span data-stu-id="2a432-150">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="2a432-151">エラーはさまざまな外部的な理由で起こる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a432-151">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="2a432-152">管理パックでは、IIS の可用性、サーバとプロセスによる CPU とメモリの使用状況、ディスクの指標など、重大な問題になりうる重要な外部の依存関係の一部について、監視とデータ収集を行うようになりました。</span><span class="sxs-lookup"><span data-stu-id="2a432-152">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2a432-153">システムが発行するアラートは、3 つの一般的なカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="2a432-153">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="2a432-154">**優先度が高いアラート。**</span><span class="sxs-lookup"><span data-stu-id="2a432-154">**High-priority Alerts.**</span></span> <span data-ttu-id="2a432-155">これらのアラートは、多数のユーザーでサービス停止が発生する状態を指します。</span><span class="sxs-lookup"><span data-stu-id="2a432-155">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="2a432-156">たとえば、Lync Server 2013 には高可用性機能が組み込まれているため、1台のコンピューターでコンポーネント障害が高優先度のアラートになることはありません。</span><span class="sxs-lookup"><span data-stu-id="2a432-156">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="2a432-157">そうではなく、優先度が高いアラートとは、"管理者が深夜に対応しなければならない" ほどの問題です。</span><span class="sxs-lookup"><span data-stu-id="2a432-157">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="2a432-158">代理トランザクションによって検出された停止や、サービスのオフライン状態 (たとえば音声/ビデオ会議) は、優先度が高いアラートと見なされます。</span><span class="sxs-lookup"><span data-stu-id="2a432-158">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="2a432-159">**中程度の優先度のアラート。**</span><span class="sxs-lookup"><span data-stu-id="2a432-159">**Medium-priority alerts.**.</span></span> <span data-ttu-id="2a432-160">これらのアラートは、ユーザーのサブセットに影響を与えたり、通話品質の低下を示したりする条件を示します。</span><span class="sxs-lookup"><span data-stu-id="2a432-160">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="2a432-161">これには、呼び出しのコンポーネント障害、通話の待機時間の遅延、音質の低下などの問題が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2a432-161">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="2a432-162">このカテゴリの通知はステートフルであり、問題の現在の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="2a432-162">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="2a432-163">たとえば、呼び出しの確立時間が警告のしきい値を超えた場合を考えます。</span><span class="sxs-lookup"><span data-stu-id="2a432-163">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="2a432-164">通話の確立時間が通常に戻ると、これらのアラートは System Center Operations Manager で自動解決されます。</span><span class="sxs-lookup"><span data-stu-id="2a432-164">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="2a432-165">これらのアラートは、管理者が同じ営業日に調査することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="2a432-165">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="2a432-166">**その他のアラート。**</span><span class="sxs-lookup"><span data-stu-id="2a432-166">**Other alerts.**</span></span> <span data-ttu-id="2a432-167">これは、特定のユーザーまたは一部のユーザーに影響を与える可能性があるコンポーネントからのアラートです。</span><span class="sxs-lookup"><span data-stu-id="2a432-167">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="2a432-168">たとえば、アドレス帳サービスが特定のユーザーの Active Directory エントリを解析できない場合が考えられます。</span><span class="sxs-lookup"><span data-stu-id="2a432-168">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="2a432-169">これらのアラートでは、管理者が時間に余裕があるときにアラートを見ることが期待されています。</span><span class="sxs-lookup"><span data-stu-id="2a432-169">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2a432-170">このセクション中</span><span class="sxs-lookup"><span data-stu-id="2a432-170">In This Section</span></span>

  - [<span data-ttu-id="2a432-171">Lync Server 2013 を System Center Operations Manager と連携するように構成する</span><span class="sxs-lookup"><span data-stu-id="2a432-171">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="2a432-172">Lync Server 2013 で代理トランザクションに対してリッチログを使用する</span><span class="sxs-lookup"><span data-stu-id="2a432-172">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="2a432-173">Lync Server 2013 の System Center Operations Manager データベースとしての Microsoft SQL Server 2008 R2 の使用</span><span class="sxs-lookup"><span data-stu-id="2a432-173">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

