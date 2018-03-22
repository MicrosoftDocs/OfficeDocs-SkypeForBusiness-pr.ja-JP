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
ms.openlocfilehash: a2b3d68d63661c988116f3b6729656eb3f34cf37
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="prepare-my-service"></a><span data-ttu-id="122e6-103">サービスを準備します。</span><span class="sxs-lookup"><span data-stu-id="122e6-103">Prepare my service</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="122e6-104">音声のワークロードをマイクロソフトのチームの契約時のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="122e6-104">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="122e6-105">次のチェックリストでは、マイクロソフトのチームでの計画を呼び出す機能を備えたオーディオ会議や電話システムを実装するための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="122e6-105">The following checklists walk you through the steps for implementing Audio Conferencing and Phone System with Calling Plans capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="122e6-106">Office 365 のチームを準備します。</span><span class="sxs-lookup"><span data-stu-id="122e6-106">Prepare Office 365 for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365)

*  [<span data-ttu-id="122e6-107">チームの中核的な機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="122e6-107">Configure Teams core capabilities</span></span>](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities)

*  [<span data-ttu-id="122e6-108">ネットワークを構成します。</span><span class="sxs-lookup"><span data-stu-id="122e6-108">Configure networking</span></span>](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)

*  [<span data-ttu-id="122e6-109">チームで音声のワークロードをクラウドを構成します。</span><span class="sxs-lookup"><span data-stu-id="122e6-109">Configure cloud voice workloads in Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams)

