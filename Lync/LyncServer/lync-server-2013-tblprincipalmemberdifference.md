---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfdd2ff1ca0c288738005c8d0740770e7c43319f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="b8649-102">Lync Server 2013 の tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="b8649-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8649-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b8649-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b8649-104">tblPrincipalMemberDifference には、以降の Active Directory ドメインサービス同期手順でまだ処理されていないグループメンバーシップの変更 (メンバーの追加および削除) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8649-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="b8649-105">Columns</span><span class="sxs-lookup"><span data-stu-id="b8649-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8649-106">列</span><span class="sxs-lookup"><span data-stu-id="b8649-106">Column</span></span></th>
<th><span data-ttu-id="b8649-107">種類</span><span class="sxs-lookup"><span data-stu-id="b8649-107">Type</span></span></th>
<th><span data-ttu-id="b8649-108">説明</span><span class="sxs-lookup"><span data-stu-id="b8649-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8649-109">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="b8649-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="b8649-110">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="b8649-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="b8649-111">変更されたグループのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="b8649-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8649-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="b8649-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="b8649-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b8649-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="b8649-114">メンバーの識別名。</span><span class="sxs-lookup"><span data-stu-id="b8649-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8649-115">メンバーの削除</span><span class="sxs-lookup"><span data-stu-id="b8649-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="b8649-116">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="b8649-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b8649-p101">メンバーが追加された場合は False。メンバーが削除された場合は True。</span><span class="sxs-lookup"><span data-stu-id="b8649-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="b8649-119">キー</span><span class="sxs-lookup"><span data-stu-id="b8649-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8649-120">列</span><span class="sxs-lookup"><span data-stu-id="b8649-120">Column</span></span></th>
<th><span data-ttu-id="b8649-121">説明</span><span class="sxs-lookup"><span data-stu-id="b8649-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8649-122">&lt;prinGuid、memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="b8649-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="b8649-123">主キー。</span><span class="sxs-lookup"><span data-stu-id="b8649-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

