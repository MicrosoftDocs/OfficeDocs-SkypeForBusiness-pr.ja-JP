---
title: PurgeSettings table (QoE)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings テーブルには、古い品質のエクスペリエンスレコードが QoE データベースから自動的に削除されるかどうかを指定する情報が含まれています。 次のコマンドを実行して、Skype for Business Server 管理シェルからパージに関連する情報を取得することもできます。
ms.openlocfilehash: dab1b2ffeab5882d0e459d7957b2817e780fc3a4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807335"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="425b5-104">PurgeSettings table (QoE)</span><span class="sxs-lookup"><span data-stu-id="425b5-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="425b5-105">PurgeSettings テーブルには、古い品質のエクスペリエンスレコードが QoE データベースから自動的に削除されるかどうかを指定する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="425b5-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="425b5-106">次のコマンドを実行して、Skype for Business Server 管理シェルからパージに関連する情報を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="425b5-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```PowerShell
Get-CsQoEConfiguration
```

<span data-ttu-id="425b5-107">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="425b5-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="425b5-108">**列**</span><span class="sxs-lookup"><span data-stu-id="425b5-108">**Column**</span></span>|<span data-ttu-id="425b5-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="425b5-109">**Data Type**</span></span>|<span data-ttu-id="425b5-110">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="425b5-110">**Key/Index**</span></span>|<span data-ttu-id="425b5-111">**詳細**</span><span class="sxs-lookup"><span data-stu-id="425b5-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="425b5-112">**ID**</span><span class="sxs-lookup"><span data-stu-id="425b5-112">**ID**</span></span> <br/> |<span data-ttu-id="425b5-113">int</span><span class="sxs-lookup"><span data-stu-id="425b5-113">int</span></span>  <br/> |<span data-ttu-id="425b5-114">Primary</span><span class="sxs-lookup"><span data-stu-id="425b5-114">Primary</span></span>  <br/> |<span data-ttu-id="425b5-115">QoE の消去設定のコレクションの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="425b5-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="425b5-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="425b5-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="425b5-117">bit</span><span class="sxs-lookup"><span data-stu-id="425b5-117">bit</span></span>  <br/> ||<span data-ttu-id="425b5-118">True (1) に設定すると、Microsoft Lync Server 2013 は、古いレコードを QoE データベースから定期的に削除します。</span><span class="sxs-lookup"><span data-stu-id="425b5-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="425b5-119">パージは、PurgeHour 設定によって指定されたサントメで毎日行われます。</span><span class="sxs-lookup"><span data-stu-id="425b5-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="425b5-120">False (0) に設定すると、レコードはデータベースから自動的に削除されません。</span><span class="sxs-lookup"><span data-stu-id="425b5-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="425b5-121">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="425b5-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="425b5-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="425b5-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="425b5-123">int</span><span class="sxs-lookup"><span data-stu-id="425b5-123">int</span></span>  <br/> ||<span data-ttu-id="425b5-124">データベースから削除される QoE レコード (日数) を指定します。 [削除] が有効になっていると、この値よりも古い QoE レコードはデータベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="425b5-124">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="425b5-125">既定値は60日です。</span><span class="sxs-lookup"><span data-stu-id="425b5-125">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="425b5-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="425b5-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="425b5-127">int</span><span class="sxs-lookup"><span data-stu-id="425b5-127">int</span></span>  <br/> ||<span data-ttu-id="425b5-128">データベースの消去が行われるローカル時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="425b5-128">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="425b5-129">時刻は24時間制を使用して指定します。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。</span><span class="sxs-lookup"><span data-stu-id="425b5-129">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="425b5-130">時刻を指定できるのは1日の時間のみです。10の値 (10:00 AM) は許可されていますが、10.5 の 10:30 (10:30 AM を示す) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="425b5-130">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="425b5-131">既定値は 1 (1:00 AM) です。</span><span class="sxs-lookup"><span data-stu-id="425b5-131">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="425b5-132">データベースの消去が行われるローカル時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="425b5-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="425b5-133">時刻は24時間制を使用して指定します。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。</span><span class="sxs-lookup"><span data-stu-id="425b5-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="425b5-134">時刻を指定できるのは1日の時間のみです。10の値 (10:00 AM) は許可されていますが、10.5 の 10:30 (10:30 AM を示す) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="425b5-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="425b5-135">既定値は 1 (1:00 AM) です。</span><span class="sxs-lookup"><span data-stu-id="425b5-135">The default value is 1 (1:00 AM).</span></span>  <br/> |
   

