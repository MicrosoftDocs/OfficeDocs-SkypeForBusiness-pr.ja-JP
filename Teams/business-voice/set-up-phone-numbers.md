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
ms.openlocfilehash: 6cec0bc8e55ef6be169de1f48a375ab40ca8ccf7
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130121"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="c3f08-103">手順 2: Business Voice の電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="c3f08-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="c3f08-104">組織内でユーザーまたは自動応答を設定する前に、ユーザーの電話番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="c3f08-105">電話番号にはいくつかの種類があります。ただし、この手順で追加する必要がある番号の種類は次の 2 種類です。</span><span class="sxs-lookup"><span data-stu-id="c3f08-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="c3f08-106">**サービス番号** これらの番号は、自動応答、電話会議、通話キューに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3f08-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="c3f08-107">有料またはフリーダイヤルの番号で、大量の通話を同時に処理できます。</span><span class="sxs-lookup"><span data-stu-id="c3f08-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="c3f08-108">会社の電話番号は、後の手順で自動応答に割り当てられるため、サービス番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="c3f08-109">**サブスクライバー番号** これらの番号は、通常のユーザーが電話を送受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3f08-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3f08-110">既存の電話番号を使用する場合でも、会社のメインの電話回線とユーザーに一時的な電話番号を作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="c3f08-111">後の手順で、これらの一時的な番号を既存の電話番号に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="c3f08-112">新しい電話番号が新しい電話番号で使用できるまで数時間かかるTeams。</span><span class="sxs-lookup"><span data-stu-id="c3f08-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

## <a name="set-up-a-service-number"></a><span data-ttu-id="c3f08-113">サービス番号を設定する</span><span class="sxs-lookup"><span data-stu-id="c3f08-113">Set up a service number</span></span>

<span data-ttu-id="c3f08-114">現在設定したサービス番号は、後の手順で会社の主要電話番号に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3f08-114">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="c3f08-115">管理センターのMicrosoft Teams移動します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-115">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="c3f08-116">左側のナビゲーションで、[Voice電話番号]  >  **に移動し、[** 追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c3f08-116">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="c3f08-117">注文の名前を入力し、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-117">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="c3f08-118">[場所と数量] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c3f08-118">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="c3f08-119">[ **国または地域] で**、国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-119">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="c3f08-120">[ **数値の種類]** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-120">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="c3f08-121">**自動応答 (有料)** 通常のフリーダイヤル以外の電話番号。</span><span class="sxs-lookup"><span data-stu-id="c3f08-121">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="c3f08-122">長距離料金は呼び出し元に請求されます。</span><span class="sxs-lookup"><span data-stu-id="c3f08-122">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="c3f08-123">**自動応答 (フリーダイヤル)** フリーダイヤル (米国とカナダ) またはフリーフォン (英国) の電話番号。</span><span class="sxs-lookup"><span data-stu-id="c3f08-123">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="c3f08-124">長距離料金は会社に請求されます。</span><span class="sxs-lookup"><span data-stu-id="c3f08-124">Long distances fees are charged to your company.</span></span> <span data-ttu-id="c3f08-125">このオプションを選択する前に、通信クレジットを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-125">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="c3f08-126">詳細については、「購入する必要がある機能」を参照[Microsoft 365 Business Voice。](what-to-buy.md)</span><span class="sxs-lookup"><span data-stu-id="c3f08-126">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="c3f08-127">[**数量] で\*\*\*\*、[1] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c3f08-127">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="c3f08-128">[この種類の数を要求するのに十分なライセンスを持ってない] というメッセージが表示される場合は、Business Voice ライセンスを購入している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-128">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="c3f08-129">詳細については、「購入する必要がある機能」を参照[Microsoft 365 Business Voice。](what-to-buy.md)</span><span class="sxs-lookup"><span data-stu-id="c3f08-129">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="c3f08-130">[ **場所]** で、[緊急の場所の設定] 手順で作成した [場所の名前を入力](set-up-emergency-locations.md) します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-130">Under **Location**, type the name of the location you created in the [Set up emergency locations](set-up-emergency-locations.md) step.</span></span>
    5. <span data-ttu-id="c3f08-131">[ **地域コード]** で地域コードを選択し、[次へ] を **クリックして** 番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-131">Under **Area code**, select an area code, and then click **Next** to select your numbers</span></span>
5. <span data-ttu-id="c3f08-132">目的の番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-132">Select the number you want.</span></span> <span data-ttu-id="c3f08-133">電話番号を選択して注文するには、10 分かかります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-133">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="c3f08-134">10 分以上かかる場合、電話番号は番号のプールに返されます。</span><span class="sxs-lookup"><span data-stu-id="c3f08-134">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="c3f08-135">注文を行う準備ができたら、[注文を行う] **をクリックし**、[完了] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="c3f08-135">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="c3f08-136">ユーザーの電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="c3f08-136">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="c3f08-137">管理センターのMicrosoft Teams移動します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-137">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="c3f08-138">左側のナビゲーションで、[Voice電話番号]  >  **に移動し、[** 追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c3f08-138">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="c3f08-139">注文の名前を入力し、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-139">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="c3f08-140">[場所と数量] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c3f08-140">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="c3f08-141">[ **国または地域] で**、国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-141">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="c3f08-142">[ **数値の種類] で**、[ **ユーザー (サブスクライバー) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c3f08-142">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="c3f08-143">[ **数量]** に、組織に必要な番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-143">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="c3f08-144">[場所 **] で** 場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-144">Under **Location**, select a location.</span></span> <span data-ttu-id="c3f08-145">[緊急の場所の設定] 手順で追加した [](set-up-emergency-locations.md)緊急の場所を選択するか、別のオフィスまたはホーム オフィス用に新しい場所を作成する必要がある場合は、[場所の追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c3f08-145">You can select either the emergency location you added in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
    5. <span data-ttu-id="c3f08-146">[ **地域コード]** で、地域コードを選択し、[次へ] をクリック **して** 番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-146">Under **Area code**, select an area code, and then click **Next** to select your numbers.</span></span>
5. <span data-ttu-id="c3f08-147">必要な番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3f08-147">Select the numbers you want.</span></span> <span data-ttu-id="c3f08-148">電話番号を選択して注文するには、10 分かかります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-148">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="c3f08-149">10 分以上かかる場合、電話番号は番号のプールに返されます。</span><span class="sxs-lookup"><span data-stu-id="c3f08-149">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="c3f08-150">注文の準備ができたら、[注文を行う] を **クリック** し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c3f08-150">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c3f08-151">次の手順: ユーザーにライセンスを割りTeamsする</span><span class="sxs-lookup"><span data-stu-id="c3f08-151">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)
