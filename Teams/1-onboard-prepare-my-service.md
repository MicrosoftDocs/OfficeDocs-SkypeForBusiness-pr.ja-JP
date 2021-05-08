---
title: クラウド 音声サービスをデプロイする準備をする
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: オンボード チェックリストを使用して、Teams の Microsoft 365 または Office 365 を準備し、Teams コア機能、ネットワーク、クラウド音声ワークロードを構成します。
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
# <a name="prepare-my-service"></a><span data-ttu-id="3cc59-103">サービスを準備する</span><span class="sxs-lookup"><span data-stu-id="3cc59-103">Prepare my service</span></span>

<span data-ttu-id="3cc59-104">この記事では、組織のクラウド 音声サービスを準備するための要件の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="3cc59-105">適切に準備することで、組織にクラウド音声機能を提供する準備ができていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3cc59-105">By preparing properly, you can be sure you're ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="3cc59-106">音声ワークロードのMicrosoft Teamsチェックリスト</span><span class="sxs-lookup"><span data-stu-id="3cc59-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="3cc59-107">次のチェックリストでは、電話会議、電話システム と通話プラン ("通話プラン")、電話システム ダイレクト ルーティング ("ダイレクト ルーティング") 機能を Microsoft Teams で実装する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans ("Calling Plans"), and Phone System Direct Routing ("Direct Routing") capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="3cc59-108">準備Microsoft 365またはOffice 365準備Teams</span><span class="sxs-lookup"><span data-stu-id="3cc59-108">Prepare Microsoft 365 or Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="3cc59-109">コア機能Teams構成する</span><span class="sxs-lookup"><span data-stu-id="3cc59-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="3cc59-110">ネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="3cc59-110">Prepare your network</span></span>](prepare-network.md)

