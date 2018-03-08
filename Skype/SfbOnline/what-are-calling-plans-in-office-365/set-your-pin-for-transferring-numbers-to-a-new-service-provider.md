---
title: "新しいサービス プロバイダー番号に転送するための自分の PIN を設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.date: 01/22/2018
ms.topic: article
ms.assetid: f1defa5b-e49c-4d8c-a5f8-3f736201af5e
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
description: "または Skype の電話番号を別の電話サービス プロバイダーまたは航空会社の for Business Online ポートを転送するには、手動で PIN を設定する必要があります。PIN を設定した後、ポートを電話番号を要求したときに反映する必要があります。"
ms.openlocfilehash: 03e2e0ca76ea434e2458f1dec4a236996a19f7aa
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-your-pin-for-transferring-numbers-to-a-new-service-provider"></a><span data-ttu-id="2a77a-104">新しいサービス プロバイダー番号に転送するための自分の PIN を設定します。</span><span class="sxs-lookup"><span data-stu-id="2a77a-104">Set your PIN for transferring numbers to a new service provider</span></span>

<span data-ttu-id="2a77a-p102">転送または*アウト ポート*に電話番号 Skype から for Business Online を別の電話サービス プロバイダーまたは carrier、PIN を手動で設定する必要があります。PIN を設定した後、ポートを電話番号を要求したときに反映する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a77a-p102">To transfer or  *port out*  phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN. After you set the PIN, you need to include it when you request to port a phone number out.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2a77a-107">暗証番号 (pin) をポートが組織の場合は米国でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="2a77a-107">A port out PIN is only used for organizations in the United States.</span></span> 
  
<span data-ttu-id="2a77a-108">転送および/アウト電話番号の移植の詳細については、 [Office 365 への電話番号に転送](transfer-phone-numbers-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a77a-108">See [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) for more information about transferring and porting in/out phone numbers.</span></span>
  
<span data-ttu-id="2a77a-109">ここでは、具体的な情報この暗証番号 (pin) がわかっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a77a-109">Here is some specific information about this PIN you should know:</span></span>
  
- <span data-ttu-id="2a77a-110">PIN が設定されていない場合は、Skype for Business Online からの転送または電話番号をポートことはできません。</span><span class="sxs-lookup"><span data-stu-id="2a77a-110">If a PIN isn't set, you won't be able to transfer or port out phone numbers from Skype for Business Online.</span></span>
    
- <span data-ttu-id="2a77a-111">6 ~ 10 桁 (数値) に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2a77a-111">It can contain 6-10 digits (numbers).</span></span>
    
- <span data-ttu-id="2a77a-112">文字や特殊文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="2a77a-112">It can't contain letters or special characters.</span></span>
    
- <span data-ttu-id="2a77a-113">既定の PIN は空ですを削除するか空白に設定した場合のいずれかを配置すると、ことはできません。</span><span class="sxs-lookup"><span data-stu-id="2a77a-113">The default PIN is blank, but if you put one in, you can't remove or set it back to blank.</span></span>
    
- <span data-ttu-id="2a77a-114">更新したりいずれかに追加した後に PIN を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="2a77a-114">You can update or change the PIN after you put one in.</span></span>
    
## <a name="set-up-your-pin"></a><span data-ttu-id="2a77a-115">自分の PIN を設定します。</span><span class="sxs-lookup"><span data-stu-id="2a77a-115">Set up your PIN</span></span>

1. <span data-ttu-id="2a77a-116">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2a77a-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2a77a-117">**Office 365 管理センター**に移動 > **管理センター** > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="2a77a-117">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="2a77a-118">左のナビゲーションで [**音声**] を選びます > **ポート注文**します。</span><span class="sxs-lookup"><span data-stu-id="2a77a-118">In the left navigation, choose **Voice** > **Port orders**.</span></span>
    
4. <span data-ttu-id="2a77a-119">をクリックして**設定セットアップして、暗証番号 (pin) を管理する**転送、または別のサービスの航空会社の番号の移植に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a77a-119">Click **Set up and manage the PIN** that is used for transferring or porting numbers to another service carrier.</span></span>
    
5. <span data-ttu-id="2a77a-120">**設定暗証番号 (pin) を使用するポートを変更または**パネル、自分の PIN を入力および**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a77a-120">In the **Set or change your port out PIN** panel, enter your PIN and click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="2a77a-121">これよりも、その他の電話番号を取得する必要がある場合は、[ビジネス製品 - 管理者向けヘルプのサポートに連絡](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。</span><span class="sxs-lookup"><span data-stu-id="2a77a-121">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="2a77a-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2a77a-122">Related topics</span></span>
[<span data-ttu-id="2a77a-123">電話番号のよく寄せられる質問を転送します。</span><span class="sxs-lookup"><span data-stu-id="2a77a-123">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="2a77a-124">さまざまなプランの呼び出し用の電話番号</span><span class="sxs-lookup"><span data-stu-id="2a77a-124">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="2a77a-125">組織の電話番号を管理します。</span><span class="sxs-lookup"><span data-stu-id="2a77a-125">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="2a77a-126">緊急の呼び出し元の条項および条件</span><span class="sxs-lookup"><span data-stu-id="2a77a-126">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="2a77a-127">Skype for Business Online: 緊急発信免責事項のラベル</span><span class="sxs-lookup"><span data-stu-id="2a77a-127">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)


  

