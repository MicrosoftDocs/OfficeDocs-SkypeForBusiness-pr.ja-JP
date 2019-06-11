---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24f963b34ef6184675e724496d7d45ca1d40d27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="f8d6c-102">Lync Server 2013 の tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="f8d6c-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8d6c-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f8d6c-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f8d6c-104">tblPrincipal には、ユーザー、フォルダー、グループを含むすべてのプリンシパルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="f8d6c-105">行</span><span class="sxs-lookup"><span data-stu-id="f8d6c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8d6c-106">列</span><span class="sxs-lookup"><span data-stu-id="f8d6c-106">Column</span></span></th>
<th><span data-ttu-id="f8d6c-107">型</span><span class="sxs-lookup"><span data-stu-id="f8d6c-107">Type</span></span></th>
<th><span data-ttu-id="f8d6c-108">説明</span><span class="sxs-lookup"><span data-stu-id="f8d6c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8d6c-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f8d6c-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="f8d6c-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8d6c-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f8d6c-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-113">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="f8d6c-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-114">プリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-114">Principal GUID.</span></span> <span data-ttu-id="f8d6c-115">これは、プライマリキーとして広く使用されており、その意味は Active Directory ドメインサービスの領域にあります。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="f8d6c-116">(キャッシュされるプリンシパルの GUID は、対応する Active Directory オブジェクト GUID と同じです)。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8d6c-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="f8d6c-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-118">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="f8d6c-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-119">プリンシパル URI。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-119">Principal URI.</span></span> <span data-ttu-id="f8d6c-120">SIP スキームはユーザのために使用され、ma はその他ほとんどすべてに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-120">The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8d6c-121">prinName</span><span class="sxs-lookup"><span data-stu-id="f8d6c-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f8d6c-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-123">共通名。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-123">Common name.</span></span> <span data-ttu-id="f8d6c-124">ユーザーの種類によってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-124">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8d6c-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="f8d6c-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f8d6c-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-127">表示名。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-127">Display name.</span></span> <span data-ttu-id="f8d6c-128">ユーザーの種類によってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-128">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8d6c-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="f8d6c-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f8d6c-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-131">会社名。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-131">Company name.</span></span> <span data-ttu-id="f8d6c-132">ユーザーの種類によってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-132">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8d6c-133">メールをプリントする</span><span class="sxs-lookup"><span data-stu-id="f8d6c-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f8d6c-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-135">電子メール。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-135">Email.</span></span> <span data-ttu-id="f8d6c-136">ユーザーの種類によってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-136">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8d6c-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="f8d6c-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="f8d6c-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-139">プリンシパルがキャッシュされたバージョンである Active Directory オブジェクトのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-139">Domain name of the Active Directory object that the principal is a cached version of.</span></span> <span data-ttu-id="f8d6c-140">Active Directory オブジェクト (システムユーザーなど) ではない型の場合は Null にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-140">Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8d6c-141">プリント</span><span class="sxs-lookup"><span data-stu-id="f8d6c-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f8d6c-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-143">ユーザーのユーザープリンシパル名 (UPN)。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-143">User’s user principal name (UPN).</span></span> <span data-ttu-id="f8d6c-144">通常のユーザーの種類でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-144">Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8d6c-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="f8d6c-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-146">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="f8d6c-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f8d6c-147">0: プリンシパルは有効です。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="f8d6c-148">1: ユーザーの SIP 機能が無効になっているため、プリンシパルが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="f8d6c-149">2: 関連付けられている広告オブジェクトが削除されたため、プリンシパルが削除されました。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8d6c-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="f8d6c-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-151">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="f8d6c-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-152">プリンシパルの種類 (tblPrincipalType テーブルから)。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8d6c-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="f8d6c-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-154">Int</span><span class="sxs-lookup"><span data-stu-id="f8d6c-154">Int</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-155">プリンシパルの Lync プールの割り当て。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8d6c-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="f8d6c-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-157">Int</span><span class="sxs-lookup"><span data-stu-id="f8d6c-157">Int</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-158">タグの種類のポリシーが存在する場合は、ユーザーの常設チャットサーバーポリシーの値。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8d6c-159">プリント</span><span class="sxs-lookup"><span data-stu-id="f8d6c-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-160">int</span><span class="sxs-lookup"><span data-stu-id="f8d6c-160">int</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-161">作成者のプリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8d6c-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="f8d6c-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-163">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="f8d6c-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-164">作成時刻のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8d6c-165">プリント</span><span class="sxs-lookup"><span data-stu-id="f8d6c-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-166">int</span><span class="sxs-lookup"><span data-stu-id="f8d6c-166">int</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-167">最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8d6c-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="f8d6c-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-169">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="f8d6c-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-170">最終更新のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8d6c-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="f8d6c-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-172">datetime。 null ではありません</span><span class="sxs-lookup"><span data-stu-id="f8d6c-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-173">プリンシパルの前回の Active Directory 同期更新の日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f8d6c-174">機能</span><span class="sxs-lookup"><span data-stu-id="f8d6c-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8d6c-175">列</span><span class="sxs-lookup"><span data-stu-id="f8d6c-175">Column</span></span></th>
<th><span data-ttu-id="f8d6c-176">説明</span><span class="sxs-lookup"><span data-stu-id="f8d6c-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8d6c-177">prinID</span><span class="sxs-lookup"><span data-stu-id="f8d6c-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-178">主キー。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8d6c-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="f8d6c-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="f8d6c-180">TblPrincipalType テーブルで参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

