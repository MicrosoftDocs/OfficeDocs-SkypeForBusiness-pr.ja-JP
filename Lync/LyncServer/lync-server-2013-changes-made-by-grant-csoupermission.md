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
ms.openlocfilehash: c64c11ba999763a44105a68502e53fc4889af305
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="eb5ab-102">Lync Server 2013 での付与-CsOUPermission による変更</span><span class="sxs-lookup"><span data-stu-id="eb5ab-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb5ab-103">_**トピックの最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="eb5ab-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="eb5ab-104">Lync Server 2013 の管理を委任するには、指定された組織単位 (Ou) にアクセス許可を追加して、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが Domain Admins グループのメンバーにならずに Ou にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="eb5ab-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="eb5ab-105">**Grant-CsOuPermission** コマンドレットは、次の表で指定されているように、指定された OU 内のオブジェクトへのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="eb5ab-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="eb5ab-106">ユーザー オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="eb5ab-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="eb5ab-107">OU 上のユーザー オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="eb5ab-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="eb5ab-108">ユーザー オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb5ab-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb5ab-109">Group</span><span class="sxs-lookup"><span data-stu-id="eb5ab-109">Group</span></span></th>
<th><span data-ttu-id="eb5ab-110">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb5ab-110">Permission</span></span></th>
<th><span data-ttu-id="eb5ab-111">適用対象</span><span class="sxs-lookup"><span data-stu-id="eb5ab-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="eb5ab-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-113">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="eb5ab-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-114">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5ab-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-116">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="eb5ab-116">List contents</span></span></p>
<p><span data-ttu-id="eb5ab-117">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-117">Read all properties</span></span></p>
<p><span data-ttu-id="eb5ab-118">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-119">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-121">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="eb5ab-121">List contents</span></span></p>
<p><span data-ttu-id="eb5ab-122">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-122">Read all properties</span></span></p>
<p><span data-ttu-id="eb5ab-123">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-124">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5ab-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-126">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-127">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-128">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-129">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="eb5ab-130">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-130">Read General-Information</span></span></p>
<p><span data-ttu-id="eb5ab-131">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-132">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="eb5ab-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="eb5ab-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-134">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-135">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="eb5ab-136">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-137">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-138">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-139">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="eb5ab-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="eb5ab-140">コンピューター オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="eb5ab-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="eb5ab-141">OU 上のコンピューター オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="eb5ab-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="eb5ab-142">コンピューター オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb5ab-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb5ab-143">Group</span><span class="sxs-lookup"><span data-stu-id="eb5ab-143">Group</span></span></th>
<th><span data-ttu-id="eb5ab-144">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb5ab-144">Permission</span></span></th>
<th><span data-ttu-id="eb5ab-145">適用対象</span><span class="sxs-lookup"><span data-stu-id="eb5ab-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="eb5ab-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-147">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="eb5ab-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-148">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5ab-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-150">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="eb5ab-150">List contents</span></span></p>
<p><span data-ttu-id="eb5ab-151">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-151">Read all properties</span></span></p>
<p><span data-ttu-id="eb5ab-152">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-153">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-155">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="eb5ab-155">List contents</span></span></p>
<p><span data-ttu-id="eb5ab-156">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-156">Read all properties</span></span></p>
<p><span data-ttu-id="eb5ab-157">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-158">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5ab-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-160">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="eb5ab-161">Validated-DNS-Host-Name の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-162">子のコンピューター オブジェクト</span><span class="sxs-lookup"><span data-stu-id="eb5ab-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="eb5ab-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-164">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="eb5ab-165">Validated-DNS-Host-Name の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-166">子のコンピューター オブジェクト</span><span class="sxs-lookup"><span data-stu-id="eb5ab-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="eb5ab-167">連絡先または AppContact オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="eb5ab-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="eb5ab-168">OU 上の連絡先オブジェクトまたは AppContact オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="eb5ab-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="eb5ab-169">連絡先または AppContact オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb5ab-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb5ab-170">Group</span><span class="sxs-lookup"><span data-stu-id="eb5ab-170">Group</span></span></th>
<th><span data-ttu-id="eb5ab-171">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb5ab-171">Permission</span></span></th>
<th><span data-ttu-id="eb5ab-172">適用対象</span><span class="sxs-lookup"><span data-stu-id="eb5ab-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="eb5ab-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-174">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="eb5ab-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-175">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5ab-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-177">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="eb5ab-177">List contents</span></span></p>
<p><span data-ttu-id="eb5ab-178">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-178">Read all properties</span></span></p>
<p><span data-ttu-id="eb5ab-179">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-180">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-182">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="eb5ab-182">List contents</span></span></p>
<p><span data-ttu-id="eb5ab-183">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-183">Read all properties</span></span></p>
<p><span data-ttu-id="eb5ab-184">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-185">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5ab-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-187">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-188">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-189">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-190">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="eb5ab-191">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-191">Read General-Information</span></span></p>
<p><span data-ttu-id="eb5ab-192">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="eb5ab-193">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-194">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="eb5ab-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="eb5ab-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-196">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-197">otherIpPhone の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="eb5ab-198">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-198">Write displayName</span></span></p>
<p><span data-ttu-id="eb5ab-199">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-199">Write description</span></span></p>
<p><span data-ttu-id="eb5ab-200">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="eb5ab-201">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="eb5ab-202">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-203">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-204">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-205">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="eb5ab-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="eb5ab-206">デバイス オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="eb5ab-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="eb5ab-207">OU 上のデバイス オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="eb5ab-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="eb5ab-208">デバイス オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb5ab-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb5ab-209">Group</span><span class="sxs-lookup"><span data-stu-id="eb5ab-209">Group</span></span></th>
<th><span data-ttu-id="eb5ab-210">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb5ab-210">Permission</span></span></th>
<th><span data-ttu-id="eb5ab-211">適用対象</span><span class="sxs-lookup"><span data-stu-id="eb5ab-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="eb5ab-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-213">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="eb5ab-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-214">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5ab-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-216">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="eb5ab-216">List contents</span></span></p>
<p><span data-ttu-id="eb5ab-217">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-217">Read all properties</span></span></p>
<p><span data-ttu-id="eb5ab-218">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-219">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-221">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="eb5ab-221">List contents</span></span></p>
<p><span data-ttu-id="eb5ab-222">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-222">Read all properties</span></span></p>
<p><span data-ttu-id="eb5ab-223">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-224">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5ab-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-226">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-227">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-228">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-229">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="eb5ab-230">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="eb5ab-231">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-231">Read General-Information</span></span></p>
<p><span data-ttu-id="eb5ab-232">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-233">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="eb5ab-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="eb5ab-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-235">子の作成</span><span class="sxs-lookup"><span data-stu-id="eb5ab-235">Create child</span></span></p>
<p><span data-ttu-id="eb5ab-236">子の削除</span><span class="sxs-lookup"><span data-stu-id="eb5ab-236">Delete child</span></span></p>
<p><span data-ttu-id="eb5ab-237">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="eb5ab-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-238">連絡先</span><span class="sxs-lookup"><span data-stu-id="eb5ab-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5ab-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="eb5ab-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-240">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-240">Write displayName</span></span></p>
<p><span data-ttu-id="eb5ab-241">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-241">Write description</span></span></p>
<p><span data-ttu-id="eb5ab-242">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-243">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="eb5ab-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="eb5ab-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-245">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-246">otherIpPhone の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="eb5ab-247">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-247">Write displayName</span></span></p>
<p><span data-ttu-id="eb5ab-248">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-248">Write description</span></span></p>
<p><span data-ttu-id="eb5ab-249">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="eb5ab-250">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="eb5ab-251">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-252">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-253">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-254">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="eb5ab-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="eb5ab-255">InetOrgPerson オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="eb5ab-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="eb5ab-256">OU 上の InetOrgPerson オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="eb5ab-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="eb5ab-257">InetOrgPerson オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb5ab-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb5ab-258">Group</span><span class="sxs-lookup"><span data-stu-id="eb5ab-258">Group</span></span></th>
<th><span data-ttu-id="eb5ab-259">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb5ab-259">Permission</span></span></th>
<th><span data-ttu-id="eb5ab-260">適用対象</span><span class="sxs-lookup"><span data-stu-id="eb5ab-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="eb5ab-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-262">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="eb5ab-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-263">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5ab-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-265">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="eb5ab-265">List contents</span></span></p>
<p><span data-ttu-id="eb5ab-266">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-266">Read all properties</span></span></p>
<p><span data-ttu-id="eb5ab-267">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-268">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-270">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="eb5ab-270">List contents</span></span></p>
<p><span data-ttu-id="eb5ab-271">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-271">Read all properties</span></span></p>
<p><span data-ttu-id="eb5ab-272">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-273">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="eb5ab-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5ab-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="eb5ab-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-275">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-276">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-277">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-278">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="eb5ab-279">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="eb5ab-280">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-280">Read General-Information</span></span></p>
<p><span data-ttu-id="eb5ab-281">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="eb5ab-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-282">子 inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="eb5ab-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5ab-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="eb5ab-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-284">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-285">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-286">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="eb5ab-287">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="eb5ab-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="eb5ab-288">子 inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="eb5ab-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

