---
title: サービス電話番号の取得
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: Office 365 から、ユーザーの電話番号を取得するだけでなく、検索、電話会議 (会議ブリッジ用) 、自動応答、および通話キュー (サービス番号とも呼ばれます) などのサービスの無料または有料電話番号を取得できます。 サービス電話番号では、同時に処理できる通話の容量が、ユーザーまたはサブスクライバーの電話番号よりも大きくなります。
ms.openlocfilehash: f45bccd76e560dacc94211d6339858e82541821e
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779160"
---
# <a name="getting-service-phone-numbers"></a><span data-ttu-id="03804-104">サービス電話番号の取得</span><span class="sxs-lookup"><span data-stu-id="03804-104">Getting service phone numbers</span></span>

<span data-ttu-id="03804-105">Office 365 から、ユーザーの電話番号を取得するだけでなく、検索、電話会議 (会議ブリッジ用) 、自動応答、および通話キュー (サービス番号とも呼ばれます) などのサービスの無料または有料電話番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="03804-105">In addition to getting phone numbers for individual users from Office 365, it's also possible to search and acquire toll or toll-free phone numbers for services such as Audio Conferencing (for conference bridges), auto attendants, and call queues.</span></span> <span data-ttu-id="03804-106">サービス電話番号では、同時に処理できる通話の容量が、ユーザーまたはサブスクライバーの電話番号よりも大きくなります。</span><span class="sxs-lookup"><span data-stu-id="03804-106">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="03804-107">たとえば、サービス電話番号では同時に 100 件の通話を処理できますが、ユーザーの電話番号では同時に数件の通話しか処理できません。</span><span class="sxs-lookup"><span data-stu-id="03804-107">For example, a service number can handle 100's of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>
  
