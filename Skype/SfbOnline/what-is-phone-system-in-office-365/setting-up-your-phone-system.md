---
title: 組織内の電話システムの設定
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
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
description: '組織の電話システム (クラウド PBX) を設定する方法について説明します。 '
ms.openlocfilehash: 2566bfcef892767f89afb28643deb91942596e76
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244632"
---
# <a name="setting-up-phone-system-in-your-organization"></a><span data-ttu-id="151cf-103">組織内の電話システムの設定</span><span class="sxs-lookup"><span data-stu-id="151cf-103">Setting up Phone System in your organization</span></span>

<span data-ttu-id="151cf-104">Office 365 の電話システムを設定するためのステップ バイ ステップ ガイドは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="151cf-104">The following is a step-by-step guide for setting up Phone System in Office 365.</span></span> <span data-ttu-id="151cf-105">各手順の最後に、詳細な追加情報へのリンクを利用できます。</span><span class="sxs-lookup"><span data-stu-id="151cf-105">Links to additional, detailed information are available at the end of each step.</span></span>

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a><span data-ttu-id="151cf-106">ステップ 1: 電話システムは、国または地域で利用可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="151cf-106">Step 1: Make sure that Phone System is available in your country or region</span></span>

1.  <span data-ttu-id="151cf-107">最初に [オーディオ会議や通話プランのための国および地域の可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) へ進み、ページの上部にある一覧表から国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="151cf-107">First go to [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page.</span></span>
2.  <span data-ttu-id="151cf-108"> **電話システム** での機能と詳細の一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="151cf-108">Under **Phone System**, review the list of features and details.</span></span>
3.  <span data-ttu-id="151cf-109">電話システムが使用可能な場合は、手順 2 に進みます。</span><span class="sxs-lookup"><span data-stu-id="151cf-109">If Phone System is available, go to step 2.</span></span>

<span data-ttu-id="151cf-110">**電話システムおよびオーディオ会議の地域別利用可能時間に関する詳細については、 [オーディオ会議や通話プランのための国および地域の可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="151cf-110">**To learn more about regional availability of Phone System and Audio Conferencing, see [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**</span></span>

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a><span data-ttu-id="151cf-111">手順 2: 電話システムおよび通話プランのライセンスを購入し、割り当てる</span><span class="sxs-lookup"><span data-stu-id="151cf-111">Step 2: Buy and assign Phone System and Calling Plan licenses</span></span>

<span data-ttu-id="151cf-112">電話システムと通話プランのライセンスを 1 人のユーザーに割り当てるには、Office 365 のライセンスを割り当てるのと同じ手順をとります。</span><span class="sxs-lookup"><span data-stu-id="151cf-112">To assign a Phone System and Calling Plan license to a single user the steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="151cf-113"> [Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="151cf-113">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="151cf-114">一括で複数のユーザーを割り当てる場合は、 [Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-114">If you want to assign multiple users in bulk, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

## <a name="step-3-get-phone-numbers-for-your-users"></a><span data-ttu-id="151cf-115">手順 3: ユーザーの電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="151cf-115">Get new phone numbers for your users</span></span>

<span data-ttu-id="151cf-116">組織内でユーザーが電話を発着信できるように設定するには、ユーザーが使う電話番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-116">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>

<span data-ttu-id="151cf-117">ユーザー用の番号を取得するには、次の３つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-117">You have two ways of getting numbers for your users:</span></span>
- <span data-ttu-id="151cf-118">Skype for Business 管理センターを使用して、新しい電話番号を取得する。</span><span class="sxs-lookup"><span data-stu-id="151cf-118">Get new numbers using the Skype for Business admin center.</span></span>
- <span data-ttu-id="151cf-119">Skype for Business管理センターでは使用できない、新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="151cf-119">Get new numbers that aren't available in the Skype for Business admin center.</span></span>
- <span data-ttu-id="151cf-120">現在のサービス プロバイダーまたは携帯電話会社から Office 365 に既存の番号を移行する。</span><span class="sxs-lookup"><span data-stu-id="151cf-120">Port or transfer your existing numbers from your current service provider or phone carrier to Office 365.</span></span>

<span data-ttu-id="151cf-121"> **新しいユーザー番号を追加** ページを使用して、電話番号の確認、検索、取得、予約を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-121">You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers.</span></span> <span data-ttu-id="151cf-122">[ 国または地域]、[ 都道府県]、[ 市区町村] で検索してから、ユーザー用に必要となる電話番号の数を入力できます。</span><span class="sxs-lookup"><span data-stu-id="151cf-122">You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span></span>

### <a name="get-new-user-phone-numbers"></a><span data-ttu-id="151cf-123">新しいユーザー電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="151cf-123">Get new user phone numbers.</span></span>

<span data-ttu-id="151cf-124">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="151cf-124">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>


1. <span data-ttu-id="151cf-125">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="151cf-125">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="151cf-126"> **Office 365 管理センター** > **Skype for Business** に進みます。</span><span class="sxs-lookup"><span data-stu-id="151cf-126">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="151cf-127">左側のナビゲーションで**音声** > **電話番号** に進み、**新しい番号を追加**![ボタンを追加](../images/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png) をクリックし、**新しいユーザーの番号** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="151cf-127">In the left navigation go to **Voice** > **Phone numbers**, click **Add new number**![Add button](../images/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png), and then click **New user numbers**.</span></span>

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a><span data-ttu-id="151cf-128">Skype for Business管理センターでは使用できない、新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="151cf-128">Get new numbers that aren't available in the Skype for Business admin center</span></span>

<span data-ttu-id="151cf-129"> (国または地域によって) Skype for Business管理センターを使用して、新規の番号を取得することができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-129">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="151cf-130">その場合は、フォームをダウンロードし、マイクロソフトに返送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-130">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="151cf-131">新しいユーザーの番号を要求する方法については、 [組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-131">See [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.</span></span>

### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="151cf-132">使用中のサービス プロバイダーまたは携帯電話会社から電話番号を移行する</span><span class="sxs-lookup"><span data-stu-id="151cf-132">Port or transfer phone numbers from your service provider or phone carrier</span></span>

- <span data-ttu-id="151cf-133">ユーザー用に必要な電話番号が 999 個以下であれば、Skype for Business 管理センターの **新しい電話番号のポート注文**ウィザードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="151cf-133">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center.</span></span> <span data-ttu-id="151cf-134">電話番号を Skype for Business Online に移行するには [Office 365に電話番号を転送する](..//what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="151cf-134">Follow the steps found in[Transfer phone numbers to Skype for Business Online](..//what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.</span></span>

- <span data-ttu-id="151cf-135">999 を超える数の電話番号の移行が必要な場合は、 [組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照し、Office 365 に移行された全ての電話番号を取得できるよう、番号移行注文サービス要請を送信するか、その旨指示してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-135">If you need to port more than 999 phone numbers, see [Manually submit a custom service request](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order to get all of these phone numbers ported over to Office 365.</span></span>

<span data-ttu-id="151cf-136">**新しい電話番号を取得するか、既存の番号を転送する方法の詳細については、 [組織の電話番号の管理](../what-are-calling-plans-in-office-365\manage-phone-numbers-for-your-organization\manage-phone-numbers-for-your-organization.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="151cf-136">**For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365\manage-phone-numbers-for-your-organization\manage-phone-numbers-for-your-organization.md).**</span></span>

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="151cf-137">手順 4: サービス用の電話番号 (電話会議、通話キュー、自動応答) を取得します。</span><span class="sxs-lookup"><span data-stu-id="151cf-137">Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="151cf-138">Office 365 から、ユーザーの電話番号を取得するだけでなく、検索、電話会議 (会議ブリッジ用) 、自動応答、および通話キュー (サービス番号とも呼ばれます) などのサービスの無料または有料電話番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="151cf-138">In addition to getting phone numbers for individual users from Office 365, it's also possible to search and acquire toll or toll-free phone numbers for services such as Audio Conferencing (for conference bridges), auto attendants, and call queues.</span></span> <span data-ttu-id="151cf-139">サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。</span><span class="sxs-lookup"><span data-stu-id="151cf-139">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="151cf-140">たとえば、サービス電話番号は同時に 100 の通話を処理できますが、ユーザーの電話番号は同時に数個の通話しか処理できません。</span><span class="sxs-lookup"><span data-stu-id="151cf-140">For example, a service number can handle 100's of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>

### <a name="get-new-service-numbers"></a><span data-ttu-id="151cf-141">新しいサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="151cf-141">Get new service numbers</span></span>

<span data-ttu-id="151cf-142">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="151cf-142">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>


1. <span data-ttu-id="151cf-143">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="151cf-143">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="151cf-144"> **Office 365 管理センター** > **Skype for Business** に進みます。</span><span class="sxs-lookup"><span data-stu-id="151cf-144">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="151cf-145">左側のナビゲーションで音声電話番号 に進み、新しい番号を追加ボタンを追加 をクリックし、新しいユーザーの番号 をクリックします。** **  >  ** **  >  ** ** ** **</span><span class="sxs-lookup"><span data-stu-id="151cf-145">In the left navigation go to **Voice** > **Phone numbers** > **Add** then click **New service numbers**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="151cf-146">Skype for Business 管理センターの左のナビゲーションに  **音声** オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム** アドオン ライセンス、または **電話会議** アドオン ライセンスを少なくとも 1 件購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-146">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a><span data-ttu-id="151cf-147">Skype for Business管理センターでは使用できない、新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="151cf-147">Get new numbers that aren't available in the Skype for Business admin center</span></span>

<span data-ttu-id="151cf-148"> (国または地域によって) Skype for Business管理センターを使用して、新規の番号を取得することができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-148">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="151cf-149">その場合は、フォームをダウンロードし、マイクロソフトに返送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-149">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="151cf-150">新しいユーザーの番号を要求する方法については、 [組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-150">See [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers.</span></span>

### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="151cf-151">既存のサービス番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="151cf-151">Port or transfer existing service numbers</span></span>

<span data-ttu-id="151cf-152">現在のサービスプロバイダーまたは通信業者からサービスの番号を転送する場合は、マイクロソフトに番号移行注文を手動で提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-152">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft.</span></span> <span data-ttu-id="151cf-153">承認状（LOA)を使用して、移行したいサービス番号（有料・無料）の種類ごとに各々番号移行注文を提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-153">You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA).</span></span> <span data-ttu-id="151cf-154">承認状（LOA)では、適切な種類のサービス番号を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-154">In the Letter of Authorization (LOA), you must select the correct type of service number.</span></span> <span data-ttu-id="151cf-155">マイクロソフト サポートに問い合わせる場合は、サービス番号 (*ユーザーまたはサブスクライバーの番号ではなく*) を転送すること、または通話量に対応するための同時通話許容量が十分ではないことを指定してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-155">When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes.</span></span> <span data-ttu-id="151cf-156">電話番号を転送したり、自分の電話番号で他の操作をする場合は、 [組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-156">If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a><span data-ttu-id="151cf-157">手順 5: 通話プランを設定する場合</span><span class="sxs-lookup"><span data-stu-id="151cf-157">Step 5: If you want to set up Calling Plans</span></span>

<span data-ttu-id="151cf-158">上記の手順に従っていれば、あなたはすでに電話システムとライセンス、通話プラン（手順２）を購入して割り当てられ、ユーザー用の電話番号を取得（手順３）したことになるので、あなたの通話プランは部分的に設定されています。
</span><span class="sxs-lookup"><span data-stu-id="151cf-158">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up.</span></span> <span data-ttu-id="151cf-159">通話プランのセットアップを完了するのには、次の 3 つの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="151cf-159">Follow the three procedures below to complete the setup of your Calling Plan.</span></span>

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a><span data-ttu-id="151cf-160">組織用の緊急対応のアドレスと場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="151cf-160">Add emergency addresses and locations for your organization.</span></span>

1. <span data-ttu-id="151cf-161"> **音声**ページで、 **緊急の場所**  > **新しいアドレスを追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="151cf-161">On the **Voice** page, choose **Emergency locations** > **Add**.</span></span>

2. <span data-ttu-id="151cf-162"> **新しいアドレス** ウィンドウで、自分のアドレスに名前を入力し、残りのボックスの入力を完了します。</span><span class="sxs-lookup"><span data-stu-id="151cf-162">In the **New address** pane, enter a name for your address, and then complete the remaining boxes.</span></span>

     ![新しい緊急時のアドレスを入力すると、住所の書式設定がエラーを引き起こす可能性があります。](../images/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)

    > [!TIP]
    > <span data-ttu-id="151cf-164">上の図のように、英語圏のお客様で街路名が数字の場合は、必ず末尾に「st」または「th」を付けます。</span><span class="sxs-lookup"><span data-stu-id="151cf-164">For English customers, if the street name is a number, be sure to include "st" or "th" at the end, as shown in the above picture.</span></span>

3. <span data-ttu-id="151cf-165">[ **検証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="151cf-165">Choose **Validate**.</span></span>

    <span data-ttu-id="151cf-166">必要な場合は、住所の訂正を求められます。</span><span class="sxs-lookup"><span data-stu-id="151cf-166">If needed, you'll be prompted to make corrections to the address.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="151cf-167">住所または公的アドレスの検証では、アドレスが正規のもので、書式設定が正しいことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="151cf-167">Validating a street or civic address involves making sure that it is legitimate and correctly formatted.</span></span> <span data-ttu-id="151cf-168">緊急対応のアドレスの一部が誤っていても (市区町村名の誤入力など)、検証をパスすることがあります。</span><span class="sxs-lookup"><span data-stu-id="151cf-168">It is possible that a partially correct emergency address - such as if you mistyped the name of the city - may still pass validation.</span></span> <span data-ttu-id="151cf-169">誤記があっても検証をパスした場合、誤記がある市区町村名と住所の他の正しい部分の組み合わせによって、適切な緊急派遣センターに通話をルーティングするために十分な情報になります。</span><span class="sxs-lookup"><span data-stu-id="151cf-169">Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center.</span></span>

    > [!TIP]
    > <span data-ttu-id="151cf-170">緊急応答用に住所に修正が必要な場合は、住所が更新されたことを通知する緑色のバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="151cf-170">If the address needs to be corrected for emergency response, a green banner will appear notifying you that the address was updated.</span></span>

4. <span data-ttu-id="151cf-171">アドレスが検証されたら、 **保存** を選びます。</span><span class="sxs-lookup"><span data-stu-id="151cf-171">After the address is validated, choose **Save**.</span></span>

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a><span data-ttu-id="151cf-172">ユーザーに電話番号と緊急対応のアドレスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="151cf-172">Assign phone numbers and emergency addresses to users</span></span>

> [!TIP]
> <span data-ttu-id="151cf-p111">この手順を実行する直前にさらにユーザーを追加すると、[ **音声ユーザー**] ページにユーザーが表示されるまでに **数時間** かかることがあります。これには遅延時間があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-p111">If you add more people to your business right before doing this step, it may take **several hours** for them to appear on the **Voice users** page. There's a latency.</span></span>

1. <span data-ttu-id="151cf-175"> **音声ユーザー** ページで、電話番号と緊急対応のアドレスを割り当てるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="151cf-175">On the **Voice users** page, choose the people who you want to assign a phone number and emergency address to.</span></span>

2. <span data-ttu-id="151cf-176">[操作] ウィンドウで、 **割り当てる番号** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="151cf-176">In the Action pane, click **Assign number**.</span></span>

3. <span data-ttu-id="151cf-177"> **番号を割り当てる** ページの  **割り当てる番号を選択** 一覧で、ユーザー用の電話番号を選びます。</span><span class="sxs-lookup"><span data-stu-id="151cf-177">On the **Assign number** page, in the **Select number to assign** drop down, select the phone number for the user.</span></span>

4. <span data-ttu-id="151cf-178">緊急対応のアドレスを選ぶには、ボックスに市区町村の名前を入力し、 **検索** を選びます。</span><span class="sxs-lookup"><span data-stu-id="151cf-178">To select an emergency address, put the name of the city in the **Find City** box and choose Search.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="151cf-179">米国外に居住している場合は、電話番号にすでに緊急対応の住所が指定されていますが、ここで変更できます。</span><span class="sxs-lookup"><span data-stu-id="151cf-179">If you are outside the U.S., your numbers already have an emergency address but you can change it now.</span></span> <span data-ttu-id="151cf-180"> [ユーザーの緊急対応の住所を割り当てるまたは変更する](../what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-180">See [Assign or change an emergency address for a user](../what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user.md).</span></span>

5. <span data-ttu-id="151cf-181">電話番号と緊急対応のアドレスの両方を割り当てたら、 **保存** を選びます。</span><span class="sxs-lookup"><span data-stu-id="151cf-181">After you assign both the phone number and emergency address, choose **Save**.</span></span>

### <a name="tell-your-users-about-their-new-phone-numbers"></a><span data-ttu-id="151cf-182">新しい電話番号をユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="151cf-182">Step 5: Tell your users about their new phone numbers</span></span>


<span data-ttu-id="151cf-183">新しい電話番号をユーザーに通知する場合は、メールを送信するか、または各組織が指定する方法で行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="151cf-183">We recommend sending mail or using your business's preferred communication method to tell the people about their new phone numbers.</span></span>

<span data-ttu-id="151cf-184">次に、ユーザーの **Skype for Business**  アプリに電話番号がどのように表示されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="151cf-184">Here's how they can see that phone number in their Skype for Business app:</span></span>

1. <span data-ttu-id="151cf-185">デスクトップで Skype for Business にサインインします。</span><span class="sxs-lookup"><span data-stu-id="151cf-185">Sign in to Skype for Business on your desktop.</span></span>

2. <span data-ttu-id="151cf-186"> **Settings** > **Tools** > **Options** を選択します。</span><span class="sxs-lookup"><span data-stu-id="151cf-186">Choose **Settings** > **Tools** > **Options**.</span></span>

     ![電話番号を表示するには、設定 > ツール > オプション。](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)

3. <span data-ttu-id="151cf-188">次に、[ **電話**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="151cf-188">Then choose **Phones**.</span></span>

    ![ ツール > オプション > 電話 を選択することで、ユーザーの割り当てられた番号が Skype for Business アプリに表示されます。](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)

<span data-ttu-id="151cf-190"> **マイクロソフトのチーム**では、ユーザーは、左側のナビゲーションで **呼び出し** をクリックすると、その電話番号を表示できます。</span><span class="sxs-lookup"><span data-stu-id="151cf-190">In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation.</span></span> <span data-ttu-id="151cf-191">電話番号は、ダイヤル パッドの上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="151cf-191">The phone number is shown above the dial pad.</span></span>

![ユーザーは、左側のナビゲーションで呼び出しをクリックすると、Microsoft Teams で番号を確認できます。](../images/teams-phone-number.png)

<span data-ttu-id="151cf-193">**通話プランを設定する手順すべての詳細については、 [通話プランの設定](../what-are-calling-plans-in-office-365/set-up-calling-plans.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="151cf-193">**For more detailed information about all of the steps involved in setting up a Calling Plan, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).**</span></span>


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a><span data-ttu-id="151cf-194">手順 6: 電話会議を設定する場合</span><span class="sxs-lookup"><span data-stu-id="151cf-194">Step 6: If you want to set up Audio Conferencing</span></span>

<span data-ttu-id="151cf-195">組織内のユーザーは、会議に出席するため時には電話を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-195">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="151cf-196">Skype for Business と Microsoft Teams には、このような状況に最適な電話会議の機能があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-196">Skype for Business and Microsoft Teams include the Audio Conferencing feature for just this situation!</span></span> <span data-ttu-id="151cf-197">ユーザーは、モバイル デバイスや PC 上の Skype for Business アプリや Microsoft Teams アプリを使用しなくても、電話機を使用して Skype for Business 会議や Microsoft Teams 会議を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="151cf-197">People can call into Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span>

<span data-ttu-id="151cf-198">必要なのは、会議を計画したり主催しようとしているユーザー向けに電話会議をセットアップすることだけです。</span><span class="sxs-lookup"><span data-stu-id="151cf-198">You only need to set up dial-in conferencing for users who plan to schedule or lead meetings.</span></span> <span data-ttu-id="151cf-199">ダイヤルインする会議参加者には、割り当てられたライセンスやその他のセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="151cf-199">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>

<span data-ttu-id="151cf-200">電話会議についてよく寄せられる質問については、 [電話会議についてよくある質問](../audio-conferencing-in-office-365/audio-conferencing-common-questions.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-200">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](../audio-conferencing-in-office-365/audio-conferencing-common-questions.md).</span></span>

1. <span data-ttu-id="151cf-201"> **電話会議** アドオンライセンスとコミュニケーション クレジットライセンスを購入した場合は、それらも割り当てます。</span><span class="sxs-lookup"><span data-stu-id="151cf-201">If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too.</span></span> <span data-ttu-id="151cf-202">手順については、 [Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="151cf-202">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

    <span data-ttu-id="151cf-203">電話会議のプロバイダーを決定します。</span><span class="sxs-lookup"><span data-stu-id="151cf-203">Decide on your audio conferencing provider.</span></span> <span data-ttu-id="151cf-204">電話会議プロバイダーは、電話会議ブリッジを提供します。</span><span class="sxs-lookup"><span data-stu-id="151cf-204">An audio conferencing provider supplies an audio conferencing bridge.</span></span> <span data-ttu-id="151cf-205">会議用ブリッジは会議用に、ダイヤルインの電話番号、PIN、会議 ID を設定します。</span><span class="sxs-lookup"><span data-stu-id="151cf-205">Provide a  dial-in conferencing bridge  . The conferencing bridge will set dial-in phone numbers, PINs and conference IDs for meetings.</span></span> <span data-ttu-id="151cf-206">Microsoft を使用するか、Microsoft以外の電話会議プロバイダーを使用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="151cf-206">Decide whether to use Microsoft or a third-party audio conferencing provider:</span></span>

    > [!NOTE]
    > <span data-ttu-id="151cf-207">Microsoft Teams のユーザーには、Microsoft 以外の電話会議プロバイダーを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="151cf-207">Microsoft Teams users can't user a third-party audio conferencing provider.</span></span>

    - <span data-ttu-id="151cf-208">**電話会議プロバイダーとしての Microsoft**: 電話会議の最も簡単なソリューションをお求めなら、電話会議プロバイダーとして Microsoft を選択します。</span><span class="sxs-lookup"><span data-stu-id="151cf-208">**Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.</span></span>

    - <span data-ttu-id="151cf-209">**電話会議プロバイダーとしての非Microsoftプロバイダー**: Office 365 の電話会議を使用できない国にいる場合、品質の優れたサービスが受けられない場所にいる場合、もしくは既存の契約がある場合は、Microsoft以外の電話会議プロバイダーを選んで下さい。</span><span class="sxs-lookup"><span data-stu-id="151cf-209">If you are in a country or region where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract with a third-party audio conferencing provider, we recommend using a third-party audio conferencing provider.</span></span> <span data-ttu-id="151cf-210">プロバイダーを検索するには、 [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530) に進みます。</span><span class="sxs-lookup"><span data-stu-id="151cf-210">To find a provider, go to [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).</span></span>

2.  <span data-ttu-id="151cf-211">会議を主導したり、会議の日程を立てる人達に電話会議プロバイダーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="151cf-211">Assign the audio conferencing provider to people who lead or schedule meetings.</span></span> <span data-ttu-id="151cf-212"> [Microsoft を電話会議プロバイダーとして割り当てる](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-212">[Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)</span></span>

3. <span data-ttu-id="151cf-213">会議出席依頼を設定します。</span><span class="sxs-lookup"><span data-stu-id="151cf-213">Set up meeting invitations.</span></span> <span data-ttu-id="151cf-214">次の手順はオプションですが、管理者の多くは次の設定を行うのを好みます。</span><span class="sxs-lookup"><span data-stu-id="151cf-214">The following steps are optional, but a lot of admins like to do them:</span></span>

    1. <span data-ttu-id="151cf-215"> [会議出席依頼をカスタマイズする](../set-up-skype-for-business-online/customize-meeting-invitations.md)。</span><span class="sxs-lookup"><span data-stu-id="151cf-215">[Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md)</span></span> <span data-ttu-id="151cf-216">ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議出席依頼に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="151cf-216">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to attendees.</span></span> <span data-ttu-id="151cf-217">ただし、独自のヘルプや法務関連リンク、テキスト メッセージ、会社の小さな画像を追加できます。</span><span class="sxs-lookup"><span data-stu-id="151cf-217">However, you can add your own help and legal links, a text message, and small company graphic.</span></span>

    2. <span data-ttu-id="151cf-218"> [出席依頼に含まれている会議の開催者用の電話会議の電話番号を設定する](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="151cf-218">[](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)Set the Audio Conferencing phone numbers for meeting organizers that are included on invites</span></span> <span data-ttu-id="151cf-219">これは、ユーザーが開催を予定している会議で表示される電話番号です。</span><span class="sxs-lookup"><span data-stu-id="151cf-219">This is the phone number that will show up in the meeting that is scheduled by the user.</span></span>

    3. <span data-ttu-id="151cf-220">発信者が電話会議の電話番号にかけたときに、電話会議の自動応答が発信者に応答する際に使われる [電話会議の自動応答言語を設定します](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="151cf-220">[Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number.</span></span> <span data-ttu-id="151cf-221">この手順は、Microsoft を電話会議プロバイダーとして使用している場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="151cf-221">This step only applies if you're using Microsoft as your audio provider.</span></span>

    4. <span data-ttu-id="151cf-222"> [電話会議の PIN の長さを設定します](../audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="151cf-222">[Set the PIN length for Audio Conferencing meetings](../audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings.md)</span></span>

    > [!NOTE]
    > <span data-ttu-id="151cf-223">中国の 21Vianet で運用される Office 365 を使用している顧客は、まだこの機能を使用できません。</span><span class="sxs-lookup"><span data-stu-id="151cf-223">This feature is not yet available to customers using Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="151cf-224">詳細については、 [21Vianet で運用される Office 365 について](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-224">To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span></span>

<span data-ttu-id="151cf-225">**電話会議の詳細については、 [電話会議の設定](../audio-conferencing-in-office-365/set-up-audio-conferencing.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="151cf-225">**For more information about Audio Conferencing, see [Set up Audio Conferencing](../audio-conferencing-in-office-365/set-up-audio-conferencing.md).**</span></span>

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a><span data-ttu-id="151cf-226">手順 7: 電話システムの通話キューを設定する場合</span><span class="sxs-lookup"><span data-stu-id="151cf-226">Step 7: If you want to set up a Phone System call queue</span></span>

<span data-ttu-id="151cf-227">電話システムの通話キューには、誰かがあなたの組織の電話番号にかけてきた時に対応する挨拶、自動的に通話を保留する機能、および通話の発信者が保留メロディを聴いている間に通話を処理するために次に利用できるコール エージェントの検索が含まれます。</span><span class="sxs-lookup"><span data-stu-id="151cf-227">Skype for Business Online Cloud PBX Call Queues include greetings that are used when someone calls into a phone number for your organization, the ability to automatically put the calls on hold and search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="151cf-228">組織では単一または複数の通話キューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="151cf-228">You can create a single or multiple call queues for your organization.</span></span>

<span data-ttu-id="151cf-229">通話キューを作成し設定する前に、既存の有料または無料のサービス番号を取得もしくは転送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-229">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="151cf-230">有料または無料のサービスの電話番号を取得した後、  **Skype for Business 管理センター** > **音声** > **電話番号** に番号が表示され、  **番号の種類** のリストには、 **サービスー無料** として一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="151cf-230">After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="151cf-231">サービス番号を取得するには、  [Skype for Business と Microsoft Teams 用のサービス電話番号の取得](getting-service-phone-numbers.md) を参照するか、既存のサービス番号を転送する場合は、  [Office 365 に電話番号を転送する](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-231">To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="151cf-232">米国以外の国では、Skype for Business 管理センターを使用してサービス番号を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="151cf-232">If you are outside the U.S., you can't use the Skype for Business admin center to get service numbers.</span></span> <span data-ttu-id="151cf-233">米国以外の国でのサービス番号を取得する方法については、 [組織の電話番号を管理する](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="151cf-233">Go [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the U.S.</span></span>

<span data-ttu-id="151cf-234">  **Skype for Business 管理センター** で、新しい通話キューを作成するには、 **通話ルーティング** > **通話キュー** をクリックし、  **新規追加** をクリックし、 [電話システム呼び出しキューを作成する]( create-a-phone-system-call-queue.md#step-3---create-a-new-call-queue) の  **手順 3** の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="151cf-234">To create a new call queue, in the **Skype for Business admin center**, click **Call routing** > **Call queues**, click **Add new**, and then follow the instructions in **Step 3** of  [Create a Phone System call queue]( create-a-phone-system-call-queue.md#step-3---create-a-new-call-queue).</span></span>

<span data-ttu-id="151cf-235">**通話キューの詳細については、 [電話システムの通話キューを作成する](create-a-phone-system-call-queue.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="151cf-235">**For more details about call queues, see [Create a Phone System call queue](create-a-phone-system-call-queue.md).**</span></span>

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a><span data-ttu-id="151cf-236">手順 8: 自動応答電話システムを設定する場合</span><span class="sxs-lookup"><span data-stu-id="151cf-236">Step 8: If you want to set up a Phone System auto attendant</span></span>

<span data-ttu-id="151cf-237">自動応答は、組織へ電話をかけてきた人にメニュー システムで自らを誘導し、希望の部署、通話キュー、目的の人、及びオペレーターに行きつけるようにします。</span><span class="sxs-lookup"><span data-stu-id="151cf-237">Auto attendants are very useful and let people that call into your organization navigate a menu system to get them to the right department, call queue, a person or the operator.</span></span> <span data-ttu-id="151cf-238">Skype for Business 管理センターを使用して、組織の自動応答を作成できます。</span><span class="sxs-lookup"><span data-stu-id="151cf-238">You can create an auto attendant for your organization using the Skype for Business admin center.</span></span>

<span data-ttu-id="151cf-239">Skype for Business 管理センターで、新しい自動応答を作成するには、 **通話ルーティング** > **自動応答** をクリックし、 **新規追加**をクリックし、 [自動応答電話システム設定](set-up-a-phone-system-auto-attendant.md#step-2---create-a-new-auto-attendant) の **ステップ 2** の指示に従って下さい。</span><span class="sxs-lookup"><span data-stu-id="151cf-239">To create a new auto attendant, in the Skype for Business admin center, click **Call routing** > **Auto attendants**, click **Add new**, and then follow the instructions for each page in **Step 2** of [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md#step-2---create-a-new-auto-attendant).</span></span>

<span data-ttu-id="151cf-240">**電話システムの自動応答の詳細については、 [電話システムの自動応答の設定](set-up-a-phone-system-auto-attendant.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="151cf-240">**For more details about Phone System auto attendants, see [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).**</span></span>

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="151cf-241">手順 9: サービス用電話番号 (電話会議、通話キュー、自動応答) の割り当て</span><span class="sxs-lookup"><span data-stu-id="151cf-241">Step 9: Assign service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="151cf-242"> **上記の手順 4** から、サービスの番号を作成したら、使用するサービスの種類ごとに番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-242">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want.</span></span> <span data-ttu-id="151cf-243">専用のサービスの電話番号(有料またはフリー ダイヤル)を挿入する場合などは、会議用ブリッジに番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-243">For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.</span></span>

- <span data-ttu-id="151cf-244">電話会議用に専用番号を会議用ブリッジに割り当てることができます。それには、 **Office 365 の管理センター** > **管理センター** > **Skype for Business** > **電話会議** に進み、会議ブリッジをクリックするか、 [電話会議ブリッジ上の有料・無料番号を変更する](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-244">For Audio Conferencing, you can assign a dedicated number to a conferencing bridge by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** and click on the conference bridge or by seeing  [Change the toll or toll-free numbers on your Audio Conferencing bridge](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

- <span data-ttu-id="151cf-245">自動応答では、自動アテンダントに専用番号を割り当てることができます。それには、  **Office 365 の管理センター** > **管理センター** > **Skype for Business** > **通話ルーティング** > **自動応答** に進み、自動応答 をクリックします。</span><span class="sxs-lookup"><span data-stu-id="151cf-245">For Auto Attendants, you can assign a dedicated number to an auto attendant by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Auto attendants** and click on the auto attendant.</span></span> <span data-ttu-id="151cf-246">既存のサービス番号は、 **全般** ページの **電話番号** ドロップダウンのリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="151cf-246">On the **General** page the service number you already have will be listed in the **Phone number** drop down.</span></span> <span data-ttu-id="151cf-247">詳細については、  [電話システムの自動応答の設定](set-up-a-phone-system-auto-attendant.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-247">For details, see [Set up a Phone System Auto Attendant](set-up-a-phone-system-auto-attendant.md).</span></span>

- <span data-ttu-id="151cf-248">通話キューでは、通話キューに専用番号を割り当てることができます。それには、  **Office 365 の管理センター** > **管理センター** > **Skype for Business** > **通話ルーティング** > **通話キュー** と進み、「通話キュー」をクリックします。</span><span class="sxs-lookup"><span data-stu-id="151cf-248">For Call Queues, you can assign a dedicated number to a call queue by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Call queues** and click on the call queue.</span></span> <span data-ttu-id="151cf-249">既存のサービス番号は、 **全般** ページの **電話番号** ドロップダウンのリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="151cf-249">On the **General** page the service number you already have will be listed in the **Phone number** drop down.</span></span> <span data-ttu-id="151cf-250">詳細については、 [電話システムの通話キューを作成する](create-a-phone-system-call-queue.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-250">For details, see [Create a Phone System call queue](create-a-phone-system-call-queue.md).</span></span>

<span data-ttu-id="151cf-251">**新しいサービス番号を取得し、既存のサービス番号を転送する方法の詳細については、 [サービスの電話番号の取得](getting-service-phone-numbers.md)  を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="151cf-251">**For detailed information about getting new service numbers and porting existing service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).**</span></span>

## <a name="step-10-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="151cf-252">手順 10: 組織用コミュニケーション クレジットの設定</span><span class="sxs-lookup"><span data-stu-id="151cf-252">Step 2: Set up Communications Credits for your organization</span></span>

<span data-ttu-id="151cf-253">Skype for Business および Microsoft Teams で無料電話番号を使用する場合は、コミュニケーション クレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-253">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="151cf-254">また、 **任意の発信先** にダイヤルアウトする機能が必要な、通話プラン (国内および国際通話) ユーザーと電話会議ユーザー向けにコミュニケーション クレジットを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="151cf-254">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="151cf-255">ご利用の通話プランまたは電話会議のサブスクリプションでは、多くの国や地域が含まれていますが、一部の発信先が含まれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="151cf-255">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="151cf-256">コミュニケーション クレジットの請求を設定しない場合や、ユーザーに **コミュニケーション クレジット**のライセンスを割り当てない場合に (国/地域の通話プランまたは電話会議プランに基づき) 組織の通話分数が不足すると、これらのユーザーは通話を発信することや、電話会議からダイヤルアウトすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="151cf-256">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="151cf-257">推奨される利用可能残高などの詳細については、[コミュニケーション クレジットについて](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="151cf-257">You can find out more information including recommended funding amounts by reading [What are Communications Credits?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)</span></span>

> [!NOTE]
> <span data-ttu-id="151cf-258">費用を確認するには、 [こちらで料金をご覧ください](https://go.microsoft.com/fwlink/p/?LinkId=799523 ) 。</span><span class="sxs-lookup"><span data-stu-id="151cf-258">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span>

### <a name="to-set-up-communications-credits"></a><span data-ttu-id="151cf-259">コミュニケーションクレジットの設定方法</span><span class="sxs-lookup"><span data-stu-id="151cf-259">How to set up Communications Credits</span></span>

1. <span data-ttu-id="151cf-260">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="151cf-260">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="151cf-261">Office 365 管理ページ左側のナビゲーションで  **請求** > **サブスクリプション** > **アドオン** > **アドオンの購入** に進み、 **コミュニケーションクレジット** > **今すぐ購入** を選択してください。</span><span class="sxs-lookup"><span data-stu-id="151cf-261">In the left navigation of the Office 365 admin center, go to **Billing** > **Subscriptions** > **Add-ons** > **Buy add-ons**, and then choose **Communications Credits** > **Buy now**.</span></span>

3. <span data-ttu-id="151cf-262"> **コミュニケーションクレジット** 申し込みのページで、自分の情報を入力し、 **次へ** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="151cf-262">On the ** Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>

4. <span data-ttu-id="151cf-263">支払い情報を入力して、 **注文** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="151cf-263">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="151cf-264">一括ライセンス契約の場合は、支払いにエンタープライズ契約番号を選択できます。</span><span class="sxs-lookup"><span data-stu-id="151cf-264">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="151cf-265">エンタープライズ契約番号が複数ある場合は、どのエンタープライズ アグリーメントを支払いに使用するかを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="151cf-265">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="151cf-266">エンタープライズ 契約番号 (存在する場合) に関連付けるよう、特定の発注書番号を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="151cf-266">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>

<span data-ttu-id="151cf-267">**コミュニケーションクレジットの設定に関する詳細については、 [組織のコミュニケーションクレジットを設定](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="151cf-267">**For more detailed information about setting up Communications Credits, see [Set up Communications Credits for your organization](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**</span></span>

### <a name="assign-a-communications-credits-license-to-users"></a><span data-ttu-id="151cf-268">コミュニケーションクレジットのライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="151cf-268">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="151cf-269">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="151cf-269">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="151cf-270">Office 365 管理ページの左側のナビゲーションで、 **ユーザー** > **アクティブなユーザー** に進み、そのリストから一人、または複数のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="151cf-270">In the left navigation of the Office 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>

3. <span data-ttu-id="151cf-271"> **製品ライセンス** の下の操作ウィンドウで、  **編集** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="151cf-271">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="151cf-272"> **製品ライセンス** ページで、  **コミュニケーションクレジット** を **オン** に切り替えて当ライセンスを割り当て、 **保存** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="151cf-272">On the **Product licenses** page, toggle ** Communications Credits** to **On** to assign this license, and then click **Save**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="151cf-273"> **Enterprise E5** ライセンスが割り当てられているユーザーがいる場合でも、この手順を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="151cf-273">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>

<span data-ttu-id="151cf-274">**コミュニケーションクレジットのライセンスの割り当ての詳細については、 [組織用コミュニケーションクレジットの設定](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md) を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="151cf-274">**To learn more about assigning Communications Credits licenses, see [Set up Communications Credits for your organization](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**</span></span>

## <a name="related-topics"></a><span data-ttu-id="151cf-275">関連トピック</span><span class="sxs-lookup"><span data-stu-id="151cf-275">Related topics</span></span>
[<span data-ttu-id="151cf-276">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="151cf-276">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="151cf-277">Skype for Business および Microsoft Teams のサービス電話番号の取得</span><span class="sxs-lookup"><span data-stu-id="151cf-277">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="151cf-278">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="151cf-278">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)


