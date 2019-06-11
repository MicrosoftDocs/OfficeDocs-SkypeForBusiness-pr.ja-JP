---
title: 'Lync Server 2013: Lync Server 2013 でのスキーマの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bbe1c08b7d03042be2c03511103bfa4e43d39d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="5d04d-102">Lync Server 2013 でのスキーマの変更</span><span class="sxs-lookup"><span data-stu-id="5d04d-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d04d-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5d04d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5d04d-104">Lync Server 2013 を展開して運用する前に、スキーマを拡張して Active Directory ドメインサービスを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d04d-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="5d04d-105">スキーマ拡張は、Lync Server 2013 に必要なクラスと属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="5d04d-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="5d04d-106">Lync Server 2013 には、いくつかの新しいクラスと属性が必要です。また、既存のクラスと属性もいくつか変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d04d-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="5d04d-107">さらに、Lync Server 2013 の多くの構成情報は、以前のバージョンと同じように、AD DS ではなく中央管理ストアに保存されています。</span><span class="sxs-lookup"><span data-stu-id="5d04d-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="5d04d-108">次の情報は、引き続き Lync Server 2013 の AD DS に保存されています。</span><span class="sxs-lookup"><span data-stu-id="5d04d-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="5d04d-109">**スキーマの拡張機能**:</span><span class="sxs-lookup"><span data-stu-id="5d04d-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="5d04d-110">ユーザー オブジェクトの拡張</span><span class="sxs-lookup"><span data-stu-id="5d04d-110">User object extensions</span></span>
    
      - <span data-ttu-id="5d04d-111">サポートされている以前のバージョンとの下位互換性を維持するための Office Communications Server 2007 と Office Communications Server 2007 R2 のクラスの拡張機能</span><span class="sxs-lookup"><span data-stu-id="5d04d-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="5d04d-112">**データ**(Lync Server 拡張スキーマと既存のスキーマクラスに保存されています):</span><span class="sxs-lookup"><span data-stu-id="5d04d-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="5d04d-113">ユーザー SIP の Uniform Resource Identifier (URI) とその他のユーザー設定</span><span class="sxs-lookup"><span data-stu-id="5d04d-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="5d04d-114">返信グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="5d04d-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="5d04d-115">中央管理ストアへのポインター</span><span class="sxs-lookup"><span data-stu-id="5d04d-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="5d04d-116">Kerberos 認証アカウント (オプションのコンピューターオブジェクト)</span><span class="sxs-lookup"><span data-stu-id="5d04d-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="5d04d-117">このトピックでは、Lync Server 2013 で必要な Active Directory スキーマの変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d04d-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="5d04d-118">以前のバージョンの Office Communications Server によって導入されたスキーマの変更については説明しません。</span><span class="sxs-lookup"><span data-stu-id="5d04d-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="5d04d-119">クラスとその説明の一覧については、「 [Lync Server 2013 のスキーマクラスと説明](lync-server-2013-schema-classes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d04d-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="5d04d-120">属性とその説明の一覧については、「 [Lync Server 2013 のスキーマ属性と説明](lync-server-2013-schema-attributes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d04d-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="5d04d-121">属性が含まれている可能性のあるクラスのリストについては、「 [Lync Server 2013 でのスキーマの属性](lync-server-2013-schema-attributes-by-class.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d04d-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="5d04d-122">Msrtcsip-userenabled true プレフィックスは、Lync Server に固有のクラスと属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d04d-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="5d04d-123">新しい Active Directory の属性</span><span class="sxs-lookup"><span data-stu-id="5d04d-123">New Active Directory Attributes</span></span>

<span data-ttu-id="5d04d-124">次の表では、Lync Server 2013 によって追加される Active Directory の属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d04d-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="5d04d-125">Lync Server 2013 によって追加された属性</span><span class="sxs-lookup"><span data-stu-id="5d04d-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d04d-126">属性</span><span class="sxs-lookup"><span data-stu-id="5d04d-126">Attribute</span></span></th>
<th><span data-ttu-id="5d04d-127">説明</span><span class="sxs-lookup"><span data-stu-id="5d04d-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d04d-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5d04d-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="5d04d-129">このマルチバリュー属性は、ユーザーに適用される保留ポリシーの識別子を保持します。</span><span class="sxs-lookup"><span data-stu-id="5d04d-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="5d04d-130">保留ポリシーは、保留中のユーザーのメールボックスアイテムを保持します。</span><span class="sxs-lookup"><span data-stu-id="5d04d-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="5d04d-131">この属性は Exchange 2013 と共有されます。</span><span class="sxs-lookup"><span data-stu-id="5d04d-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d04d-132">Msrtcsip-userenabled true-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5d04d-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="5d04d-133">これは、SIP ルーティンググループの ID です。</span><span class="sxs-lookup"><span data-stu-id="5d04d-133">This is the SIP routing group ID.</span></span> <span data-ttu-id="5d04d-134">同じグループ内のユーザーは、同じフロントエンドサーバーに登録されます。</span><span class="sxs-lookup"><span data-stu-id="5d04d-134">Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d04d-135">Msrtcsip-userenabled true-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="5d04d-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="5d04d-136">この属性は、フロントエンドプールによって使用されるミラー化された SQL Server バックエンドを格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d04d-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="5d04d-137">変更された Active Directory クラス</span><span class="sxs-lookup"><span data-stu-id="5d04d-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="5d04d-138">次の表では、Lync Server 2013 によって変更される Active Directory クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5d04d-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="5d04d-139">Lync Server 2013 によって変更されたクラス</span><span class="sxs-lookup"><span data-stu-id="5d04d-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d04d-140">クラス</span><span class="sxs-lookup"><span data-stu-id="5d04d-140">Class</span></span></th>
<th><span data-ttu-id="5d04d-141">変更</span><span class="sxs-lookup"><span data-stu-id="5d04d-141">Change</span></span></th>
<th><span data-ttu-id="5d04d-142">Class または Attribute</span><span class="sxs-lookup"><span data-stu-id="5d04d-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d04d-143">ユーザー</span><span class="sxs-lookup"><span data-stu-id="5d04d-143">User</span></span></p></td>
<td><p><span data-ttu-id="5d04d-144">追加: 指定した値を含む</span><span class="sxs-lookup"><span data-stu-id="5d04d-144">add: mayContain</span></span></p>
<p><span data-ttu-id="5d04d-145">追加: 指定した値を含む</span><span class="sxs-lookup"><span data-stu-id="5d04d-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5d04d-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5d04d-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="5d04d-147">Msrtcsip-userenabled true-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5d04d-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d04d-148">問い合わせ</span><span class="sxs-lookup"><span data-stu-id="5d04d-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="5d04d-149">追加: 指定した値を含む</span><span class="sxs-lookup"><span data-stu-id="5d04d-149">add: mayContain</span></span></p>
<p><span data-ttu-id="5d04d-150">追加: 指定した値を含む</span><span class="sxs-lookup"><span data-stu-id="5d04d-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5d04d-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5d04d-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="5d04d-152">Msrtcsip-userenabled true-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5d04d-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d04d-153">メール受信者</span><span class="sxs-lookup"><span data-stu-id="5d04d-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="5d04d-154">追加: 指定した値を含む</span><span class="sxs-lookup"><span data-stu-id="5d04d-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5d04d-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5d04d-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d04d-156">Msrtcsip-userenabled true-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="5d04d-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="5d04d-157">追加: 指定した値を含む</span><span class="sxs-lookup"><span data-stu-id="5d04d-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5d04d-158">Msrtcsip-userenabled true-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="5d04d-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

