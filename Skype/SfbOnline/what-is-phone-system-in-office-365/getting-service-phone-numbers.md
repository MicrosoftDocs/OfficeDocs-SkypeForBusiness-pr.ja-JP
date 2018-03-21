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
- Strat_SB_PSTN
description: "Office 365 から、ユーザーの電話番号を取得するだけでなく検索し、有料またはオーディオの会議 (会議ブリッジ) の自動応答、および呼び出しキュー (サービス番号とも呼ばれます) などのサービスの無料電話番号を取得できます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。"
ms.openlocfilehash: 4736de90f1a58896f744b154c26066e49a89f1cd
ms.sourcegitcommit: 50446359cd7c359eb2536176545291c723392e47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2018
---
# <a name="getting-service-phone-numbers"></a><span data-ttu-id="9e663-104">サービスの電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="9e663-104">Getting service phone numbers</span></span>

<span data-ttu-id="9e663-105">Office 365 から、ユーザーの電話番号を取得するだけでなく検索し、有料またはオーディオの会議 (会議ブリッジ) の自動応答、および呼び出しキュー (サービス番号とも呼ばれます) などのサービスの無料電話番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="9e663-105">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers).</span></span> <span data-ttu-id="9e663-106">サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。</span><span class="sxs-lookup"><span data-stu-id="9e663-106">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="9e663-107">などのサービス数 100 コールの同時に処理できます、ユーザーの電話番号で、いくつかの呼び出しを同時に処理のみことができますが。</span><span class="sxs-lookup"><span data-stu-id="9e663-107">For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e663-108">Office 365 の通信のクレジットは、フリー ダイヤル番号を取得するために最初に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e663-108">Office 365 Communications Credits must be set up first in order to acquire toll-free numbers.</span></span> <span data-ttu-id="9e663-109">[組織の通信のクレジットの設定](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e663-109">See [Set up Communications Credits for your organization](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).</span></span> 
  
<span data-ttu-id="9e663-110">使用できるようにする Skype でビジネスおよびマイクロソフトのチームには、サービス番号を取得する 2 とおりの方法があります。</span><span class="sxs-lookup"><span data-stu-id="9e663-110">You have two ways of getting service numbers so you can use them with Skype for Business and Microsoft Teams:</span></span>
  
- <span data-ttu-id="9e663-111">Office 365 から新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="9e663-111">Get new numbers from Office 365.</span></span>
    
- <span data-ttu-id="9e663-112">ポートまたはサービス プロバイダーまたは電話のキャリアから、既存の番号を Office 365 に転送します。</span><span class="sxs-lookup"><span data-stu-id="9e663-112">Port or transfer your existing numbers from your service provider or phone carrier to Office 365.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9e663-113">サービス番号を転送するときは、同時呼び出し元の容量が大きくと見なされ、正しく構成されていることを確認するのには[Microsoft のサポート](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)を問い合わせることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9e663-113">When you transfer your service numbers, it is highly recommended that you contact [Microsoft support](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) to ensure that the higher concurrent calling capacity is considered and configured correctly.</span></span>
  
## <a name="get-new-service-numbers"></a><span data-ttu-id="9e663-114">新しいサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="9e663-114">Get new service numbers</span></span>

1. <span data-ttu-id="9e663-115">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9e663-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="9e663-116">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="9e663-116">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="9e663-117">左側のナビゲーションでは、**音声**に移動 > **電話番号** > **新しい番号を追加**し、**新しいサービスの番号**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e663-117">In the left navigation go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>
    
    > [!IMPORTANT] 
    > <span data-ttu-id="9e663-118">ビジネス管理センターの Skype では、左側のナビゲーションの**音声**オプションを表示するため、まず**E5 のエンタープライズ ライセンス**を少なくとも 1 つ、1 つの**電話システム**のアドオン ライセンスまたはアドオンのライセンスが 1 つの**電話会議**を購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e663-118">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="9e663-119">**新しいサービス番号の追加**] ページで、次の手順を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e663-119">On the **Add new service numbers** page, choose the following:</span></span>
    
  - <span data-ttu-id="9e663-120">**国/地域**</span><span class="sxs-lookup"><span data-stu-id="9e663-120">**Country/Region**</span></span>
    
  - <span data-ttu-id="9e663-121">**都道府県/地域**</span><span class="sxs-lookup"><span data-stu-id="9e663-121">**State/Region**</span></span>
    
  - <span data-ttu-id="9e663-122">**市区町村**</span><span class="sxs-lookup"><span data-stu-id="9e663-122">**City**</span></span>
    
5. <span data-ttu-id="9e663-123">[ **数量**] の下に、組織に必要な電話番号の数を入力し、[ **追加**] をクリックして、予約を作成します。</span><span class="sxs-lookup"><span data-stu-id="9e663-123">Under **Quantity**, enter the number of phone numbers that you want for your organization and click **Add** to create a reservation.</span></span> <span data-ttu-id="9e663-124">自分の電話番号を選択するのには 10 分間があります。10 分以上を実行する場合、電話番号は電話番号のプールに返されます。</span><span class="sxs-lookup"><span data-stu-id="9e663-124">You have 10 minutes to select your phone numbers; if you take more than 10 minutes, the phone numbers will be returned to the pool of phone numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9e663-125">横に表示されているライセンスの数に基づいた、電話番号の数を確認することができます**合計サービス番号をことができます取得**。</span><span class="sxs-lookup"><span data-stu-id="9e663-125">You can see the number of phone numbers, which is based on the number of licenses, listed next to **Total Service numbers your can acquire**.</span></span> <span data-ttu-id="9e663-126">詳細についてを参照してください[電話番号の数を取得することができますか?](../what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get.md)</span><span class="sxs-lookup"><span data-stu-id="9e663-126">For details, see [How many phone numbers can you get?](../what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get.md)</span></span>
  
6. <span data-ttu-id="9e663-127">[ **番号を表示**] をクリックすると、電話番号の完全なリストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9e663-127">You can click **Show numbers** to see the full list of phone numbers.</span></span> <span data-ttu-id="9e663-128">リストで特定の電話番号を選択したくない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="9e663-128">This is helpful if you don't want to select a specific phone number in the list.</span></span>
    
7. <span data-ttu-id="9e663-129">目的の電話番号を選んでから、[ **番号の入手**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9e663-129">Select the phone numbers you want, and then click **Acquire numbers**.</span></span>
    
### <a name="assign-service-numbers"></a><span data-ttu-id="9e663-130">サービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="9e663-130">Assign service numbers</span></span>

<span data-ttu-id="9e663-131">サービス番号を作成したら、それらに割り当てて、オーディオ会議ブリッジにします。</span><span class="sxs-lookup"><span data-stu-id="9e663-131">Once you have your service numbers, they can then be assigned to an audio conferencing bridge.</span></span> <span data-ttu-id="9e663-132">これを行う場合は、「[電話会議ブリッジの有料または無料の電話番号を変更する](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9e663-132">To do this, see [Change the toll or toll free numbers on your Audio Conferencing bridge](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>
  
### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="9e663-133">既存のサービス番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="9e663-133">Port or transfer existing service numbers</span></span>

<span data-ttu-id="9e663-134">現在のサービスプロバイダーまたは通信業者からサービスの番号を転送する場合は、マイクロソフトにポートの順序を手動で送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e663-134">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft.</span></span> <span data-ttu-id="9e663-135">種類ごとにサービスの番号 (フリー ダイヤルとダイヤル)、転送される、文字の承認 (ロード) を使用して別のポートの注文を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e663-135">You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA).</span></span> <span data-ttu-id="9e663-136">文字の承認 (ロード)、適切な種類のサービス番号を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e663-136">In the Letter of Authorization (LOA), you must select the correct type of service number.</span></span> <span data-ttu-id="9e663-137">マイクロソフト サポートに問い合わせる場合は、サービス番号 (*および数値以外のユーザーまたはサブスクライバー*) を転送すること、または十分コール ボリュームを処理するために同時の呼び出し元の容量ではありませんを指定するか確認してください。</span><span class="sxs-lookup"><span data-stu-id="9e663-137">When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes.</span></span> <span data-ttu-id="9e663-138">電話番号を転送したり、自分の電話番号を持つ他の操作をする場合は、[組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e663-138">If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9e663-139">さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9e663-139">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="9e663-140">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="9e663-140">Related topics</span></span>
[<span data-ttu-id="9e663-141">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="9e663-141">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="9e663-142">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="9e663-142">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

## <a name="feedback"></a><span data-ttu-id="9e663-143">フィードバックですか。</span><span class="sxs-lookup"><span data-stu-id="9e663-143">Feedback?</span></span>
<span data-ttu-id="9e663-144">製品に関するフィードバックを提供するには、かをお知らせいただいて、取り組み方は、 [Skype](https://www.skypefeedback.com)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e663-144">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>