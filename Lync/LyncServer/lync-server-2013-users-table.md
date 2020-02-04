---
title: 'Lync Server 2013: ユーザー テーブル'
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
ms.openlocfilehash: c2be643f8a593af01ee47ad93d3910d44ee86e48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="13070-102">Lync Server 2013 のユーザー テーブル</span><span class="sxs-lookup"><span data-stu-id="13070-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13070-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="13070-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="13070-104">ユーザーテーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="13070-104">The Users table is a supporting table.</span></span> <span data-ttu-id="13070-105">テーブル内の各レコードには、データベース内のレコードが含まれる1人のユーザーに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="13070-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="13070-106">列</span><span class="sxs-lookup"><span data-stu-id="13070-106">Column</span></span></th>
<th><span data-ttu-id="13070-107">データ型</span><span class="sxs-lookup"><span data-stu-id="13070-107">Data Type</span></span></th>
<th><span data-ttu-id="13070-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="13070-108">Key/Index</span></span></th>
<th><span data-ttu-id="13070-109">詳細</span><span class="sxs-lookup"><span data-stu-id="13070-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13070-110"><strong>Nextupdatupdat</strong></span><span class="sxs-lookup"><span data-stu-id="13070-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="13070-111">datetime</span><span class="sxs-lookup"><span data-stu-id="13070-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="13070-112">内部使用のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="13070-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13070-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="13070-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="13070-114">int</span><span class="sxs-lookup"><span data-stu-id="13070-114">int</span></span></p></td>
<td><p><span data-ttu-id="13070-115">Primary</span><span class="sxs-lookup"><span data-stu-id="13070-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="13070-116">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="13070-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13070-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="13070-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="13070-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="13070-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="13070-119">ユーザー URI。</span><span class="sxs-lookup"><span data-stu-id="13070-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13070-120"><strong>テナント</strong></span><span class="sxs-lookup"><span data-stu-id="13070-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="13070-121">int</span><span class="sxs-lookup"><span data-stu-id="13070-121">int</span></span></p></td>
<td><p><span data-ttu-id="13070-122">外部</span><span class="sxs-lookup"><span data-stu-id="13070-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="13070-123">このユーザーのテナント ID。</span><span class="sxs-lookup"><span data-stu-id="13070-123">This user’s Tenant ID.</span></span> <span data-ttu-id="13070-124">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13070-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13070-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="13070-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="13070-126">int</span><span class="sxs-lookup"><span data-stu-id="13070-126">int</span></span></p></td>
<td><p><span data-ttu-id="13070-127">外部</span><span class="sxs-lookup"><span data-stu-id="13070-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="13070-128">このユーザーの URI 型。</span><span class="sxs-lookup"><span data-stu-id="13070-128">This user’s URI type.</span></span> <span data-ttu-id="13070-129">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13070-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

