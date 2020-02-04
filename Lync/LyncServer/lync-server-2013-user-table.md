---
title: 'Lync Server 2013: User テーブル'
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
ms.openlocfilehash: 8256dec91c93ca6e8f0fd3cfff65280a417324e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="ece18-102">Lync Server 2013 の User テーブル</span><span class="sxs-lookup"><span data-stu-id="ece18-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ece18-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ece18-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ece18-104">ユーザーテーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーの一覧を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="ece18-104">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ece18-105">テーブル内の各レコードは、1人のユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="ece18-105">Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ece18-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="ece18-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ece18-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="ece18-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ece18-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="ece18-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ece18-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="ece18-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ece18-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="ece18-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ece18-111">int</span><span class="sxs-lookup"><span data-stu-id="ece18-111">int</span></span></p></td>
<td><p><span data-ttu-id="ece18-112">Primary</span><span class="sxs-lookup"><span data-stu-id="ece18-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ece18-113">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="ece18-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ece18-114"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="ece18-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="ece18-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ece18-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ece18-116">一意</span><span class="sxs-lookup"><span data-stu-id="ece18-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="ece18-117">URI 文字列。</span><span class="sxs-lookup"><span data-stu-id="ece18-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ece18-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="ece18-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="ece18-119">int</span><span class="sxs-lookup"><span data-stu-id="ece18-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ece18-120">1の URI の型が不明です。</span><span class="sxs-lookup"><span data-stu-id="ece18-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="ece18-121">2はユーザー URI です。</span><span class="sxs-lookup"><span data-stu-id="ece18-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="ece18-122">4は会議の URI です。</span><span class="sxs-lookup"><span data-stu-id="ece18-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="ece18-123">8は電話の URI です。</span><span class="sxs-lookup"><span data-stu-id="ece18-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ece18-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="ece18-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ece18-125">int</span><span class="sxs-lookup"><span data-stu-id="ece18-125">int</span></span></p></td>
<td><p><span data-ttu-id="ece18-126">外部</span><span class="sxs-lookup"><span data-stu-id="ece18-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ece18-127">テナントテーブルから参照されたユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="ece18-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ece18-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="ece18-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ece18-129">datetime</span><span class="sxs-lookup"><span data-stu-id="ece18-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ece18-130">ユーザーが低品質の音声通話を行ったときの最新のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="ece18-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ece18-131"><strong>Nextupdatupdat</strong></span><span class="sxs-lookup"><span data-stu-id="ece18-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ece18-132">datetime</span><span class="sxs-lookup"><span data-stu-id="ece18-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ece18-133">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ece18-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

