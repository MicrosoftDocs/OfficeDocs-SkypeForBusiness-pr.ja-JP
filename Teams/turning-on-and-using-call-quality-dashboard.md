---
title: 通話品質ダッシュボードを有効にして使用する
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: '通話品質ダッシュボードをオンにして使用し、通話の品質に関する概要レポートを取得する方法について説明します。 '
ms.openlocfilehash: 25f141f30691700414c3a24e705c7d8b490fd265
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328355"
---
# <a name="turn-on-and-use-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="71f4c-103">Microsoft Teams および Skype for Business Online で通話品質ダッシュボードをオンにして使用する</span><span class="sxs-lookup"><span data-stu-id="71f4c-103">Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="71f4c-104">通話品質ダッシュボードを使って通話品質を監視できるように Office 365 組織を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="71f4c-105">通話品質ダッシュボード (CQD) は、Microsoft Teams と Skype for Business Online サービスを使って発信した通話の品質を把握するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-105">Call Quality Dashboard (CQD) provides insight into the quality of calls made using Microsoft Teams and Skype for Business Online services.</span></span> <span data-ttu-id="71f4c-106">このトピックでは、通話品質の問題をトラブルシューティングするために使用できるデータの収集を開始する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-106">This topic describes the steps to start collecting data you can use to troubleshoot call quality issues.</span></span>

<span data-ttu-id="71f4c-107">現在、CQD バージョン3と CQD バージョン2の両方を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-107">Currently, CQD version 3 and CQD version 2 are both available for use.</span></span> <span data-ttu-id="71f4c-108">CQD v3 は、で<span>https://cqd.teams.microsoft.com</span>入手できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-108">CQD v3 is available at <span>https://cqd.teams.microsoft.com</span>.</span></span> <span data-ttu-id="71f4c-109">Microsoft Teams 管理者の資格情報でログインします。</span><span class="sxs-lookup"><span data-stu-id="71f4c-109">Log in with your Microsoft Teams administrator credentials.</span></span>

## <a name="latest-changes-and-updates"></a><span data-ttu-id="71f4c-110">最新の変更と更新</span><span class="sxs-lookup"><span data-stu-id="71f4c-110">Latest changes and updates</span></span>

<span data-ttu-id="71f4c-111">CQD version 3 は、ほぼリアルタイムの CQD ダッシュボード (30 分間の待機時間) を提供し、エンドユーザーを特定できる情報 (EUII) を使用して、ユーザーレベルにズームインする機能を管理者に提供します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-111">CQD version 3 delivers a near real-time CQD dashboard (latency close to 30 minutes), and uses End User Identifiable Information (EUII), giving admins the ability to zoom in to the user level.</span></span> <span data-ttu-id="71f4c-112">また、次のような新しいシナリオをサポートするための対話式のレポートもあります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-112">There is also and report interactivity to support new scenarios such as:</span></span>

- <span data-ttu-id="71f4c-113">地域別の通話品質:</span><span class="sxs-lookup"><span data-stu-id="71f4c-113">Call Quality by Region:</span></span>
  - <span data-ttu-id="71f4c-114">日付順</span><span class="sxs-lookup"><span data-stu-id="71f4c-114">date-by-region</span></span>
  - <span data-ttu-id="71f4c-115">1時間ごとの集計</span><span class="sxs-lookup"><span data-stu-id="71f4c-115">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="71f4c-116">特定の場所</span><span class="sxs-lookup"><span data-stu-id="71f4c-116">specific locations</span></span>
  - <span data-ttu-id="71f4c-117">特定のサブネット</span><span class="sxs-lookup"><span data-stu-id="71f4c-117">specific subnet</span></span>
  - <span data-ttu-id="71f4c-118">影響を受けるユーザーまたはユーザー</span><span class="sxs-lookup"><span data-stu-id="71f4c-118">impacted user or users</span></span>

- <span data-ttu-id="71f4c-119">地域別の信頼性/障害への通話:</span><span class="sxs-lookup"><span data-stu-id="71f4c-119">Call Reliability/Failure by Region:</span></span>
  - <span data-ttu-id="71f4c-120">日付順</span><span class="sxs-lookup"><span data-stu-id="71f4c-120">date-by-region</span></span>
  - <span data-ttu-id="71f4c-121">1時間ごとの集計</span><span class="sxs-lookup"><span data-stu-id="71f4c-121">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="71f4c-122">特定の場所</span><span class="sxs-lookup"><span data-stu-id="71f4c-122">specific locations</span></span>
  - <span data-ttu-id="71f4c-123">特定のサブネット</span><span class="sxs-lookup"><span data-stu-id="71f4c-123">specific subnet</span></span>
  - <span data-ttu-id="71f4c-124">影響を受けるユーザーまたはユーザー</span><span class="sxs-lookup"><span data-stu-id="71f4c-124">impacted user or users</span></span>

- <span data-ttu-id="71f4c-125">地域によって通話 (RMC) を評価します。1か月ごとに、低い RMC 評価を提供しているユーザーを特定の場所に集約します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-125">Rate My Call (RMC) by Region: from month-by-region aggregated down to specific locations to users who provide low RMC ratings.</span></span> <span data-ttu-id="71f4c-126">CQD v3 には、その他のフィードバックも含まれています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-126">CQD v3 also includes verbatim feedback.</span></span>
- <span data-ttu-id="71f4c-127">ヘルプデスク: P2P の通話または会議の特定のユーザー、またはすべての参加者と通話の詳細について利用できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-127">Helpdesk: available for a specific user on P2P calls or Meetings, or for all participants and call details.</span></span> <span data-ttu-id="71f4c-128">ネットワークの場所、デバイス、またはファームウェアに基づいて、発生する可能性があるシステムの問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-128">Helps identify possible system issues based on network location, devices, or firmware.</span></span>  
- <span data-ttu-id="71f4c-129">[クライアントバージョン]: 各クライアントバージョンのセッションとユーザーの数を表示するか、各クライアントバージョンのユーザー名にドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="71f4c-129">Client Versions: View the Session and Users counts for each Client Version, or drill down to User names for each client version.</span></span> <span data-ttu-id="71f4c-130">製品とクライアントの種類の事前に構築されたフィルターによって、バージョンが特定のクライアントに焦点を当てていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-130">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>
- <span data-ttu-id="71f4c-131">エンドポイント: PC/Mac のメーカー/モデルにマップされているコンピューターのエンドポイントを表示します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-131">Endpoints: Shows Machine Endpoints mapped to Make/Model of the PC/Mac.</span></span> <span data-ttu-id="71f4c-132">メーカー別またはモデル別に集計された品質を示します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-132">Shows aggregated quality by Make/Model.</span></span> <span data-ttu-id="71f4c-133">マッピングデータは、データを作成する場合と同様にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-133">Mapping data is uploaded similar to Building data.</span></span>

<span data-ttu-id="71f4c-134">また、EUII access が利用できない場合、バージョン3は RBAC のサポートも提供します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-134">Version 3 also provides RBAC support, in case EUII access is not available.</span></span>  

<span data-ttu-id="71f4c-135">管理者は、CQD バージョン3を介して Skype for business Server 2019 (Skype for Business Online および Microsoft Teams だけではなく) を管理できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-135">An admin can manage Skype for Business Server 2019 (not just Skype for Business Online and Microsoft Teams) through CQD version 3.</span></span> <span data-ttu-id="71f4c-136">これには、ハイブリッド実装と Call Data Connector の使用が必要です。</span><span class="sxs-lookup"><span data-stu-id="71f4c-136">This requires a hybrid implementation and the use of Call Data Connector.</span></span> <span data-ttu-id="71f4c-137">詳細については、「[通話データコネクタを計画](/SkypeForBusiness/hybrid/plan-call-data-connector)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f4c-137">See [Plan Call Data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) for more information.</span></span>

<span data-ttu-id="71f4c-138">CQD バージョン2が追加されました:</span><span class="sxs-lookup"><span data-stu-id="71f4c-138">CQD version 2 added:</span></span>

