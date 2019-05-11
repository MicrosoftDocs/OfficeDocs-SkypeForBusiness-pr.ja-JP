---
title: PurgeSettings テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings テーブルには、(そのとき) を指定する情報が含まれている旧式の呼び出しの詳細レコードが CDR データベースから自動的に削除されます。 パージに関連する情報もから取得できます、Skype 内でビジネス サーバー 2015 の次のコマンドを実行して、注意してください。
ms.openlocfilehash: f1e982d50ab029ec2756e8fb4a92f5c01dc327b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930722"
---
# <a name="purgesettings-table"></a><span data-ttu-id="09e51-104">PurgeSettings テーブル</span><span class="sxs-lookup"><span data-stu-id="09e51-104">PurgeSettings table</span></span>
 
<span data-ttu-id="09e51-105">PurgeSettings テーブルには、(そのとき) を指定する情報が含まれている旧式の呼び出しの詳細レコードが CDR データベースから自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="09e51-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="09e51-106">パージに関連する情報もから取得できます、Skype 内でビジネス サーバー 2015 の次のコマンドを実行して、注意してください。</span><span class="sxs-lookup"><span data-stu-id="09e51-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```
Get-CsCdrConfiguration
```

<span data-ttu-id="09e51-107">管理者は、読み取り専用で PurgeSettings テーブルを扱う必要があります: への呼び出しの詳細のパージ設定のみ変更してください[新規 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)または[セット CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="09e51-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="09e51-108">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="09e51-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="09e51-109">**列**</span><span class="sxs-lookup"><span data-stu-id="09e51-109">**Column**</span></span>|<span data-ttu-id="09e51-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="09e51-110">**Data Type**</span></span>|<span data-ttu-id="09e51-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="09e51-111">**Key/Index**</span></span>|<span data-ttu-id="09e51-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="09e51-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09e51-113">**Id**</span><span class="sxs-lookup"><span data-stu-id="09e51-113">**Id**</span></span> <br/> |<span data-ttu-id="09e51-114">int</span><span class="sxs-lookup"><span data-stu-id="09e51-114">int</span></span>  <br/> |<span data-ttu-id="09e51-115">Primary</span><span class="sxs-lookup"><span data-stu-id="09e51-115">Primary</span></span>  <br/> |<span data-ttu-id="09e51-116">CDR のコレクションの一意の識別子は、設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="09e51-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="09e51-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="09e51-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="09e51-118">bit</span><span class="sxs-lookup"><span data-stu-id="09e51-118">bit</span></span>  <br/> ||<span data-ttu-id="09e51-119">CDR データベースからレコードを古い設定すると (1) Skype ビジネス サーバー 2015 の true を設定するのには定期的に削除します。</span><span class="sxs-lookup"><span data-stu-id="09e51-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="09e51-120">パージ実行されます PurgeHour 設定で指定されたサントメ毎日。</span><span class="sxs-lookup"><span data-stu-id="09e51-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="09e51-121">場合は False (0) のレコード セットはデータベースから自動的にパージされません。</span><span class="sxs-lookup"><span data-stu-id="09e51-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="09e51-122">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="09e51-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="09e51-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="09e51-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="09e51-124">int</span><span class="sxs-lookup"><span data-stu-id="09e51-124">int</span></span>  <br/> ||<span data-ttu-id="09e51-125">データベースから削除されます (日) での CDR レコードの保存期間を指定: CDR レコードがこの値よりも古いをデータベースから削除する場合は、パージを有効にすると、します。</span><span class="sxs-lookup"><span data-stu-id="09e51-125">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="09e51-126">既定値は、60 日間です。</span><span class="sxs-lookup"><span data-stu-id="09e51-126">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="09e51-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="09e51-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="09e51-128">int</span><span class="sxs-lookup"><span data-stu-id="09e51-128">int</span></span>  <br/> ||<span data-ttu-id="09e51-129">データベースから削除されます (日) でエラー レポート レコードの保存期間を指定します。 エラー レポートのレコードがこの値よりも古いをデータベースから削除する場合は、パージを有効にすると、します。</span><span class="sxs-lookup"><span data-stu-id="09e51-129">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="09e51-130">既定値は、60 日間です。</span><span class="sxs-lookup"><span data-stu-id="09e51-130">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="09e51-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="09e51-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="09e51-132">int</span><span class="sxs-lookup"><span data-stu-id="09e51-132">int</span></span>  <br/> ||<span data-ttu-id="09e51-133">データベースの削除を実行する日のローカル時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="09e51-133">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="09e51-134">時刻は、午前 0 時 (12時 00分 AM) と 23 の 11時 00分 PM を表すを表す 0 から 24 時間制を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="09e51-134">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="09e51-135">1 日の時間を指定することのみできます注: 10 の (10時 00分 AM を示す) の値も可能ですが、10:30 (10時 30分 AM を示す) 10.5 の値は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="09e51-135">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="09e51-136">既定値は、2 (2時 00分 AM) です。</span><span class="sxs-lookup"><span data-stu-id="09e51-136">The default value is 2 (2:00 AM).</span></span>  <br/> |
   

