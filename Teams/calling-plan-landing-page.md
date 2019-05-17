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
description: 計画のランディング ページを呼び出す
appliesto:
- Microsoft Teams
ms.openlocfilehash: d85546df76b7699986d28152ff08003612df8331
ms.sourcegitcommit: d4b007b88469a820595ecdcf2a90854ecefe2809
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34108756"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="1de59-103">呼び出すことを計画するが適切でしょうか。</span><span class="sxs-lookup"><span data-stu-id="1de59-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="1de59-104">[開始](get-started-with-teams-quick-start.md)するが完了しました。</span><span class="sxs-lookup"><span data-stu-id="1de59-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="1de59-105">Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。</span><span class="sxs-lookup"><span data-stu-id="1de59-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="1de59-106">かもしれません[& 会議の会議](deploy-meetings-microsoft-teams-landing-page.md)を導入しました。</span><span class="sxs-lookup"><span data-stu-id="1de59-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="1de59-107">クラウド音声のワークロードを追加する準備が整いましたし、を公衆交換電話網 (PSTN) を接続する計画を呼び出すことでマイクロソフトの電話システムを使用すると判断しました。</span><span class="sxs-lookup"><span data-stu-id="1de59-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="1de59-108">この資料を構成すること、組織のニーズに基づいて計画を呼び出すと、追加の考慮事項の中核となる展開の決定について説明します。</span><span class="sxs-lookup"><span data-stu-id="1de59-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="1de59-109">マイクロソフトのクラウドの音声サービスの詳細については[マイクロソフトのチームでのクラウドの音声](cloud-voice-landing-page.md)を参照することもあります。</span><span class="sxs-lookup"><span data-stu-id="1de59-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="1de59-110">プランの呼び出しの詳細については</span><span class="sxs-lookup"><span data-stu-id="1de59-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="1de59-111">次の記事では、展開して、マイクロソフトでは予定の呼び出しを使用しての詳細についてを提供します。</span><span class="sxs-lookup"><span data-stu-id="1de59-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="1de59-112">Office 365 の電話システム</span><span class="sxs-lookup"><span data-stu-id="1de59-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="1de59-113">Office 365 の通話プラン</span><span class="sxs-lookup"><span data-stu-id="1de59-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="1de59-114">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="1de59-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="1de59-115">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="1de59-115">Core deployment decisions</span></span>

<span data-ttu-id="1de59-116">テレフォニー キャリアでは、Microsoft を使用するには、計画を呼び出してライセンスを取得し、電話システムのユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1de59-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="1de59-117">利用は 2 種類のプランを呼び出すことがあります。</span><span class="sxs-lookup"><span data-stu-id="1de59-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="1de59-118">国内通話プラン</span><span class="sxs-lookup"><span data-stu-id="1de59-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="1de59-119">国内または国際通話プラン</span><span class="sxs-lookup"><span data-stu-id="1de59-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="1de59-120">確認事項</span><span class="sxs-lookup"><span data-stu-id="1de59-120">Ask yourself</span></span>|<span data-ttu-id="1de59-121">アクション</span><span class="sxs-lookup"><span data-stu-id="1de59-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="1de59-122">計画を呼び出して自分の地域ではでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1de59-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="1de59-123">どのユーザーの場所には、サービスの計画を呼び出すことはありますか。</span><span class="sxs-lookup"><span data-stu-id="1de59-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="1de59-124">詳細については、[オーディオ会議や予定を呼び出すための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de59-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="1de59-125">ユーザーに国際通話が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="1de59-125">Do my users need international calling?</span></span> | <span data-ttu-id="1de59-126">詳細については、 [Office 365 のプランを呼び出す](calling-plans-for-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de59-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="1de59-127">自分のユーザーにはライセンスの計画を呼び出すことがありますか。</span><span class="sxs-lookup"><span data-stu-id="1de59-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="1de59-128">購入し、ライセンスを割り当てるを参照してください[手順 2: を購入し、ライセンスを割り当てる](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="1de59-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="1de59-129">各ユーザーには直接内側 (DID) 電話番号をダイヤルがありますか。</span><span class="sxs-lookup"><span data-stu-id="1de59-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="1de59-130">電話番号を取得するを参照してください[手順 3: 電話番号を取得する](set-up-calling-plans.md#step-3-get-phone-numbers)です。</span><span class="sxs-lookup"><span data-stu-id="1de59-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="1de59-131">Office 365 に電話番号を転送する</span><span class="sxs-lookup"><span data-stu-id="1de59-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="1de59-132">チーム、現在のサービス プロバイダーから自分の電話番号に転送するのには簡単です。</span><span class="sxs-lookup"><span data-stu-id="1de59-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="1de59-133">チームに自分の電話番号を移植した後、Microsoft は、サービス ・ プロバイダーになり、に対する料金を請求している電話番号。</span><span class="sxs-lookup"><span data-stu-id="1de59-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="1de59-134">詳細については、 [Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de59-134">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="1de59-135">電話番号と緊急時の場所</span><span class="sxs-lookup"><span data-stu-id="1de59-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="1de59-136">Office 365 のプランを呼び出すこと、内向きの一意な直通を組織のニーズのすべてのユーザーは、番号と対応する検証済みの緊急アドレス電話 (でした)。</span><span class="sxs-lookup"><span data-stu-id="1de59-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="1de59-137">緊急のアドレス (オフィス番号またはフロア番号など) では、緊急の場所を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1de59-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="1de59-138">確認事項</span><span class="sxs-lookup"><span data-stu-id="1de59-138">Ask yourself</span></span>|<span data-ttu-id="1de59-139">アクション</span><span class="sxs-lookup"><span data-stu-id="1de59-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="1de59-140">詳細な方法が必要に緊急時のアドレスと場所の情報か、</span><span class="sxs-lookup"><span data-stu-id="1de59-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="1de59-141">詳細についてを参照してください[緊急の場所、住所、および通話のルーティングには何ですか?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)です。</span><span class="sxs-lookup"><span data-stu-id="1de59-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="1de59-142">識別情報を呼び出す</span><span class="sxs-lookup"><span data-stu-id="1de59-142">Calling identity</span></span>

<span data-ttu-id="1de59-143">既定では、すべての発信呼び出しは、呼び出し元の id (呼び出し元 ID) として割り当てられた電話番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="1de59-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="1de59-144">呼び出しの受信者は、呼び出し元を識別する迅速かつ呼び出しを承認または拒否かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="1de59-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="1de59-145">確認事項</span><span class="sxs-lookup"><span data-stu-id="1de59-145">Ask yourself</span></span>|<span data-ttu-id="1de59-146">アクション</span><span class="sxs-lookup"><span data-stu-id="1de59-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="1de59-147">マスクしたり、発信者番号通知を無効にするか。</span><span class="sxs-lookup"><span data-stu-id="1de59-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="1de59-148">呼び出し元 ID のブロックを変更または、[ユーザーの発信者番号の設定](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de59-148">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||




