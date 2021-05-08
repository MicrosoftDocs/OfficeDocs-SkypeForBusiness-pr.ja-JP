---
title: 電話番号Microsoft 365 Business Voice設定する
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 組織内のユーザーとサービスMicrosoft 365 Business Voice電話番号を設定する方法について学習します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7dcf582593cf09977f4992d6b78035a9726c12b8
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282544"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="6e912-103">手順 2: Business Voice の電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="6e912-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="6e912-104">組織内のユーザーまたは自動応答を設定する前に、ユーザーの電話番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e912-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="6e912-105">電話番号にはさまざまな種類があります。ただし、この手順で追加する必要がある 2 種類の電話番号を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6e912-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="6e912-106">**サービス番号** これらの番号は、自動応答、電話会議、通話キューに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e912-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="6e912-107">有料またはフリーダイヤルの番号を指定できます。また、同時に大量の通話を処理できます。</span><span class="sxs-lookup"><span data-stu-id="6e912-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="6e912-108">会社の電話番号は、後の手順で自動応答に割り当てられるため、サービス番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e912-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="6e912-109">**サブスクライバー番号** これらの番号は、通常のユーザーが通話を行って受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e912-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e912-110">既存の電話番号を使用する場合でも、会社のメイン電話番号とユーザーに一時的な電話番号を作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e912-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="6e912-111">後の手順で、これらの一時番号を既存の電話番号に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e912-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="6e912-112">新しい電話番号が新しい電話番号で利用可能になるには、数時間かかるTeams。</span><span class="sxs-lookup"><span data-stu-id="6e912-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

## <a name="set-up-a-service-number"></a><span data-ttu-id="6e912-113">サービス番号を設定する</span><span class="sxs-lookup"><span data-stu-id="6e912-113">Set up a service number</span></span>

