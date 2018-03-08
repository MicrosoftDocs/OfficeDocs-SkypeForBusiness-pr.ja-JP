---
title: "サービスの電話番号を取得します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
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
- Phone System
- Strat_SB_PSTN
description: "ユーザーの電話番号を取得する、Office 365 から、ほかを検索し、有料またはフリー ダイヤル電話番号 (会議ブリッジ) の電話会議、自動応答では、通話のキュー (サービス番号とも呼ばれます) などのサービスを取得できます。サービスの電話番号では、ユーザーまたはサブスクライバーの電話番号をよりも高い同時呼び出し容量があります。"
ms.openlocfilehash: 16b152fd738b76f0abcfe7e93f2e6a43a2ac55bb
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="getting-service-phone-numbers"></a><span data-ttu-id="5e074-104">サービスの電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="5e074-104">Getting service phone numbers</span></span>

<span data-ttu-id="5e074-p102">ユーザーの電話番号を取得する、Office 365 から、ほかを検索し、有料またはフリー ダイヤル電話番号 (会議ブリッジ) の電話会議、自動応答では、通話のキュー (サービス番号とも呼ばれます) などのサービスを取得できます。サービスの電話番号では、ユーザーまたはサブスクライバーの電話番号をよりも高い同時呼び出し容量があります。たとえば、ユーザーの電話番号のいくつかの電話を同時に処理のみできますが、サービス番号は 100 通話を処理する同時にできます。</span><span class="sxs-lookup"><span data-stu-id="5e074-p102">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e074-p103">Office 365 の通信加算したものは、フリー ダイヤルの番号を取得するために、最初に設定する必要があります。[組織の通信クレジットを設定する](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e074-p103">Office 365 Communications Credits must be set up first in order to acquire toll-free numbers. See [Set up Communications Credits for your organization](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).</span></span> 
  
<span data-ttu-id="5e074-110">2 つの方法を使えるように skype for Business とチームの Microsoft サービス番号を取得するがあります。</span><span class="sxs-lookup"><span data-stu-id="5e074-110">You have two ways of getting service numbers so you can use them with Skype for Business and Microsoft Teams:</span></span>
  
- <span data-ttu-id="5e074-111">Office 365 から新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="5e074-111">Get new numbers from Office 365.</span></span>
    
- <span data-ttu-id="5e074-112">ポートまたは Office 365 のサービス プロバイダーまたは航空会社の電話から、既存の番号に転送します。</span><span class="sxs-lookup"><span data-stu-id="5e074-112">Port or transfer your existing numbers from your service provider or phone carrier to Office 365.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5e074-113">サービス番号を転送するときは、同時呼び出しの容量が大きくと見なされます、正しく構成されていることを確認して[Microsoft のサポート](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)に連絡することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5e074-113">When you transfer your service numbers, it is highly recommended that you contact [Microsoft support](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) to ensure that the higher concurrent calling capacity is considered and configured correctly.</span></span>
  
## <a name="get-new-service-numbers"></a><span data-ttu-id="5e074-114">新しいサービスの番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="5e074-114">Get new service numbers</span></span>

