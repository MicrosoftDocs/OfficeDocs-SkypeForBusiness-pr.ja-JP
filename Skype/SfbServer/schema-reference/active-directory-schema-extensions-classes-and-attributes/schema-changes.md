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
ms.openlocfilehash: 8594ff3a25c7af7ef8c57468a8900d3abbb7f790
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240918"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="2f5c8-104">Skype ビジネス サーバーのスキーマの変更</span><span class="sxs-lookup"><span data-stu-id="2f5c8-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="2f5c8-105">展開して、ビジネス サーバー、Skype で運用する前にスキーマを拡張することによって Active Directory ドメイン サービスを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="2f5c8-106">スキーマの拡張機能は、Skype でビジネスのサーバーのために必要な属性とクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="2f5c8-107">アップグレードする Lync Server 2013 に Skype ビジネス サーバー 2015 の場合、は、スキーマの変更は行われませんし、この資料は適用されませんのでします。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="2f5c8-108">Skype ビジネス サーバーのでは、いくつかの新しいクラスと属性が必要ですし、いくつかの既存のクラスおよび属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="2f5c8-109">さらに、ビジネス サーバーの Skype の多くの構成情報は以前のバージョンのように AD DS ではなく中央管理ストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="2f5c8-110">次の情報はまだ Skype で AD DS のビジネス サーバーの格納されます。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="2f5c8-111">**スキーマの拡張機能**:</span><span class="sxs-lookup"><span data-stu-id="2f5c8-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="2f5c8-112">ユーザー オブジェクトの拡張</span><span class="sxs-lookup"><span data-stu-id="2f5c8-112">User object extensions</span></span>
    
  - <span data-ttu-id="2f5c8-113">Lync Server のサポートされている以前のバージョンとの下位互換性を維持するためにクラスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="2f5c8-114">**データ**(ビジネス サーバー拡張スキーマの Skype では既存のスキーマ クラスに格納されます。)</span><span class="sxs-lookup"><span data-stu-id="2f5c8-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="2f5c8-115">ユーザー SIP 統一リソース識別子 (URI) およびその他のユーザー設定</span><span class="sxs-lookup"><span data-stu-id="2f5c8-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="2f5c8-116">応答グループや会議アテンダントなどのアプリケーションの連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="2f5c8-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="2f5c8-117">中央管理ストアへのポインター</span><span class="sxs-lookup"><span data-stu-id="2f5c8-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="2f5c8-118">Kerberos 認証アカウント (オプションのコンピューター オブジェクト)</span><span class="sxs-lookup"><span data-stu-id="2f5c8-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="2f5c8-119">このトピックでは、Skype で必要なビジネス サーバー、Active Directory スキーマの変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="2f5c8-120">Office Communications Server の以前のバージョンで導入されたスキーマの変更については説明しません。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="2f5c8-121">クラスとその説明のリストは、[スキーマのクラスおよびビジネス サーバーの Skype での説明](schema-classes-and-descriptions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="2f5c8-122">属性とその説明のリストは、[スキーマの属性および Skype ビジネス サーバーの説明](schema-attributes-and-descriptions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="2f5c8-123">属性を持つクラスのリストが含まれている、 [Skype のビジネス サーバーのクラスによってスキーマの属性](schema-attributes-by-class.md)を参照してください、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="2f5c8-124">MsRTCSIP プレフィックスは、クラスとは、Skype のビジネス サーバーに固有の属性を識別します。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="2f5c8-125">新規の Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="2f5c8-125">New Active Directory Attributes</span></span>

<span data-ttu-id="2f5c8-126">次の表では、Skype でビジネスのサーバーに追加される Active Directory の属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="2f5c8-127">**Skype ビジネス サーバーの追加の属性**</span><span class="sxs-lookup"><span data-stu-id="2f5c8-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="2f5c8-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="2f5c8-128">**Attribute**</span></span>|<span data-ttu-id="2f5c8-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="2f5c8-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2f5c8-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="2f5c8-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="2f5c8-131">この複数値属性を保持するの識別子は、ユーザーに適用されるポリシーを保持します。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="2f5c8-132">ポリシーがユーザーのメールボックス アイテムを保持する保留リストの中に保持します。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="2f5c8-133">この属性は、Exchange 2013 で共有されています。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="2f5c8-134">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="2f5c8-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="2f5c8-135">これは、SIP のルーティング グループの id。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="2f5c8-136">同じグループ内のユーザーは、同じフロント エンド サーバーに登録されます。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="2f5c8-137">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="2f5c8-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="2f5c8-138">この属性を使用して、フロント エンド プールによって使用されるミラー化された SQL Server のバックエンドを格納します。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="2f5c8-139">変更された Active Directory クラス</span><span class="sxs-lookup"><span data-stu-id="2f5c8-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="2f5c8-140">次の表では、Skype でビジネスのサーバーの変更を Active Directory クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2f5c8-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="2f5c8-141">**Skype ビジネス サーバーの変更クラス**</span><span class="sxs-lookup"><span data-stu-id="2f5c8-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="2f5c8-142">**クラス**</span><span class="sxs-lookup"><span data-stu-id="2f5c8-142">**Class**</span></span>|<span data-ttu-id="2f5c8-143">**変更**</span><span class="sxs-lookup"><span data-stu-id="2f5c8-143">**Change**</span></span>|<span data-ttu-id="2f5c8-144">**クラスまたは属性**</span><span class="sxs-lookup"><span data-stu-id="2f5c8-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2f5c8-145">ユーザー</span><span class="sxs-lookup"><span data-stu-id="2f5c8-145">User</span></span>  <br/> |<span data-ttu-id="2f5c8-146">追加: は</span><span class="sxs-lookup"><span data-stu-id="2f5c8-146">add: mayContain</span></span>  <br/> <span data-ttu-id="2f5c8-147">追加: は</span><span class="sxs-lookup"><span data-stu-id="2f5c8-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="2f5c8-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="2f5c8-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="2f5c8-149">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="2f5c8-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="2f5c8-150">連絡先</span><span class="sxs-lookup"><span data-stu-id="2f5c8-150">Contact</span></span>  <br/> |<span data-ttu-id="2f5c8-151">追加: は</span><span class="sxs-lookup"><span data-stu-id="2f5c8-151">add: mayContain</span></span>  <br/> <span data-ttu-id="2f5c8-152">追加: は</span><span class="sxs-lookup"><span data-stu-id="2f5c8-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="2f5c8-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="2f5c8-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="2f5c8-154">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="2f5c8-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="2f5c8-155">メール受信者</span><span class="sxs-lookup"><span data-stu-id="2f5c8-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="2f5c8-156">追加: は</span><span class="sxs-lookup"><span data-stu-id="2f5c8-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="2f5c8-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="2f5c8-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="2f5c8-158">msRTCSIP GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="2f5c8-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="2f5c8-159">追加: は</span><span class="sxs-lookup"><span data-stu-id="2f5c8-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="2f5c8-160">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="2f5c8-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

