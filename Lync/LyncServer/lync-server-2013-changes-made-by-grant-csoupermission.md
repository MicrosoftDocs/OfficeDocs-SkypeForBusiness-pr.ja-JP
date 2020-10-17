---
title: 'Lync Server 2013: Grant-CsOUPermission によって加えられた変更'
description: 'Lync Server 2013: Grant-CsOUPermission によって行われた変更。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d3db0e9dde380628690bc016e2b4bd2ec85b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543613"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="ffce1-103">Lync Server 2013 での Grant-CsOUPermission による変更</span><span class="sxs-lookup"><span data-stu-id="ffce1-103">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffce1-104">_**トピックの最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="ffce1-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="ffce1-105">Lync Server 2013 の管理を委任するには、指定された組織単位 (Ou) にアクセス許可を追加して、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが Domain Admins グループのメンバーにならずに Ou にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="ffce1-105">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="ffce1-106">**Grant-CsOuPermission** コマンドレットは、次の表で指定されているように、指定された OU 内のオブジェクトへのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="ffce1-106">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="ffce1-107">ユーザー オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="ffce1-107">Granting Permission for User Objects</span></span>

<span data-ttu-id="ffce1-108">OU 上のユーザー オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ffce1-108">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="ffce1-109">ユーザー オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffce1-109">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffce1-110">グループ</span><span class="sxs-lookup"><span data-stu-id="ffce1-110">Group</span></span></th>
<th><span data-ttu-id="ffce1-111">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffce1-111">Permission</span></span></th>
<th><span data-ttu-id="ffce1-112">適用対象</span><span class="sxs-lookup"><span data-stu-id="ffce1-112">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-113">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffce1-113">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffce1-114">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="ffce1-114">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffce1-115">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-115">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffce1-116">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-116">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-117">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="ffce1-117">List contents</span></span></p>
<p><span data-ttu-id="ffce1-118">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-118">Read all properties</span></span></p>
<p><span data-ttu-id="ffce1-119">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-119">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-120">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-120">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-121">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-121">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-122">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="ffce1-122">List contents</span></span></p>
<p><span data-ttu-id="ffce1-123">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-123">Read all properties</span></span></p>
<p><span data-ttu-id="ffce1-124">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-124">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-125">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-125">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffce1-126">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-126">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-127">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-127">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-128">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-128">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-129">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-129">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-130">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-130">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffce1-131">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-131">Read General-Information</span></span></p>
<p><span data-ttu-id="ffce1-132">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-132">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-133">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffce1-133">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffce1-134">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffce1-135">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-135">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-136">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-136">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="ffce1-137">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-137">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-138">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-138">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-139">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-139">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ffce1-140">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffce1-140">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="ffce1-141">コンピューター オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="ffce1-141">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="ffce1-142">OU 上のコンピューター オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ffce1-142">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="ffce1-143">コンピューター オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffce1-143">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffce1-144">グループ</span><span class="sxs-lookup"><span data-stu-id="ffce1-144">Group</span></span></th>
<th><span data-ttu-id="ffce1-145">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffce1-145">Permission</span></span></th>
<th><span data-ttu-id="ffce1-146">適用対象</span><span class="sxs-lookup"><span data-stu-id="ffce1-146">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-147">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffce1-147">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffce1-148">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="ffce1-148">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffce1-149">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-149">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffce1-150">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-150">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-151">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="ffce1-151">List contents</span></span></p>
<p><span data-ttu-id="ffce1-152">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-152">Read all properties</span></span></p>
<p><span data-ttu-id="ffce1-153">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-153">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-154">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-154">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-155">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-155">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-156">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="ffce1-156">List contents</span></span></p>
<p><span data-ttu-id="ffce1-157">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-157">Read all properties</span></span></p>
<p><span data-ttu-id="ffce1-158">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-158">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-159">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-159">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffce1-160">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-160">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-161">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-161">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffce1-162">Validated-DNS-Host-Name の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-162">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="ffce1-163">子のコンピューター オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffce1-163">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-164">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffce1-164">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffce1-165">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-165">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffce1-166">Validated-DNS-Host-Name の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-166">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="ffce1-167">子のコンピューター オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffce1-167">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="ffce1-168">連絡先または AppContact オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="ffce1-168">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="ffce1-169">OU 上の連絡先オブジェクトまたは AppContact オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ffce1-169">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="ffce1-170">連絡先または AppContact オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffce1-170">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffce1-171">グループ</span><span class="sxs-lookup"><span data-stu-id="ffce1-171">Group</span></span></th>
<th><span data-ttu-id="ffce1-172">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffce1-172">Permission</span></span></th>
<th><span data-ttu-id="ffce1-173">適用対象</span><span class="sxs-lookup"><span data-stu-id="ffce1-173">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-174">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffce1-174">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffce1-175">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="ffce1-175">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffce1-176">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-176">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffce1-177">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-177">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-178">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="ffce1-178">List contents</span></span></p>
<p><span data-ttu-id="ffce1-179">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-179">Read all properties</span></span></p>
<p><span data-ttu-id="ffce1-180">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-180">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-181">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-181">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-182">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-182">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-183">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="ffce1-183">List contents</span></span></p>
<p><span data-ttu-id="ffce1-184">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-184">Read all properties</span></span></p>
<p><span data-ttu-id="ffce1-185">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-185">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-186">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-186">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffce1-187">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-187">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-188">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-188">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-189">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-189">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-190">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-190">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-191">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-191">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffce1-192">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-192">Read General-Information</span></span></p>
<p><span data-ttu-id="ffce1-193">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-193">Read Personal-Information</span></span></p>
<p><span data-ttu-id="ffce1-194">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-194">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-195">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffce1-195">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-196">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffce1-196">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffce1-197">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-197">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-198">otherIpPhone の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-198">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="ffce1-199">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-199">Write displayName</span></span></p>
<p><span data-ttu-id="ffce1-200">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-200">Write description</span></span></p>
<p><span data-ttu-id="ffce1-201">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-201">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="ffce1-202">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-202">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="ffce1-203">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-203">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-204">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-204">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-205">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-205">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ffce1-206">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffce1-206">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="ffce1-207">デバイス オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="ffce1-207">Granting Permission for Device Objects</span></span>

