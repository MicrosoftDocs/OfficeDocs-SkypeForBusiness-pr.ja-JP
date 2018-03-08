---
title: "発信者の使い方、組織内で"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "発信者番号は、電話システムでユーザーの通話を着信および発信 CallingLineIdentity と呼ばれるポリシーを使用して制御できます。"
ms.openlocfilehash: f87718858507405e54643575825b264c6c1cbea1
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="b1ba1-103">発信者の使い方、組織内で</span><span class="sxs-lookup"><span data-stu-id="b1ba1-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="b1ba1-104">発信者番号は、電話システムでユーザーの通話を着信および発信 CallingLineIdentity と呼ばれるポリシーを使用して制御できます。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="b1ba1-105">発信者の機能は PSTN への接続に関係なく、すべての電話システムでユーザーに利用できます。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="b1ba1-106">オンライン PSTN への接続</span><span class="sxs-lookup"><span data-stu-id="b1ba1-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="b1ba1-107">Skype for Business クラウド コネクタのエディションとオンプレミス PSTN への接続 (クラウド コネクタ Edition 1.4.2 を必要と以降)</span><span class="sxs-lookup"><span data-stu-id="b1ba1-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="b1ba1-108">Skype for Business Server が (Business Server 2015 CU5 とだけでなく、Skype が必要) とオンプレミス PSTN への接続</span><span class="sxs-lookup"><span data-stu-id="b1ba1-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="b1ba1-109">このポリシーは Skype for Business 2015 サーバーで利用できません。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="b1ba1-110">外部の発信者番号</span><span class="sxs-lookup"><span data-stu-id="b1ba1-110">Outbound caller ID</span></span>

<span data-ttu-id="b1ba1-111">送信 PSTN 発信者の利用可能なは 3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="b1ba1-112">既定では、ユーザーに割り当てられている電話番号。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="b1ba1-p101">*サービス*として分類されている電話番号との電話の Office 365 のプランの呼び出し、*フリー ダイヤル*番号を在庫に番号します。通常は組織の自動応答または着信キューに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="b1ba1-115">匿名に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-115">Set to anonymous.</span></span>
    
<span data-ttu-id="b1ba1-116">ただし、発信発信者のこれらの種類の電話番号を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="b1ba1-117">任意の電話番号で電話番号を呼び出すプラン*ユーザー*として分類されている番号の在庫</span><span class="sxs-lookup"><span data-stu-id="b1ba1-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="b1ba1-118">Skype for Business Server 内部設置型の電話番号</span><span class="sxs-lookup"><span data-stu-id="b1ba1-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="b1ba1-119">外部の発信者番号を設定するには、[ユーザーの発信者番号を設定する](set-the-caller-id-for-a-user.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="b1ba1-120">外部の発信者番号のエンド ユーザー コントロール</span><span class="sxs-lookup"><span data-stu-id="b1ba1-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="b1ba1-p102">EnableUserOverride 属性により、**匿名**の発信者番号の設定を変更するのには、1 つまたは複数のユーザー。これは、CallingLineIdentity ポリシー LineURI または代替のいずれかの CallingIDSubstitute パラメーターが設定されている場合にのみ利用できます。EnableUserOverride の既定値は、False です。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="b1ba1-124">エンドユーザーは、**着信の転送の設定**] タブの [で Skype for Business デスクトップ クライアントを使用して、**匿名**の発信者番号を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-124">Your end users can set their caller ID to **Anonymous** by using the **Call Forward Settings** tab in the Skype for Business desktop client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="b1ba1-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b1ba1-125">**Windows**</span></span> <br/> |<span data-ttu-id="b1ba1-126">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="b1ba1-126">**Version**</span></span> <br/> |<span data-ttu-id="b1ba1-127">**サポートされています。**</span><span class="sxs-lookup"><span data-stu-id="b1ba1-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="b1ba1-128">クイック実行</span><span class="sxs-lookup"><span data-stu-id="b1ba1-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="b1ba1-129">現在のチャネル リリース 2016 年 12 月 6 日の [バージョン 1611 (ビルド 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="b1ba1-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="b1ba1-130">○</span><span class="sxs-lookup"><span data-stu-id="b1ba1-130">Yes</span></span>  <br/> |
|<span data-ttu-id="b1ba1-131">クイック実行</span><span class="sxs-lookup"><span data-stu-id="b1ba1-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="b1ba1-132">最初のリリースでは、延期チャンネルのリリース 2017 年 2 月 22日] - [バージョン 1701 (ビルド 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="b1ba1-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="b1ba1-133">○</span><span class="sxs-lookup"><span data-stu-id="b1ba1-133">Yes</span></span>  <br/> |
|<span data-ttu-id="b1ba1-134">クイック実行</span><span class="sxs-lookup"><span data-stu-id="b1ba1-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="b1ba1-135">チャンネルを 2017 年 6 月 13日 - バージョン 1701 (ビルド 7766.2092) にリリースの保留</span><span class="sxs-lookup"><span data-stu-id="b1ba1-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="b1ba1-136">○</span><span class="sxs-lookup"><span data-stu-id="b1ba1-136">Yes</span></span>  <br/> |
|<span data-ttu-id="b1ba1-137">MSI</span><span class="sxs-lookup"><span data-stu-id="b1ba1-137">MSI</span></span>  <br/> |<span data-ttu-id="b1ba1-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b1ba1-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="b1ba1-139">×</span><span class="sxs-lookup"><span data-stu-id="b1ba1-139">No</span></span>  <br/> |
|<span data-ttu-id="b1ba1-140">Mac</span><span class="sxs-lookup"><span data-stu-id="b1ba1-140">Mac</span></span>  <br/> |<span data-ttu-id="b1ba1-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b1ba1-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="b1ba1-142">×</span><span class="sxs-lookup"><span data-stu-id="b1ba1-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="b1ba1-143">着信の発信者番号</span><span class="sxs-lookup"><span data-stu-id="b1ba1-143">Inbound Caller ID</span></span>

<span data-ttu-id="b1ba1-p103">BlockIncomingCallerID 属性は、PSTN 通話を受信した発信者番号をブロックすることができます。この属性を設定することができますが、ユーザー設定のページで、エンドユーザーには使用できません。現在、オンライン PSTN への接続でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-p103">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls. You can set this attribute, but it isn't available to your end users on the user settings page. And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="b1ba1-147">外部の発信者番号を設定するには、[ユーザーの発信者番号を設定する](set-the-caller-id-for-a-user.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b1ba1-148">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b1ba1-148">Related topics</span></span>
[<span data-ttu-id="b1ba1-149">電話番号のよく寄せられる質問を転送します。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-149">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="b1ba1-150">さまざまなプランの呼び出し用の電話番号</span><span class="sxs-lookup"><span data-stu-id="b1ba1-150">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="b1ba1-151">組織の電話番号を管理します。</span><span class="sxs-lookup"><span data-stu-id="b1ba1-151">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="b1ba1-152">緊急の呼び出し元の条項および条件</span><span class="sxs-lookup"><span data-stu-id="b1ba1-152">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="b1ba1-153">Skype for Business Online: 緊急発信免責事項のラベル</span><span class="sxs-lookup"><span data-stu-id="b1ba1-153">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)