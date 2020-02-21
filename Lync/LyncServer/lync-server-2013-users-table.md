---
title: 'Lync Server 2013: ユーザーテーブル'
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
ms.openlocfilehash: 70aefd95a8abaa1d9b49e89ac3e7b14dfa2444e7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="f2a6a-102">Lync Server 2013 のユーザーテーブル</span><span class="sxs-lookup"><span data-stu-id="f2a6a-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2a6a-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f2a6a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f2a6a-104">ユーザーテーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-104">The Users table is a supporting table.</span></span> <span data-ttu-id="f2a6a-105">テーブル内の各レコードには、呼び出しまたはデータベース内のレコードを持つセッションに関与している1人のユーザーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2a6a-106">列</span><span class="sxs-lookup"><span data-stu-id="f2a6a-106">Column</span></span></th>
<th><span data-ttu-id="f2a6a-107">データ型</span><span class="sxs-lookup"><span data-stu-id="f2a6a-107">Data Type</span></span></th>
<th><span data-ttu-id="f2a6a-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="f2a6a-108">Key/Index</span></span></th>
<th><span data-ttu-id="f2a6a-109">詳細</span><span class="sxs-lookup"><span data-stu-id="f2a6a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2a6a-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="f2a6a-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="f2a6a-111">日付型</span><span class="sxs-lookup"><span data-stu-id="f2a6a-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2a6a-112">内部使用のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2a6a-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="f2a6a-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2a6a-114">int</span><span class="sxs-lookup"><span data-stu-id="f2a6a-114">int</span></span></p></td>
<td><p><span data-ttu-id="f2a6a-115">Primary</span><span class="sxs-lookup"><span data-stu-id="f2a6a-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="f2a6a-116">このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2a6a-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="f2a6a-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f2a6a-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f2a6a-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f2a6a-119">ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2a6a-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="f2a6a-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2a6a-121">int</span><span class="sxs-lookup"><span data-stu-id="f2a6a-121">int</span></span></p></td>
<td><p><span data-ttu-id="f2a6a-122">外部</span><span class="sxs-lookup"><span data-stu-id="f2a6a-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2a6a-123">このユーザーのテナント ID。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-123">This user’s Tenant ID.</span></span> <span data-ttu-id="f2a6a-124">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2a6a-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="f2a6a-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2a6a-126">int</span><span class="sxs-lookup"><span data-stu-id="f2a6a-126">int</span></span></p></td>
<td><p><span data-ttu-id="f2a6a-127">外部</span><span class="sxs-lookup"><span data-stu-id="f2a6a-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2a6a-128">このユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-128">This user’s URI type.</span></span> <span data-ttu-id="f2a6a-129">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

