---
title: 'Lync Server 2013: Lync Server 2013 でのスキーマの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 789a6a67b1794eee5f01e8672f9aeb1076646ecf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="43b70-102">Lync Server 2013 でのスキーマの変更</span><span class="sxs-lookup"><span data-stu-id="43b70-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43b70-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="43b70-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="43b70-104">Lync Server 2013 を展開して運用する前に、スキーマを拡張して Active Directory ドメインサービスを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43b70-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="43b70-105">スキーマ拡張機能は、Lync Server 2013 で必要なクラスと属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="43b70-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="43b70-106">Lync Server 2013 には、いくつかの新しいクラスと属性が必要であり、一部の既存のクラスおよび属性が変更されています。</span><span class="sxs-lookup"><span data-stu-id="43b70-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="43b70-107">さらに、Lync Server 2013 の構成情報の多くは、以前のバージョンとは異なる方法で AD DS ではなく中央管理ストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="43b70-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="43b70-108">次の情報は、引き続き Lync Server 2013 の AD DS に保存されています。</span><span class="sxs-lookup"><span data-stu-id="43b70-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="43b70-109">**スキーマ拡張**:</span><span class="sxs-lookup"><span data-stu-id="43b70-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="43b70-110">ユーザー オブジェクトの拡張</span><span class="sxs-lookup"><span data-stu-id="43b70-110">User object extensions</span></span>
    
      - <span data-ttu-id="43b70-111">サポートされている以前のバージョンとの下位互換性を維持するための Office Communications Server 2007 および Office Communications Server 2007 R2 クラスの拡張機能</span><span class="sxs-lookup"><span data-stu-id="43b70-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="43b70-112">**データ**(Lync Server 拡張スキーマおよび既存のスキーマクラスに格納されている):</span><span class="sxs-lookup"><span data-stu-id="43b70-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="43b70-113">ユーザーの SIP URI (Uniform Resource Identifier) と他のユーザー設定</span><span class="sxs-lookup"><span data-stu-id="43b70-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="43b70-114">リソース グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="43b70-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="43b70-115">中央管理ストアへのポインター</span><span class="sxs-lookup"><span data-stu-id="43b70-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="43b70-116">Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)</span><span class="sxs-lookup"><span data-stu-id="43b70-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="43b70-117">このトピックでは、Lync Server 2013 で必要な Active Directory スキーマの変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="43b70-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="43b70-118">以前のバージョンの Office Communications Server で導入されたスキーマの変更については説明しません。</span><span class="sxs-lookup"><span data-stu-id="43b70-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="43b70-119">クラスとその説明の一覧については、「 [Lync Server 2013 のスキーマクラスと説明](lync-server-2013-schema-classes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43b70-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="43b70-120">属性とその説明の一覧については、「 [Lync Server 2013 のスキーマの属性と説明](lync-server-2013-schema-attributes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43b70-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="43b70-121">含まれる可能性のある属性を持つクラスの一覧については、「 [Lync Server 2013 のクラス別スキーマの属性](lync-server-2013-schema-attributes-by-class.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43b70-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="43b70-122">MsRTCSIP プレフィックスは、Lync Server に固有のクラスと属性を識別します。</span><span class="sxs-lookup"><span data-stu-id="43b70-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="43b70-123">新規 Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="43b70-123">New Active Directory Attributes</span></span>

<span data-ttu-id="43b70-124">次の表に、Lync Server 2013 によって追加される Active Directory 属性を示します。</span><span class="sxs-lookup"><span data-stu-id="43b70-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="43b70-125">Lync Server 2013 によって追加される属性</span><span class="sxs-lookup"><span data-stu-id="43b70-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43b70-126">属性</span><span class="sxs-lookup"><span data-stu-id="43b70-126">Attribute</span></span></th>
<th><span data-ttu-id="43b70-127">説明</span><span class="sxs-lookup"><span data-stu-id="43b70-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43b70-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="43b70-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="43b70-129">この複数値の属性には、ユーザーに適用される保持ポリシーの識別子が保持されます。</span><span class="sxs-lookup"><span data-stu-id="43b70-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="43b70-130">この保持の間は、ユーザーのメールボックス アイテムが保持ポリシーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="43b70-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="43b70-131">この属性は、Exchange 2013 と共有されます。</span><span class="sxs-lookup"><span data-stu-id="43b70-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43b70-132">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="43b70-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="43b70-p105">SIP ルーティング グループ ID。同じグループのユーザーは、同じフロントエンド サーバーに登録します。</span><span class="sxs-lookup"><span data-stu-id="43b70-p105">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43b70-135">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="43b70-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="43b70-136">この属性は、フロントエンドプールで使用されるミラーリングされた SQL Server バックエンドを格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="43b70-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="43b70-137">変更された Active Directory クラス</span><span class="sxs-lookup"><span data-stu-id="43b70-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="43b70-138">次の表では、Lync Server 2013 によって変更された Active Directory クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="43b70-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="43b70-139">Lync Server 2013 によって変更されるクラス</span><span class="sxs-lookup"><span data-stu-id="43b70-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43b70-140">クラス</span><span class="sxs-lookup"><span data-stu-id="43b70-140">Class</span></span></th>
<th><span data-ttu-id="43b70-141">変更</span><span class="sxs-lookup"><span data-stu-id="43b70-141">Change</span></span></th>
<th><span data-ttu-id="43b70-142">クラスまたは属性</span><span class="sxs-lookup"><span data-stu-id="43b70-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43b70-143">ユーザー</span><span class="sxs-lookup"><span data-stu-id="43b70-143">User</span></span></p></td>
<td><p><span data-ttu-id="43b70-144">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="43b70-144">add: mayContain</span></span></p>
<p><span data-ttu-id="43b70-145">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="43b70-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="43b70-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="43b70-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="43b70-147">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="43b70-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43b70-148">連絡先</span><span class="sxs-lookup"><span data-stu-id="43b70-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="43b70-149">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="43b70-149">add: mayContain</span></span></p>
<p><span data-ttu-id="43b70-150">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="43b70-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="43b70-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="43b70-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="43b70-152">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="43b70-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43b70-153">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="43b70-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="43b70-154">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="43b70-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="43b70-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="43b70-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43b70-156">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="43b70-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="43b70-157">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="43b70-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="43b70-158">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="43b70-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

