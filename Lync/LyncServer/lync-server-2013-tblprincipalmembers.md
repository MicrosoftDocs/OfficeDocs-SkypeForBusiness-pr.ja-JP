---
title: 'Lync Server 2013: tblPrincipalMembers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615022(v=OCS.15)
ms:contentKeyID: 48184965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa002b4b1f81cf2ebd607a99f0f00360e01e9292
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="4ead0-102">Lync Server 2013 の tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="4ead0-102">tblPrincipalMembers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ead0-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4ead0-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4ead0-104">tblPrincipalMembers にプリンシパルメンバーシップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ead0-104">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="4ead0-105">行</span><span class="sxs-lookup"><span data-stu-id="4ead0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ead0-106">列</span><span class="sxs-lookup"><span data-stu-id="4ead0-106">Column</span></span></th>
<th><span data-ttu-id="4ead0-107">型</span><span class="sxs-lookup"><span data-stu-id="4ead0-107">Type</span></span></th>
<th><span data-ttu-id="4ead0-108">説明</span><span class="sxs-lookup"><span data-stu-id="4ead0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ead0-109">prinID</span><span class="sxs-lookup"><span data-stu-id="4ead0-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="4ead0-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="4ead0-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4ead0-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="4ead0-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead0-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="4ead0-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="4ead0-113">nvarchar (384)、null ではない</span><span class="sxs-lookup"><span data-stu-id="4ead0-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="4ead0-114">メンバーの識別名。</span><span class="sxs-lookup"><span data-stu-id="4ead0-114">Distinguished name of a member.</span></span> <span data-ttu-id="4ead0-115">メンバーは、プリンシパル (tblPrincipal テーブル内) である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4ead0-115">A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4ead0-116">機能</span><span class="sxs-lookup"><span data-stu-id="4ead0-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ead0-117">列</span><span class="sxs-lookup"><span data-stu-id="4ead0-117">Column</span></span></th>
<th><span data-ttu-id="4ead0-118">説明</span><span class="sxs-lookup"><span data-stu-id="4ead0-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ead0-119">&lt;prinID、memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="4ead0-119">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="4ead0-120">主キー。</span><span class="sxs-lookup"><span data-stu-id="4ead0-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead0-121">prinID</span><span class="sxs-lookup"><span data-stu-id="4ead0-121">prinID</span></span></p></td>
<td><p><span data-ttu-id="4ead0-122">TblPrincipal Id で参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="4ead0-122">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

