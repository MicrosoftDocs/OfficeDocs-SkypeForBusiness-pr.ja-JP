---
title: Microsoft Teams クラウド ボイス サービスを展開する
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: サイトの有効化プレイブックをダウンロードして、Teams のロールアウトを計画し、ユーザーの導入を加速および最適化し、品質と満足度を認識します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3f0105a04484efcabd5ab6c55d1269c3627895
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112633"
---
# <a name="deploy-my-service"></a><span data-ttu-id="14093-103">サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="14093-103">Deploy my service</span></span>

<span data-ttu-id="14093-104">この記事では、クラウド 音声サービスを適切に展開する場合の要件の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="14093-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="14093-105">クラウド 音声サービスの展開に関する事前のガイダンスに従って、すべての要件を正しく考慮し、繰り返し可能な結果を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="14093-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="14093-106">Microsoft Teams 音声ワークロード用のサイト有効化プレイブック</span><span class="sxs-lookup"><span data-stu-id="14093-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="14093-107">このプレイブックを使用して、組織が Microsoft Teams 音声機能のロールアウトをサイト単位で正常に計画および実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="14093-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="14093-108">必要なすべてのアクティビティ、推奨されるタイムライン、各アクティビティに対応するガイダンスへのリンクなど、このプレイブックでは、ユーザーにとって重要な要素に重点を置き、特定のサイトで Teams の音声展開を成功に導く、エンドツーエンドのガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="14093-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="14093-109">このプレイブックのアクティビティを完了すると、組織は次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="14093-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="14093-110">Teams のロールアウトを効果的に計画し、スケジュールします。</span><span class="sxs-lookup"><span data-stu-id="14093-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="14093-111">ユーザーの導入を加速し、最適化します。</span><span class="sxs-lookup"><span data-stu-id="14093-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="14093-112">サポートのニーズを減らし、ユーザーの満足度を高めます。</span><span class="sxs-lookup"><span data-stu-id="14093-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="14093-113">この記事と関連するプレイブックは、サービスの有効化や特定のサイトへのダイヤル トーンの提供に必要な技術的な構成手順について説明するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="14093-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="14093-114">代わりに、ユーザーを簡単にオンボードするために推奨されるアクティビティとタスクに重点を置き、サポート要件を最小限に抑えながら、迅速かつスムーズな移行を通じて Teams 音声ワークロードの消費を開始します。</span><span class="sxs-lookup"><span data-stu-id="14093-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="14093-115">Teams 音声用に環境を最適に構成する方法に関する技術的なガイダンスについては [、Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)音声ワークロードの構成 [、Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)での直接ルーティングの構成 [、Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)のコア機能 [、Teams](prepare-network.md)のネットワーク、 [および Microsoft 365 または Office 365](onboarding-checklist-enable-office-365.md)の有効化に関するオンボーディング チェックリストを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14093-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](prepare-network.md), and [enabling Microsoft 365 or Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="14093-116">プレイブックのフォーカス領域</span><span class="sxs-lookup"><span data-stu-id="14093-116">Playbook focus areas</span></span>

<span data-ttu-id="14093-117">プレイブックの焦点は、Teams の音声展開に対するユーザーの認識に影響する要因に対処します。</span><span class="sxs-lookup"><span data-stu-id="14093-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="14093-118">アクティビティとタスクは、次のフォーカス領域にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="14093-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="14093-119">サービスの準備の検証</span><span class="sxs-lookup"><span data-stu-id="14093-119">Validation of service readiness</span></span>
    - <span data-ttu-id="14093-120">電話会議</span><span class="sxs-lookup"><span data-stu-id="14093-120">Audio Conferencing</span></span>
    - <span data-ttu-id="14093-121">通話プラン</span><span class="sxs-lookup"><span data-stu-id="14093-121">Calling Plans</span></span>
    - <span data-ttu-id="14093-122">ダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="14093-122">Direct Routing</span></span>

-   <span data-ttu-id="14093-123">ユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="14093-123">User enablement</span></span>

-   <span data-ttu-id="14093-124">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="14093-124">Endpoints</span></span>

-   <span data-ttu-id="14093-125">使用状況と品質</span><span class="sxs-lookup"><span data-stu-id="14093-125">Usage and quality</span></span>

-   <span data-ttu-id="14093-126">導入</span><span class="sxs-lookup"><span data-stu-id="14093-126">Adoption</span></span>

