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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '組織の電話システム (クラウド PBX) の設定方法について説明します。 '
ms.openlocfilehash: 402ae5f92e72cd1bc7ab759d3706108480a27a7e
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925298"
---
# <a name="setting-up-phone-system-in-your-organization"></a><span data-ttu-id="ca417-103">組織内の電話システムの設定</span><span class="sxs-lookup"><span data-stu-id="ca417-103">Setting up Phone System in your organization</span></span>

<span data-ttu-id="ca417-p101">以下は、Office 365 で電話システムを設定するための手順ガイドです。各手順の最後に、追加の詳細情報へのリンクが提供されています。</span><span class="sxs-lookup"><span data-stu-id="ca417-p101">The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.</span></span>

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a><span data-ttu-id="ca417-106">ステップ 1: 電話システムは、国または地域で利用可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ca417-106">Step 1: Make sure that Phone System is available in your country or region</span></span>

1.  <span data-ttu-id="ca417-107">最初に [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) へ進み、ページの上部にある一覧表から国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca417-107">First go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page.</span></span> 
2.  <span data-ttu-id="ca417-108"> **電話システム** での機能と詳細の一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="ca417-108">Under **Phone System**, review the list of features and details.</span></span> 
3.  <span data-ttu-id="ca417-109">電話システムが使用可能な場合は、手順 2 に進みます。</span><span class="sxs-lookup"><span data-stu-id="ca417-109">If Phone System is available, go to step 2.</span></span> 

