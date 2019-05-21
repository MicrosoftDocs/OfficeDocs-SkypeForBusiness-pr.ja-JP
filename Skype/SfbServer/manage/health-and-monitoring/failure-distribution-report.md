---
title: Skype for Business Server のエラー配布レポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
description: '概要: Skype for Business Server のエラー配布レポートについて説明します。'
ms.openlocfilehash: d9e7d2ac0ff10743c69bee665be3878ac9009933
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305697"
---
# <a name="failure-distribution-report-in-skype-for-business-server"></a><span data-ttu-id="057b0-103">Skype for Business Server のエラー配布レポート</span><span class="sxs-lookup"><span data-stu-id="057b0-103">Failure Distribution Report in Skype for Business Server</span></span>
 
<span data-ttu-id="057b0-104">**概要:** Skype for Business Server のエラー配布レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="057b0-104">**Summary:** Learn about the Failure Distribution Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="057b0-105">エラー分布レポートは、問題の発生したセッションを以下のカテゴリに分類します。</span><span class="sxs-lookup"><span data-stu-id="057b0-105">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>
  
- <span data-ttu-id="057b0-106">トップの診断理由</span><span class="sxs-lookup"><span data-stu-id="057b0-106">Top diagnostic reasons</span></span>
    
- <span data-ttu-id="057b0-107">トップのモダリティ</span><span class="sxs-lookup"><span data-stu-id="057b0-107">Top modalities</span></span>
    
- <span data-ttu-id="057b0-108">トップのプール</span><span class="sxs-lookup"><span data-stu-id="057b0-108">Top pools</span></span>
    
- <span data-ttu-id="057b0-109">トップのソース</span><span class="sxs-lookup"><span data-stu-id="057b0-109">Top sources</span></span>
    
- <span data-ttu-id="057b0-110">トップのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="057b0-110">Top components</span></span>
    
- <span data-ttu-id="057b0-111">トップの発信元ユーザー</span><span class="sxs-lookup"><span data-stu-id="057b0-111">Top from users</span></span>
    
- <span data-ttu-id="057b0-112">トップの発信先ユーザー</span><span class="sxs-lookup"><span data-stu-id="057b0-112">Top to users</span></span>
    
- <span data-ttu-id="057b0-113">送信元ユーザー エージェント</span><span class="sxs-lookup"><span data-stu-id="057b0-113">Top from user agents</span></span>
    
<span data-ttu-id="057b0-p101">これらのカテゴリを使用して、どこに問題が発生しているか、場合によっては、問題が発生している理由を正確に確認できます。たとえば特定の日に、242 個のオーディオ/ビデオ セッションの障害が記録されたとします。エラー分布レポートを調べてみると、これらの問題の発生したセッションのうち、237 個が Dublin プールで発生しているかもしれません。これらの問題の背後にある原因を調べて診断するには、このような情報が役に立ちます。[**トップのプール**] カテゴリの下の Dublin プールをクリックすると、そのプールのエラー分布レポートのみが表示されます。次に Dublin プールでこれほど多くの問題が発生している理由の分析を開始できます。</span><span class="sxs-lookup"><span data-stu-id="057b0-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>
  
## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="057b0-120">エラー分布レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="057b0-120">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="057b0-121">以下の任意のレポートで、[**予期されるエラー ボリューム**] または [**予期しないエラー ボリューム**] の指標をクリックすると、エラー分布レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="057b0-121">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>
  
- [<span data-ttu-id="057b0-122">Skype for Business Server の上位のエラーレポート</span><span class="sxs-lookup"><span data-stu-id="057b0-122">Top Failures Report in Skype for Business Server</span></span>](top-failures-report.md)
    
- [<span data-ttu-id="057b0-123">Skype for Business Server の会議の診断レポート</span><span class="sxs-lookup"><span data-stu-id="057b0-123">Conference Diagnostic Report in Skype for Business Server</span></span>](conference-diagnostic-report.md)
    
