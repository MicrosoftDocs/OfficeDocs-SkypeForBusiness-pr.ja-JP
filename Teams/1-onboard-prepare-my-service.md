---
title: マイクロソフト チーム クラウドのインターネット電話サービスを展開するための準備します。
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 契約時のチェックリストを使用して、Office 365 をチームに準備し、チームの中心的な機能、ネットワークを構成し、音声のワークロードをクラウドします。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1e4b6e690450b8ec81209a0244769444ee2d30d
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2018
---
# <a name="prepare-my-service"></a><span data-ttu-id="34645-103">サービスを準備します。</span><span class="sxs-lookup"><span data-stu-id="34645-103">Prepare my service</span></span>

<span data-ttu-id="34645-104">この資料では、音声サービスを組織のクラウドを準備するための要件の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="34645-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="34645-105">適切に準備するように、クラウドの組織にボイス機能を提供する準備ができていることのことができます。</span><span class="sxs-lookup"><span data-stu-id="34645-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="34645-106">音声のワークロードをマイクロソフトのチームの契約時のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="34645-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="34645-107">次のチェックリストでは、マイクロソフトのチームでの計画を呼び出す機能を備えたオーディオ会議や電話システムを実装するための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="34645-107">The following checklists walk you through the steps for implementing Audio Conferencing and Phone System with Calling Plans capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="34645-108">Office 365 のチームを準備します。</span><span class="sxs-lookup"><span data-stu-id="34645-108">Prepare Office 365 for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365)

*  [<span data-ttu-id="34645-109">チームの中核的な機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="34645-109">Configure Teams core capabilities</span></span>](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities)

*  [<span data-ttu-id="34645-110">ネットワークを構成します。</span><span class="sxs-lookup"><span data-stu-id="34645-110">Configure networking</span></span>](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)

*  [<span data-ttu-id="34645-111">チームで音声のワークロードをクラウドを構成します。</span><span class="sxs-lookup"><span data-stu-id="34645-111">Configure cloud voice workloads in Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams)