*  [<span data-ttu-id="3cc59-111">クラウド音声ワークロードを構成する Teams</span><span class="sxs-lookup"><span data-stu-id="3cc59-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  <span data-ttu-id="3cc59-112">[[ダイレクト ルーティングの構成] Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)</span><span class="sxs-lookup"><span data-stu-id="3cc59-112">[Configure Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)</span></span>

<span data-ttu-id="3cc59-113">これらのチェックリストのタスクとアクティビティは、クラウド音声機能の各デプロイに適用される主要な "To Do" Teams。</span><span class="sxs-lookup"><span data-stu-id="3cc59-113">The tasks and activities in these checklists are the core "to-do" items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="3cc59-114">チェックリストをカスタマイズして、独自のアクティビティ体験に固有のアクティビティやタスクTeamsできます。</span><span class="sxs-lookup"><span data-stu-id="3cc59-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="3cc59-115">このガイダンスでは、通話プラン、電話会議、ダイレクト ルーティングのみを中心に説明します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="3cc59-116">新しいアプリケーションを使用する場合Teamsの概要[に関するページMicrosoft Teams。](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3cc59-116">If you're new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="3cc59-117">デプロイの計画に関する一般的Teams、「チャット、[チーム](deploy-chat-teams-channels-microsoft-teams-landing-page.md)、チャネル、アプリをデプロイする」から始Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="3cc59-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="3cc59-118">提供されているチェックリストを使用して、個々のアクティビティとタスクの状態を追跡し、重要な手順をスキップしていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven't skipped any critical steps.</span></span> <span data-ttu-id="3cc59-119">各アクティビティには、必要なアクションの詳細な説明と、そのアクティビティを完了するために使用できる追加情報への参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3cc59-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="3cc59-120">チェックリストを順番に実行することをお勧めしますが、正確な順序は、デプロイの範囲と環境の構成と複雑さによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3cc59-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="3cc59-121">"greenfield" Teams デプロイ (以前の Skype for Business Online プレゼンスがないデプロイ) または Skype for Business Online から Teams への移行をサポートするために編成されています。</span><span class="sxs-lookup"><span data-stu-id="3cc59-121">They're organized to support either a "greenfield" Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="3cc59-122">Skype for Business Online から移行する場合は、これらのアクティビティの一部が既に完了している可能性があります。現在は無視できます。</span><span class="sxs-lookup"><span data-stu-id="3cc59-122">If you're migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="3cc59-123">サイトごとにユーザーをオンボードする場合は、これらのチェックリストの補足ガイドとして、Site [Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3cc59-123">When you're onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="3cc59-124">構成設定の多くが、Teams Online Skype for Businessです。</span><span class="sxs-lookup"><span data-stu-id="3cc59-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="3cc59-125">これらの設定を構成Microsoft 365管理センター Microsoft Teams管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="3cc59-126">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="3cc59-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="3cc59-127">Whoチェックリストの完了を監視する責任は何ですか?</span><span class="sxs-lookup"><span data-stu-id="3cc59-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="3cc59-128">次の手順</span><span class="sxs-lookup"><span data-stu-id="3cc59-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="3cc59-129">オンボード チェックリストをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3cc59-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="3cc59-130">組織の展開計画に従って、オンボーディング チェックリスト項目をステップ バイ ステップで実行します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-130">Work through the onboarding checklist items step-by-step in accordance with your organization's deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="3cc59-131">オンボードを続行する</span><span class="sxs-lookup"><span data-stu-id="3cc59-131">Continue onboarding</span></span>

<span data-ttu-id="3cc59-132">これらのチェックリストを完了すると、デプロイに音声機能が正常にTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="3cc59-132">After you complete these checklists, you'll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="3cc59-133">次の手順として、音声用のサイト有効化プレイブック [(プレイブック)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) を使用して、各サイトでユーザーをオンボードし、サイト固有の重要なアクティビティを計画して実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3cc59-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="3cc59-134">準備完了サイト(サイト別) ロールアウト 計画</span><span class="sxs-lookup"><span data-stu-id="3cc59-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="3cc59-135">サービス管理プロセスを確立する</span><span class="sxs-lookup"><span data-stu-id="3cc59-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="3cc59-136">テストと修復の実行</span><span class="sxs-lookup"><span data-stu-id="3cc59-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="3cc59-137">クラウド音声ワークロードをテスト Teamsする</span><span class="sxs-lookup"><span data-stu-id="3cc59-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="3cc59-138">Teams クラウド音声ビジネスの成功と技術実装計画を定義して文書化し、管理センターで必要な構成を実行したら、次の手順は、機能、機能、およびユーザビリティによって組織の期待と要件が満たされるのを検証します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-138">After you've defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization's expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="3cc59-139">この検証手順は、実稼働環境でパイロットまたは最終的なデプロイをデプロイする前に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cc59-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="3cc59-140">計画フェーズで定義したビジネス成功計画を活用して、テスト フェーズ中に評価されるアクティビティ、期待値、機能/機能テスト ケース、および全体的な範囲を決定するための基礎として機能することができます。</span><span class="sxs-lookup"><span data-stu-id="3cc59-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="3cc59-141">テストアプローチを定義する</span><span class="sxs-lookup"><span data-stu-id="3cc59-141">Define your testing approach</span></span>

<span data-ttu-id="3cc59-142">最も単純な形式では、テストアプローチは、電話会議、通話プラン、または直接ルーティング サービスの機能を確認し、スコープ内のユーザーに対して機能要件が満たされるのを確認するためのテスト計画の開発に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="3cc59-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="3cc59-143">電話会議実装のオンボード フェーズのテスト計画の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="3cc59-144">テストする電話会議機能</span><span class="sxs-lookup"><span data-stu-id="3cc59-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="3cc59-145">結果の概要</span><span class="sxs-lookup"><span data-stu-id="3cc59-145">Results summary</span></span> | <span data-ttu-id="3cc59-146">その他のメモ</span><span class="sxs-lookup"><span data-stu-id="3cc59-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="3cc59-147">電話会議のダイヤルTeamsを含む臨時の会議をスケジュールする</span><span class="sxs-lookup"><span data-stu-id="3cc59-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="3cc59-148">Pass/Fail</span><span class="sxs-lookup"><span data-stu-id="3cc59-148">Pass/Fail</span></span>   | <span data-ttu-id="3cc59-149">TBD</span><span class="sxs-lookup"><span data-stu-id="3cc59-149">TBD</span></span> |
| <span data-ttu-id="3cc59-150">PSTN からダイヤルイン情報が表示された会議にダイヤルインして音声会議に電話を使用する</span><span class="sxs-lookup"><span data-stu-id="3cc59-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="3cc59-151">Pass/Fail</span><span class="sxs-lookup"><span data-stu-id="3cc59-151">Pass/Fail</span></span> | <span data-ttu-id="3cc59-152">TBD</span><span class="sxs-lookup"><span data-stu-id="3cc59-152">TBD</span></span> |
| <span data-ttu-id="3cc59-153">PSTN 経由でダイヤルアウトして、他のユーザーを既存の会議に参加する</span><span class="sxs-lookup"><span data-stu-id="3cc59-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="3cc59-154">Pass/Fail</span><span class="sxs-lookup"><span data-stu-id="3cc59-154">Pass/Fail</span></span> | <span data-ttu-id="3cc59-155">TBD</span><span class="sxs-lookup"><span data-stu-id="3cc59-155">TBD</span></span> |



| <span data-ttu-id="3cc59-156">テストする通話プランまたはダイレクト ルーティング機能</span><span class="sxs-lookup"><span data-stu-id="3cc59-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="3cc59-157">結果の概要</span><span class="sxs-lookup"><span data-stu-id="3cc59-157">Results summary</span></span> | <span data-ttu-id="3cc59-158">その他のメモ</span><span class="sxs-lookup"><span data-stu-id="3cc59-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="3cc59-159">PSTN 番号をダイヤルして PSTN 通話を発信する</span><span class="sxs-lookup"><span data-stu-id="3cc59-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="3cc59-160">Pass/Fail</span><span class="sxs-lookup"><span data-stu-id="3cc59-160">Pass/Fail</span></span>       | <span data-ttu-id="3cc59-161">TBD</span><span class="sxs-lookup"><span data-stu-id="3cc59-161">TBD</span></span> |
| <span data-ttu-id="3cc59-162">PSTN 番号を外部回線 (携帯電話、固定電話) からダイヤルして PSTN 通話を受信する</span><span class="sxs-lookup"><span data-stu-id="3cc59-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="3cc59-163">Pass/Fail</span><span class="sxs-lookup"><span data-stu-id="3cc59-163">Pass/Fail</span></span> | <span data-ttu-id="3cc59-164">TBD</span><span class="sxs-lookup"><span data-stu-id="3cc59-164">TBD</span></span>|
| <span data-ttu-id="3cc59-165">PSTN 通話を別のユーザーにTeamsする</span><span class="sxs-lookup"><span data-stu-id="3cc59-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="3cc59-166">Pass/Fail</span><span class="sxs-lookup"><span data-stu-id="3cc59-166">Pass/Fail</span></span> | <span data-ttu-id="3cc59-167">TBD</span><span class="sxs-lookup"><span data-stu-id="3cc59-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="3cc59-168">テスト ケースの作成を開始点として支援するには、「会議と通話」で利用できるユーザー [Teamsを参照してください](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)。</span><span class="sxs-lookup"><span data-stu-id="3cc59-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="3cc59-169">クラウド音声ワークロードを設定する Teams</span><span class="sxs-lookup"><span data-stu-id="3cc59-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="3cc59-170">テストアプローチを定義したら、次の手順では、クラウド音声機能を使用するためのスコープ内のサービス環境Teams構成します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-170">Now that you've defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="3cc59-171">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cc59-171">For additional information, see:</span></span>

- [<span data-ttu-id="3cc59-172">音声会議での電話会議の計画  </span><span class="sxs-lookup"><span data-stu-id="3cc59-172">Technical Planning for Audio Conferencing</span></span>](./cloud-voice-landing-page.md)

- [<span data-ttu-id="3cc59-173">Microsoft Teams の電話会議を設定する</span><span class="sxs-lookup"><span data-stu-id="3cc59-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="3cc59-174">通話プランを使用電話システムの技術計画</span><span class="sxs-lookup"><span data-stu-id="3cc59-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="3cc59-175">通話プランをセットアップしてSkype for BusinessとMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="3cc59-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="3cc59-176">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="3cc59-176">Plan Direct Routing</span></span>](./direct-routing-plan.md)

- [<span data-ttu-id="3cc59-177">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="3cc59-177">Configure Direct Routing</span></span>](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a><span data-ttu-id="3cc59-178">テスト計画を実行する</span><span class="sxs-lookup"><span data-stu-id="3cc59-178">Execute the test plan</span></span>

[//]: # (編集は問題ありませんか?"ユーザー" は私には少しあいまいに思えました。)
<span data-ttu-id="3cc59-180">ユーザー環境とサービスが構成された後、テストの最後の手順には、機能と機能の検証に焦点を当てたテスト 計画の実行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3cc59-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="3cc59-181">**電話会議テストの前提条件と、スコープ内のユーザーとサイトの前提条件:**</span><span class="sxs-lookup"><span data-stu-id="3cc59-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="3cc59-182">電話会議サービスのビジネス の使用事例の定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="3cc59-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="3cc59-183">電話会議に必要なライセンスが利用可能であり、割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="3cc59-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="3cc59-184">組織サイトとユーザー グループの一覧が特定されました。</span><span class="sxs-lookup"><span data-stu-id="3cc59-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="3cc59-185">言語を優先する番号の専用および共有電話会議ダイヤルの一覧が識別され、構成されています。</span><span class="sxs-lookup"><span data-stu-id="3cc59-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="3cc59-186">[通信クレジット](what-are-communications-credits.md) (必要な場合) は、組織に対して設定されています。</span><span class="sxs-lookup"><span data-stu-id="3cc59-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="3cc59-187">電話会議会議ブリッジの設定が識別され、構成されています (PIN の長さ、開始/終了通知、有効化通知の設定)。</span><span class="sxs-lookup"><span data-stu-id="3cc59-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="3cc59-188">電話会議のダイヤルアウト シナリオをサポートするテナント会議ポリシーとダイヤル プランの設定は、識別、構成、適用されています。</span><span class="sxs-lookup"><span data-stu-id="3cc59-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="3cc59-189">電話会議のコンプライアンス要件が特定され、構成されています。</span><span class="sxs-lookup"><span data-stu-id="3cc59-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="3cc59-190">**スコープ内のユーザーとサイトの前提条件と前提条件をテストする通話プラン:**</span><span class="sxs-lookup"><span data-stu-id="3cc59-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="3cc59-191">通話プラン サービスのビジネス の使用事例の定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="3cc59-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="3cc59-192">通話プランに必要なライセンスが利用可能で、割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="3cc59-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="3cc59-193">組織サイトとユーザー グループの一覧が特定されました。</span><span class="sxs-lookup"><span data-stu-id="3cc59-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="3cc59-194">電話ユーザーに割り当てる番号が取得または Microsoft に移植され、テナント ポータルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cc59-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="3cc59-195">[通信クレジット](what-are-communications-credits.md) (必要な場合) は、組織に対して設定されています。</span><span class="sxs-lookup"><span data-stu-id="3cc59-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="3cc59-196">通話プランのシナリオをサポートするテナント ユーザー ポリシーとダイヤル プランの設定が識別され、構成され、適用されています。</span><span class="sxs-lookup"><span data-stu-id="3cc59-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="3cc59-197">通話プランのコンプライアンス要件が特定され、構成されています。</span><span class="sxs-lookup"><span data-stu-id="3cc59-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="3cc59-198">**ダイレクト ルーティング テストの前提条件と、スコープ内のユーザーとサイトの前提条件:**</span><span class="sxs-lookup"><span data-stu-id="3cc59-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="3cc59-199">ダイレクト ルーティング サービスのビジネス の使用事例の定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="3cc59-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="3cc59-200">直接ルーティングに必要なライセンスが利用可能であり、割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="3cc59-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="3cc59-201">組織サイトとユーザー グループの一覧が特定されました。</span><span class="sxs-lookup"><span data-stu-id="3cc59-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="3cc59-202">認定[セッション ボーダー コントローラー (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs)がデプロイされ、構成され、電話システム。</span><span class="sxs-lookup"><span data-stu-id="3cc59-202">A [certified session border controller (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="3cc59-203">Enterpriseが有効になっている場合、電話番号が割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="3cc59-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="3cc59-204">音声ルーティング ポリシーが識別され、構成され、割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="3cc59-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="3cc59-205">Microsoft Teams、スコープ内のユーザーの優先呼び出し元クライアントとして設定されています。</span><span class="sxs-lookup"><span data-stu-id="3cc59-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="3cc59-206">直接ルーティングのコンプライアンス要件が特定され、構成されています。</span><span class="sxs-lookup"><span data-stu-id="3cc59-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="3cc59-207">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="3cc59-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="3cc59-208">展開する電話会議機能を決定します (サービスの決定)。</span><span class="sxs-lookup"><span data-stu-id="3cc59-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="3cc59-209">電話会議のユーザー機能の要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="3cc59-210">電話会議のサービス構成要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="3cc59-211">直接ルーティングまたは通話プランをデプロイして構成するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="3cc59-212">デプロイする電話システム機能を決定します (サービスの決定)。</span><span class="sxs-lookup"><span data-stu-id="3cc59-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="3cc59-213">通話プランまたは直接ルーティングのユーザー機能要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="3cc59-214">通話プランまたは直接ルーティングのサービス構成要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="3cc59-215">次の手順</span><span class="sxs-lookup"><span data-stu-id="3cc59-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="3cc59-216">テスト計画のアプローチを開発して文書化します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="3cc59-217">電話会議機能のスコープ内でサービス環境とユーザーを準備します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="3cc59-218">通話プランまたは直接ルーティング機能のスコープでサービス環境とユーザーを準備します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="3cc59-219">有効にする電話会議機能のテスト検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="3cc59-220">有効にする通話プランまたは直接ルーティング機能のテスト検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="3cc59-221">テストエラーが発生した場合は、構成が正しいか確認し、コミュニティ記事を確認し、必要に応じてサポート ケースを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cc59-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="3cc59-222">Teams で電話会議のテストを実行する方法の詳細なガイダンスについては、電話会議の詳細なテスト ガイド[を参照してください](./deploy-audio-conferencing-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc59-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](./deploy-audio-conferencing-teams-landing-page.md).</span></span>

<span data-ttu-id="3cc59-223">Teams で通話プランのテストを実行する方法の詳細なガイダンスについては、電話システム の詳細なテスト[ガイドを参照してください](./cloud-voice-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc59-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](./cloud-voice-landing-page.md).</span></span>

<!--ENDOFSECTION-->