- [<span data-ttu-id="057b0-124">Skype for Business Server のピアツーピアアクティビティ診断レポート</span><span class="sxs-lookup"><span data-stu-id="057b0-124">Peer-to-Peer Activity Diagnostic Report in Skype for Business Server</span></span>](peer-to-peer-activity-diagnostic-report.md)
    
<span data-ttu-id="057b0-125">エラー配布レポートでは、次の指標のいずれかをクリックして、 [Skype For Business Server のエラー一覧レポート](failure-list-report.md)を表示できます。</span><span class="sxs-lookup"><span data-stu-id="057b0-125">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Skype for Business Server](failure-list-report.md):</span></span>
  
- <span data-ttu-id="057b0-126">トップの診断理由 (セッション)</span><span class="sxs-lookup"><span data-stu-id="057b0-126">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="057b0-127">トップのモダリティ (セッション)</span><span class="sxs-lookup"><span data-stu-id="057b0-127">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="057b0-128">トップのプール (セッション)</span><span class="sxs-lookup"><span data-stu-id="057b0-128">Top pools (sessions)</span></span>
    
- <span data-ttu-id="057b0-129">トップのソース (セッション)</span><span class="sxs-lookup"><span data-stu-id="057b0-129">Top sources (sessions)</span></span>
    
- <span data-ttu-id="057b0-130">トップのコンポーネント (セッション)</span><span class="sxs-lookup"><span data-stu-id="057b0-130">Top components (sessions)</span></span>
    
- <span data-ttu-id="057b0-131">トップの発信元ユーザー (セッション)</span><span class="sxs-lookup"><span data-stu-id="057b0-131">Top from users (sessions)</span></span>
    
- <span data-ttu-id="057b0-132">トップの発信先ユーザー (セッション)</span><span class="sxs-lookup"><span data-stu-id="057b0-132">Top to users (sessions)</span></span>
    
- <span data-ttu-id="057b0-133">トップの発信元ユーザー エージェント (セッション)</span><span class="sxs-lookup"><span data-stu-id="057b0-133">Top from user agents (sessions)</span></span>
    
## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="057b0-134">エラー分布レポートを使用する</span><span class="sxs-lookup"><span data-stu-id="057b0-134">Using the Failure Distribution Report</span></span>

<span data-ttu-id="057b0-p102">モニターの大きさと画面解像度によっては、エラー分布レポートを画面上で表示するとき、表示されるデータの一部が切り捨てられることがあります。これは特に、ユーザー エージェントのような非常に長いラベルを持つことがある指標で発生します。たとえば、"UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013) " のような名前のユーザー エージェントは、以下のように一部分のみが画面上に表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="057b0-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span> 
  
<span data-ttu-id="057b0-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="057b0-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>
  
<span data-ttu-id="057b0-139">この場合、切り捨てられた値の上にマウス ポインターを置くだけでラベル全体を表示できます。</span><span class="sxs-lookup"><span data-stu-id="057b0-139">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>
  
<span data-ttu-id="057b0-p103">エラー分布レポートを使用してフィルター処理できる、役立つ指標の 1 つが診断 ID です。さまざまなレポートで同じ診断 ID が表示される場合、エラー分布レポートでその ID をフィルター処理して、問題の発生したセッション中に、その ID が報告された正確な場所と頻度について非常に詳細な情報を得られます。</span><span class="sxs-lookup"><span data-stu-id="057b0-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>
  
## <a name="filters"></a><span data-ttu-id="057b0-142">フィルター</span><span class="sxs-lookup"><span data-stu-id="057b0-142">Filters</span></span>

<span data-ttu-id="057b0-p104">フィルターは、必要なデータのみに絞り込んだデータ セットを取得したり、取得したデータを別の方法で表示したりする方法として利用できます。たとえば、エラー分布レポートを使用すると、動作状況の種類 (ピアツーピア セッションまたは電話会議セッション) などにフィルターを適用できます。また、失敗した各セッションに添付される診断 ID によってフィルターを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="057b0-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>
  
