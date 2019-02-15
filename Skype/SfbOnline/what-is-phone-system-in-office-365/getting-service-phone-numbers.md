---
title: サービスの電話番号の取得
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
- Phone System
description: In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.
ms.openlocfilehash: e1f4020e7062066451eebd626832da8d4a633069
ms.sourcegitcommit: 60e8365281ec6d780f1b2439bedef0bd71f002d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "30048916"
---
# <a name="getting-service-phone-numbers"></a><span data-ttu-id="56ba0-104">サービスの電話番号の取得</span><span class="sxs-lookup"><span data-stu-id="56ba0-104">Getting service phone numbers</span></span>

<span data-ttu-id="56ba0-p102">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span><span class="sxs-lookup"><span data-stu-id="56ba0-p102">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56ba0-p103">Office 365 Communications Credits must be set up first in order to acquire toll-free numbers. See [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="56ba0-p103">Office 365 Communications Credits must be set up first in order to acquire toll-free numbers. See [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span> 
  
<span data-ttu-id="56ba0-110">使用できるようにする Skype でビジネスおよびマイクロソフトのチームには、サービス番号を取得する 2 とおりの方法があります。</span><span class="sxs-lookup"><span data-stu-id="56ba0-110">You have two ways of getting service numbers so you can use them with Skype for Business and Microsoft Teams:</span></span>
  
- <span data-ttu-id="56ba0-111">Office 365 から新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="56ba0-111">Get new numbers from Office 365.</span></span>
    
- <span data-ttu-id="56ba0-112">ポートまたはサービス プロバイダーまたは電話のキャリアから、既存の番号を Office 365 に転送します。</span><span class="sxs-lookup"><span data-stu-id="56ba0-112">Port or transfer your existing numbers from your service provider or phone carrier to Office 365.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="56ba0-113">サービス番号を転送するときは、同時呼び出し元の容量が大きくと見なされ、正しく構成されていることを確認するのには[Microsoft のサポート](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)を問い合わせることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="56ba0-113">When you transfer your service numbers, it is highly recommended that you contact [Microsoft support](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) to ensure that the higher concurrent calling capacity is considered and configured correctly.</span></span>
  
## <a name="get-new-service-numbers"></a><span data-ttu-id="56ba0-114">新しいサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="56ba0-114">Get new service numbers</span></span>

<span data-ttu-id="56ba0-115">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="56ba0-115">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="56ba0-116">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="56ba0-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="56ba0-117">**管理センター**を参照して > **のチームと Skype** > **Skype レガシ管理**します。</span><span class="sxs-lookup"><span data-stu-id="56ba0-117">Go to the **Admin center** > **Teams and Skype** > **Skype Legacy Admin**.</span></span>
    
3. <span data-ttu-id="56ba0-118">左側のナビゲーションでは、**音声**に移動 > **電話番号** > **新しい番号を追加**し、**新しいサービスの番号**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56ba0-118">In the left navigation go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>
    
    > [!IMPORTANT] 
    > <span data-ttu-id="56ba0-119">ビジネス管理センターの Skype では、左側のナビゲーションの**音声**オプションを表示するため、まず**E5 のエンタープライズ ライセンス**を少なくとも 1 つ、1 つの**電話システム**のアドオン ライセンスまたはアドオンのライセンスが 1 つの**電話会議**を購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56ba0-119">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="56ba0-120">**新しいサービス番号の追加**] ページで、次の手順を選択します。</span><span class="sxs-lookup"><span data-stu-id="56ba0-120">On the **Add new service numbers** page, choose the following:</span></span>
    
   - <span data-ttu-id="56ba0-121">**国/地域**</span><span class="sxs-lookup"><span data-stu-id="56ba0-121">**Country/Region**</span></span>
    
   - <span data-ttu-id="56ba0-122">**都道府県/地域**</span><span class="sxs-lookup"><span data-stu-id="56ba0-122">**State/Region**</span></span>
    
   - <span data-ttu-id="56ba0-123">**市区町村**</span><span class="sxs-lookup"><span data-stu-id="56ba0-123">**City**</span></span>
    
5. <span data-ttu-id="56ba0-p104">Under **Quantity**, enter the number of phone numbers that you want for your organization and click **Add** to create a reservation. You have 10 minutes to select your phone numbers; if you take more than 10 minutes, the phone numbers will be returned to the pool of phone numbers.</span><span class="sxs-lookup"><span data-stu-id="56ba0-p104">Under **Quantity**, enter the number of phone numbers that you want for your organization and click **Add** to create a reservation. You have 10 minutes to select your phone numbers; if you take more than 10 minutes, the phone numbers will be returned to the pool of phone numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="56ba0-p105">You can see the number of phone numbers, which is based on the number of licenses, listed next to **Total Service numbers your can acquire**. For details, see [How many phone numbers can you get?](/microsoftteams/how-many-phone-numbers-can-you-get)</span><span class="sxs-lookup"><span data-stu-id="56ba0-p105">You can see the number of phone numbers, which is based on the number of licenses, listed next to **Total Service numbers your can acquire**. For details, see [How many phone numbers can you get?](/microsoftteams/how-many-phone-numbers-can-you-get)</span></span>
  
6. <span data-ttu-id="56ba0-p106">You can click **Show numbers** to see the full list of phone numbers. This is helpful if you don't want to select a specific phone number in the list.</span><span class="sxs-lookup"><span data-stu-id="56ba0-p106">You can click **Show numbers** to see the full list of phone numbers. This is helpful if you don't want to select a specific phone number in the list.</span></span>
    
7. <span data-ttu-id="56ba0-130">目的の電話番号を選んでから、[ **番号の入手**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="56ba0-130">Select the phone numbers you want, and then click **Acquire numbers**.</span></span>
    
### <a name="assign-service-numbers"></a><span data-ttu-id="56ba0-131">サービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="56ba0-131">Assign service numbers</span></span>

<span data-ttu-id="56ba0-p107">Once you have your service numbers, they can then be assigned to an audio conferencing bridge. To do this, see [Change the toll or toll free numbers on your Audio Conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="56ba0-p107">Once you have your service numbers, they can then be assigned to an audio conferencing bridge. To do this, see [Change the toll or toll free numbers on your Audio Conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>
  
### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="56ba0-134">既存のサービス番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="56ba0-134">Port or transfer existing service numbers</span></span>

<span data-ttu-id="56ba0-p108">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="56ba0-p108">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization).</span></span>

> [!NOTE]
> <span data-ttu-id="56ba0-140">さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="56ba0-140">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="56ba0-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="56ba0-141">Related topics</span></span>
[<span data-ttu-id="56ba0-142">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="56ba0-142">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="56ba0-143">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="56ba0-143">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 