1. <span data-ttu-id="5e074-115">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5e074-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5e074-116">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="5e074-116">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5e074-117">左のナビゲーションでは、**音声**に移動 > **電話番号** > **新しい番号を追加**し、[**サービスの新しい番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e074-117">In the left navigation go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>
    
    > [!IMPORTANT] 
    > <span data-ttu-id="5e074-118">Skype for Business 管理センターの左のナビゲーションで [**音声**] オプションが表示するには、少なくとも 1 つの**エンタープライズ E5 ライセンス**、**電話システムで**アドオン ライセンスは 1 つ、または 1 つの**音声会議**アドオン ライセンスを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e074-118">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="5e074-119">[**新しいサービス番号を追加する**] ページで、次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="5e074-119">On the **Add new service numbers** page, choose the following:</span></span>
    
  - <span data-ttu-id="5e074-120">**{国/地域}**</span><span class="sxs-lookup"><span data-stu-id="5e074-120">**Country/Region**</span></span>
    
  - <span data-ttu-id="5e074-121">**州/地域**</span><span class="sxs-lookup"><span data-stu-id="5e074-121">**State/Region**</span></span>
    
  - <span data-ttu-id="5e074-122">**{City}**</span><span class="sxs-lookup"><span data-stu-id="5e074-122">**City**</span></span>
    
5. <span data-ttu-id="5e074-p104">[**数量**] には、組織に必要し、予約を作成するのには**追加**] をクリックする、電話番号の数を入力します。自分の電話番号を選択する 10 分しか時間があります。10 分を超える場合は、電話番号は、電話番号のプールに返されます。</span><span class="sxs-lookup"><span data-stu-id="5e074-p104">Under **Quantity**, enter the number of phone numbers that you want for your organization and click **Add** to create a reservation. You have 10 minutes to select your phone numbers; if you take more than 10 minutes, the phone numbers will be returned to the pool of phone numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5e074-p105">電話番号は、横に表示される、ライセンス数に基づいて数を表示する**合計サービス番号ことができますを入手する**します。詳細については、次を参照してください[数の電話番号を取得することができますか?](../what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get.md) 。</span><span class="sxs-lookup"><span data-stu-id="5e074-p105">You can see the number of phone numbers, which is based on the number of licenses, listed next to **Total Service numbers your can acquire**. For details, see [How many phone numbers can you get?](../what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get.md)</span></span>
  
6. <span data-ttu-id="5e074-p106">**数値を表示する**電話番号の完全な一覧を表示する] をクリックすることができます。一覧で特定の携帯電話番号を選択しない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="5e074-p106">You can click **Show numbers** to see the full list of phone numbers. This is helpful if you don't want to select a specific phone number in the list.</span></span>
    
7. <span data-ttu-id="5e074-129">必要な電話番号を選択し、[**番号の取得**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e074-129">Select the phone numbers you want, and then click **Acquire numbers**.</span></span>
    
### <a name="assign-service-numbers"></a><span data-ttu-id="5e074-130">サービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="5e074-130">Assign service numbers</span></span>

<span data-ttu-id="5e074-p107">サービス番号を作成したら、[割り当てることができます電話会議ブリッジにします。これを行うには、[変更の有料またはフリー ダイヤルの無料番号で電話会議ブリッジ](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e074-p107">Once you have your service numbers, they can then be assigned to an audio conferencing bridge. To do this, see [Change the toll or toll free numbers on your Audio Conferencing bridge](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>
  
### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="5e074-133">既存のサービス番号のポートまたは転送</span><span class="sxs-lookup"><span data-stu-id="5e074-133">Port or transfer existing service numbers</span></span>

<span data-ttu-id="5e074-p108">航空会社、現在のサービス プロバイダーからサービス番号に転送する場合は、Microsoft にポートの順序を手動で送信する必要があります。サービス番号 (フリー ダイヤルと有料) の種類が転送される、文字の承認 (山) を使用して別のポート注文を送信する必要があります。文字の承認 (山)、正しい型のサービスの番号を選択する必要があります。Microsoft サポートに問い合わせる場合は、サービス番号 (*しユーザーまたはサブスクライバー番号ではなく*) を転送する、または同時呼び出し容量できない場合があります通話ボリュームを処理することを指定することを確認してください。電話番号に転送または電話番号とその他の操作を行う場合は、[組織の管理の電話番号](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e074-p108">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5e074-139">これよりも、その他の電話番号を取得する必要がある場合は、[ビジネス製品 - 管理者向けヘルプのサポートに連絡](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。</span><span class="sxs-lookup"><span data-stu-id="5e074-139">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="5e074-140">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5e074-140">Related topics</span></span>
[<span data-ttu-id="5e074-141">ここではされた電話システムで Office 365 での表示</span><span class="sxs-lookup"><span data-stu-id="5e074-141">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="5e074-142">電話会議とプランの呼び出しの国と地域の空き時間情報</span><span class="sxs-lookup"><span data-stu-id="5e074-142">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
