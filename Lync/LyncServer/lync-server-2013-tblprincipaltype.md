---
title: 'Lync Server 2013: tblPrincipalType'
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
ms.openlocfilehash: 60fa841f7f88e0da2c428ae68c5007fb79e6c69d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536324"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="e75f7-102">Lync Server 2013 の tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="e75f7-102">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e75f7-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e75f7-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e75f7-104">tblPrincipal テーブルには、tblPrincipal テーブルの内容を分類するプリンシパル型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e75f7-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="e75f7-105">段組み</span><span class="sxs-lookup"><span data-stu-id="e75f7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e75f7-106">Column</span><span class="sxs-lookup"><span data-stu-id="e75f7-106">Column</span></span></th>
<th><span data-ttu-id="e75f7-107">種類</span><span class="sxs-lookup"><span data-stu-id="e75f7-107">Type</span></span></th>
<th><span data-ttu-id="e75f7-108">説明</span><span class="sxs-lookup"><span data-stu-id="e75f7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e75f7-109">Tblprincipaltype.ptypeid</span><span class="sxs-lookup"><span data-stu-id="e75f7-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="e75f7-110">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="e75f7-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="e75f7-111">プリンシパル型 ID。</span><span class="sxs-lookup"><span data-stu-id="e75f7-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e75f7-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="e75f7-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="e75f7-113">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e75f7-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="e75f7-114">型の説明。</span><span class="sxs-lookup"><span data-stu-id="e75f7-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e75f7-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="e75f7-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="e75f7-116">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="e75f7-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e75f7-117">型が内部の用途で使用されるプリンシパルに対応する場合、True。</span><span class="sxs-lookup"><span data-stu-id="e75f7-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e75f7-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="e75f7-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="e75f7-119">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="e75f7-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e75f7-120">型がユーザー型の場合、True。</span><span class="sxs-lookup"><span data-stu-id="e75f7-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="e75f7-121">キー</span><span class="sxs-lookup"><span data-stu-id="e75f7-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e75f7-122">列</span><span class="sxs-lookup"><span data-stu-id="e75f7-122">Column</span></span></th>
<th><span data-ttu-id="e75f7-123">説明</span><span class="sxs-lookup"><span data-stu-id="e75f7-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e75f7-124">Tblprincipaltype.ptypeid</span><span class="sxs-lookup"><span data-stu-id="e75f7-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="e75f7-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="e75f7-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="e75f7-126">プリンシパル値</span><span class="sxs-lookup"><span data-stu-id="e75f7-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e75f7-127">ID</span><span class="sxs-lookup"><span data-stu-id="e75f7-127">ID</span></span></th>
<th><span data-ttu-id="e75f7-128">Role</span><span class="sxs-lookup"><span data-stu-id="e75f7-128">Role</span></span></th>
<th><span data-ttu-id="e75f7-129">説明</span><span class="sxs-lookup"><span data-stu-id="e75f7-129">Description</span></span></th>
<th><span data-ttu-id="e75f7-130">User</span><span class="sxs-lookup"><span data-stu-id="e75f7-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e75f7-131">1-d</span><span class="sxs-lookup"><span data-stu-id="e75f7-131">1</span></span></p></td>
<td><p><span data-ttu-id="e75f7-132">任意</span><span class="sxs-lookup"><span data-stu-id="e75f7-132">Any</span></span></p></td>
<td><p><span data-ttu-id="e75f7-p101">既知の型を持たない汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="e75f7-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e75f7-135">pbm-2</span><span class="sxs-lookup"><span data-stu-id="e75f7-135">2</span></span></p></td>
<td><p><span data-ttu-id="e75f7-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="e75f7-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="e75f7-p102">ユーザー型の汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="e75f7-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="e75f7-139">はい</span><span class="sxs-lookup"><span data-stu-id="e75f7-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e75f7-140">1/3</span><span class="sxs-lookup"><span data-stu-id="e75f7-140">3</span></span></p></td>
<td><p><span data-ttu-id="e75f7-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="e75f7-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="e75f7-p103">グループ セマンティックを持つ汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="e75f7-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e75f7-144">4 </span><span class="sxs-lookup"><span data-stu-id="e75f7-144">4</span></span></p></td>
<td><p><span data-ttu-id="e75f7-145">自分のもの</span><span class="sxs-lookup"><span data-stu-id="e75f7-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="e75f7-146">常設チャットサーバーによって内部的に使用されるプリンシパル。</span><span class="sxs-lookup"><span data-stu-id="e75f7-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e75f7-147">5 </span><span class="sxs-lookup"><span data-stu-id="e75f7-147">5</span></span></p></td>
<td><p><span data-ttu-id="e75f7-148">User</span><span class="sxs-lookup"><span data-stu-id="e75f7-148">User</span></span></p></td>
<td><p><span data-ttu-id="e75f7-149">標準のユーザー</span><span class="sxs-lookup"><span data-stu-id="e75f7-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="e75f7-150">はい</span><span class="sxs-lookup"><span data-stu-id="e75f7-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e75f7-151">8 </span><span class="sxs-lookup"><span data-stu-id="e75f7-151">8</span></span></p></td>
<td><p><span data-ttu-id="e75f7-152">DC</span><span class="sxs-lookup"><span data-stu-id="e75f7-152">DC</span></span></p></td>
<td><p><span data-ttu-id="e75f7-153">Active Directory ドメインサービスのドメインコントローラー。</span><span class="sxs-lookup"><span data-stu-id="e75f7-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e75f7-154">9 </span><span class="sxs-lookup"><span data-stu-id="e75f7-154">9</span></span></p></td>
<td><p><span data-ttu-id="e75f7-155">グループ</span><span class="sxs-lookup"><span data-stu-id="e75f7-155">Group</span></span></p></td>
<td><p><span data-ttu-id="e75f7-156">Active Directory セキュリティ グループ。</span><span class="sxs-lookup"><span data-stu-id="e75f7-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e75f7-157">10  </span><span class="sxs-lookup"><span data-stu-id="e75f7-157">10</span></span></p></td>
<td><p><span data-ttu-id="e75f7-158">フォルダー</span><span class="sxs-lookup"><span data-stu-id="e75f7-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="e75f7-159">Active Directory コンテナーまたは組織単位。</span><span class="sxs-lookup"><span data-stu-id="e75f7-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="e75f7-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="e75f7-160">See Also</span></span>


[<span data-ttu-id="e75f7-161">Lync Server 2013 の tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="e75f7-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

