---
title: Microsoft Teams での Cloud Voice
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
description: チームでクラウドの音声を展開するためのランディング ・ ページ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 47c534eba93c6f5af21a75fa20b5015fac00c674
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198372"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="8b782-103">Microsoft Teams での Cloud Voice</span><span class="sxs-lookup"><span data-stu-id="8b782-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="8b782-104">[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。</span><span class="sxs-lookup"><span data-stu-id="8b782-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="8b782-105">Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。</span><span class="sxs-lookup"><span data-stu-id="8b782-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="8b782-106">かもしれません[& 会議の会議](deploy-meetings-microsoft-teams-landing-page.md)を導入しました。</span><span class="sxs-lookup"><span data-stu-id="8b782-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="8b782-107">ユーザーのクラウドの音声機能を追加する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="8b782-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="8b782-108">クラウドの音声は、プライベート構内交換機 (PBX) の機能が用意されています、、公衆交換電話網 (PSTN) を接続するためのオプションです。</span><span class="sxs-lookup"><span data-stu-id="8b782-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="8b782-109">この資料では、その手順を説明する各変更し、組織のプロファイルとビジネス要件に基づいて、既定のクラウド音声設定のいずれかを変更する必要があるかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="8b782-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="8b782-110">中核となる一連の[変更](#core-deployment-decisions)、2 つのグループの設定を分割しました。</span><span class="sxs-lookup"><span data-stu-id="8b782-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="8b782-111">2 番目のグループには、組織のニーズ応じた構成が求められる可能性がある[追加の設定](#additional-deployment-decisions)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8b782-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="8b782-112">すべての組織が主要な意思決定を進めるし、組織に追加の要件がある場合が、以下の内容を確認しをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8b782-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="8b782-113">クラウドの声の詳細を表示します</span><span class="sxs-lookup"><span data-stu-id="8b782-113">Learn more about cloud voice</span></span>

<span data-ttu-id="8b782-114">次の記事では、展開して、クラウドの音声機能を使用して、チームでの詳細についてを提供します。</span><span class="sxs-lookup"><span data-stu-id="8b782-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="8b782-115">Office 365 の電話システム</span><span class="sxs-lookup"><span data-stu-id="8b782-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="8b782-116">通話プランと電話システム</span><span class="sxs-lookup"><span data-stu-id="8b782-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="8b782-117">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="8b782-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="8b782-118">Cloud Voice の展開</span><span class="sxs-lookup"><span data-stu-id="8b782-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="8b782-119">Microsoft テレフォニー ソリューション</span><span class="sxs-lookup"><span data-stu-id="8b782-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="8b782-120">電話システムの詳細については、次のセッションを監視する:[マイクロソフトのチームでの電話システムの概要](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="8b782-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="8b782-121">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="8b782-121">Core deployment decisions</span></span>

<span data-ttu-id="8b782-122">次に示す設定は、ほとんどの組織が変更を必要とするものです (Teams の既定の設定では、組織に適した動作にならない場合)。</span><span class="sxs-lookup"><span data-stu-id="8b782-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="8b782-123">電話システム (Office 365)</span><span class="sxs-lookup"><span data-stu-id="8b782-123">Phone System (Office 365)</span></span>

<span data-ttu-id="8b782-124">電話システムは、通話の制御、Office 365 のクラウド内のプライベート構内交換機 (PBX) 機能を有効にする Microsoft のテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="8b782-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="8b782-125">電話システムを使用すると、Office 365 から直接配信し、企業のクラウドの生産性の経験と密接に統合の機能のセットを使用して、既存のプライベート構内交換機 (PBX) システムを置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="8b782-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company’s cloud productivity experience.</span></span>


|<span data-ttu-id="8b782-126">確認事項</span><span class="sxs-lookup"><span data-stu-id="8b782-126">Ask yourself</span></span>|<span data-ttu-id="8b782-127">アクション</span><span class="sxs-lookup"><span data-stu-id="8b782-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="8b782-128">電話システムはどのユーザーの所在地、またはオフィスで実装されますか。</span><span class="sxs-lookup"><span data-stu-id="8b782-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="8b782-129">電話システムの詳細については、 [Office 365 の電話システムと](what-is-phone-system-in-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="8b782-130">一般への接続は、電話網 (PSTN) を切り替える</span><span class="sxs-lookup"><span data-stu-id="8b782-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="8b782-131">世界中のユーザーが電話をかけることができますされるように、公衆交換電話網 (PSTN) 電話システムを接続するには、ビジネス ・ ニーズに基づいてのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8b782-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="8b782-132">以下を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-132">Ask yourself the following:</span></span>


|<span data-ttu-id="8b782-133">確認事項</span><span class="sxs-lookup"><span data-stu-id="8b782-133">Ask yourself</span></span>|<span data-ttu-id="8b782-134">アクション</span><span class="sxs-lookup"><span data-stu-id="8b782-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="8b782-135">[テレフォニーのキャリアとして Microsoft の計画を呼び出すを使用するか。</span><span class="sxs-lookup"><span data-stu-id="8b782-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="8b782-136">詳細については、[計画を呼び出すと、電話システム](calling-plan-landing-page.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="8b782-137">自分のテレフォニーのキャリアを使用する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="8b782-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="8b782-138">詳細については、[直接ルーティングの電話システム](direct-routing-landing-page.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="8b782-139">その他の展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="8b782-139">Additional deployment decisions</span></span>

<span data-ttu-id="8b782-140">、次の設定を変更することも、組織のニーズに基づいて構成します。</span><span class="sxs-lookup"><span data-stu-id="8b782-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="8b782-141">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="8b782-141">Voicemail</span></span>
- <span data-ttu-id="8b782-142">識別情報を呼び出す</span><span class="sxs-lookup"><span data-stu-id="8b782-142">Calling identity</span></span>
- <span data-ttu-id="8b782-143">マイクロソフトの電話番号</span><span class="sxs-lookup"><span data-stu-id="8b782-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="8b782-144">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="8b782-144">Dial plans</span></span>
- <span data-ttu-id="8b782-145">通話キュー</span><span class="sxs-lookup"><span data-stu-id="8b782-145">Call queues</span></span>
- <span data-ttu-id="8b782-146">自動応答</span><span class="sxs-lookup"><span data-stu-id="8b782-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="8b782-147">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="8b782-147">Voicemail</span></span>

<span data-ttu-id="8b782-148">電源は、Azure のボイスメール サービスが、クラウドのボイスメール ボイスメール出金のみの Exchange メールボックスをサポートしている、サード ・ パーティ製の電子メール システムをサポートしていません</span><span class="sxs-lookup"><span data-stu-id="8b782-148">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span> <span data-ttu-id="8b782-149">クラウドのボイス メールには、組織内のすべてのユーザーに対して既定で有効には、ボイスメールの議事録が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8b782-149">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="8b782-150">ビジネス ニーズは、特定のユーザーまたは組織全体のすべてのユーザーのボイスメールの議事録作成を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b782-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="8b782-151">確認事項</span><span class="sxs-lookup"><span data-stu-id="8b782-151">Ask yourself</span></span>|<span data-ttu-id="8b782-152">アクション</span><span class="sxs-lookup"><span data-stu-id="8b782-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="8b782-153">クラウドのボイスメールを有効にするか。</span><span class="sxs-lookup"><span data-stu-id="8b782-153">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="8b782-154">ボイスメールの設定手順は、「[クラウドのボイスメールを設定](set-up-phone-system-voicemail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-154">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="8b782-155">ボイスメールの議事録の一部またはすべてのユーザーを有効にするか。</span><span class="sxs-lookup"><span data-stu-id="8b782-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="8b782-156">ボイスメールの議事録作成を無効にするには、[組織内のボイス メール ポリシーの設定](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="8b782-157">識別情報を呼び出す</span><span class="sxs-lookup"><span data-stu-id="8b782-157">Calling identity</span></span>

<span data-ttu-id="8b782-158">既定では、すべての発信呼び出しは、呼び出し元の id (呼び出し元 ID) として割り当てられた電話番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b782-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="8b782-159">呼び出しの受信者は、呼び出し元を識別する迅速かつ呼び出しを承認または拒否かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8b782-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="8b782-160">確認事項</span><span class="sxs-lookup"><span data-stu-id="8b782-160">Ask yourself</span></span>|<span data-ttu-id="8b782-161">アクション</span><span class="sxs-lookup"><span data-stu-id="8b782-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="8b782-162">マスクしたり、発信者番号通知を無効にするか。</span><span class="sxs-lookup"><span data-stu-id="8b782-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="8b782-163">呼び出し元 ID のブロックを変更または、[ユーザーの発信者番号の設定](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-163">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="8b782-164">マイクロソフトの電話番号</span><span class="sxs-lookup"><span data-stu-id="8b782-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="8b782-165">マイクロソフトでは、2 種類の利用可能な電話番号:*サブスクライバー* (ユーザー) の番号は、組織内のユーザーに割り当てることができる、および*サービス*の番号、有料電話番号と無料サービスの番号より高い同時実行の呼び出しとして利用可能加入者番号よりも容量と、オーディオ会議、自動応答、またはキューの呼び出しなどのサービスに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8b782-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="8b782-166">確認事項</span><span class="sxs-lookup"><span data-stu-id="8b782-166">Ask yourself</span></span>|<span data-ttu-id="8b782-167">アクション</span><span class="sxs-lookup"><span data-stu-id="8b782-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="8b782-168">どのユーザーの場所には、マイクロソフトからの新しい電話番号が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="8b782-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="8b782-169">電話番号の取得方法の詳細については、[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)し[、ユーザーの電話番号の取得](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span></span> 
| <span data-ttu-id="8b782-170">電話番号 (サブスクライバーまたはサービス) の種類が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="8b782-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="8b782-171">必要がある電話番号の種類を選択するために、[さまざまな種類](different-kinds-of-phone-numbers-used-for-calling-plans.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="8b782-172">Office 365 を既存の電話番号をポートするには?</span><span class="sxs-lookup"><span data-stu-id="8b782-172">How do I port existing phone numbers to Office 365?</span></span>|<span data-ttu-id="8b782-173">詳細については、 [Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-173">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="8b782-174">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="8b782-174">Dial plans</span></span>

<span data-ttu-id="8b782-175">Office 365 の電話システムの機能で、ダイヤル プランは、承認と通話のルーティングの他の形式 (通常は E.164 形式) に電話番号をダイヤルに変換する正規化ルールのセットです。</span><span class="sxs-lookup"><span data-stu-id="8b782-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="8b782-176">ダイヤル プランの詳細については、「[ダイヤル プランについて](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="8b782-177">確認事項</span><span class="sxs-lookup"><span data-stu-id="8b782-177">Ask yourself</span></span>|<span data-ttu-id="8b782-178">アクション</span><span class="sxs-lookup"><span data-stu-id="8b782-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="8b782-179">組織はダイヤル プランのカスタマイズを必要としているか?</span><span class="sxs-lookup"><span data-stu-id="8b782-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="8b782-180">カスタムのダイヤル プランを使用する場合を判断するためには、[テナントを計画するダイヤル プラン](what-are-dial-plans.md#planning-for-tenant-dial-plans)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="8b782-181">どのユーザーがダイヤル プランのカスタマイズを要求していて、どのテナント ダイヤル プランを各ユーザーに割り当てる必要があるか?</span><span class="sxs-lookup"><span data-stu-id="8b782-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="8b782-182">PowerShell でカスタマイズされたダイヤル プランにユーザーを追加するを参照してください[を作成するダイヤル プランの管理と](create-and-manage-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="8b782-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="8b782-183">通話キュー</span><span class="sxs-lookup"><span data-stu-id="8b782-183">Call queues</span></span>

<span data-ttu-id="8b782-184">クラウド呼び出しキューには、自動的に保留中の呼び出しを配置することなどを検索する機能の呼び出しとなっている人の中に呼び出しを処理するために次の呼び出しを使用可能なエージェントのための電話番号への呼び出し際に使用するあいさつ文が含まれます保留中の音楽を聴きます。</span><span class="sxs-lookup"><span data-stu-id="8b782-184">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="8b782-185">組織の 1 つまたは複数の呼び出しキューを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b782-185">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="8b782-186">確認事項</span><span class="sxs-lookup"><span data-stu-id="8b782-186">Ask yourself</span></span>|<span data-ttu-id="8b782-187">アクション</span><span class="sxs-lookup"><span data-stu-id="8b782-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="8b782-188">自分の所属組織はキューを呼び出して必要がありますでしょうか。</span><span class="sxs-lookup"><span data-stu-id="8b782-188">Does my organization need call queues?</span></span> | <span data-ttu-id="8b782-189">詳細については、[クラウドの呼び出しキューを作成](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)し[、電話システムの設定](setting-up-your-phone-system.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-189">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="8b782-190">自動応答</span><span class="sxs-lookup"><span data-stu-id="8b782-190">Auto attendants</span></span>

<span data-ttu-id="8b782-191">外部では、組織のメニュー システムを作成するのにはクラウドの自動応答を使用することができ、内部の呼び出し元を探し、配置、ユーザーの会社または組織内の部門への呼び出しを転送する] メニューの [システムを通過します。</span><span class="sxs-lookup"><span data-stu-id="8b782-191">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="8b782-192">確認事項</span><span class="sxs-lookup"><span data-stu-id="8b782-192">Ask yourself</span></span>|<span data-ttu-id="8b782-193">アクション</span><span class="sxs-lookup"><span data-stu-id="8b782-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="8b782-194">自分の所属組織は自動応答を必要ですか。</span><span class="sxs-lookup"><span data-stu-id="8b782-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="8b782-195">詳細については、[自動応答をクラウド](what-are-phone-system-auto-attendants.md)とは[クラウドの自動応答の設定](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-195">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span> |

### <a name="devices"></a><span data-ttu-id="8b782-196">デバイス</span><span class="sxs-lookup"><span data-stu-id="8b782-196">Devices</span></span>

<span data-ttu-id="8b782-197">サポートされているデバイスの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b782-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="8b782-198">Microsoft Teams でのデバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="8b782-198">Manage your devices in Microsoft Teams</span></span>](device-management.md)
- [<span data-ttu-id="8b782-199">IP 電話</span><span class="sxs-lookup"><span data-stu-id="8b782-199">IP Phones</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="8b782-200">USB オーディオ デバイスおよびビデオ デバイス</span><span class="sxs-lookup"><span data-stu-id="8b782-200">USB audio and video devices</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="8b782-201">デバイスのインテリジェント通信</span><span class="sxs-lookup"><span data-stu-id="8b782-201">Intelligent communications for devices</span></span>](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