<span data-ttu-id="122e6-110">タスクとこれらのチェックリストでの作業は、チームと音声機能をクラウドのそれぞれの配置に適用されるコアの"to do"アイテムです。</span><span class="sxs-lookup"><span data-stu-id="122e6-110">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="122e6-111">活動と自分のチームの旅に特有のタスクを含むようにチェックリストをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="122e6-111">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="122e6-112">このガイドでは、計画を呼び出すと電話会議の電話システムにのみ焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="122e6-112">This guidance focuses solely on Phone System with Calling Plans and Audio Conferencing.</span></span> <span data-ttu-id="122e6-113">チームに新しい場合は、[マイクロソフトのチームの概要](https://docs.microsoft.com/MicrosoftTeams/teams-overview)を確認します。</span><span class="sxs-lookup"><span data-stu-id="122e6-113">If you’re new to Teams, review [Overview of Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span></span> <span data-ttu-id="122e6-114">チーム展開を計画するための一般的なガイダンスは、 [Microsoft のチームの計画ガイド 』](https://docs.microsoft.com/MicrosoftTeams/quick-start-enable-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="122e6-114">For general guidance for planning your Teams deployment, see the [Microsoft Teams Planning Guide](https://docs.microsoft.com/MicrosoftTeams/quick-start-enable-teams).</span></span>

<span data-ttu-id="122e6-115">個々 のアクティビティとタスクのステータスを追跡するために提供されているチェックリストを使用しの重要な手順をスキップしていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="122e6-115">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="122e6-116">各アクティビティには、必要なアクションとそのアクティビティを完了するのに使用できるその他の情報への参照の詳細な説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="122e6-116">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="122e6-117">順序のチェックリストを実行することをお勧めですが、展開と構成のスコープと環境の複雑さの厳密な順序によって異なります。</span><span class="sxs-lookup"><span data-stu-id="122e6-117">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="122e6-118">いずれか、"greenfield"をサポートするために整理されています、チームの配置 (ビジネス オンライン プレゼンスのない以前の Skype で 1 つ) または Skype からチームへのビジネスをオンラインに移行します。</span><span class="sxs-lookup"><span data-stu-id="122e6-118">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="122e6-119">ビジネス オンラインの Skype から移行する場合がすでに完了しているこれらの活動の一部と、それらをここで無視することができます。</span><span class="sxs-lookup"><span data-stu-id="122e6-119">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="122e6-120">サイトごとに契約時のユーザーが表示されたら、以下のチェックリストの補足ガイドとしては、[サイトの有効化の戦略 (戦略) の音声](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="122e6-120">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="122e6-121">ほとんどの構成設定は、チームと Skype のオンライン ビジネスの間で共通です。</span><span class="sxs-lookup"><span data-stu-id="122e6-121">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="122e6-122">これらの設定を構成するのにには、ビジネス管理センターの Office 365 の Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="122e6-122">You use Office 365 Skype for Business Administration Center to configure those settings.</span></span>

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="122e6-123">意思決定ポイント</span><span class="sxs-lookup"><span data-stu-id="122e6-123">Decision points</span></span></td><td><ul><li><span data-ttu-id="122e6-124">契約時チェックリストの完了を監督する責任者がされますか。</span><span class="sxs-lookup"><span data-stu-id="122e6-124">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="122e6-125">次のステップ</span><span class="sxs-lookup"><span data-stu-id="122e6-125">Next steps</span></span></td><td><ul><li><span data-ttu-id="122e6-126">契約時のチェックリストをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="122e6-126">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="122e6-127">契約時チェックリストの項目の手順に従って、組織の展開計画を使用します。</span><span class="sxs-lookup"><span data-stu-id="122e6-127">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="122e6-128">契約時を継続します。</span><span class="sxs-lookup"><span data-stu-id="122e6-128">Continue onboarding</span></span>

<span data-ttu-id="122e6-129">このチェックリストを完了すると、正常にようになりましたねボイス機能、チームの配置にします。</span><span class="sxs-lookup"><span data-stu-id="122e6-129">After you complete this checklist, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="122e6-130">次の手順では、 [(戦略) の音声をサイトの有効化の戦略](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用してユーザーを支援するオンボードの各サイトと計画し、重要なサイト固有のアクティビティを実行することを防止します。</span><span class="sxs-lookup"><span data-stu-id="122e6-130">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="122e6-131">準備ができてサイトごとの展開計画</span><span class="sxs-lookup"><span data-stu-id="122e6-131">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="122e6-132">サービス管理プロセスを確立します。</span><span class="sxs-lookup"><span data-stu-id="122e6-132">Establish Service Management Process</span></span>

-   <span data-ttu-id="122e6-133">テストを実行し、改善策</span><span class="sxs-lookup"><span data-stu-id="122e6-133">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="122e6-134">チームでクラウド音声の作業負荷をテスト</span><span class="sxs-lookup"><span data-stu-id="122e6-134">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="122e6-135">定義し Envision フェーズの一部として、チームのクラウド音声ビジネスの成功と技術的な実装計画を文書化して管理センターで必要な構成を行う、次の手順がいることを確認するのには、組織の機能、機能、および利便性を期待し、要件が満たされています。</span><span class="sxs-lookup"><span data-stu-id="122e6-135">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="122e6-136">運用環境でパイロットや最後の展開を展開する前に、この検証の手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="122e6-136">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="122e6-137">テスト段階で評価されるように活動、期待される、機能のテストの場合、および全体的な範囲を決定する基準として使用する Envision フェーズで定義したビジネスの成功プランを利用できます。</span><span class="sxs-lookup"><span data-stu-id="122e6-137">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="122e6-138">テスト アプローチを定義します。</span><span class="sxs-lookup"><span data-stu-id="122e6-138">Define your testing approach</span></span>

<span data-ttu-id="122e6-139">最も単純な形式では、テスト アプローチは、レビューの範囲内のユーザーのサービスの計画を呼び出すと、機能要件のことを確認するテスト計画を開発、オーディオ会議や電話システムの機能が満たされるに基づいています。</span><span class="sxs-lookup"><span data-stu-id="122e6-139">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing or Phone System with Calling Plans service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="122e6-140">オンボード オーディオ会議実装のフェーズでの例をテスト計画を次に示します。</span><span class="sxs-lookup"><span data-stu-id="122e6-140">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>

| <span data-ttu-id="122e6-141">オーディオ会議の機能をテストするには</span><span class="sxs-lookup"><span data-stu-id="122e6-141">Audio Conferencing feature to test</span></span> | <span data-ttu-id="122e6-142">結果の概要</span><span class="sxs-lookup"><span data-stu-id="122e6-142">Results summary</span></span> | <span data-ttu-id="122e6-143">追加の注記</span><span class="sxs-lookup"><span data-stu-id="122e6-143">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="122e6-144">オーディオ会議ダイヤルイン情報を含む特別なチームの会議のスケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="122e6-144">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="122e6-145">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="122e6-145">Pass/Fail</span></span>   | <span data-ttu-id="122e6-146">未定</span><span class="sxs-lookup"><span data-stu-id="122e6-146">TBD</span></span> |
| <span data-ttu-id="122e6-147">電話を使用して、提供されているダイヤルイン情報を使用して、PSTN から会議にダイヤルインしてミーティング オーディオの</span><span class="sxs-lookup"><span data-stu-id="122e6-147">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="122e6-148">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="122e6-148">Pass/Fail</span></span> | <span data-ttu-id="122e6-149">未定</span><span class="sxs-lookup"><span data-stu-id="122e6-149">TBD</span></span> |
| <span data-ttu-id="122e6-150">PSTN を使用してダイヤルアウトで他のユーザーを既存の会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="122e6-150">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="122e6-151">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="122e6-151">Pass/Fail</span></span> | <span data-ttu-id="122e6-152">未定</span><span class="sxs-lookup"><span data-stu-id="122e6-152">TBD</span></span> |


| <span data-ttu-id="122e6-153">計画を呼び出す機能をテストする電話システム</span><span class="sxs-lookup"><span data-stu-id="122e6-153">Phone System with Calling Plans feature to test</span></span> | <span data-ttu-id="122e6-154">結果の概要</span><span class="sxs-lookup"><span data-stu-id="122e6-154">Results summary</span></span> | <span data-ttu-id="122e6-155">追加の注記</span><span class="sxs-lookup"><span data-stu-id="122e6-155">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="122e6-156">PSTN 番号をダイヤルすることによって、PSTN の呼び出しを行う</span><span class="sxs-lookup"><span data-stu-id="122e6-156">Make a PSTN call to by dialing a PSTN number</span></span>       | <span data-ttu-id="122e6-157">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="122e6-157">Pass/Fail</span></span>       | <span data-ttu-id="122e6-158">未定</span><span class="sxs-lookup"><span data-stu-id="122e6-158">TBD</span></span> |
| <span data-ttu-id="122e6-159">外部の行 (モバイル、地上線) から、PSTN の番号をダイヤルすることによって、PSTN の呼び出しを受信します。</span><span class="sxs-lookup"><span data-stu-id="122e6-159">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="122e6-160">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="122e6-160">Pass/Fail</span></span> | <span data-ttu-id="122e6-161">未定</span><span class="sxs-lookup"><span data-stu-id="122e6-161">TBD</span></span>|
|<span data-ttu-id="122e6-162">PSTN の呼び出しを別のチームの 1 つのユーザーに転送します。</span><span class="sxs-lookup"><span data-stu-id="122e6-162">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="122e6-163">合格/不合格</span><span class="sxs-lookup"><span data-stu-id="122e6-163">Pass/Fail</span></span> | <span data-ttu-id="122e6-164">未定</span><span class="sxs-lookup"><span data-stu-id="122e6-164">TBD</span></span> |


>[!TIP]
><span data-ttu-id="122e6-165">開始点として、テスト_ケースの作成を支援するには、[チームの会議や通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8?ui=en-US&rs=en-US&ad=US#bkmk_havingmeetings)で使用可能なオーディオ会議のユーザー ガイドの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="122e6-165">To assist with test-case creation as a starting point, see the list of audio conferencing user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8?ui=en-US&rs=en-US&ad=US#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="122e6-166">チームの音声のワークロードをクラウドを設定します。</span><span class="sxs-lookup"><span data-stu-id="122e6-166">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="122e6-167">テスト方法を定義した、次の手順、構成、サービスの環境とユーザー チーム クラウドの音声機能のスコープ内です。</span><span class="sxs-lookup"><span data-stu-id="122e6-167">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span> <span data-ttu-id="122e6-168">詳細についてを参照してください[オーディオ会議のための技術的な計画](https://docs.microsoft.com/microsoftteams/audio-conferencing#technical-planning-for-audio-conferencing)および[計画を呼び出すと、電話システムの技術的な計画](https://docs.microsoft.com/microsoftteams/phone-system-with-calling-plans#technical-planning-for-phone-system-with-calling-plans)と[セットの他の[ビジネスおよびマイクロソフトのチームに Skype の電話会議の設定](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)ビジネスおよびマイクロソフトのチームに、Skype の通話プラン](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="122e6-168">For additional information, see [Technical Planning for Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing#technical-planning-for-audio-conferencing) and [Set up Audio Conferencing for Skype for Business and Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) in addition to [Technical Planning for Phone System with Calling Plans](https://docs.microsoft.com/microsoftteams/phone-system-with-calling-plans#technical-planning-for-phone-system-with-calling-plans) and [Set up Calling Plans for Skype for Business and Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)</span></span>

<!--ENDOFSECTION-->

### <a name="execute-the-test-plan"></a><span data-ttu-id="122e6-169">テスト計画を実行します。</span><span class="sxs-lookup"><span data-stu-id="122e6-169">Execute the test plan</span></span>

<span data-ttu-id="122e6-170">ユーザーとオーディオ会議サービスの環境を構成すると、テストの最後の手順には、機能と機能の検証でのフォーカスのあるテスト計画の実行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="122e6-170">After the user and audio conferencing service environments have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="122e6-171">**電話会議のスコープ内のユーザーとサイトの前提条件をテストします。**</span><span class="sxs-lookup"><span data-stu-id="122e6-171">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="122e6-172">ビジネスは、オーディオ会議サービスが完了したケースの定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="122e6-172">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="122e6-173">オーディオ会議に必要なライセンス、割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="122e6-173">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="122e6-174">組織のサイトとユーザー グループの一覧を指定しています。</span><span class="sxs-lookup"><span data-stu-id="122e6-174">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="122e6-175">言語の優先順位の番号にダイヤルを専用または共有の電話会議の一覧を特定して構成します。</span><span class="sxs-lookup"><span data-stu-id="122e6-175">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="122e6-176">[通信のクレジット](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)(必要な場合)、組織用に設定されています。</span><span class="sxs-lookup"><span data-stu-id="122e6-176">[Communications Credits](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="122e6-177">オーディオ会議会議ブリッジの設定がされている識別し、(暗証番号 (pin) の長さ、開始/終了の通知、通知の基本設定を有効化) を構成します。</span><span class="sxs-lookup"><span data-stu-id="122e6-177">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="122e6-178">テナント会議ポリシーとダイヤル プラン設定の識別、構成、および適用されるアウト ダイヤル シナリオの音声会議をサポートします。</span><span class="sxs-lookup"><span data-stu-id="122e6-178">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="122e6-179">オーディオ会議のコンプライアンス要件を特定して構成します。</span><span class="sxs-lookup"><span data-stu-id="122e6-179">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="122e6-180">**スコープ内のユーザーとサイトの前提条件のテスト計画を呼び出すことで電話システム。**</span><span class="sxs-lookup"><span data-stu-id="122e6-180">**Phone System with Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="122e6-181">サービスの計画を呼び出すと、電話システムのビジネス使用ケースの定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="122e6-181">Business use case definition for the Phone System with Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="122e6-182">計画を呼び出すと、電話システムに必要なライセンス、割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="122e6-182">Licensing required for Phone System with Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="122e6-183">組織のサイトとユーザー グループの一覧を指定しています。</span><span class="sxs-lookup"><span data-stu-id="122e6-183">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="122e6-184">ユーザーに割り当てられる電話番号を取得またはマイクロソフトとテナント ポータルで利用するように移植されました。</span><span class="sxs-lookup"><span data-stu-id="122e6-184">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="122e6-185">[通信のクレジット](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)(必要な場合)、組織用に設定されています。</span><span class="sxs-lookup"><span data-stu-id="122e6-185">[Communications Credits](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="122e6-186">テナント ユーザー ポリシーとダイヤル プランを識別、構成、および適用されるシナリオの計画を呼び出すと、電話システムをサポートするための設定をします。</span><span class="sxs-lookup"><span data-stu-id="122e6-186">Tenant user policies and dial plan settings that support Phone System with Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="122e6-187">コンプライアンス要件の計画を呼び出すと、電話システムが識別され構成されています。</span><span class="sxs-lookup"><span data-stu-id="122e6-187">Phone System with Calling Plans compliance requirements have been identified and configured.</span></span>

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="122e6-188">意思決定ポイント</span><span class="sxs-lookup"><span data-stu-id="122e6-188">Decision points</span></span></td><td><ul><li><span data-ttu-id="122e6-189">どの電話会議機能を展開するかを決定 (サービスの決定)。</span><span class="sxs-lookup"><span data-stu-id="122e6-189">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="122e6-190">オーディオ会議のユーザーの機能要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="122e6-190">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="122e6-191">オーディオ会議サービスの構成要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="122e6-191">Identify service configuration requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="122e6-192">計画を呼び出す機能を持つ電話システムを決定 (サービスの決定) を展開します。</span><span class="sxs-lookup"><span data-stu-id="122e6-192">Decide which Phone System with Calling Plans feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="122e6-193">計画を呼び出すと、電話システムのユーザーの機能要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="122e6-193">Identify user functionality requirements for Phone System with Calling Plans.</span></span></li><li><span data-ttu-id="122e6-194">計画を呼び出すと、電話システムのサービスの構成の要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="122e6-194">Identify service configuration requirement for Phone System with Calling Plans.</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="122e6-195">次のステップ</span><span class="sxs-lookup"><span data-stu-id="122e6-195">Next steps</span></span></td><td><ul><li><span data-ttu-id="122e6-196">開発し、テスト計画のアプローチを文書化します。</span><span class="sxs-lookup"><span data-stu-id="122e6-196">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="122e6-197">電話会議機能のスコープ内のユーザー、サービスの環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="122e6-197">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="122e6-198">計画を呼び出す機能を持つ電話システムのスコープ内のユーザー、サービスの環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="122e6-198">Prepare your service environment and users in scope for Phone System with Calling Plans features.</span></span></li><li><span data-ttu-id="122e6-199">電話会議機能を有効にするためのテストの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="122e6-199">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="122e6-200">有効にする計画を呼び出す機能を使用して電話システムのテスト検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="122e6-200">Execute test validation for the Phone System with Calling Plans features that you want to enable.</span></span></li><li><span data-ttu-id="122e6-201">いずれかの障害をテスト、構成が正しいことを確認、コミュニティの記事を確認し、-必要な場合-サポート ・ リクエストを発生させます。</span><span class="sxs-lookup"><span data-stu-id="122e6-201">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="122e6-202">チームでのオーディオ会議のためのテストを実行する方法の詳細なガイダンスを追加、[詳細なテスト ガイドのオーディオ会議] を参照してください (https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Audio-Conferencing)。</span><span class="sxs-lookup"><span data-stu-id="122e6-202">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing]  (https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Audio-Conferencing).</span></span>

<span data-ttu-id="122e6-203">チームの計画を呼び出すと、電話システムのテストを実行する方法に関する追加の詳細については、[電話システムのガイドをテストする詳細](https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Phone-System)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="122e6-203">For additional detailed guidance on how to perform testing for Phone System with Calling Plans in Teams, see the [detailed testing guide for Phone System](https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Phone-System).</span></span>

<!--ENDOFSECTION-->