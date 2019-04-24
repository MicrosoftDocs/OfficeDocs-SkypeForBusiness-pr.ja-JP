---
title: 組織内の電話システムの設定
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '組織の電話システム (PBX をクラウド) を設定する方法について説明します。 '
ms.openlocfilehash: 7a180817fb4a3885748a5ca80c494ef1b69143a4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32205545"
---
# <a name="setting-up-phone-system-in-your-organization"></a><span data-ttu-id="874dc-103">組織内の電話システムの設定</span><span class="sxs-lookup"><span data-stu-id="874dc-103">Setting up Phone System in your organization</span></span>

<span data-ttu-id="874dc-p101">The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.</span><span class="sxs-lookup"><span data-stu-id="874dc-p101">The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.</span></span>

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a><span data-ttu-id="874dc-106">ステップ 1: 電話システムは、国または地域で利用可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="874dc-106">Step 1: Make sure that Phone System is available in your country or region</span></span>

1.  <span data-ttu-id="874dc-107">最初に [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) へ進み、ページの上部にある一覧表から国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="874dc-107">First go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page.</span></span> 
2.  <span data-ttu-id="874dc-108"> *\*電話システム** での機能と詳細の一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="874dc-108">Under **Phone System**, review the list of features and details.</span></span> 
3.  <span data-ttu-id="874dc-109">電話システムが使用可能な場合は、手順 2 に進みます。</span><span class="sxs-lookup"><span data-stu-id="874dc-109">If Phone System is available, go to step 2.</span></span> 

