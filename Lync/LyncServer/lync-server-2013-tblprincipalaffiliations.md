---
title: 'Lync Server 2013: tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb5f6400de1c71b4d11101871b2dadedd232a9ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="50224-102">Lync Server 2013 の tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="50224-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50224-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="50224-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="50224-104">tblPrincipalAffiliations には、active Directory ドメインサービスセキュリティグループなどの場所のメンバーシップを、ドメインの Active Directory コンテナーで説明するプリンシパルの所属が含まれています。</span><span class="sxs-lookup"><span data-stu-id="50224-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="50224-105">行</span><span class="sxs-lookup"><span data-stu-id="50224-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50224-106">列</span><span class="sxs-lookup"><span data-stu-id="50224-106">Column</span></span></th>
<th><span data-ttu-id="50224-107">型</span><span class="sxs-lookup"><span data-stu-id="50224-107">Type</span></span></th>
<th><span data-ttu-id="50224-108">説明</span><span class="sxs-lookup"><span data-stu-id="50224-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50224-109">principalID</span><span class="sxs-lookup"><span data-stu-id="50224-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="50224-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="50224-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="50224-111">関連主体の ID です。</span><span class="sxs-lookup"><span data-stu-id="50224-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50224-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="50224-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="50224-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="50224-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="50224-114">所属を表すプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="50224-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="50224-115">各プリンシパル (システムユーザーの種類を除く) には、自己所属も含まれています。</span><span class="sxs-lookup"><span data-stu-id="50224-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50224-116">位置</span><span class="sxs-lookup"><span data-stu-id="50224-116">index</span></span></p></td>
<td><p><span data-ttu-id="50224-117">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="50224-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="50224-118">位置.</span><span class="sxs-lookup"><span data-stu-id="50224-118">Index.</span></span> <span data-ttu-id="50224-119">自己所属の値は-1 であり、その他の所属については、principalID の各&lt;&gt;バケット内の1から順に1が増加します。</span><span class="sxs-lookup"><span data-stu-id="50224-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50224-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="50224-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="50224-121">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="50224-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="50224-122">最新の更新プログラムを実行したプリンシパル。</span><span class="sxs-lookup"><span data-stu-id="50224-122">Principal that did the latest update.</span></span> <span data-ttu-id="50224-123">これは通常1で、Active Directory の同期を意味します。</span><span class="sxs-lookup"><span data-stu-id="50224-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="50224-124">機能</span><span class="sxs-lookup"><span data-stu-id="50224-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50224-125">行</span><span class="sxs-lookup"><span data-stu-id="50224-125">Columns</span></span></th>
<th><span data-ttu-id="50224-126">説明</span><span class="sxs-lookup"><span data-stu-id="50224-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50224-127">&lt;principalID、index、affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="50224-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="50224-128">主キー。</span><span class="sxs-lookup"><span data-stu-id="50224-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50224-129">principalID</span><span class="sxs-lookup"><span data-stu-id="50224-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="50224-130">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="50224-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50224-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="50224-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="50224-132">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="50224-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

