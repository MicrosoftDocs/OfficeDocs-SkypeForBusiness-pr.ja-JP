---
title: 呼び出し元 ID 利用する方法、組織内
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: CallingLineIdentity と呼ばれるポリシーを使用して、電話システムのユーザーの受信と送信の両方の呼び出しに呼び出し元の ID を制御できます。
ms.openlocfilehash: b242249ef42781fa84e87a2b5eee5ba823eb200b
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="897e3-103">呼び出し元 ID 利用する方法、組織内</span><span class="sxs-lookup"><span data-stu-id="897e3-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="897e3-104">CallingLineIdentity と呼ばれるポリシーを使用して、電話システムのユーザーの受信と送信の両方の呼び出しに呼び出し元の ID を制御できます。</span><span class="sxs-lookup"><span data-stu-id="897e3-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="897e3-105">発信者番号機能は、PSTN への接続に関係なくすべての電話システムのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="897e3-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="897e3-106">オンラインの PSTN への接続</span><span class="sxs-lookup"><span data-stu-id="897e3-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="897e3-107">ビジネス クラウド コネクタ ・ エディションの Skype での PSTN への接続を設置 (クラウド コネクタ版 1.4.2 が必要ですし、以降も)</span><span class="sxs-lookup"><span data-stu-id="897e3-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="897e3-108">(内外のビジネス サーバー 2015 CU5 Skype が必要です) ビジネス サーバーの Skype での PSTN への接続を設置</span><span class="sxs-lookup"><span data-stu-id="897e3-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="897e3-109">このポリシーは、ビジネス 2015年サーバーの Skype では使用できません。</span><span class="sxs-lookup"><span data-stu-id="897e3-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="897e3-110">発信の呼び出し元の ID</span><span class="sxs-lookup"><span data-stu-id="897e3-110">Outbound caller ID</span></span>

<span data-ttu-id="897e3-111">PSTN 発信者番号通知の送信に使用できるオプションは次の 3 つです。</span><span class="sxs-lookup"><span data-stu-id="897e3-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="897e3-112">既定では、ユーザーに割り当てられている電話番号です。</span><span class="sxs-lookup"><span data-stu-id="897e3-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="897e3-113">*サービス*として分類されている電話番号と Office 365 の電話の計画を呼び出すので*フリー ダイヤル*の番号は、在庫を番号します。</span><span class="sxs-lookup"><span data-stu-id="897e3-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="897e3-114">これは通常、組織の自動アテンダントまたは呼び出しのキューに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="897e3-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="897e3-115">匿名に設定します。</span><span class="sxs-lookup"><span data-stu-id="897e3-115">Set to anonymous.</span></span>
    