<span data-ttu-id="ca417-110">**電話システムおよびオーディオ会議の地域別利用可能時間に関する詳細については、 [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="ca417-110">**To learn more about regional availability of Phone System and Audio Conferencing, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**</span></span>

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a><span data-ttu-id="ca417-111">手順 2: 電話システムおよび通話プランのライセンスを購入し、割り当てる</span><span class="sxs-lookup"><span data-stu-id="ca417-111">Step 2: Buy and assign Phone System and Calling Plan licenses</span></span>

<span data-ttu-id="ca417-p102">電話システムと通話プランのライセンスを 1 人のユーザーに割り当てるには、Office 365 ライセンスの割り当ての手順と同じです。「[Microsoft Teams ライセンスを割り当てる](assign-teams-licenses.md)」を参照してください。複数のユーザーをまとめて割り当てる場合は、「[Microsoft Teams ライセンスを割り当てる](assign-teams-licenses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p102">To assign a Phone System and Calling Plan license to a single user the steps are the same as assigning an Office 365 license. See [Assign Microsoft Teams licenses](assign-teams-licenses.md). If you want to assign multiple users in bulk, see [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

## <a name="step-3-get-phone-numbers-for-your-users"></a><span data-ttu-id="ca417-115">ステップ 3: ユーザー向けの電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="ca417-115">Step 3: Get phone numbers for your users</span></span>

<span data-ttu-id="ca417-116">組織内でユーザーを設定し、電話を掛けたり受けたりする前に、ユーザーの電話番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca417-116">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>

<span data-ttu-id="ca417-117">ユーザー用の番号を取得するには、次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="ca417-117">You have three ways of getting numbers for your users:</span></span>
- <span data-ttu-id="ca417-118">Skype for Business 管理センターを使用して新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="ca417-118">Get new numbers using the Skype for Business admin center.</span></span>
- <span data-ttu-id="ca417-119">Skype for Business管理センターでは使用できない、新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="ca417-119">Get new numbers that aren't available in the Skype for Business admin center.</span></span>
- <span data-ttu-id="ca417-120">既存の番号を現在のサービス プロバイダーまたは電話会社から Office 365 に移行または転送します。</span><span class="sxs-lookup"><span data-stu-id="ca417-120">Port or transfer your existing numbers from your current service provider or phone carrier to Office 365.</span></span>

<span data-ttu-id="ca417-p103">新しいユーザー番号を表示、検索、取得、および予約するには、[**新しいユーザー番号を追加**] ページを使用する必要があります。国/地域、都道府県、市区町村で検索し、ユーザー用に必要な電話番号の数を入力できます。</span><span class="sxs-lookup"><span data-stu-id="ca417-p103">You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span></span>

### <a name="get-new-user-phone-numbers"></a><span data-ttu-id="ca417-123">新しいユーザー電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="ca417-123">Get new user phone numbers</span></span> 
 
<span data-ttu-id="ca417-124">**Skype for Business 管理センターを使って** ![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png)</span><span class="sxs-lookup"><span data-stu-id="ca417-124">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="ca417-125">職場または学校のアカウントを使用して、Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ca417-125">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="ca417-126">**Microsoft 365 管理センター** > **Skype for Business** に移動します。</span><span class="sxs-lookup"><span data-stu-id="ca417-126">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="ca417-127">左のナビゲーションで、[**音声** > **電話番号**] に移動し、[追加] ボタン**をクリック** ![してプラス](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)記号として表示し、[**新しいユーザー番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca417-127">In the left navigation go to **Voice** > **Phone numbers**, click **Add new number** ![The Add button, displayed as a plus symbol](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png), and then click **New user numbers**.</span></span>
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a><span data-ttu-id="ca417-128">Skype for Business管理センターでは使用できない、新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="ca417-128">Get new numbers that aren't available in the Skype for Business admin center</span></span>
  
<span data-ttu-id="ca417-p104">ご利用国/地域によっては、Skype for Business 管理センターを使用して新しい番号を取得できない場合があります。その場合は、フォームをダウンロードし、記入したフォームを Microsoft に送付する必要があります。新しいユーザー番号をリクエストする方法の詳細については、「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p104">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.</span></span>   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="ca417-132">サービス プロバイダーまたは電話会社から電話番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="ca417-132">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="ca417-p105">ユーザーの電話番号を999以上にする必要がある場合は、Skype for Business 管理センターの新しい電話番号の**ポート注文**ウィザードを使用できます。「電話[番号をチームに転送](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)して電話番号を転送する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ca417-p105">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center. Follow the steps found in [Transfer phone numbers to  Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to transfer your phone numbers.</span></span>
    
- <span data-ttu-id="ca417-135">電話番号が 999 個よりも多い電話番号を移行する必要がある場合は、「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照して移行注文サービスの依頼または注文を発行し、Office 365 に移行される電話番号をすべて取得します。</span><span class="sxs-lookup"><span data-stu-id="ca417-135">If you need to port more than 999 phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order to get all of these phone numbers ported over to Office 365.</span></span> 

<span data-ttu-id="ca417-136">**新しい電話番号を取得するか、既存の番号を転送する方法の詳細については、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="ca417-136">**For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).**</span></span>

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="ca417-137">手順 4: サービス用の電話番号 (電話会議、通話キュー、自動応答) を取得します。</span><span class="sxs-lookup"><span data-stu-id="ca417-137">Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="ca417-p106">Office 365 ユーザー用の電話番号の取得に加え、電話会議 (会議ブリッジ用)、自動応答、通話キュー (別名: サービス番号) などのサービス用に、有料または無料電話番号を検索し、取得できます。ユーザーまたはサブスクライバーの電話番号に比べて、サービス電話番号はより高い同時通話の処理能力を持ちます。たとえば、ユーザーの電話番号 1 つが同時に取り扱える通話数はごく少数なのに対して、1 つのサービス番号は何百もの通話を同時に取り扱えます。</span><span class="sxs-lookup"><span data-stu-id="ca417-p106">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>

### <a name="get-new-service-numbers"></a><span data-ttu-id="ca417-141">新しいサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="ca417-141">Get new service numbers</span></span>

<span data-ttu-id="ca417-142">**Skype for Business 管理センターを使って** ![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png)</span><span class="sxs-lookup"><span data-stu-id="ca417-142">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>


1. <span data-ttu-id="ca417-143">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ca417-143">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="ca417-144">**Microsoft 365 管理センター** > **Skype for Business** に移動します。</span><span class="sxs-lookup"><span data-stu-id="ca417-144">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="ca417-145">In the left navigation go to **Voice** > **Phone numbers** > **Add** then click **New service numbers**.</span><span class="sxs-lookup"><span data-stu-id="ca417-145">In the left navigation go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ca417-146">Skype for Business 管理センターの左のナビゲーションに [**音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム**アドオン ライセンス、または**電話会議**アドオン ライセンスを少なくとも 1 件購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca417-146">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a><span data-ttu-id="ca417-147">Skype for Business管理センターでは使用できない、新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="ca417-147">Get new numbers that aren't available in the Skype for Business admin center</span></span>
  
<span data-ttu-id="ca417-p107">ご利用国/地域によっては、Skype for Business 管理センターを使用して新しい番号を取得できない場合があります。その場合は、フォームをダウンロードし、記入したフォームを Microsoft に送付する必要があります。新しい番号をリクエストする方法の詳細については、「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p107">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers.</span></span> 

### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="ca417-151">既存のサービス番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="ca417-151">Port or transfer existing service numbers</span></span>

<span data-ttu-id="ca417-p108">現在のサービス プロバイダーまたは通信事業者からサービス番号を移動する場合は、ポートの注文を手動で Microsoft に送信する必要があります。承認状 (LOA) を使用して、移動するサービス番号の種類 (有料電話番号または無料電話番号) ごとに別々のポート注文を送信する必要があります。承認状 (LOA) では、適切な種類のサービス番号が選択されている必要があります。Microsoft サポートに連絡する際は、移動する番号は*ユーザーまたはサブスクライバーの番号ではなく*、サービス番号であることを必ず指定してください。これを指定しない場合、実際の通話件数を処理するには同時通話処理能力が不十分なものになる可能性があります。電話番号の移動や電話番号に関するその他の手続きを行うには、「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p108">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a><span data-ttu-id="ca417-157">手順 5: 通話プランを設定する場合</span><span class="sxs-lookup"><span data-stu-id="ca417-157">Step 5: If you want to set up Calling Plans</span></span>

<span data-ttu-id="ca417-p109">上記の手順を実行すると、電話システムと通話プランのライセンスの購入と割り当て (手順 2) およびユーザー用の電話番号の取得 (手順 3) が完了したことになり、通話プランのセットアップは部分的に完了しています。通話プランのセットアップを完了するには、次の 3 つの手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p109">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.</span></span>

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a><span data-ttu-id="ca417-160">組織の緊急連絡先と場所を追加する</span><span class="sxs-lookup"><span data-stu-id="ca417-160">Add emergency addresses and locations for your organization</span></span>

1. <span data-ttu-id="ca417-161">[**音声**] ページで、[**緊急対応の場所**]  >  [**新しいアドレスを追加**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ca417-161">On the **Voice** page, choose **Emergency locations** > **Add new address**.</span></span>

2. <span data-ttu-id="ca417-162">[**新しい住所**] ウィンドウで、住所の名前を入力し、残りのボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="ca417-162">In the **New Address** pane, enter a name for your address, and then complete the remaining boxes.</span></span>
    
     ![[新しい住所] ウィンドウのスクリーンショット](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > <span data-ttu-id="ca417-164">上の図のように、英語圏のお客様で街路名が数字の場合は、必ず末尾に「st」または「th」を付けます。</span><span class="sxs-lookup"><span data-stu-id="ca417-164">For English customers, if the street name is a number, be sure to include "st" or "th" at the end, as shown in the above picture.</span></span>

3. <span data-ttu-id="ca417-165">[ **検証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca417-165">Choose **Validate**.</span></span>

    <span data-ttu-id="ca417-166">必要な場合は、住所の訂正を求められます。</span><span class="sxs-lookup"><span data-stu-id="ca417-166">If needed, you'll be prompted to make corrections to the address.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="ca417-p110">住所や番地を確認できるよう、正当な住所が正しい形式で入力されている必要があります。部分的に正しい緊急対応用の住所 (たとえば、市名の綴りが間違っていたなど) でも住所確認が取れる場合があります。綴りに間違いがあっても住所確認が取れた場合は、綴りの間違った市名と住所情報の他の部分を組み合わせることで、通話を適切な緊急出動センターにルーティングするのに十分な情報があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ca417-p110">Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center.</span></span>

    > [!TIP]
    > <span data-ttu-id="ca417-170">緊急応答用に住所に修正が必要な場合は、住所が更新されたことを通知する緑色のバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca417-170">If the address needs to be corrected for emergency response, a green banner will appear notifying you that the address was updated.</span></span>

4. <span data-ttu-id="ca417-171">住所が検証されたら、[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ca417-171">After the address is validated, choose **Save**.</span></span>

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a><span data-ttu-id="ca417-172">ユーザーに電話番号と緊急連絡先を割り当てる</span><span class="sxs-lookup"><span data-stu-id="ca417-172">Assign phone numbers and emergency addresses to users</span></span>

> [!TIP]
> <span data-ttu-id="ca417-p111">この手順を実行する直前にさらにユーザーを追加すると、[ **音声ユーザー**] ページにユーザーが表示されるまでに **数時間** かかることがあります。これには遅延時間があります。</span><span class="sxs-lookup"><span data-stu-id="ca417-p111">If you add more people to your business right before doing this step, it may take **several hours** for them to appear on the **Voice users** page. There's a latency.</span></span>

1. <span data-ttu-id="ca417-175">[**音声ユーザー**] ページで、電話番号と緊急連絡先を割り当てるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca417-175">On the **Voice users** page, select the people who you want to assign a phone number and emergency address to.</span></span>

2. <span data-ttu-id="ca417-176">[操作] ウィンドウで、 **割り当てる番号** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca417-176">In the Action pane, click **Assign number**.</span></span>

3. <span data-ttu-id="ca417-177">[**番号を割り当てる**] ページの [ **割り当てる番号を選択**] リストで、ユーザー用の電話番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca417-177">On the **Assign number** page, in the **Select number to assign** list, select the phone number for the user.</span></span>

4. <span data-ttu-id="ca417-178">緊急連絡先を選ぶには、ボックスに市区町村の名前を入力し、[**検索**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca417-178">To select an emergency address, enter name of the city in the box and choose **Search**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ca417-p112">米国以外の場合は電話番号に緊急対応の住所がすでに関連付けられていますが、この住所は変更できます。詳細については、「[ユーザーの緊急対応の住所の割り当てまたは変更](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p112">If you are outside the United States, your numbers already have an emergency address, but you can change it now. See [Assign or change an emergency address for a user](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user).</span></span> 
  
5. <span data-ttu-id="ca417-181">電話番号と緊急連絡先の両方を割り当てたら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca417-181">After you assign both the phone number and emergency address, choose **Save**.</span></span>

### <a name="tell-your-users-about-their-new-phone-numbers"></a><span data-ttu-id="ca417-182">新しい電話番号をユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="ca417-182">Tell your users about their new phone numbers</span></span>


<span data-ttu-id="ca417-183">メールを送信するか、会社の適切な連絡方法を使用して、ユーザーに新しい電話番号を伝えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ca417-183">We recommend sending mail or using your business's preferred communication method to tell the people about their new phone numbers.</span></span>

<span data-ttu-id="ca417-184">次に、ユーザーの **Skype for Business** アプリに電話番号がどのように表示されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="ca417-184">Here's how they can see that phone number in their **Skype for Business** app:</span></span>

1. <span data-ttu-id="ca417-185">デスクトップで Skype for Business にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ca417-185">Sign in to Skype for Business on your desktop.</span></span>
    
2. <span data-ttu-id="ca417-186"> **Settings** > **Tools** > **Options** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca417-186">Choose **Settings** > **Tools** > **Options**.</span></span> 
    
     ![[ツール] メニューの [オプション] のスクリーンショット](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. <span data-ttu-id="ca417-188">次に、[ **電話**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ca417-188">Then choose **Phones**.</span></span> 
    
    ![Skype for Business 電話のオプションのスクリーンショット](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
<span data-ttu-id="ca417-p113">**Microsoft Teams** では、ユーザーは左側のナビゲーションで [**通話**] をクリックすると、自分の電話番号を表示できます。電話番号はダイヤル パッドの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca417-p113">In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.</span></span>

![[通話] をクリックした後に使用できるオプションのスクリーンショット](media/teams-phone-number.png)

<span data-ttu-id="ca417-193">**通話プランを設定する手順すべての詳細については、 [通話プランの設定](set-up-calling-plans.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="ca417-193">**For more detailed information about all of the steps involved in setting up a Calling Plan, see [Set up Calling Plans](set-up-calling-plans.md).**</span></span>


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a><span data-ttu-id="ca417-194">手順 6: 電話会議を設定する場合</span><span class="sxs-lookup"><span data-stu-id="ca417-194">Step 6: If you want to set up Audio Conferencing</span></span>

<span data-ttu-id="ca417-p114">組織のメンバーが電話で会議に参加することが必要になる場合があります。Skype for Business と Microsoft Teams では、このようなシチュエーションで活用できる電話会議機能が提供されています。ユーザーは、モバイル デバイスや PC 上の Skype for Business アプリまたは Microsoft Teams アプリを使用することなく、電話を使用して Skype for Business または Microsoft Teams の会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="ca417-p114">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span>

<span data-ttu-id="ca417-p115">電話会議の設定は、会議のスケジュールを設定または会議を進行するユーザーに対してのみ必要です。ダイヤルインで参加するユーザーについては、ライセンスの割り当てや他の設定は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ca417-p115">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="ca417-200">電話会議についてよく寄せられる質問については、 [電話会議についてよくある質問](audio-conferencing-common-questions.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-200">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>
    
1. <span data-ttu-id="ca417-p116">**電話会議**アドオンのライセンスやコミュニケーション クレジットのライセンスを購入した場合は、これらも割り当てます。手順については、「[Microsoft Teams ライセンスを割り当てる](assign-teams-licenses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p116">If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too. For instructions, see [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

    <span data-ttu-id="ca417-p117">電話会議のプロバイダーを決めます。電話会議のプロバイダーは、電話会議ブリッジを提供します。会議のダイヤルイン電話番号、PIN、および会議 ID は、会議ブリッジで設定されます。Microsoft とサード パーティの電話会議プロバイダーのどちらを使用するかを決めます。</span><span class="sxs-lookup"><span data-stu-id="ca417-p117">Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca417-207">Microsoft Teams のユーザーには、Microsoft 以外の電話会議プロバイダーを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="ca417-207">Microsoft Teams users can't user a third-party audio conferencing provider.</span></span>

    - <span data-ttu-id="ca417-208">**電話会議プロバイダーとしての Microsoft**: 電話会議の最も簡単なソリューションをお求めなら、電話会議プロバイダーとして Microsoft を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca417-208">**Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.</span></span>
    
    - <span data-ttu-id="ca417-p118">**サード パーティの電話会議プロバイダーの使用**: Office 365 の電話会議が利用できない国の場合、サービスの品質が低い地域の場合、または既存の契約がある場合、サード パーティの電話会議プロバイダーを選択してください。プロバイダーを検索するには、 [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p118">**Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).</span></span>
 
2. <span data-ttu-id="ca417-p119">会議を進行またはスケジュール設定するユーザーに、電話会議プロバイダーを割り当てます。詳細については、「[Microsoft を電話会議プロバイダーとして割り当てる](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p119">Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

3. <span data-ttu-id="ca417-p120">会議の出席依頼を設定します。次の手順は省略可能ですが、多くの管理者は実行しています。</span><span class="sxs-lookup"><span data-stu-id="ca417-p120">Set up meeting invitations. The following steps are optional, but a lot of admins like to do them:</span></span> 
  
   1. <span data-ttu-id="ca417-p121">[Skype for Business の会議の出席依頼をカスタマイズします](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)。出席者に送信される会議の出席依頼には、ユーザーに設定されているダイヤルイン番号が自動的に追加されますが、独自のヘルプ、法的事項へのリンク、テキスト メッセージ、および小さな会社ロゴを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ca417-p121">[Customize meeting invitations in Skype for Business](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations). The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to attendees. However, you can add your own help and legal links, a text message, and small company graphic.</span></span>
    
   2. <span data-ttu-id="ca417-p122">[Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) または [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) の招待状に記載される会議の開催者に、電話会議の電話番号を設定します。この電話番号は、ユーザーがスケジュールする会議に表示される電話番号です。</span><span class="sxs-lookup"><span data-stu-id="ca417-p122">Set the Audio Conferencing phone numbers for meeting organizers that are included on invites [in Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) or [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md). This is the phone number that will show up in the meeting that is scheduled by the user.</span></span>
    
   3. <span data-ttu-id="ca417-p123">[Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) または [Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) の電話会議での自動応答言語を設定します。これは、電話会議の電話番号にダイヤルインしてくる発信者への自動応答の挨拶で使用される言語です。この手順は、電話会議プロバーダーに Microsoft を使用している場合にのみ当てはまります。</span><span class="sxs-lookup"><span data-stu-id="ca417-p123">Set auto attendant languages for Audio Conferencing [in Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) or [in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number. This step only applies if you're using Microsoft as your audio provider.</span></span>
    
   4. <span data-ttu-id="ca417-222">[Microsoft Teams で](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)電話会議用の PIN の長さを設定します。</span><span class="sxs-lookup"><span data-stu-id="ca417-222">Set the length of the PIN for Audio Conferencing meetings [in Microsoft Teams](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md).</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="ca417-p124">この機能は、21Vianet が運営する Office 365 を中国で使用しているお客様にはまだご利用いただけません。詳細については、「 [21Vianet が運営する Office 365 について](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p124">This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span></span>

<span data-ttu-id="ca417-225">**電話会議の詳細については、「[Microsoft Teams の電話会議を設定する](set-up-audio-conferencing-in-teams.md)」を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="ca417-225">**For more information about Audio Conferencing, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).**</span></span>

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a><span data-ttu-id="ca417-226">手順 7: クラウドの通話キューを設定する場合</span><span class="sxs-lookup"><span data-stu-id="ca417-226">Step 7: If you want to set up a Cloud call queue</span></span>

<span data-ttu-id="ca417-p125">クラウド通話キューには、誰かが組織の電話番号に電話をかけた際に流れる挨拶メッセージ、通話を自動的に保留する機能、および保留中に電話をかけてきた方に音楽を流し、その間に通話への対応が可能な次の電話エージェントを探す機能が含まれています。1 つまたは複数の通話キューを組織のために作成できます。</span><span class="sxs-lookup"><span data-stu-id="ca417-p125">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span></span>

<span data-ttu-id="ca417-p126">通話キューを作成して設定する前に、既存の有料または無料のサービス番号を取得または移行する必要があります。有料またはフリーダイヤルのサービス電話番号を取得すると、 **Skype for business 管理センター** > **ボイス** > **電話番号**に表示され、一覧表示されている**番号の種類**が**有料サービスとして表示されます。**.サービス番号を取得するには、「 [Skype For business および Microsoft Teams のサービス電話番号を取得](/microsoftteams/getting-service-phone-numbers)する」または「既存のサービス番号を移行する」を参照してください。「[チームに電話番号を転送](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p126">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](/microsoftteams/getting-service-phone-numbers) or if you want to transfer and existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca417-p127">米国以外の場合は、サービス番号を取得するのに Skype for Business 管理センターを使用できません。米国以外の場所でサービス番号を取得する方法については、「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p127">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="ca417-234">[**Skype for Business 管理センター**] で、新しい通話キューを作成するには、[**通話ルーティング**]  >  [**通話キュー**]、そして [**新規追加**] をクリックし、「[クラウド呼び出しキューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue)」 の**手順 3** の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="ca417-234">To create a new call queue, in the **Skype for Business admin center**, click **Call routing** > **Call queues**, click **Add new**, and then follow the instructions in **Step 3** of  [Create a Cloud call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue).</span></span>

<span data-ttu-id="ca417-235">**通話キューの詳細については、[[クラウド通話キューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)] を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="ca417-235">**For more details about call queues, see [Create a Cloud call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).**</span></span>

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a><span data-ttu-id="ca417-236">手順 8: クラウドの自動応答を設定する場合</span><span class="sxs-lookup"><span data-stu-id="ca417-236">Step 8: If you want to set up a Cloud auto attendant</span></span>

<span data-ttu-id="ca417-p128">自動応答は、組織に電話をかけてくる方にメニュー システムを案内し、目的の部署、通話キュー、担当者、またはオペレーターにつなげます。Skype for Business 管理センターを使用して、組織の自動応答を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ca417-p128">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center.</span></span>

<span data-ttu-id="ca417-239">新しい自動応答を作成するには、Skype for business 管理センターで、[**通話ルーティング** > の**自動応答**]、[**新規追加**] の順にクリックして、「クラウド自動応答を作成する」の**手順 2**の各ページの指示に従います。 [](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="ca417-239">To create a new auto attendant, in the Skype for Business admin center, click **Call routing** > **Auto attendants**, click **Add new**, and then follow the instructions for each page in **Step 2** of [Create a Cloud auto attendant](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).</span></span>


<span data-ttu-id="ca417-240">**クラウドの自動応答の詳細については、 「[クラウドの自動応答を設定する](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)」を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="ca417-240">**For more details about Cloud auto attendants, see [Set up a Cloud auto attendant](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).**</span></span>

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="ca417-241">手順 9: サービス用電話番号 (電話会議、通話キュー、自動応答) の割り当て</span><span class="sxs-lookup"><span data-stu-id="ca417-241">Step 9: Assign service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="ca417-p129">**上記の手順 4** で説明するサービス番号を取得したら、目的のサービスの各種類にサービス番号を割り当てる必要があります。たとえば、専用のサービス番号 (有料または無料) を使用する場合、その番号を会議ブリッジに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca417-p129">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.</span></span>

- <span data-ttu-id="ca417-244">電話会議用に専用番号を会議用ブリッジに割り当てることができます。それには、[**Microsoft 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**電話会議**] の順に進み、会議ブリッジをクリックするか、「[電話会議ブリッジ上の有料・無料番号を変更する](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-244">For Audio Conferencing, you can assign a dedicated number to a conferencing bridge by going to **Microsoft 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** and click on the conference bridge or by seeing  [Change the toll or toll-free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

- <span data-ttu-id="ca417-p130">自動応答では、 **Microsoft 365 管理センター** > **管理** > センターの**Skype for business** > **通話ルーティング** > **自動応答にアクセスして、自動応答に専用の番号を割り当てることができます。** 自動応答をクリックします。[**全般**] ページで、すでにお持ちのサービス番号が [**電話番号**] ドロップダウンに表示されます。詳細については、「[クラウド自動応答をセットアップする](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p130">For Auto Attendants, you can assign a dedicated number to an auto attendant by going to **Microsoft 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Auto attendants** and clicking on the auto attendant. On the **General** page, the service number you already have will be listed in the **Phone number** drop down. For details, see [Set up a Cloud auto attendant](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).</span></span>
- <span data-ttu-id="ca417-p131">通話キューについては、**Microsoft 365 管理センター**  >  [**管理センター**]  >  [**Skype for Business**]  >  [**通話ルーティング**]  >  [**通話キュー**] の順に移動して目的の通話キューをクリックすると、通話キューに専用番号を割り当てられます。[**一般**] ページでは、既に持っているサービス番号は [**電話番号**] ドロップ ダウンに表示されます。詳細については、「[クラウドの通話キューを作成する](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p131">For Call Queues, you can assign a dedicated number to a call queue by going to **Microsoft 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Call queues** and click on the call queue. On the **General** page the service number you already have will be listed in the **Phone number** drop down. For details, see [Create a Cloud call queue](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue).</span></span>

<span data-ttu-id="ca417-251">**新しいサービス番号を取得し、既存のサービス番号を転送する方法の詳細については、 [サービスの電話番号の取得](/microsoftteams/getting-service-phone-numbers)  を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="ca417-251">**For detailed information about getting new service numbers and porting existing service numbers, see [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).**</span></span>

## <a name="step-10-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="ca417-252">手順 10: 組織のコミュニケーション クレジットをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ca417-252">Step 10: Set up Communications Credits for your organization</span></span>

<span data-ttu-id="ca417-p132">Skype for Business または Microsoft Teams で無料番号を使用する場合は、コミュニケーション クレジットを設定する必要があります。通話プラン (国内または国際) と電話会議のユーザーのうち、**すべての発信先**にダイヤルアウトできるようにする必要があるユーザーについてもコミュニケーション クレジットを設定することをお勧めします。通話プランと電話会議のサブクリプションには多くの国や地域が含まれていますが、一部の発信先は含まれていない場合があります。コミュニケーション クレジットの請求に関する設定をせずに**コミュニケーション クレジット** ライセンスをユーザーに割り当ている状態で組織の持つ分数 (使用する国/地域の通話プランまたは電話会議プランにより異なります) が使い切られた場合、これらのユーザーは電話会議から発信またはダイヤルアウトできなくなります。推奨される入金額などの詳細情報については、「[コミュニケーション クレジットについて](what-are-communications-credits.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca417-p132">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca417-258">必要なコストを確認するには、[こちらで料金を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。</span><span class="sxs-lookup"><span data-stu-id="ca417-258">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span>

### <a name="to-set-up-communications-credits"></a><span data-ttu-id="ca417-259">コミュニケーション クレジットをセットアップするには</span><span class="sxs-lookup"><span data-stu-id="ca417-259">To set up Communications Credits</span></span>

1. <span data-ttu-id="ca417-260">職場または学校のアカウントを使用して、Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ca417-260">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="ca417-261">管理センターの左のナビゲーションで、[**課金** > \*\*\*\* > \*\*\*\* > 月額プランのアドオン] に移動**し、[\*\*\*\*通信クレジット** > の購入] を選択**します。**</span><span class="sxs-lookup"><span data-stu-id="ca417-261">In the left navigation of the admin center, go to **Billing** > **Subscriptions** > **Add-ons** > **Buy add-ons**, and then choose **Communications Credits** > **Buy now**.</span></span>

3. <span data-ttu-id="ca417-262">[**コミュニケーション クレジット**] のサブクリプションのページで、ユーザーの情報を入力し [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca417-262">On the **Communications Credits** subscription page, fill in your information, and then click **Next**.</span></span>

4. <span data-ttu-id="ca417-263">支払い情報を入力して、[**注文**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca417-263">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="ca417-p133">ボリューム ライセンスをお持ちのお客様は、支払い方法としてエンタープライズ契約番号を選択できます。エンタープライズ契約番号が複数ある場合は、支払いに使用するエンタープライズ契約番号を選択できます。(該当する場合は) エンタープライズ契約番号に関連付ける発注書番号を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca417-p133">If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="ca417-267">**コミュニケーションクレジットの設定に関する詳細については、 [組織のコミュニケーションクレジットを設定](set-up-communications-credits-for-your-organization.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="ca417-267">**For more detailed information about setting up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).**</span></span>
  
### <a name="assign-a-communications-credits-license-to-users"></a><span data-ttu-id="ca417-268">コミュニケーション クレジットのライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="ca417-268">Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="ca417-269">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ca417-269">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="ca417-270">Microsoft 365 管理センターの左側のナビゲーションで、[**ユーザー**]  >  [**アクティブなユーザー**] に進み、そのリストから一人、または複数のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca417-270">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>

3. <span data-ttu-id="ca417-271">[操作] ウィンドウの [**製品ライセンス**] で [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca417-271">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="ca417-272">このライセンスを割り当てるには、[**製品ライセンス**] ページで [**コミュニケーション クレジット**] を [**オン**] に切り替え、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca417-272">On the **Product licenses** page, toggle **Communications Credits** to **On** to assign this license, and then click **Save**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca417-273">**Enterprise E5** ライセンスが割り当てられているユーザーがいる場合でも、これを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ca417-273">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>

<span data-ttu-id="ca417-274">**コミュニケーションクレジットのライセンスの割り当ての詳細については、 [組織用コミュニケーションクレジットの設定](set-up-communications-credits-for-your-organization.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="ca417-274">**To learn more about assigning Communications Credits licenses, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).**</span></span>

## <a name="related-topics"></a><span data-ttu-id="ca417-275">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ca417-275">Related topics</span></span>
[<span data-ttu-id="ca417-276">Office 365 の電話システムでできること</span><span class="sxs-lookup"><span data-stu-id="ca417-276">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="ca417-277">Skype for Business および Microsoft Teams のサービス電話番号の取得</span><span class="sxs-lookup"><span data-stu-id="ca417-277">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="ca417-278">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="ca417-278">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