<span data-ttu-id="34645-112">タスクとこれらのチェックリストでの作業は、チームと音声機能をクラウドのそれぞれの配置に適用されるコアの"to do"アイテムです。</span><span class="sxs-lookup"><span data-stu-id="34645-112">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="34645-113">活動と自分のチームの旅に特有のタスクを含むようにチェックリストをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="34645-113">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="34645-114">このガイドでは、計画を呼び出すと電話会議の電話システムにのみ焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="34645-114">This guidance focuses solely on Phone System with Calling Plans and Audio Conferencing.</span></span> <span data-ttu-id="34645-115">チームに新しい場合は、[マイクロソフトのチームの概要](https://docs.microsoft.com/MicrosoftTeams/teams-overview)を確認します。</span><span class="sxs-lookup"><span data-stu-id="34645-115">If you’re new to Teams, review [Overview of Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span></span> <span data-ttu-id="34645-116">チーム展開を計画するための一般的なガイダンスは、 [Microsoft のチームの計画ガイド 』](https://docs.microsoft.com/MicrosoftTeams/quick-start-enable-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34645-116">For general guidance for planning your Teams deployment, see the [Microsoft Teams Planning Guide](https://docs.microsoft.com/MicrosoftTeams/quick-start-enable-teams).</span></span>

<span data-ttu-id="34645-117">個々 のアクティビティとタスクのステータスを追跡するために提供されているチェックリストを使用しの重要な手順をスキップしていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="34645-117">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="34645-118">各アクティビティには、必要なアクションとそのアクティビティを完了するのに使用できるその他の情報への参照の詳細な説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="34645-118">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="34645-119">順序のチェックリストを実行することをお勧めですが、展開と構成のスコープと環境の複雑さの厳密な順序によって異なります。</span><span class="sxs-lookup"><span data-stu-id="34645-119">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="34645-120">いずれか、"greenfield"をサポートするために整理されています、チームの配置 (ビジネス オンライン プレゼンスのない以前の Skype で 1 つ) または Skype からチームへのビジネスをオンラインに移行します。</span><span class="sxs-lookup"><span data-stu-id="34645-120">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="34645-121">ビジネス オンラインの Skype から移行する場合がすでに完了しているこれらの活動の一部と、それらをここで無視することができます。</span><span class="sxs-lookup"><span data-stu-id="34645-121">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="34645-122">サイトごとに契約時のユーザーが表示されたら、以下のチェックリストの補足ガイドとしては、[サイトの有効化の戦略 (戦略) の音声](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="34645-122">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="34645-123">ほとんどの構成設定は、チームと Skype のオンライン ビジネスの間で共通です。</span><span class="sxs-lookup"><span data-stu-id="34645-123">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="34645-124">これらの設定を構成するのにには、ビジネス管理センターの Office 365 の Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="34645-124">You use Office 365 Skype for Business Administration Center to configure those settings.</span></span>

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="34645-125">意思決定ポイント</span><span class="sxs-lookup"><span data-stu-id="34645-125">Decision points</span></span></td><td><ul><li><span data-ttu-id="34645-126">契約時チェックリストの完了を監督する責任者がされますか。</span><span class="sxs-lookup"><span data-stu-id="34645-126">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="34645-127">次のステップ</span><span class="sxs-lookup"><span data-stu-id="34645-127">Next steps</span></span></td><td><ul><li><span data-ttu-id="34645-128">契約時のチェックリストをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="34645-128">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="34645-129">契約時チェックリストの項目の手順に従って、組織の展開計画を使用します。</span><span class="sxs-lookup"><span data-stu-id="34645-129">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="34645-130">契約時を継続します。</span><span class="sxs-lookup"><span data-stu-id="34645-130">Continue onboarding</span></span>

<span data-ttu-id="34645-131">このチェックリストを完了すると、正常にようになりましたねボイス機能、チームの配置にします。</span><span class="sxs-lookup"><span data-stu-id="34645-131">After you complete this checklist, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="34645-132">次の手順では、 [(戦略) の音声をサイトの有効化の戦略](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用してユーザーを支援するオンボードの各サイトと計画し、重要なサイト固有のアクティビティを実行することを防止します。</span><span class="sxs-lookup"><span data-stu-id="34645-132">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="34645-133">準備ができてサイトごとの展開計画</span><span class="sxs-lookup"><span data-stu-id="34645-133">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="34645-134">サービス管理プロセスを確立します。</span><span class="sxs-lookup"><span data-stu-id="34645-134">Establish Service Management Process</span></span>

-   <span data-ttu-id="34645-135">テストを実行し、改善策</span><span class="sxs-lookup"><span data-stu-id="34645-135">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="34645-136">チームでクラウド音声の作業負荷をテスト</span><span class="sxs-lookup"><span data-stu-id="34645-136">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="34645-137">定義し Envision フェーズの一部として、チームのクラウド音声ビジネスの成功と技術的な実装計画を文書化して管理センターで必要な構成を行う、次の手順がいることを確認するのには、組織の機能、機能、および利便性を期待し、要件が満たされています。</span><span class="sxs-lookup"><span data-stu-id="34645-137">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="34645-138">運用環境でパイロットや最後の展開を展開する前に、この検証の手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="34645-138">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="34645-139">テスト段階で評価されるように活動、期待される、機能のテストの場合、および全体的な範囲を決定する基準として使用する Envision フェーズで定義したビジネスの成功プランを利用できます。</span><span class="sxs-lookup"><span data-stu-id="34645-139">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="34645-140">テスト アプローチを定義します。</span><span class="sxs-lookup"><span data-stu-id="34645-140">Define your testing approach</span></span>

<span data-ttu-id="34645-141">最も単純な形式では、テスト アプローチは、レビューの範囲内のユーザーのサービスの計画を呼び出すと、機能要件のことを確認するテスト計画を開発、オーディオ会議や電話システムの機能が満たされるに基づいています。</span><span class="sxs-lookup"><span data-stu-id="34645-141">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing or Phone System with Calling Plans service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="34645-142">オンボード オーディオ会議実装のフェーズでの例をテスト計画を次に示します。</span><span class="sxs-lookup"><span data-stu-id="34645-142">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>

| <span data-ttu-id="34645-143">オーディオ会議の機能をテストするには</span><span class="sxs-lookup"><span data-stu-id="34645-143">Audio Conferencing feature to test</span></span> | <span data-ttu-id="34645-144">結果の概要</span><span class="sxs-lookup"><span data-stu-id="34645-144">Results summary</span></span> | <span data-ttu-id="34645-145">追加の注記</span><span class="sxs-lookup"><span data-stu-id="34645-145">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="34645-146">オーディオ会議ダイヤルイン情報を含む特別なチームの会議のスケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="34645-146">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="34645-147">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="34645-147">Pass/Fail</span></span>   | <span data-ttu-id="34645-148">未定</span><span class="sxs-lookup"><span data-stu-id="34645-148">TBD</span></span> |
| <span data-ttu-id="34645-149">電話を使用して、提供されているダイヤルイン情報を使用して、PSTN から会議にダイヤルインしてミーティング オーディオの</span><span class="sxs-lookup"><span data-stu-id="34645-149">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="34645-150">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="34645-150">Pass/Fail</span></span> | <span data-ttu-id="34645-151">未定</span><span class="sxs-lookup"><span data-stu-id="34645-151">TBD</span></span> |
| <span data-ttu-id="34645-152">PSTN を使用してダイヤルアウトで他のユーザーを既存の会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="34645-152">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="34645-153">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="34645-153">Pass/Fail</span></span> | <span data-ttu-id="34645-154">未定</span><span class="sxs-lookup"><span data-stu-id="34645-154">TBD</span></span> |


| <span data-ttu-id="34645-155">計画を呼び出す機能をテストする電話システム</span><span class="sxs-lookup"><span data-stu-id="34645-155">Phone System with Calling Plans feature to test</span></span> | <span data-ttu-id="34645-156">結果の概要</span><span class="sxs-lookup"><span data-stu-id="34645-156">Results summary</span></span> | <span data-ttu-id="34645-157">追加の注記</span><span class="sxs-lookup"><span data-stu-id="34645-157">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="34645-158">PSTN 番号をダイヤルすることによって、PSTN の呼び出しを行う</span><span class="sxs-lookup"><span data-stu-id="34645-158">Make a PSTN call to by dialing a PSTN number</span></span>       | <span data-ttu-id="34645-159">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="34645-159">Pass/Fail</span></span>       | <span data-ttu-id="34645-160">未定</span><span class="sxs-lookup"><span data-stu-id="34645-160">TBD</span></span> |
| <span data-ttu-id="34645-161">外部の行 (モバイル、地上線) から、PSTN の番号をダイヤルすることによって、PSTN の呼び出しを受信します。</span><span class="sxs-lookup"><span data-stu-id="34645-161">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="34645-162">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="34645-162">Pass/Fail</span></span> | <span data-ttu-id="34645-163">未定</span><span class="sxs-lookup"><span data-stu-id="34645-163">TBD</span></span>|
|<span data-ttu-id="34645-164">PSTN の呼び出しを別のチームの 1 つのユーザーに転送します。</span><span class="sxs-lookup"><span data-stu-id="34645-164">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="34645-165">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="34645-165">Pass/Fail</span></span> | <span data-ttu-id="34645-166">未定</span><span class="sxs-lookup"><span data-stu-id="34645-166">TBD</span></span> |


>[!TIP]
><span data-ttu-id="34645-167">開始点として、テスト_ケースの作成を支援するには、[チームの会議や通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8?ui=en-US&rs=en-US&ad=US#bkmk_havingmeetings)で使用可能なオーディオ会議のユーザー ガイドの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34645-167">To assist with test-case creation as a starting point, see the list of audio conferencing user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8?ui=en-US&rs=en-US&ad=US#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="34645-168">チームの音声のワークロードをクラウドを設定します。</span><span class="sxs-lookup"><span data-stu-id="34645-168">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="34645-169">テスト方法を定義した、次の手順、構成、サービスの環境とユーザー チーム クラウドの音声機能のスコープ内です。</span><span class="sxs-lookup"><span data-stu-id="34645-169">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span> <span data-ttu-id="34645-170">詳細についてを参照してください[オーディオ会議のための技術的な計画](https://docs.microsoft.com/microsoftteams/audio-conferencing#technical-planning-for-audio-conferencing)および[計画を呼び出すと、電話システムの技術的な計画](https://docs.microsoft.com/microsoftteams/phone-system-with-calling-plans#technical-planning-for-phone-system-with-calling-plans)と[セットの他の[ビジネスおよびマイクロソフトのチームに Skype の電話会議の設定](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)ビジネスおよびマイクロソフトのチームに、Skype の通話プラン](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="34645-170">For additional information, see [Technical Planning for Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing#technical-planning-for-audio-conferencing) and [Set up Audio Conferencing for Skype for Business and Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) in addition to [Technical Planning for Phone System with Calling Plans](https://docs.microsoft.com/microsoftteams/phone-system-with-calling-plans#technical-planning-for-phone-system-with-calling-plans) and [Set up Calling Plans for Skype for Business and Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)</span></span>

<!--ENDOFSECTION-->

### <a name="execute-the-test-plan"></a><span data-ttu-id="34645-171">テスト計画を実行します。</span><span class="sxs-lookup"><span data-stu-id="34645-171">Execute the test plan</span></span>

<span data-ttu-id="34645-172">ユーザーとオーディオ会議サービスの環境を構成すると、テストの最後の手順には、機能と機能の検証でのフォーカスのあるテスト計画の実行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="34645-172">After the user and audio conferencing service environments have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="34645-173">**電話会議のスコープ内のユーザーとサイトの前提条件をテストします。**</span><span class="sxs-lookup"><span data-stu-id="34645-173">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="34645-174">ビジネスは、オーディオ会議サービスが完了したケースの定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="34645-174">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="34645-175">オーディオ会議に必要なライセンス、割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="34645-175">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="34645-176">組織のサイトとユーザー グループの一覧を指定しています。</span><span class="sxs-lookup"><span data-stu-id="34645-176">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="34645-177">言語の優先順位の番号にダイヤルを専用または共有の電話会議の一覧を特定して構成します。</span><span class="sxs-lookup"><span data-stu-id="34645-177">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="34645-178">[通信のクレジット](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)(必要な場合)、組織用に設定されています。</span><span class="sxs-lookup"><span data-stu-id="34645-178">[Communications Credits](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="34645-179">オーディオ会議会議ブリッジの設定がされている識別し、(暗証番号 (pin) の長さ、開始/終了の通知、通知の基本設定を有効化) を構成します。</span><span class="sxs-lookup"><span data-stu-id="34645-179">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="34645-180">テナント会議ポリシーとダイヤル プラン設定の識別、構成、および適用されるアウト ダイヤル シナリオの音声会議をサポートします。</span><span class="sxs-lookup"><span data-stu-id="34645-180">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="34645-181">オーディオ会議のコンプライアンス要件を特定して構成します。</span><span class="sxs-lookup"><span data-stu-id="34645-181">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="34645-182">**スコープ内のユーザーとサイトの前提条件のテスト計画を呼び出すことで電話システム。**</span><span class="sxs-lookup"><span data-stu-id="34645-182">**Phone System with Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="34645-183">サービスの計画を呼び出すと、電話システムのビジネス使用ケースの定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="34645-183">Business use case definition for the Phone System with Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="34645-184">計画を呼び出すと、電話システムに必要なライセンス、割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="34645-184">Licensing required for Phone System with Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="34645-185">組織のサイトとユーザー グループの一覧を指定しています。</span><span class="sxs-lookup"><span data-stu-id="34645-185">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="34645-186">ユーザーに割り当てられる電話番号を取得またはマイクロソフトとテナント ポータルで利用するように移植されました。</span><span class="sxs-lookup"><span data-stu-id="34645-186">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="34645-187">[通信のクレジット](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)(必要な場合)、組織用に設定されています。</span><span class="sxs-lookup"><span data-stu-id="34645-187">[Communications Credits](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="34645-188">テナント ユーザー ポリシーとダイヤル プランを識別、構成、および適用されるシナリオの計画を呼び出すと、電話システムをサポートするための設定をします。</span><span class="sxs-lookup"><span data-stu-id="34645-188">Tenant user policies and dial plan settings that support Phone System with Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="34645-189">コンプライアンス要件の計画を呼び出すと、電話システムが識別され構成されています。</span><span class="sxs-lookup"><span data-stu-id="34645-189">Phone System with Calling Plans compliance requirements have been identified and configured.</span></span>

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="34645-190">意思決定ポイント</span><span class="sxs-lookup"><span data-stu-id="34645-190">Decision points</span></span></td><td><ul><li><span data-ttu-id="34645-191">どの電話会議機能を展開するかを決定 (サービスの決定)。</span><span class="sxs-lookup"><span data-stu-id="34645-191">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="34645-192">オーディオ会議のユーザーの機能要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="34645-192">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="34645-193">オーディオ会議サービスの構成要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="34645-193">Identify service configuration requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="34645-194">計画を呼び出す機能を持つ電話システムを決定 (サービスの決定) を展開します。</span><span class="sxs-lookup"><span data-stu-id="34645-194">Decide which Phone System with Calling Plans feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="34645-195">計画を呼び出すと、電話システムのユーザーの機能要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="34645-195">Identify user functionality requirements for Phone System with Calling Plans.</span></span></li><li><span data-ttu-id="34645-196">計画を呼び出すと、電話システムのサービスの構成の要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="34645-196">Identify service configuration requirement for Phone System with Calling Plans.</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="34645-197">次のステップ</span><span class="sxs-lookup"><span data-stu-id="34645-197">Next steps</span></span></td><td><ul><li><span data-ttu-id="34645-198">開発し、テスト計画のアプローチを文書化します。</span><span class="sxs-lookup"><span data-stu-id="34645-198">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="34645-199">電話会議機能のスコープ内のユーザー、サービスの環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="34645-199">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="34645-200">計画を呼び出す機能を持つ電話システムのスコープ内のユーザー、サービスの環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="34645-200">Prepare your service environment and users in scope for Phone System with Calling Plans features.</span></span></li><li><span data-ttu-id="34645-201">電話会議機能を有効にするためのテストの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="34645-201">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="34645-202">有効にする計画を呼び出す機能を使用して電話システムのテスト検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="34645-202">Execute test validation for the Phone System with Calling Plans features that you want to enable.</span></span></li><li><span data-ttu-id="34645-203">いずれかの障害をテスト、構成が正しいことを確認、コミュニティの記事を確認し、-必要な場合-サポート ・ リクエストを発生させます。</span><span class="sxs-lookup"><span data-stu-id="34645-203">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="34645-204">チームでのオーディオ会議のためのテストを実行する方法の詳細なガイダンスを追加、[詳細なテスト ガイドのオーディオ会議] を参照してください (https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Audio-Conferencing)。</span><span class="sxs-lookup"><span data-stu-id="34645-204">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing]  (https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Audio-Conferencing).</span></span>

<span data-ttu-id="34645-205">チームの計画を呼び出すと、電話システムのテストを実行する方法に関する追加の詳細については、[電話システムのガイドをテストする詳細](https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Phone-System)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34645-205">For additional detailed guidance on how to perform testing for Phone System with Calling Plans in Teams, see the [detailed testing guide for Phone System](https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Phone-System).</span></span>

<!--ENDOFSECTION-->