<span data-ttu-id="057b0-145">次の表に、エラー分布レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="057b0-145">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>
  
<span data-ttu-id="057b0-146">**エラー分布レポートのフィルター**</span><span class="sxs-lookup"><span data-stu-id="057b0-146">**Failure Distribution Report Filters**</span></span>

|<span data-ttu-id="057b0-147">**名前**</span><span class="sxs-lookup"><span data-stu-id="057b0-147">**Name**</span></span>|<span data-ttu-id="057b0-148">**説明**</span><span class="sxs-lookup"><span data-stu-id="057b0-148">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="057b0-149">**開始**</span><span class="sxs-lookup"><span data-stu-id="057b0-149">**From**</span></span> <br/> |<span data-ttu-id="057b0-p105">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="057b0-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="057b0-152">7/7/2015 13:00</span><span class="sxs-lookup"><span data-stu-id="057b0-152">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="057b0-p106">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="057b0-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="057b0-155">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="057b0-155">7/7/2015</span></span>  <br/> <span data-ttu-id="057b0-156">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="057b0-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="057b0-157">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="057b0-157">7/3/2015</span></span>  <br/> <span data-ttu-id="057b0-158">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="057b0-158">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="057b0-159">**終了**</span><span class="sxs-lookup"><span data-stu-id="057b0-159">**To**</span></span> <br/> |<span data-ttu-id="057b0-p107">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="057b0-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="057b0-162">7/7/2015 13:00</span><span class="sxs-lookup"><span data-stu-id="057b0-162">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="057b0-p108">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="057b0-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="057b0-165">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="057b0-165">7/7/2015</span></span>  <br/> <span data-ttu-id="057b0-166">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="057b0-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="057b0-167">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="057b0-167">7/3/2015</span></span>  <br/> <span data-ttu-id="057b0-168">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="057b0-168">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="057b0-169">**プール**</span><span class="sxs-lookup"><span data-stu-id="057b0-169">**Pool**</span></span> <br/> |<span data-ttu-id="057b0-p109">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[**すべて**] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="057b0-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click **[All]** to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database. </span></span><br/> |
|<span data-ttu-id="057b0-173">**[動作状況の種類]**</span><span class="sxs-lookup"><span data-stu-id="057b0-173">**Activity type**</span></span> <br/> | <span data-ttu-id="057b0-p110">フィルターを適用する動作状況の種類。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="057b0-p110">Type of activity to filter on. Select one of the following:</span></span> <br/>  <span data-ttu-id="057b0-176">[すべて]</span><span class="sxs-lookup"><span data-stu-id="057b0-176">[All]</span></span> <br/>  <span data-ttu-id="057b0-177">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="057b0-177">Peer-to-peer</span></span> <br/>  <span data-ttu-id="057b0-178">電話会議</span><span class="sxs-lookup"><span data-stu-id="057b0-178">Conference</span></span> <br/> |
|<span data-ttu-id="057b0-179">**[セッション カテゴリ]**</span><span class="sxs-lookup"><span data-stu-id="057b0-179">**Session category**</span></span> <br/> | <span data-ttu-id="057b0-p111">問題のアクティビティが成功したか失敗したかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="057b0-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span> <br/>  <span data-ttu-id="057b0-182">[すべて]</span><span class="sxs-lookup"><span data-stu-id="057b0-182">[All]</span></span> <br/>  <span data-ttu-id="057b0-183">成功</span><span class="sxs-lookup"><span data-stu-id="057b0-183">Success</span></span> <br/>  <span data-ttu-id="057b0-184">予期されたエラー</span><span class="sxs-lookup"><span data-stu-id="057b0-184">Expected failure</span></span> <br/>  <span data-ttu-id="057b0-185">予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="057b0-185">Unexpected failure</span></span> <br/>  <span data-ttu-id="057b0-p112">"予期されたエラー" は、発生が予期されるエラーです。たとえば、ユーザーが応答不可のステータスを設定した場合、そのユーザーへの呼び出しはエラーとなることが予期されます。"予期しないエラー" は、そのエラーの発生以外にはシステムに異常がないと思われる状況で発生するエラーです。たとえば、発信者が保留にされたときに、通話が終了してはなりません。そのような状態が発生する場合は、予期しないエラーとしてフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="057b0-p112">An "expected failure" is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail. An "unexpected failure" is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span> <br/> |
|<span data-ttu-id="057b0-191">**[診断 ID]**</span><span class="sxs-lookup"><span data-stu-id="057b0-191">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="057b0-p113">SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が発生したセッションについてのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="057b0-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span>  <br/> |
   
## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="057b0-194">トップの診断理由の指標</span><span class="sxs-lookup"><span data-stu-id="057b0-194">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="057b0-195">次の表に、最も報告される頻度が高い診断 ID に基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="057b0-195">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>
  
<span data-ttu-id="057b0-196">**トップの診断理由の指標**</span><span class="sxs-lookup"><span data-stu-id="057b0-196">**Metrics for Top Diagnostic Reasons**</span></span>

|<span data-ttu-id="057b0-197">**名前**</span><span class="sxs-lookup"><span data-stu-id="057b0-197">**Name**</span></span>|<span data-ttu-id="057b0-198">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="057b0-198">**Can you sort on this item?**</span></span>|<span data-ttu-id="057b0-199">**説明**</span><span class="sxs-lookup"><span data-stu-id="057b0-199">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="057b0-200">**[ランク]**</span><span class="sxs-lookup"><span data-stu-id="057b0-200">**Rank**</span></span> <br/> |<span data-ttu-id="057b0-201">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-201">No</span></span>  <br/> |<span data-ttu-id="057b0-p114">診断 ID に基づく、失敗したセッションの相対的なランク付け。診断 ID は、エラーのトラブルシューティングに役立つ情報の得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。</span><span class="sxs-lookup"><span data-stu-id="057b0-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="057b0-204">**[トップの診断理由]**</span><span class="sxs-lookup"><span data-stu-id="057b0-204">**Top diagnostic reasons**</span></span> <br/> |<span data-ttu-id="057b0-205">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-205">No</span></span>  <br/> |<span data-ttu-id="057b0-206">セッションで生成される診断 ID。</span><span class="sxs-lookup"><span data-stu-id="057b0-206">Diagnostic ID generated in a session.</span></span>  <br/> |
|<span data-ttu-id="057b0-207">**[セッション]**</span><span class="sxs-lookup"><span data-stu-id="057b0-207">**Sessions**</span></span> <br/> |<span data-ttu-id="057b0-208">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-208">No</span></span>  <br/> |<span data-ttu-id="057b0-209">指定された診断 ID が生成された、失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="057b0-209">Total number of failed sessions where the specified diagnostic ID was generated.</span></span>  <br/> |
   
## <a name="metrics-for-top-modalities"></a><span data-ttu-id="057b0-210">トップのモダリティの指標</span><span class="sxs-lookup"><span data-stu-id="057b0-210">Metrics for Top Modalities</span></span>

<span data-ttu-id="057b0-211">次の表に、最もエラーが発生したセッション モダリティに基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="057b0-211">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>
  
<span data-ttu-id="057b0-212">**トップのモダリティの指標**</span><span class="sxs-lookup"><span data-stu-id="057b0-212">**Metrics for Top Modalities**</span></span>

