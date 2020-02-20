---
title: 'Lync Server 2013: PurgeSettings テーブル (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bda217ec2711189439cfe6396faa5ba23872da9d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="4231a-102">Lync Server 2013 の PurgeSettings テーブル (QoE)</span><span class="sxs-lookup"><span data-stu-id="4231a-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4231a-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4231a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4231a-104">PurgeSettings テーブルには、古い QoE レコードを QoE データベースから自動的に削除するか、また削除する場合はどのタイミングで削除するかを指定する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4231a-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="4231a-105">削除に関連する情報は、Microsoft Lync Server 2013 管理シェルから次のコマンドを実行することによって取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="4231a-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="4231a-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4231a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4231a-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="4231a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4231a-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="4231a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4231a-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="4231a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4231a-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="4231a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4231a-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="4231a-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="4231a-112">int</span><span class="sxs-lookup"><span data-stu-id="4231a-112">int</span></span></p></td>
<td><p><span data-ttu-id="4231a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4231a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="4231a-114">QoE の削除設定のコレクションに対する一意識別子。</span><span class="sxs-lookup"><span data-stu-id="4231a-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4231a-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="4231a-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="4231a-116">若干</span><span class="sxs-lookup"><span data-stu-id="4231a-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4231a-117">True (1) に設定すると、Microsoft Lync Server 2013 は、古いレコードを定期的に QoE データベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="4231a-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="4231a-118">削除は、毎日、PurgeHour 設定で指定された時間に行われます。</span><span class="sxs-lookup"><span data-stu-id="4231a-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="4231a-119">False (0) に設定すると、レコードがデータベースから自動的に削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="4231a-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="4231a-120">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="4231a-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4231a-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="4231a-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="4231a-122">int</span><span class="sxs-lookup"><span data-stu-id="4231a-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4231a-p103">データベースから削除する QoE レコードの保有期間を (日単位で) 指定します。削除が有効の場合、この値より古い QoE レコードはデータベースから削除されます。既定値は 60 日です。</span><span class="sxs-lookup"><span data-stu-id="4231a-p103">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4231a-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="4231a-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="4231a-126">int</span><span class="sxs-lookup"><span data-stu-id="4231a-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4231a-p104">データベースでの削除が行われる日のローカル時間を指定します。時刻は 24 時間制を使用して指定します。0 は夜中 12 時 (12:00 AM) を、23 は 11:00 PM を表します。指定できるのは時間のみです。(午前 10 時 00 分を意味する) 10 の値は指定できますが、(午前 10 時 30 分を意味する) 10.5 の値は指定できません。既定値は 1 です (AM 01:00:00)。</span><span class="sxs-lookup"><span data-stu-id="4231a-p104">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

