---
title: 'Lync Server 2013: アクセス許可によって行われた変更'
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
ms.openlocfilehash: 9056753e57f57b131a05d13eb2862611ba34f966
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="ffc8d-102">Lync Server 2013 のアクセス許可によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="ffc8d-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffc8d-103">_**最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="ffc8d-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="ffc8d-104">Lync Server 2013 管理を委任するために、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが、Domain Admins グループのメンバーにならずに Ou にアクセスできるように、指定された組織単位 (Ou) にアクセス許可を追加できます。</span><span class="sxs-lookup"><span data-stu-id="ffc8d-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="ffc8d-105">**Grant-CsOuPermission**コマンドレットは、次の表に示すように、指定した OU 内のオブジェクトへのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="ffc8d-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="ffc8d-106">ユーザーオブジェクトのアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="ffc8d-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="ffc8d-107">OU 上のユーザーオブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ffc8d-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="ffc8d-108">ユーザーオブジェクトに付与される権限</span><span class="sxs-lookup"><span data-stu-id="ffc8d-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffc8d-109">化</span><span class="sxs-lookup"><span data-stu-id="ffc8d-109">Group</span></span></th>
<th><span data-ttu-id="ffc8d-110">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-110">Permission</span></span></th>
<th><span data-ttu-id="ffc8d-111">適用対象</span><span class="sxs-lookup"><span data-stu-id="ffc8d-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffc8d-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-113">ディレクトリの変更の複製</span><span class="sxs-lookup"><span data-stu-id="ffc8d-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-114">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc8d-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-116">リストの内容</span><span class="sxs-lookup"><span data-stu-id="ffc8d-116">List contents</span></span></p>
<p><span data-ttu-id="ffc8d-117">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="ffc8d-117">Read all properties</span></span></p>
<p><span data-ttu-id="ffc8d-118">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-119">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-121">リストの内容</span><span class="sxs-lookup"><span data-stu-id="ffc8d-121">List contents</span></span></p>
<p><span data-ttu-id="ffc8d-122">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="ffc8d-122">Read all properties</span></span></p>
<p><span data-ttu-id="ffc8d-123">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-124">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc8d-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-126">RTCUserSearchPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-127">RTCUserProvisioningPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-128">RTCPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-129">公開-情報を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffc8d-130">一般的な情報を読む-情報</span><span class="sxs-lookup"><span data-stu-id="ffc8d-130">Read General-Information</span></span></p>
<p><span data-ttu-id="ffc8d-131">ユーザーアカウントの制限を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-132">子孫のユーザーオブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffc8d-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffc8d-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-134">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-135">MsExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="ffc8d-136">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-137">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-138">ProxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-139">子孫のユーザーオブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffc8d-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="ffc8d-140">コンピューターオブジェクトへのアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="ffc8d-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="ffc8d-141">OU 上のコンピューターオブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ffc8d-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="ffc8d-142">コンピューターオブジェクトに付与される権限</span><span class="sxs-lookup"><span data-stu-id="ffc8d-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffc8d-143">化</span><span class="sxs-lookup"><span data-stu-id="ffc8d-143">Group</span></span></th>
<th><span data-ttu-id="ffc8d-144">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-144">Permission</span></span></th>
<th><span data-ttu-id="ffc8d-145">適用対象</span><span class="sxs-lookup"><span data-stu-id="ffc8d-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffc8d-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-147">ディレクトリの変更の複製</span><span class="sxs-lookup"><span data-stu-id="ffc8d-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-148">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc8d-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-150">リストの内容</span><span class="sxs-lookup"><span data-stu-id="ffc8d-150">List contents</span></span></p>
<p><span data-ttu-id="ffc8d-151">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="ffc8d-151">Read all properties</span></span></p>
<p><span data-ttu-id="ffc8d-152">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-153">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-155">リストの内容</span><span class="sxs-lookup"><span data-stu-id="ffc8d-155">List contents</span></span></p>
<p><span data-ttu-id="ffc8d-156">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="ffc8d-156">Read all properties</span></span></p>
<p><span data-ttu-id="ffc8d-157">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-158">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc8d-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-160">公開-情報を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffc8d-161">読み取り済みの DNS ホスト名</span><span class="sxs-lookup"><span data-stu-id="ffc8d-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-162">子コンピューターオブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffc8d-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffc8d-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-164">公開-情報を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffc8d-165">読み取り済みの DNS ホスト名</span><span class="sxs-lookup"><span data-stu-id="ffc8d-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-166">子コンピューターオブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffc8d-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="ffc8d-167">Contact オブジェクトまたは AppContact オブジェクトのアクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="ffc8d-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="ffc8d-168">組織内の連絡先オブジェクトまたは AppContact オブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ffc8d-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="ffc8d-169">Contact オブジェクトまたは AppContact オブジェクトに付与されているアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffc8d-170">化</span><span class="sxs-lookup"><span data-stu-id="ffc8d-170">Group</span></span></th>
<th><span data-ttu-id="ffc8d-171">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-171">Permission</span></span></th>
<th><span data-ttu-id="ffc8d-172">適用対象</span><span class="sxs-lookup"><span data-stu-id="ffc8d-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffc8d-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-174">ディレクトリの変更の複製</span><span class="sxs-lookup"><span data-stu-id="ffc8d-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-175">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc8d-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-177">リストの内容</span><span class="sxs-lookup"><span data-stu-id="ffc8d-177">List contents</span></span></p>
<p><span data-ttu-id="ffc8d-178">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="ffc8d-178">Read all properties</span></span></p>
<p><span data-ttu-id="ffc8d-179">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-180">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-182">リストの内容</span><span class="sxs-lookup"><span data-stu-id="ffc8d-182">List contents</span></span></p>
<p><span data-ttu-id="ffc8d-183">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="ffc8d-183">Read all properties</span></span></p>
<p><span data-ttu-id="ffc8d-184">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-185">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc8d-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-187">RTCUserSearchPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-188">RTCUserProvisioningPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-189">RTCPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-190">公開-情報を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffc8d-191">一般的な情報を読む-情報</span><span class="sxs-lookup"><span data-stu-id="ffc8d-191">Read General-Information</span></span></p>
<p><span data-ttu-id="ffc8d-192">個人情報を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="ffc8d-193">ユーザーアカウントの制限を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-194">子孫の連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffc8d-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffc8d-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-196">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-197">他の Ip電話を書く</span><span class="sxs-lookup"><span data-stu-id="ffc8d-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="ffc8d-198">DisplayName を書く</span><span class="sxs-lookup"><span data-stu-id="ffc8d-198">Write displayName</span></span></p>
<p><span data-ttu-id="ffc8d-199">説明の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-199">Write description</span></span></p>
<p><span data-ttu-id="ffc8d-200">TelephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="ffc8d-201">MsExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="ffc8d-202">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-203">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-204">ProxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-205">子孫の連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffc8d-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="ffc8d-206">デバイスオブジェクトのアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="ffc8d-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="ffc8d-207">OU 上のデバイスオブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ffc8d-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="ffc8d-208">デバイスオブジェクトに付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffc8d-209">化</span><span class="sxs-lookup"><span data-stu-id="ffc8d-209">Group</span></span></th>
<th><span data-ttu-id="ffc8d-210">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-210">Permission</span></span></th>
<th><span data-ttu-id="ffc8d-211">適用対象</span><span class="sxs-lookup"><span data-stu-id="ffc8d-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffc8d-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-213">ディレクトリの変更の複製</span><span class="sxs-lookup"><span data-stu-id="ffc8d-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-214">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc8d-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-216">リストの内容</span><span class="sxs-lookup"><span data-stu-id="ffc8d-216">List contents</span></span></p>
<p><span data-ttu-id="ffc8d-217">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="ffc8d-217">Read all properties</span></span></p>
<p><span data-ttu-id="ffc8d-218">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-219">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-221">リストの内容</span><span class="sxs-lookup"><span data-stu-id="ffc8d-221">List contents</span></span></p>
<p><span data-ttu-id="ffc8d-222">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="ffc8d-222">Read all properties</span></span></p>
<p><span data-ttu-id="ffc8d-223">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-224">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc8d-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-226">RTCUserSearchPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-227">RTCUserProvisioningPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-228">RTCPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-229">公開-情報を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffc8d-230">個人情報を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="ffc8d-231">一般的な情報を読む-情報</span><span class="sxs-lookup"><span data-stu-id="ffc8d-231">Read General-Information</span></span></p>
<p><span data-ttu-id="ffc8d-232">ユーザーアカウントの制限を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-233">子孫の連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffc8d-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffc8d-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-235">子の作成</span><span class="sxs-lookup"><span data-stu-id="ffc8d-235">Create child</span></span></p>
<p><span data-ttu-id="ffc8d-236">子の削除</span><span class="sxs-lookup"><span data-stu-id="ffc8d-236">Delete child</span></span></p>
<p><span data-ttu-id="ffc8d-237">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="ffc8d-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-238">問い合わせ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc8d-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffc8d-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-240">DisplayName を書く</span><span class="sxs-lookup"><span data-stu-id="ffc8d-240">Write displayName</span></span></p>
<p><span data-ttu-id="ffc8d-241">説明の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-241">Write description</span></span></p>
<p><span data-ttu-id="ffc8d-242">TelephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-243">子孫のユーザーオブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffc8d-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffc8d-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-245">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-246">他の Ip電話を書く</span><span class="sxs-lookup"><span data-stu-id="ffc8d-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="ffc8d-247">DisplayName を書く</span><span class="sxs-lookup"><span data-stu-id="ffc8d-247">Write displayName</span></span></p>
<p><span data-ttu-id="ffc8d-248">説明の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-248">Write description</span></span></p>
<p><span data-ttu-id="ffc8d-249">TelephoneNumber の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="ffc8d-250">MsExchUCVoiceMailSettings の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="ffc8d-251">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-252">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-253">ProxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-254">子孫の連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffc8d-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="ffc8d-255">InetOrgPerson オブジェクトのアクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="ffc8d-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="ffc8d-256">OU 上の InetOrgPerson オブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ffc8d-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="ffc8d-257">InetOrgPerson オブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffc8d-258">化</span><span class="sxs-lookup"><span data-stu-id="ffc8d-258">Group</span></span></th>
<th><span data-ttu-id="ffc8d-259">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-259">Permission</span></span></th>
<th><span data-ttu-id="ffc8d-260">適用対象</span><span class="sxs-lookup"><span data-stu-id="ffc8d-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffc8d-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-262">ディレクトリの変更の複製</span><span class="sxs-lookup"><span data-stu-id="ffc8d-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-263">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc8d-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-265">リストの内容</span><span class="sxs-lookup"><span data-stu-id="ffc8d-265">List contents</span></span></p>
<p><span data-ttu-id="ffc8d-266">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="ffc8d-266">Read all properties</span></span></p>
<p><span data-ttu-id="ffc8d-267">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-268">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-270">リストの内容</span><span class="sxs-lookup"><span data-stu-id="ffc8d-270">List contents</span></span></p>
<p><span data-ttu-id="ffc8d-271">すべてのプロパティを読み上げる</span><span class="sxs-lookup"><span data-stu-id="ffc8d-271">Read all properties</span></span></p>
<p><span data-ttu-id="ffc8d-272">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ffc8d-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-273">このオブジェクトのみ</span><span class="sxs-lookup"><span data-stu-id="ffc8d-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc8d-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffc8d-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-275">RTCUserSearchPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-276">RTCUserProvisioningPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-277">RTCPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-278">個人情報を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="ffc8d-279">公開-情報を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffc8d-280">一般的な情報を読む-情報</span><span class="sxs-lookup"><span data-stu-id="ffc8d-280">Read General-Information</span></span></p>
<p><span data-ttu-id="ffc8d-281">ユーザーアカウントの制限を読む</span><span class="sxs-lookup"><span data-stu-id="ffc8d-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-282">子の inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffc8d-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc8d-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffc8d-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-284">RTCUserSearchPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-285">RTCUserProvisioningPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-286">RTCPropertySet の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffc8d-287">ProxyAddresses の書き込み</span><span class="sxs-lookup"><span data-stu-id="ffc8d-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ffc8d-288">子の inetOrgPerson オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ffc8d-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