|<span data-ttu-id="057b0-213">**名前**</span><span class="sxs-lookup"><span data-stu-id="057b0-213">**Name**</span></span>|<span data-ttu-id="057b0-214">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="057b0-214">**Can you sort on this item?**</span></span>|<span data-ttu-id="057b0-215">**説明**</span><span class="sxs-lookup"><span data-stu-id="057b0-215">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="057b0-216">**[ランク]**</span><span class="sxs-lookup"><span data-stu-id="057b0-216">**Rank**</span></span> <br/> |<span data-ttu-id="057b0-217">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-217">No</span></span>  <br/> |<span data-ttu-id="057b0-218">セッションの種類 (たとえば、音声ビデオ会議、ピアツーピアのファイル送信セッション) に基づく、失敗したセッションの相対的なランク付け。</span><span class="sxs-lookup"><span data-stu-id="057b0-218">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span>  <br/> |
|<span data-ttu-id="057b0-219">**[トップのモダリティ]**</span><span class="sxs-lookup"><span data-stu-id="057b0-219">**Top modalities**</span></span> <br/> |<span data-ttu-id="057b0-220">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-220">No</span></span>  <br/> |<span data-ttu-id="057b0-221">セッションの種類。</span><span class="sxs-lookup"><span data-stu-id="057b0-221">Session type.</span></span>  <br/> |
|<span data-ttu-id="057b0-222">**[セッション]**</span><span class="sxs-lookup"><span data-stu-id="057b0-222">**Sessions**</span></span> <br/> |<span data-ttu-id="057b0-223">不可</span><span class="sxs-lookup"><span data-stu-id="057b0-223">No</span></span>  <br/> |<span data-ttu-id="057b0-224">指定されたモダリティが含まれる失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="057b0-224">Total number of failed sessions involving the specified modality.</span></span>  <br/> |
   
## <a name="metrics-for-top-pools"></a><span data-ttu-id="057b0-225">トップのプールの指標</span><span class="sxs-lookup"><span data-stu-id="057b0-225">Metrics for Top Pools</span></span>

<span data-ttu-id="057b0-226">次の表に、最もエラーが発生したプールに基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="057b0-226">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>
  
<span data-ttu-id="057b0-227">**トップのプールの指標**</span><span class="sxs-lookup"><span data-stu-id="057b0-227">**Metrics for Top Pools**</span></span>

|<span data-ttu-id="057b0-228">**名前**</span><span class="sxs-lookup"><span data-stu-id="057b0-228">**Name**</span></span>|<span data-ttu-id="057b0-229">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="057b0-229">**Can you sort on this item?**</span></span>|<span data-ttu-id="057b0-230">**説明**</span><span class="sxs-lookup"><span data-stu-id="057b0-230">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="057b0-231">**[ランク]**</span><span class="sxs-lookup"><span data-stu-id="057b0-231">**Rank**</span></span> <br/> |<span data-ttu-id="057b0-232">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-232">No</span></span>  <br/> |<span data-ttu-id="057b0-233">セッションが実行されたレジストラープールまたはエッジサーバーに基づいて、失敗したセッションの相対的なランクを指定します。</span><span class="sxs-lookup"><span data-stu-id="057b0-233">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span>  <br/> |
|<span data-ttu-id="057b0-234">**[トップのプール]**</span><span class="sxs-lookup"><span data-stu-id="057b0-234">**Top pools**</span></span> <br/> |<span data-ttu-id="057b0-235">不可</span><span class="sxs-lookup"><span data-stu-id="057b0-235">No</span></span>  <br/> |<span data-ttu-id="057b0-236">レジストラープールまたはエッジサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="057b0-236">Name of the Registrar pool or Edge Server.</span></span>  <br/> |
|<span data-ttu-id="057b0-237">**[セッション]**</span><span class="sxs-lookup"><span data-stu-id="057b0-237">**Sessions**</span></span> <br/> |<span data-ttu-id="057b0-238">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-238">No</span></span>  <br/> |<span data-ttu-id="057b0-239">登録プールまたはエッジサーバーあたりの失敗したセッションの合計数です。</span><span class="sxs-lookup"><span data-stu-id="057b0-239">Total number of failed sessions per Registrar pool or Edge Server.</span></span>  <br/> |
   
