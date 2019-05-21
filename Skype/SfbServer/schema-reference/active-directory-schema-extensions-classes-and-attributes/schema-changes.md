---
title: Skype for Business Server でのスキーマの変更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Skype for Business Server を展開して運用する前に、スキーマを拡張して Active Directory ドメインサービスを準備する必要があります。 スキーマ拡張は、Skype for Business Server で必要なクラスと属性を追加します。
ms.openlocfilehash: 34f97f7a37adc23635f938fb12c9a72e22429538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296659"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="47938-104">Skype for Business Server でのスキーマの変更</span><span class="sxs-lookup"><span data-stu-id="47938-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="47938-105">Skype for Business Server を展開して運用する前に、スキーマを拡張して Active Directory ドメインサービスを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47938-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="47938-106">スキーマ拡張は、Skype for Business Server で必要なクラスと属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="47938-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="47938-107">Lync Server 2013 から Skype for Business Server 2015 にアップグレードする場合は、スキーマの変更は行われないため、この記事は適用されません。</span><span class="sxs-lookup"><span data-stu-id="47938-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="47938-108">Skype for Business Server では、いくつかの新しいクラスと属性が必要になります。また、既存のクラスと属性もいくつか変更されます。</span><span class="sxs-lookup"><span data-stu-id="47938-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="47938-109">さらに、Skype for Business Server の構成情報の多くは、以前のバージョンと同じように、AD DS ではなく中央管理ストアに保存されています。</span><span class="sxs-lookup"><span data-stu-id="47938-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="47938-110">以下の情報は、Skype for Business Server の AD DS にも保存されています。</span><span class="sxs-lookup"><span data-stu-id="47938-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="47938-111">**スキーマの拡張機能**:</span><span class="sxs-lookup"><span data-stu-id="47938-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="47938-112">ユーザー オブジェクトの拡張</span><span class="sxs-lookup"><span data-stu-id="47938-112">User object extensions</span></span>
    
  - <span data-ttu-id="47938-113">サポートされている以前のバージョンの Lync Server との下位互換性を維持するためのクラスの拡張機能。</span><span class="sxs-lookup"><span data-stu-id="47938-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="47938-114">**データ**(Skype for Business Server 拡張スキーマと既存のスキーマクラスに保存されています):</span><span class="sxs-lookup"><span data-stu-id="47938-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="47938-115">ユーザー SIP の Uniform Resource Identifier (URI) とその他のユーザー設定</span><span class="sxs-lookup"><span data-stu-id="47938-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="47938-116">返信グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="47938-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="47938-117">中央管理ストアへのポインター</span><span class="sxs-lookup"><span data-stu-id="47938-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="47938-118">Kerberos 認証アカウント (オプションのコンピューターオブジェクト)</span><span class="sxs-lookup"><span data-stu-id="47938-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="47938-119">このトピックでは、Skype for Business Server で必要な Active Directory スキーマの変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="47938-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="47938-120">以前のバージョンの Office Communications Server によって導入されたスキーマの変更については説明しません。</span><span class="sxs-lookup"><span data-stu-id="47938-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="47938-121">クラスとその説明の一覧については、「 [Skype For Business Server のスキーマクラスと説明](schema-classes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47938-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="47938-122">属性とその説明の一覧については、「 [Skype For Business Server のスキーマ属性と説明](schema-attributes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47938-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="47938-123">属性が含まれるクラスの一覧については、「 [Skype For Business Server のクラス別のスキーマ属性](schema-attributes-by-class.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47938-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="47938-124">Msrtcsip-userenabled true プレフィックスは、Skype for Business Server に固有のクラスと属性を識別します。</span><span class="sxs-lookup"><span data-stu-id="47938-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="47938-125">新しい Active Directory の属性</span><span class="sxs-lookup"><span data-stu-id="47938-125">New Active Directory Attributes</span></span>

<span data-ttu-id="47938-126">次の表では、Skype for Business Server によって追加される Active Directory の属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="47938-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="47938-127">**Skype for Business Server によって追加された属性**</span><span class="sxs-lookup"><span data-stu-id="47938-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="47938-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="47938-128">**Attribute**</span></span>|<span data-ttu-id="47938-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="47938-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="47938-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="47938-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="47938-131">このマルチバリュー属性は、ユーザーに適用される保留ポリシーの識別子を保持します。</span><span class="sxs-lookup"><span data-stu-id="47938-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="47938-132">保留ポリシーは、保留中のユーザーのメールボックスアイテムを保持します。</span><span class="sxs-lookup"><span data-stu-id="47938-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="47938-133">この属性は Exchange 2013 と共有されます。</span><span class="sxs-lookup"><span data-stu-id="47938-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="47938-134">Msrtcsip-userenabled true-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="47938-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="47938-135">これは、SIP ルーティンググループの ID です。</span><span class="sxs-lookup"><span data-stu-id="47938-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="47938-136">同じグループ内のユーザーは、同じフロントエンドサーバーに登録されます。</span><span class="sxs-lookup"><span data-stu-id="47938-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="47938-137">Msrtcsip-userenabled true-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="47938-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="47938-138">この属性は、フロントエンドプールによって使用されるミラー化された SQL Server バックエンドを格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="47938-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="47938-139">変更された Active Directory クラス</span><span class="sxs-lookup"><span data-stu-id="47938-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="47938-140">次の表では、Skype for Business Server によって変更される Active Directory クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="47938-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="47938-141">**Skype for Business Server によって変更されたクラス**</span><span class="sxs-lookup"><span data-stu-id="47938-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="47938-142">**クラス**</span><span class="sxs-lookup"><span data-stu-id="47938-142">**Class**</span></span>|<span data-ttu-id="47938-143">**変更**</span><span class="sxs-lookup"><span data-stu-id="47938-143">**Change**</span></span>|<span data-ttu-id="47938-144">**Class または Attribute**</span><span class="sxs-lookup"><span data-stu-id="47938-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="47938-145">ユーザー</span><span class="sxs-lookup"><span data-stu-id="47938-145">User</span></span>  <br/> |<span data-ttu-id="47938-146">追加: 指定した値を含む</span><span class="sxs-lookup"><span data-stu-id="47938-146">add: mayContain</span></span>  <br/> <span data-ttu-id="47938-147">追加: 指定した値を含む</span><span class="sxs-lookup"><span data-stu-id="47938-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="47938-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="47938-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="47938-149">Msrtcsip-userenabled true-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="47938-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="47938-150">問い合わせ</span><span class="sxs-lookup"><span data-stu-id="47938-150">Contact</span></span>  <br/> |<span data-ttu-id="47938-151">追加: 指定した値を含む</span><span class="sxs-lookup"><span data-stu-id="47938-151">add: mayContain</span></span>  <br/> <span data-ttu-id="47938-152">追加: 指定した値を含む</span><span class="sxs-lookup"><span data-stu-id="47938-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="47938-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="47938-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="47938-154">Msrtcsip-userenabled true-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="47938-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="47938-155">メール受信者</span><span class="sxs-lookup"><span data-stu-id="47938-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="47938-156">追加: 指定した値を含む</span><span class="sxs-lookup"><span data-stu-id="47938-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="47938-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="47938-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="47938-158">Msrtcsip-userenabled true-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="47938-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="47938-159">追加: 指定した値を含む</span><span class="sxs-lookup"><span data-stu-id="47938-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="47938-160">Msrtcsip-userenabled true-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="47938-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