<span data-ttu-id="ffce1-208">OU 上のデバイス オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ffce1-208">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="ffce1-209">デバイス オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffce1-209">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffce1-210">グループ</span><span class="sxs-lookup"><span data-stu-id="ffce1-210">Group</span></span></th>
<th><span data-ttu-id="ffce1-211">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffce1-211">Permission</span></span></th>
<th><span data-ttu-id="ffce1-212">適用対象</span><span class="sxs-lookup"><span data-stu-id="ffce1-212">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-213">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffce1-213">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffce1-214">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="ffce1-214">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffce1-215">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-215">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffce1-216">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-216">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-217">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="ffce1-217">List contents</span></span></p>
<p><span data-ttu-id="ffce1-218">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-218">Read all properties</span></span></p>
<p><span data-ttu-id="ffce1-219">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-219">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-220">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-220">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-221">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-221">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-222">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="ffce1-222">List contents</span></span></p>
<p><span data-ttu-id="ffce1-223">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-223">Read all properties</span></span></p>
<p><span data-ttu-id="ffce1-224">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-224">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-225">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-225">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffce1-226">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-226">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-227">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-227">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-228">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-228">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-229">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-229">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-230">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-230">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffce1-231">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-231">Read Personal-Information</span></span></p>
<p><span data-ttu-id="ffce1-232">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-232">Read General-Information</span></span></p>
<p><span data-ttu-id="ffce1-233">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-233">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-234">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffce1-234">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-235">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffce1-235">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffce1-236">子の作成</span><span class="sxs-lookup"><span data-stu-id="ffce1-236">Create child</span></span></p>
<p><span data-ttu-id="ffce1-237">子の削除</span><span class="sxs-lookup"><span data-stu-id="ffce1-237">Delete child</span></span></p>
<p><span data-ttu-id="ffce1-238">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="ffce1-238">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="ffce1-239">Contact</span><span class="sxs-lookup"><span data-stu-id="ffce1-239">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffce1-240">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffce1-240">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffce1-241">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-241">Write displayName</span></span></p>
<p><span data-ttu-id="ffce1-242">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-242">Write description</span></span></p>
<p><span data-ttu-id="ffce1-243">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-243">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="ffce1-244">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffce1-244">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-245">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffce1-245">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffce1-246">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-246">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-247">otherIpPhone の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-247">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="ffce1-248">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-248">Write displayName</span></span></p>
<p><span data-ttu-id="ffce1-249">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-249">Write description</span></span></p>
<p><span data-ttu-id="ffce1-250">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-250">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="ffce1-251">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-251">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="ffce1-252">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-252">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-253">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-253">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-254">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-254">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ffce1-255">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffce1-255">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="ffce1-256">InetOrgPerson オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="ffce1-256">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="ffce1-257">OU 上の InetOrgPerson オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ffce1-257">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="ffce1-258">InetOrgPerson オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffce1-258">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffce1-259">グループ</span><span class="sxs-lookup"><span data-stu-id="ffce1-259">Group</span></span></th>
<th><span data-ttu-id="ffce1-260">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffce1-260">Permission</span></span></th>
<th><span data-ttu-id="ffce1-261">適用対象</span><span class="sxs-lookup"><span data-stu-id="ffce1-261">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-262">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffce1-262">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffce1-263">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="ffce1-263">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffce1-264">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-264">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffce1-265">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-265">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-266">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="ffce1-266">List contents</span></span></p>
<p><span data-ttu-id="ffce1-267">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-267">Read all properties</span></span></p>
<p><span data-ttu-id="ffce1-268">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-268">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-269">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-269">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-270">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-270">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-271">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="ffce1-271">List contents</span></span></p>
<p><span data-ttu-id="ffce1-272">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-272">Read all properties</span></span></p>
<p><span data-ttu-id="ffce1-273">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-273">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-274">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffce1-274">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffce1-275">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffce1-275">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffce1-276">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-276">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-277">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-277">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-278">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-278">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-279">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-279">Read Personal-Information</span></span></p>
<p><span data-ttu-id="ffce1-280">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-280">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffce1-281">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-281">Read General-Information</span></span></p>
<p><span data-ttu-id="ffce1-282">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="ffce1-282">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ffce1-283">子 inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffce1-283">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffce1-284">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffce1-284">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffce1-285">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-285">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-286">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-286">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-287">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-287">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffce1-288">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffce1-288">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ffce1-289">子 inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffce1-289">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