<span data-ttu-id="6e912-114">ここで設定したサービス番号は、後の手順で会社のメイン電話番号に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e912-114">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="6e912-115">Microsoft Teams 管理センターを開き、グローバル管理者であるユーザー (通常は、管理者のサインアップに使用したアカウント) でログインMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="6e912-115">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="6e912-116">左側のナビゲーションで、[Voice 電話 <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">  >  **番号] に**</a>移動し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e912-116">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="6e912-117">注文の名前を入力し、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="6e912-117">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="6e912-118">[場所と数量] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6e912-118">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="6e912-119">[ **国または地域] で**、国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e912-119">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="6e912-120">[ **数値の種類] で**、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e912-120">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="6e912-121">**自動応答 (有料)** 通常の無料以外の電話番号。</span><span class="sxs-lookup"><span data-stu-id="6e912-121">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="6e912-122">呼び出し元には、遠距離料金が請求されます。</span><span class="sxs-lookup"><span data-stu-id="6e912-122">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="6e912-123">**自動応答 (無料通話)** フリーダイヤル (米国およびカナダ) またはフリーフォン (英国) の電話番号。</span><span class="sxs-lookup"><span data-stu-id="6e912-123">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="6e912-124">遠距離料金は会社に請求されます。</span><span class="sxs-lookup"><span data-stu-id="6e912-124">Long distances fees are charged to your company.</span></span> <span data-ttu-id="6e912-125">このオプションを選択する前に、コミュニケーション クレジットを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e912-125">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="6e912-126">詳細については、「What do I need to buy to use [Microsoft 365 Business Voice?」を参照してください](what-to-buy.md)。</span><span class="sxs-lookup"><span data-stu-id="6e912-126">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="6e912-127">[**数量] で\*\*\*\*、[1] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6e912-127">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="6e912-128">[この種類の番号を要求するのに十分なライセンスはありません] というメッセージが表示される場合は、Business Voice ライセンスを購入している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e912-128">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="6e912-129">詳細については、「What do I need to buy to use [Microsoft 365 Business Voice?」を参照してください](what-to-buy.md)。</span><span class="sxs-lookup"><span data-stu-id="6e912-129">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="6e912-130">[場所 **]** **または**[市区町エリア コード] を選択します。場所の都市を使用して電話番号を検索するか、または特定の市区町エリア コードで番号を検索するかに応じて選択します。</span><span class="sxs-lookup"><span data-stu-id="6e912-130">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="6e912-131">[場所] を **選択した場合**:</span><span class="sxs-lookup"><span data-stu-id="6e912-131">If you select **Location**:</span></span>

        1. <span data-ttu-id="6e912-132">緊急対応の住所が保存されている都市を「緊急対応の [](set-up-emergency-locations.md)場所の設定」の手順で入力するか、別のオフィスまたは自宅オフィス用に新しい場所を作成する必要がある場合は、[場所の追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e912-132">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="6e912-133">[ **地域コード]** で、エリア コードを選択し、[次へ] **を選択して** 番号を予約します。</span><span class="sxs-lookup"><span data-stu-id="6e912-133">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="6e912-134">[地域コード **] を選択** した場合は、検索する地域コードを入力し、[次へ] を選択 **して番号を** 予約します。</span><span class="sxs-lookup"><span data-stu-id="6e912-134">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>

5. <span data-ttu-id="6e912-135">目的の番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e912-135">Select the number you want.</span></span> <span data-ttu-id="6e912-136">電話番号を選択して注文するには 10 分かかります。</span><span class="sxs-lookup"><span data-stu-id="6e912-136">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="6e912-137">10 分以上かかる場合は、電話番号が番号のプールに返されます。</span><span class="sxs-lookup"><span data-stu-id="6e912-137">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="6e912-138">注文の準備ができたら、[注文] をクリックし、[完了] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="6e912-138">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="6e912-139">ユーザーの電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="6e912-139">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="6e912-140">Microsoft Teams 管理センターを開き、グローバル管理者であるユーザー (通常は、管理者のサインアップに使用したアカウント) でログインMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="6e912-140">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="6e912-141">左側のナビゲーションで、[Voice 電話 <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">  >  **番号] に**</a>移動し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e912-141">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="6e912-142">注文の名前を入力し、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="6e912-142">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="6e912-143">[場所と数量] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6e912-143">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="6e912-144">[ **国または地域] で**、国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e912-144">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="6e912-145">[数値 **の種類] で**、[ユーザー **(サブスクライバー) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6e912-145">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="6e912-146">[ **数量]** で、組織に必要な数値の数を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e912-146">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="6e912-147">[場所 **]** **または**[市区町エリア コード] を選択します。場所の都市を使用して電話番号を検索するか、または特定の市区町エリア コードで番号を検索するかに応じて選択します。</span><span class="sxs-lookup"><span data-stu-id="6e912-147">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="6e912-148">[場所] を **選択した場合**:</span><span class="sxs-lookup"><span data-stu-id="6e912-148">If you select **Location**:</span></span>

        1. <span data-ttu-id="6e912-149">緊急対応の住所が保存されている都市を「緊急対応の [](set-up-emergency-locations.md)場所の設定」の手順で入力するか、別のオフィスまたは自宅オフィス用に新しい場所を作成する必要がある場合は、[場所の追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e912-149">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="6e912-150">[ **地域コード]** で、エリア コードを選択し、[次へ] **を選択して** 番号を予約します。</span><span class="sxs-lookup"><span data-stu-id="6e912-150">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="6e912-151">[地域コード **] を選択** した場合は、検索する地域コードを入力し、[次へ] を選択 **して番号を** 予約します。</span><span class="sxs-lookup"><span data-stu-id="6e912-151">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>
5. <span data-ttu-id="6e912-152">目的の数値を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e912-152">Select the numbers you want.</span></span> <span data-ttu-id="6e912-153">電話番号を選び、注文するには 10 分かかります。</span><span class="sxs-lookup"><span data-stu-id="6e912-153">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="6e912-154">10 分以上かかる場合、電話番号は番号のプールに返されます。</span><span class="sxs-lookup"><span data-stu-id="6e912-154">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="6e912-155">注文の準備ができたら、[注文] をクリックし、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e912-155">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6e912-156">次の手順: ユーザーにライセンスを割りTeamsする</span><span class="sxs-lookup"><span data-stu-id="6e912-156">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)
