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
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
description: Microsoft 365 または Office 365 で組織の電話システム (クラウド PBX) をセットアップする方法の詳細なステップ バイ ステップ ガイド。
ms.openlocfilehash: c00b628716a54adcb19c3dd1f00e8e9e2b6f4c40
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701215"
---
# <a name="set-up-phone-system-in-your-organization"></a><span data-ttu-id="995cd-103">組織で電話システムをセットアップする</span><span class="sxs-lookup"><span data-stu-id="995cd-103">Set up Phone System in your organization</span></span>

<span data-ttu-id="995cd-p101">以下は、Microsoft 365 または Office 365 で電話システムをセットアップする手順ガイドです。その他の詳細情報へのリンクは、各手順の最後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="995cd-p101">The following is a step-by-step guide for setting up Phone System in Microsoft 365 or Office 365. Links to additional, detailed information are available at the end of each step.</span></span>

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a><span data-ttu-id="995cd-106">ステップ 1: 電話システムは、国または地域で利用可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="995cd-106">Step 1: Make sure that Phone System is available in your country or region</span></span>

1.    <span data-ttu-id="995cd-107">最初に [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) へ進み、ページの上部にある一覧表から国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="995cd-107">First go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page.</span></span> 
2.    <span data-ttu-id="995cd-108"> **電話システム** での機能と詳細の一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="995cd-108">Under **Phone System**, review the list of features and details.</span></span> 
3.    <span data-ttu-id="995cd-109">電話システムが使用可能な場合は、手順 2 に進みます。</span><span class="sxs-lookup"><span data-stu-id="995cd-109">If Phone System is available, go to step 2.</span></span> 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a><span data-ttu-id="995cd-110">手順 2: 電話システムおよび通話プランのライセンスを購入し、割り当てる</span><span class="sxs-lookup"><span data-stu-id="995cd-110">Step 2: Buy and assign Phone System and Calling Plan licenses</span></span>

