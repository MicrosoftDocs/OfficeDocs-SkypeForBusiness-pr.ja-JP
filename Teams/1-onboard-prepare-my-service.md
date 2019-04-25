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
description: 契約時のチェックリストを使用して、Office 365 をチームに準備し、チームの中心的な機能、ネットワークを構成し、音声のワークロードをクラウドします。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 886fb0d851112fbb76ca20aeb6b4c1b35e736757
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241371"
---
# <a name="prepare-my-service"></a><span data-ttu-id="c2f24-103">サービスを準備する</span><span class="sxs-lookup"><span data-stu-id="c2f24-103">Prepare my service</span></span>

<span data-ttu-id="c2f24-104">この資料では、音声サービスを組織のクラウドを準備するための要件の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="c2f24-105">適切に準備するように、クラウドの組織にボイス機能を提供する準備ができていることのことができます。</span><span class="sxs-lookup"><span data-stu-id="c2f24-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="c2f24-106">音声のワークロードをマイクロソフトのチームの契約時のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="c2f24-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="c2f24-107">次のチェックリストでは、マイクロソフトのチームでオーディオ会議、電話システム ("呼び出しプラン])、計画を呼び出すと、電話システム直接ルーティング (「直接ルーティング") 機能を実装するため手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="c2f24-108">Office 365 のチームを準備します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="c2f24-109">チームの中核的な機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="c2f24-110">ネットワークを構成します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-110">Configure networking</span></span>](onboarding-checklist-configure-networking.md)