<span data-ttu-id="897e3-116">ただし、発信呼び出し元 ID のこれらの種類の電話番号を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="897e3-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="897e3-117">計画を呼び出す電話番号の*ユーザー*として分類されている任意の電話番号の番号の在庫</span><span class="sxs-lookup"><span data-stu-id="897e3-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="897e3-118">Skype のビジネス サーバー設置型の電話番号</span><span class="sxs-lookup"><span data-stu-id="897e3-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="897e3-119">発信の呼び出し元の ID を設定するには、[ユーザーの発信者番号の設定](set-the-caller-id-for-a-user.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="897e3-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="897e3-120">発信呼び出し元 ID のユーザー コントロール</span><span class="sxs-lookup"><span data-stu-id="897e3-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="897e3-121">EnableUserOverride 属性は、**匿名**の発信者番号通知設定を変更するのには 1 つまたは複数のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="897e3-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="897e3-122">LineURI または代替のいずれかの CallingIDSubstitute パラメーターを持つ CallingLineIdentity ポリシーが構成されている場合こののみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="897e3-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="897e3-123">EnableUserOverride の既定値は、False です。</span><span class="sxs-lookup"><span data-stu-id="897e3-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="897e3-124">エンド ・ ユーザーは、Skype のビジネス デスクトップ クライアントの**呼び出しの転送の設定**] タブを使用して、**匿名**の呼び出し元の ID を設定できます。</span><span class="sxs-lookup"><span data-stu-id="897e3-124">Your end users can set their caller ID to **Anonymous** by using the **Call Forward Settings** tab in the Skype for Business desktop client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="897e3-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="897e3-125">**Windows**</span></span> <br/> |<span data-ttu-id="897e3-126">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="897e3-126">**Version**</span></span> <br/> |<span data-ttu-id="897e3-127">**サポート**</span><span class="sxs-lookup"><span data-stu-id="897e3-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="897e3-128">クイック実行</span><span class="sxs-lookup"><span data-stu-id="897e3-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="897e3-129">2016 年 12 月 6 日 - 1611 (ビルド 7571.2072) のバージョンでリリースされた現在のチャネル</span><span class="sxs-lookup"><span data-stu-id="897e3-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="897e3-130">あり</span><span class="sxs-lookup"><span data-stu-id="897e3-130">Yes</span></span>  <br/> |
|<span data-ttu-id="897e3-131">クイック実行</span><span class="sxs-lookup"><span data-stu-id="897e3-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="897e3-132">2017 年 2 月 22日 - 1701 (ビルド 7766.2060) のバージョンでリリースされた延期のチャネルの最初のリリース</span><span class="sxs-lookup"><span data-stu-id="897e3-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="897e3-133">あり</span><span class="sxs-lookup"><span data-stu-id="897e3-133">Yes</span></span>  <br/> |
|<span data-ttu-id="897e3-134">クイック実行</span><span class="sxs-lookup"><span data-stu-id="897e3-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="897e3-135">チャネルは、2017 年 6 月 13日-1701 (ビルド 7766.2092) のバージョンのリリースを延期</span><span class="sxs-lookup"><span data-stu-id="897e3-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="897e3-136">はい</span><span class="sxs-lookup"><span data-stu-id="897e3-136">Yes</span></span>  <br/> |
|<span data-ttu-id="897e3-137">MSI</span><span class="sxs-lookup"><span data-stu-id="897e3-137">MSI</span></span>  <br/> |<span data-ttu-id="897e3-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="897e3-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="897e3-139">なし</span><span class="sxs-lookup"><span data-stu-id="897e3-139">No</span></span>  <br/> |
|<span data-ttu-id="897e3-140">Mac</span><span class="sxs-lookup"><span data-stu-id="897e3-140">Mac</span></span>  <br/> |<span data-ttu-id="897e3-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="897e3-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="897e3-142">なし</span><span class="sxs-lookup"><span data-stu-id="897e3-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="897e3-143">発信者番号通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="897e3-143">Inbound Caller ID</span></span>

<span data-ttu-id="897e3-144">BlockIncomingCallerID 属性では、PSTN 通話の着信の呼び出し元 ID をブロックします。</span><span class="sxs-lookup"><span data-stu-id="897e3-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="897e3-145">この属性を設定することができますが、ユーザー設定] ページで、エンド ・ ユーザーには使用できません。</span><span class="sxs-lookup"><span data-stu-id="897e3-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="897e3-146">オンラインの PSTN への接続のみで現在使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="897e3-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="897e3-147">発信の呼び出し元の ID を設定するには、[ユーザーの発信者番号の設定](set-the-caller-id-for-a-user.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="897e3-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="897e3-148">[米国 (無料の電話番号) 用の承認状 (LOA) (v.2.0)](http://download.microsoft.com/download/F/0/1/F01AE714-0F3C-4D9D-B41A-DFD180EC1622/Letter of Authorization %28LOA%29 for the U.S. (Toll Free numbers) (v.3.1) (en-US).pdf)</span><span class="sxs-lookup"><span data-stu-id="897e3-148">Related topics</span></span>
<span data-ttu-id="897e3-149">電話番号の管理フォームのダウンロード</span><span class="sxs-lookup"><span data-stu-id="897e3-149">[Transferring phone numbers common questions](transferring-phone-numbers-common-questions.md)</span></span>

[<span data-ttu-id="897e3-150">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="897e3-150">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

<span data-ttu-id="897e3-151">[[Skype for Business 新しい電話番号の申請](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="897e3-151">[Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span></span>

[<span data-ttu-id="897e3-152">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="897e3-152">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="897e3-153">Skype for Business Online: 緊急通話の免責事項ラベル</span><span class="sxs-lookup"><span data-stu-id="897e3-153">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 