<span data-ttu-id="14093-127">音声 [用サイト有効化プレイブック (Playbook) は](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 、Microsoft Excel ブックです。</span><span class="sxs-lookup"><span data-stu-id="14093-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="14093-128">これら 5 つのフォーカス領域は、それぞれブック内の個別のシートであり、各展開タスクとアクティビティは、これらのシートの 1 つにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="14093-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="14093-129">![サイト有効化プレイブックのスクリーンショット](media/deploy-my-service-image1.png "プレイブックのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="14093-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="14093-130">Teams のロールアウトの範囲で、サイトごとにプレイブックの個別のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="14093-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="14093-131">プレイブックの使い方</span><span class="sxs-lookup"><span data-stu-id="14093-131">How to use the playbook</span></span>

<span data-ttu-id="14093-132">場所の規模や複雑さにかかわらず、各サイトを有効にする場合は、タスクとアクティビティを十分な早い段階で計画し、実際のサービス ロールアウトの前、中、後に最適な順序で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14093-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="14093-133">Microsoft Teams 音声への独自の手順を計画して実行する場合は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="14093-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="14093-134">Microsoft Teams [Voice 用の Voice 用サイト有効化プレイブック (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="14093-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="14093-135">サイトごとにプレイブックのコピーを個別に作成します。</span><span class="sxs-lookup"><span data-stu-id="14093-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="14093-136">**{SiteName-Code}** の Playbook という名前のシートのタブで **、{SiteName-Code}** を関連するサイト名またはサイト コードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="14093-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="14093-137">次に **示すサイト名、サイト** コード、および開始予定日を入力します。</span><span class="sxs-lookup"><span data-stu-id="14093-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="14093-138">これは重要な手順です。プレイブック内のすべてのアクティビティの推奨期限が調整されます。</span><span class="sxs-lookup"><span data-stu-id="14093-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="14093-139">![サイト名、サイト コード、および開始予定日の例](media/deploy-my-service-image2.png "ニューヨークのサイト名、サイト コード NY01、および 20-Mar-18 の開始予定日の例")</span><span class="sxs-lookup"><span data-stu-id="14093-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="14093-140">各アクティビティを確認し、必要なアクションを実行し、タイムラインを移動すると状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="14093-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="14093-141">状態は、以下で説明するようにグラフィックで表されます。</span><span class="sxs-lookup"><span data-stu-id="14093-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="14093-142">![緑のチェック マーク [はい]、または該当しない (緑色) の図: アクティビティが完了したか、このサイトに適用できないので、それ以上のアクションは ](media/deploy-my-service-image3.png) 必要はありません。</span><span class="sxs-lookup"><span data-stu-id="14093-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="14093-143">![黄色の感嘆符の図。アクティビティがまだ完了していません (黄色): アクティビティはまだ完了していません。スケジュールに合って [はい] または [いいえ] に更新する必要があります。 ](media/deploy-my-service-image4.png) <strong></strong></span><span class="sxs-lookup"><span data-stu-id="14093-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="14093-144">![[いいえ] (赤) を示す赤い X の図: 問題が原因でアクティビティを完了できないので、プロジェクトの状況会議に持ち ](media/deploy-my-service-image5.png) <strong></strong>込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="14093-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="14093-145">状態は各セクション内でロールアップされ、セクション見出しは次のいずれかのステータス インジケーターで書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="14093-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="14093-146">**週単位の** 状態も自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="14093-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="14093-147">![プレイブックの週次ステータスロールアップのスクリーンショット](media/deploy-my-service-image6.png "プレイブックの週次ステータス ロールアップのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="14093-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="14093-148">すべての場所について、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="14093-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14093-149">一部の手順は、一部の場所とサイトに適用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="14093-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="14093-150">特定のアクティビティがサイトに関連しない場合は、[このアクティビティに該当しない] を **選択する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="14093-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="14093-151">**プレイブック内** の行を削除しない。この操作を行った場合、状態のロールアップ数式は機能しません。</span><span class="sxs-lookup"><span data-stu-id="14093-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="14093-152">番号の移植や調達活動など、計画よりも時間がかかる可能性があるアクティビティに注意してください。</span><span class="sxs-lookup"><span data-stu-id="14093-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="14093-153">これらのアクティビティは、サイト展開タイムラインに悪影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14093-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="14093-154">アクティビティ リストと関連するタイムラインを毎週確認して更新し、運営委員会の会議で[](./envision-steering-committee-complete-guide.md)発表して、関係者が各サイトの状態と展開スケジュールからの偏差の可能性を確実に認識します。</span><span class="sxs-lookup"><span data-stu-id="14093-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](./envision-steering-committee-complete-guide.md) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="14093-155">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="14093-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="14093-156">展開にサイト有効化プレイブックが必要かを決定します。</span><span class="sxs-lookup"><span data-stu-id="14093-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="14093-157">展開するサイトごとに、Microsoft Teams のサイト有効化プレイブックをカスタマイズする責任者を決定します。</span><span class="sxs-lookup"><span data-stu-id="14093-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="14093-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="14093-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="14093-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">サイトの有効化プレイブックをダウンロードします</a>。</span><span class="sxs-lookup"><span data-stu-id="14093-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="14093-160">最初のサイト用にサイトの有効化プレイブックをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="14093-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="14093-161">必要に応じて、追加のサイトで同じ操作を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="14093-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->