## <a name="metrics-for-top-sources"></a><span data-ttu-id="057b0-240">トップのソースの指標</span><span class="sxs-lookup"><span data-stu-id="057b0-240">Metrics for Top Sources</span></span>

<span data-ttu-id="057b0-241">次の表に、最もエラーが発生したコンピューターに基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="057b0-241">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>
  
<span data-ttu-id="057b0-242">**トップのソースの指標**</span><span class="sxs-lookup"><span data-stu-id="057b0-242">**Metrics for Top Sources**</span></span>

|<span data-ttu-id="057b0-243">**名前**</span><span class="sxs-lookup"><span data-stu-id="057b0-243">**Name**</span></span>|<span data-ttu-id="057b0-244">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="057b0-244">**Can you sort on this item?**</span></span>|<span data-ttu-id="057b0-245">**説明**</span><span class="sxs-lookup"><span data-stu-id="057b0-245">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="057b0-246">**[ランク]**</span><span class="sxs-lookup"><span data-stu-id="057b0-246">**Rank**</span></span> <br/> |<span data-ttu-id="057b0-247">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-247">No</span></span>  <br/> |<span data-ttu-id="057b0-248">コンピューターごとの失敗したセッションの相対的なランク付け。</span><span class="sxs-lookup"><span data-stu-id="057b0-248">Relative ranking failed sessions per computer.</span></span>  <br/> |
|<span data-ttu-id="057b0-249">**[トップのソース]**</span><span class="sxs-lookup"><span data-stu-id="057b0-249">**Top sources**</span></span> <br/> |<span data-ttu-id="057b0-250">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-250">No</span></span>  <br/> |<span data-ttu-id="057b0-251">失敗したセッションに含まれるコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="057b0-251">Name of the computer involved in the failed session.</span></span>  <br/> |
|<span data-ttu-id="057b0-252">**[セッション]**</span><span class="sxs-lookup"><span data-stu-id="057b0-252">**Sessions**</span></span> <br/> |<span data-ttu-id="057b0-253">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-253">No</span></span>  <br/> |<span data-ttu-id="057b0-254">コンピューターごとの失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="057b0-254">Total number of failed sessions per computer.</span></span>  <br/> |
   
## <a name="metrics-for-top-components"></a><span data-ttu-id="057b0-255">トップ コンポーネントの指標</span><span class="sxs-lookup"><span data-stu-id="057b0-255">Metrics for Top Components</span></span>

<span data-ttu-id="057b0-256">次の表に、最もエラーが発生したコンポーネントに基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="057b0-256">The following table lists the information provided in the Failure Distribution Report based on the components that experienced the most failures.</span></span>
  
<span data-ttu-id="057b0-257">**トップのコンポーネントの指標**</span><span class="sxs-lookup"><span data-stu-id="057b0-257">**Metrics for Top Components**</span></span>

