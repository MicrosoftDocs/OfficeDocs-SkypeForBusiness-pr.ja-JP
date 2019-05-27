---
title: 番号を新しいサービス プロバイダーに移行するための PIN を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: f1defa5b-e49c-4d8c-a5f8-3f736201af5e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 電話番号を Skype for Business Online から別の電話サービス プロバイダーまたは通信業者に転送または移行するには、PIN を手動で設定する必要があります。 PIN を設定した後、電話番号を移行するときにその PIN を含める必要があります。
ms.openlocfilehash: 5daea877e17582ecb85bc8d7e13db5001dcdbfc6
ms.sourcegitcommit: 4bb900228cc55e0cbbce8c5b74b7de8df5a2288f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408511"
---
# <a name="set-your-pin-for-transferring-numbers-to-a-new-service-provider"></a><span data-ttu-id="4dfcb-104">番号を新しいサービス プロバイダーに移行するための PIN を設定する</span><span class="sxs-lookup"><span data-stu-id="4dfcb-104">Set your PIN for transferring numbers to a new service provider</span></span>

<span data-ttu-id="4dfcb-105">電話番号を Skype for Business Online から別の電話サービス プロバイダーまたは通信業者に転送または 移行する には、PIN を手動で設定する必要があります。\*\*</span><span class="sxs-lookup"><span data-stu-id="4dfcb-105">To transfer or  *port out*  phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN.</span></span> <span data-ttu-id="4dfcb-106">PIN を設定した後、電話番号を移行するときにその PIN を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-106">After you set the PIN, you need to include it when you request to port a phone number out.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4dfcb-107">移行した PIN は、米国内の組織においてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-107">A port out PIN is only used for organizations in the United States.</span></span> 
  
<span data-ttu-id="4dfcb-108">電話番号の転送と移行の詳細については、「[Office 365 に電話番号を転送する](/microsoftteams/transfer-phone-numbers-to-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-108">See [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) for more information about transferring and porting in/out phone numbers.</span></span>
  
<span data-ttu-id="4dfcb-109">この PIN に関して知っておくべき特定の情報を以下に記載します。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-109">Here is some specific information about this PIN you should know:</span></span>
  
- <span data-ttu-id="4dfcb-110">PIN が設定されていない場合、Skype for Business Online から電話番号を転送または移行できません。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-110">If a PIN isn't set, you won't be able to transfer or port out phone numbers from Skype for Business Online.</span></span>
    
- <span data-ttu-id="4dfcb-111">PIN は、6 - 10 桁 (数字) で指定できます。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-111">It can contain 6-10 digits (numbers).</span></span>
    
- <span data-ttu-id="4dfcb-112">文字または特殊文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-112">It can't contain letters or special characters.</span></span>
    
- <span data-ttu-id="4dfcb-113">既定の PIN は空白となっていますが、数字を入力すると、その数字を削除することも、空白に戻すこともできません。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-113">The default PIN is blank, but if you put one in, you can't remove or set it back to blank.</span></span>
    
- <span data-ttu-id="4dfcb-114">PIN の入力後に、PIN の更新または変更が行えます。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-114">You can update or change the PIN after you put one in.</span></span>
    
## <a name="set-up-your-pin"></a><span data-ttu-id="4dfcb-115">PIN の設定</span><span class="sxs-lookup"><span data-stu-id="4dfcb-115">Set up your PIN</span></span>

<span data-ttu-id="4dfcb-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="4dfcb-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="4dfcb-117">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="4dfcb-118">**Microsoft Teams 管理センター** > の**従来のポータル**に移動します。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-118">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="4dfcb-119">左側のナビゲーションで、[**音声** > **ポートの注文**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-119">In the left navigation, choose **Voice** > **Port orders**.</span></span>
    
4. <span data-ttu-id="4dfcb-120">別の通信業者に転送または移行する番号に使われる **[PIN の設定と管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-120">Click **Set up and manage the PIN** that is used for transferring or porting numbers to another service carrier.</span></span>
    
5. <span data-ttu-id="4dfcb-121">[**移行する PIN の設定または変更**] パネルで、PIN を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-121">In the **Set or change your port out PIN** panel, enter your PIN and click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="4dfcb-122">さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4dfcb-122">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4dfcb-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4dfcb-123">Related topics</span></span>
[<span data-ttu-id="4dfcb-124">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="4dfcb-124">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="4dfcb-125">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="4dfcb-125">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

<span data-ttu-id="4dfcb-126">[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="4dfcb-126">[Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization)</span></span>

[<span data-ttu-id="4dfcb-127">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="4dfcb-127">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="4dfcb-128">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="4dfcb-128">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
  

