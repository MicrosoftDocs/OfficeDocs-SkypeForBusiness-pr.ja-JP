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
ms.openlocfilehash: 6731d0bcda6e4e66b1b498a5f1bf91023627b1f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="18481-102">Lync Server 2013 の tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="18481-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18481-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="18481-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="18481-104">tblPrincipalType には、tblPrincipal テーブルの内容を分類するためのプリンシパルの種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="18481-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="18481-105">行</span><span class="sxs-lookup"><span data-stu-id="18481-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18481-106">列</span><span class="sxs-lookup"><span data-stu-id="18481-106">Column</span></span></th>
<th><span data-ttu-id="18481-107">型</span><span class="sxs-lookup"><span data-stu-id="18481-107">Type</span></span></th>
<th><span data-ttu-id="18481-108">説明</span><span class="sxs-lookup"><span data-stu-id="18481-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18481-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="18481-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="18481-110">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="18481-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="18481-111">プリンシパルの種類 ID。</span><span class="sxs-lookup"><span data-stu-id="18481-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18481-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="18481-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="18481-113">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="18481-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="18481-114">型の説明。</span><span class="sxs-lookup"><span data-stu-id="18481-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18481-115">ptypeIsSystemUser 場合</span><span class="sxs-lookup"><span data-stu-id="18481-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="18481-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="18481-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="18481-117">内部目的で使用されるプリンシパルに対応する型の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="18481-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18481-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="18481-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="18481-119">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="18481-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="18481-120">型がユーザーの型である場合は True です。</span><span class="sxs-lookup"><span data-stu-id="18481-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="18481-121">キー</span><span class="sxs-lookup"><span data-stu-id="18481-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18481-122">列</span><span class="sxs-lookup"><span data-stu-id="18481-122">Column</span></span></th>
<th><span data-ttu-id="18481-123">説明</span><span class="sxs-lookup"><span data-stu-id="18481-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18481-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="18481-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="18481-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="18481-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="18481-126">プリンシパルの値</span><span class="sxs-lookup"><span data-stu-id="18481-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18481-127">ID</span><span class="sxs-lookup"><span data-stu-id="18481-127">ID</span></span></th>
<th><span data-ttu-id="18481-128">役割</span><span class="sxs-lookup"><span data-stu-id="18481-128">Role</span></span></th>
<th><span data-ttu-id="18481-129">説明</span><span class="sxs-lookup"><span data-stu-id="18481-129">Description</span></span></th>
<th><span data-ttu-id="18481-130">[ユーザー]</span><span class="sxs-lookup"><span data-stu-id="18481-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18481-131">1</span><span class="sxs-lookup"><span data-stu-id="18481-131">1</span></span></p></td>
<td><p><span data-ttu-id="18481-132">任意</span><span class="sxs-lookup"><span data-stu-id="18481-132">Any</span></span></p></td>
<td><p><span data-ttu-id="18481-133">既知の型のない汎用プリンシパル。</span><span class="sxs-lookup"><span data-stu-id="18481-133">Generic principal with no known type.</span></span> <span data-ttu-id="18481-134">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="18481-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18481-135">両面</span><span class="sxs-lookup"><span data-stu-id="18481-135">2</span></span></p></td>
<td><p><span data-ttu-id="18481-136">任意のユーザー</span><span class="sxs-lookup"><span data-stu-id="18481-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="18481-137">ユーザーの種類の汎用プリンシパル。</span><span class="sxs-lookup"><span data-stu-id="18481-137">Generic principal of user type.</span></span> <span data-ttu-id="18481-138">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="18481-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="18481-139">はい</span><span class="sxs-lookup"><span data-stu-id="18481-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18481-140">3</span><span class="sxs-lookup"><span data-stu-id="18481-140">3</span></span></p></td>
<td><p><span data-ttu-id="18481-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="18481-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="18481-142">グループの意味を持つ汎用プリンシパル。</span><span class="sxs-lookup"><span data-stu-id="18481-142">Generic principal with group semantic.</span></span> <span data-ttu-id="18481-143">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="18481-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18481-144">4</span><span class="sxs-lookup"><span data-stu-id="18481-144">4</span></span></p></td>
<td><p><span data-ttu-id="18481-145">他のお互い</span><span class="sxs-lookup"><span data-stu-id="18481-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="18481-146">常設チャットサーバーで内部的に使用されているプリンシパル。</span><span class="sxs-lookup"><span data-stu-id="18481-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18481-147">5</span><span class="sxs-lookup"><span data-stu-id="18481-147">5</span></span></p></td>
<td><p><span data-ttu-id="18481-148">ユーザー</span><span class="sxs-lookup"><span data-stu-id="18481-148">User</span></span></p></td>
<td><p><span data-ttu-id="18481-149">標準ユーザー。</span><span class="sxs-lookup"><span data-stu-id="18481-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="18481-150">はい</span><span class="sxs-lookup"><span data-stu-id="18481-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18481-151">個</span><span class="sxs-lookup"><span data-stu-id="18481-151">8</span></span></p></td>
<td><p><span data-ttu-id="18481-152">修飾</span><span class="sxs-lookup"><span data-stu-id="18481-152">DC</span></span></p></td>
<td><p><span data-ttu-id="18481-153">Active Directory ドメインサービスのドメインコントローラー。</span><span class="sxs-lookup"><span data-stu-id="18481-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18481-154">ファイブ</span><span class="sxs-lookup"><span data-stu-id="18481-154">9</span></span></p></td>
<td><p><span data-ttu-id="18481-155">化</span><span class="sxs-lookup"><span data-stu-id="18481-155">Group</span></span></p></td>
<td><p><span data-ttu-id="18481-156">Active Directory セキュリティグループ。</span><span class="sxs-lookup"><span data-stu-id="18481-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18481-157">常用</span><span class="sxs-lookup"><span data-stu-id="18481-157">10</span></span></p></td>
<td><p><span data-ttu-id="18481-158">]</span><span class="sxs-lookup"><span data-stu-id="18481-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="18481-159">Active Directory コンテナーまたは組織単位。</span><span class="sxs-lookup"><span data-stu-id="18481-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="18481-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="18481-160">See Also</span></span>


[<span data-ttu-id="18481-161">Lync Server 2013 の tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="18481-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

