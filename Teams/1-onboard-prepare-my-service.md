---
title: Microsoft Teams クラウド ボイス サービスの展開を準備する
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: オンボードのチェックリストを使用して、チーム用に Office 365 を準備し、Teams のコア機能、ネットワーク、およびクラウド音声のワークロードを構成します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27a3555443ecf1988a49c6002477e8ec2cb4680e
ms.sourcegitcommit: ca7a22da082ac5336f31ffd76f3d4aef6c76285b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "33868689"
---
# <a name="prepare-my-service"></a><span data-ttu-id="48345-103">サービスを準備する</span><span class="sxs-lookup"><span data-stu-id="48345-103">Prepare my service</span></span>

<span data-ttu-id="48345-104">この記事では、組織のクラウド音声サービスを準備するための要件の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="48345-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="48345-105">適切に準備しておくと、クラウドの音声機能を組織に提供する準備ができているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="48345-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="48345-106">Microsoft Teams の音声ワークロードのオンボードチェックリスト</span><span class="sxs-lookup"><span data-stu-id="48345-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="48345-107">次のチェックリストは、Microsoft Teams の電話会議、電話システム (以下、「通話プラン」)、電話システムダイレクトルーティング (以下、「直接ルーティング」) 機能を実装するための手順を説明しています。</span><span class="sxs-lookup"><span data-stu-id="48345-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="48345-108">Teams 用の Office 365 を準備する</span><span class="sxs-lookup"><span data-stu-id="48345-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="48345-109">Teams のコア機能を構成する</span><span class="sxs-lookup"><span data-stu-id="48345-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="48345-110">ネットワークを構成する</span><span class="sxs-lookup"><span data-stu-id="48345-110">Configure networking</span></span>](onboarding-checklist-configure-networking.md)

