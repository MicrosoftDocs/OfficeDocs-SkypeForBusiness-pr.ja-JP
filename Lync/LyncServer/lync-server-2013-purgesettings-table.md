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
ms.openlocfilehash: 84c75e96c9a1541a8bd56f68d5fcf9d1a8655204
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512214"
---
# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="83fe6-102">Lync Server 2013 の PurgeSettings テーブル</span><span class="sxs-lookup"><span data-stu-id="83fe6-102">PurgeSettings table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83fe6-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="83fe6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="83fe6-104">PurgeSettings テーブルには、(およびいつ) 古くなった通話詳細レコードが CDR データベースから自動的に削除されるかどうかを指定する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83fe6-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="83fe6-105">削除に関連する情報は、Microsoft Lync Server 2013 管理シェルから次のコマンドを実行することによって取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="83fe6-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="83fe6-106">管理者は、PurgeSettings テーブルを読み取り専用として扱う必要があります。呼び出し詳細の削除設定に対する変更は、 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) コマンドレットまたは [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) コマンドレットを使用してのみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83fe6-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="83fe6-107">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="83fe6-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83fe6-108">Column</span><span class="sxs-lookup"><span data-stu-id="83fe6-108">Column</span></span></th>
<th><span data-ttu-id="83fe6-109">データ型</span><span class="sxs-lookup"><span data-stu-id="83fe6-109">Data Type</span></span></th>
<th><span data-ttu-id="83fe6-110">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="83fe6-110">Key/Index</span></span></th>
<th><span data-ttu-id="83fe6-111">詳細</span><span class="sxs-lookup"><span data-stu-id="83fe6-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83fe6-112"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="83fe6-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="83fe6-113">int</span><span class="sxs-lookup"><span data-stu-id="83fe6-113">int</span></span></p></td>
<td><p><span data-ttu-id="83fe6-114">Primary</span><span class="sxs-lookup"><span data-stu-id="83fe6-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="83fe6-115">CDR 削除設定のコレクションの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="83fe6-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83fe6-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="83fe6-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="83fe6-117">若干</span><span class="sxs-lookup"><span data-stu-id="83fe6-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="83fe6-118">True (1) に設定されている場合、Microsoft Lync Server 2013 は、古いレコードを CDR データベースから定期的に削除します。</span><span class="sxs-lookup"><span data-stu-id="83fe6-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="83fe6-119">削除は、毎日、PurgeHour 設定で指定された時間に行われます。</span><span class="sxs-lookup"><span data-stu-id="83fe6-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="83fe6-120">False (0) に設定すると、レコードがデータベースから自動的に削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="83fe6-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="83fe6-121">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="83fe6-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83fe6-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="83fe6-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="83fe6-123">int</span><span class="sxs-lookup"><span data-stu-id="83fe6-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="83fe6-124">データベースから削除される CDR レコード (日数) を指定します。この場合、削除が有効になっていると、この値より古い CDR レコードがデータベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="83fe6-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="83fe6-125">既定値は 60 日です。</span><span class="sxs-lookup"><span data-stu-id="83fe6-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83fe6-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="83fe6-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="83fe6-127">int</span><span class="sxs-lookup"><span data-stu-id="83fe6-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="83fe6-128">データベースから削除されるエラー報告レコード (日数) を指定します。削除が有効になっている場合は、この値よりも古いエラーレポートレコードがデータベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="83fe6-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="83fe6-129">既定値は 60 日です。</span><span class="sxs-lookup"><span data-stu-id="83fe6-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83fe6-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="83fe6-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="83fe6-131">int</span><span class="sxs-lookup"><span data-stu-id="83fe6-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="83fe6-132">データベースの削除が行われるローカル時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="83fe6-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="83fe6-133">時刻は24時間形式を使用して指定されます。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。</span><span class="sxs-lookup"><span data-stu-id="83fe6-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="83fe6-134">指定できるのは1日の時間のみです。値 10 (10:00 AM) は許可されていますが、10:30 10.5 の (10:30 AM を示す) の値は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="83fe6-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="83fe6-135">既定値は 2 (2:00 AM) です。</span><span class="sxs-lookup"><span data-stu-id="83fe6-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

