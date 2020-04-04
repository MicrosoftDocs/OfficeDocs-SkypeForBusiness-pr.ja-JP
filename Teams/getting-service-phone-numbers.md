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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: チームの電話会議、自動応答、および通話キュー (サービス番号) の新しい電話番号やポートを取得したり、既存の電話番号を移行したりする方法について説明します。
ms.openlocfilehash: 9eb88d46a9e993067e7a2fc8baf9847dea5b32d7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136717"
---
# <a name="getting-service-phone-numbers"></a><span data-ttu-id="df59a-103">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="df59a-103">Getting service phone numbers</span></span>

<span data-ttu-id="df59a-104">[ユーザーの電話番号を取得](/microsoftteams/getting-phone-numbers-for-your-users)することに加えて、電話会議 (会議ブリッジ用)、自動応答、通話キュー (サービス番号とも呼ばれます) などのサービスの有料または無料の電話番号を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="df59a-104">In addition to [getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users), you can get toll or toll-free phone numbers for services such as Audio Conferencing (for conference bridges), auto attendants, and call queues (also called service numbers).</span></span> <span data-ttu-id="df59a-105">サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。</span><span class="sxs-lookup"><span data-stu-id="df59a-105">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="df59a-106">たとえば、サービス番号では何百もの通話を同時に処理できますが、ユーザーの電話番号は同時に複数の通話を処理できます。</span><span class="sxs-lookup"><span data-stu-id="df59a-106">For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df59a-107">無料の番号を取得するには、まず通信クレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df59a-107">You have to first set up Communications Credits before you can get toll-free numbers.</span></span> <span data-ttu-id="df59a-108">詳細については、「[組織のためにコミュニケーションクレジット](/microsoftteams/set-up-communications-credits-for-your-organization)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df59a-108">To learn more, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
  
<span data-ttu-id="df59a-109">サービス番号を取得するには、次の3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="df59a-109">There are three ways to get service numbers:</span></span>
  
