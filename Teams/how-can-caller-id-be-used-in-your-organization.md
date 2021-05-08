---
title: 組織での発信者番号の利用方法
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: e723311b2780dd1d43bad4874b72133e09ff4fc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120678"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="1d480-103">組織での発信者番号の利用方法</span><span class="sxs-lookup"><span data-stu-id="1d480-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="1d480-104">発信者番号通知は、CallingLineIdentity と呼ばれるポリシーを使用して、電話システム ユーザーの着信と発信の両方で制御できます。</span><span class="sxs-lookup"><span data-stu-id="1d480-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="1d480-105">発信者番号機能は、PSTN 接続電話システム、すべてのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d480-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>

- <span data-ttu-id="1d480-106">Microsoft 通話プラン</span><span class="sxs-lookup"><span data-stu-id="1d480-106">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="1d480-107">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="1d480-107">Phone System Direct Routing</span></span> 
  
- <span data-ttu-id="1d480-108">オンラインの PSTN 接続</span><span class="sxs-lookup"><span data-stu-id="1d480-108">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="1d480-109">Skype for Business Cloud Connector Edition を使用したオンプレミスの PSTN 接続 (Cloud Connector Edition 1.4.2 以降が必要です)</span><span class="sxs-lookup"><span data-stu-id="1d480-109">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="1d480-110">Skype for Business Server を使用したオンプレミスの SPTN 接続 (Skype for Business Server 2015 CU5 以降が必要です）</span><span class="sxs-lookup"><span data-stu-id="1d480-110">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="1d480-111">このポリシーは、Skype for Business 2015 Server では使用できません。</span><span class="sxs-lookup"><span data-stu-id="1d480-111">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="1d480-112">発信側の発信者番号通知</span><span class="sxs-lookup"><span data-stu-id="1d480-112">Outbound caller ID</span></span>

<span data-ttu-id="1d480-113">発信 PSTN 発信者番号には、次の 3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="1d480-113">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="1d480-114">ユーザーに割り当てられた電話番号。既定です。</span><span class="sxs-lookup"><span data-stu-id="1d480-114">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="1d480-115">通話プランの電話番号インベントリでサービスとして分類される電話番号と無料電話番号。</span><span class="sxs-lookup"><span data-stu-id="1d480-115">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="1d480-116">これは通常、組織の自動応答またはコール キューに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1d480-116">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="1d480-117">非通知に設定。</span><span class="sxs-lookup"><span data-stu-id="1d480-117">Set to anonymous.</span></span>
    
<span data-ttu-id="1d480-118">ただし、以下の種類の電話番号を発信側の発信者番号通知に割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="1d480-118">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="1d480-119">通話プランの電話番号インベントリで *ユーザー* として分類されているすべての電話番号。</span><span class="sxs-lookup"><span data-stu-id="1d480-119">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="1d480-120">Skype for Business Server のオンプレミスの電話番号</span><span class="sxs-lookup"><span data-stu-id="1d480-120">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="1d480-121">発信側の発信者番号通知を設定するには、「[ユーザーの発信者番号通知を設定する](./set-the-caller-id-for-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d480-121">To set the outbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="1d480-122">送信呼び出し元 ID のエンド ユーザー制御</span><span class="sxs-lookup"><span data-stu-id="1d480-122">End user control of outbound caller ID</span></span>

<span data-ttu-id="1d480-123">EnableUserOverride 属性を使用すると、1 人または複数のユーザーが発信者番号の設定を Anonymous に **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="1d480-123">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="1d480-124">これが適用されるのは、CallingLineIdentity のポリシーが LineURI または Substitute のいずれかの CallingIDSubstitute パラメーターで構成されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="1d480-124">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="1d480-125">EnableUserOverride の既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="1d480-125">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="1d480-126">エンド ユーザーは、Skype for Business デスクトップクライアントの **設定** タブを使用して発信者番号を匿名に設定し、[エンド ユーザーの呼び出し] **(管理者** が有効になっている場合) を選択し、[すべての通話で電話番号とプロファイル情報を非表示にする] を選択 **します。**</span><span class="sxs-lookup"><span data-stu-id="1d480-126">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="1d480-127">このTeams、ユーザーは右上隅にある自分のプロフィール画像に移動し **、[設定** 通話] を選択し、[発信者番号] で [すべての通話の電話番号とプロファイル情報を非表示にする] を選択します  >  。  </span><span class="sxs-lookup"><span data-stu-id="1d480-127">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="1d480-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="1d480-128">**Windows**</span></span> <br/> |<span data-ttu-id="1d480-129">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="1d480-129">**Version**</span></span> <br/> |<span data-ttu-id="1d480-130">**サポートされています**</span><span class="sxs-lookup"><span data-stu-id="1d480-130">**Supported**</span></span> <br/> |
|<span data-ttu-id="1d480-131">クイック実行</span><span class="sxs-lookup"><span data-stu-id="1d480-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="1d480-132">2016 年 12 月 6 日 - バージョン 1611 (ビルド 7571.2072) でリリースされた現在のチャネル</span><span class="sxs-lookup"><span data-stu-id="1d480-132">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="1d480-133">はい</span><span class="sxs-lookup"><span data-stu-id="1d480-133">Yes</span></span>  <br/> |
|<span data-ttu-id="1d480-134">クイック実行</span><span class="sxs-lookup"><span data-stu-id="1d480-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="1d480-135">2017 年 2 月 22日 - バージョン 1701 (ビルド 7766.2060) でリリースされた段階的提供チャネルの最初のリリース</span><span class="sxs-lookup"><span data-stu-id="1d480-135">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="1d480-136">はい</span><span class="sxs-lookup"><span data-stu-id="1d480-136">Yes</span></span>  <br/> |
|<span data-ttu-id="1d480-137">クイック実行</span><span class="sxs-lookup"><span data-stu-id="1d480-137">Click-to-Run</span></span>  <br/> |<span data-ttu-id="1d480-138">2017年 6 月 13日 - バージョン 1701 (ビルド 7766.2092) でリリースされた段階的提供チャネル</span><span class="sxs-lookup"><span data-stu-id="1d480-138">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="1d480-139">はい</span><span class="sxs-lookup"><span data-stu-id="1d480-139">Yes</span></span>  <br/> |
|<span data-ttu-id="1d480-140">MSI</span><span class="sxs-lookup"><span data-stu-id="1d480-140">MSI</span></span>  <br/> |<span data-ttu-id="1d480-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1d480-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="1d480-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="1d480-142">No</span></span>  <br/> |
|<span data-ttu-id="1d480-143">Mac</span><span class="sxs-lookup"><span data-stu-id="1d480-143">Mac</span></span>  <br/> |<span data-ttu-id="1d480-144">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1d480-144">Skype for Business</span></span>  <br/> |<span data-ttu-id="1d480-145">いいえ</span><span class="sxs-lookup"><span data-stu-id="1d480-145">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="1d480-146">受信呼び出し元 ID</span><span class="sxs-lookup"><span data-stu-id="1d480-146">Inbound caller ID</span></span>

<span data-ttu-id="1d480-147">電話システムは、その番号が Azure AD のユーザーに関連付けられている場合、外部電話番号の呼び出し ID を表示します。</span><span class="sxs-lookup"><span data-stu-id="1d480-147">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="1d480-148">電話番号が Azure ADではない場合は、電話会社が指定した表示名が表示されます (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="1d480-148">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="1d480-149">BlockIncomingCallerID 属性を使用すると、着信した PSTN 通話の発信者番号通知をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="1d480-149">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="1d480-150">この属性を設定することはできますが、ユーザー設定ページではエンド ユーザーには使用できません。</span><span class="sxs-lookup"><span data-stu-id="1d480-150">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="1d480-151">また、現在はオンラインの PSTN 接続のみで使用可能です。</span><span class="sxs-lookup"><span data-stu-id="1d480-151">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="1d480-152">発信側の発信者番号通知を設定するには、「[ユーザーの発信者番号通知を設定する](./set-the-caller-id-for-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d480-152">To set the outbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1d480-153">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1d480-153">Related topics</span></span>
[<span data-ttu-id="1d480-154">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="1d480-154">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="1d480-155">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="1d480-155">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="1d480-156">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="1d480-156">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="1d480-157">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="1d480-157">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="1d480-158">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="1d480-158">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
