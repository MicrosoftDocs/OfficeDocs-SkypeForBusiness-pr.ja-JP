---
title: Microsoft Teams クラウド ボイス サービスを展開する
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: サイト有効化のプレイブックをダウンロードして、チームのロールアウトを計画し、ユーザーの採用、品質、および満足度を向上させることができます。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c4652e27caf207b1af275ecc1fae0d0daa8598b
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548367"
---
# <a name="deploy-my-service"></a><span data-ttu-id="dc4ee-103">サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="dc4ee-103">Deploy my service</span></span>

<span data-ttu-id="dc4ee-104">この記事では、クラウド音声サービスを適切に展開するための要件の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="dc4ee-105">クラウド音声サービスを展開するための規範となるガイダンスに従うと、すべての要件を適切に考慮して、反復可能な結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="dc4ee-106">Microsoft Teams の音声ワークロードのためのサイトの有効化のプレイブック</span><span class="sxs-lookup"><span data-stu-id="dc4ee-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="dc4ee-107">このプレイブックを使用して、組織がサイトごとに Microsoft Teams の音声機能のロールアウトを正常に計画して実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="dc4ee-108">このプレイには、必要なすべてのアクティビティ、推奨されるタイムライン、および各アクティビティの対応するガイダンスへのリンクが含まれています。このプレイには、特定のサイトにチームの音声展開を成功させるためのエンドツーエンドのガイダンスが記載されています。重要な要因に焦点を当てます。を選びます。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="dc4ee-109">このプレイブックのアクティビティを完了することで、組織は次のことができます。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="dc4ee-110">チームのロールアウトを効果的に計画してスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="dc4ee-111">ユーザー導入を迅速化し、最適化します。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="dc4ee-112">サポートニーズを減らし、ユーザーの満足度を高める。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="dc4ee-113">この記事と関連するプレイブックは、サービスの有効化または特定のサイトへのダイヤルトーンの提供に必要なすべての技術的構成手順を説明することを目的としていません。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="dc4ee-114">代わりに、ユーザーが簡単にオンボードで作業するために推奨されるアクティビティとタスクに重点を置いています。また、サポート要件を最小限に抑えながら、迅速かつスムーズな移行によってチームのボイスワークロードを使い始めることができます。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="dc4ee-115">チームボイス向けに環境を最適に構成する方法についての技術的なガイダンスについては、「チームの[音声ワークロードを構成](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)する」のオンボードチェックリストを参照してください。 [Teams での直接ルーティングの構成](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)、 [teams のコア機能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)、[ネットワークTeams の](onboarding-checklist-configure-networking.md)場合は、 [Office 365 を有効](onboarding-checklist-enable-office-365.md)にします。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](onboarding-checklist-configure-networking.md), and [enabling Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="dc4ee-116">フォーカス領域</span><span class="sxs-lookup"><span data-stu-id="dc4ee-116">Playbook focus areas</span></span>

<span data-ttu-id="dc4ee-117">このプレイブックの焦点は、チームの音声展開に対するユーザーの認識に影響を与える要因に対処することです。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="dc4ee-118">アクティビティとタスクは、次のフォーカス領域にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="dc4ee-119">サービス準備の検証</span><span class="sxs-lookup"><span data-stu-id="dc4ee-119">Validation of service readiness</span></span>
    - <span data-ttu-id="dc4ee-120">電話会議</span><span class="sxs-lookup"><span data-stu-id="dc4ee-120">Audio Conferencing</span></span>
    - <span data-ttu-id="dc4ee-121">通話プラン</span><span class="sxs-lookup"><span data-stu-id="dc4ee-121">Calling Plans</span></span>
    - <span data-ttu-id="dc4ee-122">ダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="dc4ee-122">Direct Routing</span></span>

-   <span data-ttu-id="dc4ee-123">ユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="dc4ee-123">User enablement</span></span>

-   <span data-ttu-id="dc4ee-124">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="dc4ee-124">Endpoints</span></span>

-   <span data-ttu-id="dc4ee-125">使用状況と品質</span><span class="sxs-lookup"><span data-stu-id="dc4ee-125">Usage and quality</span></span>

-   <span data-ttu-id="dc4ee-126">出産</span><span class="sxs-lookup"><span data-stu-id="dc4ee-126">Adoption</span></span>

