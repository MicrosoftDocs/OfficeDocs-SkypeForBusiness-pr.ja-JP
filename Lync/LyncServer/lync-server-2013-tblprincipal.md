---
title: 'Lync Server 2013: tblPrincipal'
description: 'Lync Server 2013: tblPrincipal。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f07b37ac4c8ceed5c044b5c263eeee6370adfdc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547493"
---
# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="bc42e-103">Lync Server 2013 の tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="bc42e-103">tblPrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc42e-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bc42e-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bc42e-105">tblPrincipal テーブルには、ユーザー、フォルダー、グループなど、すべてのプリンシパルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="bc42e-105">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="bc42e-106">段組み</span><span class="sxs-lookup"><span data-stu-id="bc42e-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc42e-107">Column</span><span class="sxs-lookup"><span data-stu-id="bc42e-107">Column</span></span></th>
<th><span data-ttu-id="bc42e-108">種類</span><span class="sxs-lookup"><span data-stu-id="bc42e-108">Type</span></span></th>
<th><span data-ttu-id="bc42e-109">説明</span><span class="sxs-lookup"><span data-stu-id="bc42e-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc42e-110">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="bc42e-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="bc42e-111">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="bc42e-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bc42e-112">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="bc42e-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc42e-113">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="bc42e-113">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="bc42e-114">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="bc42e-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="bc42e-115">プリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="bc42e-115">Principal GUID.</span></span> <span data-ttu-id="bc42e-116">これは、代替主キーとして広く使用されています。これは、Active Directory ドメインサービスの領域にわたる意味があるためです。</span><span class="sxs-lookup"><span data-stu-id="bc42e-116">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="bc42e-117">(キャッシュされたプリンシパルの GUID は、対応する Active Directory オブジェクトの GUID と同じです。)</span><span class="sxs-lookup"><span data-stu-id="bc42e-117">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc42e-118">prinUri</span><span class="sxs-lookup"><span data-stu-id="bc42e-118">prinUri</span></span></p></td>
<td><p><span data-ttu-id="bc42e-119">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bc42e-119">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="bc42e-p102">プリンシパル URI。SIP スキームはユーザーで使用され、ma-grp はユーザーを除くほぼすべてで使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc42e-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc42e-122">prinName</span><span class="sxs-lookup"><span data-stu-id="bc42e-122">prinName</span></span></p></td>
<td><p><span data-ttu-id="bc42e-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bc42e-123">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="bc42e-p103">共通名。ユーザーの種類でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc42e-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc42e-126">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="bc42e-126">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="bc42e-127">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bc42e-127">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="bc42e-p104">表示名。ユーザーの種類でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc42e-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc42e-130">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="bc42e-130">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="bc42e-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bc42e-131">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="bc42e-p105">会社名。ユーザーの種類でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc42e-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc42e-134">prinEmail</span><span class="sxs-lookup"><span data-stu-id="bc42e-134">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="bc42e-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bc42e-135">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="bc42e-p106">電子メール。ユーザーの種類でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc42e-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc42e-138">prinADPath</span><span class="sxs-lookup"><span data-stu-id="bc42e-138">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="bc42e-139">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="bc42e-139">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="bc42e-p107">プリンシパルがキャッシュされたバージョンである Active Directory オブジェクトのドメイン名。Active Directory オブジェクトでない種類 (システム ユーザーなど) では NULL になります。</span><span class="sxs-lookup"><span data-stu-id="bc42e-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc42e-142">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="bc42e-142">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="bc42e-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bc42e-143">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="bc42e-p108">ユーザーのユーザー プリンシパル名 (UPN)。通常のユーザーの種類でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc42e-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc42e-146">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="bc42e-146">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="bc42e-147">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="bc42e-147">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bc42e-148">0: プリンシパルはアクティブです。</span><span class="sxs-lookup"><span data-stu-id="bc42e-148">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="bc42e-149">1: ユーザーの SIP 機能が無効であるため、プリンシパルは無効です。</span><span class="sxs-lookup"><span data-stu-id="bc42e-149">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="bc42e-150">2: 関連付けられている AD オブジェクトが削除されたため、プリンシパルは削除されます。</span><span class="sxs-lookup"><span data-stu-id="bc42e-150">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc42e-151">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="bc42e-151">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="bc42e-152">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="bc42e-152">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="bc42e-153">プリンシパルの種類 (tblPrincipalType テーブルに基づいています)。</span><span class="sxs-lookup"><span data-stu-id="bc42e-153">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc42e-154">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="bc42e-154">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="bc42e-155">Int</span><span class="sxs-lookup"><span data-stu-id="bc42e-155">Int</span></span></p></td>
<td><p><span data-ttu-id="bc42e-156">プリンシパルの Lync プールの割り当て。</span><span class="sxs-lookup"><span data-stu-id="bc42e-156">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc42e-157">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="bc42e-157">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="bc42e-158">Int</span><span class="sxs-lookup"><span data-stu-id="bc42e-158">Int</span></span></p></td>
<td><p><span data-ttu-id="bc42e-159">タグの種類のポリシーが存在する場合、ユーザーの常設チャットサーバーポリシーの値。</span><span class="sxs-lookup"><span data-stu-id="bc42e-159">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc42e-160">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="bc42e-160">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="bc42e-161">int</span><span class="sxs-lookup"><span data-stu-id="bc42e-161">int</span></span></p></td>
<td><p><span data-ttu-id="bc42e-162">作成者のプリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="bc42e-162">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc42e-163">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="bc42e-163">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="bc42e-164">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="bc42e-164">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="bc42e-165">作成時刻のタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="bc42e-165">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc42e-166">プリント</span><span class="sxs-lookup"><span data-stu-id="bc42e-166">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="bc42e-167">int</span><span class="sxs-lookup"><span data-stu-id="bc42e-167">int</span></span></p></td>
<td><p><span data-ttu-id="bc42e-168">このテーブルを最後に更新したプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="bc42e-168">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc42e-169">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="bc42e-169">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="bc42e-170">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="bc42e-170">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="bc42e-171">最後の更新のタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="bc42e-171">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc42e-172">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="bc42e-172">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="bc42e-173">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="bc42e-173">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="bc42e-174">プリンシパルに対する Active Directory の同期による最終更新の日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="bc42e-174">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bc42e-175">Keys</span><span class="sxs-lookup"><span data-stu-id="bc42e-175">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc42e-176">列</span><span class="sxs-lookup"><span data-stu-id="bc42e-176">Column</span></span></th>
<th><span data-ttu-id="bc42e-177">説明</span><span class="sxs-lookup"><span data-stu-id="bc42e-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc42e-178">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="bc42e-178">prinID</span></span></p></td>
<td><p><span data-ttu-id="bc42e-179">主キー。</span><span class="sxs-lookup"><span data-stu-id="bc42e-179">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc42e-180">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="bc42e-180">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="bc42e-181">tblPrincipalType.ptypeID テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="bc42e-181">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