> [!NOTE]
> <span data-ttu-id="03804-108">Office 365 コミュニケーション クレジットは、フリー ダイヤル番号を取得できるように、最初にセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="03804-108">Office 365 Communications Credits must be set up first in order to acquire toll-free numbers.</span></span> <span data-ttu-id="03804-109">「[組織のためにコミュニケーション クレジットをセットアップする](/microsoftteams/set-up-communications-credits-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03804-109">[Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization)</span></span> 
  
<span data-ttu-id="03804-110">サービス番号を取得して Skype for Business と Microsoft Teams で使用できるようにするには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="03804-110">You have two ways of getting service numbers so you can use them with Skype for Business:</span></span>
  
- <span data-ttu-id="03804-111">Office 365 から新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="03804-111">Get new numbers from Office 365 Skype for Business.</span></span>
    
- <span data-ttu-id="03804-112">現在のサービス プロバイダーまたは電話会社から Office 365 に既存の番号を移行または転送します。</span><span class="sxs-lookup"><span data-stu-id="03804-112">Port or transfer your existing numbers from your current service provider or phone carrier to Office 365.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03804-113">サービス番号を転送する場合は、同時通話容量を考慮して正しく構成するために、[Microsoft サポート](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)に連絡することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="03804-113">When you transfer your service numbers, it is highly recommended that you contact [Contact support for business products - Admin Help](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) to ensure the higher concurrent calling capacity is considered and configured correctly.</span></span>
  
## <a name="get-new-service-numbers"></a><span data-ttu-id="03804-114">新しいサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="03804-114">Get new service numbers</span></span>

<span data-ttu-id="03804-115">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="03804-115">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="03804-116">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="03804-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="03804-117">**[Office 365 管理センター]** > **[Skype for Business]** に進みます。</span><span class="sxs-lookup"><span data-stu-id="03804-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="03804-118">左側のナビゲーションで、**[音声]**  >  **[電話番号]**  >  **[新しい番号を追加]** と進み、**[新しいユーザーの番号]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03804-118">In the left navigation go to **Voice** > **Phone numbers** > **Add** then click **New service numbers**.</span></span>
    
    > [!IMPORTANT] 
    > <span data-ttu-id="03804-119">Skype for Business 管理センターの左のナビゲーションに  **[音声]** オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム** アドオン ライセンス、または **電話会議** アドオン ライセンスを少なくとも 1 件購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03804-119">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="03804-120">[ **新しいサービス番号の追加**] ページで、次を選択します。</span><span class="sxs-lookup"><span data-stu-id="03804-120">On the **Add new user numbers** page, choose the following:</span></span>
    
  - <span data-ttu-id="03804-121">**国/地域**</span><span class="sxs-lookup"><span data-stu-id="03804-121">**Country/Region**</span></span>
    
  - <span data-ttu-id="03804-122">**都道府県/地域**</span><span class="sxs-lookup"><span data-stu-id="03804-122">**State/Region**</span></span>
    
  - <span data-ttu-id="03804-123">**市区町村**</span><span class="sxs-lookup"><span data-stu-id="03804-123">**City**</span></span>
    
5. <span data-ttu-id="03804-124">[ **数量**] の下に、組織に必要な電話番号の数を入力し、[ **追加**] をクリックして、予約を作成します。</span><span class="sxs-lookup"><span data-stu-id="03804-124">Under **Quantity**, enter the number of phone numbers that you want for your organization and click **Add** to create a reservation.</span></span> <span data-ttu-id="03804-125">電話番号を選ぶのに与えられた時間は 10 分間です。選ぶのに 10 分以上かかると、電話番号は電話番号のプールに戻ります。</span><span class="sxs-lookup"><span data-stu-id="03804-125">You have 10 minutes to select your phone numbers; if you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03804-126">[ **取得できる合計ユーザー数**] の横に表示されるライセンス数に基づいた電話番号の数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="03804-126">You can see the number of phone numbers which is based on the number of licenses listed next to **Total user number your can acquire**.</span></span> <span data-ttu-id="03804-127">詳細は、「[取得できる電話番号の数について](/microsoftteams/how-many-phone-numbers-can-you-get)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="03804-127">[How many phone numbers can you get?](/microsoftteams/how-many-phone-numbers-can-you-get)</span></span>
  
6. <span data-ttu-id="03804-128">[ **番号を表示**] をクリックすると、電話番号の完全なリストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="03804-128">You can click **Show numbers** to see the full list of phone numbers.</span></span> <span data-ttu-id="03804-129">リストにある電話番号を選びたくない場合には、この方法が便利です。</span><span class="sxs-lookup"><span data-stu-id="03804-129">This is helpful is you don't want to select a specific phone number in the list.</span></span>
    
7. <span data-ttu-id="03804-130">目的の電話番号を選んでから、[ **番号を取得**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="03804-130">Select the phone numbers you want, and then click **Acquire numbers**.</span></span>
    
### <a name="assign-service-numbers"></a><span data-ttu-id="03804-131">サービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="03804-131">Assign service numbers</span></span>

<span data-ttu-id="03804-132">取得したサービス電話番号は、電話会議ブリッジに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="03804-132">Once you have your service numbers, they can then be assigned to a dial-in conferencing bridge.</span></span> <span data-ttu-id="03804-133">これを行う場合は、「[電話会議ブリッジの有料または無料の電話番号を変更する](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="03804-133">To do this, see [Change the toll or toll free numbers on your Audio Conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>
  
### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="03804-134">既存のサービス番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="03804-134">Port or transfer existing service numbers</span></span>

<span data-ttu-id="03804-135">現在のサービスプロバイダーまたは通信業者からサービスの番号を転送する場合は、マイクロソフトに番号移行注文を手動で提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03804-135">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft.</span></span> <span data-ttu-id="03804-136">承認状（LOA)を使用して、移行したいサービス番号（有料・無料）の種類ごとに各々番号移行注文を提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03804-136">You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA).</span></span> <span data-ttu-id="03804-137">承認状（LOA)では、適切な種類のサービス番号を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03804-137">In the Letter of Authorization (LOA), you must select the correct type of service number.</span></span> <span data-ttu-id="03804-138">マイクロソフト サポートに問い合わせる場合は、サービス番号 (*ユーザーまたはサブスクライバーの番号ではなく*) を転送すること、または通話量に対応するための同時通話許容量が十分ではないことを指定してください。</span><span class="sxs-lookup"><span data-stu-id="03804-138">When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes.</span></span> <span data-ttu-id="03804-139">電話番号を転送したり、自分の電話番号で他の操作をする場合は、「[組織の電話番号の管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03804-139">If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization).</span></span>

> [!NOTE]
> <span data-ttu-id="03804-140">さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="03804-140">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="03804-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="03804-141">Related topics</span></span>
[<span data-ttu-id="03804-142">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="03804-142">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="03804-143">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="03804-143">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 