*  [<span data-ttu-id="c2f24-111">チームで音声のワークロードをクラウドを構成します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="c2f24-112">チームに直接ルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="c2f24-113">タスクとこれらのチェックリストでの作業は、チームと音声機能をクラウドのそれぞれの配置に適用されるコアの"to do"アイテムです。</span><span class="sxs-lookup"><span data-stu-id="c2f24-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="c2f24-114">活動と自分のチームの旅に特有のタスクを含むようにチェックリストをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c2f24-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="c2f24-115">このガイドでは、計画を呼び出して、オーディオ会議、および直接ルーティングだけに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="c2f24-116">チームに新しい場合は、[マイクロソフトのチームの概要](teams-overview.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="c2f24-117">チーム展開を計画するための一般的なガイダンスは、[展開のチャット、チーム、チャネル、およびマイクロソフトのチームでのアプリケーション](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を起動します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="c2f24-118">個々 のアクティビティとタスクのステータスを追跡するために提供されているチェックリストを使用しの重要な手順をスキップしていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="c2f24-119">各アクティビティには、必要なアクションとそのアクティビティを完了するのに使用できるその他の情報への参照の詳細な説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="c2f24-120">順序のチェックリストを実行することをお勧めですが、展開と構成のスコープと環境の複雑さの厳密な順序によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c2f24-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="c2f24-121">いずれか、"greenfield"をサポートするために整理されています、チームの配置 (ビジネス オンライン プレゼンスのない以前の Skype で 1 つ) または Skype からチームへのビジネスをオンラインに移行します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="c2f24-122">ビジネス オンラインの Skype から移行する場合がすでに完了しているこれらの活動の一部と、それらをここで無視することができます。</span><span class="sxs-lookup"><span data-stu-id="c2f24-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="c2f24-123">サイトごとに契約時のユーザーが表示されたら、以下のチェックリストの補足ガイドとしては、[サイトの有効化の戦略 (戦略) の音声](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="c2f24-124">ほとんどの構成設定は、チームと Skype のオンライン ビジネスの間で共通です。</span><span class="sxs-lookup"><span data-stu-id="c2f24-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="c2f24-125">これらの設定を構成するのには、Office 365 管理者センターとマイクロソフトのチーム管理センターを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="c2f24-125">You use the Office 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="c2f24-126">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="c2f24-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="c2f24-127">契約時チェックリストの完了を監督する責任者がされますか。</span><span class="sxs-lookup"><span data-stu-id="c2f24-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="c2f24-128">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c2f24-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="c2f24-129">契約時のチェックリストをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="c2f24-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="c2f24-130">契約時チェックリストの項目の手順に従って、組織の展開計画を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="c2f24-131">契約時を継続します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-131">Continue onboarding</span></span>

<span data-ttu-id="c2f24-132">これらのチェックリストを完了すると、正常にようになりましたねボイス機能、チームの配置にします。</span><span class="sxs-lookup"><span data-stu-id="c2f24-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="c2f24-133">次の手順では、 [(戦略) の音声をサイトの有効化の戦略](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用してユーザーを支援するオンボードの各サイトと計画し、重要なサイト固有のアクティビティを実行することを防止します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="c2f24-134">準備ができてサイトごとの展開計画</span><span class="sxs-lookup"><span data-stu-id="c2f24-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="c2f24-135">サービス管理プロセスを確立します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="c2f24-136">テストを実行し、改善策</span><span class="sxs-lookup"><span data-stu-id="c2f24-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="c2f24-137">チームでクラウド音声の作業負荷をテスト</span><span class="sxs-lookup"><span data-stu-id="c2f24-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="c2f24-138">定義し Envision フェーズの一部として、チームのクラウド音声ビジネスの成功と技術的な実装計画を文書化して管理センターで必要な構成を行う、次の手順がいることを確認するのには、組織の機能、機能、および利便性を期待し、要件が満たされています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="c2f24-139">運用環境でパイロットや最後の展開を展開する前に、この検証の手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2f24-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="c2f24-140">テスト段階で評価されるように活動、期待される、機能のテストの場合、および全体的な範囲を決定する基準として使用する Envision フェーズで定義したビジネスの成功プランを利用できます。</span><span class="sxs-lookup"><span data-stu-id="c2f24-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="c2f24-141">テスト アプローチを定義します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-141">Define your testing approach</span></span>

<span data-ttu-id="c2f24-142">最も単純な形式で、テスト アプローチが、計画を呼び出すには、オーディオ会議の機能を確認する、に基づいてまたはスコープ内のユーザーの機能要件が満たされていることを確認するのには直接ルーティング サービスとテストの開発を計画します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="c2f24-143">オンボード オーディオ会議実装のフェーズでの例をテスト計画を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="c2f24-144">オーディオ会議の機能をテストするには</span><span class="sxs-lookup"><span data-stu-id="c2f24-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="c2f24-145">結果の概要</span><span class="sxs-lookup"><span data-stu-id="c2f24-145">Results summary</span></span> | <span data-ttu-id="c2f24-146">追加の注記</span><span class="sxs-lookup"><span data-stu-id="c2f24-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="c2f24-147">オーディオ会議ダイヤルイン情報を含む特別なチームの会議のスケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="c2f24-148">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="c2f24-148">Pass/Fail</span></span>   | <span data-ttu-id="c2f24-149">TBD</span><span class="sxs-lookup"><span data-stu-id="c2f24-149">TBD</span></span> |
| <span data-ttu-id="c2f24-150">電話を使用して、提供されているダイヤルイン情報を使用して、PSTN から会議にダイヤルインしてミーティング オーディオの</span><span class="sxs-lookup"><span data-stu-id="c2f24-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="c2f24-151">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="c2f24-151">Pass/Fail</span></span> | <span data-ttu-id="c2f24-152">TBD</span><span class="sxs-lookup"><span data-stu-id="c2f24-152">TBD</span></span> |
| <span data-ttu-id="c2f24-153">PSTN を使用してダイヤルアウトで他のユーザーを既存の会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="c2f24-154">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="c2f24-154">Pass/Fail</span></span> | <span data-ttu-id="c2f24-155">TBD</span><span class="sxs-lookup"><span data-stu-id="c2f24-155">TBD</span></span> |



| <span data-ttu-id="c2f24-156">通話プランまたは直接ルーティング機能をテストするのには</span><span class="sxs-lookup"><span data-stu-id="c2f24-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="c2f24-157">結果の概要</span><span class="sxs-lookup"><span data-stu-id="c2f24-157">Results summary</span></span> | <span data-ttu-id="c2f24-158">追加の注記</span><span class="sxs-lookup"><span data-stu-id="c2f24-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="c2f24-159">PSTN 番号をダイヤルすることによって、PSTN の呼び出しを行う</span><span class="sxs-lookup"><span data-stu-id="c2f24-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="c2f24-160">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="c2f24-160">Pass/Fail</span></span>       | <span data-ttu-id="c2f24-161">TBD</span><span class="sxs-lookup"><span data-stu-id="c2f24-161">TBD</span></span> |
| <span data-ttu-id="c2f24-162">外部の行 (モバイル、地上線) から、PSTN の番号をダイヤルすることによって、PSTN の呼び出しを受信します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="c2f24-163">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="c2f24-163">Pass/Fail</span></span> | <span data-ttu-id="c2f24-164">TBD</span><span class="sxs-lookup"><span data-stu-id="c2f24-164">TBD</span></span>|
| <span data-ttu-id="c2f24-165">PSTN の呼び出しを別のチームの 1 つのユーザーに転送します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="c2f24-166">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="c2f24-166">Pass/Fail</span></span> | <span data-ttu-id="c2f24-167">TBD</span><span class="sxs-lookup"><span data-stu-id="c2f24-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="c2f24-168">開始点として、テスト_ケースの作成を支援するには、[チームの会議や通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)で使用可能なユーザー ・ ガイドの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2f24-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="c2f24-169">チームの音声のワークロードをクラウドを設定します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="c2f24-170">テスト方法を定義した、次の手順、構成、サービスの環境とユーザー チーム クラウドの音声機能のスコープ内です。</span><span class="sxs-lookup"><span data-stu-id="c2f24-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="c2f24-171">詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2f24-171">For additional information, see:</span></span>

- [<span data-ttu-id="c2f24-172">音声会議での電話会議の計画  </span><span class="sxs-lookup"><span data-stu-id="c2f24-172">Technical Planning for Audio Conferencing</span></span>](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [<span data-ttu-id="c2f24-173">Microsoft Teams の電話会議を設定する</span><span class="sxs-lookup"><span data-stu-id="c2f24-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="c2f24-174">通話プランと電話システムの計画技術</span><span class="sxs-lookup"><span data-stu-id="c2f24-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="c2f24-175">設定計画を呼び出す Skype のビジネスおよびマイクロソフトのチーム</span><span class="sxs-lookup"><span data-stu-id="c2f24-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="c2f24-176">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="c2f24-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="c2f24-177">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="c2f24-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="c2f24-178">テスト計画を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-178">Execute the test plan</span></span>

[//]: # (Ok で編集しますか。「ユーザー」は、自分に少しあいまいな思えました。)
<span data-ttu-id="c2f24-180">ユーザー環境とサービスを構成すると、テストの最後の手順には、機能と機能の検証でのフォーカスのあるテスト計画の実行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="c2f24-181">**電話会議のスコープ内のユーザーとサイトの前提条件をテストします。**</span><span class="sxs-lookup"><span data-stu-id="c2f24-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="c2f24-182">ビジネスは、オーディオ会議サービスが完了したケースの定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="c2f24-183">オーディオ会議に必要なライセンス、割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="c2f24-184">組織のサイトとユーザー グループの一覧を指定しています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="c2f24-185">言語の優先順位の番号にダイヤルを専用または共有の電話会議の一覧を特定して構成します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="c2f24-186">[通信のクレジット](what-are-communications-credits.md)(必要な場合)、組織用に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="c2f24-187">オーディオ会議会議ブリッジの設定がされている識別し、(暗証番号 (pin) の長さ、開始/終了の通知、通知の基本設定を有効化) を構成します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="c2f24-188">テナント会議ポリシーとダイヤル プラン設定の識別、構成、および適用されるアウト ダイヤル シナリオの音声会議をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c2f24-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="c2f24-189">オーディオ会議のコンプライアンス要件を特定して構成します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="c2f24-190">**通話プランがスコープ内のユーザーとサイトの前提条件をテストします。**</span><span class="sxs-lookup"><span data-stu-id="c2f24-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="c2f24-191">ビジネス、呼び出す計画サービスが完了したケースの定義で使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="c2f24-192">計画を呼び出すために必要なライセンス、割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="c2f24-193">組織のサイトとユーザー グループの一覧を指定しています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="c2f24-194">ユーザーに割り当てられる電話番号を取得またはマイクロソフトとテナント ポータルで利用するように移植されました。</span><span class="sxs-lookup"><span data-stu-id="c2f24-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="c2f24-195">[通信のクレジット](what-are-communications-credits.md)(必要な場合)、組織用に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="c2f24-196">テナント ユーザー ポリシーとダイヤル プランの設定を呼び出すことを計画のシナリオをサポートする識別、構成、および適用。</span><span class="sxs-lookup"><span data-stu-id="c2f24-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="c2f24-197">コンプライアンス要件を特定して構成の計画を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="c2f24-198">**直接ルーティングがスコープ内のユーザーとサイトの前提条件をテストします。**</span><span class="sxs-lookup"><span data-stu-id="c2f24-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="c2f24-199">ビジネスでは、直接ルーティング サービスが完了したケースの定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="c2f24-200">直接ルーティングのために必要なライセンス、割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="c2f24-201">組織のサイトとユーザー グループの一覧を指定しています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="c2f24-202">[セッション ボーダー コント ローラー (SBC) の認定](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)を導入が構成され、電話システムとペアにします。</span><span class="sxs-lookup"><span data-stu-id="c2f24-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="c2f24-203">エンタープライズ ボイスが有効になっていると電話番号が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="c2f24-204">音声ルーティング ポリシーの識別、構成、および割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="c2f24-205">マイクロソフト チームは、スコープ内のユーザーの優先する呼び出し元クライアントとして設定されています。</span><span class="sxs-lookup"><span data-stu-id="c2f24-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="c2f24-206">直接ルーティングのコンプライアンス要件を特定して構成します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="c2f24-207">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="c2f24-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="c2f24-208">どの電話会議機能を展開するかを決定 (サービスの決定)。</span><span class="sxs-lookup"><span data-stu-id="c2f24-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="c2f24-209">オーディオ会議のユーザーの機能要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="c2f24-210">オーディオ会議サービスの構成要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="c2f24-211">かどうか直接ルーティングまたはプランを呼び出すことができる展開し、構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="c2f24-212">どの電話システムの機能を配置するかを決定 (サービスの決定)。</span><span class="sxs-lookup"><span data-stu-id="c2f24-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="c2f24-213">計画を呼び出すか、直接ルーティングのユーザーの機能要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="c2f24-214">計画を呼び出すことや、直接ルーティング サービスの構成要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="c2f24-215">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c2f24-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="c2f24-216">開発し、テスト計画のアプローチを文書化します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="c2f24-217">電話会議機能のスコープ内のユーザー、サービスの環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="c2f24-218">計画を呼び出すか、直接ルーティング機能のスコープ内のユーザー、サービスの環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="c2f24-219">電話会議機能を有効にするためのテストの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="c2f24-220">計画を呼び出すか、直接ルーティング機能を有効にするためのテストの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2f24-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="c2f24-221">いずれかの障害をテスト、構成が正しいことを確認、コミュニティの記事を確認し、-必要な場合-サポート ・ リクエストを発生させます。</span><span class="sxs-lookup"><span data-stu-id="c2f24-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="c2f24-222">チームでのオーディオ会議のためのテストを実行する方法の詳細なガイダンスが追加は、[オーディオ会議のためのガイドをテストする詳細](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2f24-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="c2f24-223">チームの計画を呼び出すことでテストを実行する方法に関する追加の詳細については、[電話システムのガイドをテストする詳細](onboarding-test-plan-for-enterprises-Phone-System.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2f24-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
