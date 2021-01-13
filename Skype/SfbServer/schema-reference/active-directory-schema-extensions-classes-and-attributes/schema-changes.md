---
title: Skype for Business Server でのスキーマの変更点
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Skype for Business Server を展開して運用する前に、スキーマを拡張して Active Directory ドメイン サービスを準備する必要があります。 スキーマ拡張機能は、Skype for Business Server に必要なクラスと属性を追加します。
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813577"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="5bd6f-104">Skype for Business Server でのスキーマの変更点</span><span class="sxs-lookup"><span data-stu-id="5bd6f-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="5bd6f-105">Skype for Business Server を展開して運用する前に、スキーマを拡張して Active Directory ドメイン サービスを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="5bd6f-106">スキーマ拡張機能は、Skype for Business Server に必要なクラスと属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="5bd6f-107">Lync Server 2013 から Skype for Business Server 2015 にアップグレードする場合、スキーマは変更されないので、この記事は適用されません。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="5bd6f-108">Skype for Business Server は、いくつかの新しいクラスと属性を必要とし、いくつかの既存のクラスと属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="5bd6f-109">さらに、Skype for Business Server の多くの構成情報は、以前のバージョンと同様に、AD DS ではなく中央管理ストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="5bd6f-110">次の情報は、Skype for Business Server AD DS に保存されます。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="5bd6f-111">**スキーマ拡張**:</span><span class="sxs-lookup"><span data-stu-id="5bd6f-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="5bd6f-112">ユーザー オブジェクトの拡張</span><span class="sxs-lookup"><span data-stu-id="5bd6f-112">User object extensions</span></span>
    
  - <span data-ttu-id="5bd6f-113">サポートされている以前のバージョンの Lync Server との下位互換性を維持するためのクラスの拡張機能。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="5bd6f-114">**データ** (Skype for Business Server の拡張スキーマと既存のスキーマ クラスに格納されます):</span><span class="sxs-lookup"><span data-stu-id="5bd6f-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="5bd6f-115">ユーザーの SIP URI (Uniform Resource Identifier) と他のユーザー設定</span><span class="sxs-lookup"><span data-stu-id="5bd6f-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="5bd6f-116">リソース グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="5bd6f-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="5bd6f-117">中央管理ストアへのポインター</span><span class="sxs-lookup"><span data-stu-id="5bd6f-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="5bd6f-118">Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)</span><span class="sxs-lookup"><span data-stu-id="5bd6f-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="5bd6f-119">このトピックでは、Skype for Business Server に必要な Active Directory スキーマの変更点について説明します。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="5bd6f-120">以前のバージョンの Communications Server で導入されたスキーマの変更Officeしません。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="5bd6f-121">クラスとその説明の一覧については、Skype for Business Server のスキーマ クラスと [説明を参照してください](schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="5bd6f-122">属性とその説明の一覧については、Skype for Business Server のスキーマ属性と [説明を参照してください](schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="5bd6f-123">含め得る属性を持つクラスの一覧については、Skype for Business Server のクラス別の [スキーマ属性を参照してください](schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="5bd6f-124">msRTCSIP プレフィックスは、Skype for Business Server に固有のクラスと属性を識別します。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="5bd6f-125">新規 Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="5bd6f-125">New Active Directory Attributes</span></span>

<span data-ttu-id="5bd6f-126">次の表では、Skype for Business Server によって追加される Active Directory 属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="5bd6f-127">**Skype for Business Server によって追加される属性**</span><span class="sxs-lookup"><span data-stu-id="5bd6f-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="5bd6f-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="5bd6f-128">**Attribute**</span></span>|<span data-ttu-id="5bd6f-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="5bd6f-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5bd6f-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5bd6f-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="5bd6f-131">この複数値の属性には、ユーザーに適用される保持ポリシーの識別子が保持されます。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="5bd6f-132">この保持の間は、ユーザーのメールボックス アイテムが保持ポリシーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="5bd6f-133">この属性は Exchange 2013 と共有されます。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="5bd6f-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5bd6f-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="5bd6f-p106">SIP ルーティング グループ ID。同じグループのユーザーは、同じフロントエンド サーバーに登録します。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-p106">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="5bd6f-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="5bd6f-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="5bd6f-138">この属性は、フロントエンド プールで使用SQL Serverミラー化されたバックエンドを格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="5bd6f-139">変更された Active Directory クラス</span><span class="sxs-lookup"><span data-stu-id="5bd6f-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="5bd6f-140">次の表では、Skype for Business Server によって変更される Active Directory クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5bd6f-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="5bd6f-141">**Skype for Business Server によって変更されるクラス**</span><span class="sxs-lookup"><span data-stu-id="5bd6f-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="5bd6f-142">**クラス**</span><span class="sxs-lookup"><span data-stu-id="5bd6f-142">**Class**</span></span>|<span data-ttu-id="5bd6f-143">**変更**</span><span class="sxs-lookup"><span data-stu-id="5bd6f-143">**Change**</span></span>|<span data-ttu-id="5bd6f-144">**クラスまたは属性**</span><span class="sxs-lookup"><span data-stu-id="5bd6f-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5bd6f-145">User</span><span class="sxs-lookup"><span data-stu-id="5bd6f-145">User</span></span>  <br/> |<span data-ttu-id="5bd6f-146">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5bd6f-146">add: mayContain</span></span>  <br/> <span data-ttu-id="5bd6f-147">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5bd6f-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="5bd6f-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5bd6f-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="5bd6f-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5bd6f-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="5bd6f-150">Contact</span><span class="sxs-lookup"><span data-stu-id="5bd6f-150">Contact</span></span>  <br/> |<span data-ttu-id="5bd6f-151">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5bd6f-151">add: mayContain</span></span>  <br/> <span data-ttu-id="5bd6f-152">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5bd6f-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="5bd6f-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5bd6f-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="5bd6f-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5bd6f-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="5bd6f-155">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="5bd6f-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="5bd6f-156">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="5bd6f-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="5bd6f-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5bd6f-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="5bd6f-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="5bd6f-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="5bd6f-159">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5bd6f-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="5bd6f-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="5bd6f-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

