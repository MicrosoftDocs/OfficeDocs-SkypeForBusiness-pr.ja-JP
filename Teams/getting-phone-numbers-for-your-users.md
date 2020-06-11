---
title: ユーザー用に電話番号を取得する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
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
- Calling Plans
description: 'チームに新しい番号を取得する方法、既存の番号を移行する方法、ユーザーへの変更を表示する方法について説明します。 '
ms.openlocfilehash: 45c0b87d8e208913b9be0d231a8e2ae2e0ebfd5a
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691433"
---
# <a name="getting-phone-numbers-for-your-users"></a><span data-ttu-id="c73d8-103">ユーザー用に電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="c73d8-103">Getting phone numbers for your users</span></span>

<span data-ttu-id="c73d8-104">[] 組織内でユーザーが電話を発着信できるように設定するには、組織のための電話番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c73d8-104">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>
  
<span data-ttu-id="c73d8-105">ユーザー番号を取得するには、次の3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c73d8-105">There are three ways to get user numbers:</span></span>

- <span data-ttu-id="c73d8-106">**Microsoft Teams 管理センターを使用します。**</span><span class="sxs-lookup"><span data-stu-id="c73d8-106">**Use the Microsoft Teams admin center.**</span></span> <span data-ttu-id="c73d8-107">一部の国と地域では、Microsoft Teams 管理センターを使用して、ユーザーの電話番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="c73d8-107">For some countries and regions, you can get numbers for your users using the Microsoft Teams admin center.</span></span> <span data-ttu-id="c73d8-108">「[ユーザー用に新しい電話番号を取得する」を](#get-new-phone-numbers-for-your-users)参照してください。</span><span class="sxs-lookup"><span data-stu-id="c73d8-108">See [Get new phone numbers for your users](#get-new-phone-numbers-for-your-users).</span></span>
    
- <span data-ttu-id="c73d8-109">**既存の番号を移行する。**</span><span class="sxs-lookup"><span data-stu-id="c73d8-109">**Port your existing numbers.**</span></span> <span data-ttu-id="c73d8-110">現在のサービスプロバイダーまたは電話会社から既存の番号を移行または転送することができます。</span><span class="sxs-lookup"><span data-stu-id="c73d8-110">You can port or transfer existing numbers from your current service provider or phone carrier.</span></span> <span data-ttu-id="c73d8-111">この方法の詳細については、「[Teams に電話番号を移行](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)」または「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c73d8-111">See [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="c73d8-112">**新しい番号には申請書を使用します。**</span><span class="sxs-lookup"><span data-stu-id="c73d8-112">**Use a request form for new numbers.**</span></span> <span data-ttu-id="c73d8-113">場合によっては (お住まいの国または地域によっては)、Microsoft Teams 管理センターを使用して新しい電話番号を取得することはできません。または、特定の電話番号または市外局番が必要です。</span><span class="sxs-lookup"><span data-stu-id="c73d8-113">Sometimes (depending on your country or region) you won't be able to get your new phone numbers using the Microsoft Teams Admin Center or you'll need specific phone numbers or area codes.</span></span> <span data-ttu-id="c73d8-114">詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c73d8-114">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c73d8-115">組織の電話番号の設定に関するヘルプが必要な場合は、[ビジネス製品のサポートへの問い合わせ-管理者向けヘルプ] () を参照してください https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online 。</span><span class="sxs-lookup"><span data-stu-id="c73d8-115">If you need help setting up phone numbers for your organization, please [contact Support Contact for Business Products - Admin Help(https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online.</span></span>
  
## <a name="get-new-phone-numbers-for-your-users"></a><span data-ttu-id="c73d8-116">ユーザーの電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="c73d8-116">Get new phone numbers for your users</span></span>

<span data-ttu-id="c73d8-117">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="c73d8-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c73d8-118">Microsoft Teams 管理センターに移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。</span><span class="sxs-lookup"><span data-stu-id="c73d8-118">Go to the Microsoft Teams Admin Center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="c73d8-119">左側のナビゲーションで、 **Voice**  >  [**電話番号**] に移動し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c73d8-119">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="c73d8-120">注文の名前を入力し、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="c73d8-120">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="c73d8-121">[場所と数量] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c73d8-121">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="c73d8-122">[**国または地域**] で、国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="c73d8-122">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="c73d8-123">[**番号の種類**] で、[**ユーザー (サブスクライバー)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c73d8-123">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="c73d8-124">[**場所**] で、場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="c73d8-124">Under **Location**, select a location.</span></span> <span data-ttu-id="c73d8-125">新しい場所を作成する必要がある場合は、[**場所の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c73d8-125">If you need to create a new location, click **Add a location**.</span></span>
    4. <span data-ttu-id="c73d8-126">[**市外局番**] で、市外局番を選択します。</span><span class="sxs-lookup"><span data-stu-id="c73d8-126">Under **Area code**, select an area code.</span></span> 
    5. <span data-ttu-id="c73d8-127">[**数量**] の下で、組織に必要な数値の数を入力し、[**次へ**] をクリックして番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="c73d8-127">Under **Quantity**, enter the number of numbers that you want for your organization, and then click **Next** to select your numbers.</span></span>
5. <span data-ttu-id="c73d8-128">目的の番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="c73d8-128">Select the numbers you want.</span></span> <span data-ttu-id="c73d8-129">電話番号を選択して注文するには、10分間かかります。</span><span class="sxs-lookup"><span data-stu-id="c73d8-129">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="c73d8-130">10分以上経過すると、電話番号は番号のプールに戻されます。</span><span class="sxs-lookup"><span data-stu-id="c73d8-130">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="c73d8-131">注文する準備ができたら、[**注文**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c73d8-131">When you're ready to place your order, click **Place order**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c73d8-132">(サブスクライバー) のユーザーの電話番号の数は、割り当てられた\*\* 国内通話プラン\*\*  / \*\* 国内と国際通話プラン\*\* ライセンスの合計数に 1.1 をかけて、さらに 10 個の電話番号を足した数と同じです。</span><span class="sxs-lookup"><span data-stu-id="c73d8-132">The number of phone numbers for users (subscribers) is equal to the total number of **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses you have assigned multiplied by 1.1, plus 10 additional phone numbers.</span></span> <span data-ttu-id="c73d8-133">たとえば、国内通話プラン / 国内と国際通話プランの合計ユーザー数が 50 人の場合、取得できる電話番号の数は **65** 個 **(50 x 1.1 + 10)** となります。</span><span class="sxs-lookup"><span data-stu-id="c73d8-133">For example, if you have 50 users in total with a Domestic Calling Plan and/or Domestic and International Calling Plan, you can acquire **65** phone numbers **(50 x 1.1 + 10)**.</span></span> <span data-ttu-id="c73d8-134">詳細については、「[取得できる電話番号の数](/microsoftteams/how-many-phone-numbers-can-you-get)を確認する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c73d8-134">For details, see [How many phone numbers can you get?](/microsoftteams/how-many-phone-numbers-can-you-get).</span></span> <span data-ttu-id="c73d8-135">その他の電話番号を取得する必要がある場合は、「[ビジネス製品のサポートへの問い合わせ-管理者向けヘルプ](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c73d8-135">If you need to get more phone numbers than this, [contact Support Contact for Business Products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online).</span></span>
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="c73d8-136">サービス プロバイダーまたは電話会社から電話番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="c73d8-136">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="c73d8-137">ユーザー用の電話番号を999以下にする必要がある場合は、Microsoft Teams 管理センターの [移植] ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="c73d8-137">If you need 999 or fewer phone numbers for your users, use the porting wizard in the Microsoft Teams Admin Center.</span></span> <span data-ttu-id="c73d8-138">「[チームに電話番号を転送する](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c73d8-138">Follow the steps in [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span> <span data-ttu-id="c73d8-139">お住まいの国または地域が [移植ウィザード] に表示されていない場合は、[手動でポート注文を送信](phone-number-calling-plans/manually-submit-port-order.md)するか、「[組織の電話番号の管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照して正しい文字の承認 (loa) をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="c73d8-139">If your country or region isn't listed in the porting wizard, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) to download the correct Letter of Authorization (LOA).</span></span>

- <span data-ttu-id="c73d8-140">999を超える電話番号を移植する必要がある場合は、[手動でポート注文を送信](phone-number-calling-plans/manually-submit-port-order.md)するか、「[組織の電話番号の管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照して、正しい文字の承認 (loa) をダウンロードしてから、 [PSTN サービスデスク](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)に送信してすべての電話番号を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="c73d8-140">If you need to port more than 999 phone numbers, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) to download the correct Letter of Authorization (LOA) and then send it to [the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) to get all your numbers transferred.</span></span>

## <a name="view-the-phone-numbers-for-your-organization"></a><span data-ttu-id="c73d8-141">組織の電話番号を表示する</span><span class="sxs-lookup"><span data-stu-id="c73d8-141">View the phone numbers for your organization</span></span>

<span data-ttu-id="c73d8-142">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="c73d8-142">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span> 

<span data-ttu-id="c73d8-143"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>の左のナビゲーションで、[電話番号 **] に移動**し  >  **Phone numbers**て、所在地、番号の種類、状態など、組織の番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="c73d8-143">In the left navigation of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to **Voice** > **Phone numbers** to view the numbers for your organization, including location, number type, and status information.</span></span>
  
## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="c73d8-144">ユーザーに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="c73d8-144">Assign phone numbers to users</span></span>

<span data-ttu-id="c73d8-145">電話番号を取得したら、各ユーザーに電話番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c73d8-145">After you get your phone numbers, you'll need to assign a number to each of your users.</span></span> <span data-ttu-id="c73d8-146">詳細については、「[ユーザーの電話番号を割り当て、変更、または削除](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c73d8-146">See [Assign, change, or remove a phone number for a user](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) for more information.</span></span>

> [!NOTE]
> <span data-ttu-id="c73d8-147">その他の電話番号を取得する必要がある場合は、「[ビジネス製品のサポートへの問い合わせ-管理者向けヘルプ](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c73d8-147">If you need to get more phone numbers than this, [contact Support Contact for Business Products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c73d8-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="c73d8-148">Related topics</span></span>

[<span data-ttu-id="c73d8-149">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="c73d8-149">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="c73d8-150">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="c73d8-150">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="c73d8-151">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="c73d8-151">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="c73d8-152">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="c73d8-152">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="c73d8-153">[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c73d8-153">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
