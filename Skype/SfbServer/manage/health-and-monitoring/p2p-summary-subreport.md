---
title: ビジネス サーバーの Skype での P2P 概要サブレポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: '概要: は、ビジネスのサーバーに、Skype の P2P 概要サブレポートについて説明します。'
ms.openlocfilehash: 019682818d25fcd0088cb47fe51e12a17b9ce1bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915819"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a><span data-ttu-id="63bf4-103">ビジネス サーバーの Skype での P2P 概要サブレポート</span><span class="sxs-lookup"><span data-stu-id="63bf4-103">P2P Summary Subreport in Skype for Business Server</span></span>
 
<span data-ttu-id="63bf4-104">**の概要:** Business Server には、Skype の P2P 概要サブレポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="63bf4-104">**Summary:** Learn about the P2P Summary Subreport in Skype for Business Server.</span></span>
  
<span data-ttu-id="63bf4-105">P2P 概要サブレポートは、エラーが発生したピアツーピア セッションの総合的な概要を示します。</span><span class="sxs-lookup"><span data-stu-id="63bf4-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>
  
## <a name="filters"></a><span data-ttu-id="63bf4-106">フィルター</span><span class="sxs-lookup"><span data-stu-id="63bf4-106">Filters</span></span>

<span data-ttu-id="63bf4-p101">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。次の表に、P2P 概要サブレポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="63bf4-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="63bf4-109">**P2P 概要サブレポートのフィルター**</span><span class="sxs-lookup"><span data-stu-id="63bf4-109">**P2P Summary Subreport Filters**</span></span>

|<span data-ttu-id="63bf4-110">**名前**</span><span class="sxs-lookup"><span data-stu-id="63bf4-110">**Name**</span></span>|<span data-ttu-id="63bf4-111">**説明**</span><span class="sxs-lookup"><span data-stu-id="63bf4-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="63bf4-112">**開始**</span><span class="sxs-lookup"><span data-stu-id="63bf4-112">**From**</span></span> <br/> |<span data-ttu-id="63bf4-p102">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="63bf4-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="63bf4-115">7/7/2015 13:00</span><span class="sxs-lookup"><span data-stu-id="63bf4-115">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="63bf4-p103">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="63bf4-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="63bf4-118">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="63bf4-118">7/7/2015</span></span>  <br/> <span data-ttu-id="63bf4-119">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="63bf4-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="63bf4-120">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="63bf4-120">7/3/2015</span></span>  <br/> <span data-ttu-id="63bf4-121">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="63bf4-121">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="63bf4-122">**終了**</span><span class="sxs-lookup"><span data-stu-id="63bf4-122">**To**</span></span> <br/> |<span data-ttu-id="63bf4-p104">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="63bf4-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="63bf4-125">7/7/2015 13:00</span><span class="sxs-lookup"><span data-stu-id="63bf4-125">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="63bf4-p105">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="63bf4-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="63bf4-128">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="63bf4-128">7/7/2015</span></span>  <br/> <span data-ttu-id="63bf4-129">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="63bf4-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="63bf4-130">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="63bf4-130">7/3/2015</span></span>  <br/> <span data-ttu-id="63bf4-131">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="63bf4-131">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="63bf4-132">**プール**</span><span class="sxs-lookup"><span data-stu-id="63bf4-132">**Pool**</span></span> <br/> |<span data-ttu-id="63bf4-p106">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[**すべて**] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="63bf4-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click **[All]** to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database. </span></span><br/> |
   
## <a name="metrics"></a><span data-ttu-id="63bf4-136">指標</span><span class="sxs-lookup"><span data-stu-id="63bf4-136">Metrics</span></span>

<span data-ttu-id="63bf4-137">次の表に、P2P 概要サブレポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="63bf4-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="63bf4-138">**P2P 概要サブレポートの指標**</span><span class="sxs-lookup"><span data-stu-id="63bf4-138">**P2P Summary Subreport Metrics**</span></span>

|<span data-ttu-id="63bf4-139">**名前**</span><span class="sxs-lookup"><span data-stu-id="63bf4-139">**Name**</span></span>|<span data-ttu-id="63bf4-140">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="63bf4-140">**Can you sort on this item?**</span></span>|<span data-ttu-id="63bf4-141">**説明**</span><span class="sxs-lookup"><span data-stu-id="63bf4-141">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63bf4-142">**セッションの合計数**</span><span class="sxs-lookup"><span data-stu-id="63bf4-142">**Total sessions**</span></span> <br/> |<span data-ttu-id="63bf4-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="63bf4-143">No</span></span>  <br/> |<span data-ttu-id="63bf4-144">セッションの総数です。成功したセッション、失敗したセッション (予期されるエラーと予期しないエラーの両方)、およびどちらにも分類されないセッションを含みます。</span><span class="sxs-lookup"><span data-stu-id="63bf4-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span>  <br/> |
|<span data-ttu-id="63bf4-145">**エラー率**</span><span class="sxs-lookup"><span data-stu-id="63bf4-145">**Failure rate**</span></span> <br/> |<span data-ttu-id="63bf4-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="63bf4-146">No</span></span>  <br/> |<span data-ttu-id="63bf4-147">エラーが発生したピアツーピア セッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="63bf4-147">Percentage of peer-to-peer sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="63bf4-148">**セッション (モダリティ別)**</span><span class="sxs-lookup"><span data-stu-id="63bf4-148">**Sessions by Modality**</span></span> <br/> |<span data-ttu-id="63bf4-149">不可</span><span class="sxs-lookup"><span data-stu-id="63bf4-149">No</span></span>  <br/> |<span data-ttu-id="63bf4-150">モダリティによってグループ化されたセッションの合計数 (たとえば、インスタント メッセージング)。</span><span class="sxs-lookup"><span data-stu-id="63bf4-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
|<span data-ttu-id="63bf4-151">**エラー率 (モダリティ別)**</span><span class="sxs-lookup"><span data-stu-id="63bf4-151">**Failure rate by modality**</span></span> <br/> |<span data-ttu-id="63bf4-152">不可</span><span class="sxs-lookup"><span data-stu-id="63bf4-152">No</span></span>  <br/> |<span data-ttu-id="63bf4-153">モダリティによってグループ化された失敗したセッションの合計数 (たとえば、インスタント メッセージング)。</span><span class="sxs-lookup"><span data-stu-id="63bf4-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
   