|<span data-ttu-id="057b0-258">**名前**</span><span class="sxs-lookup"><span data-stu-id="057b0-258">**Name**</span></span>|<span data-ttu-id="057b0-259">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="057b0-259">**Can you sort on this item?**</span></span>|<span data-ttu-id="057b0-260">**説明**</span><span class="sxs-lookup"><span data-stu-id="057b0-260">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="057b0-261">**[ランク]**</span><span class="sxs-lookup"><span data-stu-id="057b0-261">**Rank**</span></span> <br/> |<span data-ttu-id="057b0-262">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-262">No</span></span>  <br/> |<span data-ttu-id="057b0-263">コンポーネント (ExumRouting、GroupChat、MediationServer など) に基づいて、失敗したセッションの相対的なランクを示します。</span><span class="sxs-lookup"><span data-stu-id="057b0-263">Relative ranking of failed sessions based on component (for example, ExumRouting, GroupChat, or MediationServer).</span></span>  <br/> |
|<span data-ttu-id="057b0-264">**[トップのコンポーネント]**</span><span class="sxs-lookup"><span data-stu-id="057b0-264">**Top components**</span></span> <br/> |<span data-ttu-id="057b0-265">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-265">No</span></span>  <br/> |<span data-ttu-id="057b0-266">失敗したセッションに含まれるコンポーネントの名前。</span><span class="sxs-lookup"><span data-stu-id="057b0-266">Name of the component involved in the failed session.</span></span>  <br/> |
|<span data-ttu-id="057b0-267">**[セッション]**</span><span class="sxs-lookup"><span data-stu-id="057b0-267">**Sessions**</span></span> <br/> |<span data-ttu-id="057b0-268">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-268">No</span></span>  <br/> |<span data-ttu-id="057b0-269">コンポーネントごとの失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="057b0-269">Total number of failed sessions per component.</span></span>  <br/> |
   
## <a name="metrics-for-top-from-users"></a><span data-ttu-id="057b0-270">トップの発信元ユーザーの指標</span><span class="sxs-lookup"><span data-stu-id="057b0-270">Metrics for Top From Users</span></span>

<span data-ttu-id="057b0-271">次の表に、他のユーザーを呼び出したときに最もエラーが発生したユーザー ("発信元" ユーザーと呼ばれる) に基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="057b0-271">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>
  
<span data-ttu-id="057b0-272">**トップの発信元ユーザーの指標**</span><span class="sxs-lookup"><span data-stu-id="057b0-272">**Metrics for Top From Users**</span></span>

