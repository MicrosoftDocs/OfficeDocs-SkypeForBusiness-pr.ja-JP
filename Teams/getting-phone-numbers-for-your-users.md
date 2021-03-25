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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 'Teams の既存の番号を新規に取得、移植、または転送する方法と、ユーザーに変更を表示する方法について学習します。 '
ms.openlocfilehash: 41693bedec0bd41edd80bc12ae67c87204f1c38e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120718"
---
# <a name="getting-phone-numbers-for-your-users"></a><span data-ttu-id="81415-103">ユーザー用に電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="81415-103">Getting phone numbers for your users</span></span>

<span data-ttu-id="81415-104">[] 組織内でユーザーが電話を発着信できるように設定するには、組織のための電話番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81415-104">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>
  
<span data-ttu-id="81415-105">ユーザー番号を取得するには、次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="81415-105">There are three ways to get user numbers:</span></span>

- <span data-ttu-id="81415-106">**Microsoft Teams 管理センターを使用します。**</span><span class="sxs-lookup"><span data-stu-id="81415-106">**Use the Microsoft Teams admin center.**</span></span> <span data-ttu-id="81415-107">一部の国と地域では、Microsoft Teams 管理センターを使用してユーザーの番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="81415-107">For some countries and regions, you can get numbers for your users using the Microsoft Teams admin center.</span></span> <span data-ttu-id="81415-108">「ユーザー [の新しい電話番号を取得する」を参照してください](#get-new-phone-numbers-for-your-users)。</span><span class="sxs-lookup"><span data-stu-id="81415-108">See [Get new phone numbers for your users](#get-new-phone-numbers-for-your-users).</span></span>

- <span data-ttu-id="81415-109">**既存の番号を移行する。**</span><span class="sxs-lookup"><span data-stu-id="81415-109">**Port your existing numbers.**</span></span> <span data-ttu-id="81415-110">現在のサービス プロバイダーまたは携帯電話会社から既存の番号を移植または転送することができます。</span><span class="sxs-lookup"><span data-stu-id="81415-110">You can port or transfer existing numbers from your current service provider or phone carrier.</span></span> <span data-ttu-id="81415-111">この方法の詳細については、「[Teams に電話番号を移行](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」または「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81415-111">See [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="81415-112">**新しい番号には申請書を使用します。**</span><span class="sxs-lookup"><span data-stu-id="81415-112">**Use a request form for new numbers.**</span></span> <span data-ttu-id="81415-113">(お客様の国や地域によって異なります) Microsoft Teams 管理センターを使用して新しい電話番号を取得できない場合や、特定の電話番号または市番が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="81415-113">Sometimes (depending on your country or region) you won't be able to get your new phone numbers using the Microsoft Teams Admin Center or you'll need specific phone numbers or area codes.</span></span> <span data-ttu-id="81415-114">詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81415-114">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="81415-115">組織の電話番号の設定に関するヘルプが必要な場合は、[ビジネス製品のサポート担当者に問い合わせ - 管理者向け https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online ヘルプ(</span><span class="sxs-lookup"><span data-stu-id="81415-115">If you need help setting up phone numbers for your organization, please [contact Support Contact for Business Products - Admin Help(https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online.</span></span>
  
## <a name="get-new-phone-numbers-for-your-users"></a><span data-ttu-id="81415-116">ユーザーの電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="81415-116">Get new phone numbers for your users</span></span>

<span data-ttu-id="81415-117">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="81415-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="81415-118">これらの変更を行うには、Teams サービス管理者であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="81415-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="81415-119">「[Teams 管理者ロールを使用してチームを管理する](./using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。</span><span class="sxs-lookup"><span data-stu-id="81415-119">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="81415-120">Microsoft Teams 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="81415-120">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="81415-121">左側のナビゲーションで、[**音声電話番号]** に移動し、[追加]  >  をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="81415-121">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="81415-122">注文の名前を入力し、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="81415-122">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="81415-123">[場所と数量] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="81415-123">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="81415-124">[ **国または地域] で**、国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="81415-124">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="81415-125">[ **数値の種類] で**、[ **ユーザー (サブスクライバー)] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="81415-125">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="81415-126">[ **場所] で** 場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="81415-126">Under **Location**, select a location.</span></span> <span data-ttu-id="81415-127">新しい場所を作成する必要がある場合は、[場所の追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="81415-127">If you need to create a new location, click **Add a location**.</span></span>
    4. <span data-ttu-id="81415-128">[ **郵便番号] で**、地域コードを選択します。</span><span class="sxs-lookup"><span data-stu-id="81415-128">Under **Area code**, select an area code.</span></span>
    5. <span data-ttu-id="81415-129">[**数量]** で、組織に必要な数値の数を入力し、[次へ] をクリックして番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="81415-129">Under **Quantity**, enter the number of numbers that you want for your organization, and then click **Next** to select your numbers.</span></span>
5. <span data-ttu-id="81415-130">目的の数値を選択します。</span><span class="sxs-lookup"><span data-stu-id="81415-130">Select the numbers you want.</span></span> <span data-ttu-id="81415-131">電話番号を選択して注文するには、10 分かかります。</span><span class="sxs-lookup"><span data-stu-id="81415-131">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="81415-132">10 分以上かかる場合は、電話番号が番号のプールに返されます。</span><span class="sxs-lookup"><span data-stu-id="81415-132">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="81415-133">注文の準備ができたら、[注文] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="81415-133">When you're ready to place your order, click **Place order**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="81415-134">(サブスクライバー) のユーザーの電話番号の数は、割り当てられた **国内通話プラン**  / **国内と国際通話プラン** ライセンスの合計数に 1.1 をかけて、さらに 10 個の電話番号を足した数と同じです。</span><span class="sxs-lookup"><span data-stu-id="81415-134">The number of phone numbers for users (subscribers) is equal to the total number of **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses you have assigned multiplied by 1.1, plus 10 additional phone numbers.</span></span> <span data-ttu-id="81415-135">たとえば、国内通話プラン / 国内と国際通話プランの合計ユーザー数が 50 人の場合、取得できる電話番号の数は **65** 個 **(50 x 1.1 + 10)** となります。</span><span class="sxs-lookup"><span data-stu-id="81415-135">For example, if you have 50 users in total with a Domestic Calling Plan and/or Domestic and International Calling Plan, you can acquire **65** phone numbers **(50 x 1.1 + 10)**.</span></span> <span data-ttu-id="81415-136">詳細については、「取得できる電話番号 [の数」を参照してください](./how-many-phone-numbers-can-you-get.md)。</span><span class="sxs-lookup"><span data-stu-id="81415-136">For details, see [How many phone numbers can you get?](./how-many-phone-numbers-can-you-get.md).</span></span> <span data-ttu-id="81415-137">これより多くの電話番号を取得する必要がある場合は、ビジネス製品のサポート問い合わせ - 管理者向け [ヘルプにお問い合わせください](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="81415-137">If you need to get more phone numbers than this, [contact Support Contact for Business Products - Admin Help](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide).</span></span>
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="81415-138">サービス プロバイダーまたは電話会社から電話番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="81415-138">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="81415-139">ユーザーに必要な電話番号が 999 以下の場合は、Microsoft Teams 管理センターの移植ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="81415-139">If you need 999 or fewer phone numbers for your users, use the porting wizard in the Microsoft Teams Admin Center.</span></span> <span data-ttu-id="81415-140">「電話番号を [Teams に転送する」の手順に従います](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="81415-140">Follow the steps in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span> <span data-ttu-id="81415-141">お客様の国または地域が移植ウィザードに表示されていない場合は、ポート注文を[](phone-number-calling-plans/manually-submit-port-order.md)手動で送信するか、「組織の[](/microsoftteams/manage-phone-numbers-for-your-organization)電話番号を管理する」を参照して、正しい承認状 (LOA) をダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="81415-141">If your country or region isn't listed in the porting wizard, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) to download the correct Letter of Authorization (LOA).</span></span>

- <span data-ttu-id="81415-142">999 を超える電話番号を移行する必要がある場合は[](phone-number-calling-plans/manually-submit-port-order.md)、番号移行注文を手動で[](/microsoftteams/manage-phone-numbers-for-your-organization)送信するか、「組織の電話番号を管理する」を参照して正しい承認状 (LOA) をダウンロードし[、PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)サービス デスクに送信してすべての番号を転送することができます。</span><span class="sxs-lookup"><span data-stu-id="81415-142">If you need to port more than 999 phone numbers, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) to download the correct Letter of Authorization (LOA) and then send it to [the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) to get all your numbers transferred.</span></span>

## <a name="view-the-phone-numbers-for-your-organization"></a><span data-ttu-id="81415-143">組織の電話番号を表示する</span><span class="sxs-lookup"><span data-stu-id="81415-143">View the phone numbers for your organization</span></span>

<span data-ttu-id="81415-144">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="81415-144">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="81415-145">管理センターの左側のナビゲーションで、[音声電話番号]に移動して、場所、番号の種類、状態情報など、組織の番号  >  を表示します。</span><span class="sxs-lookup"><span data-stu-id="81415-145">In the left navigation of the admin center, go to **Voice** > **Phone numbers** to view the numbers for your organization, including location, number type, and status information.</span></span>
  
## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="81415-146">ユーザーに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="81415-146">Assign phone numbers to users</span></span>

<span data-ttu-id="81415-147">電話番号を取得した後は、各ユーザーに番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="81415-147">After you get your phone numbers, you'll need to assign a number to each of your users.</span></span> <span data-ttu-id="81415-148">詳細 [については、「ユーザーの電話番号を割り当てる](./assign-change-or-remove-a-phone-number-for-a-user.md) 、変更する、または削除する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81415-148">See [Assign, change, or remove a phone number for a user](./assign-change-or-remove-a-phone-number-for-a-user.md) for more information.</span></span>

> [!NOTE]
> <span data-ttu-id="81415-149">これより多くの電話番号を取得する必要がある場合は、ビジネス製品のサポート問い合わせ - 管理者向け [ヘルプにお問い合わせください](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="81415-149">If you need to get more phone numbers than this, [contact Support Contact for Business Products - Admin Help](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide).</span></span>

## <a name="related-topics"></a><span data-ttu-id="81415-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="81415-150">Related topics</span></span>

[<span data-ttu-id="81415-151">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="81415-151">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="81415-152">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="81415-152">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="81415-153">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="81415-153">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="81415-154">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="81415-154">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="81415-155">[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="81415-155">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>