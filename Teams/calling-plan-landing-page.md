---
title: Microsoft Teams の通話プラン
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Teams のクラウドボイスで組織に最適な Microsoft 電話システム通話プランを決定する。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b1fb0abed3477039f4c19c0e2de0ea696626f35
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905029"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="c328a-103">どの通話プランが適していますか?</span><span class="sxs-lookup"><span data-stu-id="c328a-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="c328a-104">[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。</span><span class="sxs-lookup"><span data-stu-id="c328a-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="c328a-105">Teams の[チャット、チーム、チャネル、アプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。</span><span class="sxs-lookup"><span data-stu-id="c328a-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="c328a-106">[会議および電話会議](deploy-meetings-microsoft-teams-landing-page.md)を展開した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c328a-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="c328a-107">クラウド ボイスのワークロードを追加する準備ができました。通話プランが設定された Microsoft 電話システムを使用して公衆交換電話網 (PSTN) に接続することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="c328a-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="c328a-108">この記事では、通話プランの展開に関する重要な決定事項に加え、お客様の組織のニーズに合わせて構成する必要があるその他の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="c328a-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="c328a-109">また、Microsoft のクラウド ボイス サービスの詳細については、「[Microsoft Teams でのクラウド ボイス](cloud-voice-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c328a-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="c328a-110">通話プランに関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="c328a-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="c328a-111">Microsoft 通話プランの展開と使用の詳細については、次の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c328a-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="c328a-112">Office 365 の電話システム</span><span class="sxs-lookup"><span data-stu-id="c328a-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="c328a-113">Office 365 の通話プラン</span><span class="sxs-lookup"><span data-stu-id="c328a-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="c328a-114">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="c328a-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="c328a-115">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="c328a-115">Core deployment decisions</span></span>

<span data-ttu-id="c328a-116">Microsoft をテレフォニー通信事業者として使用するには、通話プランのライセンスを取得して、そのライセンスを電話システムのユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c328a-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="c328a-117">使用できる通話プランには次の 2 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="c328a-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="c328a-118">国内通話プラン</span><span class="sxs-lookup"><span data-stu-id="c328a-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="c328a-119">国内および国際通話プラン</span><span class="sxs-lookup"><span data-stu-id="c328a-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="c328a-120">確認事項</span><span class="sxs-lookup"><span data-stu-id="c328a-120">Ask yourself</span></span>|<span data-ttu-id="c328a-121">Action</span><span class="sxs-lookup"><span data-stu-id="c328a-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="c328a-122">自分の住んでいる地域で通話プランを利用できますか?</span><span class="sxs-lookup"><span data-stu-id="c328a-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="c328a-123">通話プラン サービスを利用できるのはどのユーザーの場所ですか?</span><span class="sxs-lookup"><span data-stu-id="c328a-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="c328a-124">詳細については、「[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c328a-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="c328a-125">ユーザーは国際電話を利用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c328a-125">Do my users need international calling?</span></span> | <span data-ttu-id="c328a-126">詳細については、「[Office 365 の通話プラン](calling-plans-for-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c328a-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="c328a-127">ユーザーは通話プランのライセンスを持っていますか?</span><span class="sxs-lookup"><span data-stu-id="c328a-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="c328a-128">ライセンスを購入して割り当てるには、「[手順 2: ライセンスを購入して割り当てる](set-up-calling-plans.md#step-2-buy-and-assign-licenses)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c328a-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="c328a-129">ユーザーはそれぞれ直通社内通話 (DID) 電話番号がありますか?</span><span class="sxs-lookup"><span data-stu-id="c328a-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="c328a-130">電話番号を取得するには、「[手順 3: 電話番号を取得する](set-up-calling-plans.md#step-3-get-phone-numbers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c328a-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="c328a-131">Office 365 に電話番号を転送する</span><span class="sxs-lookup"><span data-stu-id="c328a-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="c328a-132">電話番号を現在のサービス プロバイダーから Teams に簡単に移行できます。</span><span class="sxs-lookup"><span data-stu-id="c328a-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="c328a-133">電話番号を Teams に移行した後、Microsoft がサービス プロバイダーになり、それらの電話番号に対する請求を行います。</span><span class="sxs-lookup"><span data-stu-id="c328a-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="c328a-134">詳細については、「[電話番号を Teams に転送する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c328a-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="c328a-135">電話番号と緊急対応の場所</span><span class="sxs-lookup"><span data-stu-id="c328a-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="c328a-136">Office 365 の通話プランを使用している場合、組織内のすべてのユーザーには、固有の直通社内通話 (DID) 電話番号と、対応する検証済みの緊急対応の住所が必要です。</span><span class="sxs-lookup"><span data-stu-id="c328a-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="c328a-137">緊急対応の住所に、緊急対応の場所 (たとえば、部屋番号や階数) を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c328a-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="c328a-138">確認事項</span><span class="sxs-lookup"><span data-stu-id="c328a-138">Ask yourself</span></span>|<span data-ttu-id="c328a-139">Action</span><span class="sxs-lookup"><span data-stu-id="c328a-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="c328a-140">緊急対応の住所と場所をどれほど詳しく指定しますか?</span><span class="sxs-lookup"><span data-stu-id="c328a-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="c328a-141">詳細については、[緊急対応の場所、住所、通話ルーティングの概要](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c328a-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="c328a-142">通話 ID</span><span class="sxs-lookup"><span data-stu-id="c328a-142">Calling identity</span></span>

<span data-ttu-id="c328a-143">既定で、すべての発信通話は、割り当てられた電話番号を通話 ID (発信者 ID) として使用します。</span><span class="sxs-lookup"><span data-stu-id="c328a-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="c328a-144">通話の受信者は、発信者をすばやく特定して、通話を承諾または拒否するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="c328a-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="c328a-145">確認事項</span><span class="sxs-lookup"><span data-stu-id="c328a-145">Ask yourself</span></span>|<span data-ttu-id="c328a-146">Action</span><span class="sxs-lookup"><span data-stu-id="c328a-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="c328a-147">発信者 ID のマスクや無効化を行いますか?</span><span class="sxs-lookup"><span data-stu-id="c328a-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="c328a-148">発信者 ID を変更またはブロックするには、「[ユーザーの発信者 ID を設定する](set-the-caller-id-for-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c328a-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




