---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="6e557-102">Lync Server 2013 の tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="6e557-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e557-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="6e557-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="6e557-104">tblPrincipalType には、tblPrincipal テーブルの内容を分類するためのプリンシパルの種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e557-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="6e557-105">行</span><span class="sxs-lookup"><span data-stu-id="6e557-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e557-106">列</span><span class="sxs-lookup"><span data-stu-id="6e557-106">Column</span></span></th>
<th><span data-ttu-id="6e557-107">型</span><span class="sxs-lookup"><span data-stu-id="6e557-107">Type</span></span></th>
<th><span data-ttu-id="6e557-108">説明</span><span class="sxs-lookup"><span data-stu-id="6e557-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e557-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="6e557-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="6e557-110">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="6e557-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="6e557-111">プリンシパルの種類 ID。</span><span class="sxs-lookup"><span data-stu-id="6e557-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e557-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="6e557-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="6e557-113">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="6e557-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="6e557-114">型の説明。</span><span class="sxs-lookup"><span data-stu-id="6e557-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e557-115">ptypeIsSystemUser 場合</span><span class="sxs-lookup"><span data-stu-id="6e557-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="6e557-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="6e557-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="6e557-117">内部目的で使用されるプリンシパルに対応する型の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="6e557-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e557-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="6e557-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="6e557-119">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="6e557-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="6e557-120">型がユーザーの型である場合は True です。</span><span class="sxs-lookup"><span data-stu-id="6e557-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="6e557-121">キー</span><span class="sxs-lookup"><span data-stu-id="6e557-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e557-122">列</span><span class="sxs-lookup"><span data-stu-id="6e557-122">Column</span></span></th>
<th><span data-ttu-id="6e557-123">説明</span><span class="sxs-lookup"><span data-stu-id="6e557-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e557-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="6e557-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="6e557-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="6e557-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="6e557-126">プリンシパルの値</span><span class="sxs-lookup"><span data-stu-id="6e557-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e557-127">ID</span><span class="sxs-lookup"><span data-stu-id="6e557-127">ID</span></span></th>
<th><span data-ttu-id="6e557-128">役割</span><span class="sxs-lookup"><span data-stu-id="6e557-128">Role</span></span></th>
<th><span data-ttu-id="6e557-129">説明</span><span class="sxs-lookup"><span data-stu-id="6e557-129">Description</span></span></th>
<th><span data-ttu-id="6e557-130">[ユーザー]</span><span class="sxs-lookup"><span data-stu-id="6e557-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e557-131">1</span><span class="sxs-lookup"><span data-stu-id="6e557-131">1</span></span></p></td>
<td><p><span data-ttu-id="6e557-132">任意</span><span class="sxs-lookup"><span data-stu-id="6e557-132">Any</span></span></p></td>
<td><p><span data-ttu-id="6e557-133">既知の型のない汎用プリンシパル。</span><span class="sxs-lookup"><span data-stu-id="6e557-133">Generic principal with no known type.</span></span> <span data-ttu-id="6e557-134">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="6e557-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e557-135">2</span><span class="sxs-lookup"><span data-stu-id="6e557-135">2</span></span></p></td>
<td><p><span data-ttu-id="6e557-136">任意のユーザー</span><span class="sxs-lookup"><span data-stu-id="6e557-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="6e557-137">ユーザーの種類の汎用プリンシパル。</span><span class="sxs-lookup"><span data-stu-id="6e557-137">Generic principal of user type.</span></span> <span data-ttu-id="6e557-138">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="6e557-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="6e557-139">はい</span><span class="sxs-lookup"><span data-stu-id="6e557-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e557-140">3</span><span class="sxs-lookup"><span data-stu-id="6e557-140">3</span></span></p></td>
<td><p><span data-ttu-id="6e557-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="6e557-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="6e557-142">グループの意味を持つ汎用プリンシパル。</span><span class="sxs-lookup"><span data-stu-id="6e557-142">Generic principal with group semantic.</span></span> <span data-ttu-id="6e557-143">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="6e557-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e557-144">4</span><span class="sxs-lookup"><span data-stu-id="6e557-144">4</span></span></p></td>
<td><p><span data-ttu-id="6e557-145">他のお互い</span><span class="sxs-lookup"><span data-stu-id="6e557-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="6e557-146">常設チャットサーバーで内部的に使用されているプリンシパル。</span><span class="sxs-lookup"><span data-stu-id="6e557-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e557-147">5</span><span class="sxs-lookup"><span data-stu-id="6e557-147">5</span></span></p></td>
<td><p><span data-ttu-id="6e557-148">ユーザー</span><span class="sxs-lookup"><span data-stu-id="6e557-148">User</span></span></p></td>
<td><p><span data-ttu-id="6e557-149">標準ユーザー。</span><span class="sxs-lookup"><span data-stu-id="6e557-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="6e557-150">はい</span><span class="sxs-lookup"><span data-stu-id="6e557-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e557-151">個</span><span class="sxs-lookup"><span data-stu-id="6e557-151">8</span></span></p></td>
<td><p><span data-ttu-id="6e557-152">修飾</span><span class="sxs-lookup"><span data-stu-id="6e557-152">DC</span></span></p></td>
<td><p><span data-ttu-id="6e557-153">Active Directory ドメインサービスのドメインコントローラー。</span><span class="sxs-lookup"><span data-stu-id="6e557-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e557-154">ファイブ</span><span class="sxs-lookup"><span data-stu-id="6e557-154">9</span></span></p></td>
<td><p><span data-ttu-id="6e557-155">化</span><span class="sxs-lookup"><span data-stu-id="6e557-155">Group</span></span></p></td>
<td><p><span data-ttu-id="6e557-156">Active Directory セキュリティグループ。</span><span class="sxs-lookup"><span data-stu-id="6e557-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e557-157">常用</span><span class="sxs-lookup"><span data-stu-id="6e557-157">10</span></span></p></td>
<td><p><span data-ttu-id="6e557-158">]</span><span class="sxs-lookup"><span data-stu-id="6e557-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="6e557-159">Active Directory コンテナーまたは組織単位。</span><span class="sxs-lookup"><span data-stu-id="6e557-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="6e557-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e557-160">See Also</span></span>


[<span data-ttu-id="6e557-161">Lync Server 2013 の tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="6e557-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

