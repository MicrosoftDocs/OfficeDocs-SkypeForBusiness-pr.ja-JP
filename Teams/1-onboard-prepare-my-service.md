---
title: クラウド 音声サービスの展開を準備する
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: オンボーディング チェックリストを使用して、Microsoft 365 または Office 365 for Teams を準備し、Teams のコア機能、ネットワーク、クラウド 音声ワークロードを構成します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 42ded974ba5f4400bdcb5796410a8277fbed4488
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103973"
---
# <a name="prepare-my-service"></a><span data-ttu-id="47186-103">サービスを準備する</span><span class="sxs-lookup"><span data-stu-id="47186-103">Prepare my service</span></span>

<span data-ttu-id="47186-104">この記事では、組織のクラウド 音声サービスを準備するための要件の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="47186-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="47186-105">適切に準備することで、組織にクラウド音声機能を提供する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="47186-105">By preparing properly, you can be sure you're ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="47186-106">Microsoft Teams 音声ワークロードのオンボーディング チェックリスト</span><span class="sxs-lookup"><span data-stu-id="47186-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="47186-107">次のチェックリストでは、Microsoft Teams の電話会議、通話プランを含む電話システム ("通話プラン")、電話システムダイレクト ルーティング ("ダイレクト ルーティング") 機能を実装する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="47186-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans ("Calling Plans"), and Phone System Direct Routing ("Direct Routing") capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="47186-108">Microsoft 365 または Office 365 for Teams を準備する</span><span class="sxs-lookup"><span data-stu-id="47186-108">Prepare Microsoft 365 or Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="47186-109">Teams のコア機能を構成する</span><span class="sxs-lookup"><span data-stu-id="47186-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="47186-110">ネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="47186-110">Prepare your network</span></span>](prepare-network.md)

