---
title: 'Lync Server 2013: アクセス許可によって行われた変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ce6b16dff48afeeec848024d763655695905008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="e8ef5-102">Lync Server 2013 のアクセス許可によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="e8ef5-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8ef5-103">_**最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="e8ef5-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="e8ef5-104">Lync Server 2013 管理を委任するために、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが、Domain Admins グループのメンバーにならずに Ou にアクセスできるように、指定された組織単位 (Ou) にアクセス許可を追加できます。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="e8ef5-105">**Grant-CsOuPermission**コマンドレットは、次の表に示すように、指定した OU 内のオブジェクトへのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="e8ef5-106">ユーザーオブジェクトのアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="e8ef5-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="e8ef5-107">OU 上のユーザーオブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="e8ef5-108">ユーザーオブジェクトに付与される権限</span><span class="sxs-lookup"><span data-stu-id="e8ef5-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8ef5-109">化</span><span class="sxs-lookup"><span data-stu-id="e8ef5-109">Group</span></span></th>
<th><span data-ttu-id="e8ef5-110">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-110">Permission</span></span></th>
<th><span data-ttu-id="e8ef5-111">適用対象</span><span class="sxs-lookup"><span data-stu-id="e8ef5-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e8ef5-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-113">ディレクトリの変更の複製</span><span class="sxs-lookup"><span data-stu-id="e8ef5-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-114">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8ef5-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-116">リストの内容</span><span class="sxs-lookup"><span data-stu-id="e8ef5-116">List contents</span></span></p>
<p><span data-ttu-id="e8ef5-117">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="e8ef5-117">Read all properties</span></span></p>
<p><span data-ttu-id="e8ef5-118">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-119">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-121">リストの内容</span><span class="sxs-lookup"><span data-stu-id="e8ef5-121">List contents</span></span></p>
<p><span data-ttu-id="e8ef5-122">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="e8ef5-122">Read all properties</span></span></p>
<p><span data-ttu-id="e8ef5-123">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-124">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8ef5-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-126">RTCUserSearchPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-127">RTCUserProvisioningPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-128">RTCPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-129">公開-情報を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="e8ef5-130">一般的な情報を読む-情報</span><span class="sxs-lookup"><span data-stu-id="e8ef5-130">Read General-Information</span></span></p>
<p><span data-ttu-id="e8ef5-131">ユーザーアカウントの制限を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-132">子孫のユーザーオブジェクト</span><span class="sxs-lookup"><span data-stu-id="e8ef5-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e8ef5-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-134">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-135">MsExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="e8ef5-136">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-137">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-138">ProxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-139">子孫のユーザーオブジェクト</span><span class="sxs-lookup"><span data-stu-id="e8ef5-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="e8ef5-140">コンピューターオブジェクトへのアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="e8ef5-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="e8ef5-141">OU 上のコンピューターオブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="e8ef5-142">コンピューターオブジェクトに付与される権限</span><span class="sxs-lookup"><span data-stu-id="e8ef5-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8ef5-143">化</span><span class="sxs-lookup"><span data-stu-id="e8ef5-143">Group</span></span></th>
<th><span data-ttu-id="e8ef5-144">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-144">Permission</span></span></th>
<th><span data-ttu-id="e8ef5-145">適用対象</span><span class="sxs-lookup"><span data-stu-id="e8ef5-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e8ef5-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-147">ディレクトリの変更の複製</span><span class="sxs-lookup"><span data-stu-id="e8ef5-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-148">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8ef5-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-150">リストの内容</span><span class="sxs-lookup"><span data-stu-id="e8ef5-150">List contents</span></span></p>
<p><span data-ttu-id="e8ef5-151">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="e8ef5-151">Read all properties</span></span></p>
<p><span data-ttu-id="e8ef5-152">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-153">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-155">リストの内容</span><span class="sxs-lookup"><span data-stu-id="e8ef5-155">List contents</span></span></p>
<p><span data-ttu-id="e8ef5-156">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="e8ef5-156">Read all properties</span></span></p>
<p><span data-ttu-id="e8ef5-157">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-158">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8ef5-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-160">公開-情報を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="e8ef5-161">読み取り済みの DNS ホスト名</span><span class="sxs-lookup"><span data-stu-id="e8ef5-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-162">子コンピューターオブジェクト</span><span class="sxs-lookup"><span data-stu-id="e8ef5-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e8ef5-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-164">公開-情報を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="e8ef5-165">読み取り済みの DNS ホスト名</span><span class="sxs-lookup"><span data-stu-id="e8ef5-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-166">子コンピューターオブジェクト</span><span class="sxs-lookup"><span data-stu-id="e8ef5-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="e8ef5-167">Contact オブジェクトまたは AppContact オブジェクトのアクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="e8ef5-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="e8ef5-168">組織内の連絡先オブジェクトまたは AppContact オブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="e8ef5-169">Contact オブジェクトまたは AppContact オブジェクトに付与されているアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8ef5-170">化</span><span class="sxs-lookup"><span data-stu-id="e8ef5-170">Group</span></span></th>
<th><span data-ttu-id="e8ef5-171">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-171">Permission</span></span></th>
<th><span data-ttu-id="e8ef5-172">適用対象</span><span class="sxs-lookup"><span data-stu-id="e8ef5-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e8ef5-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-174">ディレクトリの変更の複製</span><span class="sxs-lookup"><span data-stu-id="e8ef5-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-175">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8ef5-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-177">リストの内容</span><span class="sxs-lookup"><span data-stu-id="e8ef5-177">List contents</span></span></p>
<p><span data-ttu-id="e8ef5-178">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="e8ef5-178">Read all properties</span></span></p>
<p><span data-ttu-id="e8ef5-179">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-180">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-182">リストの内容</span><span class="sxs-lookup"><span data-stu-id="e8ef5-182">List contents</span></span></p>
<p><span data-ttu-id="e8ef5-183">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="e8ef5-183">Read all properties</span></span></p>
<p><span data-ttu-id="e8ef5-184">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-185">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8ef5-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-187">RTCUserSearchPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-188">RTCUserProvisioningPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-189">RTCPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-190">公開-情報を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="e8ef5-191">一般的な情報を読む-情報</span><span class="sxs-lookup"><span data-stu-id="e8ef5-191">Read General-Information</span></span></p>
<p><span data-ttu-id="e8ef5-192">個人情報を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="e8ef5-193">ユーザーアカウントの制限を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-194">子孫の連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e8ef5-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e8ef5-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-196">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-197">他の Ip電話を書く</span><span class="sxs-lookup"><span data-stu-id="e8ef5-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="e8ef5-198">DisplayName を書く</span><span class="sxs-lookup"><span data-stu-id="e8ef5-198">Write displayName</span></span></p>
<p><span data-ttu-id="e8ef5-199">説明の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-199">Write description</span></span></p>
<p><span data-ttu-id="e8ef5-200">TelephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="e8ef5-201">MsExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="e8ef5-202">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-203">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-204">ProxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-205">子孫の連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e8ef5-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="e8ef5-206">デバイスオブジェクトのアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="e8ef5-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="e8ef5-207">OU 上のデバイスオブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="e8ef5-208">デバイスオブジェクトに付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8ef5-209">化</span><span class="sxs-lookup"><span data-stu-id="e8ef5-209">Group</span></span></th>
<th><span data-ttu-id="e8ef5-210">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-210">Permission</span></span></th>
<th><span data-ttu-id="e8ef5-211">適用対象</span><span class="sxs-lookup"><span data-stu-id="e8ef5-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e8ef5-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-213">ディレクトリの変更の複製</span><span class="sxs-lookup"><span data-stu-id="e8ef5-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-214">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8ef5-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-216">リストの内容</span><span class="sxs-lookup"><span data-stu-id="e8ef5-216">List contents</span></span></p>
<p><span data-ttu-id="e8ef5-217">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="e8ef5-217">Read all properties</span></span></p>
<p><span data-ttu-id="e8ef5-218">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-219">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-221">リストの内容</span><span class="sxs-lookup"><span data-stu-id="e8ef5-221">List contents</span></span></p>
<p><span data-ttu-id="e8ef5-222">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="e8ef5-222">Read all properties</span></span></p>
<p><span data-ttu-id="e8ef5-223">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-224">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8ef5-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-226">RTCUserSearchPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-227">RTCUserProvisioningPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-228">RTCPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-229">公開-情報を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="e8ef5-230">個人情報を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="e8ef5-231">一般的な情報を読む-情報</span><span class="sxs-lookup"><span data-stu-id="e8ef5-231">Read General-Information</span></span></p>
<p><span data-ttu-id="e8ef5-232">ユーザーアカウントの制限を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-233">子孫の連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e8ef5-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e8ef5-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-235">子の作成</span><span class="sxs-lookup"><span data-stu-id="e8ef5-235">Create child</span></span></p>
<p><span data-ttu-id="e8ef5-236">子の削除</span><span class="sxs-lookup"><span data-stu-id="e8ef5-236">Delete child</span></span></p>
<p><span data-ttu-id="e8ef5-237">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="e8ef5-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-238">問い合わせ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8ef5-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e8ef5-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-240">DisplayName を書く</span><span class="sxs-lookup"><span data-stu-id="e8ef5-240">Write displayName</span></span></p>
<p><span data-ttu-id="e8ef5-241">説明の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-241">Write description</span></span></p>
<p><span data-ttu-id="e8ef5-242">TelephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-243">子孫のユーザーオブジェクト</span><span class="sxs-lookup"><span data-stu-id="e8ef5-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e8ef5-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-245">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-246">他の Ip電話を書く</span><span class="sxs-lookup"><span data-stu-id="e8ef5-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="e8ef5-247">DisplayName を書く</span><span class="sxs-lookup"><span data-stu-id="e8ef5-247">Write displayName</span></span></p>
<p><span data-ttu-id="e8ef5-248">説明の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-248">Write description</span></span></p>
<p><span data-ttu-id="e8ef5-249">TelephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="e8ef5-250">MsExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="e8ef5-251">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-252">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-253">ProxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-254">子孫の連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e8ef5-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="e8ef5-255">InetOrgPerson オブジェクトのアクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="e8ef5-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="e8ef5-256">OU 上の InetOrgPerson オブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="e8ef5-257">InetOrgPerson オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8ef5-258">化</span><span class="sxs-lookup"><span data-stu-id="e8ef5-258">Group</span></span></th>
<th><span data-ttu-id="e8ef5-259">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-259">Permission</span></span></th>
<th><span data-ttu-id="e8ef5-260">適用対象</span><span class="sxs-lookup"><span data-stu-id="e8ef5-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e8ef5-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-262">ディレクトリの変更の複製</span><span class="sxs-lookup"><span data-stu-id="e8ef5-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-263">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8ef5-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-265">リストの内容</span><span class="sxs-lookup"><span data-stu-id="e8ef5-265">List contents</span></span></p>
<p><span data-ttu-id="e8ef5-266">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="e8ef5-266">Read all properties</span></span></p>
<p><span data-ttu-id="e8ef5-267">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-268">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-270">リストの内容</span><span class="sxs-lookup"><span data-stu-id="e8ef5-270">List contents</span></span></p>
<p><span data-ttu-id="e8ef5-271">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="e8ef5-271">Read all properties</span></span></p>
<p><span data-ttu-id="e8ef5-272">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e8ef5-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-273">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="e8ef5-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8ef5-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e8ef5-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-275">RTCUserSearchPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-276">RTCUserProvisioningPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-277">RTCPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-278">個人情報を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="e8ef5-279">公開-情報を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="e8ef5-280">一般的な情報を読む-情報</span><span class="sxs-lookup"><span data-stu-id="e8ef5-280">Read General-Information</span></span></p>
<p><span data-ttu-id="e8ef5-281">ユーザーアカウントの制限を読む</span><span class="sxs-lookup"><span data-stu-id="e8ef5-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-282">子の inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e8ef5-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8ef5-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e8ef5-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-284">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-285">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-286">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="e8ef5-287">ProxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="e8ef5-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e8ef5-288">子の inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e8ef5-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