*  [<span data-ttu-id="48345-111">Teams でクラウド音声のワークロードを構成する</span><span class="sxs-lookup"><span data-stu-id="48345-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="48345-112">Teams で直接ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="48345-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="48345-113">これらのチェックリストのタスクとアクティビティは、チームとのクラウド音声機能のすべての展開に適用される "to do" のコア項目です。</span><span class="sxs-lookup"><span data-stu-id="48345-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="48345-114">このチェックリストをカスタマイズして、自分のチームの旅に固有のアクティビティとタスクを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="48345-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="48345-115">このガイダンスは、通話プラン、電話会議、直接ルーティングにのみ焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="48345-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="48345-116">チームを初めてお使いになる場合は、 [「Microsoft teams の概要」](teams-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48345-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="48345-117">チーム展開の計画に関する一般的なガイダンスについては、「 [Microsoft teams でのチャット、チーム、チャネル、アプリの展開](deploy-chat-teams-channels-microsoft-teams-landing-page.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="48345-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="48345-118">該当するチェックリストを使用して、個々のアクティビティとタスクの状態を追跡し、クリティカルステップをスキップしていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="48345-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="48345-119">各アクティビティには、必要なアクションの詳細な説明と、そのアクティビティを完了するために使用できる追加情報への参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="48345-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="48345-120">チェックリストは順番に従うことをお勧めしますが、正確な順序は展開の範囲と環境の構成と複雑さによって異なります。</span><span class="sxs-lookup"><span data-stu-id="48345-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="48345-121">これらのユーザーは、"から始め" Teams の展開 (以前の Skype for Business Online プレゼンスがないもの) または Skype for Business Online から Teams への移行のいずれかをサポートするように開催されています。</span><span class="sxs-lookup"><span data-stu-id="48345-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="48345-122">Skype for Business Online から移行している場合は、これらのアクティビティの一部を既に完了している可能性があります。これを無視することができます。</span><span class="sxs-lookup"><span data-stu-id="48345-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="48345-123">サイトベースでユーザーをオンにしている場合は、これらのチェックリストのガイドとして、[サイトの有効化のためのプレイリスト (プレイリスト)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="48345-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="48345-124">ほとんどの構成設定は、Teams と Skype for Business Online で共通です。</span><span class="sxs-lookup"><span data-stu-id="48345-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="48345-125">これらの設定を構成するには、Microsoft 365 管理センターと Microsoft Teams 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="48345-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="48345-126">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="48345-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="48345-127">オンボードチェックリストの完了を監督する担当者を教えてください。</span><span class="sxs-lookup"><span data-stu-id="48345-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="48345-128">次のステップ</span><span class="sxs-lookup"><span data-stu-id="48345-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="48345-129">オンボードチェックリストをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="48345-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="48345-130">組織の展開計画に従って、オンボードのチェックリスト項目を段階的に操作します。</span><span class="sxs-lookup"><span data-stu-id="48345-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="48345-131">オンボードを続行する</span><span class="sxs-lookup"><span data-stu-id="48345-131">Continue onboarding</span></span>

<span data-ttu-id="48345-132">これらのチェックリストを完了すると、音声機能がチーム展開に正常に追加されます。</span><span class="sxs-lookup"><span data-stu-id="48345-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="48345-133">次の手順として、お客様が各サイトでの使用を計画し、サイト固有の重要なアクティビティを計画して実行できるように、[音声 (プレイブック) 向けのサイト支援プレイブック](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用します。</span><span class="sxs-lookup"><span data-stu-id="48345-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="48345-134">サイトロールアウトプランごとの準備が完了しました</span><span class="sxs-lookup"><span data-stu-id="48345-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="48345-135">サービス管理プロセスを確立する</span><span class="sxs-lookup"><span data-stu-id="48345-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="48345-136">テストと修復を実行する</span><span class="sxs-lookup"><span data-stu-id="48345-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="48345-137">Teams でクラウドの音声ワークロードをテストする</span><span class="sxs-lookup"><span data-stu-id="48345-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="48345-138">チームクラウドの音声ビジネスの成功と技術の実装計画を定義して、管理センターで必要な構成を実施したら、次の手順として、組織のことを確認します。期待と要件は、機能、機能、ユーザビリティによって満たされます。</span><span class="sxs-lookup"><span data-stu-id="48345-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="48345-139">パイロットまたは最終的な展開を運用環境に展開する前に、この検証手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48345-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="48345-140">ビジョン化フェーズで定義したビジネス成功計画を活用して、アクティビティ、期待、機能/機能テストケース、およびテストフェーズで評価される全体的な範囲を決定するための基礎として使用できます。</span><span class="sxs-lookup"><span data-stu-id="48345-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="48345-141">テスト方法を定義する</span><span class="sxs-lookup"><span data-stu-id="48345-141">Define your testing approach</span></span>

<span data-ttu-id="48345-142">最も簡単な方法として、テスト方法は、電話会議、通話プラン、または直接ルーティングサービスの機能を確認して、範囲内のユーザーに対して機能要件が満たされていることを確認するためのテスト計画を策定することに基づいています。</span><span class="sxs-lookup"><span data-stu-id="48345-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="48345-143">以下は、電話会議の実装のオンボードフェーズのテスト計画の例です。</span><span class="sxs-lookup"><span data-stu-id="48345-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="48345-144">テストする電話会議機能</span><span class="sxs-lookup"><span data-stu-id="48345-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="48345-145">結果の概要</span><span class="sxs-lookup"><span data-stu-id="48345-145">Results summary</span></span> | <span data-ttu-id="48345-146">追加のメモ</span><span class="sxs-lookup"><span data-stu-id="48345-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="48345-147">電話会議のダイヤルイン情報が含まれる臨時の Teams 会議のスケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="48345-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="48345-148">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="48345-148">Pass/Fail</span></span>   | <span data-ttu-id="48345-149">TBD</span><span class="sxs-lookup"><span data-stu-id="48345-149">TBD</span></span> |
| <span data-ttu-id="48345-150">音声会議に電話を使用するには、対応する PSTN からの会議にダイヤルイン情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="48345-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="48345-151">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="48345-151">Pass/Fail</span></span> | <span data-ttu-id="48345-152">TBD</span><span class="sxs-lookup"><span data-stu-id="48345-152">TBD</span></span> |
| <span data-ttu-id="48345-153">PSTN 経由でダイヤルアウトして、他のユーザーを既存の会議に参加する</span><span class="sxs-lookup"><span data-stu-id="48345-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="48345-154">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="48345-154">Pass/Fail</span></span> | <span data-ttu-id="48345-155">TBD</span><span class="sxs-lookup"><span data-stu-id="48345-155">TBD</span></span> |



| <span data-ttu-id="48345-156">テストのための通話プランまたはダイレクトルーティング機能</span><span class="sxs-lookup"><span data-stu-id="48345-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="48345-157">結果の概要</span><span class="sxs-lookup"><span data-stu-id="48345-157">Results summary</span></span> | <span data-ttu-id="48345-158">追加のメモ</span><span class="sxs-lookup"><span data-stu-id="48345-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="48345-159">PSTN 番号にダイヤルして PSTN 通話を行う</span><span class="sxs-lookup"><span data-stu-id="48345-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="48345-160">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="48345-160">Pass/Fail</span></span>       | <span data-ttu-id="48345-161">TBD</span><span class="sxs-lookup"><span data-stu-id="48345-161">TBD</span></span> |
| <span data-ttu-id="48345-162">外部の回線 (携帯電話、固定電話) から PSTN 番号をダイヤルして、PSTN 通話を受信します。</span><span class="sxs-lookup"><span data-stu-id="48345-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="48345-163">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="48345-163">Pass/Fail</span></span> | <span data-ttu-id="48345-164">TBD</span><span class="sxs-lookup"><span data-stu-id="48345-164">TBD</span></span>|
| <span data-ttu-id="48345-165">1つの Teams ユーザーから別のユーザーに PSTN 通話を転送する</span><span class="sxs-lookup"><span data-stu-id="48345-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="48345-166">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="48345-166">Pass/Fail</span></span> | <span data-ttu-id="48345-167">TBD</span><span class="sxs-lookup"><span data-stu-id="48345-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="48345-168">開始点としてテストケースの作成を支援するには、 [Teams の会議と通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)で利用できるユーザーガイダンスの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48345-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="48345-169">Teams でクラウド音声のワークロードを設定する</span><span class="sxs-lookup"><span data-stu-id="48345-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="48345-170">テスト方法の定義が完了したら、次の手順では、Teams クラウドボイス機能のスコープ内のサービス環境とユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="48345-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="48345-171">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48345-171">For additional information, see:</span></span>

- [<span data-ttu-id="48345-172">音声会議での電話会議の計画  </span><span class="sxs-lookup"><span data-stu-id="48345-172">Technical Planning for Audio Conferencing</span></span>](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [<span data-ttu-id="48345-173">Microsoft Teams の電話会議を設定する</span><span class="sxs-lookup"><span data-stu-id="48345-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="48345-174">通話プランを使用した電話システムの技術計画</span><span class="sxs-lookup"><span data-stu-id="48345-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="48345-175">Skype for Business および Microsoft Teams の通話プランを設定する</span><span class="sxs-lookup"><span data-stu-id="48345-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="48345-176">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="48345-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="48345-177">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="48345-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="48345-178">テスト計画を実行する</span><span class="sxs-lookup"><span data-stu-id="48345-178">Execute the test plan</span></span>

[//]: # (編集しますか?"ユーザー" は、自分にとって少々あいまいなものに思われます。)
<span data-ttu-id="48345-180">ユーザー環境とサービスを構成した後、テストの最後のステップには、機能と機能の検証にフォーカスがあるテスト計画の実行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="48345-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="48345-181">**電話会議は、スコープ内のユーザーとサイトに関する前提条件と前提条件をテストします。**</span><span class="sxs-lookup"><span data-stu-id="48345-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="48345-182">電話会議サービスのビジネスユースケースの定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="48345-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="48345-183">電話会議に必要なライセンスはあり、割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="48345-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="48345-184">組織のサイトとユーザーグループの一覧が確認されました。</span><span class="sxs-lookup"><span data-stu-id="48345-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="48345-185">専用の電話会議のダイヤルインの一覧と言語の優先順位が設定されています。</span><span class="sxs-lookup"><span data-stu-id="48345-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="48345-186">[通信クレジット](what-are-communications-credits.md)(必要な場合) 組織用に設定されています。</span><span class="sxs-lookup"><span data-stu-id="48345-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="48345-187">電話会議のブリッジの設定が識別され構成されている (PIN の長さ、エントリ/終了の通知、有効化通知の設定)。</span><span class="sxs-lookup"><span data-stu-id="48345-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="48345-188">電話会議のダイヤルアウトシナリオをサポートするテナント会議のポリシーとダイヤルプランの設定が、特定、構成、適用されている。</span><span class="sxs-lookup"><span data-stu-id="48345-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="48345-189">電話会議のコンプライアンス要件を特定して構成しました。</span><span class="sxs-lookup"><span data-stu-id="48345-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="48345-190">**通話プラン: スコープ内のユーザーとサイトの前提条件と前提条件をテストします。**</span><span class="sxs-lookup"><span data-stu-id="48345-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="48345-191">通話プランサービスのビジネスユースケースの定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="48345-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="48345-192">通話プランのライセンスが必要であり、割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="48345-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="48345-193">組織のサイトとユーザーグループの一覧が確認されました。</span><span class="sxs-lookup"><span data-stu-id="48345-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="48345-194">ユーザーに割り当てられる電話番号は、Microsoft に取得または移植されたため、テナントポータルで利用できます。</span><span class="sxs-lookup"><span data-stu-id="48345-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="48345-195">[通信クレジット](what-are-communications-credits.md)(必要な場合) 組織用に設定されています。</span><span class="sxs-lookup"><span data-stu-id="48345-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="48345-196">通話プランのシナリオをサポートしているテナントのユーザーポリシーとダイヤルプランの設定が、特定、構成、適用されている。</span><span class="sxs-lookup"><span data-stu-id="48345-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="48345-197">通話プランのコンプライアンス要件は、確認および構成されています。</span><span class="sxs-lookup"><span data-stu-id="48345-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="48345-198">**スコープ内のユーザーとサイトに対する直接ルーティングテストの前提条件と前提条件:**</span><span class="sxs-lookup"><span data-stu-id="48345-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="48345-199">ダイレクトルーティングサービスのビジネスユースケースの定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="48345-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="48345-200">直接ルーティングのために必要なライセンスは利用可能であり、割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="48345-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="48345-201">組織のサイトとユーザーグループの一覧が確認されました。</span><span class="sxs-lookup"><span data-stu-id="48345-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="48345-202">[認定セッションボーダーコントローラー (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)は、電話システムとの組み合わせ、構成、およびペアリングされています。</span><span class="sxs-lookup"><span data-stu-id="48345-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="48345-203">エンタープライズボイスが有効になり、電話番号が割り当てられました。</span><span class="sxs-lookup"><span data-stu-id="48345-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="48345-204">音声ルーティングポリシーは、識別、構成、割り当てされています。</span><span class="sxs-lookup"><span data-stu-id="48345-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="48345-205">Microsoft Teams は、範囲内のユーザーの優先発信クライアントとして設定されています。</span><span class="sxs-lookup"><span data-stu-id="48345-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="48345-206">直接ルーティングのコンプライアンス要件が識別され、構成されている。</span><span class="sxs-lookup"><span data-stu-id="48345-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="48345-207">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="48345-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="48345-208">どの電話会議機能を展開するかを決定します (サービス決定)。</span><span class="sxs-lookup"><span data-stu-id="48345-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="48345-209">電話会議のユーザー機能要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="48345-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="48345-210">電話会議のサービス構成要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="48345-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="48345-211">ダイレクトルーティングまたは通話プランを展開して構成するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="48345-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="48345-212">どの電話システム機能が展開されるかを決定します (サービス決定)。</span><span class="sxs-lookup"><span data-stu-id="48345-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="48345-213">プランまたはダイレクトルーティングのためのユーザー機能要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="48345-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="48345-214">プランまたはダイレクトルーティングのサービス構成要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="48345-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="48345-215">次のステップ</span><span class="sxs-lookup"><span data-stu-id="48345-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="48345-216">テスト計画のアプローチを開発し、文書化します。</span><span class="sxs-lookup"><span data-stu-id="48345-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="48345-217">電話会議機能のスコープでサービス環境とユーザーを準備します。</span><span class="sxs-lookup"><span data-stu-id="48345-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="48345-218">プランまたはダイレクトルーティング機能の対象となるように、サービス環境とユーザーを準備します。</span><span class="sxs-lookup"><span data-stu-id="48345-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="48345-219">有効にする電話会議機能のテストの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="48345-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="48345-220">有効にする通話プランまたはダイレクトルーティング機能に対してテストの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="48345-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="48345-221">テストの失敗については、構成が正しいことを確認し、コミュニティの記事を確認し、必要に応じてサポート案件を提起します。</span><span class="sxs-lookup"><span data-stu-id="48345-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="48345-222">Teams で電話会議のテストを実行する方法の詳細については、「[電話会議の詳細なテストガイド](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48345-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="48345-223">Teams での通話プランのテストを実行する方法の詳細については、「[電話システムの詳細なテストガイド](onboarding-test-plan-for-enterprises-Phone-System.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48345-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
