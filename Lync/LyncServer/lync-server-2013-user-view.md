---
title: 'Lync Server 2013: ユーザービュー'
description: 'Lync Server 2013: ユーザービュー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa606887e8050a51f1e5a87656bb74a7cd58bbc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558913"
---
# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="14793-103">Lync Server 2013 のユーザービュー</span><span class="sxs-lookup"><span data-stu-id="14793-103">User view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14793-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="14793-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="14793-105">ユーザー ビューには、データベース内にレコードのある通話またはセッションに関係するユーザーについての情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="14793-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="14793-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="14793-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14793-107">Column</span><span class="sxs-lookup"><span data-stu-id="14793-107">Column</span></span></th>
<th><span data-ttu-id="14793-108">データ型</span><span class="sxs-lookup"><span data-stu-id="14793-108">Data Type</span></span></th>
<th><span data-ttu-id="14793-109">詳細</span><span class="sxs-lookup"><span data-stu-id="14793-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14793-110">UserId</span><span class="sxs-lookup"><span data-stu-id="14793-110">UserId</span></span></p></td>
<td><p><span data-ttu-id="14793-111">int</span><span class="sxs-lookup"><span data-stu-id="14793-111">int</span></span></p></td>
<td><p><span data-ttu-id="14793-112">このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="14793-112">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14793-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="14793-113">UserUri</span></span></p></td>
<td><p><span data-ttu-id="14793-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="14793-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="14793-115">ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="14793-115">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14793-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="14793-116">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="14793-117">識別子</span><span class="sxs-lookup"><span data-stu-id="14793-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="14793-118">ユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="14793-118">Tenant of user.</span></span> <span data-ttu-id="14793-119">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14793-119">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14793-120">UriType</span><span class="sxs-lookup"><span data-stu-id="14793-120">UriType</span></span></p></td>
<td><p><span data-ttu-id="14793-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="14793-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14793-122">ユーザー URI の種類。</span><span class="sxs-lookup"><span data-stu-id="14793-122">Type of user URI.</span></span> <span data-ttu-id="14793-123">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14793-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

