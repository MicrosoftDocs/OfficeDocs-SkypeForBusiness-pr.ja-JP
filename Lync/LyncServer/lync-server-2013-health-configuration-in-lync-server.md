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
ms.openlocfilehash: 14a4da3ec3f06dfb573ef7e9422bdd6b751db636
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="63af1-102">Lync Server 2013 の正常性構成</span><span class="sxs-lookup"><span data-stu-id="63af1-102">Health configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63af1-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="63af1-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="63af1-104">さまざまな web サイト、Microsoft サポート技術情報の記事、Lync Server リソースキットツールの間に、Lync Server の実行時に問題が発生した管理者は、この問題を解決する方法についてはあまりありません。</span><span class="sxs-lookup"><span data-stu-id="63af1-104">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="63af1-105">Lync Server は、ネットワークのクラッシュやハードウェアの障害などのさまざまな要因によって影響を受ける可能性があるため、lync server 2013 で問題が発生しないことを保証する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="63af1-105">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="63af1-106">正常性の監視を実装することにより、管理者は問題を実際に解決する前に潜在的な問題を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="63af1-106">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="63af1-107">たとえば、管理者は Lync Server の監視を使用して、傾向と傾向を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="63af1-107">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="63af1-108">たとえば、音声/ビデオ会議の数が着実に増加した場合は、システムが過負荷になる前に容量を追加する必要があると考えられます。</span><span class="sxs-lookup"><span data-stu-id="63af1-108">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="63af1-109">同様に、管理者は、System Center Operations Manager を使って、特定のイベントが発生したときにリアルタイムの通知を発行したり、システムを事前にテストする代理トランザクションを実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="63af1-109">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="63af1-110">代理トランザクションは、ユーザーがシステムへのログオン、インスタントメッセージの交換、公衆交換電話網 (PSTN) 上にある電話への通話の発信などの一般的なタスクを正常に完了できることを確認するために、Lync Server で使用されます。</span><span class="sxs-lookup"><span data-stu-id="63af1-110">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="63af1-111">たとえば、これらのテストを定期的に実行することで、ユーザーが Lync Server にログオンする際に発生する可能性のある問題について通知したり、ユーザーからの通話が切断される前に問題を解決したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="63af1-111">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="63af1-112">System Center Operations Manager を使用してこれらの代理トランザクションを実行すると、管理者は毎日24時間いつでも Lync Server の展開を継続的に監視することができます。これは、アラートに応答する必要があります。発行されます。</span><span class="sxs-lookup"><span data-stu-id="63af1-112">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63af1-113">Lync Server 2013 の場合、System Center Operations Manager の管理パックは、Lync Server に悪影響を及ぼす可能性がある "外部" の問題を検出することもできます。</span><span class="sxs-lookup"><span data-stu-id="63af1-113">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="63af1-114">たとえば、インターネットインフォメーションサービス (IIS) がオフラインになった場合、または Lync Server コンピューターのシステムリソースが指定した容量未満になった場合、または Lync Server コンピューターでハードウェア障害が発生した場合に、管理者に通知することができます。</span><span class="sxs-lookup"><span data-stu-id="63af1-114">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="63af1-115">Lync Server 2013 の正常性構成は、System Center Operations Manager と Lync Server 管理パックの使用に基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="63af1-115">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="63af1-116">これらの管理パックには、次のようなさまざまな新機能と強化機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="63af1-116">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="63af1-117">**どこからでもシナリオの可用性。**</span><span class="sxs-lookup"><span data-stu-id="63af1-117">**Scenario availability from any location.**</span></span> <span data-ttu-id="63af1-118">Lync Server 2010 管理パックには、代理トランザクションによるエンドユーザーシナリオの可用性の監視の概念が導入されています。</span><span class="sxs-lookup"><span data-stu-id="63af1-118">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="63af1-119">Lync Server 2013 では、これらのエージェントは、より多くの代理トランザクションを所有しており、社内の離れた場所から、社内の地理的な場所、支社のアプライアンス、および Lync Server 2010 に対して実行することができます。従来のエッジ展開に適用するための展開。</span><span class="sxs-lookup"><span data-stu-id="63af1-119">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="63af1-120">**代理トランザクションログ。**</span><span class="sxs-lookup"><span data-stu-id="63af1-120">**Synthetic transaction logs.**</span></span> <span data-ttu-id="63af1-121">代理トランザクションが失敗すると、管理者は HTML ログにアクセスして、失敗したものを特定できます。</span><span class="sxs-lookup"><span data-stu-id="63af1-121">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="63af1-122">これには、失敗したアクション、各操作の待機時間、テストを実行するために使用されたコマンドライン、検出されたエラーについての説明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="63af1-122">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="63af1-123">**通話の信頼性が向上しました。**</span><span class="sxs-lookup"><span data-stu-id="63af1-123">**Increased call reliability coverage.**</span></span> <span data-ttu-id="63af1-124">Lync Server 2010 管理パックでは、エンドユーザーの音声通話に影響する深刻な接続の問題を検出するために、通話信頼性のアラートが導入されました。</span><span class="sxs-lookup"><span data-stu-id="63af1-124">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="63af1-125">Lync Server 2013 管理パックは、ピアツーピアインスタントメッセージング (IM) とその他の基本的な会議機能の範囲を追加して、ノイズを減らしながら利用可能範囲を最大限に高めます。</span><span class="sxs-lookup"><span data-stu-id="63af1-125">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="63af1-126">**依存関係の監視。**</span><span class="sxs-lookup"><span data-stu-id="63af1-126">**Dependency monitoring.**</span></span> <span data-ttu-id="63af1-127">Lync Server のシナリオは、IIS がオフラインになっている、CPU とメモリのリソースが少ない、ディスクの問題など、さまざまな外部要因が原因で失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="63af1-127">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="63af1-128">新しい管理パックは、いくつかの重要な依存関係をチェックして、管理者が影響を把握できるようにします。</span><span class="sxs-lookup"><span data-stu-id="63af1-128">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="63af1-129">**レポート機能が強化されました。**</span><span class="sxs-lookup"><span data-stu-id="63af1-129">**Enhanced reporting.**</span></span> <span data-ttu-id="63af1-130">管理者がシナリオの可用性の見積もり、キャパシティの計画、問題が発生しているコンポーネントの確認に役立つ一連のレポート。</span><span class="sxs-lookup"><span data-stu-id="63af1-130">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="63af1-131">また、管理パックには、Lync Server の展開の正常性をリアルタイムで把握できるようにするために役立つさまざまな機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="63af1-131">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="63af1-132">以下の表に、これらの機能を示します。</span><span class="sxs-lookup"><span data-stu-id="63af1-132">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="63af1-133">管理パックの機能</span><span class="sxs-lookup"><span data-stu-id="63af1-133">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63af1-134">機能</span><span class="sxs-lookup"><span data-stu-id="63af1-134">Feature</span></span></th>
<th><span data-ttu-id="63af1-135">説明</span><span class="sxs-lookup"><span data-stu-id="63af1-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63af1-136">代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="63af1-136">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="63af1-137">エンドユーザーがサインイン、プレゼンス、IM、会議などのエンドユーザーシナリオを簡単に利用できるようにするために、さまざまな場所から実行できる Windows PowerShell コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="63af1-137">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63af1-138">信頼性の警告の呼び出し</span><span class="sxs-lookup"><span data-stu-id="63af1-138">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="63af1-139">通話の詳細記録 (CDR) のデータベースクエリ。</span><span class="sxs-lookup"><span data-stu-id="63af1-139">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="63af1-140">これらのレコードは、エンドユーザーが通話に接続できるかどうか、または通話が終了した理由を反映するために、フロントエンドサーバーによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="63af1-140">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="63af1-141">これらのクエリによって、ピアツーピア通話または基本的な会議機能のために、さまざまなエンドユーザーの接続に関する問題が発生したことを示す通知が生成されます。</span><span class="sxs-lookup"><span data-stu-id="63af1-141">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63af1-142">メディア品質の警告</span><span class="sxs-lookup"><span data-stu-id="63af1-142">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="63af1-143">各通話の終了時にクライアントによって発行された Quality of Experience (QoE) レポートを表示するデータベースクエリ。</span><span class="sxs-lookup"><span data-stu-id="63af1-143">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call.</span></span> <span data-ttu-id="63af1-144">これらのクエリによって、通話や会議中にユーザーのメディアの品質が低下する可能性があるシナリオを特定するための警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="63af1-144">These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences.</span></span> <span data-ttu-id="63af1-145">データは、パケット待ち時間や損失などの主要な指標に基づいて構築されます。また、通話品質に直接寄与することがわかっているメトリックもあります。</span><span class="sxs-lookup"><span data-stu-id="63af1-145">The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63af1-146">コンポーネントの正常性</span><span class="sxs-lookup"><span data-stu-id="63af1-146">Component Health</span></span></p></td>
<td><p><span data-ttu-id="63af1-147">個々のサーバーコンポーネントは、イベントログとパフォーマンスカウンターを使って警告を発生させます。</span><span class="sxs-lookup"><span data-stu-id="63af1-147">Individual server components raise alerts by using event logs and performance counters.</span></span> <span data-ttu-id="63af1-148">これらのアラートは、1つ以上のエンドユーザーシナリオに重大な影響を与える可能性がある障害条件を示します。</span><span class="sxs-lookup"><span data-stu-id="63af1-148">These alerts indicate failure conditions that can severely impact one or more end user scenarios.</span></span> <span data-ttu-id="63af1-149">また、これらのアラートは、実行されていないサービス、高エラー率、高メッセージ待ち時間、接続の問題など、他のさまざまな障害の状態を示すこともあります。</span><span class="sxs-lookup"><span data-stu-id="63af1-149">These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63af1-150">依存関係の正常性</span><span class="sxs-lookup"><span data-stu-id="63af1-150">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="63af1-151">障害は、さまざまな外的理由で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="63af1-151">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="63af1-152">管理パックは、IIS の可用性、サーバーとプロセスの CPU およびメモリ使用量、ディスクメトリックなど、重大な問題を示す可能性がある重大な外部依存関係のデータを監視および収集できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="63af1-152">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="63af1-153">システムによって発行される警告は、次の3つの一般的なカテゴリに分類されています。</span><span class="sxs-lookup"><span data-stu-id="63af1-153">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="63af1-154">**優先度の高い警告。**</span><span class="sxs-lookup"><span data-stu-id="63af1-154">**High-priority Alerts.**</span></span> <span data-ttu-id="63af1-155">これらのアラートは、大規模なユーザーのグループに対するサービスの停止の原因となる条件を示します。</span><span class="sxs-lookup"><span data-stu-id="63af1-155">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="63af1-156">たとえば、Lync Server 2013 には高可用性機能が組み込まれているため、単一コンピューターでのコンポーネントの失敗は優先度の高い警告ではありません。</span><span class="sxs-lookup"><span data-stu-id="63af1-156">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="63af1-157">代わりに、優先度の高いアラートは、夜間に管理者をウェイクアップするのに十分な重大な問題を表します。</span><span class="sxs-lookup"><span data-stu-id="63af1-157">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="63af1-158">代理トランザクションとオフラインサービス (たとえば、音声/ビデオ会議) によって検出された停止は、優先度の高いアラートとして評価されます。</span><span class="sxs-lookup"><span data-stu-id="63af1-158">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="63af1-159">**中程度の優先度の高い警告**。</span><span class="sxs-lookup"><span data-stu-id="63af1-159">**Medium-priority alerts.**.</span></span> <span data-ttu-id="63af1-160">これらのアラートは、ユーザーのサブセットに影響を与える、または通話品質の劣化を示す条件を示します。</span><span class="sxs-lookup"><span data-stu-id="63af1-160">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="63af1-161">これには、コンポーネントの障害、通話確立中の待ち時間、通話の音質の低下などの問題が含まれます。</span><span class="sxs-lookup"><span data-stu-id="63af1-161">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="63af1-162">このカテゴリの通知はステートフルであり、問題の現在の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="63af1-162">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="63af1-163">たとえば、通話の発信時刻が通知のしきい値を超えているとします。</span><span class="sxs-lookup"><span data-stu-id="63af1-163">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="63af1-164">発信時刻を正常に戻すと、これらのアラートは System Center Operations Manager で自動解決されます。</span><span class="sxs-lookup"><span data-stu-id="63af1-164">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="63af1-165">これらのアラートについては、管理者が同じ営業日に確認することになります。</span><span class="sxs-lookup"><span data-stu-id="63af1-165">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="63af1-166">**その他のアラート。**</span><span class="sxs-lookup"><span data-stu-id="63af1-166">**Other alerts.**</span></span> <span data-ttu-id="63af1-167">これは、特定のユーザーまたはユーザーのサブセットに影響を与える可能性のあるコンポーネントからの通知です。</span><span class="sxs-lookup"><span data-stu-id="63af1-167">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="63af1-168">たとえば、アドレス帳サービスが、特定のユーザーの Active Directory エントリを解析できなかった可能性があります。</span><span class="sxs-lookup"><span data-stu-id="63af1-168">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="63af1-169">これらのアラートには、時間があるときに管理者がアクセスできるという期待があります。</span><span class="sxs-lookup"><span data-stu-id="63af1-169">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="63af1-170">このセクション中</span><span class="sxs-lookup"><span data-stu-id="63af1-170">In This Section</span></span>

  - [<span data-ttu-id="63af1-171">System Center Operations Manager と連携するように Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="63af1-171">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="63af1-172">Lync Server 2013 での代理トランザクションに対するリッチログの使用</span><span class="sxs-lookup"><span data-stu-id="63af1-172">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="63af1-173">Lync Server 2013 の System Center Operations Manager データベースとして Microsoft SQL Server 2008 R2 を使用する</span><span class="sxs-lookup"><span data-stu-id="63af1-173">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

