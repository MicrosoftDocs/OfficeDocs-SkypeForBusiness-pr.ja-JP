---
title: 'Lync Server 2013: tblPrincipalType'
description: 'Lync Server 2013: tblPrincipalType。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba0f607d4499b54b16d7ecf8a4e7de603e874788
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549863"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="b309d-103">Lync Server 2013 の tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="b309d-103">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b309d-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b309d-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b309d-105">tblPrincipal テーブルには、tblPrincipal テーブルの内容を分類するプリンシパル型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b309d-105">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="b309d-106">段組み</span><span class="sxs-lookup"><span data-stu-id="b309d-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b309d-107">Column</span><span class="sxs-lookup"><span data-stu-id="b309d-107">Column</span></span></th>
<th><span data-ttu-id="b309d-108">種類</span><span class="sxs-lookup"><span data-stu-id="b309d-108">Type</span></span></th>
<th><span data-ttu-id="b309d-109">説明</span><span class="sxs-lookup"><span data-stu-id="b309d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b309d-110">Tblprincipaltype.ptypeid</span><span class="sxs-lookup"><span data-stu-id="b309d-110">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="b309d-111">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="b309d-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="b309d-112">プリンシパル型 ID。</span><span class="sxs-lookup"><span data-stu-id="b309d-112">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b309d-113">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="b309d-113">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="b309d-114">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b309d-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="b309d-115">型の説明。</span><span class="sxs-lookup"><span data-stu-id="b309d-115">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b309d-116">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="b309d-116">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="b309d-117">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="b309d-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b309d-118">型が内部の用途で使用されるプリンシパルに対応する場合、True。</span><span class="sxs-lookup"><span data-stu-id="b309d-118">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b309d-119">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="b309d-119">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="b309d-120">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="b309d-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b309d-121">型がユーザー型の場合、True。</span><span class="sxs-lookup"><span data-stu-id="b309d-121">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="b309d-122">キー</span><span class="sxs-lookup"><span data-stu-id="b309d-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b309d-123">列</span><span class="sxs-lookup"><span data-stu-id="b309d-123">Column</span></span></th>
<th><span data-ttu-id="b309d-124">説明</span><span class="sxs-lookup"><span data-stu-id="b309d-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b309d-125">Tblprincipaltype.ptypeid</span><span class="sxs-lookup"><span data-stu-id="b309d-125">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="b309d-126">主キー。</span><span class="sxs-lookup"><span data-stu-id="b309d-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="b309d-127">プリンシパル値</span><span class="sxs-lookup"><span data-stu-id="b309d-127">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b309d-128">ID</span><span class="sxs-lookup"><span data-stu-id="b309d-128">ID</span></span></th>
<th><span data-ttu-id="b309d-129">Role</span><span class="sxs-lookup"><span data-stu-id="b309d-129">Role</span></span></th>
<th><span data-ttu-id="b309d-130">説明</span><span class="sxs-lookup"><span data-stu-id="b309d-130">Description</span></span></th>
<th><span data-ttu-id="b309d-131">User</span><span class="sxs-lookup"><span data-stu-id="b309d-131">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b309d-132">1-d</span><span class="sxs-lookup"><span data-stu-id="b309d-132">1</span></span></p></td>
<td><p><span data-ttu-id="b309d-133">任意</span><span class="sxs-lookup"><span data-stu-id="b309d-133">Any</span></span></p></td>
<td><p><span data-ttu-id="b309d-p101">既知の型を持たない汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="b309d-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b309d-136">pbm-2</span><span class="sxs-lookup"><span data-stu-id="b309d-136">2</span></span></p></td>
<td><p><span data-ttu-id="b309d-137">AnyUser</span><span class="sxs-lookup"><span data-stu-id="b309d-137">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="b309d-p102">ユーザー型の汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="b309d-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="b309d-140">はい</span><span class="sxs-lookup"><span data-stu-id="b309d-140">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b309d-141">1/3</span><span class="sxs-lookup"><span data-stu-id="b309d-141">3</span></span></p></td>
<td><p><span data-ttu-id="b309d-142">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="b309d-142">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="b309d-p103">グループ セマンティックを持つ汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="b309d-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b309d-145">4 </span><span class="sxs-lookup"><span data-stu-id="b309d-145">4</span></span></p></td>
<td><p><span data-ttu-id="b309d-146">自分のもの</span><span class="sxs-lookup"><span data-stu-id="b309d-146">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="b309d-147">常設チャットサーバーによって内部的に使用されるプリンシパル。</span><span class="sxs-lookup"><span data-stu-id="b309d-147">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b309d-148">5 </span><span class="sxs-lookup"><span data-stu-id="b309d-148">5</span></span></p></td>
<td><p><span data-ttu-id="b309d-149">User</span><span class="sxs-lookup"><span data-stu-id="b309d-149">User</span></span></p></td>
<td><p><span data-ttu-id="b309d-150">標準のユーザー</span><span class="sxs-lookup"><span data-stu-id="b309d-150">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="b309d-151">はい</span><span class="sxs-lookup"><span data-stu-id="b309d-151">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b309d-152">8 </span><span class="sxs-lookup"><span data-stu-id="b309d-152">8</span></span></p></td>
<td><p><span data-ttu-id="b309d-153">DC</span><span class="sxs-lookup"><span data-stu-id="b309d-153">DC</span></span></p></td>
<td><p><span data-ttu-id="b309d-154">Active Directory ドメインサービスのドメインコントローラー。</span><span class="sxs-lookup"><span data-stu-id="b309d-154">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b309d-155">9 </span><span class="sxs-lookup"><span data-stu-id="b309d-155">9</span></span></p></td>
<td><p><span data-ttu-id="b309d-156">グループ</span><span class="sxs-lookup"><span data-stu-id="b309d-156">Group</span></span></p></td>
<td><p><span data-ttu-id="b309d-157">Active Directory セキュリティ グループ。</span><span class="sxs-lookup"><span data-stu-id="b309d-157">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b309d-158">10  </span><span class="sxs-lookup"><span data-stu-id="b309d-158">10</span></span></p></td>
<td><p><span data-ttu-id="b309d-159">フォルダー</span><span class="sxs-lookup"><span data-stu-id="b309d-159">Folder</span></span></p></td>
<td><p><span data-ttu-id="b309d-160">Active Directory コンテナーまたは組織単位。</span><span class="sxs-lookup"><span data-stu-id="b309d-160">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="b309d-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="b309d-161">See Also</span></span>


[<span data-ttu-id="b309d-162">Lync Server 2013 の tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="b309d-162">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

