---
title: 'Lync Server 2013: tblAdminLock'
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
ms.openlocfilehash: 26a8236145f86fa86039b4030fe82327d9fc4dfa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a><span data-ttu-id="fd21a-102">Lync Server 2013 の tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="fd21a-102">tblAdminLock in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd21a-103">_**トピックの最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="fd21a-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="fd21a-104">tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが格納されます。</span><span class="sxs-lookup"><span data-stu-id="fd21a-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>

### <a name="columns"></a><span data-ttu-id="fd21a-105">Columns</span><span class="sxs-lookup"><span data-stu-id="fd21a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd21a-106">列</span><span class="sxs-lookup"><span data-stu-id="fd21a-106">Column</span></span></th>
<th><span data-ttu-id="fd21a-107">種類</span><span class="sxs-lookup"><span data-stu-id="fd21a-107">Type</span></span></th>
<th><span data-ttu-id="fd21a-108">説明</span><span class="sxs-lookup"><span data-stu-id="fd21a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd21a-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="fd21a-109">lockExpiresTime</span></span></p></td>
<td><p><span data-ttu-id="fd21a-110">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="fd21a-110">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="fd21a-p101">ロックの有効期限の日時。所有者はこの値による期限を定期的に延長できます。</span><span class="sxs-lookup"><span data-stu-id="fd21a-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21a-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="fd21a-113">lockServerID</span></span></p></td>
<td><p><span data-ttu-id="fd21a-114">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="fd21a-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fd21a-115">ロックを所有するサーバーの ID。</span><span class="sxs-lookup"><span data-stu-id="fd21a-115">ID of the server that owns the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21a-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="fd21a-116">lockActorID</span></span></p></td>
<td><p><span data-ttu-id="fd21a-117">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="fd21a-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fd21a-118">ロックを所有するプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="fd21a-118">ID of the principal that owns the lock.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

