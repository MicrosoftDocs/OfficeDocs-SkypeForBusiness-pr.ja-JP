---
title: 'Lync Server 2013: Grant-CsOUPermission によって加えられた変更'
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
ms.openlocfilehash: 0ff916c0b4e284f9c6ce4d5dbaf9c2e196ed4bc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529434"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="7ace1-102">Lync Server 2013 での Grant-CsOUPermission による変更</span><span class="sxs-lookup"><span data-stu-id="7ace1-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ace1-103">_**トピックの最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="7ace1-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="7ace1-104">Lync Server 2013 の管理を委任するには、指定された組織単位 (Ou) にアクセス許可を追加して、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが Domain Admins グループのメンバーにならずに Ou にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="7ace1-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="7ace1-105">**Grant-CsOuPermission** コマンドレットは、次の表で指定されているように、指定された OU 内のオブジェクトへのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="7ace1-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="7ace1-106">ユーザー オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="7ace1-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="7ace1-107">OU 上のユーザー オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="7ace1-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="7ace1-108">ユーザー オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="7ace1-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ace1-109">グループ</span><span class="sxs-lookup"><span data-stu-id="7ace1-109">Group</span></span></th>
<th><span data-ttu-id="7ace1-110">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7ace1-110">Permission</span></span></th>
<th><span data-ttu-id="7ace1-111">適用対象</span><span class="sxs-lookup"><span data-stu-id="7ace1-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7ace1-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7ace1-113">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="7ace1-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="7ace1-114">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ace1-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-116">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="7ace1-116">List contents</span></span></p>
<p><span data-ttu-id="7ace1-117">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-117">Read all properties</span></span></p>
<p><span data-ttu-id="7ace1-118">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-119">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-121">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="7ace1-121">List contents</span></span></p>
<p><span data-ttu-id="7ace1-122">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-122">Read all properties</span></span></p>
<p><span data-ttu-id="7ace1-123">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-124">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ace1-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-126">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-127">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-128">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-129">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="7ace1-130">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-130">Read General-Information</span></span></p>
<p><span data-ttu-id="7ace1-131">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-132">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7ace1-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7ace1-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7ace1-134">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-135">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="7ace1-136">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-137">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-138">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="7ace1-139">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7ace1-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="7ace1-140">コンピューター オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="7ace1-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="7ace1-141">OU 上のコンピューター オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="7ace1-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="7ace1-142">コンピューター オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="7ace1-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ace1-143">グループ</span><span class="sxs-lookup"><span data-stu-id="7ace1-143">Group</span></span></th>
<th><span data-ttu-id="7ace1-144">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7ace1-144">Permission</span></span></th>
<th><span data-ttu-id="7ace1-145">適用対象</span><span class="sxs-lookup"><span data-stu-id="7ace1-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7ace1-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7ace1-147">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="7ace1-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="7ace1-148">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ace1-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-150">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="7ace1-150">List contents</span></span></p>
<p><span data-ttu-id="7ace1-151">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-151">Read all properties</span></span></p>
<p><span data-ttu-id="7ace1-152">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-153">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-155">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="7ace1-155">List contents</span></span></p>
<p><span data-ttu-id="7ace1-156">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-156">Read all properties</span></span></p>
<p><span data-ttu-id="7ace1-157">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-158">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ace1-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-160">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="7ace1-161">Validated-DNS-Host-Name の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="7ace1-162">子のコンピューター オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7ace1-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7ace1-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7ace1-164">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="7ace1-165">Validated-DNS-Host-Name の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="7ace1-166">子のコンピューター オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7ace1-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="7ace1-167">連絡先または AppContact オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="7ace1-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="7ace1-168">OU 上の連絡先オブジェクトまたは AppContact オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="7ace1-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="7ace1-169">連絡先または AppContact オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="7ace1-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ace1-170">グループ</span><span class="sxs-lookup"><span data-stu-id="7ace1-170">Group</span></span></th>
<th><span data-ttu-id="7ace1-171">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7ace1-171">Permission</span></span></th>
<th><span data-ttu-id="7ace1-172">適用対象</span><span class="sxs-lookup"><span data-stu-id="7ace1-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7ace1-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7ace1-174">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="7ace1-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="7ace1-175">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ace1-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-177">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="7ace1-177">List contents</span></span></p>
<p><span data-ttu-id="7ace1-178">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-178">Read all properties</span></span></p>
<p><span data-ttu-id="7ace1-179">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-180">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-182">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="7ace1-182">List contents</span></span></p>
<p><span data-ttu-id="7ace1-183">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-183">Read all properties</span></span></p>
<p><span data-ttu-id="7ace1-184">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-185">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ace1-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-187">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-188">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-189">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-190">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="7ace1-191">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-191">Read General-Information</span></span></p>
<p><span data-ttu-id="7ace1-192">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="7ace1-193">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-194">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7ace1-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7ace1-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7ace1-196">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-197">otherIpPhone の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="7ace1-198">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-198">Write displayName</span></span></p>
<p><span data-ttu-id="7ace1-199">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-199">Write description</span></span></p>
<p><span data-ttu-id="7ace1-200">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="7ace1-201">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="7ace1-202">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-203">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-204">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="7ace1-205">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7ace1-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="7ace1-206">デバイス オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="7ace1-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="7ace1-207">OU 上のデバイス オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="7ace1-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="7ace1-208">デバイス オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="7ace1-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ace1-209">グループ</span><span class="sxs-lookup"><span data-stu-id="7ace1-209">Group</span></span></th>
<th><span data-ttu-id="7ace1-210">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7ace1-210">Permission</span></span></th>
<th><span data-ttu-id="7ace1-211">適用対象</span><span class="sxs-lookup"><span data-stu-id="7ace1-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7ace1-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7ace1-213">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="7ace1-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="7ace1-214">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ace1-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-216">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="7ace1-216">List contents</span></span></p>
<p><span data-ttu-id="7ace1-217">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-217">Read all properties</span></span></p>
<p><span data-ttu-id="7ace1-218">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-219">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-221">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="7ace1-221">List contents</span></span></p>
<p><span data-ttu-id="7ace1-222">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-222">Read all properties</span></span></p>
<p><span data-ttu-id="7ace1-223">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-224">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ace1-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-226">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-227">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-228">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-229">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="7ace1-230">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="7ace1-231">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-231">Read General-Information</span></span></p>
<p><span data-ttu-id="7ace1-232">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-233">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7ace1-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7ace1-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7ace1-235">子の作成</span><span class="sxs-lookup"><span data-stu-id="7ace1-235">Create child</span></span></p>
<p><span data-ttu-id="7ace1-236">子の削除</span><span class="sxs-lookup"><span data-stu-id="7ace1-236">Delete child</span></span></p>
<p><span data-ttu-id="7ace1-237">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="7ace1-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="7ace1-238">Contact</span><span class="sxs-lookup"><span data-stu-id="7ace1-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ace1-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7ace1-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7ace1-240">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-240">Write displayName</span></span></p>
<p><span data-ttu-id="7ace1-241">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-241">Write description</span></span></p>
<p><span data-ttu-id="7ace1-242">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="7ace1-243">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7ace1-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7ace1-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7ace1-245">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-246">otherIpPhone の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="7ace1-247">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-247">Write displayName</span></span></p>
<p><span data-ttu-id="7ace1-248">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-248">Write description</span></span></p>
<p><span data-ttu-id="7ace1-249">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="7ace1-250">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="7ace1-251">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-252">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-253">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="7ace1-254">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7ace1-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="7ace1-255">InetOrgPerson オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="7ace1-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="7ace1-256">OU 上の InetOrgPerson オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="7ace1-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="7ace1-257">InetOrgPerson オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="7ace1-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ace1-258">グループ</span><span class="sxs-lookup"><span data-stu-id="7ace1-258">Group</span></span></th>
<th><span data-ttu-id="7ace1-259">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7ace1-259">Permission</span></span></th>
<th><span data-ttu-id="7ace1-260">適用対象</span><span class="sxs-lookup"><span data-stu-id="7ace1-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7ace1-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7ace1-262">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="7ace1-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="7ace1-263">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ace1-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-265">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="7ace1-265">List contents</span></span></p>
<p><span data-ttu-id="7ace1-266">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-266">Read all properties</span></span></p>
<p><span data-ttu-id="7ace1-267">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-268">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-270">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="7ace1-270">List contents</span></span></p>
<p><span data-ttu-id="7ace1-271">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-271">Read all properties</span></span></p>
<p><span data-ttu-id="7ace1-272">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-273">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="7ace1-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ace1-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7ace1-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7ace1-275">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-276">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-277">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-278">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="7ace1-279">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="7ace1-280">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-280">Read General-Information</span></span></p>
<p><span data-ttu-id="7ace1-281">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="7ace1-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="7ace1-282">子 inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7ace1-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ace1-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7ace1-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7ace1-284">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-285">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-286">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="7ace1-287">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="7ace1-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="7ace1-288">子 inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7ace1-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