<span data-ttu-id="dc4ee-127">[音声 (プレイブック) のサイト有効化のプレイ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)ブックは Microsoft Excel ブックです。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="dc4ee-128">これら5つの各フォーカス領域は、ブック内の個別のシートであり、展開タスクとアクティビティはそれぞれ次のいずれかのシートにまとめられています。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="dc4ee-129">![サイトの有効化のプレイブックのスクリーンショット](media/deploy-my-service-image1.png "プレイブックのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="dc4ee-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="dc4ee-130">チームのロールアウトの対象となる範囲内の各サイトについて、個別のプレイブックのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="dc4ee-131">プレイブックの使い方</span><span class="sxs-lookup"><span data-stu-id="dc4ee-131">How to use the playbook</span></span>

<span data-ttu-id="dc4ee-132">場所のサイズと複雑さに関係なく、各サイトを有効にするには、実際のサービスのロールアウトの前、前後、または後で、タスクとアクティビティを適切な順序で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="dc4ee-133">Microsoft Teams voice の計画を立てて実行する場合は、次の手順に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="dc4ee-134">Microsoft Teams Voice 用の[音声 (プレイブック) 用のサイト有効化のプレイブック](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="dc4ee-135">各サイトのプレイブックのコピーを別途作成します。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="dc4ee-136">**{Sitename-code} 用の "プレイブック**" というシートのタブで、 **{sitename-code}** を関連するサイト名やサイトコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="dc4ee-137">次に示すように、**サイト名、サイトコード**、計画された**開始日**を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="dc4ee-138">これは、プレイブック内のすべてのアクティビティについて推奨される期限を調整するため、重要なステップです。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="dc4ee-139">![サイト名、サイトコード、計画された開始日の例](media/deploy-my-service-image2.png "ニューヨークのサイト名、サイトコードの NY01、予定されている開始日: 3 月18日の例")</span><span class="sxs-lookup"><span data-stu-id="dc4ee-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="dc4ee-140">各アクティビティを確認し、必要なアクションを実行して、タイムラインを通して状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="dc4ee-141">次に示すように、状態はグラフィカルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="dc4ee-142">![緑のチェックマーク](media/deploy-my-service-image3.png)が **[はい] または [該当しない] (緑)** の場合: アクティビティが完了しているか、このサイトには適用されず、これ以上の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="dc4ee-143">![まだアクティビティが完了して](media/deploy-my-service-image4.png)いないことを示す黄色の感嘆符<strong>(黄):</strong>アクティビティはまだ完了していません。また、スケジュールされている場合は、[はい] または [いいえ] に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="dc4ee-144">![赤い X マーク](media/deploy-my-service-image5.png) <strong>(赤)</strong>の図: 問題が発生したため、そのアクティビティは完了できません。また、プロジェクトの進捗会議に参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-144">![Illustration of a red X mark](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="dc4ee-145">ステータスは各セクション内でロールアップされ、セクション見出しは次のいずれかのステータスインジケーターで表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="dc4ee-146">**週単位のステータス**も自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="dc4ee-147">![プレイブックの毎週のステータスロールアップのスクリーンショット](media/deploy-my-service-image6.png "プレイブックの毎週のステータスロールアップのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="dc4ee-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="dc4ee-148">使用しているすべての場所について、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc4ee-149">一部の手順は、すべての場所やサイトに適用されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="dc4ee-150">特定のアクティビティがサイトに関連していない場合は、このアクティビティに**適用しない**ことを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="dc4ee-151">プレイブック内の行を削除しないで**ください**。この操作を行うと、ステータスロールアップ数式が機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="dc4ee-152">電話番号の移植や調達など、計画した時間よりも時間がかかる可能性があるアクティビティには注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="dc4ee-153">これらのアクティビティは、サイト展開のタイムラインに悪影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="dc4ee-154">アクティビティリストと関連するタイムラインの週を確認して更新して、関係者[](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide)が各サイトのステータスと展開スケジュールの誤差を確実に認識できるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="dc4ee-155">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="dc4ee-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="dc4ee-156">展開にサイトの有効化のプレイブックが必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="dc4ee-157">展開するすべてのサイトについて、Microsoft Teams のサイト有効化のプレイブックをカスタマイズする責任者を決定します。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="dc4ee-158">次のステップ</span><span class="sxs-lookup"><span data-stu-id="dc4ee-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="dc4ee-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">サイト有効化のプレイブックをダウンロード</a>します。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="dc4ee-160">初めてのサイト向けのサイト有効化のプレイブックをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="dc4ee-161">必要に応じて、他のサイトにも同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="dc4ee-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->