*  [<span data-ttu-id="47186-111">Teams でクラウド音声ワークロードを構成する</span><span class="sxs-lookup"><span data-stu-id="47186-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="47186-112">Teams で直接ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="47186-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="47186-113">これらのチェックリストのタスクとアクティビティは、Teams でのクラウド音声機能のすべての展開に適用される主要な "To Do" アイテムです。</span><span class="sxs-lookup"><span data-stu-id="47186-113">The tasks and activities in these checklists are the core "to-do" items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="47186-114">自分の Teams の旅に固有のアクティビティやタスクを含めるチェックリストをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="47186-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="47186-115">このガイダンスでは、通話プラン、電話会議、ダイレクト ルーティングのみを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="47186-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="47186-116">Teams を使用する場合は、Microsoft Teams [の概要を確認します](teams-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="47186-116">If you're new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="47186-117">Teams の展開を計画する一般的なガイダンスについては、Microsoft Teams でのチャット、チーム、チャネル、アプリの展開 [から開始します](deploy-chat-teams-channels-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="47186-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="47186-118">提供されたチェックリストを使用して、個々のアクティビティとタスクの状態を追跡し、重要な手順をスキップしていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="47186-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven't skipped any critical steps.</span></span> <span data-ttu-id="47186-119">各アクティビティには、必要なアクションの詳細な説明と、そのアクティビティを完了するために使用できる追加情報への参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="47186-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="47186-120">チェックリストを順番に実行することをお勧めしますが、正確な順序は展開の範囲と環境の構成と複雑さによって異なります。</span><span class="sxs-lookup"><span data-stu-id="47186-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="47186-121">これらのチームは、"greenfield" Teams の展開 (以前の Skype for Business Online プレゼンスがない展開) または Skype for Business Online から Teams への移行のいずれかをサポートするために編成されています。</span><span class="sxs-lookup"><span data-stu-id="47186-121">They're organized to support either a "greenfield" Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="47186-122">Skype for Business Online から移行する場合は、これらのアクティビティの一部を既に完了している可能性があります。この時点では無視できます。</span><span class="sxs-lookup"><span data-stu-id="47186-122">If you're migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="47186-123">サイトごとにユーザーのオンボーディングを行う場合は、これらのチェックリストの補足ガイドとして、音声用サイト有効化プレイブック [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="47186-123">When you're onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="47186-124">構成設定の大部分は、Teams と Skype for Business Online の間で一般的です。</span><span class="sxs-lookup"><span data-stu-id="47186-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="47186-125">これらの設定を構成するには、Microsoft 365 管理センターと Microsoft Teams 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="47186-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="47186-126">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="47186-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="47186-127">オンボーディング チェックリストの完了を監督する責任は誰ですか?</span><span class="sxs-lookup"><span data-stu-id="47186-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="47186-128">次の手順</span><span class="sxs-lookup"><span data-stu-id="47186-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="47186-129">オンボーディング チェックリストをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="47186-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="47186-130">組織の展開計画に従って、オンボーディング チェックリスト項目をステップ バイ ステップで実行します。</span><span class="sxs-lookup"><span data-stu-id="47186-130">Work through the onboarding checklist items step-by-step in accordance with your organization's deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="47186-131">オンボーディングを続行する</span><span class="sxs-lookup"><span data-stu-id="47186-131">Continue onboarding</span></span>

<span data-ttu-id="47186-132">これらのチェックリストを完了すると、Teams の展開に音声機能が正常に追加されます。</span><span class="sxs-lookup"><span data-stu-id="47186-132">After you complete these checklists, you'll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="47186-133">次の手順として、音声用サイト有効化プレイブック [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) を使用して、各サイトでユーザーをオンボードし、サイト固有の重要なアクティビティを計画して実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="47186-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="47186-134">サイト別の準備が整ったサイトの展開計画</span><span class="sxs-lookup"><span data-stu-id="47186-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="47186-135">サービス管理プロセスを確立する</span><span class="sxs-lookup"><span data-stu-id="47186-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="47186-136">テストと修復を実行する</span><span class="sxs-lookup"><span data-stu-id="47186-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="47186-137">Teams でクラウド音声ワークロードをテストする</span><span class="sxs-lookup"><span data-stu-id="47186-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="47186-138">Teams クラウド 音声ビジネスの成功計画と技術実装計画をビジョンフェーズの一環として定義し、管理センターで必要な構成を実行したら、次の手順は、機能、機能、ユーザビリティを通じて組織の期待と要件が満たされる検証です。</span><span class="sxs-lookup"><span data-stu-id="47186-138">After you've defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization's expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="47186-139">実稼働環境にパイロットまたは最終的な展開を展開する前に、この検証手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47186-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="47186-140">ビジョン フェーズで定義したビジネスの成功計画を活用して、テスト フェーズ中に評価されるアクティビティ、期待値、機能/機能テスト ケース、全体的な範囲を決定するベースとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="47186-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="47186-141">テストのアプローチを定義する</span><span class="sxs-lookup"><span data-stu-id="47186-141">Define your testing approach</span></span>

<span data-ttu-id="47186-142">最も簡単な形式では、テストのアプローチは、電話会議、通話プラン、またはダイレクト ルーティング サービスの機能を確認し、範囲内のユーザーに対して機能要件が満たされるのを確認するためのテスト計画の開発に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="47186-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="47186-143">電話会議の実装のオンボード フェーズのテスト計画の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="47186-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="47186-144">テストする電話会議機能</span><span class="sxs-lookup"><span data-stu-id="47186-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="47186-145">結果の概要</span><span class="sxs-lookup"><span data-stu-id="47186-145">Results summary</span></span> | <span data-ttu-id="47186-146">その他のメモ</span><span class="sxs-lookup"><span data-stu-id="47186-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="47186-147">電話会議のダイヤルイン情報を含む臨時の Teams 会議をスケジュールする</span><span class="sxs-lookup"><span data-stu-id="47186-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="47186-148">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="47186-148">Pass/Fail</span></span>   | <span data-ttu-id="47186-149">TBD</span><span class="sxs-lookup"><span data-stu-id="47186-149">TBD</span></span> |
| <span data-ttu-id="47186-150">PSTN からダイヤルイン情報を含む会議にダイヤルインして音声会議に電話を使う</span><span class="sxs-lookup"><span data-stu-id="47186-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="47186-151">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="47186-151">Pass/Fail</span></span> | <span data-ttu-id="47186-152">TBD</span><span class="sxs-lookup"><span data-stu-id="47186-152">TBD</span></span> |
| <span data-ttu-id="47186-153">PSTN 経由でダイヤルアウトして既存の会議に他のユーザーを参加する</span><span class="sxs-lookup"><span data-stu-id="47186-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="47186-154">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="47186-154">Pass/Fail</span></span> | <span data-ttu-id="47186-155">TBD</span><span class="sxs-lookup"><span data-stu-id="47186-155">TBD</span></span> |



| <span data-ttu-id="47186-156">通話プランまたは直接ルーティング機能をテストする</span><span class="sxs-lookup"><span data-stu-id="47186-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="47186-157">結果の概要</span><span class="sxs-lookup"><span data-stu-id="47186-157">Results summary</span></span> | <span data-ttu-id="47186-158">その他のメモ</span><span class="sxs-lookup"><span data-stu-id="47186-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="47186-159">PSTN 番号をダイヤルして PSTN 通話を発信する</span><span class="sxs-lookup"><span data-stu-id="47186-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="47186-160">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="47186-160">Pass/Fail</span></span>       | <span data-ttu-id="47186-161">TBD</span><span class="sxs-lookup"><span data-stu-id="47186-161">TBD</span></span> |
| <span data-ttu-id="47186-162">PSTN 番号を外部回線 (携帯電話、固定電話) からダイヤルして PSTN 通話を受信する</span><span class="sxs-lookup"><span data-stu-id="47186-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="47186-163">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="47186-163">Pass/Fail</span></span> | <span data-ttu-id="47186-164">TBD</span><span class="sxs-lookup"><span data-stu-id="47186-164">TBD</span></span>|
| <span data-ttu-id="47186-165">Teams ユーザー間で PSTN 通話を転送する</span><span class="sxs-lookup"><span data-stu-id="47186-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="47186-166">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="47186-166">Pass/Fail</span></span> | <span data-ttu-id="47186-167">TBD</span><span class="sxs-lookup"><span data-stu-id="47186-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="47186-168">テスト ケースの作成を開始点として支援するには、Teams 会議と通話で利用できるユーザー ガイダンス [の一覧を参照してください](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)。</span><span class="sxs-lookup"><span data-stu-id="47186-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="47186-169">Teams のクラウド音声ワークロードをセットアップする</span><span class="sxs-lookup"><span data-stu-id="47186-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="47186-170">テストのアプローチを定義したら、次の手順は、Teams クラウド音声機能の範囲内でサービス環境とユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="47186-170">Now that you've defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="47186-171">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47186-171">For additional information, see:</span></span>

- [<span data-ttu-id="47186-172">音声会議での電話会議の計画  </span><span class="sxs-lookup"><span data-stu-id="47186-172">Technical Planning for Audio Conferencing</span></span>](./cloud-voice-landing-page.md)

- [<span data-ttu-id="47186-173">Microsoft Teams の電話会議を設定する</span><span class="sxs-lookup"><span data-stu-id="47186-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="47186-174">通話プランを使用した電話システムの技術計画</span><span class="sxs-lookup"><span data-stu-id="47186-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="47186-175">Skype for Business および Microsoft Teams の通話プランをセットアップする</span><span class="sxs-lookup"><span data-stu-id="47186-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="47186-176">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="47186-176">Plan Direct Routing</span></span>](./direct-routing-plan.md)

- [<span data-ttu-id="47186-177">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="47186-177">Configure Direct Routing</span></span>](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a><span data-ttu-id="47186-178">テスト計画を実行する</span><span class="sxs-lookup"><span data-stu-id="47186-178">Execute the test plan</span></span>

[//]: # (編集は問題ありませんか?"ユーザー" は私には少しあいまいに見えました。)
<span data-ttu-id="47186-180">ユーザー環境とサービスを構成した後、テストの最後の手順には、機能と機能の検証に焦点を当てたテスト 計画の実行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="47186-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="47186-181">**電話会議のテストの前提条件と、スコープ内のユーザーとサイトの想定:**</span><span class="sxs-lookup"><span data-stu-id="47186-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="47186-182">電話会議サービスのビジネス 用の使用例の定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="47186-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="47186-183">電話会議に必要なライセンスが利用可能で、割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="47186-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="47186-184">組織サイトとユーザー グループの一覧が識別されました。</span><span class="sxs-lookup"><span data-stu-id="47186-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="47186-185">言語設定を使用して、専用および共有の電話会議ダイヤルの番号の一覧が識別され、構成されています。</span><span class="sxs-lookup"><span data-stu-id="47186-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="47186-186">[組織に](what-are-communications-credits.md) 通信クレジット (必要な場合) が設定されています。</span><span class="sxs-lookup"><span data-stu-id="47186-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="47186-187">電話会議会議ブリッジの設定が識別され、構成されています (PIN の長さ、入退出通知、有効化通知の基本設定)。</span><span class="sxs-lookup"><span data-stu-id="47186-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="47186-188">電話会議のダイヤルアウト シナリオをサポートするテナント会議ポリシーとダイヤル プランの設定は、識別、構成、適用されています。</span><span class="sxs-lookup"><span data-stu-id="47186-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="47186-189">電話会議のコンプライアンス要件が特定され、構成されています。</span><span class="sxs-lookup"><span data-stu-id="47186-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="47186-190">**対象となるユーザーとサイトの前提条件と前提条件をテストする通話プラン:**</span><span class="sxs-lookup"><span data-stu-id="47186-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="47186-191">通話プラン サービスのビジネス 用の使用例の定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="47186-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="47186-192">通話プランに必要なライセンスが利用可能で、割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="47186-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="47186-193">組織サイトとユーザー グループの一覧が識別されました。</span><span class="sxs-lookup"><span data-stu-id="47186-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="47186-194">ユーザーに割り当てられる電話番号は、取得または Microsoft に移植され、テナント ポータルで利用できます。</span><span class="sxs-lookup"><span data-stu-id="47186-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="47186-195">[組織に](what-are-communications-credits.md) 通信クレジット (必要な場合) が設定されています。</span><span class="sxs-lookup"><span data-stu-id="47186-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="47186-196">通話プランのシナリオをサポートするテナント ユーザー ポリシーとダイヤル プランの設定は、識別、構成、適用されています。</span><span class="sxs-lookup"><span data-stu-id="47186-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="47186-197">通話プランのコンプライアンス要件が特定され、構成されています。</span><span class="sxs-lookup"><span data-stu-id="47186-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="47186-198">**スコープ内のユーザーとサイトのダイレクト ルーティング テストの前提条件と想定:**</span><span class="sxs-lookup"><span data-stu-id="47186-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="47186-199">ダイレクト ルーティング サービスのビジネス 用の使用例の定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="47186-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="47186-200">直接ルーティングに必要なライセンスが利用可能で、割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="47186-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="47186-201">組織サイトとユーザー グループの一覧が識別されました。</span><span class="sxs-lookup"><span data-stu-id="47186-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="47186-202">認定 [されたセッション ボーダー コントローラー (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) が電話システムと展開、構成、ペアリングされています。</span><span class="sxs-lookup"><span data-stu-id="47186-202">A [certified session border controller (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="47186-203">エンタープライズ ボイスが有効になっているので、電話番号が割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="47186-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="47186-204">音声ルーティング ポリシーは、識別、構成、割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="47186-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="47186-205">Microsoft Teams は、範囲内のユーザーの優先呼び出しクライアントとして設定されています。</span><span class="sxs-lookup"><span data-stu-id="47186-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="47186-206">ダイレクト ルーティングのコンプライアンス要件が特定され、構成されています。</span><span class="sxs-lookup"><span data-stu-id="47186-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="47186-207">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="47186-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="47186-208">展開する電話会議機能を決定する (サービス決定)。</span><span class="sxs-lookup"><span data-stu-id="47186-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="47186-209">電話会議のユーザー機能要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="47186-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="47186-210">電話会議のサービス構成要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="47186-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="47186-211">ダイレクト ルーティングと通話プランの配置と構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="47186-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="47186-212">展開する電話システム機能を決定する (サービス決定)。</span><span class="sxs-lookup"><span data-stu-id="47186-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="47186-213">通話プランまたはダイレクト ルーティングのユーザー機能要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="47186-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="47186-214">通話プランまたはダイレクト ルーティングのサービス構成要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="47186-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="47186-215">次の手順</span><span class="sxs-lookup"><span data-stu-id="47186-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="47186-216">テスト計画のアプローチを開発して文書化します。</span><span class="sxs-lookup"><span data-stu-id="47186-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="47186-217">電話会議機能の範囲でサービス環境とユーザーを準備します。</span><span class="sxs-lookup"><span data-stu-id="47186-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="47186-218">通話プランまたはダイレクト ルーティング機能の範囲でサービス環境とユーザーを準備します。</span><span class="sxs-lookup"><span data-stu-id="47186-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="47186-219">有効にする電話会議機能のテスト検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="47186-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="47186-220">有効にする通話プランまたはダイレクト ルーティング機能のテスト検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="47186-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="47186-221">テストの失敗がある場合は、構成が正しいか確認し、コミュニティの記事を確認し、必要に応じてサポート ケースを上げてください。</span><span class="sxs-lookup"><span data-stu-id="47186-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="47186-222">Teams で電話会議のテストを実行する方法の詳細なガイダンスについては、電話会議の詳細なテスト [ガイドを参照してください](./deploy-audio-conferencing-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="47186-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](./deploy-audio-conferencing-teams-landing-page.md).</span></span>

<span data-ttu-id="47186-223">Teams で通話プランのテストを実行する方法の詳細なガイダンスについては、電話システムの詳細なテスト [ガイドを参照してください](./cloud-voice-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="47186-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](./cloud-voice-landing-page.md).</span></span>

<!--ENDOFSECTION-->