- <span data-ttu-id="df59a-110">**Microsoft Teams 管理センターを使用します。**</span><span class="sxs-lookup"><span data-stu-id="df59a-110">**Use the Microsoft Teams admin center.**</span></span> <span data-ttu-id="df59a-111">一部の国と地域では、Microsoft Teams 管理センターを使用してサービス番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="df59a-111">For some countries and regions, you can get service numbers using the Microsoft Teams admin center.</span></span> <span data-ttu-id="df59a-112">「[新しいサービス番号を取得](#get-new-service-numbers)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df59a-112">See [Get new service numbers](#get-new-service-numbers).</span></span>

- <span data-ttu-id="df59a-113">**既存の番号を移行する。**</span><span class="sxs-lookup"><span data-stu-id="df59a-113">**Port your existing numbers.**</span></span> <span data-ttu-id="df59a-114">現在のサービスプロバイダーまたは電話会社から既存の番号を移行または転送することができます。</span><span class="sxs-lookup"><span data-stu-id="df59a-114">You can port or transfer existing numbers from your current service provider or phone carrier.</span></span> <span data-ttu-id="df59a-115">この方法の詳細については、「[Teams に電話番号を移行](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)」または「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df59a-115">See [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="df59a-116">**新しい番号には申請書を使用します。**</span><span class="sxs-lookup"><span data-stu-id="df59a-116">**Use a request form for new numbers.**</span></span> <span data-ttu-id="df59a-117">場合によっては (お住まいの国または地域によっては)、Microsoft Teams 管理センターを使用して新しい電話番号を取得することはできません。または、特定の電話番号または市外局番が必要です。</span><span class="sxs-lookup"><span data-stu-id="df59a-117">Sometimes (depending on your country or region) you won't be able to get your new phone numbers using the Microsoft Teams admin center, or you'll need specific phone numbers or area codes.</span></span> <span data-ttu-id="df59a-118">その場合は、フォームをダウンロードして、もう一度送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df59a-118">If so, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="df59a-119">詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df59a-119">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df59a-120">サービス番号が必要なので、特定の番号の同時通話能力を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="df59a-120">Service numbers are needed so you can get a higher concurrent call capacity for a specific number.</span></span> <span data-ttu-id="df59a-121">お客さまの番号を転送する場合は、 [PSTN サービスデスクに問い合わせて](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)、転送するサービス番号の同時通話能力が高いことを確認します。</span><span class="sxs-lookup"><span data-stu-id="df59a-121">When you're transferring the number over to us, you can [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) to make sure the service number you're transferring has a high concurrent call capacity.</span></span>
  
## <a name="get-new-service-numbers"></a><span data-ttu-id="df59a-122">新しいサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="df59a-122">Get new service numbers</span></span>

<span data-ttu-id="df59a-123">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="df59a-123">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="df59a-124">左側のナビゲーションで、[**電話番号** **] に移動** > し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df59a-124">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
2. <span data-ttu-id="df59a-125">注文の名前を入力し、必要に応じて説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="df59a-125">Enter a name for the order and if you want, add a description.</span></span>
3. <span data-ttu-id="df59a-126">[場所と数量] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="df59a-126">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="df59a-127">[**国または地域**] で、国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="df59a-127">Under **Country or region**, select a country or region.</span></span>
    1. <span data-ttu-id="df59a-128">[**番号の種類**] で、目的のサービス番号の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="df59a-128">Under **Number type**, select the type of service number that you want.</span></span>
    1. <span data-ttu-id="df59a-129">[**場所**] で、場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="df59a-129">Under **Location**, select a location.</span></span> <span data-ttu-id="df59a-130">新しい場所を作成する必要がある場合は、[**場所の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df59a-130">If you need to create a new location, click **Add a location**.</span></span>
    1. <span data-ttu-id="df59a-131">[**市外局番**] で、市外局番を選択します。</span><span class="sxs-lookup"><span data-stu-id="df59a-131">Under **Area code**, select an area code.</span></span> 
    2. <span data-ttu-id="df59a-132">[**数量**] の下で、組織に必要な数値の数を入力し、[**次へ**] をクリックして番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="df59a-132">Under **Quantity**, enter the number of numbers that you want for your organization, and then click **Next** to select your numbers.</span></span>
4. <span data-ttu-id="df59a-133">目的の番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="df59a-133">Select the numbers you want.</span></span> <span data-ttu-id="df59a-134">電話番号を選択して注文するには、10分間かかります。</span><span class="sxs-lookup"><span data-stu-id="df59a-134">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="df59a-135">10分以上経過すると、電話番号は番号のプールに戻されます。</span><span class="sxs-lookup"><span data-stu-id="df59a-135">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
5. <span data-ttu-id="df59a-136">注文する準備ができたら、[**注文**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df59a-136">When you're ready to place your order, click **Place order**.</span></span>

## <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="df59a-137">既存のサービス番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="df59a-137">Port or transfer existing service numbers</span></span>

<span data-ttu-id="df59a-138">現在のサービスプロバイダーまたは通信事業者からチームに電話番号を移行するには、Microsoft Teams 管理センターの [移植] ウィザードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="df59a-138">To transfer your phone numbers from your current service provider or carrier to Teams, you can use the porting wizard in the Microsoft Teams admin center.</span></span> <span data-ttu-id="df59a-139">「[チームに電話番号を転送する](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="df59a-139">Follow the steps in [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

<span data-ttu-id="df59a-140">お住まいの国または地域が [移植ウィザード] に表示されていない場合は、[手動でポート注文を送信](phone-number-calling-plans/manually-submit-port-order.md)するか、「[組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」にアクセスして、お住まいの国または地域を選択してから、承認状 (loa) をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="df59a-140">If your country or region isn't listed in the porting wizard, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md), select your country or region, and then download a Letter of Authorization (LOA).</span></span> <span data-ttu-id="df59a-141">サービス番号の種類 (有料と無料など) ごとに個別のポート注文を送信して、LOA を使って転送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df59a-141">You'll have to submit separate port orders for each type of service number (for example, toll vs. toll-free) that you'll be transferring by using an LOA.</span></span> <span data-ttu-id="df59a-142">LOA では、適切な種類のサービス番号を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df59a-142">In the LOA, you must select the correct type of service number.</span></span> <span data-ttu-id="df59a-143">(ユーザーまたは加入者番号ではなく) サービス番号を転送することを指定してください。または、同時通話容量が、通話ボリュームを処理するには十分でない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df59a-143">Make sure you specify that you're transferring a service number (and not a user or subscriber number), or the concurrent calling capacity may not be enough to handle call volumes.</span></span>  

> [!NOTE]
> <span data-ttu-id="df59a-144">その他の電話番号を取得する必要がある場合は、 [PSTN サービスデスクにお問い合わせください](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。</span><span class="sxs-lookup"><span data-stu-id="df59a-144">If you need to get more phone numbers than this, [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span>

## <a name="view-the-phone-numbers-for-your-organization"></a><span data-ttu-id="df59a-145">組織の電話番号を表示する</span><span class="sxs-lookup"><span data-stu-id="df59a-145">View the phone numbers for your organization</span></span>

<span data-ttu-id="df59a-146">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="df59a-146">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span> 

<span data-ttu-id="df59a-147">左側のナビゲーションで、[ > **電話番号**] に移動して、場所、番号の種類、状態の情報など、組織の電話**番号を表示**します。</span><span class="sxs-lookup"><span data-stu-id="df59a-147">In the left navigation, go to **Voice** > **Phone numbers** to view the numbers for your organization, including location, number type, and status information.</span></span>

## <a name="assign-service-phone-numbers"></a><span data-ttu-id="df59a-148">サービスの電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="df59a-148">Assign service phone numbers</span></span>

<span data-ttu-id="df59a-149">サービス番号を取得したら、電話会議ブリッジに各番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="df59a-149">After you get your service numbers, assign each number to an Audio Conferencing bridge.</span></span> <span data-ttu-id="df59a-150">「[電話会議ブリッジの有料または無料電話番号を変更する」を](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)参照してください。</span><span class="sxs-lookup"><span data-stu-id="df59a-150">See [Change the toll or toll free numbers on your Audio Conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="related-topics"></a><span data-ttu-id="df59a-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="df59a-151">Related topics</span></span>

[<span data-ttu-id="df59a-152">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="df59a-152">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="df59a-153">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="df59a-153">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="df59a-154">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="df59a-154">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="df59a-155">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="df59a-155">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="df59a-156">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="df59a-156">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
