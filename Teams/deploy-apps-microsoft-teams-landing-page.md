---
title: Microsoft Teams のアプリ、ボット、およびコネクタ
description: ここに示す展開リソースを使用して、Microsoft のアプリを展開してください。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/28/2019
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7ccc2c489d4423b906aec92dcb594f82a380e40
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460797"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a><span data-ttu-id="b8cf6-103">Microsoft Teams のアプリ、ボット、およびコネクタ</span><span class="sxs-lookup"><span data-stu-id="b8cf6-103">Apps, bots, & connectors in Microsoft Teams</span></span>

<span data-ttu-id="b8cf6-104">アプリを使用すると、お気に入りのサービスからコンテンツを見つけて、そのコンテンツをすぐに Teams で共有できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-104">Apps let you find content from your favorite services and share it right in Teams.</span></span> <span data-ttu-id="b8cf6-105">チャネルの上部にサービスを固定したり、ボットとチャットしたり、タスクを共有および割り当てるときなどに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-105">They help you do things such as pin services at the top of a channel, chat with bots, or share and assign tasks.</span></span> <span data-ttu-id="b8cf6-106">詳細については、「[Teams のアプリの概要](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-106">To learn more, read [Overview of apps in Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).</span></span>

<span data-ttu-id="b8cf6-107">Teams の初期展開時に、おすすめのアプリ (Planner など) を含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-107">We recommend that you include our featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="b8cf6-108">Teams 導入の進行に応じて、その他のアプリ、ボット、およびコネクタを追加してください。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-108">Add other apps, bots, & connectors as you drive Teams adoption.</span></span>



## <a name="apps-deployment-decisions"></a><span data-ttu-id="b8cf6-109">アプリの展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="b8cf6-109">Apps deployment decisions</span></span>

<span data-ttu-id="b8cf6-110">Teams は、すぐに使用できる優れたコラボレーション エクスペリエンスを組織に提供します。既定の設定は、ほとんどの組織の業務に通用します。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-110">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them.</span></span> <span data-ttu-id="b8cf6-111">この記事では、自分の組織のプロファイルとビジネスの要件に基づいて既定の設定に変更が必要かどうかを判断する際のガイダンスを示し、それぞれの変更の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-111">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="b8cf6-112">設定については 2 つのグループに分けて、まず、[変更する可能性が高いと考えられる](#core-deployment-decisions)中心的な部分について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-112">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="b8cf6-113">2 番目のグループには、組織のニーズ応じた構成が求められる可能性がある[追加の設定](#additional-deployment-decisions)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-113">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="b8cf6-114">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="b8cf6-114">Core deployment decisions</span></span>

<span data-ttu-id="b8cf6-115">次に示すアプリの設定は、ほとんどの組織が変更を必要とするものです (Teams の既定の設定では適切に動作しない場合)。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-115">These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).</span></span>

### <a name="app-availability-settings"></a><span data-ttu-id="b8cf6-116">アプリの可用性の設定</span><span class="sxs-lookup"><span data-stu-id="b8cf6-116">App availability settings</span></span> 

<span data-ttu-id="b8cf6-117">Teams には、複数のファースト パーティ (Microsoft 提供) のアプリとサード パーティ製アプリがあり、ユーザー参加の促進、生産性のサポート、および一般に使用されるビジネス サービスの Teams への統合のために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-117">Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="b8cf6-118">Teams Store からアプリを入手してください。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-118">Get apps from the Teams Store.</span></span> <span data-ttu-id="b8cf6-119">既定では、すべてのアプリ ([Teams Store 承認プロセス](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)で提出した外部アプリを含む) が、すべてのユーザーに対してオンにされています。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-119">By default, all apps, including external apps that you've submitted via the [Teams Store approval process](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users.</span></span> <span data-ttu-id="b8cf6-120">たとえば、ユーザーは Planner アプリを使用して Teams のチーム タスクを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-120">For example, users can use the Planner app to build and manage team tasks in Teams.</span></span>

<span data-ttu-id="b8cf6-121">既定では、すべての Microsoft 提供のアプリと外部アプリが使用可能になっていて、個別のアプリをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-121">By default, all Microsoft-provided and external apps are available, and you can turn individual apps on or off.</span></span> <span data-ttu-id="b8cf6-122">すべての外部アプリを組織全体でオンまたはオフにできるグローバル設定があります。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-122">There's a global setting that lets you turn all external apps on or off for your entire organization.</span></span>

| <span data-ttu-id="b8cf6-123">確認事項</span><span class="sxs-lookup"><span data-stu-id="b8cf6-123">Ask yourself</span></span> | <span data-ttu-id="b8cf6-124">アクション</span><span class="sxs-lookup"><span data-stu-id="b8cf6-124">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="b8cf6-125">既定の Teams アプリの設定を変更するか?</span><span class="sxs-lookup"><span data-stu-id="b8cf6-125">Will you change the default Teams apps settings?</span></span> | <span data-ttu-id="b8cf6-126">外部アプリの可用性を構成する方法の詳細については、「[Microsoft Teams でのアプリの管理設定](admin-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-126">For more information about configuring the availability of external apps, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="app-permissions-and-other-considerations"></a><span data-ttu-id="b8cf6-127">アプリのアクセス許可とその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="b8cf6-127">App permissions and other considerations</span></span>

<span data-ttu-id="b8cf6-128">アプリはユーザーが同意し、管理者または IT 担当者がポリシーによって管理します。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-128">Apps are consented to by users and managed by the admin or IT pro through policies.</span></span> <span data-ttu-id="b8cf6-129">ただし、ほとんどの場合、アプリのアクセス許可とリスク プロファイルはアプリ自体で定義されています。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-129">However, for the most part, an app's permissions and risk profile are defined in the app itself.</span></span> 

| <span data-ttu-id="b8cf6-130">確認事項</span><span class="sxs-lookup"><span data-stu-id="b8cf6-130">Ask yourself</span></span> | <span data-ttu-id="b8cf6-131">アクション</span><span class="sxs-lookup"><span data-stu-id="b8cf6-131">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="b8cf6-132">どのアプリへのアクセスを許可するか?</span><span class="sxs-lookup"><span data-stu-id="b8cf6-132">Which apps do I want to allow access to?</span></span> <span data-ttu-id="b8cf6-133">どのアプリへのアクセスを禁止するか?</span><span class="sxs-lookup"><span data-stu-id="b8cf6-133">Which ones do I not want to allow access to?</span></span>  | <ul><li><span data-ttu-id="b8cf6-134">アプリ、ボット、タブ、またはコネクタへのアクセスを許可する際の考慮事項に関するリストについては、「[Microsoft Teams アプリのアクセス許可と考慮事項](app-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-134">See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</span></span></li><li><span data-ttu-id="b8cf6-135">組織内のユーザーがアプリを使用できるようにする方法の詳細については、「[Teams テナントのアプリ カタログでアプリを公開する](tenant-apps-catalog-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-135">See [Publish apps in the Teams tenant apps catalog](tenant-apps-catalog-teams.md) for information about making an app available to users in your organization.</span></span></li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a><span data-ttu-id="b8cf6-136">プライベート チャットおよびチャネルのボット</span><span class="sxs-lookup"><span data-stu-id="b8cf6-136">Bots for private chats and channels</span></span>

<span data-ttu-id="b8cf6-137">ボットとは、クエリに応答したり、ユーザーが興味を持っている詳細や常に情報を得ていたい詳細について更新や通知を行う自動プログラムのことです。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-137">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="b8cf6-138">ボットを使用すると、ユーザーは Teams チャットでのタスク管理、スケジュール設定、投票などのクラウド サービスと対話できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-138">Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat.</span></span> <span data-ttu-id="b8cf6-139">Teams は、プライベートのチャットおよびチャネルでボットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-139">Teams supports bots in private chats and channels.</span></span> <span data-ttu-id="b8cf6-140">管理者は、Office 365 テナントでのボットの使用を許可するかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-140">Administrators can control whether the use of bots is allowed in an Office 365 tenant.</span></span>

| <span data-ttu-id="b8cf6-141">確認事項</span><span class="sxs-lookup"><span data-stu-id="b8cf6-141">Ask yourself</span></span> | <span data-ttu-id="b8cf6-142">アクション</span><span class="sxs-lookup"><span data-stu-id="b8cf6-142">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="b8cf6-143">Office 365 テナントでカスタムのボットを許可するか?</span><span class="sxs-lookup"><span data-stu-id="b8cf6-143">Do I want to allow custom bots in my Office 365 tenant?</span></span>|<span data-ttu-id="b8cf6-144">ボットの追加の詳細については、「[Microsoft Teams でプライベートのチャットやチャネルのボットを追加する](add-bots.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-144">For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](add-bots.md).</span></span> <span data-ttu-id="b8cf6-145">カスタムのボットをオンまたはオフにする方法の詳細については、「[Microsoft Teams でのアプリの管理設定](admin-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-145">For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="built-in-and-custom-tabs"></a><span data-ttu-id="b8cf6-146">組み込みタブとカスタム タブ</span><span class="sxs-lookup"><span data-stu-id="b8cf6-146">Built-in and custom tabs</span></span>

<span data-ttu-id="b8cf6-147">所有者とチーム メンバーは、チャネル、プライベート チャット、およびグループ チャットにタブを追加して、クラウド サービスの統合に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-147">Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services.</span></span> <span data-ttu-id="b8cf6-148">ユーザーが必要なデータや頻繁に使用するデータにアクセスしたり管理する際に役立つタブを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-148">Add tabs to help users access and manage the data they need or use the most.</span></span> <span data-ttu-id="b8cf6-149">チャネルには、[会話] のタブと [ファイル] のタブが既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-149">In channels, the Conversations and Files tabs are created by default.</span></span> <span data-ttu-id="b8cf6-150">すべてのプライベート チャットには、[会話]、[ファイル]、[組織]、および [アクティビティ] のタブが既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-150">In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default.</span></span> <span data-ttu-id="b8cf6-151">これらの組み込みタブに加えて、カスタムのタブを設計して追加できます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-151">In addition to these built-in tabs, you can design and add custom tabs.</span></span> <span data-ttu-id="b8cf6-152">組織に対して Teams アプリをオンまたはオフにする方法の詳細については、「[Teams でのアプリの管理設定](admin-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-152">To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).</span></span>

| <span data-ttu-id="b8cf6-153">確認事項</span><span class="sxs-lookup"><span data-stu-id="b8cf6-153">Ask yourself</span></span> | <span data-ttu-id="b8cf6-154">アクション</span><span class="sxs-lookup"><span data-stu-id="b8cf6-154">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="b8cf6-155">Office 365 テナントでカスタムのタブを許可するか?</span><span class="sxs-lookup"><span data-stu-id="b8cf6-155">Do I want to allow custom tabs in my Office 365 tenant?</span></span>|<span data-ttu-id="b8cf6-156">詳細については、「[Teams の組み込みタブとカスタム タブを使用する](built-in-custom-tabs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-156">For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).</span></span>|
|||

### <a name="office-365-and-custom-connectors"></a><span data-ttu-id="b8cf6-157">Office 365 コネクタとカスタム コネクタ</span><span class="sxs-lookup"><span data-stu-id="b8cf6-157">Office 365 and custom connectors</span></span>

<span data-ttu-id="b8cf6-158">コネクタにより、頻繁に使用するサービスからコンテンツと更新内容がチャネルに直接配信されるため、チームは最新の状態に保たれます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-158">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel.</span></span> <span data-ttu-id="b8cf6-159">コネクタを使用すると、Teams のユーザーは大手のサービス (Twitter、Trello、Wunderlist、GitHub、Visual Studio Team Services (VSTS) など) からの更新内容を Teams のチャットで受信できます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-159">With connectors, your Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Visual Studio Team Services (VSTS) in their Teams chats.</span></span>

| <span data-ttu-id="b8cf6-160">確認事項</span><span class="sxs-lookup"><span data-stu-id="b8cf6-160">Ask yourself</span></span> | <span data-ttu-id="b8cf6-161">アクション</span><span class="sxs-lookup"><span data-stu-id="b8cf6-161">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="b8cf6-162">ユーザーにカスタム コネクタの作成を許可するか?</span><span class="sxs-lookup"><span data-stu-id="b8cf6-162">Do I want to allow users to create custom connectors?</span></span>|<span data-ttu-id="b8cf6-163">詳細については、「[Office 365 コネクタとカスタム コネクタ](office-365-custom-connectors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-163">For more information, see [Use Office 365 and custom connectors in Teams](office-365-custom-connectors.md).</span></span>|
|||

## <a name="additional-deployment-decisions"></a><span data-ttu-id="b8cf6-164">その他の展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="b8cf6-164">Additional deployment decisions</span></span>

<span data-ttu-id="b8cf6-165">次の設定は、組織のニーズと構成に基づいて変更できます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-165">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="activity-reports"></a><span data-ttu-id="b8cf6-166">アクティビティ レポート</span><span class="sxs-lookup"><span data-stu-id="b8cf6-166">Activity reports</span></span>

<span data-ttu-id="b8cf6-167">アクティビティ レポートを使用すると、組織内のユーザーがどのように Teams を使用しているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-167">You can use activity reports to see how users in your organization are using Teams.</span></span> <span data-ttu-id="b8cf6-168">たとえば、まだ Teams を使用していないユーザーがいる場合、そのユーザーは使用の開始方法を知らないか、Teams を使用して生産性と共同作業の効率を向上させる方法を理解していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-168">For example, if some don’t use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative.</span></span> <span data-ttu-id="b8cf6-169">組織では、アクティビティ レポートを使用して、トレーニングとコミュニケーションに関する優先項目を判断できます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-169">Your organization can use the activity reports to decide where to prioritize training and communication efforts.</span></span> <span data-ttu-id="b8cf6-170">アクティビティ レポートを表示するには、Office 365 の全体管理者、Teams のサービス管理者、または Skype for Business の管理者であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-170">To view activity reports, you must be a global admin in Office 365, Teams service admin, or Skype for Business admin.</span></span>

| <span data-ttu-id="b8cf6-171">確認事項</span><span class="sxs-lookup"><span data-stu-id="b8cf6-171">Ask yourself</span></span> | <span data-ttu-id="b8cf6-172">アクション</span><span class="sxs-lookup"><span data-stu-id="b8cf6-172">Action</span></span> |
|--------------|--------|
| <br><span data-ttu-id="b8cf6-173">誰がアクティビティ レポートの確認を必要としていて、レポートを表示するための適切なアクセス許可が割り当てられているか?</span><span class="sxs-lookup"><span data-stu-id="b8cf6-173">Who needs to see the activity reports, and do they have the correct permissions to view them?</span></span> |<ul><li><span data-ttu-id="b8cf6-174">ユーザーに管理者の役割を割り当てたくない場合は、[レポート閲覧者の役割を割り当てる](teams-activity-reports.md#reports-reader-role)ことができます。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-174">If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="b8cf6-175">Azure Active Directory で管理者の役割を割り当てる方法の詳細については、「[役割とアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」および「[役割の表示と割り当て](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-175">See [Roles and permissions](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</span></span></li></ul> |
|||


## <a name="next-steps"></a><span data-ttu-id="b8cf6-176">次のステップ</span><span class="sxs-lookup"><span data-stu-id="b8cf6-176">Next steps</span></span>
- <span data-ttu-id="b8cf6-177">おすすめのアプリ (Planner など) の[導入を推進](adopt-microsoft-teams-landing-page.md)する。</span><span class="sxs-lookup"><span data-stu-id="b8cf6-177">[Drive adoption](adopt-microsoft-teams-landing-page.md) of featured apps, such as Planner.</span></span>
- [<span data-ttu-id="b8cf6-178">ミーティングと会議を展開する</span><span class="sxs-lookup"><span data-stu-id="b8cf6-178">Roll out meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="b8cf6-179">クラウド ボイスを展開する</span><span class="sxs-lookup"><span data-stu-id="b8cf6-179">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)