<span data-ttu-id="874dc-110">**電話システムおよびオーディオ会議の地域別利用可能時間に関する詳細については、 [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="874dc-110">**To learn more about regional availability of Phone System and Audio Conferencing, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**</span></span>

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a><span data-ttu-id="874dc-111">手順 2: 電話システムおよび通話プランのライセンスを購入し、割り当てる</span><span class="sxs-lookup"><span data-stu-id="874dc-111">Step 2: Buy and assign Phone System and Calling Plan licenses</span></span>

<span data-ttu-id="874dc-112">電話システムと通話プランのライセンスを 1 人のユーザーに割り当てるには、Office 365 のライセンスを割り当てるのと同じ手順をとります。</span><span class="sxs-lookup"><span data-stu-id="874dc-112">To assign a Phone System and Calling Plan license to a single user the steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="874dc-113">[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="874dc-113">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="874dc-114">一括で複数のユーザーを割り当てる場合は、[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="874dc-114">If you want to assign multiple users in bulk, see [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

## <a name="step-3-get-phone-numbers-for-your-users"></a><span data-ttu-id="874dc-115">手順 3: ユーザーの電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="874dc-115">Step 3: Get phone numbers for your users</span></span>

<span data-ttu-id="874dc-116">[] 組織内でユーザーが電話を発着信できるように設定するには、組織のための電話番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="874dc-116">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>

<span data-ttu-id="874dc-117">ユーザーに番号を取得する 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="874dc-117">You have three ways of getting numbers for your users:</span></span>
- <span data-ttu-id="874dc-118">Skype for Business 管理センターを使用して、新しい電話番号を取得する。</span><span class="sxs-lookup"><span data-stu-id="874dc-118">Get new numbers using the Skype for Business admin center.</span></span>
- <span data-ttu-id="874dc-119">Skype for Business管理センターでは使用できない、新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="874dc-119">Get new numbers that aren't available in the Skype for Business admin center.</span></span>
- <span data-ttu-id="874dc-120">現在のサービス プロバイダーまたは携帯電話会社から Office 365 に既存の番号を移行する。</span><span class="sxs-lookup"><span data-stu-id="874dc-120">Port or transfer your existing numbers from your current service provider or phone carrier to Office 365.</span></span>

<span data-ttu-id="874dc-p103">You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span><span class="sxs-lookup"><span data-stu-id="874dc-p103">You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span></span>

### <a name="get-new-user-phone-numbers"></a><span data-ttu-id="874dc-123">新しいユーザーの電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="874dc-123">Get new user phone numbers</span></span> 
 
<span data-ttu-id="874dc-124">![デバイスのロゴ-30x30.png](media/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="874dc-124">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="874dc-125">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="874dc-125">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="874dc-126">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="874dc-126">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="874dc-127">左側のナビゲーションでは、**音声**に移動 > **電話番号**、**新しい番号を追加**をクリックして![[追加] ボタン](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)、し、**新しいユーザーの番号**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="874dc-127">In the left navigation go to **Voice** > **Phone numbers**, click **Add new number** ![Add button](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png), and then click **New user numbers**.</span></span>
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a><span data-ttu-id="874dc-128">Skype for Business管理センターでは使用できない、新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="874dc-128">Get new numbers that aren't available in the Skype for Business admin center</span></span>
  
<span data-ttu-id="874dc-p104">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.</span><span class="sxs-lookup"><span data-stu-id="874dc-p104">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.</span></span>   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="874dc-132">使用中のサービス プロバイダーまたは携帯電話会社から電話番号を移行する</span><span class="sxs-lookup"><span data-stu-id="874dc-132">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="874dc-p105">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center. Follow the steps found in [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="874dc-p105">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center. Follow the steps found in [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.</span></span>
    
- <span data-ttu-id="874dc-135">999 を超える数の電話番号のポートが必要な場合は、ポート注文サービスの要求またはすべての Office 365 に移植されたこれらの電話番号を取得する順序を送信するのには[、組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="874dc-135">If you need to port more than 999 phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order to get all of these phone numbers ported over to Office 365.</span></span> 

<span data-ttu-id="874dc-136">**新しい電話番号を取得するか、既存の番号を転送する方法の詳細については、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="874dc-136">**For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).**</span></span>

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="874dc-137">手順 4: サービス用の電話番号 (電話会議、通話キュー、自動応答) を取得します。</span><span class="sxs-lookup"><span data-stu-id="874dc-137">Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="874dc-p106">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span><span class="sxs-lookup"><span data-stu-id="874dc-p106">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>

### <a name="get-new-service-numbers"></a><span data-ttu-id="874dc-141">新しいサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="874dc-141">Get new service numbers</span></span>

<span data-ttu-id="874dc-142">![デバイスのロゴ-30x30.png](media/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="874dc-142">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>


1. <span data-ttu-id="874dc-143">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="874dc-143">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="874dc-144">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="874dc-144">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="874dc-145">左側のナビゲーションでは、**音声**に移動 > **電話番号** > **新しい番号を追加**し、**新しいサービスの番号**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="874dc-145">In the left navigation go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="874dc-146">ビジネス管理センターの Skype では、左側のナビゲーションの**音声**オプションを表示するため、まず**E5 のエンタープライズ ライセンス**を少なくとも 1 つ、1 つの**電話システム**のアドオン ライセンスまたはアドオンのライセンスが 1 つの**電話会議**を購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="874dc-146">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a><span data-ttu-id="874dc-147">Skype for Business管理センターでは使用できない、新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="874dc-147">Get new numbers that aren't available in the Skype for Business admin center</span></span>
  
<span data-ttu-id="874dc-p107">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers.</span><span class="sxs-lookup"><span data-stu-id="874dc-p107">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers.</span></span> 

### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="874dc-151">既存のサービス番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="874dc-151">Port or transfer existing service numbers</span></span>

<span data-ttu-id="874dc-p108">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="874dc-p108">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a><span data-ttu-id="874dc-157">手順 5: 通話プランを設定する場合</span><span class="sxs-lookup"><span data-stu-id="874dc-157">Step 5: If you want to set up Calling Plans</span></span>

<span data-ttu-id="874dc-p109">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="874dc-p109">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.</span></span>

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a><span data-ttu-id="874dc-160">緊急時のアドレスと、組織の場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="874dc-160">Add emergency addresses and locations for your organization</span></span>

1. <span data-ttu-id="874dc-161">**緊急の場所**を選択して [**音声**] ページで、 > **新しいアドレスを追加**します。</span><span class="sxs-lookup"><span data-stu-id="874dc-161">On the **Voice** page, choose **Emergency locations** > **Add new address**.</span></span>

2. <span data-ttu-id="874dc-162">[ **新しい住所**] ウィンドウで、住所の名前を入力し、残りのボックスの入力を完了します。</span><span class="sxs-lookup"><span data-stu-id="874dc-162">In the **New address** pane, enter a name for your address, and then complete the remaining boxes.</span></span>
    
     ![新しい緊急時のアドレスを入力すると、住所の書式設定がエラーを引き起こす可能性があります。](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > <span data-ttu-id="874dc-164">上の図のように、英語圏のお客様で街路名が数字の場合は、必ず末尾に「st」または「th」を付けます。</span><span class="sxs-lookup"><span data-stu-id="874dc-164">For English customers, if the street name is a number, be sure to include "st" or "th" at the end, as shown in the above picture.</span></span>

3. <span data-ttu-id="874dc-165">[ **検証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="874dc-165">Choose **Validate**.</span></span>

    <span data-ttu-id="874dc-166">必要な場合は、住所の訂正を求められます。</span><span class="sxs-lookup"><span data-stu-id="874dc-166">If needed, you'll be prompted to make corrections to the address.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="874dc-p110">Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center.</span><span class="sxs-lookup"><span data-stu-id="874dc-p110">Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center.</span></span>

    > [!TIP]
    > <span data-ttu-id="874dc-170">緊急応答用に住所に修正が必要な場合は、住所が更新されたことを通知する緑色のバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="874dc-170">If the address needs to be corrected for emergency response, a green banner will appear notifying you that the address was updated.</span></span>

4. <span data-ttu-id="874dc-171">住所が検証されたら、[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="874dc-171">After the address is validated, choose **Save**.</span></span>

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a><span data-ttu-id="874dc-172">ユーザーに電話番号と緊急時のアドレスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="874dc-172">Assign phone numbers and emergency addresses to users</span></span>

> [!TIP]
> <span data-ttu-id="874dc-p111">この手順を実行する直前にさらにユーザーを追加すると、[ **音声ユーザー**] ページにユーザーが表示されるまでに **数時間** かかることがあります。これには遅延時間があります。</span><span class="sxs-lookup"><span data-stu-id="874dc-p111">If you add more people to your business right before doing this step, it may take **several hours** for them to appear on the **Voice users** page. There's a latency.</span></span>

1. <span data-ttu-id="874dc-175">**ボイス ユーザー**ページで、電話番号と緊急時のアドレスを割り当てたいユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="874dc-175">On the **Voice users** page, select the people who you want to assign a phone number and emergency address to.</span></span>

2. <span data-ttu-id="874dc-176">[操作] ウィンドウで、 **割り当てる番号** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="874dc-176">In the Action pane, click **Assign number**.</span></span>

3. <span data-ttu-id="874dc-177">**番号の割り当て**] ページで、**割り当てる番号の選択**] ボックスの一覧で、ユーザーの電話番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="874dc-177">On the **Assign number** page, in the **Select number to assign** list, select the phone number for the user.</span></span>

4. <span data-ttu-id="874dc-178">緊急アドレスを選択するには、都市の名前をボックスに入力し、**検索**を選択します。</span><span class="sxs-lookup"><span data-stu-id="874dc-178">To select an emergency address, enter name of the city in the box and choose **Search**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="874dc-p112">If you are outside the United States, your numbers already have an emergency address, but you can change it now. See [Assign or change an emergency address for a user](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="874dc-p112">If you are outside the United States, your numbers already have an emergency address, but you can change it now. See [Assign or change an emergency address for a user](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user).</span></span> 
  
5. <span data-ttu-id="874dc-181">電話番号と緊急対応の住所の両方を割り当てたら、[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="874dc-181">After you assign both the phone number and emergency address, choose **Save**.</span></span>

### <a name="tell-your-users-about-their-new-phone-numbers"></a><span data-ttu-id="874dc-182">に関する新しい電話番号をユーザーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="874dc-182">Tell your users about their new phone numbers</span></span>


<span data-ttu-id="874dc-183">新しい電話番号をユーザーに通知する場合は、メールを送信するか、または各組織が指定する方法で行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="874dc-183">We recommend sending mail or using your business's preferred communication method to tell the people about their new phone numbers.</span></span>

<span data-ttu-id="874dc-184">以下は、**ビジネスの Skype**アプリでは、その電話番号を表示できる方法です。</span><span class="sxs-lookup"><span data-stu-id="874dc-184">Here's how they can see that phone number in their **Skype for Business** app:</span></span>

1. <span data-ttu-id="874dc-185">デスクトップで Skype for Business にサインインします。</span><span class="sxs-lookup"><span data-stu-id="874dc-185">Sign in to Skype for Business on your desktop.</span></span>
    
2. <span data-ttu-id="874dc-186"> *\*Settings** > *\*Tools** > *\*Options** を選択します。</span><span class="sxs-lookup"><span data-stu-id="874dc-186">Choose **Settings** > **Tools** > **Options**.</span></span> 
    
     ![電話番号を表示するには、設定 > ツール > オプション。](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. <span data-ttu-id="874dc-188">次に、[ **電話**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="874dc-188">Then choose **Phones**.</span></span> 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
<span data-ttu-id="874dc-p113">In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.</span><span class="sxs-lookup"><span data-stu-id="874dc-p113">In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.</span></span>

![ユーザーは、左側のナビゲーションで呼び出しをクリックすると、Microsoft Teams で番号を確認できます。](media/teams-phone-number.png)

<span data-ttu-id="874dc-193">**通話プランを設定する手順すべての詳細については、 [通話プランの設定](set-up-calling-plans.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="874dc-193">**For more detailed information about all of the steps involved in setting up a Calling Plan, see [Set up Calling Plans](set-up-calling-plans.md).**</span></span>


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a><span data-ttu-id="874dc-194">手順 6: 電話会議を設定する場合</span><span class="sxs-lookup"><span data-stu-id="874dc-194">Step 6: If you want to set up Audio Conferencing</span></span>

<span data-ttu-id="874dc-p114">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span><span class="sxs-lookup"><span data-stu-id="874dc-p114">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span>

<span data-ttu-id="874dc-p115">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="874dc-p115">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="874dc-200">電話会議についてよく寄せられる質問については、 [電話会議についてよくある質問](audio-conferencing-common-questions.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="874dc-200">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>
    
1. <span data-ttu-id="874dc-201"> *\*電話会議** アドオンライセンスとコミュニケーション クレジットライセンスを購入した場合は、それらも割り当てます。</span><span class="sxs-lookup"><span data-stu-id="874dc-201">If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too.</span></span> <span data-ttu-id="874dc-202">手順については、[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="874dc-202">For instructions, see [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

    <span data-ttu-id="874dc-p117">Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:</span><span class="sxs-lookup"><span data-stu-id="874dc-p117">Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:</span></span>

    > [!NOTE]
    > <span data-ttu-id="874dc-207">Microsoft Teams のユーザーには、Microsoft 以外の電話会議プロバイダーを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="874dc-207">Microsoft Teams users can't user a third-party audio conferencing provider.</span></span>

    - <span data-ttu-id="874dc-208">**電話会議プロバイダーとしての Microsoft**: 電話会議の最も簡単なソリューションをお求めなら、電話会議プロバイダーとして Microsoft を選択します。</span><span class="sxs-lookup"><span data-stu-id="874dc-208">**Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.</span></span>
    
    - <span data-ttu-id="874dc-p118">**Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).</span><span class="sxs-lookup"><span data-stu-id="874dc-p118">**Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).</span></span>
 
2. <span data-ttu-id="874dc-p119">Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="874dc-p119">Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

3. <span data-ttu-id="874dc-p120">Set up meeting invitations. The following steps are optional, but a lot of admins like to do them:</span><span class="sxs-lookup"><span data-stu-id="874dc-p120">Set up meeting invitations. The following steps are optional, but a lot of admins like to do them:</span></span> 
  
   1. <span data-ttu-id="874dc-215">[ビジネス用の Skype でミーティングの招待状をカスタマイズ](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)します。</span><span class="sxs-lookup"><span data-stu-id="874dc-215">[Customize meeting invitations in Skype for Business](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations).</span></span> <span data-ttu-id="874dc-216">ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議出席依頼に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="874dc-216">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to attendees.</span></span> <span data-ttu-id="874dc-217">ただし、独自のヘルプや法務関連リンク、テキスト メッセージ、会社の小さな画像を追加できます。</span><span class="sxs-lookup"><span data-stu-id="874dc-217">However, you can add your own help and legal links, a text message, and small company graphic.</span></span>
    
   2. <span data-ttu-id="874dc-218">[ビジネス用の Skype](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)または[マイクロソフトのチームで](set-the-phone-numbers-included-on-invites-in-teams.md)ミーティングの開催者に含まれているへの招待には、電話会議の電話番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="874dc-218">Set the Audio Conferencing phone numbers for meeting organizers that are included on invites [in Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) or [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span> <span data-ttu-id="874dc-219">これは、ユーザーが開催を予定している会議で表示される電話番号です。</span><span class="sxs-lookup"><span data-stu-id="874dc-219">This is the phone number that will show up in the meeting that is scheduled by the user.</span></span>
    
   3. <span data-ttu-id="874dc-220">[ビジネス用の Skype で](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing)電話会議、または[マイクロソフトのチームで](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)の電話会議の電話番号にダイヤルするときに、呼び出し元を呼びかけられるように設定するのには、オーディオ会議自動アテンダントを使用するには、自動アテンダントの言語を設定します。</span><span class="sxs-lookup"><span data-stu-id="874dc-220">Set auto attendant languages for Audio Conferencing [in Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) or [in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number.</span></span> <span data-ttu-id="874dc-221">この手順は、Microsoft を電話会議プロバイダーとして使用している場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="874dc-221">This step only applies if you're using Microsoft as your audio provider.</span></span>
    
   4. <span data-ttu-id="874dc-222">オーディオ会議の会議の暗証番号 (pin) の長さを設定[では、マイクロソフトのチーム](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)です。</span><span class="sxs-lookup"><span data-stu-id="874dc-222">Set the length of the PIN for Audio Conferencing meetings [in Microsoft Teams](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md).</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="874dc-p124">This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span><span class="sxs-lookup"><span data-stu-id="874dc-p124">This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span></span>

<span data-ttu-id="874dc-225">**オーディオ会議の詳細については、[マイクロソフトのチームでのオーディオ会議を設定](set-up-audio-conferencing-in-teams.md)を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="874dc-225">**For more information about Audio Conferencing, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).**</span></span>

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a><span data-ttu-id="874dc-226">手順 7: クラウドの呼び出しキューを設定する場合は、</span><span class="sxs-lookup"><span data-stu-id="874dc-226">Step 7: If you want to set up a Cloud call queue</span></span>

<span data-ttu-id="874dc-227">クラウド呼び出しキューには、自動的に保留中の呼び出しを配置することなどを検索する機能の呼び出しとなっている人の中に呼び出しを処理するために次の呼び出しを使用可能なエージェントのための電話番号への呼び出し際に使用するあいさつ文が含まれます保留中の音楽を聴きます。</span><span class="sxs-lookup"><span data-stu-id="874dc-227">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="874dc-228">組織の 1 つまたは複数の呼び出しキューを作成します。</span><span class="sxs-lookup"><span data-stu-id="874dc-228">You can create single or multiple call queues for your organization.</span></span>

<span data-ttu-id="874dc-p126">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="874dc-p126">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="874dc-p127">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span><span class="sxs-lookup"><span data-stu-id="874dc-p127">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="874dc-234">**Skype**で、新しい呼び出しキューを作成するに**呼のルーティング**] をクリックします > **キューを呼び出す**と、**新規追加**] をクリックし[クラウド呼び出しキューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue)は、**手順 3**の指示に従って操作します。</span><span class="sxs-lookup"><span data-stu-id="874dc-234">To create a new call queue, in the **Skype for Business admin center**, click **Call routing** > **Call queues**, click **Add new**, and then follow the instructions in **Step 3** of  [Create a Cloud call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue).</span></span>

<span data-ttu-id="874dc-235">**呼び出しキューの詳細については、[クラウド呼び出しキューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="874dc-235">**For more details about call queues, see [Create a Cloud call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).**</span></span>

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a><span data-ttu-id="874dc-236">手順 8: クラウドを設定する場合は、自動的に応答</span><span class="sxs-lookup"><span data-stu-id="874dc-236">Step 8: If you want to set up a Cloud auto attendant</span></span>

<span data-ttu-id="874dc-p128">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center.</span><span class="sxs-lookup"><span data-stu-id="874dc-p128">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center.</span></span>

<span data-ttu-id="874dc-239">作成する新しい自動アテンダントでは、ビジネス管理センターの Skype で**呼のルーティング**] をクリックします > **自動応答**を**新規追加**] をクリックし、クラウドの自動応答を[セットの**ステップ 2**では、各ページの指示に従って](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="874dc-239">To create a new auto attendant, in the Skype for Business admin center, click **Call routing** > **Auto attendants**, click **Add new**, and then follow the instructions for each page in **Step 2** of [Set up a Cloud auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).</span></span>

<span data-ttu-id="874dc-240">**クラウドの自動応答の詳細については、[クラウドの自動応答の設定](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="874dc-240">**For more details about Cloud auto attendants, see [Set up a Cloud auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).**</span></span>

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="874dc-241">手順 9: サービス用電話番号 (電話会議、通話キュー、自動応答) の割り当て</span><span class="sxs-lookup"><span data-stu-id="874dc-241">Step 9: Assign service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="874dc-p129">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.</span><span class="sxs-lookup"><span data-stu-id="874dc-p129">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.</span></span>

- <span data-ttu-id="874dc-244">電話会議用に専用番号を会議用ブリッジに割り当てることができます。それには、 **Office 365 の管理センター** > **管理センター** > **Skype for Business** > **電話会議** に進み、会議ブリッジをクリックするか、 [電話会議ブリッジ上の有料・無料番号を変更する](change-the-phone-numbers-on-your-audio-conferencing-bridge.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="874dc-244">For Audio Conferencing, you can assign a dedicated number to a conferencing bridge by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** and click on the conference bridge or by seeing  [Change the toll or toll-free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

- <span data-ttu-id="874dc-245">自動応答では、自動アテンダントに専用番号を割り当てることができます。それには、  **Office 365 の管理センター** > **管理センター** > **Skype for Business** > **通話ルーティング** > **自動応答** に進み、自動応答 をクリックします。</span><span class="sxs-lookup"><span data-stu-id="874dc-245">For Auto Attendants, you can assign a dedicated number to an auto attendant by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Auto attendants** and click on the auto attendant.</span></span> <span data-ttu-id="874dc-246">既存のサービス番号は、 **全般** ページの **電話番号** ドロップダウンのリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="874dc-246">On the **General** page the service number you already have will be listed in the **Phone number** drop down.</span></span> <span data-ttu-id="874dc-247">詳細については、[クラウドの自動応答の設定](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="874dc-247">For details, see [Set up a Cloud Auto Attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).</span></span>

- <span data-ttu-id="874dc-248">通話キューでは、通話キューに専用番号を割り当てることができます。それには、  **Office 365 の管理センター** > **管理センター** > **Skype for Business** > **通話ルーティング** > **通話キュー** と進み、「通話キュー」をクリックします。</span><span class="sxs-lookup"><span data-stu-id="874dc-248">For Call Queues, you can assign a dedicated number to a call queue by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Call queues** and click on the call queue.</span></span> <span data-ttu-id="874dc-249">既存のサービス番号は、 **全般** ページの **電話番号** ドロップダウンのリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="874dc-249">On the **General** page the service number you already have will be listed in the **Phone number** drop down.</span></span> <span data-ttu-id="874dc-250">詳細については、[クラウドの呼び出しキューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="874dc-250">For details, see [Create a Cloud call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span></span>

<span data-ttu-id="874dc-251">**新しいサービス番号を取得し、既存のサービス番号を転送する方法の詳細については、 [サービスの電話番号の取得](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)  を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="874dc-251">**For detailed information about getting new service numbers and porting existing service numbers, see [Getting service phone numbers](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers).**</span></span>

## <a name="step-10-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="874dc-252">通信のクレジット、組織の設定手順 10。</span><span class="sxs-lookup"><span data-stu-id="874dc-252">Step 10: Set up Communications Credits for your organization</span></span>

<span data-ttu-id="874dc-p132">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="874dc-p132">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="874dc-258">費用を確認するには、[こちらで料金をご覧ください](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。</span><span class="sxs-lookup"><span data-stu-id="874dc-258">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span>

### <a name="to-set-up-communications-credits"></a><span data-ttu-id="874dc-259">通信のクレジットを設定するには</span><span class="sxs-lookup"><span data-stu-id="874dc-259">To set up Communications Credits</span></span>

1. <span data-ttu-id="874dc-260">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="874dc-260">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="874dc-261">Office 365 管理ページ左側のナビゲーションで  **請求** > **サブスクリプション** > **アドオン** > **アドオンの購入** に進み、 **コミュニケーションクレジット** > **今すぐ購入** を選択してください。</span><span class="sxs-lookup"><span data-stu-id="874dc-261">In the left navigation of the Office 365 admin center, go to **Billing** > **Subscriptions** > **Add-ons** > **Buy add-ons**, and then choose **Communications Credits** > **Buy now**.</span></span>

3. <span data-ttu-id="874dc-262">**通信のクレジット**申し込みのページでの情報を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="874dc-262">On the **Communications Credits** subscription page, fill in your information, and then click **Next**.</span></span>

4. <span data-ttu-id="874dc-263">支払い情報を入力して、[ **注文**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="874dc-263">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="874dc-p133">If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span><span class="sxs-lookup"><span data-stu-id="874dc-p133">If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="874dc-267">**コミュニケーションクレジットの設定に関する詳細については、 [組織のコミュニケーションクレジットを設定](set-up-communications-credits-for-your-organization.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="874dc-267">**For more detailed information about setting up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).**</span></span>
  
### <a name="assign-a-communications-credits-license-to-users"></a><span data-ttu-id="874dc-268">通信のクレジットのライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="874dc-268">Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="874dc-269">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="874dc-269">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="874dc-270">Office 365 管理ページの左側のナビゲーションで、 **ユーザー** > **アクティブなユーザー** に進み、そのリストから一人、または複数のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="874dc-270">In the left navigation of the Office 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>

3. <span data-ttu-id="874dc-271">操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="874dc-271">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="874dc-272">[**製品ライセンス**] ページで、**上**、本ライセンスを割り当てるには、**通信のクレジット**を切り替えるし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="874dc-272">On the **Product licenses** page, toggle **Communications Credits** to **On** to assign this license, and then click **Save**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="874dc-273">**Enterprise E5** ライセンスが割り当てられているユーザーがいる場合でも、この手順を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="874dc-273">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>

<span data-ttu-id="874dc-274">**コミュニケーションクレジットのライセンスの割り当ての詳細については、 [組織用コミュニケーションクレジットの設定](set-up-communications-credits-for-your-organization.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="874dc-274">**To learn more about assigning Communications Credits licenses, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).**</span></span>

## <a name="related-topics"></a><span data-ttu-id="874dc-275">関連トピック</span><span class="sxs-lookup"><span data-stu-id="874dc-275">Related topics</span></span>
[<span data-ttu-id="874dc-276">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="874dc-276">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="874dc-277">Skype for Business および Microsoft Teams のサービス電話番号の取得</span><span class="sxs-lookup"><span data-stu-id="874dc-277">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[<span data-ttu-id="874dc-278">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="874dc-278">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
