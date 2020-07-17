---
title: Microsoft Teams でのクラウド ボイス
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: クラウドボイス機能についての詳細を確認して、必要な展開の意思決定について理解してください。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8106e5ef30b71ec82e9b1ae42f785b7a73b170a5
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158645"
---
# <a name="voice---phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="62e29-103">ボイスフォンシステムと PSTN 接続オプション</span><span class="sxs-lookup"><span data-stu-id="62e29-103">Voice - Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="62e29-104">
            [使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。</span><span class="sxs-lookup"><span data-stu-id="62e29-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="62e29-105">Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。</span><span class="sxs-lookup"><span data-stu-id="62e29-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="62e29-106">[会議および電話会議](deploy-meetings-microsoft-teams-landing-page.md)も展開しました。</span><span class="sxs-lookup"><span data-stu-id="62e29-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="62e29-107">これで、ユーザーに音声機能を追加する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="62e29-107">Now you're ready to add voice capabilities for your users.</span></span> 

<span data-ttu-id="62e29-108">Voice は、構内交換機 (PBX) 機能と、公衆交換電話網 (PSTN) に接続するためのオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="62e29-108">Voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="62e29-109">この記事では、組織のプロファイルとビジネス要件に基づいて、既定の音声設定を変更する必要があるかどうかを決定する際に、それぞれの変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="62e29-109">This article helps you decide whether you need to change any of the default voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="62e29-110">設定については 2 つのグループに分け、[変更する可能性が高いと考えられる](#core-deployment-decisions)中心的な部分から説明します。</span><span class="sxs-lookup"><span data-stu-id="62e29-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="62e29-111">2 番目のグループには、組織のニーズ応じた構成する可能性のある[追加の設定](#additional-deployment-decisions)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="62e29-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="62e29-112">中心的な部分についてはすべての組織が実行し、残りの内容は、組織に追加の要件がある場合に確認するようお勧めします。</span><span class="sxs-lookup"><span data-stu-id="62e29-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-voice"></a><span data-ttu-id="62e29-113">音声についての詳細はこちら</span><span class="sxs-lookup"><span data-stu-id="62e29-113">Learn more about voice</span></span>

<span data-ttu-id="62e29-114">次の記事では、Teams での音声機能の展開と使用に関する詳細情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="62e29-114">The following articles provide more information about deploying and using voice features in Teams:</span></span>

- [<span data-ttu-id="62e29-115">Microsoft 365 または Office 365 の電話システム</span><span class="sxs-lookup"><span data-stu-id="62e29-115">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="62e29-116">通話プランが設定された電話システム</span><span class="sxs-lookup"><span data-stu-id="62e29-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="62e29-117">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="62e29-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="62e29-118">Microsoft テレフォニー ソリューション</span><span class="sxs-lookup"><span data-stu-id="62e29-118">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="62e29-119">電話システムの詳細については、「[Microsoft Teams での電話システムの概要](https://aka.ms/teams-phone-system)」のセッションを視聴してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-119">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="62e29-120">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="62e29-120">Core deployment decisions</span></span>

<span data-ttu-id="62e29-121">次に示す設定は、ほとんどの組織が変更を必要とするものです (Teams の既定の設定では、組織に適した動作にならない場合)。</span><span class="sxs-lookup"><span data-stu-id="62e29-121">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="62e29-122">電話システム (Office 365)</span><span class="sxs-lookup"><span data-stu-id="62e29-122">Phone System (Office 365)</span></span>

<span data-ttu-id="62e29-123">電話システムは、microsoft 365 または Office 365 クラウドでの通話管理および構内交換 (PBX) 機能を有効にするための Microsoft のテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="62e29-123">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud.</span></span> <span data-ttu-id="62e29-124">電話システムを使用すると、既存の構内交換機 (PBX) システムを、Microsoft 365 または Office 365 から直接配信され、会社のクラウド生産性エクスペリエンスに緊密に統合することができます。</span><span class="sxs-lookup"><span data-stu-id="62e29-124">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Microsoft 365 or Office 365 and tightly integrated into the company's cloud productivity experience.</span></span>


|<span data-ttu-id="62e29-125">確認事項</span><span class="sxs-lookup"><span data-stu-id="62e29-125">Ask yourself</span></span>|<span data-ttu-id="62e29-126">操作</span><span class="sxs-lookup"><span data-stu-id="62e29-126">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="62e29-127">どんなユーザーの場所、またはオフィスに電話システムを実装しますか?</span><span class="sxs-lookup"><span data-stu-id="62e29-127">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="62e29-128">電話システムの詳細については、「 [Microsoft 365 または Office 365 の電話システムとは](what-is-phone-system-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-128">For more information about Phone System, see [What is Phone System in Microsoft 365 or Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="62e29-129">公衆交換電話網 (PSTN) への接続</span><span class="sxs-lookup"><span data-stu-id="62e29-129">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="62e29-130">電話システムを公衆交換電話網 (PSTN) へ接続してユーザーが世界中に電話をかけることができるようにする場合、ビジネス ニーズに応じた選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="62e29-130">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="62e29-131">次の点について確認してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-131">Ask yourself the following:</span></span>


|<span data-ttu-id="62e29-132">確認事項</span><span class="sxs-lookup"><span data-stu-id="62e29-132">Ask yourself</span></span>|<span data-ttu-id="62e29-133">操作</span><span class="sxs-lookup"><span data-stu-id="62e29-133">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="62e29-134">Microsoft 通話プランをテレフォニー通信事業者として使用しますか?</span><span class="sxs-lookup"><span data-stu-id="62e29-134">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="62e29-135">詳細については、「[通話プランが設定された電話システム](calling-plan-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-135">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="62e29-136">自分のテレフォニー通信事業者を使用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="62e29-136">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="62e29-137">詳細については、「[直接ルーティングを行う電話システム](direct-routing-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-137">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="62e29-138">その他の展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="62e29-138">Additional deployment decisions</span></span>

<span data-ttu-id="62e29-139">次の設定は、組織のニーズと構成に基づいて変更できます。</span><span class="sxs-lookup"><span data-stu-id="62e29-139">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="62e29-140">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="62e29-140">Voicemail</span></span>
- <span data-ttu-id="62e29-141">通話 ID</span><span class="sxs-lookup"><span data-stu-id="62e29-141">Calling identity</span></span>
- <span data-ttu-id="62e29-142">Microsoft からの電話番号</span><span class="sxs-lookup"><span data-stu-id="62e29-142">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="62e29-143">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="62e29-143">Dial plans</span></span>
- <span data-ttu-id="62e29-144">通話キュー</span><span class="sxs-lookup"><span data-stu-id="62e29-144">Call queues</span></span>
- <span data-ttu-id="62e29-145">自動応答</span><span class="sxs-lookup"><span data-stu-id="62e29-145">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="62e29-146">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="62e29-146">Voicemail</span></span>

<span data-ttu-id="62e29-147">Azure ボイスメールサービスを利用したクラウドボイスメールは、Exchange メールボックスのみを対象としたボイスメールのデポジットをサポートしており、サードパーティのメールシステムをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="62e29-147">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn't support third-party email systems.</span></span> <span data-ttu-id="62e29-148">クラウド ボイスメールでは、組織内のすべてのユーザーに対してボイスメールの文字起こしが既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="62e29-148">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="62e29-149">会社のニーズに応じて、特定のユーザーまたは組織全体の全ユーザーに対してボイスメールの文字起こしを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="62e29-149">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="62e29-150">確認事項</span><span class="sxs-lookup"><span data-stu-id="62e29-150">Ask yourself</span></span>|<span data-ttu-id="62e29-151">操作</span><span class="sxs-lookup"><span data-stu-id="62e29-151">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="62e29-152">クラウド ボイスメールを有効にしますか?</span><span class="sxs-lookup"><span data-stu-id="62e29-152">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="62e29-153">ボイスメールのセットアップ手順については、「[クラウド ボイスメールのセットアップ](set-up-phone-system-voicemail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-153">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="62e29-154">一部またはすべてのユーザーのボイスメールの文字起こしを有効にしますか?</span><span class="sxs-lookup"><span data-stu-id="62e29-154">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="62e29-155">ボイスメールの文字起こしをオフにする方法については、「[組織のボイスメール ポリシーの設定](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-155">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="62e29-156">通話 ID</span><span class="sxs-lookup"><span data-stu-id="62e29-156">Calling identity</span></span>

<span data-ttu-id="62e29-157">既定で、すべての発信通話は、割り当てられた電話番号を通話 ID (発信者 ID) として使用します。</span><span class="sxs-lookup"><span data-stu-id="62e29-157">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="62e29-158">通話の受信者は、発信者をすばやく特定して、通話を承諾または拒否するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="62e29-158">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="62e29-159">確認事項</span><span class="sxs-lookup"><span data-stu-id="62e29-159">Ask yourself</span></span>|<span data-ttu-id="62e29-160">操作</span><span class="sxs-lookup"><span data-stu-id="62e29-160">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="62e29-161">発信者 ID のマスクや無効化を行いますか?</span><span class="sxs-lookup"><span data-stu-id="62e29-161">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="62e29-162">発信者 ID を変更またはブロックするには、「[ユーザーの発信者 ID を設定する](set-the-caller-id-for-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-162">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="62e29-163">Microsoft からの電話番号</span><span class="sxs-lookup"><span data-stu-id="62e29-163">Phone numbers from Microsoft</span></span>

<span data-ttu-id="62e29-164">Microsoft では、2 種類の電話番号が用意されています。*サブスクライバー* (ユーザー) 番号は、組織内のユーザーに割り当てることができます。*サービス*番号は、有料および無料のサービス番号として使うことができ、サブスクライバー番号よりも大きな同時呼び出しの容量があり、電話会議、自動応答、通話キューなどのサービスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="62e29-164">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="62e29-165">確認事項</span><span class="sxs-lookup"><span data-stu-id="62e29-165">Ask yourself</span></span>|<span data-ttu-id="62e29-166">操作</span><span class="sxs-lookup"><span data-stu-id="62e29-166">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="62e29-167">Microsoft からの新しい電話番号が必要なのはどのユーザー ロケーションですか?</span><span class="sxs-lookup"><span data-stu-id="62e29-167">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="62e29-168">電話番号を取得する方法については、「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」および「[ユーザー用の電話番号を取得する](getting-phone-numbers-for-your-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-168">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="62e29-169">どの種類の電話番号が必要ですか (サブスクライバーまたはサービス)?</span><span class="sxs-lookup"><span data-stu-id="62e29-169">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="62e29-170">必要な電話番号の種類を選択するには、「[通話プランで使用される電話番号の種類](different-kinds-of-phone-numbers-used-for-calling-plans.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-170">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="62e29-171">どんな方法で既存の電話番号を Teams に移植しますか?</span><span class="sxs-lookup"><span data-stu-id="62e29-171">How do I port existing phone numbers to Teams?</span></span>|<span data-ttu-id="62e29-172">詳細については、「[Microsoft Teams に電話番号を転送する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-172">For more information, see [Transfer phone numbers to Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="62e29-173">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="62e29-173">Dial plans</span></span>

<span data-ttu-id="62e29-174">Microsoft 365 または Office 365 の電話システム機能のダイヤルプランは、ダイヤルした電話番号を別の形式 (通常は164形式) に変換する正規化ルールのセットです。</span><span class="sxs-lookup"><span data-stu-id="62e29-174">A dial plan in the Phone System feature of Microsoft 365 or Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="62e29-175">ダイヤル プランの詳細については、「[ダイヤル プランについて](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-175">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="62e29-176">確認事項</span><span class="sxs-lookup"><span data-stu-id="62e29-176">Ask yourself</span></span>|<span data-ttu-id="62e29-177">アクション</span><span class="sxs-lookup"><span data-stu-id="62e29-177">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="62e29-178">組織はダイヤル プランのカスタマイズを必要としているか?</span><span class="sxs-lookup"><span data-stu-id="62e29-178">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="62e29-179">カスタムのダイヤル プランが必要かどうかを判断するには、「[テナント ダイヤル プランの計画](what-are-dial-plans.md#planning-for-tenant-dial-plans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-179">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="62e29-180">どのユーザーがダイヤル プランのカスタマイズを要求していて、どのテナント ダイヤル プランを各ユーザーに割り当てる必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="62e29-180">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="62e29-181">PowerShell で、カスタマイズしたダイヤル プランにユーザーを追加するには、「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-181">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="62e29-182">通話キュー</span><span class="sxs-lookup"><span data-stu-id="62e29-182">Call queues</span></span>

<span data-ttu-id="62e29-p107">クラウド通話キューには、誰かが組織の電話番号に電話をかけた際に流れる挨拶メッセージ、通話を自動的に保留する機能、および保留中に電話をかけてきた方に音楽を流し、その間に通話への対応が可能な次の電話エージェントを探す機能が含まれています。1 つまたは複数の通話キューを組織のために作成できます。</span><span class="sxs-lookup"><span data-stu-id="62e29-p107">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="62e29-185">確認事項</span><span class="sxs-lookup"><span data-stu-id="62e29-185">Ask yourself</span></span>|<span data-ttu-id="62e29-186">操作</span><span class="sxs-lookup"><span data-stu-id="62e29-186">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="62e29-187">組織で通話キューは必要ですか?</span><span class="sxs-lookup"><span data-stu-id="62e29-187">Does my organization need call queues?</span></span> | <span data-ttu-id="62e29-188">詳細については、「[クラウドの通話キューを作成する](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)」および「[電話システムをセットアップする](setting-up-your-phone-system.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-188">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="62e29-189">自動応答</span><span class="sxs-lookup"><span data-stu-id="62e29-189">Auto attendants</span></span>

<span data-ttu-id="62e29-190">クラウド自動応答を使用して、組織のメニュー システムを作成できます。外部および内部の発信者はこのメニュー システムを介して組織内の企業ユーザーまたは部門を特定し、通話の発信および転送を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="62e29-190">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="62e29-191">確認事項</span><span class="sxs-lookup"><span data-stu-id="62e29-191">Ask yourself</span></span>|<span data-ttu-id="62e29-192">Action</span><span class="sxs-lookup"><span data-stu-id="62e29-192">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="62e29-193">組織で自動応答は必要ですか?</span><span class="sxs-lookup"><span data-stu-id="62e29-193">Does my organization need auto attendants?</span></span> | <span data-ttu-id="62e29-194">詳細については、「[クラウド自動応答とは](what-are-phone-system-auto-attendants.md)」および「[クラウドの自動応答をセットアップする](create-a-phone-system-auto-attendant.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-194">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="62e29-195">デバイス</span><span class="sxs-lookup"><span data-stu-id="62e29-195">Devices</span></span>

<span data-ttu-id="62e29-196">サポートされているデバイスの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e29-196">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="62e29-197">Microsoft Teams でのデバイスの管理</span><span class="sxs-lookup"><span data-stu-id="62e29-197">Manage your devices in Microsoft Teams</span></span>](devices/device-management.md)
- [<span data-ttu-id="62e29-198">IP 電話</span><span class="sxs-lookup"><span data-stu-id="62e29-198">IP Phones</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="62e29-199">USB オーディオ デバイスおよびビデオ デバイス</span><span class="sxs-lookup"><span data-stu-id="62e29-199">USB audio and video devices</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="62e29-200">デバイスのインテリジェント コミュニケーション</span><span class="sxs-lookup"><span data-stu-id="62e29-200">Intelligent communications for devices</span></span>](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


