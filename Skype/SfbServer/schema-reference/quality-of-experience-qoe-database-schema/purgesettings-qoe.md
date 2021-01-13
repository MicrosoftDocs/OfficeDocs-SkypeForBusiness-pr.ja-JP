---
title: PurgeSettings テーブル (QoE)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings テーブルには、古い QoE レコードを QoE データベースから自動的に削除するか、また削除する場合はどのタイミングで削除するかを指定する情報が含まれます。 削除に関連する情報は、次のコマンドを実行して Skype for Business Server 管理シェルから取得することもできます。
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815807"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="c901b-104">PurgeSettings テーブル (QoE)</span><span class="sxs-lookup"><span data-stu-id="c901b-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="c901b-105">PurgeSettings テーブルには、古い QoE レコードを QoE データベースから自動的に削除するか、また削除する場合はどのタイミングで削除するかを指定する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c901b-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="c901b-106">削除に関連する情報は、次のコマンドを実行して Skype for Business Server 管理シェル内から取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="c901b-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```PowerShell
Get-CsQoEConfiguration
```

<span data-ttu-id="c901b-107">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c901b-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c901b-108">**列**</span><span class="sxs-lookup"><span data-stu-id="c901b-108">**Column**</span></span>|<span data-ttu-id="c901b-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c901b-109">**Data Type**</span></span>|<span data-ttu-id="c901b-110">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="c901b-110">**Key/Index**</span></span>|<span data-ttu-id="c901b-111">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c901b-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c901b-112">**ID**</span><span class="sxs-lookup"><span data-stu-id="c901b-112">**ID**</span></span> <br/> |<span data-ttu-id="c901b-113">int</span><span class="sxs-lookup"><span data-stu-id="c901b-113">int</span></span>  <br/> |<span data-ttu-id="c901b-114">Primary</span><span class="sxs-lookup"><span data-stu-id="c901b-114">Primary</span></span>  <br/> |<span data-ttu-id="c901b-115">QoE の削除設定のコレクションに対する一意識別子。</span><span class="sxs-lookup"><span data-stu-id="c901b-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="c901b-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="c901b-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="c901b-117">bit</span><span class="sxs-lookup"><span data-stu-id="c901b-117">bit</span></span>  <br/> ||<span data-ttu-id="c901b-118">True (1) に設定すると、Microsoft Lync Server 2013 は QoE データベースから古いレコードを定期的に削除します。</span><span class="sxs-lookup"><span data-stu-id="c901b-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="c901b-119">削除は、毎日、PurgeHour 設定で指定された時間に行われます。</span><span class="sxs-lookup"><span data-stu-id="c901b-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="c901b-120">False (0) に設定すると、レコードがデータベースから自動的に削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c901b-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="c901b-121">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="c901b-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="c901b-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="c901b-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="c901b-123">int</span><span class="sxs-lookup"><span data-stu-id="c901b-123">int</span></span>  <br/> ||<span data-ttu-id="c901b-p104">データベースから削除する QoE レコードの保有期間を (日単位で) 指定します。削除が有効の場合、この値より古い QoE レコードはデータベースから削除されます。既定値は 60 日です。</span><span class="sxs-lookup"><span data-stu-id="c901b-p104">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="c901b-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="c901b-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="c901b-127">int</span><span class="sxs-lookup"><span data-stu-id="c901b-127">int</span></span>  <br/> ||<span data-ttu-id="c901b-p105">データベースでの削除が行われる日のローカル時間を指定します。時刻は 24 時間制を使用して指定します。0 は夜中 12 時 (12:00 AM) を、23 は 11:00 PM を表します。指定できるのは時間のみです。(午前 10 時 00 分を意味する) 10 の値は指定できますが、(午前 10 時 30 分を意味する) 10.5 の値は指定できません。既定値は 1 です (AM 01:00:00)。</span><span class="sxs-lookup"><span data-stu-id="c901b-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span>  <br/> |
   

