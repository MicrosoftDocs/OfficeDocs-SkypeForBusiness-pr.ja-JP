---
title: 'Lync Server 2013: tblPrincipal'
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
ms.openlocfilehash: b9d5122b375b4906320f254179ce101652ad6db2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="06012-102">Lync Server 2013 の tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="06012-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06012-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="06012-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="06012-104">tblPrincipal テーブルには、ユーザー、フォルダー、グループなど、すべてのプリンシパルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="06012-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="06012-105">Columns</span><span class="sxs-lookup"><span data-stu-id="06012-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06012-106">列</span><span class="sxs-lookup"><span data-stu-id="06012-106">Column</span></span></th>
<th><span data-ttu-id="06012-107">種類</span><span class="sxs-lookup"><span data-stu-id="06012-107">Type</span></span></th>
<th><span data-ttu-id="06012-108">説明</span><span class="sxs-lookup"><span data-stu-id="06012-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06012-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="06012-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="06012-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="06012-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="06012-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="06012-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06012-112">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="06012-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="06012-113">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="06012-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="06012-114">プリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="06012-114">Principal GUID.</span></span> <span data-ttu-id="06012-115">これは、代替主キーとして広く使用されています。これは、Active Directory ドメインサービスの領域にわたる意味があるためです。</span><span class="sxs-lookup"><span data-stu-id="06012-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="06012-116">(キャッシュされたプリンシパルの GUID は、対応する Active Directory オブジェクトの GUID と同じです。)</span><span class="sxs-lookup"><span data-stu-id="06012-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06012-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="06012-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="06012-118">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="06012-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="06012-p102">プリンシパル URI。SIP スキームはユーザーで使用され、ma-grp はユーザーを除くほぼすべてで使用されます。</span><span class="sxs-lookup"><span data-stu-id="06012-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06012-121">prinName</span><span class="sxs-lookup"><span data-stu-id="06012-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="06012-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="06012-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="06012-p103">共通名。ユーザーの種類でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="06012-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06012-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="06012-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="06012-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="06012-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="06012-p104">表示名。ユーザーの種類でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="06012-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06012-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="06012-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="06012-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="06012-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="06012-p105">会社名。ユーザーの種類でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="06012-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06012-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="06012-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="06012-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="06012-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="06012-p106">電子メール。ユーザーの種類でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="06012-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06012-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="06012-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="06012-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="06012-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="06012-p107">プリンシパルがキャッシュされたバージョンである Active Directory オブジェクトのドメイン名。Active Directory オブジェクトでない種類 (システム ユーザーなど) では NULL になります。</span><span class="sxs-lookup"><span data-stu-id="06012-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06012-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="06012-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="06012-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="06012-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="06012-p108">ユーザーのユーザー プリンシパル名 (UPN)。通常のユーザーの種類でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="06012-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06012-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="06012-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="06012-146">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="06012-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="06012-147">0: プリンシパルはアクティブです。</span><span class="sxs-lookup"><span data-stu-id="06012-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="06012-148">1: ユーザーの SIP 機能が無効であるため、プリンシパルは無効です。</span><span class="sxs-lookup"><span data-stu-id="06012-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="06012-149">2: 関連付けられている AD オブジェクトが削除されたため、プリンシパルは削除されます。</span><span class="sxs-lookup"><span data-stu-id="06012-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06012-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="06012-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="06012-151">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="06012-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="06012-152">プリンシパルの種類 (tblPrincipalType テーブルに基づいています)。</span><span class="sxs-lookup"><span data-stu-id="06012-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06012-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="06012-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="06012-154">Int</span><span class="sxs-lookup"><span data-stu-id="06012-154">Int</span></span></p></td>
<td><p><span data-ttu-id="06012-155">プリンシパルの Lync プールの割り当て。</span><span class="sxs-lookup"><span data-stu-id="06012-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06012-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="06012-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="06012-157">Int</span><span class="sxs-lookup"><span data-stu-id="06012-157">Int</span></span></p></td>
<td><p><span data-ttu-id="06012-158">タグの種類のポリシーが存在する場合、ユーザーの常設チャットサーバーポリシーの値。</span><span class="sxs-lookup"><span data-stu-id="06012-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06012-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="06012-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="06012-160">int</span><span class="sxs-lookup"><span data-stu-id="06012-160">int</span></span></p></td>
<td><p><span data-ttu-id="06012-161">作成者のプリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="06012-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06012-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="06012-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="06012-163">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="06012-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="06012-164">作成時刻のタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="06012-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06012-165">プリント</span><span class="sxs-lookup"><span data-stu-id="06012-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="06012-166">int</span><span class="sxs-lookup"><span data-stu-id="06012-166">int</span></span></p></td>
<td><p><span data-ttu-id="06012-167">このテーブルを最後に更新したプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="06012-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06012-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="06012-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="06012-169">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="06012-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="06012-170">最後の更新のタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="06012-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06012-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="06012-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="06012-172">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="06012-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="06012-173">プリンシパルに対する Active Directory の同期による最終更新の日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="06012-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="06012-174">Keys</span><span class="sxs-lookup"><span data-stu-id="06012-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06012-175">列</span><span class="sxs-lookup"><span data-stu-id="06012-175">Column</span></span></th>
<th><span data-ttu-id="06012-176">説明</span><span class="sxs-lookup"><span data-stu-id="06012-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06012-177">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="06012-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="06012-178">主キー。</span><span class="sxs-lookup"><span data-stu-id="06012-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06012-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="06012-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="06012-180">tblPrincipalType.ptypeID テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="06012-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

