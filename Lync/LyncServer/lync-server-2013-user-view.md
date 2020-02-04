---
title: 'Lync Server 2013: ユーザービュー'
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
ms.openlocfilehash: c8e88d7a9fa66f309bbd64ab064ec95adafc40b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="716a8-102">Lync Server 2013 のユーザービュー</span><span class="sxs-lookup"><span data-stu-id="716a8-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="716a8-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="716a8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="716a8-104">ユーザービューには、データベース内のレコードを持つ通話またはセッションに参加しているユーザーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="716a8-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="716a8-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="716a8-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="716a8-106">列</span><span class="sxs-lookup"><span data-stu-id="716a8-106">Column</span></span></th>
<th><span data-ttu-id="716a8-107">データ型</span><span class="sxs-lookup"><span data-stu-id="716a8-107">Data Type</span></span></th>
<th><span data-ttu-id="716a8-108">詳細</span><span class="sxs-lookup"><span data-stu-id="716a8-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="716a8-109">UserId</span><span class="sxs-lookup"><span data-stu-id="716a8-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="716a8-110">int</span><span class="sxs-lookup"><span data-stu-id="716a8-110">int</span></span></p></td>
<td><p><span data-ttu-id="716a8-111">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="716a8-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="716a8-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="716a8-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="716a8-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="716a8-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="716a8-114">ユーザーの Uri。</span><span class="sxs-lookup"><span data-stu-id="716a8-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="716a8-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="716a8-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="716a8-116">長さ</span><span class="sxs-lookup"><span data-stu-id="716a8-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="716a8-117">ユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="716a8-117">Tenant of user.</span></span> <span data-ttu-id="716a8-118">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="716a8-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="716a8-119">UriType</span><span class="sxs-lookup"><span data-stu-id="716a8-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="716a8-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="716a8-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="716a8-121">ユーザー URI の種類。</span><span class="sxs-lookup"><span data-stu-id="716a8-121">Type of user URI.</span></span> <span data-ttu-id="716a8-122">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="716a8-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

