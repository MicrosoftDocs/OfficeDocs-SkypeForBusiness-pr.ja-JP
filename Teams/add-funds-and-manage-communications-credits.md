---
title: 資金を追加してコミュニケーション クレジットを管理する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: 691c9301-1f66-41fe-9b2c-ca24ae987463
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365E_SFBVoiceCredit
- O365E_SFBVoiceCreditAether
- O365M_SFBVoiceCredit
- O365M_SFBVoiceCreditAether
- O365P_SFBVoiceCreditAether
- O365E_SFBVoiceCreditAether
- O365P_SFBVoiceCredit
- O365P_SFBVoiceCreditAether
ms.custom:
- Licensing
description: 'Skype for Business サービスの通信クレジット (PSTN 追加機能プラン) に対する支払い方法と、継続的な電話システムへのアクセスをユーザーに許可するプランについて説明します。 '
ms.openlocfilehash: 93fb828f434c07b32852711772b6c16613415749
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278321"
---
# <a name="add-funds-and-manage-communications-credits"></a><span data-ttu-id="f0ce0-103">資金を追加してコミュニケーション クレジットを管理する</span><span class="sxs-lookup"><span data-stu-id="f0ce0-103">Add funds and manage Communications Credits</span></span>

<span data-ttu-id="f0ce0-104">通信クレジットは、Office 365 で電話システムと通話プランの支払いに便利な手段です。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-104">Communications Credits are a convenient way to pay for Phone System and Calling Plans in Office 365.</span></span> <span data-ttu-id="f0ce0-105">通信クレジットを使用すると、ユーザーとユーザーがキャッチされずに、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-105">Communication Credits helps ensure that you and your users are never caught without being able to:</span></span>
  
- <span data-ttu-id="f0ce0-106">無料のダイヤルイン電話番号を使用して、電話会議にダイヤルインします。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-106">Dial in to Audio Conferencing meetings using toll-free dial-in phone numbers.</span></span>
    
- <span data-ttu-id="f0ce0-107">電話会議からダイヤルアウトして、世界中のどこからでも他のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-107">Dial out from an Audio Conferencing meeting to add someone else from anywhere in the world.</span></span>
    
- <span data-ttu-id="f0ce0-108">Skype for Business または Microsoft Teams アプリがインストールされている状態で、電話会議から携帯電話にダイヤルアウトします。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-108">Dial out from an Audio Conferencing meeting to your mobile phone with the Skype for Business or Microsoft Teams app installed.</span></span>
    
- <span data-ttu-id="f0ce0-109">**国内通話プラン**を利用している場合は、任意の国際電話番号にダイヤルできます。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-109">Dial any international phone number when you have a **Domestic Calling Plan**.</span></span>
    
- <span data-ttu-id="f0ce0-110">月額プランの月額プランがなくなった場合は、1分あたりのダイヤルアウトと料金がかかります。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-110">Dial out and pay per minute once you have exhausted your monthly minute allotment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f0ce0-111">料金と料金について知りたい場合は、「[通話プラン](https://go.microsoft.com/fwlink/p/?LinkId=799523)」ページで「料金表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-111">If you're wondering how much it is and the rates, see the rates table on the [Calling Plans](https://go.microsoft.com/fwlink/p/?LinkId=799523) page.</span></span>
  
<span data-ttu-id="f0ce0-112">管理者は、手動で資金を追加するか、自動再充電を設定すること\*\*\*\* ができます。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-112">As admin, you can add funds manually or you can set up auto-recharge, which we **recommend**.</span></span>
  
<span data-ttu-id="f0ce0-p102">自動再チャージでは、設定した金額を下回ると、自動的に最高額まで残高が追加されます。自動再チャージの使用をお勧めします。これにより、利用可能残高の手動による追加を忘れないようにする必要がなくなります。利用可能残高が設定した金額を下回ると、自動的にチャージされます。自動再チャージを選択していないと、利用可能残高がゼロを下回ってしまうことがあります。その時点で、管理者やユーザーは無料通話や国際通話を発信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-p102">Auto-recharge automatically tops off your balance when it falls below the trigger amount you set. We recommend using auto-recharge so you don't have to remember to add funds manually. When your balance hits the trigger amount, funds are added automatically. If you don't choose auto-recharge, you run the risk of your balance falling below zero. At that point, you and your users won't be able to make toll-free calls or international calls.</span></span>
  
<span data-ttu-id="f0ce0-118">支払いオプションはいつでも更新できます。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-118">You can update your payment options at any time.</span></span> <span data-ttu-id="f0ce0-119">[**サブスクリプション**] ページで、[**通信クレジット**] を選択して、更新を行います。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-119">On the **Subscriptions** page, select **Communications Credits**, and make your updates.</span></span>
  
<span data-ttu-id="f0ce0-120">サービスが使用されると、Microsoft の公開料金でクレジットが適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-120">Funds will be applied only to Communications Credits at Microsoft's published rates when the services are used.</span></span> <span data-ttu-id="f0ce0-121">12ヶ月12日以内に使用していなかった資金は、有効期限が切れて forfeited されます。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-121">Any funds not used within twelve (12) months of the purchase date will expire and be forfeited.</span></span>
  
> [!TIP]
> <span data-ttu-id="f0ce0-122">自動再充電の際に、自動再充電 (クレジットカードの有効期限が切れた場合など)、または残高がゼロ未満の場合は、メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-122">We'll send you email notifications when funds are added via auto-recharge, when auto-recharge fails (for example, when a credit card expires), and when your balance falls below zero.</span></span> 
  
<span data-ttu-id="f0ce0-123">詳細については、「[通信クレジットとは](what-are-communications-credits.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-123">For more information, see [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="f0ce0-124">プランと価格の詳細情報</span><span class="sxs-lookup"><span data-stu-id="f0ce0-124">Want to know about plans and pricing?</span></span>

<span data-ttu-id="f0ce0-125">次のいずれかのリンクにアクセスすると、プランと価格を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-125">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="f0ce0-126">通話プラン</span><span class="sxs-lookup"><span data-stu-id="f0ce0-126">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="f0ce0-127">電話会議プラン</span><span class="sxs-lookup"><span data-stu-id="f0ce0-127">Audio Conferencing plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="f0ce0-128">電話システムプラン</span><span class="sxs-lookup"><span data-stu-id="f0ce0-128">Phone System plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="f0ce0-129">[Microsoft 365 管理センターにサインイン](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)して、[サブスクリプションの\*\*\*\* > \*\*\*\* > **追加**] サブスクリプションに移動して、情報を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-129">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="f0ce0-130">各機能に必要なライセンスの表を表示するには、「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0ce0-130">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f0ce0-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f0ce0-131">Related topics</span></span>

- [<span data-ttu-id="f0ce0-132">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="f0ce0-132">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="f0ce0-133">クラウド ボイスメールのセットアップ - Admin ヘルプ</span><span class="sxs-lookup"><span data-stu-id="f0ce0-133">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="f0ce0-134">[呼び出しプランの設定](set-up-calling-plans.md) および [Office 365 の呼び出しプラン](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f0ce0-134">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>
        
 
 
