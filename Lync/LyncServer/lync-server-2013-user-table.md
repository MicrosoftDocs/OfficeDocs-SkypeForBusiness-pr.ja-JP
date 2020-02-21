---
title: 'Lync Server 2013: ユーザーテーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f3ea921981726ad1865741a1e8e37f82f8ac125
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="5db6f-102">Lync Server 2013 のユーザーテーブル</span><span class="sxs-lookup"><span data-stu-id="5db6f-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5db6f-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5db6f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5db6f-p101">User テーブルは、データベースに記録されるセッションに参加したさまざまなユーザーの一覧を格納するサポート テーブルです。このテーブルの各レコードは、1 人のユーザーを表しています。</span><span class="sxs-lookup"><span data-stu-id="5db6f-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5db6f-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="5db6f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5db6f-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="5db6f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5db6f-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="5db6f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5db6f-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="5db6f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5db6f-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="5db6f-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="5db6f-111">int</span><span class="sxs-lookup"><span data-stu-id="5db6f-111">int</span></span></p></td>
<td><p><span data-ttu-id="5db6f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="5db6f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5db6f-113">このユーザーを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="5db6f-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db6f-114"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="5db6f-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="5db6f-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5db6f-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5db6f-116">一意</span><span class="sxs-lookup"><span data-stu-id="5db6f-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="5db6f-117">URI 文字列です。</span><span class="sxs-lookup"><span data-stu-id="5db6f-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5db6f-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="5db6f-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="5db6f-119">int</span><span class="sxs-lookup"><span data-stu-id="5db6f-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5db6f-120">1 は不明な URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="5db6f-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="5db6f-121">2 はユーザーの URI です。</span><span class="sxs-lookup"><span data-stu-id="5db6f-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="5db6f-122">4 は電話会議の URI です。</span><span class="sxs-lookup"><span data-stu-id="5db6f-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="5db6f-123">8 は電話の URI です。</span><span class="sxs-lookup"><span data-stu-id="5db6f-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db6f-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="5db6f-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="5db6f-125">int</span><span class="sxs-lookup"><span data-stu-id="5db6f-125">int</span></span></p></td>
<td><p><span data-ttu-id="5db6f-126">外部</span><span class="sxs-lookup"><span data-stu-id="5db6f-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5db6f-127">ユーザーのテナントであり、テナント テーブルから参照されます。</span><span class="sxs-lookup"><span data-stu-id="5db6f-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5db6f-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="5db6f-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5db6f-129">日付型</span><span class="sxs-lookup"><span data-stu-id="5db6f-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5db6f-130">ユーザーが低音質の通話を行った時点を示す最新のタイム スタンプです。</span><span class="sxs-lookup"><span data-stu-id="5db6f-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db6f-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="5db6f-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="5db6f-132">日付型</span><span class="sxs-lookup"><span data-stu-id="5db6f-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5db6f-133">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="5db6f-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

