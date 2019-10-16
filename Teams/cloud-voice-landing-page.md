---
title: Microsoft Teams での Cloud Voice
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
search.appverid: MET150
description: Teams でクラウドボイスを展開するためのランディングページ
appliesto:
- Microsoft Teams
ms.openlocfilehash: f60159d2d9d65afd3837a0b48b82ac7e13b8e0df
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37515834"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="e05e0-103">Microsoft Teams での Cloud Voice</span><span class="sxs-lookup"><span data-stu-id="e05e0-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="e05e0-104">[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。</span><span class="sxs-lookup"><span data-stu-id="e05e0-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="e05e0-105">Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。</span><span class="sxs-lookup"><span data-stu-id="e05e0-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="e05e0-106">会議[&](deploy-meetings-microsoft-teams-landing-page.md)会議を展開したことがあるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="e05e0-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="e05e0-107">これで、ユーザーにクラウド音声機能を追加する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="e05e0-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="e05e0-108">クラウドボイスは、構内交換機 (PBX) 機能と、公衆交換電話網 (PSTN) に接続するためのオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="e05e0-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="e05e0-109">この記事では、組織のプロファイルとビジネス要件に基づいて、既定のクラウドボイス設定を変更する必要があるかどうかを決定するのに役立ちます。次に、それぞれの変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="e05e0-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="e05e0-110">設定を2つのグループに分割しました。これからは、主要[な変更](#core-deployment-decisions)の中心となります。</span><span class="sxs-lookup"><span data-stu-id="e05e0-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="e05e0-111">2 番目のグループには、組織のニーズ応じた構成が求められる可能性がある[追加の設定](#additional-deployment-decisions)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e05e0-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="e05e0-112">すべての組織が主要な決定を行い、その他の要件が組織にある場合は、次の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="e05e0-113">クラウドの音声について、詳細はこちらをご覧ください</span><span class="sxs-lookup"><span data-stu-id="e05e0-113">Learn more about cloud voice</span></span>

<span data-ttu-id="e05e0-114">次の記事では、Teams でのクラウド音声機能の展開と使用に関する詳細情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="e05e0-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="e05e0-115">Office 365 の電話システム</span><span class="sxs-lookup"><span data-stu-id="e05e0-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="e05e0-116">通話プランが設定された電話システム</span><span class="sxs-lookup"><span data-stu-id="e05e0-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="e05e0-117">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="e05e0-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="e05e0-118">Cloud Voice の展開</span><span class="sxs-lookup"><span data-stu-id="e05e0-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="e05e0-119">Microsoft テレフォニー ソリューション</span><span class="sxs-lookup"><span data-stu-id="e05e0-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="e05e0-120">電話システムの詳細については、次のセッションをご覧ください。 [Microsoft Teams での電話システムの紹介](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="e05e0-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="e05e0-121">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="e05e0-121">Core deployment decisions</span></span>

<span data-ttu-id="e05e0-122">次に示す設定は、ほとんどの組織が変更を必要とするものです (Teams の既定の設定では、組織に適した動作にならない場合)。</span><span class="sxs-lookup"><span data-stu-id="e05e0-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="e05e0-123">電話システム (Office 365)</span><span class="sxs-lookup"><span data-stu-id="e05e0-123">Phone System (Office 365)</span></span>

<span data-ttu-id="e05e0-124">電話システムは Microsoft の技術であり、Office 365 クラウドで、通話制御と構内交換 (PBX) 機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e05e0-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="e05e0-125">電話システムを使用すると、既存の構内交換機 (PBX) システムを、Office 365 から直接配布された機能セットに置き換えることができます。また、会社のクラウド生産性エクスペリエンスに密接に統合されています。</span><span class="sxs-lookup"><span data-stu-id="e05e0-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company’s cloud productivity experience.</span></span>


|<span data-ttu-id="e05e0-126">確認事項</span><span class="sxs-lookup"><span data-stu-id="e05e0-126">Ask yourself</span></span>|<span data-ttu-id="e05e0-127">アクション</span><span class="sxs-lookup"><span data-stu-id="e05e0-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="e05e0-128">電話システムを実装するのは、どのようなユーザーの場所またはオフィスですか?</span><span class="sxs-lookup"><span data-stu-id="e05e0-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="e05e0-129">電話システムの詳細については、「 [Office 365 の電話システムとは](what-is-phone-system-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="e05e0-130">公衆交換電話網 (PSTN) への接続</span><span class="sxs-lookup"><span data-stu-id="e05e0-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="e05e0-131">電話システムを公衆交換電話網 (PSTN) に接続して、ユーザーが世界中で電話をかけることができるようにするには、ビジネスニーズに応じたオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="e05e0-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="e05e0-132">次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-132">Ask yourself the following:</span></span>


|<span data-ttu-id="e05e0-133">確認事項</span><span class="sxs-lookup"><span data-stu-id="e05e0-133">Ask yourself</span></span>|<span data-ttu-id="e05e0-134">アクション</span><span class="sxs-lookup"><span data-stu-id="e05e0-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="e05e0-135">テレフォニーキャリアとして Microsoft 通話プランを使用しますか?</span><span class="sxs-lookup"><span data-stu-id="e05e0-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="e05e0-136">詳細については、「[通話プランを使用した電話システム](calling-plan-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="e05e0-137">自分のテレフォニーキャリアを使用する必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="e05e0-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="e05e0-138">詳細については、「[ダイレクトルーティングを使用した電話システム](direct-routing-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="e05e0-139">その他の展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="e05e0-139">Additional deployment decisions</span></span>

<span data-ttu-id="e05e0-140">組織のニーズと構成に基づいて、次の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e05e0-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="e05e0-141">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="e05e0-141">Voicemail</span></span>
- <span data-ttu-id="e05e0-142">通話 id</span><span class="sxs-lookup"><span data-stu-id="e05e0-142">Calling identity</span></span>
- <span data-ttu-id="e05e0-143">Microsoft からの電話番号</span><span class="sxs-lookup"><span data-stu-id="e05e0-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="e05e0-144">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e05e0-144">Dial plans</span></span>
- <span data-ttu-id="e05e0-145">通話キュー</span><span class="sxs-lookup"><span data-stu-id="e05e0-145">Call queues</span></span>
- <span data-ttu-id="e05e0-146">自動応答</span><span class="sxs-lookup"><span data-stu-id="e05e0-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="e05e0-147">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="e05e0-147">Voicemail</span></span>

<span data-ttu-id="e05e0-148">Azure ボイスメールサービスを利用したクラウドボイスメールは、Exchange メールボックスのみを対象としたボイスメールのデポジットをサポートしており、サードパーティのメールシステムをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e05e0-148">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span> <span data-ttu-id="e05e0-149">クラウドボイスメールには、既定で組織内のすべてのユーザーに対して有効になるボイスメールの議事録が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e05e0-149">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="e05e0-150">ビジネスニーズによっては、特定のユーザーまたは組織全体のすべてのユーザーに対してボイスメールを無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e05e0-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="e05e0-151">確認事項</span><span class="sxs-lookup"><span data-stu-id="e05e0-151">Ask yourself</span></span>|<span data-ttu-id="e05e0-152">アクション</span><span class="sxs-lookup"><span data-stu-id="e05e0-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="e05e0-153">クラウドボイスメールを有効にしますか?</span><span class="sxs-lookup"><span data-stu-id="e05e0-153">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="e05e0-154">ボイスメールのセットアップ手順については、「[クラウドボイスメール](set-up-phone-system-voicemail.md)をセットアップする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-154">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="e05e0-155">一部またはすべてのユーザーに対してボイスメールの書き起こしを有効にしますか?</span><span class="sxs-lookup"><span data-stu-id="e05e0-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="e05e0-156">ボイスメールのトランスクリプト機能をオフにするには、「[組織でボイスメールポリシーを設定](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="e05e0-157">通話 id</span><span class="sxs-lookup"><span data-stu-id="e05e0-157">Calling identity</span></span>

<span data-ttu-id="e05e0-158">既定では、すべての発信通話で、割り当てられた電話番号が発信 id (発信者番号) として使用されます。</span><span class="sxs-lookup"><span data-stu-id="e05e0-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="e05e0-159">通話の受信者は、すぐに発信者を特定して、通話を承諾または拒否するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="e05e0-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="e05e0-160">確認事項</span><span class="sxs-lookup"><span data-stu-id="e05e0-160">Ask yourself</span></span>|<span data-ttu-id="e05e0-161">アクション</span><span class="sxs-lookup"><span data-stu-id="e05e0-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="e05e0-162">発信者番号認識を無効にするか、無効にしますか?</span><span class="sxs-lookup"><span data-stu-id="e05e0-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="e05e0-163">発信者番号通知を変更またはブロックするには、「[ユーザーに発信者番号を設定](set-the-caller-id-for-a-user.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-163">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="e05e0-164">Microsoft からの電話番号</span><span class="sxs-lookup"><span data-stu-id="e05e0-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="e05e0-165">Microsoft には、2種類の電話番号が用意されています。*加入者*(ユーザー) 番号は、組織内のユーザーに割り当てることができます。また、電話番号は有料またはフリーダイヤルのサービス*番号とし*て利用できます。加入者番号よりもキャパシティ。電話会議、自動応答、通話キューなどのサービスに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e05e0-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="e05e0-166">確認事項</span><span class="sxs-lookup"><span data-stu-id="e05e0-166">Ask yourself</span></span>|<span data-ttu-id="e05e0-167">アクション</span><span class="sxs-lookup"><span data-stu-id="e05e0-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="e05e0-168">Microsoft からの新しい電話番号が必要なユーザーの場所</span><span class="sxs-lookup"><span data-stu-id="e05e0-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="e05e0-169">電話番号を取得する方法については、「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」および「[ユーザーの電話番号を取得](getting-phone-numbers-for-your-users.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="e05e0-170">必要な電話番号の種類 (加入者またはサービス)</span><span class="sxs-lookup"><span data-stu-id="e05e0-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="e05e0-171">必要な電話番号の種類を選択するには、「[通話プラン用に使用される電話番号が異なる](different-kinds-of-phone-numbers-used-for-calling-plans.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="e05e0-172">既存の電話番号を Office 365 に移植するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="e05e0-172">How do I port existing phone numbers to Office 365?</span></span>|<span data-ttu-id="e05e0-173">詳細については、「 [Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-173">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="e05e0-174">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e05e0-174">Dial plans</span></span>

<span data-ttu-id="e05e0-175">Office 365 の電話システム機能のダイヤルプランは、ダイヤルされた電話番号を別の形式 (通常は164形式) に変換する正規化ルールのセットです。これは、通話承認と通話ルーティングに適しています。</span><span class="sxs-lookup"><span data-stu-id="e05e0-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="e05e0-176">ダイヤル プランの詳細については、「[ダイヤル プランについて](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="e05e0-177">確認事項</span><span class="sxs-lookup"><span data-stu-id="e05e0-177">Ask yourself</span></span>|<span data-ttu-id="e05e0-178">アクション</span><span class="sxs-lookup"><span data-stu-id="e05e0-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="e05e0-179">組織はダイヤル プランのカスタマイズを必要としているか?</span><span class="sxs-lookup"><span data-stu-id="e05e0-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="e05e0-180">カスタムダイヤルプランが必要かどうかを判断する方法については、「[テナントダイヤルプランの計画](what-are-dial-plans.md#planning-for-tenant-dial-plans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="e05e0-181">どのユーザーがダイヤル プランのカスタマイズを要求していて、どのテナント ダイヤル プランを各ユーザーに割り当てる必要があるか?</span><span class="sxs-lookup"><span data-stu-id="e05e0-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="e05e0-182">PowerShell のカスタマイズされたダイヤルプランにユーザーを追加する方法については、「[ダイヤルプランを作成して管理](create-and-manage-dial-plans.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="e05e0-183">通話キュー</span><span class="sxs-lookup"><span data-stu-id="e05e0-183">Call queues</span></span>

<span data-ttu-id="e05e0-p107">クラウド通話キューには、誰かが組織の電話番号に電話をかけた際に流れる挨拶メッセージ、通話を自動的に保留する機能、および保留中に電話をかけてきた方に音楽を流し、その間に通話への対応が可能な次の電話エージェントを探す機能が含まれています。1 つまたは複数の通話キューを組織のために作成できます。</span><span class="sxs-lookup"><span data-stu-id="e05e0-p107">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="e05e0-186">確認事項</span><span class="sxs-lookup"><span data-stu-id="e05e0-186">Ask yourself</span></span>|<span data-ttu-id="e05e0-187">アクション</span><span class="sxs-lookup"><span data-stu-id="e05e0-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="e05e0-188">組織には通話キューが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="e05e0-188">Does my organization need call queues?</span></span> | <span data-ttu-id="e05e0-189">詳細については、「[クラウドの通話キューを作成する](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)」と「[電話システム](setting-up-your-phone-system.md)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-189">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="e05e0-190">自動応答</span><span class="sxs-lookup"><span data-stu-id="e05e0-190">Auto attendants</span></span>

<span data-ttu-id="e05e0-191">クラウド自動応答を使用すると、外部および内部の発信者がメニューシステムを通じて組織内の会社のユーザーや部署に通話を発信したり、転送したりできるように、組織のメニューシステムを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e05e0-191">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="e05e0-192">確認事項</span><span class="sxs-lookup"><span data-stu-id="e05e0-192">Ask yourself</span></span>|<span data-ttu-id="e05e0-193">アクション</span><span class="sxs-lookup"><span data-stu-id="e05e0-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="e05e0-194">組織に自動応答が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="e05e0-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="e05e0-195">詳細については、「[クラウド自動応答](what-are-phone-system-auto-attendants.md)と[クラウド自動応答のセットアップ](create-a-phone-system-auto-attendant.md)とは」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-195">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="e05e0-196">デバイス</span><span class="sxs-lookup"><span data-stu-id="e05e0-196">Devices</span></span>

<span data-ttu-id="e05e0-197">サポートされているデバイスの詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05e0-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="e05e0-198">Microsoft Teams でのデバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="e05e0-198">Manage your devices in Microsoft Teams</span></span>](device-management.md)
- [<span data-ttu-id="e05e0-199">IP 電話</span><span class="sxs-lookup"><span data-stu-id="e05e0-199">IP Phones</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="e05e0-200">USB オーディオ デバイスおよびビデオ デバイス</span><span class="sxs-lookup"><span data-stu-id="e05e0-200">USB audio and video devices</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="e05e0-201">デバイスのインテリジェントな通信</span><span class="sxs-lookup"><span data-stu-id="e05e0-201">Intelligent communications for devices</span></span>](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


