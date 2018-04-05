---
title: マイクロソフト チーム クラウドのインターネット電話サービスを展開します。
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: サイトの対応戦略、チームのロールアウトを計画し、加速し、ユーザーの選定、品質、および満足度の認識を最適化をダウンロードします。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f59b7568f5ec0d3d9b6ef3b04f4094b222d0702b
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2018
---
# <a name="deploy-my-service"></a><span data-ttu-id="a16ef-103">サービスを展開します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-103">Deploy my service</span></span>

<span data-ttu-id="a16ef-104">この資料では、クラウドの音声サービスを正しく展開するための要件の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="a16ef-105">次のことを確認するクラウドの音声サービスを展開するための規範的なガイダンスが正常にすべての要件を明確にして反復可能な結果を提供します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="a16ef-106">音声のワークロードをマイクロソフト チームのサイトの有効化の戦略</span><span class="sxs-lookup"><span data-stu-id="a16ef-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="a16ef-107">このプレイブックを使用して、正常に計画し、サイトごとにマイクロソフトのチームの音声機能の展開を実行する組織を支援します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="a16ef-108">このプレイブックのチーム ボイス展開を成功させる重要な要因に焦点を当てて、特定のサイトを確保するエンド ・ ツー ・ エンドのガイダンスの説明など必要なすべての活動、時間帯、およびリンクを各アクティビティに対応するガイダンスを推奨ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a16ef-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="a16ef-109">このプレイブックのアクティビティを完了すると、組織は次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a16ef-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="a16ef-110">効率的に計画して、チームのロールアウト スケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="a16ef-111">迅速化し、ユーザーの導入を最適化します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="a16ef-112">サポートのニーズを削減し、ユーザーの満足度を向上します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="a16ef-113">この記事と関連付けられている戦略はないサービスの有効化に必要なまたは特定のサイトにダイヤル トーンを提供するすべての技術的な構成手順を説明するものです。</span><span class="sxs-lookup"><span data-stu-id="a16ef-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="a16ef-114">代わりに、簡単にオンボードのユーザーに推奨されるタスク活動に重点を置いて、サポート要件を最小限に抑えながら採用の高速度、高速かつ滑らかな遷移をチーム音声のワークロードの使用を開始することがあります。</span><span class="sxs-lookup"><span data-stu-id="a16ef-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="a16ef-115">最適なチームの音声を環境を構成する方法についての技術的なガイダンスは、Office 365 を有効にすると[音声のワークロードのチームを構成する](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams)[チームの中心的な機能](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities)、[チームのネットワーク](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)、および[の契約時チェックリストを参照してください。](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365).</span><span class="sxs-lookup"><span data-stu-id="a16ef-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams), [Teams core capabilities](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities), [networking for Teams](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking), and [enabling Office 365](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="a16ef-116">プレイブックの重点分野</span><span class="sxs-lookup"><span data-stu-id="a16ef-116">Playbook focus areas</span></span>

<span data-ttu-id="a16ef-117">プレイブックの焦点は、チームのボイスの展開のユーザーの認識に影響を与える要因に対処します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="a16ef-118">アクティビティとタスクは、次の重点分野にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="a16ef-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="a16ef-119">サービス対応の検証</span><span class="sxs-lookup"><span data-stu-id="a16ef-119">Validation of service readiness</span></span>

-   <span data-ttu-id="a16ef-120">ユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="a16ef-120">User enablement</span></span>

-   <span data-ttu-id="a16ef-121">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="a16ef-121">Endpoints</span></span>

-   <span data-ttu-id="a16ef-122">使用率と品質</span><span class="sxs-lookup"><span data-stu-id="a16ef-122">Usage and quality</span></span>

-   <span data-ttu-id="a16ef-123">導入</span><span class="sxs-lookup"><span data-stu-id="a16ef-123">Adoption</span></span>

<span data-ttu-id="a16ef-124">[(戦略) の音声をサイトの有効化の戦略](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)は、Microsoft Excel ブックです。</span><span class="sxs-lookup"><span data-stu-id="a16ef-124">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="a16ef-125">ブック内の別のシートは、これらの 5 つの重点分野のそれぞれと各展開タスクと活動がこれらのシートのいずれかにグループ化します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-125">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="a16ef-126">![プレイブックのスクリーン ショット](media/deploy-my-service-image1.png "プレイブックのスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="a16ef-126">![Screenshot of the playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="a16ef-127">チームの展開のスコープでは、各サイトのプレイブックの別のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-127">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="a16ef-128">プレイブックを使用する方法</span><span class="sxs-lookup"><span data-stu-id="a16ef-128">How to use the playbook</span></span>

<span data-ttu-id="a16ef-129">規模と複雑さの場所に関係なく各サイトを有効にする必要があります、タスクおよび活動を計画すること十分な事前- し、最適な順序で実行-の前にいる間、および実際のサービス導入後です。</span><span class="sxs-lookup"><span data-stu-id="a16ef-129">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="a16ef-130">計画およびマイクロソフトのチームの音声を独自の旅を実行する際は、次の手順に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a16ef-130">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1.  <span data-ttu-id="a16ef-131">マイクロソフト チームの音声を[サイトの有効化の戦略](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)(戦略) の音声をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="a16ef-131">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2.  <span data-ttu-id="a16ef-132">各サイトのプレイブックの別のコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-132">Create a separate copy of the playbook for each site.</span></span>

3.  <span data-ttu-id="a16ef-133">**{コード-サイト名} のプレイブック**をという名前のワークシートのタブ、[関連するサイトの名前とサイト コードの**{コード-サイト名}**を交換してください。</span><span class="sxs-lookup"><span data-stu-id="a16ef-133">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4.  <span data-ttu-id="a16ef-134">下図のように**サイト名、サイト コード**、および**計画の実施日**をを入力します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-134">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="a16ef-135">これは、推奨期限プレイブックですべてのアクティビティを調整するための重要なステップです。</span><span class="sxs-lookup"><span data-stu-id="a16ef-135">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

    <span data-ttu-id="a16ef-136">![ニューヨークのサイト名、サイト コード NY01、18-20-3 月 3 日の予定日を使用した例](media/deploy-my-service-image2.png "ニューヨークのサイト名、サイト コード NY01、18-20-3 月 3 日の予定日を使用した例")</span><span class="sxs-lookup"><span data-stu-id="a16ef-136">![Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5.  <span data-ttu-id="a16ef-137">各動作を確認して、必要な処理を行うスケジュールを説明するように状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-137">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="a16ef-138">状態が視覚的に、以下の説明として表されます。</span><span class="sxs-lookup"><span data-stu-id="a16ef-138">Status is represented graphically, as described below:</span></span>
    <ul>
    <li><span data-ttu-id="a16ef-139">![緑のチェック マーク](media/deploy-my-service-image3.png) **[はい]、または該当なし (緑):** 、アクティビティが完了すると、やこのサイトの該当する場合はそれ以上の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a16ef-139">![Green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
    <li><span data-ttu-id="a16ef-140">![黄色の感嘆符](media/deploy-my-service-image4.png)**活動はまだ完了されていない、(黄色):**活動がまだ完了していないし、スケジュール上、はいまたは No に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a16ef-140">![Yellow exclamation point](media/deploy-my-service-image4.png) **The activity isn’t completed yet (yellow):** The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
    <li><span data-ttu-id="a16ef-141">![赤の X](media/deploy-my-service-image5.png) **(赤):**活動の問題が発生したためが完了できず、プロジェクトの進捗会議を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a16ef-141">![Red X](media/deploy-my-service-image5.png) **No (red):** The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6.  <span data-ttu-id="a16ef-142">状態は、各セクションに重ね、セクションの見出しは、これらのステータス インジケーターのいずれかでフォーマットされました。</span><span class="sxs-lookup"><span data-stu-id="a16ef-142">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="a16ef-143">**毎週のステータス**に自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="a16ef-143">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="a16ef-144">![毎週の状態のロールアップ、プレイブックでのスクリーン ショット](media/deploy-my-service-image6.png "毎週の状態のロールアップ、プレイブックでのスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="a16ef-144">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="a16ef-145">あるすべての場所で上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-145">Repeat the steps above for all the locations you have.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a16ef-146">いくつかの手順をすべての場所やサイトに適用されることができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a16ef-146">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="a16ef-147">場合は、特定のアクティビティには、サイトに関連のない場合を選択してください**適用されない**この活動にします。</span><span class="sxs-lookup"><span data-stu-id="a16ef-147">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="a16ef-148">**削除しないで**プレイブック; のいずれかの行その場合は、状態ロールアップ数式は機能しません。</span><span class="sxs-lookup"><span data-stu-id="a16ef-148">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="a16ef-149">番号を移植するなどの計画より多くの時間を要する可能性がある活動と調達活動に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a16ef-149">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="a16ef-150">これらのアクティビティには、サイト展開の期限も悪影響します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-150">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="a16ef-151">確認し、アクティビティのリストと関連付けられているタイムラインの更新を毎週、および利害関係者が各サイトと展開のスケジュールは、可能な差異の状態の認識であることを確認するのには、[運営委員会の会議](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide)でそれらを提示することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-151">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="a16ef-152">意思決定ポイント</span><span class="sxs-lookup"><span data-stu-id="a16ef-152">Decision points</span></span></td><td><ul><li><span data-ttu-id="a16ef-153">サイト対応の戦略は、配置に必要なかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-153">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="a16ef-154">マイクロソフト チームのサイトの有効化の戦略をカスタマイズするのすべてのサイトを展開することを担当するユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-154">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you'll deploy.</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="a16ef-155">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a16ef-155">Next steps</span></span></td><td><ul><li><span data-ttu-id="a16ef-156">サイト対応のプレイブックをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a16ef-156">Download the Site Enablement Playbook.</span></span></li><li><span data-ttu-id="a16ef-157">最初のサイトのサイトの有効化の戦略をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="a16ef-157">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="a16ef-158">追加のサイトを必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a16ef-158">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->