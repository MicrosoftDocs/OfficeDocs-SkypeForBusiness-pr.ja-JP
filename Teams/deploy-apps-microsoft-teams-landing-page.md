---
title: Microsoft Teams のアプリ、ボット、およびコネクタ
ms.reviewer: ''
description: アプリ、ボット、コネクタについて、および組織のプロファイルとビジネスの要件に基づいてどれを Microsoft Teams に展開するかについて説明します。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: admin
ms.date: 01/28/2019
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
ms.openlocfilehash: bf2e7304fc452478da57bad003fffc5193353c8b
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085823"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a><span data-ttu-id="5d336-103">Microsoft Teams のアプリ、ボット、およびコネクタ</span><span class="sxs-lookup"><span data-stu-id="5d336-103">Apps, bots, & connectors in Microsoft Teams</span></span>

<span data-ttu-id="5d336-104">アプリを使用すると、お気に入りのサービスからコンテンツを見つけて、そのコンテンツをすぐに Teams で共有できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5d336-104">Apps let you find content from your favorite services and share it right in Teams.</span></span> <span data-ttu-id="5d336-105">チャネルの上部にサービスを固定したり、ボットとチャットしたり、タスクを共有および割り当てるときなどに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5d336-105">They help you do things such as pin services at the top of a channel, chat with bots, or share and assign tasks.</span></span> <span data-ttu-id="5d336-106">詳細については、「[Teams のアプリの概要](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d336-106">To learn more, read [Overview of apps in Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).</span></span>

<span data-ttu-id="5d336-107">Teams の初期展開時に、おすすめのアプリ (Planner など) を含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5d336-107">We recommend that you include our featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="5d336-108">Teams 導入の進行に応じて、その他のアプリ、ボット、およびコネクタを追加してください。</span><span class="sxs-lookup"><span data-stu-id="5d336-108">Add other apps, bots, & connectors as you drive Teams adoption.</span></span>

<span data-ttu-id="5d336-109">また、独自のカスタム アプリを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d336-109">You also have the option of creating your own custom apps.</span></span> <span data-ttu-id="5d336-110">詳細については、「[開発者向けドキュメント](/microsoftteams/platform/overview)」を参照してください:</span><span class="sxs-lookup"><span data-stu-id="5d336-110">See our [developer documentation](/microsoftteams/platform/overview) for more information.</span></span>

## <a name="apps-deployment-decisions"></a><span data-ttu-id="5d336-111">アプリの展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="5d336-111">Apps deployment decisions</span></span>

<span data-ttu-id="5d336-112">Teams は、すぐに使用できる優れたコラボレーション エクスペリエンスを組織に提供します。既定の設定は、ほとんどの組織の業務に通用します。</span><span class="sxs-lookup"><span data-stu-id="5d336-112">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them.</span></span> <span data-ttu-id="5d336-113">この記事では、自分の組織のプロファイルとビジネスの要件に基づいて既定の設定に変更が必要かどうかを判断する際のガイダンスを示し、それぞれの変更の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="5d336-113">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="5d336-114">設定については 2 つのグループに分けて、まず、[変更する可能性が高いと考えられる](#core-deployment-decisions)中心的な部分について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d336-114">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="5d336-115">2 番目のグループには、組織のニーズ応じた構成が求められる可能性がある[追加の設定](#additional-deployment-decisions)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5d336-115">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="5d336-116">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="5d336-116">Core deployment decisions</span></span>

<span data-ttu-id="5d336-117">次に示すアプリの設定は、ほとんどの組織が変更を必要とするものです (Teams の既定の設定では適切に動作しない場合)。</span><span class="sxs-lookup"><span data-stu-id="5d336-117">These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).</span></span>

### <a name="app-availability-settings"></a><span data-ttu-id="5d336-118">アプリの可用性の設定</span><span class="sxs-lookup"><span data-stu-id="5d336-118">App availability settings</span></span> 

<span data-ttu-id="5d336-119">Teams には、Microsoft とサード パーティが公開する複数のアプリがあり、ユーザー参加の促進、生産性のサポート、および一般に使用されるビジネス サービスの Teams への統合のために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d336-119">Teams provides a number of apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="5d336-120">Teams Store からアプリを入手してください。</span><span class="sxs-lookup"><span data-stu-id="5d336-120">Get apps from the Teams Store.</span></span> <span data-ttu-id="5d336-121">既定では、すべてのアプリ ([Teams Store 承認プロセス](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)で提出したカスタム アプリを含む) が、すべてのユーザーに対してオンにされています。</span><span class="sxs-lookup"><span data-stu-id="5d336-121">By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users.</span></span> <span data-ttu-id="5d336-122">たとえば、ユーザーは Planner アプリを使用して Teams のチーム タスクを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="5d336-122">For example, users can use the Planner app to build and manage team tasks in Teams.</span></span>

<span data-ttu-id="5d336-123">既定では、すべての Microsoft 提供のアプリとカスタム アプリが使用可能になっていて、個別のアプリをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d336-123">By default, all Microsoft-provided and custom apps are available, and you can turn individual apps on or off.</span></span> <span data-ttu-id="5d336-124">すべてのカスタム アプリを組織全体でオンまたはオフにできる組織全体の設定があります。</span><span class="sxs-lookup"><span data-stu-id="5d336-124">There's an org-wide setting that lets you turn all custom apps on or off for your entire organization.</span></span>

| <span data-ttu-id="5d336-125">確認事項</span><span class="sxs-lookup"><span data-stu-id="5d336-125">Ask yourself</span></span> | <span data-ttu-id="5d336-126">アクション</span><span class="sxs-lookup"><span data-stu-id="5d336-126">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="5d336-127">既定の Teams アプリの設定を変更するか?</span><span class="sxs-lookup"><span data-stu-id="5d336-127">Will you change the default Teams apps settings?</span></span> | <span data-ttu-id="5d336-128">組織内のアプリを管理するために使用できるポリシーと設定の詳細については、「[Microsoft Teams でのアプリの管理設定](admin-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d336-128">For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="app-permissions-and-other-considerations"></a><span data-ttu-id="5d336-129">アプリのアクセス許可とその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="5d336-129">App permissions and other considerations</span></span>

<span data-ttu-id="5d336-130">アプリはユーザーが同意し、管理者または IT 担当者がポリシーによって管理します。</span><span class="sxs-lookup"><span data-stu-id="5d336-130">Apps are consented to by users and managed by the admin or IT pro through policies.</span></span> <span data-ttu-id="5d336-131">ただし、ほとんどの場合、アプリのアクセス許可とリスク プロファイルはアプリ自体で定義されています。</span><span class="sxs-lookup"><span data-stu-id="5d336-131">However, for the most part, an app's permissions and risk profile are defined in the app itself.</span></span> 

| <span data-ttu-id="5d336-132">確認事項</span><span class="sxs-lookup"><span data-stu-id="5d336-132">Ask yourself</span></span> | <span data-ttu-id="5d336-133">アクション</span><span class="sxs-lookup"><span data-stu-id="5d336-133">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="5d336-134">どのアプリへのアクセスを許可するか?</span><span class="sxs-lookup"><span data-stu-id="5d336-134">Which apps do I want to allow access to?</span></span> <span data-ttu-id="5d336-135">どのアプリへのアクセスを禁止するか?</span><span class="sxs-lookup"><span data-stu-id="5d336-135">Which ones do I not want to allow access to?</span></span>  | <ul><li><span data-ttu-id="5d336-136">アプリ、ボット、タブ、またはコネクタへのアクセスを許可する際の考慮事項に関するリストについては、「[Microsoft Teams アプリのアクセス許可と考慮事項](app-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d336-136">See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</span></span></li><li><span data-ttu-id="5d336-137">組織内のユーザーがアプリを使用できるようにする方法の詳細については、「[Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d336-137">See [Manage your apps in the Microsoft Teams admin center](manage-apps.md) for information about making an app available to users in your organization.</span></span></li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a><span data-ttu-id="5d336-138">プライベート チャットおよびチャネルのボット</span><span class="sxs-lookup"><span data-stu-id="5d336-138">Bots for private chats and channels</span></span>

<span data-ttu-id="5d336-139">ボットとは、クエリに応答したり、ユーザーが興味を持っている詳細や常に情報を得ていたい詳細について更新や通知を行う自動プログラムのことです。</span><span class="sxs-lookup"><span data-stu-id="5d336-139">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="5d336-140">ボットを使用すると、ユーザーは Teams チャットでのタスク管理、スケジュール設定、投票などのクラウド サービスと対話できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5d336-140">Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat.</span></span> <span data-ttu-id="5d336-141">Teams は、プライベートのチャットおよびチャネルでボットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5d336-141">Teams supports bots in private chats and channels.</span></span> <span data-ttu-id="5d336-142">管理者は、Microsoft 365 組織または Office 365 組織でのボットの使用を許可するかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="5d336-142">Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.</span></span>

| <span data-ttu-id="5d336-143">確認事項</span><span class="sxs-lookup"><span data-stu-id="5d336-143">Ask yourself</span></span> | <span data-ttu-id="5d336-144">アクション</span><span class="sxs-lookup"><span data-stu-id="5d336-144">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="5d336-145">組織でカスタムのボットを許可しますか?</span><span class="sxs-lookup"><span data-stu-id="5d336-145">Do I want to allow custom bots in my organization?</span></span>|<span data-ttu-id="5d336-146">ボットの追加の詳細については、「[Microsoft Teams でプライベートのチャットやチャネルのボットを追加する](add-bots.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d336-146">For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](add-bots.md).</span></span> <span data-ttu-id="5d336-147">カスタムのボットをオンまたはオフにする方法の詳細については、「[Microsoft Teams でのアプリの管理設定](admin-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d336-147">For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="built-in-and-custom-tabs"></a><span data-ttu-id="5d336-148">組み込みタブとカスタム タブ</span><span class="sxs-lookup"><span data-stu-id="5d336-148">Built-in and custom tabs</span></span>

<span data-ttu-id="5d336-149">所有者とチーム メンバーは、チャネル、プライベート チャット、およびグループ チャットにタブを追加して、クラウド サービスの統合に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="5d336-149">Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services.</span></span> <span data-ttu-id="5d336-150">ユーザーが必要なデータや頻繁に使用するデータにアクセスしたり管理する際に役立つタブを追加します。</span><span class="sxs-lookup"><span data-stu-id="5d336-150">Add tabs to help users access and manage the data they need or use the most.</span></span> <span data-ttu-id="5d336-151">チャネルには、[会話] のタブと [ファイル] のタブが既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="5d336-151">In channels, the Conversations and Files tabs are created by default.</span></span> <span data-ttu-id="5d336-152">すべてのプライベート チャットには、[会話]、[ファイル]、[組織]、および [アクティビティ] のタブが既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="5d336-152">In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default.</span></span> <span data-ttu-id="5d336-153">これらの組み込みタブに加えて、カスタムのタブを設計して追加できます。</span><span class="sxs-lookup"><span data-stu-id="5d336-153">In addition to these built-in tabs, you can design and add custom tabs.</span></span> <span data-ttu-id="5d336-154">組織に対して Teams アプリをオンまたはオフにする方法の詳細については、「[Teams でのアプリの管理設定](admin-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d336-154">To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).</span></span>

| <span data-ttu-id="5d336-155">確認事項</span><span class="sxs-lookup"><span data-stu-id="5d336-155">Ask yourself</span></span> | <span data-ttu-id="5d336-156">アクション</span><span class="sxs-lookup"><span data-stu-id="5d336-156">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="5d336-157">組織でカスタムのタブを許可しますか?</span><span class="sxs-lookup"><span data-stu-id="5d336-157">Do I want to allow custom tabs in my organization?</span></span>|<span data-ttu-id="5d336-158">詳細については、「[Teams の組み込みタブとカスタム タブを使用する](built-in-custom-tabs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d336-158">For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).</span></span>|
|||

### <a name="custom-connectors"></a><span data-ttu-id="5d336-159">カスタム コネクタ</span><span class="sxs-lookup"><span data-stu-id="5d336-159">Custom connectors</span></span>

<span data-ttu-id="5d336-160">コネクタにより、頻繁に使用するサービスからコンテンツと更新内容がチャネルに直接配信されるため、チームは最新の状態に保たれます。</span><span class="sxs-lookup"><span data-stu-id="5d336-160">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel.</span></span> <span data-ttu-id="5d336-161">コネクタを使用すると、Teams ユーザーはTwitter、Trello、Wunderlist、GitHub、Azure DevOps ServicesなどのポピュラーなサービスからTeams チャットで最新情報を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="5d336-161">With connectors, your Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.</span></span>

| <span data-ttu-id="5d336-162">確認事項</span><span class="sxs-lookup"><span data-stu-id="5d336-162">Ask yourself</span></span> | <span data-ttu-id="5d336-163">アクション</span><span class="sxs-lookup"><span data-stu-id="5d336-163">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="5d336-164">ユーザーにカスタム コネクタの作成を許可するか?</span><span class="sxs-lookup"><span data-stu-id="5d336-164">Do I want to allow users to create custom connectors?</span></span>|<span data-ttu-id="5d336-165">詳細については、「[Teams でカスタム コネクタを使用する](office-365-custom-connectors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d336-165">For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).</span></span>|
|||

## <a name="additional-deployment-decisions"></a><span data-ttu-id="5d336-166">その他の展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="5d336-166">Additional deployment decisions</span></span>

<span data-ttu-id="5d336-167">次の設定は、組織のニーズと構成に基づいて変更できます。</span><span class="sxs-lookup"><span data-stu-id="5d336-167">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="activity-reports"></a><span data-ttu-id="5d336-168">アクティビティ レポート</span><span class="sxs-lookup"><span data-stu-id="5d336-168">Activity reports</span></span>

<span data-ttu-id="5d336-169">アクティビティ レポートを使用すると、組織内のユーザーがどのように Teams を使用しているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5d336-169">You can use activity reports to see how users in your organization are using Teams.</span></span> <span data-ttu-id="5d336-170">たとえば、まだ Teams を使用していないユーザーがいる場合、そのユーザーは使用の開始方法を知らないか、Teams を使用して生産性と共同作業の効率を向上させる方法を理解していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d336-170">For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative.</span></span> <span data-ttu-id="5d336-171">組織では、アクティビティ レポートを使用して、トレーニングとコミュニケーションに関する優先項目を判断できます。</span><span class="sxs-lookup"><span data-stu-id="5d336-171">Your organization can use the activity reports to decide where to prioritize training and communication efforts.</span></span> <span data-ttu-id="5d336-172">アクティビティ レポートを表示するには、Microsoft 365 または Office 365 の全体管理者、Teams のサービス管理者、または Skype for Business の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d336-172">To view activity reports, you must be a global admin in Microsoft 365 or Office 365, Teams service admin, or Skype for Business admin.</span></span>

| <span data-ttu-id="5d336-173">確認事項</span><span class="sxs-lookup"><span data-stu-id="5d336-173">Ask yourself</span></span> | <span data-ttu-id="5d336-174">アクション</span><span class="sxs-lookup"><span data-stu-id="5d336-174">Action</span></span> |
|--------------|--------|
| <br><span data-ttu-id="5d336-175">誰がアクティビティ レポートの確認を必要としていて、レポートを表示するための適切なアクセス許可が割り当てられているか?</span><span class="sxs-lookup"><span data-stu-id="5d336-175">Who needs to see the activity reports, and do they have the correct permissions to view them?</span></span> |<ul><li><span data-ttu-id="5d336-176">ユーザーに管理者の役割を割り当てたくない場合は、[レポート閲覧者の役割を割り当てる](teams-activity-reports.md#reports-reader-role)ことができます。</span><span class="sxs-lookup"><span data-stu-id="5d336-176">If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="5d336-177">Azure Active Directory で管理者の役割を割り当てる方法の詳細については、「[役割とアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」および「[役割の表示と割り当て](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d336-177">See [Roles and permissions](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</span></span></li></ul> |
|||

### <a name="app-templates"></a><span data-ttu-id="5d336-178">アプリ テンプレート</span><span class="sxs-lookup"><span data-stu-id="5d336-178">App templates</span></span>

<span data-ttu-id="5d336-179">アプリ テンプレートは、Microsoft Teams 用の実稼働可能なアプリです。コミュニティ主導型、オープン ソースで、GitHub で利用できます。</span><span class="sxs-lookup"><span data-stu-id="5d336-179">App templates are production-ready apps for Microsoft Teams that are community driven, open-source, and available on GitHub.</span></span> <span data-ttu-id="5d336-180">各アプリには、組織用に展開してインストールするための詳細な手順が記載されています。使用可能な状態でアプリが提供されているため、すぐにインストールして使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="5d336-180">Each contains detailed instructions for deploying and installing that app for your organization, providing a ready-to-use app that you can install and begin using immediately.</span></span> <span data-ttu-id="5d336-181">完全なソースコードも利用できるので、詳細を調べたり、コードをフォークして特定のニーズに合わせて変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="5d336-181">The complete source code is available as well, so you can explore it in detail, or fork the code and alter it to meet your specific needs.</span></span>

| <span data-ttu-id="5d336-182">確認事項</span><span class="sxs-lookup"><span data-stu-id="5d336-182">Ask yourself</span></span> | <span data-ttu-id="5d336-183">操作</span><span class="sxs-lookup"><span data-stu-id="5d336-183">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="5d336-184">アイスブレーカーなどの Teams アプリ テンプレートをインストールしますか?</span><span class="sxs-lookup"><span data-stu-id="5d336-184">Do I want to install any Teams app templates, such as Icebreaker?</span></span> |<span data-ttu-id="5d336-185">詳細については、「[Microsoft Teams 用のアプリ テンプレート](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d336-185">To learn more, read [App templates for Teams](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||


## <a name="next-steps"></a><span data-ttu-id="5d336-186">次の手順</span><span class="sxs-lookup"><span data-stu-id="5d336-186">Next steps</span></span>
- <span data-ttu-id="5d336-187">おすすめのアプリ (Planner など) の[導入を推進](adopt-microsoft-teams-landing-page.md)する。</span><span class="sxs-lookup"><span data-stu-id="5d336-187">[Drive adoption](adopt-microsoft-teams-landing-page.md) of featured apps, such as Planner.</span></span>
- [<span data-ttu-id="5d336-188">ミーティングと会議を展開する</span><span class="sxs-lookup"><span data-stu-id="5d336-188">Roll out meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="5d336-189">クラウド ボイスを展開する</span><span class="sxs-lookup"><span data-stu-id="5d336-189">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)


