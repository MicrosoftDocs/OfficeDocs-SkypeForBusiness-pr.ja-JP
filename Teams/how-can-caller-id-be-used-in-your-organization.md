---
title: 組織での発信者番号の利用方法
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: 発信者番号通知は、CallingLineIdentity と呼ばれるポリシーを使用して、電話システム ユーザーの着信と発信の両方で制御できます。
ms.openlocfilehash: 2547e6ca3aed10d112897aa1b24900a479c5c8ef
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224210"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="0dd98-103">組織での発信者番号の利用方法</span><span class="sxs-lookup"><span data-stu-id="0dd98-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="0dd98-104">発信者番号通知は、CallingLineIdentity と呼ばれるポリシーを使用して、電話システム ユーザーの着信と発信の両方で制御できます。</span><span class="sxs-lookup"><span data-stu-id="0dd98-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="0dd98-105">発信者番号機能は、PSTN 接続にかかわらず、すべての電話システムユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="0dd98-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="0dd98-106">オンラインの PSTN 接続</span><span class="sxs-lookup"><span data-stu-id="0dd98-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="0dd98-107">Skype for Business Cloud Connector Edition を使用したオンプレミスの PSTN 接続 (Cloud Connector Edition 1.4.2 以降が必要です)</span><span class="sxs-lookup"><span data-stu-id="0dd98-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="0dd98-108">Skype for Business Server を使用したオンプレミスの SPTN 接続 (Skype for Business Server 2015 CU5 以降が必要です）</span><span class="sxs-lookup"><span data-stu-id="0dd98-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="0dd98-109">このポリシーは、Skype for Business 2015 Server では使用できません。</span><span class="sxs-lookup"><span data-stu-id="0dd98-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="0dd98-110">発信側の発信者番号通知</span><span class="sxs-lookup"><span data-stu-id="0dd98-110">Outbound caller ID</span></span>

<span data-ttu-id="0dd98-111">送信 PSTN の発信者番号認識には、次の3つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0dd98-111">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="0dd98-112">ユーザーに割り当てられた電話番号。既定です。</span><span class="sxs-lookup"><span data-stu-id="0dd98-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="0dd98-113">Office 365 の電話番号インベントリの通話プランで*サービス*電話番号と*無料*電話番号として分類されている電話番号。</span><span class="sxs-lookup"><span data-stu-id="0dd98-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="0dd98-114">これは通常、組織の自動応答またはコール キューに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0dd98-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="0dd98-115">非通知に設定。</span><span class="sxs-lookup"><span data-stu-id="0dd98-115">Set to anonymous.</span></span>
    
<span data-ttu-id="0dd98-116">ただし、以下の種類の電話番号を発信側の発信者番号通知に割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="0dd98-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="0dd98-117">通話プランの電話番号インベントリで*ユーザー*として分類されているすべての電話番号。</span><span class="sxs-lookup"><span data-stu-id="0dd98-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="0dd98-118">Skype for Business Server のオンプレミスの電話番号</span><span class="sxs-lookup"><span data-stu-id="0dd98-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="0dd98-119">発信側の発信者番号通知を設定するには、「[ユーザーの発信者番号通知を設定する](/microsoftteams/set-the-caller-id-for-a-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dd98-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="0dd98-120">発信の発信者番号のエンドユーザーによる制御</span><span class="sxs-lookup"><span data-stu-id="0dd98-120">End user control of outbound caller ID</span></span>

<span data-ttu-id="0dd98-121">EnableUserOverride 属性を使うと、1人または複数のユーザーがその発信者番号設定を**匿名**に変更できます。</span><span class="sxs-lookup"><span data-stu-id="0dd98-121">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="0dd98-122">これが適用されるのは、CallingLineIdentity のポリシーが LineURI または Substitute のいずれかの CallingIDSubstitute パラメーターで構成されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="0dd98-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="0dd98-123">EnableUserOverride の既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="0dd98-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="0dd98-124">エンドユーザーは、Skype for Business デスクトップクライアントの [**設定**] タブを使用して、発信者番号を**匿名**に設定することができます。 [**エンドユーザーに通話**を発信する (管理者によって有効になっている場合)] を選び、[**すべての通話に対して電話番号とプロファイル情報を非表示に**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0dd98-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="0dd98-125">Teams では、ユーザーは右上隅にある自分のプロファイル画像に移動して、[**設定**の呼び出し] を選び、[  >  **Calls\*\*\*\*発信者**番号認識] で [**すべての通話に対して電話番号とプロファイル情報を非表示に**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0dd98-125">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="0dd98-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="0dd98-126">**Windows**</span></span> <br/> |<span data-ttu-id="0dd98-127">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="0dd98-127">**Version**</span></span> <br/> |<span data-ttu-id="0dd98-128">**サポートされ**</span><span class="sxs-lookup"><span data-stu-id="0dd98-128">**Supported**</span></span> <br/> |
|<span data-ttu-id="0dd98-129">クイック実行</span><span class="sxs-lookup"><span data-stu-id="0dd98-129">Click-to-Run</span></span>  <br/> |<span data-ttu-id="0dd98-130">2016 年 12 月 6 日 - バージョン 1611 (ビルド 7571.2072) でリリースされた現在のチャネル</span><span class="sxs-lookup"><span data-stu-id="0dd98-130">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="0dd98-131">はい</span><span class="sxs-lookup"><span data-stu-id="0dd98-131">Yes</span></span>  <br/> |
|<span data-ttu-id="0dd98-132">クイック実行</span><span class="sxs-lookup"><span data-stu-id="0dd98-132">Click-to-Run</span></span>  <br/> |<span data-ttu-id="0dd98-133">2017 年 2 月 22日 - バージョン 1701 (ビルド 7766.2060) でリリースされた段階的提供チャネルの最初のリリース</span><span class="sxs-lookup"><span data-stu-id="0dd98-133">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="0dd98-134">はい</span><span class="sxs-lookup"><span data-stu-id="0dd98-134">Yes</span></span>  <br/> |
|<span data-ttu-id="0dd98-135">クイック実行</span><span class="sxs-lookup"><span data-stu-id="0dd98-135">Click-to-Run</span></span>  <br/> |<span data-ttu-id="0dd98-136">2017年 6 月 13日 - バージョン 1701 (ビルド 7766.2092) でリリースされた段階的提供チャネル</span><span class="sxs-lookup"><span data-stu-id="0dd98-136">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="0dd98-137">はい</span><span class="sxs-lookup"><span data-stu-id="0dd98-137">Yes</span></span>  <br/> |
|<span data-ttu-id="0dd98-138">MSI</span><span class="sxs-lookup"><span data-stu-id="0dd98-138">MSI</span></span>  <br/> |<span data-ttu-id="0dd98-139">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0dd98-139">Skype for Business</span></span>  <br/> |<span data-ttu-id="0dd98-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="0dd98-140">No</span></span>  <br/> |
|<span data-ttu-id="0dd98-141">Mac</span><span class="sxs-lookup"><span data-stu-id="0dd98-141">Mac</span></span>  <br/> |<span data-ttu-id="0dd98-142">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0dd98-142">Skype for Business</span></span>  <br/> |<span data-ttu-id="0dd98-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="0dd98-143">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="0dd98-144">着信の発信者番号</span><span class="sxs-lookup"><span data-stu-id="0dd98-144">Inbound caller ID</span></span>

<span data-ttu-id="0dd98-145">電話システムでは、番号が Azure AD のユーザーに関連付けられている場合は、外部電話番号の [ID] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dd98-145">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="0dd98-146">電話番号が Azure AD にない場合は、電話会社が指定した表示名が表示されます (利用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="0dd98-146">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="0dd98-147">BlockIncomingCallerID 属性を使用すると、着信した PSTN 通話の発信者番号通知をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="0dd98-147">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="0dd98-148">この属性を設定することはできますが、ユーザー設定ページではエンド ユーザーには使用できません。</span><span class="sxs-lookup"><span data-stu-id="0dd98-148">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="0dd98-149">また、現在はオンラインの PSTN 接続のみで使用可能です。</span><span class="sxs-lookup"><span data-stu-id="0dd98-149">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="0dd98-150">発信側の発信者番号通知を設定するには、「[ユーザーの発信者番号通知を設定する](/microsoftteams/set-the-caller-id-for-a-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dd98-150">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0dd98-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="0dd98-151">Related topics</span></span>
[<span data-ttu-id="0dd98-152">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="0dd98-152">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="0dd98-153">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="0dd98-153">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="0dd98-154">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="0dd98-154">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="0dd98-155">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="0dd98-155">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="0dd98-156">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="0dd98-156">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
