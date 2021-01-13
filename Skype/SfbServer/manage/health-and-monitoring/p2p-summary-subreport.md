---
title: Skype for Business Server の P2P 概要サブレポート
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: '概要: Skype for Business Server の P2P 概要サブレポートについて学習します。'
ms.openlocfilehash: 518047fbca3c46cdc9b99299b8222d4f4fbd48ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816817"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a><span data-ttu-id="5f782-103">Skype for Business Server の P2P 概要サブレポート</span><span class="sxs-lookup"><span data-stu-id="5f782-103">P2P Summary Subreport in Skype for Business Server</span></span>
 
<span data-ttu-id="5f782-104">**概要:** Skype for Business Server の P2P 概要サブレポートについて学習します。</span><span class="sxs-lookup"><span data-stu-id="5f782-104">**Summary:** Learn about the P2P Summary Subreport in Skype for Business Server.</span></span>
  
<span data-ttu-id="5f782-105">P2P 概要サブレポートは、エラーが発生したピアツーピア セッションの総合的な概要を示します。</span><span class="sxs-lookup"><span data-stu-id="5f782-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>
  
## <a name="filters"></a><span data-ttu-id="5f782-106">フィルター</span><span class="sxs-lookup"><span data-stu-id="5f782-106">Filters</span></span>

<span data-ttu-id="5f782-p101">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。次の表に、P2P 概要サブレポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="5f782-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="5f782-109">**P2P 概要サブレポートのフィルター**</span><span class="sxs-lookup"><span data-stu-id="5f782-109">**P2P Summary Subreport Filters**</span></span>

|<span data-ttu-id="5f782-110">**名前**</span><span class="sxs-lookup"><span data-stu-id="5f782-110">**Name**</span></span>|<span data-ttu-id="5f782-111">**説明**</span><span class="sxs-lookup"><span data-stu-id="5f782-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5f782-112">**From**</span><span class="sxs-lookup"><span data-stu-id="5f782-112">**From**</span></span> <br/> |<span data-ttu-id="5f782-p102">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f782-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="5f782-115">2015 年 7 月 7 日午後 1 時</span><span class="sxs-lookup"><span data-stu-id="5f782-115">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="5f782-p103">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="5f782-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="5f782-118">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="5f782-118">7/7/2015</span></span>  <br/> <span data-ttu-id="5f782-119">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="5f782-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="5f782-120">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="5f782-120">7/3/2015</span></span>  <br/> <span data-ttu-id="5f782-121">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="5f782-121">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="5f782-122">**To**</span><span class="sxs-lookup"><span data-stu-id="5f782-122">**To**</span></span> <br/> |<span data-ttu-id="5f782-p104">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f782-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="5f782-125">2015 年 7 月 7 日午後 1 時</span><span class="sxs-lookup"><span data-stu-id="5f782-125">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="5f782-p105">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="5f782-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="5f782-128">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="5f782-128">7/7/2015</span></span>  <br/> <span data-ttu-id="5f782-129">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="5f782-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="5f782-130">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="5f782-130">7/3/2015</span></span>  <br/> <span data-ttu-id="5f782-131">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="5f782-131">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="5f782-132">**Pool**</span><span class="sxs-lookup"><span data-stu-id="5f782-132">**Pool**</span></span> <br/> |<span data-ttu-id="5f782-p106">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[**すべて**] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5f782-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click **[All]** to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database. </span></span><br/> |
   
## <a name="metrics"></a><span data-ttu-id="5f782-136">指標</span><span class="sxs-lookup"><span data-stu-id="5f782-136">Metrics</span></span>

<span data-ttu-id="5f782-137">次の表に、P2P 概要サブレポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="5f782-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="5f782-138">**P2P 概要サブレポートの指標**</span><span class="sxs-lookup"><span data-stu-id="5f782-138">**P2P Summary Subreport Metrics**</span></span>

|<span data-ttu-id="5f782-139">**名前**</span><span class="sxs-lookup"><span data-stu-id="5f782-139">**Name**</span></span>|<span data-ttu-id="5f782-140">**このアイテムを並べ替えることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="5f782-140">**Can you sort on this item?**</span></span>|<span data-ttu-id="5f782-141">**説明**</span><span class="sxs-lookup"><span data-stu-id="5f782-141">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5f782-142">[**セッションの合計数**]</span><span class="sxs-lookup"><span data-stu-id="5f782-142">**Total sessions**</span></span> <br/> |<span data-ttu-id="5f782-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="5f782-143">No</span></span>  <br/> |<span data-ttu-id="5f782-144">セッションの総数です。成功したセッション、失敗したセッション (予期されるエラーと予期しないエラーの両方)、およびどちらにも分類されないセッションを含みます。</span><span class="sxs-lookup"><span data-stu-id="5f782-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span>  <br/> |
|<span data-ttu-id="5f782-145">[**エラー率**]</span><span class="sxs-lookup"><span data-stu-id="5f782-145">**Failure rate**</span></span> <br/> |<span data-ttu-id="5f782-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="5f782-146">No</span></span>  <br/> |<span data-ttu-id="5f782-147">エラーが発生したピアツーピア セッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="5f782-147">Percentage of peer-to-peer sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="5f782-148">[**モダリティ別セッション**]</span><span class="sxs-lookup"><span data-stu-id="5f782-148">**Sessions by Modality**</span></span> <br/> |<span data-ttu-id="5f782-149">いいえ</span><span class="sxs-lookup"><span data-stu-id="5f782-149">No</span></span>  <br/> |<span data-ttu-id="5f782-150">モダリティによってグループ化されたセッションの合計数 (たとえば、インスタント メッセージング)。</span><span class="sxs-lookup"><span data-stu-id="5f782-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
|<span data-ttu-id="5f782-151">[**モダリティ別エラー率**]</span><span class="sxs-lookup"><span data-stu-id="5f782-151">**Failure rate by modality**</span></span> <br/> |<span data-ttu-id="5f782-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="5f782-152">No</span></span>  <br/> |<span data-ttu-id="5f782-153">モダリティによってグループ化された失敗したセッションの合計数 (たとえば、インスタント メッセージング)。</span><span class="sxs-lookup"><span data-stu-id="5f782-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
   

