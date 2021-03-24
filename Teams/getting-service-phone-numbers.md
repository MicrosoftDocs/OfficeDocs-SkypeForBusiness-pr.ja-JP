---
title: サービス電話番号を取得する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Teams の電話会議、自動応答、通話キュー (サービス番号) の新しい電話番号を取得し、既存の番号を移植または転送する方法について説明します。
ms.openlocfilehash: 72436591411070ed7ffc67aab5d8d4470f39521d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092235"
---
# <a name="getting-service-phone-numbers"></a><span data-ttu-id="398c9-103">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="398c9-103">Getting service phone numbers</span></span>

<span data-ttu-id="398c9-104">ユーザーの電話番号[](./getting-phone-numbers-for-your-users.md)を取得する以外に、電話会議 (電話会議ブリッジ用)、自動応答、通話キュー (サービス番号とも呼ばれる) などのサービスの有料または無料電話番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="398c9-104">In addition to [getting phone numbers for your users](./getting-phone-numbers-for-your-users.md), you can get toll or toll-free phone numbers for services such as Audio Conferencing (for conference bridges), auto attendants, and call queues (also called service numbers).</span></span> <span data-ttu-id="398c9-105">サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。</span><span class="sxs-lookup"><span data-stu-id="398c9-105">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="398c9-106">たとえば、サービス番号は何百もの通話を同時に処理できるのに対し、ユーザーの電話番号は同時に数件の通話しか処理できません。</span><span class="sxs-lookup"><span data-stu-id="398c9-106">For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>
  