<span data-ttu-id="995cd-111">電話システムと通話プランのライセンスを 1 人のユーザーに割り当てる手順は、Microsoft 365 または Office 365 ライセンスの割り当てと同じです。</span><span class="sxs-lookup"><span data-stu-id="995cd-111">To assign a Phone System and Calling Plan license to a single user, the steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span>  <span data-ttu-id="995cd-112">複数のユーザーにライセンスを一括で割り当て込む方法も可能です。</span><span class="sxs-lookup"><span data-stu-id="995cd-112">You can also assign licenses to multiple users in bulk.</span></span> <span data-ttu-id="995cd-113">詳細については、「Microsoft Teams アドオン ライセンスを割り当てる [」を参照してください](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="995cd-113">For more information, see [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>

<span data-ttu-id="995cd-114">お客様の国または地域で通話プランを利用できない場合は、ダイレクト ルーティングを使用して、オンプレミスのテレフォニー インフラストラクチャを電話システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="995cd-114">If Calling Plans are not available for your country or region, consider using Direct Routing to connect your on-premises telephony infrastructure to Phone System.</span></span>  <span data-ttu-id="995cd-115">詳細については、「[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995cd-115">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

## <a name="step-3-get-phone-numbers-for-your-users"></a><span data-ttu-id="995cd-116">ステップ 3: ユーザー向けの電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="995cd-116">Step 3: Get phone numbers for your users</span></span>

<span data-ttu-id="995cd-117">組織内でユーザーを設定し、電話を掛けたり受けたりする前に、ユーザーの電話番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-117">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>

<span data-ttu-id="995cd-118">ユーザー用の番号を取得するには、次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-118">You have three ways of getting numbers for your users:</span></span>
- <span data-ttu-id="995cd-119">Teams 管理センターを使用して新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="995cd-119">Get new numbers using the Teams admin center.</span></span>
- <span data-ttu-id="995cd-120">Teams 管理センターでは利用できない新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="995cd-120">Get new numbers that aren't available in the Teams admin center.</span></span>
- <span data-ttu-id="995cd-121">現在のサービス プロバイダーまたは携帯電話会社から Microsoft 365 または Office 365 に既存の番号を移植または転送します。</span><span class="sxs-lookup"><span data-stu-id="995cd-121">Port or transfer your existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="995cd-122">これらの数値を表示、 **検索、取得** 、予約するには、[数値の追加] ページを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-122">You must use the **Add numbers** page to see, search, acquire, and reserve those numbers.</span></span> <span data-ttu-id="995cd-123">[ 国または地域]、[ 都道府県]、[ 市区町村] で検索してから、ユーザー用に必要となる電話番号の数を入力できます。</span><span class="sxs-lookup"><span data-stu-id="995cd-123">You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span></span>

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a><span data-ttu-id="995cd-124">Teams 管理センターを使用して新しいユーザーの電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="995cd-124">Get new user phone numbers using the Teams admin center</span></span>

1. <span data-ttu-id="995cd-125">職場または学校のアカウントを使用して、Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="995cd-125">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="995cd-126">Teams 管理センター **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="995cd-126">Go to the **Teams admin center**.</span></span>
    
3. <span data-ttu-id="995cd-127">左側のナビゲーションで [音声電話番号]**に** 移動し、[追加] をクリックして、画面  >  の指示に従います。 </span><span class="sxs-lookup"><span data-stu-id="995cd-127">In the left navigation go to **Voice** > **Phone numbers**, click **Add**, and then follow the prompts.</span></span>
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="995cd-128">Teams 管理センターで利用できない新しい番号を取得する</span><span class="sxs-lookup"><span data-stu-id="995cd-128">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="995cd-129">(お客様の国/地域によって異なります) Teams 管理センターを使用して新しい番号を取得できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-129">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="995cd-130">この場合は、フォームをダウンロードして返送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-130">In this case, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="995cd-131">新しいユーザー番号を要求する方法については、「組織の電話番号を管理する [」を参照してください](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="995cd-131">To learn how to request new user numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="995cd-132">サービス プロバイダーまたは電話会社から電話番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="995cd-132">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="995cd-133">ユーザーに必要な電話番号が 999 以下の場合は、Teams 管理センターで新しい電話番号のポート注文ウィザードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="995cd-133">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Teams admin center.</span></span> <span data-ttu-id="995cd-134">「電話番号を Teams に [転送する」](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) の手順に従って、電話番号を転送します。</span><span class="sxs-lookup"><span data-stu-id="995cd-134">Follow the steps found in [Transfer phone numbers to  Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to transfer your phone numbers.</span></span>
    
- <span data-ttu-id="995cd-135">999 を超える電話番号を移植する必要がある場合[](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)は、「組織の電話番号を管理してポート注文サービスの依頼または注文を送信する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995cd-135">If you need to port more than 999 phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order.</span></span> 

<span data-ttu-id="995cd-136">新しい電話番号を取得するか、既存の番号を転送する方法の詳細については、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995cd-136">For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="995cd-137">手順 4: サービス用の電話番号 (電話会議、通話キュー、自動応答) を取得します。</span><span class="sxs-lookup"><span data-stu-id="995cd-137">Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="995cd-138">Microsoft 365 または Office 365 からユーザーの電話番号を取得できるだけでなく、電話会議 (会議ブリッジ用)、自動応答、通話キューなどのサービスの有料または無料電話番号を検索して取得できます。</span><span class="sxs-lookup"><span data-stu-id="995cd-138">In addition to getting phone numbers for your users from Microsoft 365 or Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues.</span></span> <span data-ttu-id="995cd-139">サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。</span><span class="sxs-lookup"><span data-stu-id="995cd-139">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="995cd-140">たとえば、サービス番号は何百もの通話を同時に処理できるのに対し、ユーザーの電話番号は同時に数件の通話しか処理できません。</span><span class="sxs-lookup"><span data-stu-id="995cd-140">For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a><span data-ttu-id="995cd-141">Teams 管理センターを使用して新しいサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="995cd-141">Get new service numbers using the Teams admin center</span></span>


1. <span data-ttu-id="995cd-142">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="995cd-142">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="995cd-143">Teams 管理センター **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="995cd-143">Go to the **Teams admin center**.</span></span>

3. <span data-ttu-id="995cd-144">左側のナビゲーション ウィンドウで、[音声 **電話番号]** に移動し、[新しい番号を追加] をクリックし、[新しい  >    >  **サービス番号] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="995cd-144">In the left navigation pane go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="995cd-145">Teams 管理センターの左側のナビゲーション ウィンドウに音声オプションを表示するには、まず、Enterprise **E5** ライセンス、電話システム アドオンライセンス、または電話会議アドオン ライセンスを1 つ以上購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-145">For you to see the **Voice** option in the left navigation pane in the Teams admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="995cd-146">Teams 管理センターで利用できない新しい番号を取得する</span><span class="sxs-lookup"><span data-stu-id="995cd-146">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="995cd-147">(お客様の国/地域によって異なります) Teams 管理センターを使用して新しい番号を取得できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-147">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="995cd-148">この場合は、フォームをダウンロードして返送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-148">In this case, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="995cd-149">新しい電話番号を要求する方法については、「組織の電話番号を管理する [」を参照してください](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="995cd-149">To learn how to request new numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span> 

### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="995cd-150">既存のサービス番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="995cd-150">Port or transfer existing service numbers</span></span>

<span data-ttu-id="995cd-151">現在のサービスプロバイダーまたは通信業者からサービスの番号を転送する場合は、マイクロソフトに番号移行注文を手動で提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-151">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft.</span></span> <span data-ttu-id="995cd-152">承認状 (LOA) を使用して移行するサービス番号の種類 (有料と無料電話番号) ごとに、個別の番号移行注文を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-152">You need to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA).</span></span> <span data-ttu-id="995cd-153">承認状（LOA)では、適切な種類のサービス番号を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-153">In the Letter of Authorization (LOA), you must select the correct type of service number.</span></span> <span data-ttu-id="995cd-154">Microsoft サポートに問い合わせするときに、サービス番号 *(ユーザー* またはサブスクライバー番号ではなく) を転送する場合、または同時呼び出しキャパシティーが通話ボリュームを処理するのに十分ではない可能性がある場合を指定します。</span><span class="sxs-lookup"><span data-stu-id="995cd-154">When contacting Microsoft support, specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes.</span></span> <span data-ttu-id="995cd-155">電話番号を転送したり、自分の電話番号で他の操作をする場合は、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995cd-155">If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a><span data-ttu-id="995cd-156">手順 5: 通話プランを設定する場合</span><span class="sxs-lookup"><span data-stu-id="995cd-156">Step 5: If you want to set up Calling Plans</span></span>

<span data-ttu-id="995cd-157">上記の手順に従っていれば、あなたはすでに電話システムとライセンス、通話プラン（手順２）を購入して割り当てられ、ユーザー用の電話番号を取得（手順３）したことになるので、あなたの通話プランは部分的に設定されています。
</span><span class="sxs-lookup"><span data-stu-id="995cd-157">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up.</span></span> <span data-ttu-id="995cd-158">通話プランを設定する手順を完了するには、「通話プランを設定 [する」を参照してください](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="995cd-158">To complete the procedures for setting up Calling Plan, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a><span data-ttu-id="995cd-159">手順 6: 電話会議を設定する場合</span><span class="sxs-lookup"><span data-stu-id="995cd-159">Step 6: If you want to set up Audio Conferencing</span></span>

<span data-ttu-id="995cd-160">組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-160">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="995cd-161">Microsoft Teams には、このような状況専用の電話会議機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="995cd-161">Microsoft Teams includes the Audio Conferencing feature for just this situation.</span></span> <span data-ttu-id="995cd-162">ユーザーは、モバイル デバイスや PC で Teams アプリを使用する代わりに、電話を使って Teams 会議にコールインできます。</span><span class="sxs-lookup"><span data-stu-id="995cd-162">People can call in to  Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span>
<span data-ttu-id="995cd-163">電話会議の設定方法については、「Teams の電話会議をセットアップする」を [参照してください](set-up-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="995cd-163">For information about how to set up Audio Conferencing, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md).</span></span>

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a><span data-ttu-id="995cd-164">手順 7: クラウドの通話キューを設定する場合</span><span class="sxs-lookup"><span data-stu-id="995cd-164">Step 7: If you want to set up a Cloud call queue</span></span>

<span data-ttu-id="995cd-p112">クラウド通話キューには、誰かが組織の電話番号に電話をかけた際に流れる挨拶メッセージ、通話を自動的に保留する機能、および保留中に電話をかけてきた方に音楽を流し、その間に通話への対応が可能な次の電話エージェントを探す機能が含まれています。1 つまたは複数の通話キューを組織のために作成できます。</span><span class="sxs-lookup"><span data-stu-id="995cd-p112">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span></span>

<span data-ttu-id="995cd-167">通話キューの詳細については、「クラウド通話キューを作成 [する」を参照してください](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="995cd-167">For more information about call queues, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a><span data-ttu-id="995cd-168">手順 8: クラウドの自動応答を設定する場合</span><span class="sxs-lookup"><span data-stu-id="995cd-168">Step 8: If you want to set up a Cloud auto attendant</span></span>

<span data-ttu-id="995cd-169">自動応答を使用すると、組織にコールインし、メニュー システムに移動して、適切な部署、通話キュー、ユーザー、またはオペレーターに移動できます。</span><span class="sxs-lookup"><span data-stu-id="995cd-169">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="995cd-170">Teams 管理センターを使用して、組織の自動応答を作成できます。</span><span class="sxs-lookup"><span data-stu-id="995cd-170">You can create an auto attendant for your organization by using the Teams admin center.</span></span>

<span data-ttu-id="995cd-171">クラウド自動出席依頼の設定の詳細については、「クラウド自動応答を設定する」 [を参照してください](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="995cd-171">For information about setting up a Cloud auto attendendant, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="995cd-172">手順 9: サービス用電話番号 (電話会議、通話キュー、自動応答) の割り当て</span><span class="sxs-lookup"><span data-stu-id="995cd-172">Step 9: Assign service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="995cd-173"> **上記の手順 4** から、サービスの番号を作成したら、使用するサービスの種類ごとに番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-173">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want.</span></span> <span data-ttu-id="995cd-174">たとえば、専用サービス電話番号 (有料または無料電話番号) が必要な場合は、その番号を会議ブリッジに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-174">For example, if you want a dedicated service phone number (toll or toll-free), you'll need to assign the number to the conferencing bridge.</span></span>

- <span data-ttu-id="995cd-175">電話会議の場合 **、Teams** 管理センターの会議ブリッジに移動し、画面の指示に従って会議ブリッジに専用の番号を割り  >    >  当てできます。</span><span class="sxs-lookup"><span data-stu-id="995cd-175">For Audio Conferencing, you can assign a dedicated number to a conferencing bridge by going to **Teams admin center** > **Meetings** > **Conference bridges** and follow the prompts.</span></span>  <span data-ttu-id="995cd-176">詳細については、「電話会議  [ブリッジで有料](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)または無料電話番号を変更する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995cd-176">For more information, see  [Change the toll or toll-free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

- <span data-ttu-id="995cd-177">自動応答の場合 **、Teams** 管理センターの音声自動応答に移動し、画面の指示に従って、自動応答に専用の番号を  >    >  割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="995cd-177">For Auto Attendants, you can assign a dedicated number to an auto attendant by going to  **Teams admin center** > **Voice** > **Auto attendants** and follow the prompts.</span></span>  <span data-ttu-id="995cd-178">詳細については、「クラウド自動応答 [を設定する」を参照してください](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="995cd-178">For more information, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

- <span data-ttu-id="995cd-179">通話キューの場合は **、Teams** 管理センターの音声通話キューに移動し、画面の指示に従って、通話キューに専用の番号を  >    >  割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="995cd-179">For Call Queues, you can assign a dedicated number to a call queue by going to **Teams admin center** > **Voice** > **Call queues** and follow the prompts.</span></span> <span data-ttu-id="995cd-180">詳細については、「クラウド通話キュー [を作成する」を参照してください](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="995cd-180">For more information, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

<span data-ttu-id="995cd-181">新しいサービス番号を取得し、既存のサービス番号を転送する方法の詳細については、 [サービスの電話番号の取得](getting-service-phone-numbers.md)  を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995cd-181">For detailed information about getting new service numbers and porting existing service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

## <a name="step-10-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="995cd-182">手順 10: 組織のコミュニケーション クレジットをセットアップする</span><span class="sxs-lookup"><span data-stu-id="995cd-182">Step 10: Set up Communications Credits for your organization</span></span>

<span data-ttu-id="995cd-183">Microsoft Teams で無料電話番号を使用する場合は、コミュニケーション クレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-183">If you would like to use toll-free numbers with Microsoft Teams, You'll need to set up Communications Credits.</span></span> <span data-ttu-id="995cd-184">Microsoft では、任意の発信先にダイヤルアウトする機能が必要な通話プラン (国内または国際) および電話会議ユーザー用にコミュニケーション クレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-184">Microsoft recommends that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to any destination.</span></span> <span data-ttu-id="995cd-185">ご利用の通話プランまたは電話会議のサブスクリプションでは、多くの国や地域が含まれていますが、一部の発信先が含まれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="995cd-185">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> 

<span data-ttu-id="995cd-186">コミュニケーション クレジットの請求を設定しない場合や、ユーザーに **コミュニケーション クレジット** のライセンスを割り当てない場合に (国/地域の通話プランまたは電話会議プランに基づき) 組織の通話分数が不足すると、これらのユーザーは通話を発信することや、電話会議からダイヤルアウトすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="995cd-186">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="995cd-187">推奨される利用可能金額などの詳細については、「通信クレジットとは[](what-are-communications-credits.md)何か」および「組織の通信クレジット[を設定する」を参照してください](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="995cd-187">For more information, including recommended funding amounts, see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="995cd-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="995cd-188">Related topics</span></span>
[<span data-ttu-id="995cd-189">Microsoft 365 または Office 365 の電話システムで利用Office説明します。</span><span class="sxs-lookup"><span data-stu-id="995cd-189">Here's what you get with Phone System in Microsoft 365 or Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="995cd-190">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="995cd-190">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="995cd-191">Skype for Business および Microsoft Teams のサービス電話番号の取得</span><span class="sxs-lookup"><span data-stu-id="995cd-191">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="995cd-192">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="995cd-192">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
