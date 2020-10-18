---
title: 'Lync Server 2013: tblAdminLock'
description: 'Lync Server 2013: tblAdminLock。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3313826b2c0d578c515fb25f83e713b8978ae63
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573713"
---
# <a name="tbladminlock-in-lync-server-2013"></a><span data-ttu-id="fa678-103">Lync Server 2013 の tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="fa678-103">tblAdminLock in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa678-104">_**トピックの最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="fa678-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="fa678-105">tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが格納されます。</span><span class="sxs-lookup"><span data-stu-id="fa678-105">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>

### <a name="columns"></a><span data-ttu-id="fa678-106">段組み</span><span class="sxs-lookup"><span data-stu-id="fa678-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa678-107">Column</span><span class="sxs-lookup"><span data-stu-id="fa678-107">Column</span></span></th>
<th><span data-ttu-id="fa678-108">種類</span><span class="sxs-lookup"><span data-stu-id="fa678-108">Type</span></span></th>
<th><span data-ttu-id="fa678-109">説明</span><span class="sxs-lookup"><span data-stu-id="fa678-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa678-110">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="fa678-110">lockExpiresTime</span></span></p></td>
<td><p><span data-ttu-id="fa678-111">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="fa678-111">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="fa678-p101">ロックの有効期限の日時。所有者はこの値による期限を定期的に延長できます。</span><span class="sxs-lookup"><span data-stu-id="fa678-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa678-114">lockServerID</span><span class="sxs-lookup"><span data-stu-id="fa678-114">lockServerID</span></span></p></td>
<td><p><span data-ttu-id="fa678-115">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="fa678-115">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fa678-116">ロックを所有するサーバーの ID。</span><span class="sxs-lookup"><span data-stu-id="fa678-116">ID of the server that owns the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa678-117">lockActorID</span><span class="sxs-lookup"><span data-stu-id="fa678-117">lockActorID</span></span></p></td>
<td><p><span data-ttu-id="fa678-118">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="fa678-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fa678-119">ロックを所有するプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="fa678-119">ID of the principal that owns the lock.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

