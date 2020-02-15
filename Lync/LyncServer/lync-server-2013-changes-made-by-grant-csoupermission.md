---
title: 'Lync Server 2013: Grant-CsOUPermission によって行われた変更'
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
ms.openlocfilehash: dfad0cf4b8b863cd19d4d4113241477de1a50aaf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="52193-102">Lync Server 2013 での付与-CsOUPermission による変更</span><span class="sxs-lookup"><span data-stu-id="52193-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52193-103">_**トピックの最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="52193-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="52193-104">Lync Server 2013 の管理を委任するには、指定された組織単位 (Ou) にアクセス許可を追加して、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが Domain Admins グループのメンバーにならずに Ou にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="52193-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="52193-105">**Grant-CsOuPermission** コマンドレットは、次の表で指定されているように、指定された OU 内のオブジェクトへのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="52193-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="52193-106">ユーザー オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="52193-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="52193-107">OU 上のユーザー オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="52193-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="52193-108">ユーザー オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="52193-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52193-109">Group</span><span class="sxs-lookup"><span data-stu-id="52193-109">Group</span></span></th>
<th><span data-ttu-id="52193-110">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="52193-110">Permission</span></span></th>
<th><span data-ttu-id="52193-111">適用対象</span><span class="sxs-lookup"><span data-stu-id="52193-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52193-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="52193-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="52193-113">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="52193-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="52193-114">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52193-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-116">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="52193-116">List contents</span></span></p>
<p><span data-ttu-id="52193-117">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-117">Read all properties</span></span></p>
<p><span data-ttu-id="52193-118">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="52193-119">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52193-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-121">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="52193-121">List contents</span></span></p>
<p><span data-ttu-id="52193-122">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-122">Read all properties</span></span></p>
<p><span data-ttu-id="52193-123">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="52193-124">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52193-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-126">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="52193-127">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="52193-128">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="52193-129">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="52193-130">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-130">Read General-Information</span></span></p>
<p><span data-ttu-id="52193-131">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="52193-132">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="52193-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52193-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="52193-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="52193-134">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="52193-135">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="52193-136">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="52193-137">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="52193-138">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="52193-139">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="52193-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="52193-140">コンピューター オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="52193-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="52193-141">OU 上のコンピューター オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="52193-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="52193-142">コンピューター オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="52193-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52193-143">Group</span><span class="sxs-lookup"><span data-stu-id="52193-143">Group</span></span></th>
<th><span data-ttu-id="52193-144">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="52193-144">Permission</span></span></th>
<th><span data-ttu-id="52193-145">適用対象</span><span class="sxs-lookup"><span data-stu-id="52193-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52193-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="52193-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="52193-147">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="52193-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="52193-148">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52193-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-150">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="52193-150">List contents</span></span></p>
<p><span data-ttu-id="52193-151">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-151">Read all properties</span></span></p>
<p><span data-ttu-id="52193-152">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="52193-153">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52193-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-155">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="52193-155">List contents</span></span></p>
<p><span data-ttu-id="52193-156">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-156">Read all properties</span></span></p>
<p><span data-ttu-id="52193-157">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="52193-158">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52193-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-160">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="52193-161">Validated-DNS-Host-Name の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="52193-162">子のコンピューター オブジェクト</span><span class="sxs-lookup"><span data-stu-id="52193-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52193-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="52193-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="52193-164">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="52193-165">Validated-DNS-Host-Name の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="52193-166">子のコンピューター オブジェクト</span><span class="sxs-lookup"><span data-stu-id="52193-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="52193-167">連絡先または AppContact オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="52193-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="52193-168">OU 上の連絡先オブジェクトまたは AppContact オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="52193-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="52193-169">連絡先または AppContact オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="52193-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52193-170">Group</span><span class="sxs-lookup"><span data-stu-id="52193-170">Group</span></span></th>
<th><span data-ttu-id="52193-171">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="52193-171">Permission</span></span></th>
<th><span data-ttu-id="52193-172">適用対象</span><span class="sxs-lookup"><span data-stu-id="52193-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52193-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="52193-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="52193-174">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="52193-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="52193-175">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52193-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-177">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="52193-177">List contents</span></span></p>
<p><span data-ttu-id="52193-178">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-178">Read all properties</span></span></p>
<p><span data-ttu-id="52193-179">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="52193-180">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52193-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-182">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="52193-182">List contents</span></span></p>
<p><span data-ttu-id="52193-183">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-183">Read all properties</span></span></p>
<p><span data-ttu-id="52193-184">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="52193-185">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52193-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-187">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="52193-188">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="52193-189">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="52193-190">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="52193-191">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-191">Read General-Information</span></span></p>
<p><span data-ttu-id="52193-192">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="52193-193">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="52193-194">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="52193-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52193-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="52193-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="52193-196">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="52193-197">otherIpPhone の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="52193-198">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-198">Write displayName</span></span></p>
<p><span data-ttu-id="52193-199">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-199">Write description</span></span></p>
<p><span data-ttu-id="52193-200">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="52193-201">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="52193-202">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="52193-203">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="52193-204">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="52193-205">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="52193-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="52193-206">デバイス オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="52193-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="52193-207">OU 上のデバイス オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="52193-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="52193-208">デバイス オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="52193-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52193-209">Group</span><span class="sxs-lookup"><span data-stu-id="52193-209">Group</span></span></th>
<th><span data-ttu-id="52193-210">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="52193-210">Permission</span></span></th>
<th><span data-ttu-id="52193-211">適用対象</span><span class="sxs-lookup"><span data-stu-id="52193-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52193-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="52193-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="52193-213">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="52193-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="52193-214">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52193-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-216">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="52193-216">List contents</span></span></p>
<p><span data-ttu-id="52193-217">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-217">Read all properties</span></span></p>
<p><span data-ttu-id="52193-218">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="52193-219">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52193-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-221">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="52193-221">List contents</span></span></p>
<p><span data-ttu-id="52193-222">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-222">Read all properties</span></span></p>
<p><span data-ttu-id="52193-223">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="52193-224">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52193-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-226">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="52193-227">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="52193-228">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="52193-229">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="52193-230">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="52193-231">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-231">Read General-Information</span></span></p>
<p><span data-ttu-id="52193-232">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="52193-233">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="52193-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52193-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="52193-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="52193-235">子の作成</span><span class="sxs-lookup"><span data-stu-id="52193-235">Create child</span></span></p>
<p><span data-ttu-id="52193-236">子の削除</span><span class="sxs-lookup"><span data-stu-id="52193-236">Delete child</span></span></p>
<p><span data-ttu-id="52193-237">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="52193-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="52193-238">連絡先</span><span class="sxs-lookup"><span data-stu-id="52193-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52193-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="52193-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="52193-240">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-240">Write displayName</span></span></p>
<p><span data-ttu-id="52193-241">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-241">Write description</span></span></p>
<p><span data-ttu-id="52193-242">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="52193-243">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="52193-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52193-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="52193-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="52193-245">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="52193-246">otherIpPhone の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="52193-247">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-247">Write displayName</span></span></p>
<p><span data-ttu-id="52193-248">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-248">Write description</span></span></p>
<p><span data-ttu-id="52193-249">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="52193-250">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="52193-251">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="52193-252">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="52193-253">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="52193-254">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="52193-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="52193-255">InetOrgPerson オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="52193-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="52193-256">OU 上の InetOrgPerson オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="52193-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="52193-257">InetOrgPerson オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="52193-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52193-258">Group</span><span class="sxs-lookup"><span data-stu-id="52193-258">Group</span></span></th>
<th><span data-ttu-id="52193-259">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="52193-259">Permission</span></span></th>
<th><span data-ttu-id="52193-260">適用対象</span><span class="sxs-lookup"><span data-stu-id="52193-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52193-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="52193-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="52193-262">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="52193-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="52193-263">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52193-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-265">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="52193-265">List contents</span></span></p>
<p><span data-ttu-id="52193-266">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-266">Read all properties</span></span></p>
<p><span data-ttu-id="52193-267">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="52193-268">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52193-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-270">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="52193-270">List contents</span></span></p>
<p><span data-ttu-id="52193-271">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-271">Read all properties</span></span></p>
<p><span data-ttu-id="52193-272">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="52193-273">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="52193-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52193-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52193-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52193-275">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="52193-276">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="52193-277">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="52193-278">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="52193-279">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="52193-280">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-280">Read General-Information</span></span></p>
<p><span data-ttu-id="52193-281">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="52193-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="52193-282">子 inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="52193-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52193-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="52193-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="52193-284">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="52193-285">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="52193-286">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="52193-287">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="52193-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="52193-288">子 inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="52193-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