- <span data-ttu-id="71f4c-139">Microsoft Teams および Skype for Business Online のデータ</span><span class="sxs-lookup"><span data-stu-id="71f4c-139">Data for Microsoft Teams and Skype for Business Online</span></span>
- <span data-ttu-id="71f4c-140">概要レポートには、すべてのデータ、Microsoft Teams データ、または Skype for Business Online のデータを選択するための製品フィルターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-140">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data</span></span>
- <span data-ttu-id="71f4c-141">ビデオと VBSS ストリーム品質分類ロジックが更新されました。</span><span class="sxs-lookup"><span data-stu-id="71f4c-141">Updated Video and VBSS stream quality classification logic.</span></span> <span data-ttu-id="71f4c-142">分類子定義については、「[通話品質ダッシュボードのストリームの分類」](stream-classification-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f4c-142">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the classifier definitions.</span></span>

<span data-ttu-id="71f4c-143">[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)の一覧については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f4c-143">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="71f4c-144">ダッシュボードの更新と変更に関する情報を表示するには、**適切なニュース**のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="71f4c-144">To see information about updates and changes to the dashboard,  click the link in the **Good news!**</span></span> <span data-ttu-id="71f4c-145">ダッシュボードに表示されたバナー。</span><span class="sxs-lookup"><span data-stu-id="71f4c-145">banner when it displays on the dashboard.</span></span>

<span data-ttu-id="71f4c-146">CQD バージョン1では、Skype for Business Server 2015 管理者が次の機能を提供しています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-146">CQD version 1 provided Skype for Business Server 2015 admins the following features:</span></span>

- <span data-ttu-id="71f4c-147">キャッシュされたレポートデータにアクセスしてすばやくアクセス</span><span class="sxs-lookup"><span data-stu-id="71f4c-147">Access to cached report data for fast access</span></span>
- <span data-ttu-id="71f4c-148">情報を共有および公開するためのレポートページへのディープリンク</span><span class="sxs-lookup"><span data-stu-id="71f4c-148">Deep links to report pages for sharing and publishing information</span></span>
- <span data-ttu-id="71f4c-149">合理化されたレポートの編集と作成、およびレポートの説明の編集可能なメタデータ</span><span class="sxs-lookup"><span data-stu-id="71f4c-149">Streamlined report editing and creation, and editable metadata for report descriptions</span></span>
- <span data-ttu-id="71f4c-150">カスタムダッシュボードで使用するために、プログラムによるキューブデータへのアクセスを提供する Web Api</span><span class="sxs-lookup"><span data-stu-id="71f4c-150">Web APIs that give programmatic access to the cube data for use in custom dashboards</span></span>

## <a name="cqd-near-real-time-nrt-data"></a><span data-ttu-id="71f4c-151">CQD (NRT) データのほぼリアルタイムのデータ</span><span class="sxs-lookup"><span data-stu-id="71f4c-151">CQD Near-Real-Time (NRT) Data</span></span>

<span data-ttu-id="71f4c-152">CQD v3 は、near リアルタイムデータフィードを利用します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-152">CQD v3 utilizes a near-real-time data feed.</span></span> <span data-ttu-id="71f4c-153">通話記録は、通話の終了後30分以内に CQD ポータルで利用できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-153">Call Records are available at the CQD portal within 30 minutes of the end of the call.</span></span> <span data-ttu-id="71f4c-154">NRT パイプラインからの通話レコードは、データセットから削除されるまで数ヶ月分しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="71f4c-154">Call Records from the NRT pipeline are only available for a few months before they are removed from the data set.</span></span> <span data-ttu-id="71f4c-155">CQD v3 は、v3 パイプラインの NRT データで現在の v2 パイプラインからデータを結合します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-155">CQD v3 merges data from the current v2 pipeline with NRT data from the v3 pipeline.</span></span> <span data-ttu-id="71f4c-156">アーカイブ期間のデータに対する v2 と v3 ポータルのクエリでは、同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-156">Queries on the v2 and v3 portals for the data from the Archival period produce the same results.</span></span> <span data-ttu-id="71f4c-157">NRT データと NRT データと PII 期間の V2 と v3 のデータクエリは、異なるものになります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-157">V2 and v3 data queries for the NRT Data and NRT Data + PII periods will be different.</span></span>

### <a name="piieuii-data"></a><span data-ttu-id="71f4c-158">PII/EUII データ</span><span class="sxs-lookup"><span data-stu-id="71f4c-158">PII/EUII Data</span></span>

<span data-ttu-id="71f4c-159">PII または EUII データは、v3 パイプラインからのみ取得されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-159">PII or EUII data only comes from the v3 pipeline.</span></span> <span data-ttu-id="71f4c-160">コンプライアンスのため、PII/EUII データは30日間のみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-160">Due to compliance reasons, PII/EUII data is only kept for 30 days.</span></span> <span data-ttu-id="71f4c-161">NRT データは、30日間のマークに交差するため、pii/EUII フィールドは消去され、その結果、PII が無料の NRT データになります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-161">As NRT data crosses the 30-day mark, the PII/EUII fields are cleared out, resulting in PII-free NRT data.</span></span> <span data-ttu-id="71f4c-162">PII/EUII フィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="71f4c-162">The PII/EUII fields are:</span></span>

- <span data-ttu-id="71f4c-163">完全な IP アドレス</span><span class="sxs-lookup"><span data-stu-id="71f4c-163">Full IP address</span></span>
- <span data-ttu-id="71f4c-164">メディアアクセス制御 (MAC) アドレス</span><span class="sxs-lookup"><span data-stu-id="71f4c-164">Media Access Control (MAC) Address</span></span>
- <span data-ttu-id="71f4c-165">基本サービスセット識別子 (BSSID)</span><span class="sxs-lookup"><span data-stu-id="71f4c-165">Basic Service Set identifier (BSSID)</span></span>
- <span data-ttu-id="71f4c-166">セッション開始プロトコル (SIP) URI (Skype for Business のみ)</span><span class="sxs-lookup"><span data-stu-id="71f4c-166">Session Initiation Protocol (SIP) URI (Skype for Business only)</span></span>
- <span data-ttu-id="71f4c-167">ユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="71f4c-167">User Principal Name (UPN)</span></span>
- <span data-ttu-id="71f4c-168">マシンのエンドポイント名</span><span class="sxs-lookup"><span data-stu-id="71f4c-168">Machine Endpoint Name</span></span>
- <span data-ttu-id="71f4c-169">ユーザーからのフィードバック</span><span class="sxs-lookup"><span data-stu-id="71f4c-169">User Verbatim Feedback</span></span>
- <span data-ttu-id="71f4c-170">オブジェクト ID (エンドポイントのユーザーの Active Directory オブジェクト ID)</span><span class="sxs-lookup"><span data-stu-id="71f4c-170">Object ID (the Active Directory object ID of the endpoint's user)</span></span>

### <a name="date-controls"></a><span data-ttu-id="71f4c-171">日付コントロール</span><span class="sxs-lookup"><span data-stu-id="71f4c-171">Date controls</span></span>

<span data-ttu-id="71f4c-172">CQD v3 では、次の新しいローリング傾向の種類が追加されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-172">CQD v3 adds the following new Rolling Trend types:</span></span>

- <span data-ttu-id="71f4c-173">5日</span><span class="sxs-lookup"><span data-stu-id="71f4c-173">5-day</span></span>
- <span data-ttu-id="71f4c-174">7日間</span><span class="sxs-lookup"><span data-stu-id="71f4c-174">7-day</span></span>
- <span data-ttu-id="71f4c-175">30日間</span><span class="sxs-lookup"><span data-stu-id="71f4c-175">30-day</span></span>
- <span data-ttu-id="71f4c-176">60日</span><span class="sxs-lookup"><span data-stu-id="71f4c-176">60-day</span></span>
- <span data-ttu-id="71f4c-177">90日</span><span class="sxs-lookup"><span data-stu-id="71f4c-177">90-day</span></span>

<span data-ttu-id="71f4c-178">URL Date パラメーターで Day フィールドを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="71f4c-178">The URL Date parameter can now accept a Day field.</span></span> <span data-ttu-id="71f4c-179">ローリングレポートでは、トレンドの最終日として YYYY-MM-DD 形式の日付が使用されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-179">Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend.</span></span>  <span data-ttu-id="71f4c-180">URL Date パラメーター "00" は "today" を示します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-180">The URL Date parameter “00”  indicates “today”.</span></span>

|<span data-ttu-id="71f4c-181">URL</span><span class="sxs-lookup"><span data-stu-id="71f4c-181">URL</span></span>| <span data-ttu-id="71f4c-182">ローリング日のトレンドの終了日</span><span class="sxs-lookup"><span data-stu-id="71f4c-182">End date of Rolling Day Trend</span></span>|
|:---|:---|
|<span data-ttu-id="71f4c-183"><span>https://<cqdv3>/spd/#/ダッシュボード/<reportid>/2019-02/</span></span><span class="sxs-lookup"><span data-stu-id="71f4c-183"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02/</span></span></span>   |<span data-ttu-id="71f4c-184">2019年2月の現在の日付</span><span class="sxs-lookup"><span data-stu-id="71f4c-184">Current Day of Feb 2019</span></span>|
|<span data-ttu-id="71f4c-185"><span>https://<cqdv3>/spd/#/ダッシュボード/<reportid>/2019-02-15/</span></span><span class="sxs-lookup"><span data-stu-id="71f4c-185"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02-15/</span></span></span>|<span data-ttu-id="71f4c-186">2019年2月15日</span><span class="sxs-lookup"><span data-stu-id="71f4c-186">Feb 15, 2019</span></span>|
|<span data-ttu-id="71f4c-187"><span>https://<cqdv3>/spd/#/ダッシュボード/<reportid>/00/</span></span><span class="sxs-lookup"><span data-stu-id="71f4c-187"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/00/</span></span></span>        |<span data-ttu-id="71f4c-188">現在の日付</span><span class="sxs-lookup"><span data-stu-id="71f4c-188">Current Day</span></span>|
|||

<span data-ttu-id="71f4c-189">既定では、月の現在の日付が、ローリング日の傾向の最終日として使用されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-189">By default the current day of the month is used as the last day of the Rolling Day Trend.</span></span>

### <a name="drill-thru-functionality"></a><span data-ttu-id="71f4c-190">ドリルスルー機能</span><span class="sxs-lookup"><span data-stu-id="71f4c-190">Drill Thru Functionality</span></span>

<span data-ttu-id="71f4c-191">CQD v3 は、SPD レポートでのドリルスルーまたはドリルダウンフィールドの使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-191">CQD v3 supports the use of drill through or drill-down fields in SPD reports.</span></span> <span data-ttu-id="71f4c-192">これらのディメンションフィールドが選択されている場合、レポートは自動的に別の [レポート] タブを開き、選択した値に基づいてフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-192">If these dimension fields are selected,  the report automatically opens a different report tab and filters on the selected value.</span></span> <span data-ttu-id="71f4c-193">ドリルスルーフィルターが割り当てられているフィールドは、マウスをポイントしたときに別のカーソルアイコン (ポインター) によって区別されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-193">Fields with an assigned drill through filter are distinguished by a different cursor icon (the pointer) when you hover over them.</span></span>

<span data-ttu-id="71f4c-194">ドリルスルーフィールドが選択されると、ダッシュボードは自動的に新しい指定されたタブに移動し、選択した値のフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-194">When a drill through field is selected, the Dashboard automatically navigates to the new, specified tab and applies a filter with the selected value.</span></span> <span data-ttu-id="71f4c-195">そのタブに独自のドリルスルーフィールドがあり、1つが選択されている場合は、前のドリルスルーフィルターと新しいフィルターがすべて順に伝達されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-195">If that tab has its own drill through fields and one is selected, the previous drill through filters and the new one all propagate forward.</span></span> <span data-ttu-id="71f4c-196">これにより、結果として得られたデータセットを段階的に絞り込むレポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-196">This allows you to build a report that progressively narrows the resulting data set.</span></span>

<span data-ttu-id="71f4c-197">たとえば、通話品質ドリルスルーレポートでは、ユーザーは "ドリルスルー" の日付をクリックすると、[場所] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-197">For example, in a Call quality drill-through report, a user can click the date they would like to 'drill-through', which leads to the Location tab.</span></span>

    ![Screenshot: shows the drill thru report](media/CQD-drill-thru-report.png)

<span data-ttu-id="71f4c-198">[場所] タブでは、複数の日付を追加できます。たとえば、2019-09-22 を日付に追加します。 2019-09-24:</span><span class="sxs-lookup"><span data-stu-id="71f4c-198">You can add multiple dates from the location tab, such as adding 2019-09-22 to Date: 2019-09-24:</span></span> 

    ![Screenshot: add a date to the drill thru report](media/CQD-add-date.png)

> [!NOTE]
> <span data-ttu-id="71f4c-199">最後のタブに直接ジャンプしないでください。前のドリルスルーで選択したフィルターがないと、結果が大きすぎてテーブルに表示されません。</span><span class="sxs-lookup"><span data-stu-id="71f4c-199">Don't jump directly to the last tab. Without filters selected from a previous drill-through the results would be too large to show on a table.</span></span>

## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="71f4c-200">Microsoft 通話品質ダッシュボード (CQD) の概要レポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="71f4c-200">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="71f4c-201">CQD の使用を開始する前に、次のようにして Office 365 組織に対してライセンス認証を行います。</span><span class="sxs-lookup"><span data-stu-id="71f4c-201">Before you can start using CQD, activate it for your Office 365 organization as follows:</span></span>

<span data-ttu-id="71f4c-202">![](media/teams-logo-30x30.png) **Microsoft teams 管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="71f4c-202">![An icon that shows the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="71f4c-203">Microsoft Teams service 管理者アカウントを使用して Office 365 組織にサインインし、[**管理者**] タイルを選んで管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-203">Sign in to your Office 365 organization using Microsoft Teams service admin account, and then select the **Admin** tile to open the Admin center.</span></span>
2. <span data-ttu-id="71f4c-204">左側のウィンドウの [**管理センター**] で、[ **microsoft teams** ] を選択して、microsoft teams 管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-204">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
3. <span data-ttu-id="71f4c-205">Microsoft Teams 管理センターで、左側のウィンドウの [**通話品質ダッシュボード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-205">In the Microsoft Teams admin center, select **Call quality dashboard** in the left pane.</span></span>
4. <span data-ttu-id="71f4c-206">Https:// \(<span><span/>cqd.teams.microsoft.com\)が開かれるページで、[**サインイン**] をクリックして、グローバル管理者アカウントまたは microsoft teams サービス管理者アカウント情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-206">On the page that opens \(https://<span>cqd.teams.microsoft.com<span/>\), click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Admin account information.</span></span>

    ![スクリーンショット: 資格情報のプロンプトが表示されます](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="71f4c-208">サインインすると、CQD によってデータの収集と処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-208">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>  
> [!NOTE]
> <span data-ttu-id="71f4c-209">レポートに意味のある結果を表示するために十分なデータの処理には、1時間以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-209">It may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="71f4c-210">![Skype for business の](media/sfb-logo-30x30.png) **レガシポータルを使用し**た skype for business ロゴのアイコン</span><span class="sxs-lookup"><span data-stu-id="71f4c-210">![An icon of the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business legacy portal**</span></span>

1. <span data-ttu-id="71f4c-211">管理者アカウントを使用して Office 365 組織にサインインし、[**管理者**] タイルを選んで管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-211">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
2. <span data-ttu-id="71f4c-212">左側のウィンドウの [**管理センター**] で、[ **microsoft teams** ] を選択して、microsoft teams 管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-212">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
3. <span data-ttu-id="71f4c-213">Microsoft Teams 管理センターで、左側のウィンドウで [**従来のポータル**] を選び、[**ツール**]、[ **Skype For business Online 通話品質ダッシュボード**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-213">In the Microsoft Teams admin center, select **Legacy Portal** in the left pane, select **Tools**, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>

     ![スクリーンショット: 通話品質ダッシュボードを選択します。](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. <span data-ttu-id="71f4c-215">表示されたページで、グローバル管理者アカウントでサインインし、メッセージが表示されたらアカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-215">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>

<span data-ttu-id="71f4c-216">サインインすると、アクティブ化されると、通話品質ダッシュボードでデータの収集と処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-216">After you sign in, once activated, the Call Quality Dashboard will begin collecting and processing data.</span></span>

## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="71f4c-217">Microsoft Teams および Skype for Business Online の通話品質ダッシュボードの機能</span><span class="sxs-lookup"><span data-stu-id="71f4c-217">Features of the Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="71f4c-218"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="71f4c-218"></span></span>

<!-- Siunies, this isn't very clear, it doesn't call out v1 and v2. unsure how to elaborate for v3, please comment -->
<span data-ttu-id="71f4c-219">CQD の概要レポートには、詳細レポート用に計画されている機能のサブセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-219">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="71f4c-220">各エディションの違いは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="71f4c-220">The differences between the editions are summarized here:</span></span>
  
|<span data-ttu-id="71f4c-221">機能</span><span class="sxs-lookup"><span data-stu-id="71f4c-221">Feature</span></span>|<span data-ttu-id="71f4c-222">概要レポート</span><span class="sxs-lookup"><span data-stu-id="71f4c-222">Summary Reports</span></span>|<span data-ttu-id="71f4c-223">詳細レポート</span><span class="sxs-lookup"><span data-stu-id="71f4c-223">Detailed Reports</span></span>|
|:--- |:--- |:--- |
|<span data-ttu-id="71f4c-224">アプリケーション共有のメトリック</span><span class="sxs-lookup"><span data-stu-id="71f4c-224">Application sharing metric</span></span> | <span data-ttu-id="71f4c-225">いいえ</span><span class="sxs-lookup"><span data-stu-id="71f4c-225">No</span></span> | <span data-ttu-id="71f4c-226">はい</span><span class="sxs-lookup"><span data-stu-id="71f4c-226">Yes</span></span> |
|<span data-ttu-id="71f4c-227">顧客の建物情報のサポート</span><span class="sxs-lookup"><span data-stu-id="71f4c-227">Customer building information support</span></span> | <span data-ttu-id="71f4c-228">はい</span><span class="sxs-lookup"><span data-stu-id="71f4c-228">Yes</span></span> | <span data-ttu-id="71f4c-229">可</span><span class="sxs-lookup"><span data-stu-id="71f4c-229">Yes</span></span> |
|<span data-ttu-id="71f4c-230">顧客エンドポイント情報のサポート</span><span class="sxs-lookup"><span data-stu-id="71f4c-230">Customer endpoint information support</span></span> | <span data-ttu-id="71f4c-231"><span>Cqd.teams.microsoft.com のみ<span/></span><span class="sxs-lookup"><span data-stu-id="71f4c-231">Only in <span>cqd.teams.microsoft.com<span/></span></span> | <span data-ttu-id="71f4c-232"><span>Cqd.teams.microsoft.com のみ<span/></span><span class="sxs-lookup"><span data-stu-id="71f4c-232">Only in <span>cqd.teams.microsoft.com<span/></span></span> |
|<span data-ttu-id="71f4c-233">ドリルダウン分析のサポート</span><span class="sxs-lookup"><span data-stu-id="71f4c-233">Drill down analysis support</span></span>   | <span data-ttu-id="71f4c-234">いいえ</span><span class="sxs-lookup"><span data-stu-id="71f4c-234">No</span></span>   | <span data-ttu-id="71f4c-235">はい</span><span class="sxs-lookup"><span data-stu-id="71f4c-235">Yes</span></span>   |
|<span data-ttu-id="71f4c-236">メディアの信頼性のメトリック</span><span class="sxs-lookup"><span data-stu-id="71f4c-236">Media reliability metrics</span></span>   | <span data-ttu-id="71f4c-237">いいえ</span><span class="sxs-lookup"><span data-stu-id="71f4c-237">No</span></span>   | <span data-ttu-id="71f4c-238">はい</span><span class="sxs-lookup"><span data-stu-id="71f4c-238">Yes</span></span>   |
|<span data-ttu-id="71f4c-239">ボックスのないレポート</span><span class="sxs-lookup"><span data-stu-id="71f4c-239">Out-of-the-box reports</span></span>   | <span data-ttu-id="71f4c-240">はい</span><span class="sxs-lookup"><span data-stu-id="71f4c-240">Yes</span></span>   | <span data-ttu-id="71f4c-241">可</span><span class="sxs-lookup"><span data-stu-id="71f4c-241">Yes</span></span>   |
|<span data-ttu-id="71f4c-242">概要レポート</span><span class="sxs-lookup"><span data-stu-id="71f4c-242">Overview reports</span></span>   | <span data-ttu-id="71f4c-243">はい</span><span class="sxs-lookup"><span data-stu-id="71f4c-243">Yes</span></span>   | <span data-ttu-id="71f4c-244">可</span><span class="sxs-lookup"><span data-stu-id="71f4c-244">Yes</span></span>   |
|<span data-ttu-id="71f4c-245">ユーザーごとのレポートセット</span><span class="sxs-lookup"><span data-stu-id="71f4c-245">Per-user report set</span></span>   | <span data-ttu-id="71f4c-246">いいえ</span><span class="sxs-lookup"><span data-stu-id="71f4c-246">No</span></span>   | <span data-ttu-id="71f4c-247">はい</span><span class="sxs-lookup"><span data-stu-id="71f4c-247">Yes</span></span>   |
|<span data-ttu-id="71f4c-248">レポートセットのカスタマイズ (レポートの追加、削除、変更)</span><span class="sxs-lookup"><span data-stu-id="71f4c-248">Report set customization (add, delete, modify reports)</span></span>   | <span data-ttu-id="71f4c-249">いいえ</span><span class="sxs-lookup"><span data-stu-id="71f4c-249">No</span></span>   | <span data-ttu-id="71f4c-250">はい</span><span class="sxs-lookup"><span data-stu-id="71f4c-250">Yes</span></span>   |
|<span data-ttu-id="71f4c-251">ビデオベースの画面共有のメトリック</span><span class="sxs-lookup"><span data-stu-id="71f4c-251">Video-based screen sharing metrics</span></span>   | <span data-ttu-id="71f4c-252">いいえ</span><span class="sxs-lookup"><span data-stu-id="71f4c-252">No</span></span>   | <span data-ttu-id="71f4c-253">はい</span><span class="sxs-lookup"><span data-stu-id="71f4c-253">Yes</span></span>   |
|<span data-ttu-id="71f4c-254">ビデオ指標</span><span class="sxs-lookup"><span data-stu-id="71f4c-254">Video metrics</span></span>   | <span data-ttu-id="71f4c-255">いいえ</span><span class="sxs-lookup"><span data-stu-id="71f4c-255">No</span></span>   | <span data-ttu-id="71f4c-256">はい</span><span class="sxs-lookup"><span data-stu-id="71f4c-256">Yes</span></span>   |
|<span data-ttu-id="71f4c-257">利用可能なデータの量</span><span class="sxs-lookup"><span data-stu-id="71f4c-257">Amount of data available</span></span>   | <span data-ttu-id="71f4c-258">過去6ヶ月</span><span class="sxs-lookup"><span data-stu-id="71f4c-258">Last 6 months</span></span>   | <span data-ttu-id="71f4c-259">過去6ヶ月</span><span class="sxs-lookup"><span data-stu-id="71f4c-259">Last 6 months</span></span>   |
|<span data-ttu-id="71f4c-260">Microsoft Teams データ</span><span class="sxs-lookup"><span data-stu-id="71f4c-260">Microsoft Teams data</span></span>   | <span data-ttu-id="71f4c-261">はい</span><span class="sxs-lookup"><span data-stu-id="71f4c-261">Yes</span></span>   | <span data-ttu-id="71f4c-262">可</span><span class="sxs-lookup"><span data-stu-id="71f4c-262">Yes</span></span>   |
| | | |

### <a name="out-of-the-box-reports"></a><span data-ttu-id="71f4c-263">ボックスのないレポート</span><span class="sxs-lookup"><span data-stu-id="71f4c-263">Out-of-the-box reports</span></span>

<span data-ttu-id="71f4c-264">CQD のすべてのエディションでは、新しいレポートを作成することなく、品質指標を呼び出すことができるエクスペリエンスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-264">All editions of CQD provide an experience that gives you call quality metrics without the need to create new reports.</span></span> <span data-ttu-id="71f4c-265">バックエンドでデータが処理されると、レポートに通話品質データが表示されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-265">Once data is processed in the back-end, you see call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="71f4c-266">概要レポート</span><span class="sxs-lookup"><span data-stu-id="71f4c-266">Overview reports</span></span>

<span data-ttu-id="71f4c-267">CQD のすべてのエディションでは、全体的な通話品質情報への上位レベルのエントリポイントが提供されますが、概要レポートでは情報の表示方法は詳細レポートとは異なります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-267">All editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from Detailed Reports.</span></span>  
  
<span data-ttu-id="71f4c-268">概要レポートには、シンプルなタブ表示のページレポートビューが用意されているので、全体的な通話品質の状態と傾向を簡単に参照して理解できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-268">Summary Reports provide a simplified tabbed page report view so you can quickly browse and understand the overall call quality status and trends.</span></span>

<span data-ttu-id="71f4c-269">次の4つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-269">The four tabs include:</span></span>
  
- <span data-ttu-id="71f4c-270">**全体的な通話品質**: すべてのストリームに関する情報を提供します。これは、毎月および1日の傾向を示す集計です。</span><span class="sxs-lookup"><span data-stu-id="71f4c-270">**Overall Call Quality** — provides information about all streams, which is an aggregation that shows monthly and daily trends for:</span></span>
  - <span data-ttu-id="71f4c-271">サーバークライアントストリーム</span><span class="sxs-lookup"><span data-stu-id="71f4c-271">Server-Client streams</span></span>
  - <span data-ttu-id="71f4c-272">クライアントクライアントストリーム</span><span class="sxs-lookup"><span data-stu-id="71f4c-272">Client-Client streams</span></span>
  - <span data-ttu-id="71f4c-273">個別のサーバークライアントとクライアント間のクライアントストリーム</span><span class="sxs-lookup"><span data-stu-id="71f4c-273">Separate Server-Client and Client-Client streams</span></span>
- <span data-ttu-id="71f4c-274">[**サーバー] — [クライアント**]-サーバーエンドポイントとクライアントエンドポイント間のストリームの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-274">**Server—Client** — provides details for the streams between Server and Client endpoints.</span></span>
- <span data-ttu-id="71f4c-275">**クライアント**-クライアント: 2 つのクライアントエンドポイント間のストリームの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-275">**Client—Client** — provides details for the streams between two Client endpoints.</span></span>
- <span data-ttu-id="71f4c-276">[**音声品質の sla** : Skype For business Online の音声品質の sla に含まれる通話に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-276">**Voice Quality SLA** — provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>

> [!NOTE]
> <span data-ttu-id="71f4c-277">CQD バージョン3は、Microsoft Teams、Skype for Business Online、Skype for Business Server と連携しています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-277">CQD Version 3 works with Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span> <span data-ttu-id="71f4c-278">Skype for Business Server 2019 で CQD を使用するには、[通話データコネクタを構成](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-278">To use CQD with Skype for Business Server 2019, you will have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="71f4c-279">始める前に「[通話データコネクタを計画](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/plan-call-data-connector)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f4c-279">See [Plan Call Data Connector](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>

- <span data-ttu-id="71f4c-280">地域別の通話品質:</span><span class="sxs-lookup"><span data-stu-id="71f4c-280">Call Quality by Region:</span></span>

  - <span data-ttu-id="71f4c-281">日付順</span><span class="sxs-lookup"><span data-stu-id="71f4c-281">date-by-region</span></span>
  - <span data-ttu-id="71f4c-282">1時間ごとの集計</span><span class="sxs-lookup"><span data-stu-id="71f4c-282">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="71f4c-283">特定の場所</span><span class="sxs-lookup"><span data-stu-id="71f4c-283">specific locations</span></span>
  - <span data-ttu-id="71f4c-284">特定のサブネット</span><span class="sxs-lookup"><span data-stu-id="71f4c-284">specific subnet</span></span>
  - <span data-ttu-id="71f4c-285">影響を受けるユーザーまたはユーザー</span><span class="sxs-lookup"><span data-stu-id="71f4c-285">impacted user or users</span></span>

- <span data-ttu-id="71f4c-286">地域別の信頼性/障害への通話:</span><span class="sxs-lookup"><span data-stu-id="71f4c-286">Call Reliability/Failure by Region:</span></span>
  - <span data-ttu-id="71f4c-287">日付順</span><span class="sxs-lookup"><span data-stu-id="71f4c-287">date-by-region</span></span>
  - <span data-ttu-id="71f4c-288">1時間ごとの集計</span><span class="sxs-lookup"><span data-stu-id="71f4c-288">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="71f4c-289">特定の場所</span><span class="sxs-lookup"><span data-stu-id="71f4c-289">specific locations</span></span>
  - <span data-ttu-id="71f4c-290">特定のサブネット</span><span class="sxs-lookup"><span data-stu-id="71f4c-290">specific subnet</span></span>
  - <span data-ttu-id="71f4c-291">影響を受けるユーザーまたはユーザー</span><span class="sxs-lookup"><span data-stu-id="71f4c-291">impacted user or users</span></span>

- <span data-ttu-id="71f4c-292">地域によって通話 (RMC) を評価します。1か月ごとに、低い RMC 評価を提供しているユーザーを特定の場所に集約します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-292">Rate My Call (RMC) by Region: from month-by-region aggregated down to specific locations to users who provide low RMC ratings.</span></span> <span data-ttu-id="71f4c-293">CQD v3 には、その他のフィードバックも含まれています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-293">CQD v3 also includes verbatim feedback.</span></span>
- <span data-ttu-id="71f4c-294">ヘルプデスク: P2P の通話または会議の特定のユーザー、またはすべての参加者と通話の詳細について利用できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-294">Helpdesk: available for a specific user on P2P calls or Meetings, or for all participants and call details.</span></span> <span data-ttu-id="71f4c-295">ネットワークの場所、デバイス、またはファームウェアに基づいて、発生する可能性があるシステムの問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-295">Helps identify possible system issues based on network location, devices, or firmware.</span></span>  
- <span data-ttu-id="71f4c-296">[クライアントバージョン]: 各クライアントバージョンのセッションとユーザーの数を表示するか、各クライアントバージョンのユーザー名にドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="71f4c-296">Client Versions: View the Session and Users counts for each Client Version, or drill down to User names for each client version.</span></span> <span data-ttu-id="71f4c-297">製品とクライアントの種類の事前に構築されたフィルターによって、バージョンが特定のクライアントに焦点を当てていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-297">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>
- <span data-ttu-id="71f4c-298">エンドポイント: PC/Mac のメーカー/モデルにマップされているコンピューターのエンドポイントを表示します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-298">Endpoints: Shows Machine Endpoints mapped to Make/Model of the PC/Mac.</span></span> <span data-ttu-id="71f4c-299">メーカー別またはモデル別に集計された品質を示します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-299">Shows aggregated quality by Make/Model.</span></span> <span data-ttu-id="71f4c-300">マッピングデータは、データを作成する場合と同様にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-300">Mapping data is uploaded similar to Building data.</span></span>

### <a name="overall-call-quality-tab"></a><span data-ttu-id="71f4c-301">[全体的な通話品質] タブ</span><span class="sxs-lookup"><span data-stu-id="71f4c-301">Overall Call Quality tab</span></span>

<span data-ttu-id="71f4c-302">このタブのデータを使用して、通話品質の状態と、ストリーミングカウントと低い割合に基づいた傾向を評価します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-302">Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages.</span></span> <span data-ttu-id="71f4c-303">右上隅の凡例は、どの色と視覚要素がこれらのメトリックを表しているかを示しています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-303">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![スクリーンショット: [通話品質] タブを表示する](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="71f4c-305">ストリームは、良好、低品質、未分類の3つのグループに分類されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-305">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="71f4c-306">また、分類されたストリームの合計数に*低品質*として分類されたストリームの比率を示す*低品質*の値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-306">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="71f4c-307">*低品質のストリーム/(不十分なストリーム + 良好なストリーム) \* 100\*\*は、* 複数の*未分類*ストリームの存在によって影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="71f4c-307">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*, the *Poor %*  is unaffected by the presence of multiple *Unclassified*  streams.</span></span> <span data-ttu-id="71f4c-308">ストリームを低品質または良好な状態として分類する方法については、「[通話品質ダッシュボードでのストリームの分類」](stream-classification-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f4c-308">To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="71f4c-309">ストリーム数の値を測定するには、左側のスケールを使用します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-309">Use the scale on the left to measure the stream count values.</span></span>
  
![スクリーンショット: ストリームカウント値の表示](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="71f4c-311">右側のスケールを使用して、低品質の値を測定します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-311">Use the scale on the right to measure the Poor % values.</span></span>
  
![スクリーンショット: 低品質の値が表示されます](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="71f4c-313">また、バーの上にマウスを置くと、実際の数値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-313">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="71f4c-314">次の例は、非常に小さなサンプルデータセットからの値で、実際の展開には現実的ではありません。</span><span class="sxs-lookup"><span data-stu-id="71f4c-314">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span>
  
![スクリーンショット: データへのアクセスに使用されたマウスの表示](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="71f4c-316">全体的なストリームボリュームは、計算された低品質の割合の関連性を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-316">The overall stream volume helps determine how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="71f4c-317">全体的なストリームの量が少ないほど、報告される低割合の値は、信頼性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-317">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="71f4c-318">[サーバー-クライアント] タブと [クライアント-クライアント] タブ</span><span class="sxs-lookup"><span data-stu-id="71f4c-318">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="71f4c-319">次の2つのタブは、エンドポイント間のシナリオで発生したストリームの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-319">These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="71f4c-320">[サーバー-クライアント] タブには、メディアストリームが流れる4つのシナリオを表す4つの折りたたみ可能なセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-320">The Server-Client tab has four collapsible sections  that represent four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="71f4c-321">有線 (内部)</span><span class="sxs-lookup"><span data-stu-id="71f4c-321">Wired Inside</span></span>
- <span data-ttu-id="71f4c-322">有線 (外部)</span><span class="sxs-lookup"><span data-stu-id="71f4c-322">Wired Outside</span></span>
- <span data-ttu-id="71f4c-323">Wifi (内部)</span><span class="sxs-lookup"><span data-stu-id="71f4c-323">Wifi Inside</span></span>
- <span data-ttu-id="71f4c-324">Wifi (外部)</span><span class="sxs-lookup"><span data-stu-id="71f4c-324">Wifi Outside</span></span>

<span data-ttu-id="71f4c-325">同様に、[クライアント-クライアント] タブには、5つの折りたたみ可能なセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-325">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="71f4c-326">有線 (内側)、有線</span><span class="sxs-lookup"><span data-stu-id="71f4c-326">Wired Inside — Wired Inside</span></span>
- <span data-ttu-id="71f4c-327">有線 (内部)-有線 (外部)</span><span class="sxs-lookup"><span data-stu-id="71f4c-327">Wired Inside — Wired Outside</span></span>
- <span data-ttu-id="71f4c-328">有線 (外部)-有線 (外部)</span><span class="sxs-lookup"><span data-stu-id="71f4c-328">Wired Outside — Wired Outside</span></span>
- <span data-ttu-id="71f4c-329">有線 (内部) — Wifi (内部)</span><span class="sxs-lookup"><span data-stu-id="71f4c-329">Wired Inside — Wifi Inside</span></span>
- <span data-ttu-id="71f4c-330">有線 (内部) — Wifi (外部)</span><span class="sxs-lookup"><span data-stu-id="71f4c-330">Wired Inside — Wifi Outside</span></span>

#### <a name="inside-test"></a><span data-ttu-id="71f4c-331">内部テスト</span><span class="sxs-lookup"><span data-stu-id="71f4c-331">Inside Test</span></span>

<span data-ttu-id="71f4c-332">処理中、CQD バックエンドは、構築情報を使用してストリームを*内部*または*外部*として分類します (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="71f4c-332">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="71f4c-333">各ストリームのエンドポイントは、サブネットアドレスと関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-333">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="71f4c-334">アップロードした建物情報の InsideCorp とマークされているサブネットの一覧にサブネットがある場合、そのサブネットは*内部*と見なされます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-334">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="71f4c-335">作成情報がまだアップロードされていない場合は、内側のテストでは常に*外部*としてストリームを分類します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-335">If Building information has not yet been uploaded, then Inside Test  always classifies the streams as *Outside*.</span></span>  

> [!NOTE]
> <span data-ttu-id="71f4c-336">サーバークライアントシナリオの内部テストでは、クライアントエンドポイントのみが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-336">The Inside Test for a Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="71f4c-337">サーバーは常にユーザーの視点から外れているため、これはテストでは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="71f4c-337">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="71f4c-338">有線と wifi の比較</span><span class="sxs-lookup"><span data-stu-id="71f4c-338">Wired vs. wifi</span></span>

<span data-ttu-id="71f4c-339">名前が示すように、分類条件は、クライアント接続の種類に基づいています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-339">As the names indicate, the classification criteria is based on the type of client connections.</span></span> <span data-ttu-id="71f4c-340">この場合も、サーバーは常に有線であり、計算に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="71f4c-340">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="71f4c-341">特定のストリームについて、2つのエンドポイントの一方が Wifi ネットワークに接続されていれば、CQD で Wifi として分類されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-341">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span>
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="71f4c-342">レポートで表示する製品データの選択</span><span class="sxs-lookup"><span data-stu-id="71f4c-342">Selecting product data to see in reports</span></span>

<a name="BKMKProductFilter"></a>

<span data-ttu-id="71f4c-343">概要と位置を拡張したレポートでは、[**製品フィルター** ] ドロップダウンを使用して、すべての製品データ、Microsoft Teams のデータのみ、または Skype For business Online データのみを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-343">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![スクリーンショット: 製品フィルターコントロールオプションを示します。](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="71f4c-345">詳細レポートで**は、Is Teams**ディメンションを使用して、Microsoft Teams または Skype For business Online データにデータをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-345">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data.</span></span>
  
## <a name="upload-tenant-data-information"></a><span data-ttu-id="71f4c-346">テナントデータ情報をアップロードする</span><span class="sxs-lookup"><span data-stu-id="71f4c-346">Upload Tenant Data information</span></span>

<a name="BKMKTenantDataInformationUpload"></a>

<span data-ttu-id="71f4c-347">CQD Summary レポートダッシュボードには、右上隅にある [設定] メニューから [**テナントデータ**アップロード] を選択することによってアクセスできる**テナントデータアップロード**ページが含まれています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-347">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="71f4c-348">このページは、管理者が次のような独自の情報をアップロードするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-348">This page is used for admins to upload their own information, such as:</span></span>

- <span data-ttu-id="71f4c-349">IP アドレスと地理的情報のマップ</span><span class="sxs-lookup"><span data-stu-id="71f4c-349">A map of IP address and geographical information</span></span>
- <span data-ttu-id="71f4c-350">各ワイヤレス AP とその MAC アドレスの地図</span><span class="sxs-lookup"><span data-stu-id="71f4c-350">A map of each wireless AP and its MAC address</span></span>
- <span data-ttu-id="71f4c-351">エンドポイントからエンドポイントの作成/モデル/型へのマップ。など</span><span class="sxs-lookup"><span data-stu-id="71f4c-351">A map of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
![スクリーンショット: 通話品質ダッシュボードのテナントデータが表示されます](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="71f4c-353">[**テナントデータのアップロード**] ページで、ドロップダウンメニューを使用してアップロードするデータファイルの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-353">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type to upload.</span></span> <span data-ttu-id="71f4c-354">ファイルのデータ型は、ファイルの内容を示します (たとえば、"建物" は、IP アドレスと建物およびその他の地理情報のマッピングを指します)。 "Endpoint" は、エンドポイントの名前とエンドポイントの型情報のマッピングを指します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-354">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building and other geographical information, “Endpoint” refers to mapping of Endpoint Name to Endpoint Make/Model/Type information).</span></span> <span data-ttu-id="71f4c-355">現在、CQD では、cqd.teams.microsoft.com (プレビューステージでは、まだ公式利用可能ではない) の "建物" と "Endpoint" データ型がサポートされています。 cqd.lync.com は、"建物" データ型のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-355">Currently CQD supports “Building” and “Endpoint” data types for cqd.teams.microsoft.com (in preview stage and not officially available yet), cqd.lync.com only supports the "Building" data type.</span></span>
2. <span data-ttu-id="71f4c-356">ファイルデータの種類を選んだら、[**参照**] をクリックしてデータファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-356">After you select the file data type, click **Browse** to choose a data file.</span></span>

   - <span data-ttu-id="71f4c-357">データファイルには、.tsv (タブ区切り値) ファイルまたは .csv (カンマ区切り値) ファイルを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-357">A data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="71f4c-358">.Csv ファイルでは、カンマが含まれているフィールドは引用符で囲む必要があります。または、コンマが削除されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-358">With a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="71f4c-359">たとえば、建物の名前が ny である場合は、.csv ファイルに "NY, NY" と入力します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-359">For example, if your building name is NY,NY,  enter  "NY,NY" in the .csv file.</span></span>
   - <span data-ttu-id="71f4c-360">データファイルのサイズは、50 MB 以下でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="71f4c-360">The data file must be no larger than 50 MB.</span></span>
   - <span data-ttu-id="71f4c-361">Cqd.teams.microsoft.com にアップロードされたファイルの行数の上限は100万で、クエリのパフォーマンスが速くなります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-361">Files uploaded to cqd.teams.microsoft.com have an expanded row limit of 1,000,000 to keep query performance fast.</span></span> <span data-ttu-id="71f4c-362">この制限は、CQD<span></span><span></span>の CQD v2 にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-362">This limit also applies to CQD v2  on cqd<span></span>.lync<span></span>.com.</span></span>
   - <span data-ttu-id="71f4c-363">データファイルの各列は、このトピックの後半で説明するように、定義済みのデータ型と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-363">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
3. <span data-ttu-id="71f4c-364">次に、**開始日**を指定し、必要に応じて**終了日を指定**します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-364">Next, specify a **Start date** and, optionally, **Specify an end date**.</span></span>
4. <span data-ttu-id="71f4c-365">最後に、[**アップロード**] を選んで、CQD サーバーにファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="71f4c-365">Finally, select **Upload** to upload the file to the CQD server.</span></span>
    <span data-ttu-id="71f4c-366">ファイルがアップロードされる前に、まず検証されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-366">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="71f4c-367">検証が完了すると、Azure blob に格納されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-367">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="71f4c-368">検証に失敗した場合、またはファイルが Azure blob に保存されていない場合、エラーメッセージによってファイルに修正を要求します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-368">If validation fails or the file fails to be stored in an Azure blob, an error message requests a correction to the file.</span></span> <span data-ttu-id="71f4c-369">次の図は、データファイルの列数が正しくないエラーの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-369">The following image shows a sample error with an incorrect number of columns in the data file.</span></span>

     ![スクリーンショット: アップロード検証エラーを示します。](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="71f4c-371">検証中にエラーが発生しなかった場合、ファイルのアップロードは成功します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-371">If no errors occur during validation, the file upload succeeds.</span></span> <span data-ttu-id="71f4c-372">アップロードされたデータファイルは、[**マイアップロード**] テーブルに表示できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-372">You can then see the uploaded data file in the **My uploads** table.</span></span> <span data-ttu-id="71f4c-373">このページの下部には、現在のテナントにアップロードされたすべてのファイルの一覧も表示されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-373">The bottom of that page also shows a full list of all files uploaded for the current tenant.</span></span>
    <span data-ttu-id="71f4c-374">各レコードには、アップロードされたテナントデータファイルが1つ表示されます。これには、ファイルの種類、最終更新時刻、[期間]、[説明]、[削除] アイコン、ダウンロードアイコンがあります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-374">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="71f4c-375">ファイルを削除するには、表のゴミ箱アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-375">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="71f4c-376">ファイルをダウンロードするには、表の [**ダウンロード**] 列の [ダウンロード] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-376">To download a file, select the download icon in the **Download** column of the table.</span></span>

     ![スクリーンショット: マイアップロードテーブルを表示します。](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. <span data-ttu-id="71f4c-378">複数の建物データファイルまたは複数のエンドポイントデータファイルを使用する場合、一部のレポートの生成速度が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-378">If you choose to use multiple building data files or multiple endpoint data files, some reports generate more slowly.</span></span>

### <a name="tenant-data-file-format-and-structure"></a><span data-ttu-id="71f4c-379">テナントデータファイルの形式と構造</span><span class="sxs-lookup"><span data-stu-id="71f4c-379">Tenant data file format and structure</span></span>

<span data-ttu-id="71f4c-380"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="71f4c-380"></span></span>

### <a name="building-data-file"></a><span data-ttu-id="71f4c-381">データファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="71f4c-381">Building data file</span></span>

<span data-ttu-id="71f4c-382">CQD は、建物データファイルを使用します。これにより、有用な通話の詳細が提供されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-382">CQD uses a Building data file, which helps provide useful call details.</span></span> <span data-ttu-id="71f4c-383">[Subnet] 列を抽出するには、Network + NetworkRange 列を展開し、サブネット列を通話レコードの最初のサブネットまたは第2サブネット列に結合して、建物、市区町村、国、または地域の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-383">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="71f4c-384">アップロードするデータファイルの形式は、次の条件に従って、アップロード前に検証チェックに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-384">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>
  
- <span data-ttu-id="71f4c-385">ファイルは、.tsv ファイル (列はタブで区切られます) または .csv ファイル (列はコンマで区切られます) のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-385">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>
- <span data-ttu-id="71f4c-386">データファイルには、テーブルの見出し行が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="71f4c-386">The data file doesn't include a table header row.</span></span> <span data-ttu-id="71f4c-387">データファイルの最初の行は、"Network" のようなヘッダーラベルではなく、実際のデータであると想定されています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-387">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>
- <span data-ttu-id="71f4c-388">ファイル内のデータ型に指定できるのは、String、Integer、またはブール値のみです。</span><span class="sxs-lookup"><span data-stu-id="71f4c-388">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="71f4c-389">整数データ型の場合、値は数値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-389">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="71f4c-390">ブール値は、0または1でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="71f4c-390">Boolean values must be either 0 or 1.</span></span>
- <span data-ttu-id="71f4c-391">列に文字列データ型が使用されている場合、データフィールドは空でもかまいませんが、タブまたはコンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-391">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="71f4c-392">空のデータフィールドでは、空の文字列値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-392">An empty data field just assigns an empty String value.</span></span>
- <span data-ttu-id="71f4c-393">各行には14個の列がある必要があります。各列には適切なデータ型が設定されており、列は次の表の順序である必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-393">There must be 14 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table:</span></span>

||||||||||||||||
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:---  |:--- |:---|
|<span data-ttu-id="71f4c-394">**列フィールド名**</span><span class="sxs-lookup"><span data-stu-id="71f4c-394">**Column field name**</span></span>|<span data-ttu-id="71f4c-395">NetworkIP</span><span class="sxs-lookup"><span data-stu-id="71f4c-395">NetworkIP</span></span>  |<span data-ttu-id="71f4c-396">NetworkName</span><span class="sxs-lookup"><span data-stu-id="71f4c-396">NetworkName</span></span>              |<span data-ttu-id="71f4c-397">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="71f4c-397">NetworkRange</span></span>|<span data-ttu-id="71f4c-398">BuildingName</span><span class="sxs-lookup"><span data-stu-id="71f4c-398">BuildingName</span></span>  |<span data-ttu-id="71f4c-399">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="71f4c-399">OwnershipType</span></span>| <span data-ttu-id="71f4c-400">BuildingType</span><span class="sxs-lookup"><span data-stu-id="71f4c-400">BuildingType</span></span>  |<span data-ttu-id="71f4c-401">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="71f4c-401">BuildingOfficeType</span></span>|<span data-ttu-id="71f4c-402">市区町村</span><span class="sxs-lookup"><span data-stu-id="71f4c-402">City</span></span>   |<span data-ttu-id="71f4c-403">ZipCode</span><span class="sxs-lookup"><span data-stu-id="71f4c-403">ZipCode</span></span>|<span data-ttu-id="71f4c-404">居住</span><span class="sxs-lookup"><span data-stu-id="71f4c-404">Country</span></span>|<span data-ttu-id="71f4c-405">都道府県</span><span class="sxs-lookup"><span data-stu-id="71f4c-405">State</span></span> |<span data-ttu-id="71f4c-406">Region</span><span class="sxs-lookup"><span data-stu-id="71f4c-406">Region</span></span>|<span data-ttu-id="71f4c-407">InsideCorp&dagger;</span><span class="sxs-lookup"><span data-stu-id="71f4c-407">InsideCorp&dagger;</span></span>|<span data-ttu-id="71f4c-408">ExpressRoute&Dagger;</span><span class="sxs-lookup"><span data-stu-id="71f4c-408">ExpressRoute&Dagger;</span></span>|<span data-ttu-id="71f4c-409">VPN (オプション)</span><span class="sxs-lookup"><span data-stu-id="71f4c-409">VPN (optional)</span></span>|
|<span data-ttu-id="71f4c-410">**データ型**</span><span class="sxs-lookup"><span data-stu-id="71f4c-410">**Data type**</span></span>        | <span data-ttu-id="71f4c-411">String</span><span class="sxs-lookup"><span data-stu-id="71f4c-411">String</span></span>    | <span data-ttu-id="71f4c-412">String</span><span class="sxs-lookup"><span data-stu-id="71f4c-412">String</span></span>                  |<span data-ttu-id="71f4c-413">数値</span><span class="sxs-lookup"><span data-stu-id="71f4c-413">Number</span></span>      | <span data-ttu-id="71f4c-414">String</span><span class="sxs-lookup"><span data-stu-id="71f4c-414">String</span></span>       | <span data-ttu-id="71f4c-415">String</span><span class="sxs-lookup"><span data-stu-id="71f4c-415">String</span></span>      | <span data-ttu-id="71f4c-416">String</span><span class="sxs-lookup"><span data-stu-id="71f4c-416">String</span></span>        |<span data-ttu-id="71f4c-417">String</span><span class="sxs-lookup"><span data-stu-id="71f4c-417">String</span></span>            |<span data-ttu-id="71f4c-418">String</span><span class="sxs-lookup"><span data-stu-id="71f4c-418">String</span></span> |<span data-ttu-id="71f4c-419">String</span><span class="sxs-lookup"><span data-stu-id="71f4c-419">String</span></span> |<span data-ttu-id="71f4c-420">String</span><span class="sxs-lookup"><span data-stu-id="71f4c-420">String</span></span> |<span data-ttu-id="71f4c-421">String</span><span class="sxs-lookup"><span data-stu-id="71f4c-421">String</span></span>|<span data-ttu-id="71f4c-422">String</span><span class="sxs-lookup"><span data-stu-id="71f4c-422">String</span></span>|<span data-ttu-id="71f4c-423">Boolean</span><span class="sxs-lookup"><span data-stu-id="71f4c-423">Boolean</span></span>   |<span data-ttu-id="71f4c-424">Boolean</span><span class="sxs-lookup"><span data-stu-id="71f4c-424">Boolean</span></span>     |<span data-ttu-id="71f4c-425">Boolean</span><span class="sxs-lookup"><span data-stu-id="71f4c-425">Boolean</span></span>|
|<span data-ttu-id="71f4c-426">**値の例**</span><span class="sxs-lookup"><span data-stu-id="71f4c-426">**Example value**</span></span>    |<span data-ttu-id="71f4c-427">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="71f4c-427">192.168.1.0</span></span>|<span data-ttu-id="71f4c-428">米国/シアトル/シアトル-SEA-1</span><span class="sxs-lookup"><span data-stu-id="71f4c-428">USA/Seattle/SEATTLE-SEA-1</span></span>| <span data-ttu-id="71f4c-429">#</span><span class="sxs-lookup"><span data-stu-id="71f4c-429">26</span></span>         | <span data-ttu-id="71f4c-430">シアトル-SEA-1</span><span class="sxs-lookup"><span data-stu-id="71f4c-430">SEATTLE-SEA-1</span></span>| <span data-ttu-id="71f4c-431">コントソ</span><span class="sxs-lookup"><span data-stu-id="71f4c-431">Contoso</span></span>     | <span data-ttu-id="71f4c-432">IT の終了</span><span class="sxs-lookup"><span data-stu-id="71f4c-432">IT Termination</span></span>|<span data-ttu-id="71f4c-433">エンジニアリング</span><span class="sxs-lookup"><span data-stu-id="71f4c-433">Engineering</span></span>       |<span data-ttu-id="71f4c-434">調布市調布ヶ丘</span><span class="sxs-lookup"><span data-stu-id="71f4c-434">Seattle</span></span>|<span data-ttu-id="71f4c-435">98001</span><span class="sxs-lookup"><span data-stu-id="71f4c-435">98001</span></span>  |<span data-ttu-id="71f4c-436">プロセッサー</span><span class="sxs-lookup"><span data-stu-id="71f4c-436">US</span></span>     |<span data-ttu-id="71f4c-437">WA</span><span class="sxs-lookup"><span data-stu-id="71f4c-437">WA</span></span>    |<span data-ttu-id="71f4c-438">MSUS</span><span class="sxs-lookup"><span data-stu-id="71f4c-438">MSUS</span></span>  | <span data-ttu-id="71f4c-439">1</span><span class="sxs-lookup"><span data-stu-id="71f4c-439">1</span></span>        |<span data-ttu-id="71f4c-440">0</span><span class="sxs-lookup"><span data-stu-id="71f4c-440">0</span></span>           | <span data-ttu-id="71f4c-441">0</span><span class="sxs-lookup"><span data-stu-id="71f4c-441">0</span></span>|
|||||||||||||||||

<span data-ttu-id="71f4c-442">&dagger;この設定は、サブネットが企業ネットワーク内にあるかどうかを反映するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-442">&dagger; This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="71f4c-443">必要に応じて、他の目的の使用をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-443">You can customize usage for other purposes if you decide to.</span></span>

<span data-ttu-id="71f4c-444">&Dagger;この設定は、ネットワークが Azure ExpressRoute を使用しているかどうかを反映するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-444">&Dagger; This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="71f4c-445">必要に応じて、他の目的の使用をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-445">You can customize usage for other purposes if you decide to.</span></span>  

<span data-ttu-id="71f4c-446">**サンプルの行:**</span><span class="sxs-lookup"><span data-stu-id="71f4c-446">**Sample row:**</span></span>

```
192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0
```

> [!IMPORTANT]
> <span data-ttu-id="71f4c-447">ネットワーク範囲は、スーパーネット (単一のルーティングプレフィックスを持つ複数のサブネットの組み合わせ) を表すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-447">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="71f4c-448">新しくなったすべての文書のアップロードで、重複範囲が確認されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-448">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="71f4c-449">以前にビルドファイルをアップロードしたことがある場合は、現在のファイルをダウンロードして再アップロードし、重複を特定し、問題を解決してからもう一度アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-449">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="71f4c-450">以前にアップロードされたファイルが重なっていると、サブネットとレポートの建物とのマッピングが間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-450">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="71f4c-451">特定の VPN の実装では、サブネット情報が正確に報告されません。</span><span class="sxs-lookup"><span data-stu-id="71f4c-451">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="71f4c-452">構成ファイルに VPN サブネットを追加するときは、サブネットのエントリの1つではなく、個別の32ビットネットワークとして、VPN サブネットの各アドレスに個別のエントリを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="71f4c-452">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="71f4c-453">各行には、同じビルドメタデータを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-453">Each row can have the same building metadata.</span></span> <span data-ttu-id="71f4c-454">たとえば、172.16.18.0/24 の1行ではなく、256行と、172.16.18.0/32 と 172.16.18.255/32 の間の各アドレスに1つの行が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-454">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span>
>
> <span data-ttu-id="71f4c-455">VPN 列はオプションであり、既定値は0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-455">The VPN column is optional and will default to 0.</span></span>  <span data-ttu-id="71f4c-456">VPN 列の値が1に設定されている場合、その行で表されるサブネットは、サブネット内のすべての IP アドレスと一致するように完全に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-456">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="71f4c-457">これらのサブネットを完全に拡張すると、データの作成に関係するクエリのクエリ時間に悪影響を与える可能性があるため、このように慎重に使用してください。</span><span class="sxs-lookup"><span data-stu-id="71f4c-457">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>

### <a name="endpoint-data-file"></a><span data-ttu-id="71f4c-458">エンドポイントデータファイル</span><span class="sxs-lookup"><span data-stu-id="71f4c-458">Endpoint data file</span></span>

<span data-ttu-id="71f4c-459">CQD はエンドポイントデータファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-459">CQD uses an Endpoint data file.</span></span> <span data-ttu-id="71f4c-460">列の値は、[通話記録の最初のクライアントエンドポイント名] または [第2のクライアントエンドポイント名] 列で使用され、エンドポイントの作成、モデル、または型の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-460">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="71f4c-461">アップロードするデータファイルの形式は、次の条件に従って、アップロード前に検証チェックに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-461">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="71f4c-462">ファイルは、.tsv ファイル (列はタブで区切られます) または .csv ファイル (列はコンマで区切られます) のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-462">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>
- <span data-ttu-id="71f4c-463">データファイルの内容には、テーブル見出しは含まれません。</span><span class="sxs-lookup"><span data-stu-id="71f4c-463">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="71f4c-464">データファイルの最初の行は、"EndpointName" のような見出しラベルではなく、実際のデータである必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-464">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>
- <span data-ttu-id="71f4c-465">7つの列はすべて、文字列データ型のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-465">All seven columns use the String data type only.</span></span> <span data-ttu-id="71f4c-466">使用できる最大文字数は64文字です。</span><span class="sxs-lookup"><span data-stu-id="71f4c-466">The maximum allowed length is 64 characters.</span></span>
- <span data-ttu-id="71f4c-467">データフィールドは空白にすることもできますが、タブまたはコンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-467">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="71f4c-468">空のデータフィールドでは、空の文字列値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-468">An empty data field just assigns an empty String value.</span></span>
- <span data-ttu-id="71f4c-469">EndpointName は一意である必要があります。そうでない場合、アップロードは失敗します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-469">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="71f4c-470">重複している行が重複している場合、または2つの行に同じ EndpointName が含まれている場合は、競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-470">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>
- <span data-ttu-id="71f4c-471">EndpointLabel1、EndpointLabel2、EndpointLabel3 はカスタマイズ可能なラベルです。</span><span class="sxs-lookup"><span data-stu-id="71f4c-471">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="71f4c-472">空の文字列や値にすることができるのは、"IT 部門が指定した2018ノート Pc" または "Asset Tag 5678" などです。</span><span class="sxs-lookup"><span data-stu-id="71f4c-472">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>
- <span data-ttu-id="71f4c-473">各行には7つの列があり、列は次の順序である必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-473">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="71f4c-474">**フィールドの順序:**</span><span class="sxs-lookup"><span data-stu-id="71f4c-474">**Field order:**</span></span>

  <span data-ttu-id="71f4c-475">EndpointName、EndpointModel、Endpointmodel、EndpointLabel1、EndpointLabel2、EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="71f4c-475">EndpointName, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="71f4c-476">**サンプルの行:**</span><span class="sxs-lookup"><span data-stu-id="71f4c-476">**Sample row:**</span></span>

  `1409W3534, Fabrikam Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018,`  

## <a name="create-custom-detailed-reports"></a><span data-ttu-id="71f4c-477">ユーザー設定の詳細レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="71f4c-477">Create custom detailed reports</span></span>

<span data-ttu-id="71f4c-478">特定のレポートを作成して、提供された詳細レポートではないような方法でデータを分析するには、カスタムレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-478">If you find you want to create a specific report that focuses on a dimension of the data in a way the provided detailed reports do not, create a custom report.</span></span>

<span data-ttu-id="71f4c-479">ログイン\(時に表示される画面の上部にあるレポートのプルダウンリストで、[ \*\*\*\* レポートの概要\) ] 画面**を選択し**、[**新規作成**] をクリックします。クエリエディターを表示するには、レポートのアクションメニューで [編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71f4c-479">From the pull-down list of reports at the top of the screen displayed at login \(the **Summary Reports** screen\) Select **Detailed Reports**  and then **New** d Click "Edit" in the action menu of a report to see the Query Editor.</span></span> <span data-ttu-id="71f4c-480">それぞれのレポートは、キューブに対するクエリに基づきます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-480">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="71f4c-481">レポートは、クエリから返されたデータを視覚化したものです。</span><span class="sxs-lookup"><span data-stu-id="71f4c-481">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="71f4c-482">クエリエディターを使用すると、これらのクエリやレポートの表示オプションを編集できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-482">The Query Editor helps you edit these queries and the display options of the report.</span></span> <span data-ttu-id="71f4c-483">新しいレポートのクエリエディターを開くと、次のスクリーンショットのような画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-483">When you open the Query Editor for a new report, you see something similar to this screenshot:</span></span>

![新しいレポートを編集する](media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. <span data-ttu-id="71f4c-485">左側のウィンドウでは、ディメンション、メジャー、およびフィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-485">Dimensions, measures, and filters are chosen in the left pane.</span></span> <span data-ttu-id="71f4c-486">見出しの横にあるプラス記号 (+) をクリックしてダイアログを開き、ディメンション、測定、またはフィルターを追加して、対応するボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="71f4c-486">Click the "plus" button next to a heading to open the dialog where you can add a  dimension, measure, or filter and check the corresponding box.</span></span> <span data-ttu-id="71f4c-487">既存のレポートを編集する場合は、既存の値をオフにして削除することができます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-487">If you edit an existing report, you can uncheck existing values to remove them.</span></span> <span data-ttu-id="71f4c-488">詳しくは、「[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="71f4c-488">For details, see [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
2. <span data-ttu-id="71f4c-489">最上部には、グラフをカスタマイズするためのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-489">Options for chart customization are displayed at the top.</span></span>
3. <span data-ttu-id="71f4c-490">レポートのプレビューは、クエリエディターで確認できます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-490">A preview of the report is available in the Query Editor.</span></span>
4. <span data-ttu-id="71f4c-491">詳細なレポート名と説明を作成するには、下部にある編集ボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-491">A detailed report name and description can be created with the edit box at the bottom.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="71f4c-492">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="71f4c-492">Frequently Asked Questions</span></span>

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a><span data-ttu-id="71f4c-493">CQD v2 のレポートデータが CQD v3 のレポートデータと異なるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="71f4c-493">Why does my CQD v2 report data look different than the CQD v3 report data?</span></span> 

<span data-ttu-id="71f4c-494">CQD v2 と v3 のデータの違いが表示される場合は、データの比較または検証が、集計レベルではなく、"りんごからりんご" と "幅" レベルで行われていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="71f4c-494">If you see data differences between CQD v2 and v3, make sure that data comparison or validation is done on an 'apples-to-apples'  and narrow level, not an aggregated level.</span></span> <span data-ttu-id="71f4c-495">たとえば、"建物 30" の WiFi Teams のデスクトップクライアントデータの両方のレポートをフィルター処理する場合、低品質の割合は、v2 と v3 で同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-495">For example, if you filter both reports for MSIT ‘Building 30' WiFi Teams Desktop client data, the Percentage of Poor Quality should be the same between v2 and v3.</span></span>

<span data-ttu-id="71f4c-496">CQD v3 では CQD v2 に新しいシナリオが存在しないため、CQD v2 と CQD v3 の合計数は異なります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-496">CQD v2 and CQD v3 have different total counts since CQD v3 has new scenarios not present in CQD v2.</span></span> <span data-ttu-id="71f4c-497">フィルターを使用しない場合は、集計の合計または総計が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-497">Summary Total or Aggregated all-up numbers with no filters are expected to be different.</span></span>  

<span data-ttu-id="71f4c-498">使用シナリオに Skype for Business Server の2019通話が含まれている場合、CQD v3 のデータには、Skype ボット通話 (自動応答、CVI、仮想デスクトップインターフェイス)、ライブイベント、PSTN 通話が含まれます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-498">If the usage scenario includes Skype for Business Server 2019 calls, CQD v3 data includes Skype Bot calls (auto attendant, CVI, Virtual Desktop Interface), Live Events, and PSTN calls.</span></span> <span data-ttu-id="71f4c-499">CQD v2 では、このデータは使用されません。</span><span class="sxs-lookup"><span data-stu-id="71f4c-499">CQD v2 does not use this data.</span></span> <span data-ttu-id="71f4c-500">(CQD v3 には、クラウドデータコネクタが構成された Skype for Business Server 2019 が必要です。)</span><span class="sxs-lookup"><span data-stu-id="71f4c-500">(CQD v3 requires Skype for Business Server 2019 with cloud data connector configured.)</span></span>

<span data-ttu-id="71f4c-501">たとえば、CQD v2 の概要レポートで5000のエラーを含む20万オーディオストリームが表示された場合は、5500の障害が発生している30万オーディオストリーム (Skype for Business Server 2019 通話、CVI 通話、PSTN 通話など) が表示されない可能性があります。など) を CQD v3 の概要レポートで作成します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-501">For instance, if you see 200,000 audio streams with 5000 failures in a CQD v2 Summary Report it would not be unusual to see 300,000 audio streams with 5500 failures (the difference can be due to Skype for Business Server 2019 calls, CVI calls, PSTN calls, and so on) in a CQD v3 Summary report.</span></span>

<span data-ttu-id="71f4c-502">予期しない違いを明確にするために、データ全体の1つ以上の内訳を確認します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-502">To disambiguate unexpected differences, look at more than one breakdown of the overall data.</span></span> <span data-ttu-id="71f4c-503">次のパラメーターの1つ以上を使ってデータにフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-503">Filter the data by one or more of the following parameters:</span></span>

- <span data-ttu-id="71f4c-504">User Agent Category Pair</span><span class="sxs-lookup"><span data-stu-id="71f4c-504">User Agent Category Pair</span></span>
- <span data-ttu-id="71f4c-505">第1の製品</span><span class="sxs-lookup"><span data-stu-id="71f4c-505">First Product</span></span>
- <span data-ttu-id="71f4c-506">第2の製品</span><span class="sxs-lookup"><span data-stu-id="71f4c-506">Second Product</span></span>

### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a><span data-ttu-id="71f4c-507">CQD v2 と CQD v3 とのその他の予想される違い</span><span class="sxs-lookup"><span data-stu-id="71f4c-507">Other expected differences between CQD v2 and CQD v3</span></span>

<span data-ttu-id="71f4c-508">Teams では、Skype for Business Online ではなく、いくつかの品質と信頼性が向上しています。</span><span class="sxs-lookup"><span data-stu-id="71f4c-508">There are several Quality and Reliability improvements in Teams but not Skype for Business Online:</span></span>

- <span data-ttu-id="71f4c-509">自動再接続</span><span class="sxs-lookup"><span data-stu-id="71f4c-509">Auto-reconnect</span></span>
- <span data-ttu-id="71f4c-510">高速ローミング</span><span class="sxs-lookup"><span data-stu-id="71f4c-510">Fast roaming</span></span>
- <span data-ttu-id="71f4c-511">白黒管理の改善</span><span class="sxs-lookup"><span data-stu-id="71f4c-511">Improved BW management</span></span>

<span data-ttu-id="71f4c-512">次の2つのサービスのデータを比較する場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="71f4c-512">When you compare data for these two services:</span></span>

- <span data-ttu-id="71f4c-513">会社の有線接続、Windows デスクトップ、または1つの地域や建物など、集中するシナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-513">Pick a scenario with a tight focus, such as corporate wired connections, Windows Desktops, or a single region or building.</span></span>
- <span data-ttu-id="71f4c-514">Teams の [MR]、[TR]、または [MP] の IP 範囲を確認します。</span><span class="sxs-lookup"><span data-stu-id="71f4c-514">Check the Teams MR, TR, or MP IP ranges.</span></span> <span data-ttu-id="71f4c-515">チームの範囲は Skype for Business Online よりも新しいものであり、ファイアウォールに関連する接続の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-515">The Teams ranges are newer than Skype for Business Online, and that can cause connectivity issues involving firewalls</span></span>
- <span data-ttu-id="71f4c-516">サマリーまたはトップレベルの数値を比較しないでください。</span><span class="sxs-lookup"><span data-stu-id="71f4c-516">Don't compare summary or top-level numbers.</span></span> <span data-ttu-id="71f4c-517">これらの比較を行うことで、企業の有線接続での Skype for Business Online 通話の大きな通話音量と、LTE またはプライベートネットワーク上での少人数のチーム通話との比較を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="71f4c-517">These comparisons will lead you to compare a large call volume of Skype for Business Online calls on a corporate wired connection to a small volume of Teams calls on an LTE or private network.</span></span>
- <span data-ttu-id="71f4c-518">位置のバイアスと母集団の相違点に注意してください。多すぎては、次のような違いがあります。</span><span class="sxs-lookup"><span data-stu-id="71f4c-518">Beware of location bias and population differences: There are many comparisons that are too dissimilar to be useful:</span></span>
  - <span data-ttu-id="71f4c-519">NOAM: APAC</span><span class="sxs-lookup"><span data-stu-id="71f4c-519">NOAM : APAC</span></span>
  - <span data-ttu-id="71f4c-520">NY: Goa</span><span class="sxs-lookup"><span data-stu-id="71f4c-520">NY : Goa</span></span>
  - <span data-ttu-id="71f4c-521">有線 : WiFi</span><span class="sxs-lookup"><span data-stu-id="71f4c-521">Wired : wifi</span></span>
  - <span data-ttu-id="71f4c-522">企業ネットワーク: ホームネットワーク</span><span class="sxs-lookup"><span data-stu-id="71f4c-522">Corporate network : home network</span></span>
  


## <a name="related-topics"></a><span data-ttu-id="71f4c-523">関連トピック</span><span class="sxs-lookup"><span data-stu-id="71f4c-523">Related topics</span></span>

[<span data-ttu-id="71f4c-524">通話品質ダッシュボードで利用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="71f4c-524">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="71f4c-525">通話品質ダッシュボードでのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="71f4c-525">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="71f4c-526">Skype for Business の通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="71f4c-526">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="71f4c-527">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="71f4c-527">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="71f4c-528">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="71f4c-528">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
