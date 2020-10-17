---
title: 'Lync Server 2013: 容量と可用性の管理'
description: 'Lync Server 2013: 容量と可用性の管理。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d498649651f8cfbccc65f5b1b5f010025ac418e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565153"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="3307c-103">Lync Server 2013 での容量と可用性の管理</span><span class="sxs-lookup"><span data-stu-id="3307c-103">Capacity and availability management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3307c-104">_**トピックの最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="3307c-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="3307c-105">容量管理および可用性管理の目的は、システムパフォーマンスを測定および制御することです。</span><span class="sxs-lookup"><span data-stu-id="3307c-105">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="3307c-106">システムパフォーマンスを測定および制御できるように、容量管理および可用性管理の手順を実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3307c-106">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="3307c-107">ベースラインを設定し、傾向を調べるためにシステムを監視することによって、システムが利用可能かどうかと、予想される需要を処理できるかどうかを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="3307c-107">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="3307c-108">容量管理</span><span class="sxs-lookup"><span data-stu-id="3307c-108">Capacity management</span></span>

<span data-ttu-id="3307c-109">容量管理では、SLA で指定されている最小のパフォーマンスレベルを超えていることを保証するために、サービスのキャパシティの計画、サイズ変更、および制御を行います。</span><span class="sxs-lookup"><span data-stu-id="3307c-109">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="3307c-110">適切な容量管理によって、IT サービスを妥当なコストで提供できるようになり、Sla で定義されているパフォーマンスのレベルをクライアントで引き続き満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="3307c-110">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="3307c-111">これらの条件には、次のものを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3307c-111">These criteria can include the following:</span></span>

  - <span data-ttu-id="3307c-112">**システムの応答時間**    これは、システムが通常のアクションを実行するために実行する測定時間です。</span><span class="sxs-lookup"><span data-stu-id="3307c-112">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="3307c-113">例としては、音声ビデオサーバーの役割が音声ビデオのトラフィックを処理するために必要な時間、会議を作成して参加するクライアントに必要な時間、すべての監視クライアントでプレゼンスが更新されるまでの時間などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3307c-113">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="3307c-114">**ストレージ容量**    これは、コンテンツデータベース、バックアップデバイス、またはローカルドライブであるかどうかにかかわらず、ストレージシステムの容量です。</span><span class="sxs-lookup"><span data-stu-id="3307c-114">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="3307c-115">例としては、サイトごとに提供される記憶域の最大容量と、上書きされるまでにバックアップが保存される時間が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="3307c-115">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="3307c-116">容量を調整することは、多くの場合、ディスク容量やネットワーク帯域幅など、十分な数の物理リソースが利用可能であることを確認するためのものです。</span><span class="sxs-lookup"><span data-stu-id="3307c-116">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="3307c-117">次の表に、容量に関する問題の一般的な解決策を示します。</span><span class="sxs-lookup"><span data-stu-id="3307c-117">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="3307c-118">容量に関する問題の一般的な解決策</span><span class="sxs-lookup"><span data-stu-id="3307c-118">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3307c-119">問題</span><span class="sxs-lookup"><span data-stu-id="3307c-119">Issue</span></span></th>
<th><span data-ttu-id="3307c-120">考えられる解決策</span><span class="sxs-lookup"><span data-stu-id="3307c-120">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3307c-121">音声/ビデオのパフォーマンスが低いリモートユーザー</span><span class="sxs-lookup"><span data-stu-id="3307c-121">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="3307c-122">WAN リンクで適切な帯域幅が利用できるかどうかを確認し、QoS が有効で適切に構成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3307c-122">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="3307c-123">QoE データを確認します。</span><span class="sxs-lookup"><span data-stu-id="3307c-123">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3307c-124">Lync 環境の全体的な応答速度は遅くなります。</span><span class="sxs-lookup"><span data-stu-id="3307c-124">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="3307c-125">テストを実行して、既存のフロントエンドサーバーが負荷を処理できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3307c-125">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="3307c-126">必要に応じて、新しいフロントエンドサーバーを導入します。SQL データベースの応答時間を確認し、遅延の原因 (ディスク i/o の向上など) を修正します。</span><span class="sxs-lookup"><span data-stu-id="3307c-126">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3307c-127">詳細なトラブルシューティングについては、「Lync Server ネットワークガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3307c-127">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="3307c-128">容量はシステム構成の影響を受け、ネットワーク帯域幅などの物理リソースに依存します。</span><span class="sxs-lookup"><span data-stu-id="3307c-128">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="3307c-129">たとえば、Lync 環境が完全バックアップを毎晩実行するように構成されている場合は、エンドユーザーによる対話的なパフォーマンスへの影響を最小限に抑えるために注意を払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3307c-129">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="3307c-130">容量管理は、システムのキャパシティを許容できるレベルに保ち、次の問題に対処するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="3307c-130">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="3307c-131">要件の変更への対応**Reacting to changes in requirements**    システムまたは組織での変更に対応できるように容量の要件を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3307c-131">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="3307c-132">たとえば、環境でエンタープライズ Voip を実装することを決定した場合は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイの数と配置が非常に重要になります。</span><span class="sxs-lookup"><span data-stu-id="3307c-132">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="3307c-133">セッション開始プロトコル (SIP) トランキングまたは直接 SIP を使用している場合は、最適なエンタープライズ Voip パフォーマンスを提供するように設計全体が大幅に変更されます。</span><span class="sxs-lookup"><span data-stu-id="3307c-133">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="3307c-134">**今後の要件**     を予測する時間の経過とともに、一部の容量要件が予測できます。</span><span class="sxs-lookup"><span data-stu-id="3307c-134">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="3307c-135">傾向を追跡することで、アップグレードを事前に計画することができます。</span><span class="sxs-lookup"><span data-stu-id="3307c-135">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="3307c-136">たとえば、ベースラインを作成するには、さまざまな Lync サイト間で使用可能な帯域幅を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3307c-136">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="3307c-137">この基準によって、これらのリンクに帯域幅を追加する必要がある場合に、これらのリモートサイトのユーザー数が時間の経過と共に増加することを予測できます。</span><span class="sxs-lookup"><span data-stu-id="3307c-137">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="3307c-138">可用性管理</span><span class="sxs-lookup"><span data-stu-id="3307c-138">Availability management</span></span>

