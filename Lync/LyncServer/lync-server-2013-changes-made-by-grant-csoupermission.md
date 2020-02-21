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
ms.openlocfilehash: 6143310797c7372a30665cd380d7fb07340ebaf9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="9e6be-102">Lync Server 2013 での付与-CsOUPermission による変更</span><span class="sxs-lookup"><span data-stu-id="9e6be-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e6be-103">_**トピックの最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="9e6be-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="9e6be-104">Lync Server 2013 の管理を委任するには、指定された組織単位 (Ou) にアクセス許可を追加して、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが Domain Admins グループのメンバーにならずに Ou にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="9e6be-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="9e6be-105">**Grant-CsOuPermission** コマンドレットは、次の表で指定されているように、指定された OU 内のオブジェクトへのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="9e6be-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="9e6be-106">ユーザー オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="9e6be-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="9e6be-107">OU 上のユーザー オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="9e6be-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="9e6be-108">ユーザー オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9e6be-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e6be-109">Group</span><span class="sxs-lookup"><span data-stu-id="9e6be-109">Group</span></span></th>
<th><span data-ttu-id="9e6be-110">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9e6be-110">Permission</span></span></th>
<th><span data-ttu-id="9e6be-111">適用対象</span><span class="sxs-lookup"><span data-stu-id="9e6be-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9e6be-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9e6be-113">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="9e6be-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9e6be-114">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e6be-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-116">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="9e6be-116">List contents</span></span></p>
<p><span data-ttu-id="9e6be-117">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-117">Read all properties</span></span></p>
<p><span data-ttu-id="9e6be-118">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-119">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-121">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="9e6be-121">List contents</span></span></p>
<p><span data-ttu-id="9e6be-122">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-122">Read all properties</span></span></p>
<p><span data-ttu-id="9e6be-123">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-124">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e6be-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-126">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-127">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-128">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-129">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="9e6be-130">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-130">Read General-Information</span></span></p>
<p><span data-ttu-id="9e6be-131">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-132">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9e6be-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9e6be-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9e6be-134">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-135">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="9e6be-136">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-137">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-138">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="9e6be-139">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9e6be-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="9e6be-140">コンピューター オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="9e6be-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="9e6be-141">OU 上のコンピューター オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="9e6be-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="9e6be-142">コンピューター オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9e6be-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e6be-143">Group</span><span class="sxs-lookup"><span data-stu-id="9e6be-143">Group</span></span></th>
<th><span data-ttu-id="9e6be-144">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9e6be-144">Permission</span></span></th>
<th><span data-ttu-id="9e6be-145">適用対象</span><span class="sxs-lookup"><span data-stu-id="9e6be-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9e6be-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9e6be-147">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="9e6be-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9e6be-148">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e6be-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-150">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="9e6be-150">List contents</span></span></p>
<p><span data-ttu-id="9e6be-151">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-151">Read all properties</span></span></p>
<p><span data-ttu-id="9e6be-152">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-153">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-155">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="9e6be-155">List contents</span></span></p>
<p><span data-ttu-id="9e6be-156">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-156">Read all properties</span></span></p>
<p><span data-ttu-id="9e6be-157">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-158">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e6be-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-160">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="9e6be-161">Validated-DNS-Host-Name の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="9e6be-162">子のコンピューター オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9e6be-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9e6be-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9e6be-164">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="9e6be-165">Validated-DNS-Host-Name の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="9e6be-166">子のコンピューター オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9e6be-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="9e6be-167">連絡先または AppContact オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="9e6be-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="9e6be-168">OU 上の連絡先オブジェクトまたは AppContact オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="9e6be-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="9e6be-169">連絡先または AppContact オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9e6be-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e6be-170">Group</span><span class="sxs-lookup"><span data-stu-id="9e6be-170">Group</span></span></th>
<th><span data-ttu-id="9e6be-171">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9e6be-171">Permission</span></span></th>
<th><span data-ttu-id="9e6be-172">適用対象</span><span class="sxs-lookup"><span data-stu-id="9e6be-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9e6be-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9e6be-174">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="9e6be-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9e6be-175">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e6be-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-177">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="9e6be-177">List contents</span></span></p>
<p><span data-ttu-id="9e6be-178">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-178">Read all properties</span></span></p>
<p><span data-ttu-id="9e6be-179">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-180">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-182">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="9e6be-182">List contents</span></span></p>
<p><span data-ttu-id="9e6be-183">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-183">Read all properties</span></span></p>
<p><span data-ttu-id="9e6be-184">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-185">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e6be-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-187">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-188">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-189">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-190">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="9e6be-191">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-191">Read General-Information</span></span></p>
<p><span data-ttu-id="9e6be-192">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="9e6be-193">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-194">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9e6be-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9e6be-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9e6be-196">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-197">otherIpPhone の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="9e6be-198">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-198">Write displayName</span></span></p>
<p><span data-ttu-id="9e6be-199">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-199">Write description</span></span></p>
<p><span data-ttu-id="9e6be-200">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="9e6be-201">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="9e6be-202">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-203">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-204">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="9e6be-205">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9e6be-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="9e6be-206">デバイス オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="9e6be-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="9e6be-207">OU 上のデバイス オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="9e6be-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="9e6be-208">デバイス オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9e6be-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e6be-209">Group</span><span class="sxs-lookup"><span data-stu-id="9e6be-209">Group</span></span></th>
<th><span data-ttu-id="9e6be-210">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9e6be-210">Permission</span></span></th>
<th><span data-ttu-id="9e6be-211">適用対象</span><span class="sxs-lookup"><span data-stu-id="9e6be-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9e6be-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9e6be-213">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="9e6be-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9e6be-214">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e6be-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-216">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="9e6be-216">List contents</span></span></p>
<p><span data-ttu-id="9e6be-217">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-217">Read all properties</span></span></p>
<p><span data-ttu-id="9e6be-218">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-219">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-221">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="9e6be-221">List contents</span></span></p>
<p><span data-ttu-id="9e6be-222">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-222">Read all properties</span></span></p>
<p><span data-ttu-id="9e6be-223">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-224">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e6be-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-226">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-227">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-228">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-229">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="9e6be-230">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="9e6be-231">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-231">Read General-Information</span></span></p>
<p><span data-ttu-id="9e6be-232">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-233">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9e6be-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9e6be-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9e6be-235">子の作成</span><span class="sxs-lookup"><span data-stu-id="9e6be-235">Create child</span></span></p>
<p><span data-ttu-id="9e6be-236">子の削除</span><span class="sxs-lookup"><span data-stu-id="9e6be-236">Delete child</span></span></p>
<p><span data-ttu-id="9e6be-237">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="9e6be-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="9e6be-238">連絡先</span><span class="sxs-lookup"><span data-stu-id="9e6be-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e6be-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9e6be-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9e6be-240">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-240">Write displayName</span></span></p>
<p><span data-ttu-id="9e6be-241">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-241">Write description</span></span></p>
<p><span data-ttu-id="9e6be-242">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="9e6be-243">子ユーザー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9e6be-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9e6be-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9e6be-245">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-246">otherIpPhone の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="9e6be-247">displayName の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-247">Write displayName</span></span></p>
<p><span data-ttu-id="9e6be-248">description の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-248">Write description</span></span></p>
<p><span data-ttu-id="9e6be-249">telephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="9e6be-250">msExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="9e6be-251">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-252">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-253">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="9e6be-254">子連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9e6be-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="9e6be-255">InetOrgPerson オブジェクトに対するアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="9e6be-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="9e6be-256">OU 上の InetOrgPerson オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="9e6be-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="9e6be-257">InetOrgPerson オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9e6be-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e6be-258">Group</span><span class="sxs-lookup"><span data-stu-id="9e6be-258">Group</span></span></th>
<th><span data-ttu-id="9e6be-259">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9e6be-259">Permission</span></span></th>
<th><span data-ttu-id="9e6be-260">適用対象</span><span class="sxs-lookup"><span data-stu-id="9e6be-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9e6be-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9e6be-262">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="9e6be-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9e6be-263">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e6be-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-265">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="9e6be-265">List contents</span></span></p>
<p><span data-ttu-id="9e6be-266">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-266">Read all properties</span></span></p>
<p><span data-ttu-id="9e6be-267">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-268">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-270">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="9e6be-270">List contents</span></span></p>
<p><span data-ttu-id="9e6be-271">すべてのプロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-271">Read all properties</span></span></p>
<p><span data-ttu-id="9e6be-272">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-273">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="9e6be-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e6be-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9e6be-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9e6be-275">RTCUserSearchPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-276">RTCUserProvisioningPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-277">RTCPropertySet の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-278">Personal-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="9e6be-279">Public-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="9e6be-280">General-Information の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-280">Read General-Information</span></span></p>
<p><span data-ttu-id="9e6be-281">User-Account-Restrictions の読み取り</span><span class="sxs-lookup"><span data-stu-id="9e6be-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9e6be-282">子 inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9e6be-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e6be-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9e6be-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9e6be-284">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-285">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-286">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="9e6be-287">proxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="9e6be-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="9e6be-288">子 inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9e6be-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

