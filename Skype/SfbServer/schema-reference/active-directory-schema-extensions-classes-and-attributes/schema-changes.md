---
title: Skype ビジネス サーバーのスキーマの変更
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 展開して、ビジネス サーバー、Skype で運用する前にスキーマを拡張することによって Active Directory ドメイン サービスを準備する必要があります。 スキーマの拡張機能は、Skype でビジネスのサーバーのために必要な属性とクラスを追加します。
ms.openlocfilehash: 42b4417311c557323535aa03053ccb03d95cc840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="28d70-104">Skype ビジネス サーバーのスキーマの変更</span><span class="sxs-lookup"><span data-stu-id="28d70-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="28d70-105">展開して、ビジネス サーバー、Skype で運用する前にスキーマを拡張することによって Active Directory ドメイン サービスを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28d70-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="28d70-106">スキーマの拡張機能は、Skype でビジネスのサーバーのために必要な属性とクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="28d70-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span> 
  
<span data-ttu-id="28d70-107">Skype ビジネス サーバーのでは、いくつかの新しいクラスと属性が必要ですし、いくつかの既存のクラスおよび属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="28d70-107">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="28d70-108">さらに、ビジネス サーバーの Skype の多くの構成情報は以前のバージョンのように AD DS ではなく中央管理ストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="28d70-108">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="28d70-109">次の情報はまだ Skype で AD DS のビジネス サーバーの格納されます。</span><span class="sxs-lookup"><span data-stu-id="28d70-109">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="28d70-110">**スキーマの拡張機能**:</span><span class="sxs-lookup"><span data-stu-id="28d70-110">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="28d70-111">ユーザー オブジェクトの拡張</span><span class="sxs-lookup"><span data-stu-id="28d70-111">User object extensions</span></span>
    
  - <span data-ttu-id="28d70-112">Lync Server のサポートされている以前のバージョンとの下位互換性を維持するためにクラスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="28d70-112">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="28d70-113">**データ**(ビジネス サーバー拡張スキーマの Skype では既存のスキーマ クラスに格納されます。)</span><span class="sxs-lookup"><span data-stu-id="28d70-113">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="28d70-114">ユーザー SIP 統一リソース識別子 (URI) およびその他のユーザー設定</span><span class="sxs-lookup"><span data-stu-id="28d70-114">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="28d70-115">応答グループや会議アテンダントなどのアプリケーションの連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="28d70-115">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="28d70-116">中央管理ストアへのポインター</span><span class="sxs-lookup"><span data-stu-id="28d70-116">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="28d70-117">Kerberos 認証アカウント (オプションのコンピューター オブジェクト)</span><span class="sxs-lookup"><span data-stu-id="28d70-117">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="28d70-118">このトピックでは、Skype で必要なビジネス サーバー、Active Directory スキーマの変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="28d70-118">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="28d70-119">Office Communications Server の以前のバージョンで導入されたスキーマの変更については説明しません。</span><span class="sxs-lookup"><span data-stu-id="28d70-119">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="28d70-120">クラスとその説明のリストは、[スキーマのクラスおよびビジネス サーバーの Skype での説明](schema-classes-and-descriptions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28d70-120">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="28d70-121">属性とその説明のリストは、[スキーマの属性および Skype ビジネス サーバーの説明](schema-attributes-and-descriptions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28d70-121">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="28d70-122">属性を持つクラスのリストが含まれている、 [Skype のビジネス サーバーのクラスによってスキーマの属性](schema-attributes-by-class.md)を参照してください、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="28d70-122">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="28d70-123">MsRTCSIP プレフィックスは、クラスとは、Skype のビジネス サーバーに固有の属性を識別します。</span><span class="sxs-lookup"><span data-stu-id="28d70-123">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="28d70-124">新規の Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="28d70-124">New Active Directory Attributes</span></span>

<span data-ttu-id="28d70-125">次の表では、Skype でビジネスのサーバーに追加される Active Directory の属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="28d70-125">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="28d70-126">**Skype ビジネス サーバーの追加の属性**</span><span class="sxs-lookup"><span data-stu-id="28d70-126">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="28d70-127">**属性**</span><span class="sxs-lookup"><span data-stu-id="28d70-127">**Attribute**</span></span>|<span data-ttu-id="28d70-128">**説明**</span><span class="sxs-lookup"><span data-stu-id="28d70-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28d70-129">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="28d70-129">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="28d70-130">この複数値属性を保持するの識別子は、ユーザーに適用されるポリシーを保持します。</span><span class="sxs-lookup"><span data-stu-id="28d70-130">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="28d70-131">ポリシーがユーザーのメールボックス アイテムを保持する保留リストの中に保持します。</span><span class="sxs-lookup"><span data-stu-id="28d70-131">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="28d70-132">この属性は、Exchange 2013 で共有されています。</span><span class="sxs-lookup"><span data-stu-id="28d70-132">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="28d70-133">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="28d70-133">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="28d70-134">これは、SIP のルーティング グループの id。</span><span class="sxs-lookup"><span data-stu-id="28d70-134">This is the SIP routing group ID.</span></span> <span data-ttu-id="28d70-135">同じグループ内のユーザーは、同じフロント エンド サーバーに登録されます。</span><span class="sxs-lookup"><span data-stu-id="28d70-135">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="28d70-136">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="28d70-136">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="28d70-137">この属性を使用して、フロント エンド プールによって使用されるミラー化された SQL Server のバックエンドを格納します。</span><span class="sxs-lookup"><span data-stu-id="28d70-137">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="28d70-138">変更された Active Directory クラス</span><span class="sxs-lookup"><span data-stu-id="28d70-138">Modified Active Directory Classes</span></span>

<span data-ttu-id="28d70-139">次の表では、Skype でビジネスのサーバーの変更を Active Directory クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="28d70-139">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="28d70-140">**Skype ビジネス サーバーの変更クラス**</span><span class="sxs-lookup"><span data-stu-id="28d70-140">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="28d70-141">**クラス**</span><span class="sxs-lookup"><span data-stu-id="28d70-141">**Class**</span></span>|<span data-ttu-id="28d70-142">**変更**</span><span class="sxs-lookup"><span data-stu-id="28d70-142">**Change**</span></span>|<span data-ttu-id="28d70-143">**クラスまたは属性**</span><span class="sxs-lookup"><span data-stu-id="28d70-143">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="28d70-144">ユーザー</span><span class="sxs-lookup"><span data-stu-id="28d70-144">User</span></span>  <br/> |<span data-ttu-id="28d70-145">追加: は</span><span class="sxs-lookup"><span data-stu-id="28d70-145">add: mayContain</span></span>  <br/> <span data-ttu-id="28d70-146">追加: は</span><span class="sxs-lookup"><span data-stu-id="28d70-146">add: mayContain</span></span>  <br/> |<span data-ttu-id="28d70-147">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="28d70-147">ProxyAddresses</span></span>  <br/> <span data-ttu-id="28d70-148">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="28d70-148">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="28d70-149">連絡先</span><span class="sxs-lookup"><span data-stu-id="28d70-149">Contact</span></span>  <br/> |<span data-ttu-id="28d70-150">追加: は</span><span class="sxs-lookup"><span data-stu-id="28d70-150">add: mayContain</span></span>  <br/> <span data-ttu-id="28d70-151">追加: は</span><span class="sxs-lookup"><span data-stu-id="28d70-151">add: mayContain</span></span>  <br/> |<span data-ttu-id="28d70-152">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="28d70-152">ProxyAddresses</span></span>  <br/> <span data-ttu-id="28d70-153">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="28d70-153">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="28d70-154">メール受信者</span><span class="sxs-lookup"><span data-stu-id="28d70-154">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="28d70-155">追加: は</span><span class="sxs-lookup"><span data-stu-id="28d70-155">add: mayContain</span></span>  <br/> |<span data-ttu-id="28d70-156">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="28d70-156">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="28d70-157">msRTCSIP GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="28d70-157">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="28d70-158">追加: は</span><span class="sxs-lookup"><span data-stu-id="28d70-158">add: mayContain</span></span>  <br/> |<span data-ttu-id="28d70-159">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="28d70-159">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

