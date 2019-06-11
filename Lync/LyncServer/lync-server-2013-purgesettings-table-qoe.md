---
title: 'Lync Server 2013: PurgeSettings table (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cc227d11ee723acb5a49c50d5b8d4d7e819062
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="e4f83-102">Lync Server 2013 の PurgeSettings テーブル (QoE)</span><span class="sxs-lookup"><span data-stu-id="e4f83-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4f83-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e4f83-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e4f83-104">PurgeSettings テーブルには、古い品質のエクスペリエンスレコードが QoE データベースから自動的に削除されるかどうかを指定する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4f83-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="e4f83-105">また、次のコマンドを実行することで、Microsoft Lync Server 2013 管理シェル内からパージに関連する情報を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4f83-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="e4f83-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e4f83-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4f83-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="e4f83-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e4f83-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="e4f83-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e4f83-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="e4f83-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e4f83-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="e4f83-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4f83-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="e4f83-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f83-112">int</span><span class="sxs-lookup"><span data-stu-id="e4f83-112">int</span></span></p></td>
<td><p><span data-ttu-id="e4f83-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e4f83-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e4f83-114">QoE の消去設定のコレクションの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="e4f83-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f83-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="e4f83-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f83-116">bit</span><span class="sxs-lookup"><span data-stu-id="e4f83-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4f83-117">True (1) に設定すると、Microsoft Lync Server 2013 は、古いレコードを QoE データベースから定期的に削除します。</span><span class="sxs-lookup"><span data-stu-id="e4f83-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="e4f83-118">パージは、PurgeHour 設定によって指定されたサントメで毎日行われます。</span><span class="sxs-lookup"><span data-stu-id="e4f83-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="e4f83-119">False (0) に設定すると、レコードはデータベースから自動的に削除されません。</span><span class="sxs-lookup"><span data-stu-id="e4f83-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="e4f83-120">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="e4f83-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f83-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="e4f83-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f83-122">int</span><span class="sxs-lookup"><span data-stu-id="e4f83-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4f83-123">データベースから削除される QoE レコード (日数) を指定します。 [削除] が有効になっていると、この値よりも古い QoE レコードはデータベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e4f83-123">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="e4f83-124">既定値は60日です。</span><span class="sxs-lookup"><span data-stu-id="e4f83-124">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f83-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="e4f83-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f83-126">int</span><span class="sxs-lookup"><span data-stu-id="e4f83-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4f83-127">データベースの消去が行われるローカル時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f83-127">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="e4f83-128">時刻は24時間制を使用して指定します。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。</span><span class="sxs-lookup"><span data-stu-id="e4f83-128">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="e4f83-129">時刻を指定できるのは1日の時間のみです。10の値 (10:00 AM) は許可されていますが、10.5 の 10:30 (10:30 AM を示す) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="e4f83-129">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="e4f83-130">既定値は 1 (1:00 AM) です。</span><span class="sxs-lookup"><span data-stu-id="e4f83-130">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="e4f83-131">データベースの消去が行われるローカル時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f83-131">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="e4f83-132">時刻は24時間制を使用して指定します。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。</span><span class="sxs-lookup"><span data-stu-id="e4f83-132">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="e4f83-133">時刻を指定できるのは1日の時間のみです。10の値 (10:00 AM) は許可されていますが、10.5 の 10:30 (10:30 AM を示す) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="e4f83-133">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="e4f83-134">既定値は 1 (1:00 AM) です。</span><span class="sxs-lookup"><span data-stu-id="e4f83-134">The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

