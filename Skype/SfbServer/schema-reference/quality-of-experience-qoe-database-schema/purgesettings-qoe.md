---
title: PurgeSettings テーブル (QoE)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings テーブルには、(そのとき) を指定する情報が含まれている高品質のエクスペリエンスの古いレコードは QoE データベースから自動的に削除されます。 パージに関連する情報もから取得できます、Skype 内でビジネス サーバー管理シェルの次のコマンドを実行して、注意してください。
ms.openlocfilehash: 2b78f066907d6d0763fab7faa9d378e51f3715fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924788"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="5c374-104">PurgeSettings テーブル (QoE)</span><span class="sxs-lookup"><span data-stu-id="5c374-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="5c374-105">PurgeSettings テーブルには、(そのとき) を指定する情報が含まれている高品質のエクスペリエンスの古いレコードは QoE データベースから自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="5c374-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="5c374-106">パージに関連する情報もから取得できます、Skype 内でビジネス サーバー管理シェルの次のコマンドを実行して、注意してください。</span><span class="sxs-lookup"><span data-stu-id="5c374-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```
Get-CsQoEConfiguration
```

<span data-ttu-id="5c374-107">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5c374-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5c374-108">**列**</span><span class="sxs-lookup"><span data-stu-id="5c374-108">**Column**</span></span>|<span data-ttu-id="5c374-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5c374-109">**Data Type**</span></span>|<span data-ttu-id="5c374-110">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="5c374-110">**Key/Index**</span></span>|<span data-ttu-id="5c374-111">**詳細**</span><span class="sxs-lookup"><span data-stu-id="5c374-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5c374-112">**ID**</span><span class="sxs-lookup"><span data-stu-id="5c374-112">**ID**</span></span> <br/> |<span data-ttu-id="5c374-113">int</span><span class="sxs-lookup"><span data-stu-id="5c374-113">int</span></span>  <br/> |<span data-ttu-id="5c374-114">Primary</span><span class="sxs-lookup"><span data-stu-id="5c374-114">Primary</span></span>  <br/> |<span data-ttu-id="5c374-115">QoE のコレクションの一意の識別子は、設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="5c374-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="5c374-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="5c374-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="5c374-117">bit</span><span class="sxs-lookup"><span data-stu-id="5c374-117">bit</span></span>  <br/> ||<span data-ttu-id="5c374-118">(1) は、Microsoft Lync Server 2013 を True に設定が QoE データベースから古いレコードを定期的に削除するができます。</span><span class="sxs-lookup"><span data-stu-id="5c374-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="5c374-119">パージ実行されます PurgeHour 設定で指定されたサントメ毎日。</span><span class="sxs-lookup"><span data-stu-id="5c374-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="5c374-120">場合は False (0) のレコード セットはデータベースから自動的にパージされません。</span><span class="sxs-lookup"><span data-stu-id="5c374-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="5c374-121">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="5c374-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="5c374-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="5c374-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="5c374-123">int</span><span class="sxs-lookup"><span data-stu-id="5c374-123">int</span></span>  <br/> ||<span data-ttu-id="5c374-124">(日) で、データベースからパージされる QoE レコードの保存期間を指定: QoE レコードがこの値よりも古いをデータベースから削除する場合は、パージを有効にすると、します。</span><span class="sxs-lookup"><span data-stu-id="5c374-124">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="5c374-125">既定値は、60 日間です。</span><span class="sxs-lookup"><span data-stu-id="5c374-125">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="5c374-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="5c374-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="5c374-127">int</span><span class="sxs-lookup"><span data-stu-id="5c374-127">int</span></span>  <br/> ||<span data-ttu-id="5c374-128">データベースの削除を実行する日のローカル時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c374-128">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="5c374-129">時刻は、午前 0 時 (12時 00分 AM) と 23 の 11時 00分 PM を表すを表す 0 から 24 時間制を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="5c374-129">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="5c374-130">1 日の時間を指定することのみできます注: 10 の (10時 00分 AM を示す) の値も可能ですが、10:30 (10時 30分 AM を示す) 10.5 の値は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="5c374-130">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="5c374-131">既定値は 1 (1時 00分 AM) です。</span><span class="sxs-lookup"><span data-stu-id="5c374-131">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="5c374-132">データベースの削除を実行する日のローカル時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c374-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="5c374-133">時刻は、午前 0 時 (12時 00分 AM) と 23 の 11時 00分 PM を表すを表す 0 から 24 時間制を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="5c374-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="5c374-134">1 日の時間を指定することのみできます注: 10 の (10時 00分 AM を示す) の値も可能ですが、10:30 (10時 30分 AM を示す) 10.5 の値は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="5c374-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="5c374-135">既定値は 1 (1時 00分 AM) です。</span><span class="sxs-lookup"><span data-stu-id="5c374-135">The default value is 1 (1:00 AM).</span></span>  <br/> |
   

