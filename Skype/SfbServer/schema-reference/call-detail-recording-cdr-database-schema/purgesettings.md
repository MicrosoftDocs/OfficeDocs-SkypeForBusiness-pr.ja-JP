---
title: PurgeSettings テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings テーブルには、古い通話の詳細レコードが CDR データベースから自動的に削除されるかどうかを指定する情報が含まれています。 次のコマンドを実行して、Skype for Business Server 2015 内からパージに関連する情報を取得することもできます。
ms.openlocfilehash: 81e702a4d62b4c85fb849a768c97428719ddc391
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814965"
---
# <a name="purgesettings-table"></a><span data-ttu-id="eebb2-104">PurgeSettings テーブル</span><span class="sxs-lookup"><span data-stu-id="eebb2-104">PurgeSettings table</span></span>
 
<span data-ttu-id="eebb2-105">PurgeSettings テーブルには、古い通話の詳細レコードが CDR データベースから自動的に削除されるかどうかを指定する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eebb2-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="eebb2-106">次のコマンドを実行して、Skype for Business Server 2015 内からパージに関連する情報を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="eebb2-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```PowerShell
Get-CsCdrConfiguration
```

<span data-ttu-id="eebb2-107">管理者は、PurgeSettings テーブルを読み取り専用として扱う必要があります。呼び出しの詳細の消去設定への変更は、 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)または[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)コマンドレットを使用して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="eebb2-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="eebb2-108">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="eebb2-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="eebb2-109">**列**</span><span class="sxs-lookup"><span data-stu-id="eebb2-109">**Column**</span></span>|<span data-ttu-id="eebb2-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="eebb2-110">**Data Type**</span></span>|<span data-ttu-id="eebb2-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="eebb2-111">**Key/Index**</span></span>|<span data-ttu-id="eebb2-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="eebb2-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eebb2-113">**ID**</span><span class="sxs-lookup"><span data-stu-id="eebb2-113">**Id**</span></span> <br/> |<span data-ttu-id="eebb2-114">int</span><span class="sxs-lookup"><span data-stu-id="eebb2-114">int</span></span>  <br/> |<span data-ttu-id="eebb2-115">Primary</span><span class="sxs-lookup"><span data-stu-id="eebb2-115">Primary</span></span>  <br/> |<span data-ttu-id="eebb2-116">CDR 消去設定のコレクションの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="eebb2-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="eebb2-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="eebb2-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="eebb2-118">bit</span><span class="sxs-lookup"><span data-stu-id="eebb2-118">bit</span></span>  <br/> ||<span data-ttu-id="eebb2-119">True に設定すると、Skype for Business Server 2015 は、古いレコードを CDR データベースから定期的に削除します。</span><span class="sxs-lookup"><span data-stu-id="eebb2-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="eebb2-120">パージは、PurgeHour 設定によって指定されたサントメで毎日行われます。</span><span class="sxs-lookup"><span data-stu-id="eebb2-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="eebb2-121">False (0) に設定すると、レコードはデータベースから自動的に削除されません。</span><span class="sxs-lookup"><span data-stu-id="eebb2-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="eebb2-122">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="eebb2-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="eebb2-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="eebb2-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="eebb2-124">int</span><span class="sxs-lookup"><span data-stu-id="eebb2-124">int</span></span>  <br/> ||<span data-ttu-id="eebb2-125">データベースから削除される CDR レコード (日数) を指定します。 [削除] が有効になっていると、この値よりも古い CDR レコードがデータベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="eebb2-125">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="eebb2-126">既定値は60日です。</span><span class="sxs-lookup"><span data-stu-id="eebb2-126">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="eebb2-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="eebb2-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="eebb2-128">int</span><span class="sxs-lookup"><span data-stu-id="eebb2-128">int</span></span>  <br/> ||<span data-ttu-id="eebb2-129">データベースから削除されるエラーレポートレコード (日数) を指定します。 [削除] を有効にすると、この値よりも古いエラーレポートレコードがデータベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="eebb2-129">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="eebb2-130">既定値は60日です。</span><span class="sxs-lookup"><span data-stu-id="eebb2-130">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="eebb2-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="eebb2-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="eebb2-132">int</span><span class="sxs-lookup"><span data-stu-id="eebb2-132">int</span></span>  <br/> ||<span data-ttu-id="eebb2-133">データベースの消去が行われるローカル時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="eebb2-133">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="eebb2-134">時刻は24時間制を使用して指定します。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。</span><span class="sxs-lookup"><span data-stu-id="eebb2-134">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="eebb2-135">時刻を指定できるのは1日の時間のみです。10の値 (10:00 AM) は許可されていますが、10.5 の 10:30 (10:30 AM を示す) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="eebb2-135">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="eebb2-136">既定値は 2 (2:00 AM) です。</span><span class="sxs-lookup"><span data-stu-id="eebb2-136">The default value is 2 (2:00 AM).</span></span>  <br/> |
   

