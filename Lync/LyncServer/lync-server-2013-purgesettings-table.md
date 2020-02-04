---
title: 'Lync Server 2013: PurgeSettings テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ea95d0ba54a34eaa315ff345efb45cd563700c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="283af-102">Lync Server 2013 の PurgeSettings テーブル</span><span class="sxs-lookup"><span data-stu-id="283af-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="283af-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="283af-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="283af-104">PurgeSettings テーブルには、古い通話の詳細レコードが CDR データベースから自動的に削除されるかどうかを指定する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="283af-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="283af-105">また、次のコマンドを実行することで、Microsoft Lync Server 2013 管理シェル内からパージに関連する情報を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="283af-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="283af-106">管理者は、PurgeSettings テーブルを読み取り専用として扱う必要があります。呼び出しの詳細の消去設定への変更は、 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration)または[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration)コマンドレットを使用して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="283af-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="283af-107">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="283af-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="283af-108">列</span><span class="sxs-lookup"><span data-stu-id="283af-108">Column</span></span></th>
<th><span data-ttu-id="283af-109">データ型</span><span class="sxs-lookup"><span data-stu-id="283af-109">Data Type</span></span></th>
<th><span data-ttu-id="283af-110">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="283af-110">Key/Index</span></span></th>
<th><span data-ttu-id="283af-111">詳細</span><span class="sxs-lookup"><span data-stu-id="283af-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="283af-112"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="283af-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="283af-113">int</span><span class="sxs-lookup"><span data-stu-id="283af-113">int</span></span></p></td>
<td><p><span data-ttu-id="283af-114">Primary</span><span class="sxs-lookup"><span data-stu-id="283af-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="283af-115">CDR 消去設定のコレクションの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="283af-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="283af-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="283af-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="283af-117">bit</span><span class="sxs-lookup"><span data-stu-id="283af-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="283af-118">True に設定すると (1) Microsoft Lync Server 2013 は、古いレコードを CDR データベースから定期的に削除します。</span><span class="sxs-lookup"><span data-stu-id="283af-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="283af-119">パージは、PurgeHour 設定によって指定されたサントメで毎日行われます。</span><span class="sxs-lookup"><span data-stu-id="283af-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="283af-120">False (0) に設定すると、レコードはデータベースから自動的に削除されません。</span><span class="sxs-lookup"><span data-stu-id="283af-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="283af-121">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="283af-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="283af-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="283af-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="283af-123">int</span><span class="sxs-lookup"><span data-stu-id="283af-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="283af-124">データベースから削除される CDR レコード (日数) を指定します。 [削除] が有効になっていると、この値よりも古い CDR レコードがデータベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="283af-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="283af-125">既定値は60日です。</span><span class="sxs-lookup"><span data-stu-id="283af-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="283af-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="283af-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="283af-127">int</span><span class="sxs-lookup"><span data-stu-id="283af-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="283af-128">データベースから削除されるエラーレポートレコード (日数) を指定します。 [削除] を有効にすると、この値よりも古いエラーレポートレコードがデータベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="283af-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="283af-129">既定値は60日です。</span><span class="sxs-lookup"><span data-stu-id="283af-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="283af-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="283af-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="283af-131">int</span><span class="sxs-lookup"><span data-stu-id="283af-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="283af-132">データベースの消去が行われるローカル時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="283af-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="283af-133">時刻は24時間制を使用して指定します。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。</span><span class="sxs-lookup"><span data-stu-id="283af-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="283af-134">時刻を指定できるのは1日の時間のみです。10の値 (10:00 AM) は許可されていますが、10.5 の 10:30 (10:30 AM を示す) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="283af-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="283af-135">既定値は 2 (2:00 AM) です。</span><span class="sxs-lookup"><span data-stu-id="283af-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

