---
title: 'Lync Server 2013: ユーザーテーブル'
description: 'Lync Server 2013: ユーザーテーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b1418e162a04e46ee0dfeca082aa66b0665fc77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548633"
---
# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="068bc-103">Lync Server 2013 のユーザーテーブル</span><span class="sxs-lookup"><span data-stu-id="068bc-103">Users table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="068bc-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="068bc-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="068bc-105">ユーザーテーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="068bc-105">The Users table is a supporting table.</span></span> <span data-ttu-id="068bc-106">テーブル内の各レコードには、呼び出しまたはデータベース内のレコードを持つセッションに関与している1人のユーザーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="068bc-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="068bc-107">Column</span><span class="sxs-lookup"><span data-stu-id="068bc-107">Column</span></span></th>
<th><span data-ttu-id="068bc-108">データ型</span><span class="sxs-lookup"><span data-stu-id="068bc-108">Data Type</span></span></th>
<th><span data-ttu-id="068bc-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="068bc-109">Key/Index</span></span></th>
<th><span data-ttu-id="068bc-110">詳細</span><span class="sxs-lookup"><span data-stu-id="068bc-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="068bc-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="068bc-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="068bc-112">日付型</span><span class="sxs-lookup"><span data-stu-id="068bc-112">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="068bc-113">内部使用のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="068bc-113">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="068bc-114"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="068bc-114"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="068bc-115">int</span><span class="sxs-lookup"><span data-stu-id="068bc-115">int</span></span></p></td>
<td><p><span data-ttu-id="068bc-116">Primary</span><span class="sxs-lookup"><span data-stu-id="068bc-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="068bc-117">このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="068bc-117">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="068bc-118"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="068bc-118"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="068bc-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="068bc-119">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="068bc-120">ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="068bc-120">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="068bc-121"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="068bc-121"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="068bc-122">int</span><span class="sxs-lookup"><span data-stu-id="068bc-122">int</span></span></p></td>
<td><p><span data-ttu-id="068bc-123">外部</span><span class="sxs-lookup"><span data-stu-id="068bc-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="068bc-124">このユーザーのテナント ID。</span><span class="sxs-lookup"><span data-stu-id="068bc-124">This user’s Tenant ID.</span></span> <span data-ttu-id="068bc-125">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="068bc-125">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="068bc-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="068bc-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="068bc-127">int</span><span class="sxs-lookup"><span data-stu-id="068bc-127">int</span></span></p></td>
<td><p><span data-ttu-id="068bc-128">外部</span><span class="sxs-lookup"><span data-stu-id="068bc-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="068bc-129">このユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="068bc-129">This user’s URI type.</span></span> <span data-ttu-id="068bc-130">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="068bc-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