> [!NOTE]
> <span data-ttu-id="398c9-107">無料電話番号を取得するには、まずコミュニケーション クレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="398c9-107">You have to first set up Communications Credits before you can get toll-free numbers.</span></span> <span data-ttu-id="398c9-108">詳細については、組織の [コミュニケーション クレジットのセットアップに関するページを参照してください](./set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="398c9-108">To learn more, see [Set up Communications Credits for your organization](./set-up-communications-credits-for-your-organization.md).</span></span>
  
<span data-ttu-id="398c9-109">サービス番号を取得するには、次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="398c9-109">There are three ways to get service numbers:</span></span>
  
- <span data-ttu-id="398c9-110">**Microsoft Teams 管理センターを使用します。**</span><span class="sxs-lookup"><span data-stu-id="398c9-110">**Use the Microsoft Teams admin center.**</span></span> <span data-ttu-id="398c9-111">一部の国と地域では、Microsoft Teams 管理センターを使用してサービス番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="398c9-111">For some countries and regions, you can get service numbers using the Microsoft Teams admin center.</span></span> <span data-ttu-id="398c9-112">「新 [しいサービス番号を取得する」を参照してください](#get-new-service-numbers)。</span><span class="sxs-lookup"><span data-stu-id="398c9-112">See [Get new service numbers](#get-new-service-numbers).</span></span>

- <span data-ttu-id="398c9-113">**既存の番号を移行する。**</span><span class="sxs-lookup"><span data-stu-id="398c9-113">**Port your existing numbers.**</span></span> <span data-ttu-id="398c9-114">現在のサービス プロバイダーまたは携帯電話会社から既存の番号を移植または転送することができます。</span><span class="sxs-lookup"><span data-stu-id="398c9-114">You can port or transfer existing numbers from your current service provider or phone carrier.</span></span> <span data-ttu-id="398c9-115">この方法の詳細については、「[Teams に電話番号を移行](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」または「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="398c9-115">See [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="398c9-116">**新しい番号には申請書を使用します。**</span><span class="sxs-lookup"><span data-stu-id="398c9-116">**Use a request form for new numbers.**</span></span> <span data-ttu-id="398c9-117">(お客様の国や地域に応じて) Microsoft Teams 管理センターを使用して新しい電話番号を取得できない場合や、特定の電話番号または市番が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="398c9-117">Sometimes (depending on your country or region) you won't be able to get your new phone numbers using the Microsoft Teams admin center, or you'll need specific phone numbers or area codes.</span></span> <span data-ttu-id="398c9-118">その場合は、フォームをダウンロードして返送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="398c9-118">If so, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="398c9-119">詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="398c9-119">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="398c9-120">サービス番号は、特定の番号に対してより高い同時通話容量を取得するために必要です。</span><span class="sxs-lookup"><span data-stu-id="398c9-120">Service numbers are needed so you can get a higher concurrent call capacity for a specific number.</span></span> <span data-ttu-id="398c9-121">番号を転送する場合は [、PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) サービス デスクに問い合わせ、移行するサービス番号の同時通話容量が高い確認を行います。</span><span class="sxs-lookup"><span data-stu-id="398c9-121">When you're transferring the number over to us, you can [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) to make sure the service number you're transferring has a high concurrent call capacity.</span></span>
  
## <a name="get-new-service-numbers"></a><span data-ttu-id="398c9-122">新しいサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="398c9-122">Get new service numbers</span></span>

<span data-ttu-id="398c9-123">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="398c9-123">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="398c9-124">左側のナビゲーションで、[**音声電話番号]** に移動し、[追加]  >  をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="398c9-124">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
2. <span data-ttu-id="398c9-125">注文の名前を入力し、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="398c9-125">Enter a name for the order and add a description.</span></span>
3. <span data-ttu-id="398c9-126">[場所と数量] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="398c9-126">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="398c9-127">[ **国または地域] で**、国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="398c9-127">Under **Country or region**, select a country or region.</span></span>
    1. <span data-ttu-id="398c9-128">[ **番号の種類]** で、必要なサービス番号の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="398c9-128">Under **Number type**, select the type of service number that you want.</span></span>
    1. <span data-ttu-id="398c9-129">[ **場所] で** 場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="398c9-129">Under **Location**, select a location.</span></span> <span data-ttu-id="398c9-130">新しい場所を作成する必要がある場合は、[場所の追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="398c9-130">If you need to create a new location, click **Add a location**.</span></span>
    1. <span data-ttu-id="398c9-131">[ **郵便番号] で**、地域コードを選択します。</span><span class="sxs-lookup"><span data-stu-id="398c9-131">Under **Area code**, select an area code.</span></span> 
    2. <span data-ttu-id="398c9-132">[**数量]** で、組織に必要な数値の数を入力し、[次へ] をクリックして番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="398c9-132">Under **Quantity**, enter the number of numbers that you want for your organization, and then click **Next** to select your numbers.</span></span>
4. <span data-ttu-id="398c9-133">目的の数値を選択します。</span><span class="sxs-lookup"><span data-stu-id="398c9-133">Select the numbers you want.</span></span> <span data-ttu-id="398c9-134">電話番号を選択して注文するには、10 分かかります。</span><span class="sxs-lookup"><span data-stu-id="398c9-134">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="398c9-135">10 分以上かかる場合は、電話番号が番号のプールに返されます。</span><span class="sxs-lookup"><span data-stu-id="398c9-135">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
5. <span data-ttu-id="398c9-136">注文の準備ができたら、[注文] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="398c9-136">When you're ready to place your order, click **Place order**.</span></span>

## <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="398c9-137">既存のサービス番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="398c9-137">Port or transfer existing service numbers</span></span>

<span data-ttu-id="398c9-138">現在のサービス プロバイダーまたは通信事業者から Teams に電話番号を転送するには、Microsoft Teams 管理センターの移植ウィザードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="398c9-138">To transfer your phone numbers from your current service provider or carrier to Teams, you can use the porting wizard in the Microsoft Teams admin center.</span></span> <span data-ttu-id="398c9-139">「電話番号を [Teams に転送する」の手順に従います](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="398c9-139">Follow the steps in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

<span data-ttu-id="398c9-140">お客様の国または地域が移植ウィザードに表示されていない場合は、ポート注文を[](phone-number-calling-plans/manually-submit-port-order.md)手動で送信するか、組織の電話番号[](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)の管理に移動して、お客様の国または地域を選択し、承認状 (LOA) をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="398c9-140">If your country or region isn't listed in the porting wizard, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md), select your country or region, and then download a Letter of Authorization (LOA).</span></span> <span data-ttu-id="398c9-141">LOA を使用して移行するサービス番号の種類 (有料と無料通話など) ごとに個別の番号移行注文を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="398c9-141">You'll have to submit separate port orders for each type of service number (for example, toll vs. toll-free) that you'll be transferring by using an LOA.</span></span> <span data-ttu-id="398c9-142">LOA で、適切なサービス番号の種類を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="398c9-142">In the LOA, you must select the correct type of service number.</span></span> <span data-ttu-id="398c9-143">サービス番号 (ユーザーまたはサブスクライバー番号ではなく) を転送する場合、または同時呼び出しキャパシティーが通話ボリュームを処理するのに十分ではない可能性がある場合は、必ず指定してください。</span><span class="sxs-lookup"><span data-stu-id="398c9-143">Make sure you specify that you're transferring a service number (and not a user or subscriber number), or the concurrent calling capacity may not be enough to handle call volumes.</span></span>  

> [!NOTE]
> <span data-ttu-id="398c9-144">これより多くの電話番号を取得する必要がある場合は [、PSTN サービス デスクにお問い合わせください](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。</span><span class="sxs-lookup"><span data-stu-id="398c9-144">If you need to get more phone numbers than this, [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span>

## <a name="view-the-phone-numbers-for-your-organization"></a><span data-ttu-id="398c9-145">組織の電話番号を表示する</span><span class="sxs-lookup"><span data-stu-id="398c9-145">View the phone numbers for your organization</span></span>

<span data-ttu-id="398c9-146">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="398c9-146">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span> 

<span data-ttu-id="398c9-147">左側のナビゲーションで [音声電話番号] に移動し、場所、番号の種類、状態情報など、組織の番号  >  を表示します。</span><span class="sxs-lookup"><span data-stu-id="398c9-147">In the left navigation, go to **Voice** > **Phone numbers** to view the numbers for your organization, including location, number type, and status information.</span></span>

## <a name="assign-service-phone-numbers"></a><span data-ttu-id="398c9-148">サービス電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="398c9-148">Assign service phone numbers</span></span>

<span data-ttu-id="398c9-149">サービス番号を取得した後、各番号を電話会議ブリッジに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="398c9-149">After you get your service numbers, assign each number to an Audio Conferencing bridge.</span></span> <span data-ttu-id="398c9-150">「 [電話会議ブリッジで有料または無料電話番号を変更する」を参照してください](./change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="398c9-150">See [Change the toll or toll free numbers on your Audio Conferencing bridge](./change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="398c9-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="398c9-151">Related topics</span></span>

[<span data-ttu-id="398c9-152">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="398c9-152">Here's what you get with Phone System</span></span>](./here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="398c9-153">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="398c9-153">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="398c9-154">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="398c9-154">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="398c9-155">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="398c9-155">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="398c9-156">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="398c9-156">Country and region availability for Audio Conferencing and Calling Plans</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)