|<span data-ttu-id="057b0-273">**名前**</span><span class="sxs-lookup"><span data-stu-id="057b0-273">**Name**</span></span>|<span data-ttu-id="057b0-274">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="057b0-274">**Can you sort on this item?**</span></span>|<span data-ttu-id="057b0-275">**説明**</span><span class="sxs-lookup"><span data-stu-id="057b0-275">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="057b0-276">**[ランク]**</span><span class="sxs-lookup"><span data-stu-id="057b0-276">**Rank**</span></span> <br/> |<span data-ttu-id="057b0-277">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-277">No</span></span>  <br/> |<span data-ttu-id="057b0-278">セッションに招待されたユーザーに基づく、失敗したセッションの相対的なランク付け。</span><span class="sxs-lookup"><span data-stu-id="057b0-278">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span>  <br/> |
|<span data-ttu-id="057b0-279">**[トップの発信元ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="057b0-279">**Top from users**</span></span> <br/> |<span data-ttu-id="057b0-280">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-280">No</span></span>  <br/> |<span data-ttu-id="057b0-281">セッションに招待されたユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="057b0-281">SIP address of the user invited to join the session.</span></span>  <br/> |
|<span data-ttu-id="057b0-282">**[セッション]**</span><span class="sxs-lookup"><span data-stu-id="057b0-282">**Sessions**</span></span> <br/> |<span data-ttu-id="057b0-283">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-283">No</span></span>  <br/> |<span data-ttu-id="057b0-284">ユーザーごとの失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="057b0-284">Total number of failed sessions per user.</span></span>  <br/> |
   
## <a name="metrics-for-top-to-users"></a><span data-ttu-id="057b0-285">トップの発信先ユーザーの指標</span><span class="sxs-lookup"><span data-stu-id="057b0-285">Metrics for Top To Users</span></span>

<span data-ttu-id="057b0-286">次の表に、ユーザーが他のユーザーを呼び出したときに最もエラーが発生したユーザー ("発信先" ユーザーと呼ばれる) に基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="057b0-286">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>
  
|<span data-ttu-id="057b0-287">**名前**</span><span class="sxs-lookup"><span data-stu-id="057b0-287">**Name**</span></span>|<span data-ttu-id="057b0-288">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="057b0-288">**Can you sort on this item?**</span></span>|<span data-ttu-id="057b0-289">**説明**</span><span class="sxs-lookup"><span data-stu-id="057b0-289">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="057b0-290">**[ランク]**</span><span class="sxs-lookup"><span data-stu-id="057b0-290">**Rank**</span></span> <br/> |<span data-ttu-id="057b0-291">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-291">No</span></span>  <br/> |<span data-ttu-id="057b0-292">セッションを開始したユーザーに基づく、失敗したセッションの相対的なランク付け。</span><span class="sxs-lookup"><span data-stu-id="057b0-292">Relative ranking of failed sessions based on the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="057b0-293">**[トップの発信先ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="057b0-293">**Top to users**</span></span> <br/> |<span data-ttu-id="057b0-294">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-294">No</span></span>  <br/> |<span data-ttu-id="057b0-295">セッションを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="057b0-295">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="057b0-296">**[セッション]**</span><span class="sxs-lookup"><span data-stu-id="057b0-296">**Sessions**</span></span> <br/> |<span data-ttu-id="057b0-297">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-297">No</span></span>  <br/> |<span data-ttu-id="057b0-298">ユーザーごとの失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="057b0-298">Total number of failed sessions per user.</span></span>  <br/> |
   
## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="057b0-299">トップ ユーザー エージェントの指標</span><span class="sxs-lookup"><span data-stu-id="057b0-299">Metrics for Top User Agents</span></span>

<span data-ttu-id="057b0-300">次の表に、最もエラーが発生したエンドポイント ソフトウェアに基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="057b0-300">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>
  
<span data-ttu-id="057b0-301">**トップ ユーザー エージェントの指標**</span><span class="sxs-lookup"><span data-stu-id="057b0-301">**Metrics for Top User Agents**</span></span>

|<span data-ttu-id="057b0-302">**名前**</span><span class="sxs-lookup"><span data-stu-id="057b0-302">**Name**</span></span>|<span data-ttu-id="057b0-303">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="057b0-303">**Can you sort on this item?**</span></span>|<span data-ttu-id="057b0-304">**説明**</span><span class="sxs-lookup"><span data-stu-id="057b0-304">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="057b0-305">**[ランク]**</span><span class="sxs-lookup"><span data-stu-id="057b0-305">**Rank**</span></span> <br/> |<span data-ttu-id="057b0-306">いいえ</span><span class="sxs-lookup"><span data-stu-id="057b0-306">No</span></span>  <br/> |<span data-ttu-id="057b0-p115">セッションに含まれるユーザー エージェント (ソフトウェア) に基づく、失敗したセッションの相対的なランク付け。例: RTCC/4.0.0.0 Inbound Routing/4.0.0.0。</span><span class="sxs-lookup"><span data-stu-id="057b0-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span>  <br/> |
|<span data-ttu-id="057b0-309">**[トップ ユーザー エージェント]**</span><span class="sxs-lookup"><span data-stu-id="057b0-309">**Top user agents**</span></span> <br/> |<span data-ttu-id="057b0-310">不可</span><span class="sxs-lookup"><span data-stu-id="057b0-310">No</span></span>  <br/> |<span data-ttu-id="057b0-311">失敗したセッションに含まれるユーザー エージェントの名前。</span><span class="sxs-lookup"><span data-stu-id="057b0-311">Name of the user agent involved in the failed session.</span></span>  <br/> |
|<span data-ttu-id="057b0-312">**[セッション]**</span><span class="sxs-lookup"><span data-stu-id="057b0-312">**Sessions**</span></span> <br/> |<span data-ttu-id="057b0-313">不可</span><span class="sxs-lookup"><span data-stu-id="057b0-313">No</span></span>  <br/> |<span data-ttu-id="057b0-314">ユーザー エージェントごとの失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="057b0-314">Total number of failed sessions per user agent.</span></span>  <br/> |
   

