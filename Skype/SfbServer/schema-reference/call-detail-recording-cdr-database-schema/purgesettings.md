---
title: PurgeSettings テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings テーブルには、古い通話詳細レコードが CDR データベースから自動的に削除される場合 (およびいつ) を指定する情報が含まれます。 次のコマンドを実行すると、Skype for Business Server 2015 内から削除関連の情報を取得することもできます。
ms.openlocfilehash: 2e834f64ca5500f8d8bab1d89fb263d2708fa60c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098663"
---
# <a name="purgesettings-table"></a><span data-ttu-id="45a44-104">PurgeSettings テーブル</span><span class="sxs-lookup"><span data-stu-id="45a44-104">PurgeSettings table</span></span>
 
<span data-ttu-id="45a44-105">PurgeSettings テーブルには、古い通話詳細レコードが CDR データベースから自動的に削除される場合 (およびいつ) を指定する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="45a44-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="45a44-106">次のコマンドを実行すると、Skype for Business Server 2015 内から削除関連の情報を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="45a44-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```PowerShell
Get-CsCdrConfiguration
```

<span data-ttu-id="45a44-107">管理者は PurgeSettings テーブルを読み取り専用として扱う必要があります。呼び出しの詳細の削除設定の変更は [、New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) コマンドレットまたは [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) コマンドレットのみを使用して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="45a44-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="45a44-108">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="45a44-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="45a44-109">**列**</span><span class="sxs-lookup"><span data-stu-id="45a44-109">**Column**</span></span>|<span data-ttu-id="45a44-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="45a44-110">**Data Type**</span></span>|<span data-ttu-id="45a44-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="45a44-111">**Key/Index**</span></span>|<span data-ttu-id="45a44-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="45a44-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45a44-113">
  **Id**</span><span class="sxs-lookup"><span data-stu-id="45a44-113">**Id**</span></span> <br/> |<span data-ttu-id="45a44-114">int</span><span class="sxs-lookup"><span data-stu-id="45a44-114">int</span></span>  <br/> |<span data-ttu-id="45a44-115">Primary</span><span class="sxs-lookup"><span data-stu-id="45a44-115">Primary</span></span>  <br/> |<span data-ttu-id="45a44-116">CDR パージ設定のコレクションの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="45a44-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="45a44-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="45a44-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="45a44-118">ビット</span><span class="sxs-lookup"><span data-stu-id="45a44-118">bit</span></span>  <br/> ||<span data-ttu-id="45a44-119">True (1) Skype for Business Server 2015 に設定すると、古いレコードが CDR データベースから定期的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="45a44-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="45a44-120">削除は、毎日、PurgeHour 設定で指定された時間に行われます。</span><span class="sxs-lookup"><span data-stu-id="45a44-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="45a44-121">False (0) に設定すると、レコードがデータベースから自動的に削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="45a44-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="45a44-122">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="45a44-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="45a44-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="45a44-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="45a44-124">int</span><span class="sxs-lookup"><span data-stu-id="45a44-124">int</span></span>  <br/> ||<span data-ttu-id="45a44-125">データベースから削除される CDR レコードの年齢 (日数) を指定します。削除が有効な場合、この値より古い CDR レコードはデータベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="45a44-125">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="45a44-126">既定値は 60 日です。</span><span class="sxs-lookup"><span data-stu-id="45a44-126">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="45a44-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="45a44-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="45a44-128">int</span><span class="sxs-lookup"><span data-stu-id="45a44-128">int</span></span>  <br/> ||<span data-ttu-id="45a44-129">データベースから削除されるエラー レポート レコードの日数を指定します。削除が有効な場合、この値より古いエラー レポート レコードはデータベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="45a44-129">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="45a44-130">既定値は 60 日です。</span><span class="sxs-lookup"><span data-stu-id="45a44-130">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="45a44-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="45a44-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="45a44-132">int</span><span class="sxs-lookup"><span data-stu-id="45a44-132">int</span></span>  <br/> ||<span data-ttu-id="45a44-133">データベース削除が行なうローカル時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="45a44-133">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="45a44-134">時刻は 24 時間時計を使用して指定され、0 は午前 0 時 (午前 12:00)、23 は午後 11:00 を表します。</span><span class="sxs-lookup"><span data-stu-id="45a44-134">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="45a44-135">1 日の時間のみを指定できますが、値 10 (午前 10:00 を示す) は許可されますが、10.5 の値 10:30 (午前 10:30 を示す) は使用できない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="45a44-135">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="45a44-136">既定値は 2 (午前 2 時) です。</span><span class="sxs-lookup"><span data-stu-id="45a44-136">The default value is 2 (2:00 AM).</span></span>  <br/> |
