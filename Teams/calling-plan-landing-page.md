---
title: Microsoft Teams の通話プラン
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: 通話プランのランディングページ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b9d1a012c545dbaf8f8c65d87f58718bda13946
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "34381838"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="2b630-103">適切な通話プランはどれですか?</span><span class="sxs-lookup"><span data-stu-id="2b630-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="2b630-104">[作業を開始](get-started-with-teams-quick-start.md)しました。</span><span class="sxs-lookup"><span data-stu-id="2b630-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="2b630-105">Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。</span><span class="sxs-lookup"><span data-stu-id="2b630-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="2b630-106">会議[&](deploy-meetings-microsoft-teams-landing-page.md)会議を展開したことがあるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="2b630-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="2b630-107">これで、クラウド音声のワークロードを追加する準備ができました。電話システムを使用して公衆交換電話網 (PSTN) に接続しています。</span><span class="sxs-lookup"><span data-stu-id="2b630-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="2b630-108">この記事では、組織のニーズに基づいて、通話プランの主要な展開決定と、構成する必要があるその他の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b630-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="2b630-109">Microsoft のクラウド音声サービスの詳細については、「 [Microsoft Teams でクラウド音声](cloud-voice-landing-page.md)を読む」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2b630-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="2b630-110">通話プランについて、詳細はこちらをご覧ください</span><span class="sxs-lookup"><span data-stu-id="2b630-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="2b630-111">次の記事では、Microsoft の通話プランの展開と使用に関する詳細情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="2b630-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="2b630-112">Office 365 の電話システム</span><span class="sxs-lookup"><span data-stu-id="2b630-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="2b630-113">Office 365 の通話プラン</span><span class="sxs-lookup"><span data-stu-id="2b630-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="2b630-114">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="2b630-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="2b630-115">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="2b630-115">Core deployment decisions</span></span>

<span data-ttu-id="2b630-116">Microsoft をテレフォニーキャリアとして使用するには、通話プランのライセンスを取得し、電話システムのユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b630-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="2b630-117">利用可能な通話プランには、次の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="2b630-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="2b630-118">国内通話プラン</span><span class="sxs-lookup"><span data-stu-id="2b630-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="2b630-119">国内および国際通話プラン</span><span class="sxs-lookup"><span data-stu-id="2b630-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="2b630-120">確認事項</span><span class="sxs-lookup"><span data-stu-id="2b630-120">Ask yourself</span></span>|<span data-ttu-id="2b630-121">アクション</span><span class="sxs-lookup"><span data-stu-id="2b630-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="2b630-122">地域で通話プランを利用できますか?</span><span class="sxs-lookup"><span data-stu-id="2b630-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="2b630-123">どのユーザーの場所で通話プランサービスを利用できますか?</span><span class="sxs-lookup"><span data-stu-id="2b630-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="2b630-124">詳細については、「[電話会議と通話プランの国と地域の空き時間](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)情報」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b630-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="2b630-125">ユーザーには国際通話が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="2b630-125">Do my users need international calling?</span></span> | <span data-ttu-id="2b630-126">詳細については、「 [Office 365 の通話プラン](calling-plans-for-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b630-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="2b630-127">ユーザーが通話プランのライセンスを持っているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="2b630-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="2b630-128">ライセンスを購入して割り当てるには、「[手順 2: ライセンスを購入して割り当てる](set-up-calling-plans.md#step-2-buy-and-assign-licenses)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b630-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="2b630-129">各ユーザーは、それぞれに1つの内向きダイヤル (DID) 電話番号を持っていますか?</span><span class="sxs-lookup"><span data-stu-id="2b630-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="2b630-130">電話番号を取得するには、「[手順 3: 電話番号を取得](set-up-calling-plans.md#step-3-get-phone-numbers)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b630-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="2b630-131">Office 365 に電話番号を転送する</span><span class="sxs-lookup"><span data-stu-id="2b630-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="2b630-132">現在のサービスプロバイダから Teams に電話番号を転送するのは簡単です。</span><span class="sxs-lookup"><span data-stu-id="2b630-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="2b630-133">お客さまの電話番号を Teams に移植すると、Microsoft はサービスプロバイダになり、これらの電話番号について請求されます。</span><span class="sxs-lookup"><span data-stu-id="2b630-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="2b630-134">詳細については、「 [Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b630-134">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="2b630-135">電話番号と緊急対応の場所</span><span class="sxs-lookup"><span data-stu-id="2b630-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="2b630-136">Office 365 の通話プランでは、組織内のすべてのユーザーが、固有の直通電話番号と、対応する有効な緊急対応の住所を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b630-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="2b630-137">緊急対応の住所に緊急対応の場所を指定することもできます (たとえば、オフィス番号やフロア番号)。</span><span class="sxs-lookup"><span data-stu-id="2b630-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="2b630-138">確認事項</span><span class="sxs-lookup"><span data-stu-id="2b630-138">Ask yourself</span></span>|<span data-ttu-id="2b630-139">アクション</span><span class="sxs-lookup"><span data-stu-id="2b630-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="2b630-140">緊急対応の住所と住所の情報を詳細に確認するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="2b630-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="2b630-141">詳細については、「[緊急対応の場所、アドレス、通話ルーティング](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b630-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="2b630-142">通話 id</span><span class="sxs-lookup"><span data-stu-id="2b630-142">Calling identity</span></span>

<span data-ttu-id="2b630-143">既定では、すべての発信通話で、割り当てられた電話番号が発信 id (発信者番号) として使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b630-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="2b630-144">通話の受信者は、すぐに発信者を特定して、通話を承諾または拒否するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="2b630-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="2b630-145">確認事項</span><span class="sxs-lookup"><span data-stu-id="2b630-145">Ask yourself</span></span>|<span data-ttu-id="2b630-146">アクション</span><span class="sxs-lookup"><span data-stu-id="2b630-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="2b630-147">発信者番号認識を無効にするか、無効にしますか?</span><span class="sxs-lookup"><span data-stu-id="2b630-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="2b630-148">発信者番号通知を変更またはブロックするには、「[ユーザーに発信者番号を設定](set-the-caller-id-for-a-user.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b630-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