<span data-ttu-id="3307c-139">可用性管理とは、お客様が必要とする一貫した信頼できるサービスのレベルを、IT サービスの一貫したコストで確実に提供するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="3307c-139">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="3307c-140">可用性管理では、サービスの損失を最小限に抑え、サービスが失われた場合に適切なアクションを確実に実行します。</span><span class="sxs-lookup"><span data-stu-id="3307c-140">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="3307c-141">Lync 環境では、ユーザーがスケジュールされた会議に参加できるかどうかなど、エンタープライズ Voip サービスが利用可能かどうかを懸念することがあります。</span><span class="sxs-lookup"><span data-stu-id="3307c-141">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="3307c-142">SLA は、許容可能な頻度および停止の長さを定義し、システムが計画されたメンテナンスで利用できない場合に一定の期間有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3307c-142">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="3307c-143">システムの可用性についてのレポートを管理に提供する必要がある場合や、不足している空き時間の目標に関連する財務またはその他の罰則がある場合は、可用性データを記録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3307c-143">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="3307c-144">このような正式な要件がない場合でも、特定の期間内にシステムに障害が発生した頻度を少なくすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3307c-144">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="3307c-145">たとえば、過去12か月間のシステム可用性、および各障害からの回復にかかる時間。</span><span class="sxs-lookup"><span data-stu-id="3307c-145">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="3307c-146">この情報は、システム障害への対応のチームの有効性を測定および改善するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3307c-146">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="3307c-147">また、争議がある場合に役立つ情報を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="3307c-147">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="3307c-148">可用性に関連するメジャーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3307c-148">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="3307c-149">**可用性**    これは通常、ダウンしている時間と比較して、システムまたはサービスにアクセスできる時間として表現されます。</span><span class="sxs-lookup"><span data-stu-id="3307c-149">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="3307c-150">通常、パーセンテージで表されます。</span><span class="sxs-lookup"><span data-stu-id="3307c-150">It is typically expressed as a percentage.</span></span> <span data-ttu-id="3307c-151">(「3ナイン」または「ファイブナイン」への参照が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3307c-151">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="3307c-152">これらは、99.9% または99.999% の可用性を意味します。)</span><span class="sxs-lookup"><span data-stu-id="3307c-152">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="3307c-153">**信頼性**    これは、システムの障害が発生するまでの時間の測定値であり、平均 (または平均) 時間差 (MTBF) で表される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3307c-153">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="3307c-154">**修復時間**    これは、障害が発生した後にサービスを回復するためにかかる時間で、多くの場合、平均 (平均) 修復時間 (MTTR) として表現されます。</span><span class="sxs-lookup"><span data-stu-id="3307c-154">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="3307c-155">可用性、信頼性、および修復時間は、次のように関連しています。</span><span class="sxs-lookup"><span data-stu-id="3307c-155">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="3307c-156">**Availability = (mtbf – MTTR)/MTBF**    たとえば、サーバーが6か月の期間にわたって2回失敗し、平均で20分間利用できない場合、MTBF は3か90日で、MTTR は20分です。</span><span class="sxs-lookup"><span data-stu-id="3307c-156">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="3307c-157">そのため、可用性 = (90 日–20分)/90 日 = 99.985% です。</span><span class="sxs-lookup"><span data-stu-id="3307c-157">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="3307c-158">可用性管理とは、Sla で定義されているパラメーター内で可用性を最大化し、保持することを確認するプロセスのことです。</span><span class="sxs-lookup"><span data-stu-id="3307c-158">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="3307c-159">可用性管理には、次のプロセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3307c-159">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="3307c-160">**監視**    どのくらいの時間サービスを使用できないかを調べる。</span><span class="sxs-lookup"><span data-stu-id="3307c-160">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="3307c-161">**レポート**    可用性の図は、管理、ユーザー、および運用チームに定期的に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3307c-161">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="3307c-162">これらのレポートでは、傾向を強調表示し、よく行われる領域と注意が必要な領域を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3307c-162">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="3307c-163">このレポートは、Sla で設定されたターゲットに準拠していることを要約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3307c-163">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="3307c-164">**向上**    利用可能時間が Sla で定義されているターゲットを満たしていない場合、または可用性が向上していることが予測される場合は、可用性管理プロセスで改善手順を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3307c-164">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="3307c-165">これには、その他のチームと協力して、停止の理由を強調表示し、停止の繰り返しを防止するための是正措置を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3307c-165">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="3307c-166">容量と可用性の測定値は、Microsoft System Center Operations Manager (旧称 Microsoft Operations Manager) などの自動化ツールやスクリプトに最適な反復的なタスクです。これについては、このドキュメントで後述します。</span><span class="sxs-lookup"><span data-stu-id="3307c-166">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3307c-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="3307c-167">See Also</span></span>


[<span data-ttu-id="3307c-168">System Center Operations Manager を使用した Lync Server 2013 の監視</span><span class="sxs-lookup"><span data-stu-id="3307c-168">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

