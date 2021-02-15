---
title: Microsoft Teams のアプリ、ボット、およびコネクタ
ms.reviewer: ''
description: アプリ、ボット、コネクタについて、および組織のプロファイルとビジネスの要件に基づいてどれを Microsoft Teams に展開するかについて説明します。
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: admin
ms.date: 02/10/2021
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d1a6462d0cb1581142eb2f5076e6b2ebad2b9003
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196521"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a><span data-ttu-id="8d280-103">Microsoft Teams のアプリ、ボット、およびコネクタ</span><span class="sxs-lookup"><span data-stu-id="8d280-103">Apps, bots, & connectors in Microsoft Teams</span></span>

<span data-ttu-id="8d280-104">アプリを使用すると、お気に入りのサービスからコンテンツを見つけて、そのコンテンツを Teams で共有できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8d280-104">Apps let you find content from your favorite services and share it in Teams.</span></span> <span data-ttu-id="8d280-105">チャネルの上部にサービスを固定したり、ボットとチャットしたり、タスクを共有および割り当てるときなどに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8d280-105">They help you do things such as pin services at the top of a channel, chat with bots, or share and assign tasks.</span></span> <span data-ttu-id="8d280-106">詳細については、「[Teams のアプリの概要](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-106">To learn more, read [Overview of apps in Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).</span></span> 

<span data-ttu-id="8d280-107">Microsoft Teams で提供されるアプリを使用するか、認定されたサードパーティのアプリとテンプレートを使用するか、独自のカスタム アプリを作成することにより、Teams の展開にアプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8d280-107">You can add apps to your Teams deployment by using the apps provided with Microsoft Teams, by using certified third-party apps and templates, and by creating your own custom apps.</span></span>

## <a name="use-microsoft-provided-apps"></a><span data-ttu-id="8d280-108">Microsoft 提供のアプリを使用する</span><span class="sxs-lookup"><span data-stu-id="8d280-108">Use Microsoft-provided apps</span></span>

<span data-ttu-id="8d280-109">Teams には、リスト、Tasks、称賛、承認などを含む一連の組み込みアプリが付属しています。</span><span class="sxs-lookup"><span data-stu-id="8d280-109">Teams comes with a set of built-in apps, including Lists, Tasks, Praise, Approvals, and more.</span></span> <span data-ttu-id="8d280-110">Teams の初期展開時に、おすすめのアプリ (Planner など) を含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d280-110">We recommend that you include Teams featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="8d280-111">Teams 導入の進行に応じて、その他のアプリ、ボット、およびコネクタを追加してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-111">Add other apps, bots, & connectors as you drive Teams adoption.</span></span>

## <a name="use-third-party-apps"></a><span data-ttu-id="8d280-112">サードパーティ製アプリを使用する</span><span class="sxs-lookup"><span data-stu-id="8d280-112">Use third-party apps</span></span>

<span data-ttu-id="8d280-113">Microsoft 提供のアプリに加えて、Microsoft 認定のサードパーティ製アプリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d280-113">In addition to Microsoft-provided apps, you can use Microsoft-certified third-party apps.</span></span> <span data-ttu-id="8d280-114">Microsoft は、Microsoft 365 開発者パートナーと協力して、Teams アプリとアドインの使用に関する決定を迅速化するために必要な情報を提供します。詳細については、「[Microsoft Teams アプリのセキュリティとコンプライアンス](https://docs.microsoft.com/microsoft-365-app-certification/teams/teams-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-114">Microsoft works with  Microsoft 365 developer partners to provide the information needed to expedite decisions about using Teams apps and add-ins. For more information, see [Microsoft Teams App Security and Compliance](https://docs.microsoft.com/microsoft-365-app-certification/teams/teams-apps).</span></span>

## <a name="use-teams-templates"></a><span data-ttu-id="8d280-115">Teams テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="8d280-115">Use Teams templates</span></span>

<span data-ttu-id="8d280-116">また、Microsoft Teams 用の実稼働可能なアプリ、[Teams テンプレート](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を使用することもできます。コミュニティ主導型、オープン ソースで、GitHub で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8d280-116">You can also use [Teams templates](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json), production-ready apps for Microsoft Teams that are community driven, open-source, and available on GitHub.</span></span>

## <a name="create-custom-apps"></a><span data-ttu-id="8d280-117">カスタム アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="8d280-117">Create custom apps</span></span>

<span data-ttu-id="8d280-118">Teams の [Microsoft Power Platform](teams-power-platfom-integration.md) との統合を使用すると、カスタムのローコード (わずかなコードを記述するだけで使用できる) ソリューションをすばやく構築できます。</span><span class="sxs-lookup"><span data-stu-id="8d280-118">You can quickly build custom low-code solutions by using Teams integration with [Microsoft Power Platform](teams-power-platfom-integration.md).</span></span> <span data-ttu-id="8d280-119">ビジネス ニーズに合わせて独自のカスタム アプリを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8d280-119">You can also create your own custom app to suit your business needs.</span></span> <span data-ttu-id="8d280-120">詳細については、「[Microsoft Teams 用アプリを構築する](https://docs.microsoft.com/microsoftteams/platform/overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-120">For more information, see [Build apps for Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/overview).</span></span>  


## <a name="apps-deployment-decisions"></a><span data-ttu-id="8d280-121">アプリの展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="8d280-121">Apps deployment decisions</span></span>

<span data-ttu-id="8d280-p105">Teams は、すぐに使用できる優れたコラボレーション エクスペリエンスを組織に提供します。ほとんどの組織は、既定の設定がよく機能することに気づいています。この記事は、組織のプロファイルとビジネス要件に基づいて、既定の設定のいずれかを変更するかどうかを決定する方法について、その後、各変更について説明します。設定を 2 つのグループに分割しました。まず、[変更を加える可能性が高い](#core-deployment-decisions)コアセットから始めます。2 番目のグループには、組織のニーズに基づいて構成する可能性のある[追加の設定](#additional-deployment-decisions)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d280-p105">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="8d280-126">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="8d280-126">Core deployment decisions</span></span>

<span data-ttu-id="8d280-127">次に示すアプリの設定は、ほとんどの組織が変更を必要とするものです (Teams の既定の設定では適切に動作しない場合)。</span><span class="sxs-lookup"><span data-stu-id="8d280-127">These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).</span></span>

### <a name="app-availability-settings"></a><span data-ttu-id="8d280-128">アプリの可用性の設定</span><span class="sxs-lookup"><span data-stu-id="8d280-128">App availability settings</span></span> 

<span data-ttu-id="8d280-129">Teams は、Microsoft とサード パーティによって発行された複数のアプリを提供します。それらのアプリは、ユーザー参加の促進、生産性のサポート、一般に使用されるビジネス サービスの Teams への統合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="8d280-129">Teams provides many apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="8d280-130">Teams Store からアプリを入手してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-130">Get apps from the Teams Store.</span></span> <span data-ttu-id="8d280-131">既定では、すべてのアプリ ([Teams Store 承認プロセス](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)で提出したカスタム アプリを含む) が、すべてのユーザーに対してオンにされています。</span><span class="sxs-lookup"><span data-stu-id="8d280-131">By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users.</span></span> <span data-ttu-id="8d280-132">たとえば、ユーザーは Planner アプリを使用して Teams のチーム タスクを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="8d280-132">For example, users can use the Planner app to build and manage team tasks in Teams.</span></span>

<span data-ttu-id="8d280-133">既定では、すべての Microsoft 提供のアプリ、サード パーティ製、カスタム アプリが使用可能になっていて、個別のアプリをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8d280-133">By default, all Microsoft-provided, third-party, and custom apps are available, and you can turn individual apps on or off.</span></span> <span data-ttu-id="8d280-134">すべてのサード パーティ製および/またはカスタム アプリを組織全体でオンまたはオフにできる、組織全体の設定があります。</span><span class="sxs-lookup"><span data-stu-id="8d280-134">There are org-wide settings that lets you turn all third-party and/or custom apps on or off for your entire organization.</span></span>

| <span data-ttu-id="8d280-135">確認事項</span><span class="sxs-lookup"><span data-stu-id="8d280-135">Ask yourself</span></span> | <span data-ttu-id="8d280-136">アクション</span><span class="sxs-lookup"><span data-stu-id="8d280-136">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="8d280-137">既定の Teams アプリの設定を変更するか?</span><span class="sxs-lookup"><span data-stu-id="8d280-137">Will you change the default Teams apps settings?</span></span> | <span data-ttu-id="8d280-138">組織内のアプリを管理するために使用できるポリシーと設定の詳細については、「[Microsoft Teams でのアプリの管理設定](admin-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-138">For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="app-permissions-and-other-considerations"></a><span data-ttu-id="8d280-139">アプリのアクセス許可とその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="8d280-139">App permissions and other considerations</span></span>

<span data-ttu-id="8d280-140">アプリはユーザーが同意し、管理者または IT 担当者がポリシーによって管理します。</span><span class="sxs-lookup"><span data-stu-id="8d280-140">Apps are consented to by users and managed by the admin or IT pro through policies.</span></span> <span data-ttu-id="8d280-141">ただし、ほとんどの場合、アプリのアクセス許可とリスク プロファイルはアプリ自体で定義されています。</span><span class="sxs-lookup"><span data-stu-id="8d280-141">However, for the most part, an app's permissions and risk profile are defined in the app itself.</span></span> 

| <span data-ttu-id="8d280-142">確認事項</span><span class="sxs-lookup"><span data-stu-id="8d280-142">Ask yourself</span></span> | <span data-ttu-id="8d280-143">アクション</span><span class="sxs-lookup"><span data-stu-id="8d280-143">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="8d280-144">どのアプリへのアクセスを許可するか?</span><span class="sxs-lookup"><span data-stu-id="8d280-144">Which apps do I want to allow access to?</span></span> <span data-ttu-id="8d280-145">どのアプリへのアクセスを禁止するか?</span><span class="sxs-lookup"><span data-stu-id="8d280-145">Which ones do I not want to allow access to?</span></span>  | <ul><li><span data-ttu-id="8d280-146">アプリ、ボット、タブ、またはコネクタへのアクセスを許可する際の考慮事項に関するリストについては、「[Microsoft Teams アプリのアクセス許可と考慮事項](app-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-146">See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</span></span></li><li><span data-ttu-id="8d280-147">組織内のユーザーがアプリを使用できるようにする方法の詳細については、「[Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-147">See [Manage your apps in the Microsoft Teams admin center](manage-apps.md) for information about making an app available to users in your organization.</span></span></li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a><span data-ttu-id="8d280-148">プライベート チャットおよびチャネルのボット</span><span class="sxs-lookup"><span data-stu-id="8d280-148">Bots for private chats and channels</span></span>

<span data-ttu-id="8d280-149">ボットとは、クエリに応答したり、ユーザーが興味を持っている詳細や常に情報を得ていたい詳細について更新や通知を行う自動プログラムのことです。</span><span class="sxs-lookup"><span data-stu-id="8d280-149">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="8d280-150">ボットを使用すると、ユーザーは Teams チャットでのタスク管理、スケジュール設定、投票などのクラウド サービスと対話できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8d280-150">Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat.</span></span> <span data-ttu-id="8d280-151">Teams は、プライベートのチャットおよびチャネルでボットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8d280-151">Teams supports bots in private chats and channels.</span></span> <span data-ttu-id="8d280-152">管理者は、Microsoft 365 組織または Office 365 組織でのボットの使用を許可するかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="8d280-152">Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.</span></span>

| <span data-ttu-id="8d280-153">確認事項</span><span class="sxs-lookup"><span data-stu-id="8d280-153">Ask yourself</span></span> | <span data-ttu-id="8d280-154">アクション</span><span class="sxs-lookup"><span data-stu-id="8d280-154">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="8d280-155">組織でカスタムのボットを許可しますか?</span><span class="sxs-lookup"><span data-stu-id="8d280-155">Do I want to allow custom bots in my organization?</span></span>|<span data-ttu-id="8d280-156">ボットの追加の詳細については、「[Microsoft Teams でプライベートのチャットやチャネルのボットを追加する](add-bots.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-156">For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](add-bots.md).</span></span> <span data-ttu-id="8d280-157">カスタムのボットをオンまたはオフにする方法の詳細については、「[Microsoft Teams でのアプリの管理設定](admin-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-157">For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="built-in-and-custom-tabs"></a><span data-ttu-id="8d280-158">組み込みタブとカスタム タブ</span><span class="sxs-lookup"><span data-stu-id="8d280-158">Built-in and custom tabs</span></span>

<span data-ttu-id="8d280-159">所有者とチーム メンバーは、チャネル、プライベート チャット、およびグループ チャットにタブを追加して、クラウド サービスの統合に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="8d280-159">Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services.</span></span> <span data-ttu-id="8d280-160">ユーザーが必要なデータや頻繁に使用するデータにアクセスしたり管理する際に役立つタブを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d280-160">Add tabs to help users access and manage the data they need or use the most.</span></span> <span data-ttu-id="8d280-161">チャネルには、[会話] のタブと [ファイル] のタブが既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="8d280-161">In channels, the Conversations and Files tabs are created by default.</span></span> <span data-ttu-id="8d280-162">すべてのプライベート チャットには、[会話]、[ファイル]、[組織]、および [アクティビティ] のタブが既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="8d280-162">In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default.</span></span> <span data-ttu-id="8d280-163">これらの組み込みタブに加えて、カスタムのタブを設計して追加できます。</span><span class="sxs-lookup"><span data-stu-id="8d280-163">In addition to these built-in tabs, you can design and add custom tabs.</span></span> <span data-ttu-id="8d280-164">組織に対して Teams アプリをオンまたはオフにする方法の詳細については、「[Teams でのアプリの管理設定](admin-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-164">To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).</span></span>

| <span data-ttu-id="8d280-165">確認事項</span><span class="sxs-lookup"><span data-stu-id="8d280-165">Ask yourself</span></span> | <span data-ttu-id="8d280-166">アクション</span><span class="sxs-lookup"><span data-stu-id="8d280-166">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="8d280-167">組織でカスタムのタブを許可しますか?</span><span class="sxs-lookup"><span data-stu-id="8d280-167">Do I want to allow custom tabs in my organization?</span></span>|<span data-ttu-id="8d280-168">詳細については、「[Teams の組み込みタブとカスタム タブを使用する](built-in-custom-tabs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-168">For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).</span></span>|
|||

### <a name="custom-connectors"></a><span data-ttu-id="8d280-169">カスタム コネクタ</span><span class="sxs-lookup"><span data-stu-id="8d280-169">Custom connectors</span></span>

<span data-ttu-id="8d280-170">コネクタにより、頻繁に使用するサービスからコンテンツと更新内容がチャネルに直接配信されるため、チームは最新の状態に保たれます。</span><span class="sxs-lookup"><span data-stu-id="8d280-170">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel.</span></span> <span data-ttu-id="8d280-171">コネクタを使用すると、Teams ユーザーはTwitter、Trello、Wunderlist、GitHub、Azure DevOps ServicesなどのポピュラーなサービスからTeams チャットで最新情報を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="8d280-171">With connectors, your Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.</span></span>

| <span data-ttu-id="8d280-172">確認事項</span><span class="sxs-lookup"><span data-stu-id="8d280-172">Ask yourself</span></span> | <span data-ttu-id="8d280-173">アクション</span><span class="sxs-lookup"><span data-stu-id="8d280-173">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="8d280-174">ユーザーにカスタム コネクタの作成を許可するか?</span><span class="sxs-lookup"><span data-stu-id="8d280-174">Do I want to allow users to create custom connectors?</span></span>|<span data-ttu-id="8d280-175">詳細については、「[Teams でカスタム コネクタを使用する](office-365-custom-connectors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-175">For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).</span></span>|
|||

## <a name="additional-deployment-decisions"></a><span data-ttu-id="8d280-176">その他の展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="8d280-176">Additional deployment decisions</span></span>

<span data-ttu-id="8d280-177">次の設定は、組織のニーズと構成に基づいて変更できます。</span><span class="sxs-lookup"><span data-stu-id="8d280-177">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="activity-reports"></a><span data-ttu-id="8d280-178">アクティビティ レポート</span><span class="sxs-lookup"><span data-stu-id="8d280-178">Activity reports</span></span>

<span data-ttu-id="8d280-179">アクティビティ レポートを使用すると、組織内のユーザーがどのように Teams を使用しているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8d280-179">You can use activity reports to see how users in your organization are using Teams.</span></span> <span data-ttu-id="8d280-180">たとえば、まだ Teams を使用していないユーザーがいる場合、そのユーザーは使用の開始方法を知らないか、Teams を使用して生産性と共同作業の効率を向上させる方法を理解していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d280-180">For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative.</span></span> <span data-ttu-id="8d280-181">組織では、アクティビティ レポートを使用して、トレーニングとコミュニケーションに関する優先項目を判断できます。</span><span class="sxs-lookup"><span data-stu-id="8d280-181">Your organization can use the activity reports to decide where to prioritize training and communication efforts.</span></span> <span data-ttu-id="8d280-182">アクティビティ レポートを表示するには、Microsoft 365 または Office 365 の全体管理者、Teams のサービス管理者、または Skype for Business の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d280-182">To view activity reports, you must be a global admin in Microsoft 365 or Office 365, Teams service admin, or Skype for Business admin.</span></span>

| <span data-ttu-id="8d280-183">確認事項</span><span class="sxs-lookup"><span data-stu-id="8d280-183">Ask yourself</span></span> | <span data-ttu-id="8d280-184">アクション</span><span class="sxs-lookup"><span data-stu-id="8d280-184">Action</span></span> |
|--------------|--------|
| <br><span data-ttu-id="8d280-185">誰がアクティビティ レポートの確認を必要としていて、レポートを表示するための適切なアクセス許可が割り当てられているか?</span><span class="sxs-lookup"><span data-stu-id="8d280-185">Who needs to see the activity reports, and do they have the correct permissions to view them?</span></span> |<ul><li><span data-ttu-id="8d280-186">ユーザーに管理者の役割を割り当てたくない場合は、[レポート閲覧者の役割を割り当てる](teams-activity-reports.md#reports-reader-role)ことができます。</span><span class="sxs-lookup"><span data-stu-id="8d280-186">If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="8d280-187">Azure Active Directory で管理者の役割を割り当てる方法の詳細については、「[役割とアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」および「[役割の表示と割り当て](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-187">See [Roles and permissions](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</span></span></li></ul> |
|||

### <a name="app-templates"></a><span data-ttu-id="8d280-188">アプリ テンプレート</span><span class="sxs-lookup"><span data-stu-id="8d280-188">App templates</span></span>

<span data-ttu-id="8d280-189">アプリ テンプレートは、Microsoft Teams 用の実稼働可能なアプリです。コミュニティ主導型、オープン ソースで、GitHub で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8d280-189">App templates are production-ready apps for Microsoft Teams that are community driven, open-source, and available on GitHub.</span></span> <span data-ttu-id="8d280-190">各アプリには、組織用に展開してインストールするための詳細な手順が記載されています。使用可能な状態でアプリが提供されているため、すぐにインストールして使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="8d280-190">Each contains detailed instructions for deploying and installing that app for your organization, providing a ready-to-use app that you can install and begin using immediately.</span></span> <span data-ttu-id="8d280-191">完全なソースコードも利用できるので、詳細を調べたり、コードをフォークして特定のニーズに合わせて変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="8d280-191">The complete source code is available as well, so you can explore it in detail, or fork the code and alter it to meet your specific needs.</span></span>

| <span data-ttu-id="8d280-192">確認事項</span><span class="sxs-lookup"><span data-stu-id="8d280-192">Ask yourself</span></span> | <span data-ttu-id="8d280-193">操作</span><span class="sxs-lookup"><span data-stu-id="8d280-193">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="8d280-194">アイスブレーカーなどの Teams アプリ テンプレートをインストールしますか?</span><span class="sxs-lookup"><span data-stu-id="8d280-194">Do I want to install any Teams app templates, such as Icebreaker?</span></span> |<span data-ttu-id="8d280-195">詳細については、「[Microsoft Teams 用のアプリ テンプレート](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d280-195">To learn more, read [App templates for Teams](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||





