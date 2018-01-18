---
title: "番号を新しいサービス プロバイダーに転送するための暗証番号を設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: f1defa5b-e49c-4d8c-a5f8-3f736201af5e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "転送または別の電話サービスプロバイダーまたは通信業者にオンライン ビジネスのポートの Skype からの電話番号、PIN を手動で設定する必要があります。 PIN を設定した後にポートの電話番号を要求するときに含めることを必要があります。"
ms.openlocfilehash: a45d88c58add21544de2a2e92e8a32e5cafce7b5
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="set-your-pin-for-transferring-numbers-to-a-new-service-provider"></a><span data-ttu-id="0c9f3-104">番号を新しいサービス プロバイダーに転送するための暗証番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-104">Set your PIN for transferring numbers to a new service provider</span></span>

<span data-ttu-id="0c9f3-105">転送または*out ポート*に電話番号 Skype からオンライン ビジネスの別のキャリアまたは電話サービス プロバイダーに PIN を手動で設定する必要がありますが。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-105">To transfer or  *port out*  phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN.</span></span> <span data-ttu-id="0c9f3-106">PIN を設定した後にポートの電話番号を要求するときに含めることを必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-106">After you set the PIN, you need to include it when you request to port a phone number out.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0c9f3-107">ピンをポートは、米国内の組織においてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-107">A port out PIN is only used for organizations in the United States.</span></span> 
  
<span data-ttu-id="0c9f3-108">転送して、入力/出力の電話番号を移植の詳細については、 [Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-108">See [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) for more information about transferring and porting in/out phone numbers.</span></span>
  
<span data-ttu-id="0c9f3-109">知っておくべきこの暗証番号 (pin) に関する特定情報を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-109">Here is some specific information about this PIN you should know:</span></span>
  
- <span data-ttu-id="0c9f3-110">PIN が設定されていない場合は、ビジネス オンラインの Skype からや電話番号のポートを転送することはできません。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-110">If a PIN isn't set, you won't be able to transfer or port out phone numbers from Skype for Business Online.</span></span>
    
- <span data-ttu-id="0c9f3-111">6 ~ 10 桁 (数値) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-111">It can contain 6-10 digits (numbers).</span></span>
    
- <span data-ttu-id="0c9f3-112">文字または特殊文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-112">It can't contain letters or special characters.</span></span>
    
- <span data-ttu-id="0c9f3-113">既定の暗証番号 (pin) 空白ですのいずれかを配置すると、削除または、空白に設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-113">The default PIN is blank, but if you put one in, you can't remove or set it back to blank.</span></span>
    
- <span data-ttu-id="0c9f3-114">更新したりいずれかを挿入した後に、暗証番号 (pin) を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-114">You can update or change the PIN after you put one in.</span></span>
    
## <a name="set-up-your-pin"></a><span data-ttu-id="0c9f3-115">暗証番号 (pin) を設定します</span><span class="sxs-lookup"><span data-stu-id="0c9f3-115">Set up your PIN</span></span>

1. <span data-ttu-id="0c9f3-116">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0c9f3-117">**Office 365 管理センター**を参照して > **管理センター** > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-117">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0c9f3-118">左側のナビゲーションの**音声**を選択します > **ポート注文**します。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-118">In the left navigation, choose **Voice** > **Port orders**.</span></span>
    
4. <span data-ttu-id="0c9f3-119">をクリックして**を設定し、暗証番号 (pin) を管理する**を転送するか、別のサービス キャリアに番号を移植するに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-119">Click **Set up and manage the PIN** that is used for transferring or porting numbers to another service carrier.</span></span>
    
5. <span data-ttu-id="0c9f3-120">**を設定または暗証番号 (pin) を使用するポートを変更する**パネル、暗証番号を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-120">In the **Set or change your port out PIN** panel, enter your PIN and click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="0c9f3-121">これよりも、他の電話番号を取得する場合は、[ビジネス製品の管理のヘルプのサポートに連絡](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-121">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="0c9f3-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0c9f3-122">Related topics</span></span>
[<span data-ttu-id="0c9f3-123">電話番号のよく寄せられる質問を転送します。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-123">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="0c9f3-124">さまざまな種類の計画を呼び出すための電話番号</span><span class="sxs-lookup"><span data-stu-id="0c9f3-124">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="0c9f3-125">組織の電話番号を管理します。</span><span class="sxs-lookup"><span data-stu-id="0c9f3-125">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="0c9f3-126">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="0c9f3-126">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="0c9f3-127">Skype for Business Online: 緊急通話の免責事項ラベル</span><span class="sxs-lookup"><span data-stu-id="0c9f3-127">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)


  

