---
title: Microsoft Teams のチャット、チーム、チャネル、およびアプリ
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft Teams のチャット、チーム、アプリ、およびチャネルの Teams 設定を構成するための詳細なガイダンスが含まれています。
localization_priority: Priority
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
appliesto:
- Microsoft Teams
- seo-marvel-apr2020
- seo-marvel-may2020
ms.openlocfilehash: a5cf7c91ef3b0e91504753a1e04ed334f4132adc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094363"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a><span data-ttu-id="83bc9-103">Microsoft Teams のチャット、チーム、チャネル、およびアプリ</span><span class="sxs-lookup"><span data-stu-id="83bc9-103">Chat, teams, channels, & apps in Microsoft Teams</span></span>

<span data-ttu-id="83bc9-p101">Teams は、すぐに使用できる優れたコラボレーション エクスペリエンスを組織に提供します。ほとんどの組織は、既定の設定がよく機能することに気づいています。この記事は、組織のプロファイルとビジネス要件に基づいて、既定の設定のいずれかを変更するかどうかを決定する方法について、その後、各変更について説明します。設定を 2 つのグループに分割しました。まず、[変更を加える可能性が高い](#core-deployment-decisions)コアセットから始めます。2 番目のグループには、組織のニーズに基づいて構成する可能性のある[追加の設定](#additional-deployment-decisions)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p101">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="83bc9-108">開始するには、短い Teams チャット、チーム、およびチャネルのビデオをご覧ください (4:30 分):</span><span class="sxs-lookup"><span data-stu-id="83bc9-108">To get started, watch our short Teams chat, teams, and channels video (4:30 minutes):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

<span data-ttu-id="83bc9-109">*2019 年 11 月の新機能*</span><span class="sxs-lookup"><span data-stu-id="83bc9-109">*New in November 2019*</span></span>
 - <span data-ttu-id="83bc9-p102">これで、[Teams アドバイザー (プレビュー) を使用して、Microsoft Teams の展開に役立てる](use-advisor-teams-roll-out.md)ことができます。Teams アドバイザー (プレビュー) が、チームのロールアウトについて説明します。Microsoft 365 または Office 365 環境を評価し、チームを正常に展開する前に更新または変更する必要がある可能性のある最も一般的な構成を特定します。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p102">You can now [use Advisor for Teams (preview) to help you roll out Microsoft Teams](use-advisor-teams-roll-out.md). Advisor for Teams (preview) walks you through your Teams rollout. It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span>
 - <span data-ttu-id="83bc9-113">[IT 担当者向けの Microsoft Teams の基礎の YouTube チャネル](https://aka.ms/MicrosoftTeamsforIT)には、Teams の展開、構成、および管理の方法を示す短い (8 〜 10 分) ビデオが含まれています。</span><span class="sxs-lookup"><span data-stu-id="83bc9-113">[Microsoft Teams Essentials for IT YouTube channel](https://aka.ms/MicrosoftTeamsforIT), including short (8-10 minute) videos that show you how to roll out, configure, and manage Teams.</span></span>

> [!TIP]
> <span data-ttu-id="83bc9-p103">最初の Teams ロールアウトには、Planner などのおすすめのアプリを含めることをお勧めします。 Teams 導入の進行に応じて、その他の[アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)を追加してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p103">We recommend that you include our featured apps -- such as Planner -- in your initial Teams rollout. Add other [apps, bots, and connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>

 > [!Note]
 > <span data-ttu-id="83bc9-116">別のプラットフォームでの Teams の機能についての詳細は、 [プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-116">For details about Teams features on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="chat-deployment-prerequisites"></a><span data-ttu-id="83bc9-117">チャットの展開に関する前提条件</span><span class="sxs-lookup"><span data-stu-id="83bc9-117">Chat deployment prerequisites</span></span>

<span data-ttu-id="83bc9-p104">組織全体に Teams をロールアウトする前に、時間をかけてお使いの環境で Teams を使用する準備ができていることを確認してください。[組織のネットワークを Teams のために準備して](prepare-network.md)、環境に必要な変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p104">Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams. Review [Prepare your organization's network for Teams](prepare-network.md) and make any required changes to your environment.</span></span>

|<span data-ttu-id="83bc9-120">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-120">Ask yourself</span></span>|<span data-ttu-id="83bc9-121">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="83bc9-122">Teams を展開するために組織の準備が整っているか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-122">Is my organization ready to roll out Teams?</span></span>|<span data-ttu-id="83bc9-123">この質問に回答するには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-123">To answer this question, see:</span></span> <ul><li>[<span data-ttu-id="83bc9-124">Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="83bc9-124">Prepare your organization's network for Teams</span></span>](prepare-network.md)</li><li>[<span data-ttu-id="83bc9-125">URL と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="83bc9-125">URLs and IP address ranges</span></span>](office-365-urls-ip-address-ranges.md)</li><li>[<span data-ttu-id="83bc9-126">チームを作成するときの Microsoft 365 グループの計画</span><span class="sxs-lookup"><span data-stu-id="83bc9-126">Plan for Microsoft 365 Groups when creating teams</span></span>](plan-office-365-groups.md)</li></ul>|
|||

## <a name="core-deployment-decisions"></a><span data-ttu-id="83bc9-127">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-127">Core deployment decisions</span></span>

<span data-ttu-id="83bc9-128">次に示すチャット、チーム、およびチャネルの設定は、ほとんどの組織が変更を必要とするものです (既定の設定では適切に機能しない場合)。</span><span class="sxs-lookup"><span data-stu-id="83bc9-128">These are the chat, teams, and channels settings that most organizations want to change (if the default settings don't work for them).</span></span>

### <a name="teams-administrators"></a><span data-ttu-id="83bc9-129">Teams の管理者</span><span class="sxs-lookup"><span data-stu-id="83bc9-129">Teams administrators</span></span>

<span data-ttu-id="83bc9-p105">Teams は、組織のチームを管理するために使用できる、カスタムの管理者ロールのセットを提供します。ロールは、管理者がさまざまな機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p105">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.</span></span>

| <span data-ttu-id="83bc9-132">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-132">Ask yourself</span></span> | <span data-ttu-id="83bc9-133">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-133">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="83bc9-134">Teams 通信管理者の役割を誰に割り当てるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-134">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="83bc9-135">Teams 管理者の役割の詳細については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-135">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="83bc9-136">Teams 通信サポート エンジニアの役割を誰に割り当てるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-136">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="83bc9-137">管理者の役割を割り当てるには、「[Active Directory で管理者の役割と管理者以外の役割をユーザーに割り当てる](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-137">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="83bc9-138">Teams 通信サポート スペシャリストの役割を誰に割り当てるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-138">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="teams-owners-and-members"></a><span data-ttu-id="83bc9-139">Teams の所有者とメンバー</span><span class="sxs-lookup"><span data-stu-id="83bc9-139">Teams owners and members</span></span>

<span data-ttu-id="83bc9-p106">管理者の役割に加えて、Teams には所有者とメンバーのユーザーの役割を割り当てる機能があります。また、それらのユーザーに選択的にモデレーターの役割を与えて (モデレートを設定している場合)、チャネル内で特定の操作を実行できるユーザーを制御できます。モデレート機能を使用すると、チャネルで新しい投稿を開始できるユーザーを制御したり、チーム メンバーをモデレーターとして追加、削除したり、既存のチャネル メッセージに返信可能かどうかを制御したりできます。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p106">In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel. Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.</span></span>

|<span data-ttu-id="83bc9-142">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-142">Ask yourself</span></span>|<span data-ttu-id="83bc9-143">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-143">Action</span></span> |
|------------|-------|
|<span data-ttu-id="83bc9-144">各役割に誰を割り当てるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-144">Who should be assigned to each role?</span></span> | <span data-ttu-id="83bc9-145">各役割の機能を比較するには「[Microsoft Teams でチームの所有者、モデレーター、メンバーを割り当てる](assign-roles-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-145">To compare the capabilities of each role, see [Assign team owners, moderators, and members in Microsoft Teams](assign-roles-permissions.md).</span></span>
|<span data-ttu-id="83bc9-146">ユーザー役割を割り当てるにはどうすればよいか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-146">How do I assign a user role?</span></span> | <span data-ttu-id="83bc9-147">役割を割り当てたり変更したりするには、「[ユーザー役割の割り当て](assign-roles-permissions.md#assign-a-user-role)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-147">To assign or change a role, see [Assign a user role](assign-roles-permissions.md#assign-a-user-role).</span></span>
|<span data-ttu-id="83bc9-148">チャネルで投稿したり、返信したりできるユーザーを制御する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-148">Do I need to control who can post and reply in a channel?</span></span> | <span data-ttu-id="83bc9-149">モデレートを構成するには、「[Microsoft Teams でチャネル モデレートをセットアップして管理する](manage-channel-moderation-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-149">To configure moderation, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="83bc9-150">メッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="83bc9-150">Messaging policies</span></span>

<span data-ttu-id="83bc9-p107">既定のグローバル ポリシーを使用することも、組織内のユーザーに応じた 1 つ以上のポリシーを作成することもできます。たとえば、どのユーザーが送信メッセージの編集および削除が可能か、どのユーザーがチャットを使用できるか、どのユーザーが会話でミームを使用できるかなどです。既定では、ユーザーにグローバル メッセージング ポリシーが割り当てられていて、すべての機能が **オン** になっています。デフォルトのグローバル ポリシーを使用することも、組織内のユーザー向けに1つ以上のカスタム メッセージング ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p107">Messaging policies control which chat and channel messaging features are available to users in Teams. For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more. By default, users are assigned the global messaging policy and all features are **On**. You can use the default global policy or create one or more custom messaging policies for people in your organization.</span></span> 

|<span data-ttu-id="83bc9-155">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-155">Ask yourself</span></span>|<span data-ttu-id="83bc9-156">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-156">Action</span></span> |
|------------|-------|
|<span data-ttu-id="83bc9-157">グローバル メッセージング ポリシーをカスタマイズするか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-157">Will I customize the global messaging policy?</span></span>|<span data-ttu-id="83bc9-158">Microsoft Teams 管理センターを使用したグローバル メッセージング ポリシーの変更や新しいポリシーの追加に関する詳細については、「[Teams でのメッセージング ポリシーを管理する](messaging-policies-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-158">For information about using the Microsoft Teams admin center to change the global messaging policy or add a new policy, see [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>|
|<span data-ttu-id="83bc9-159">複数のメッセージング ポリシーが必要か?</span><span class="sxs-lookup"><span data-stu-id="83bc9-159">Do I require multiple messaging policies?</span></span>|<span data-ttu-id="83bc9-160">メッセージング ポリシーを PowerShell で作成して割り当てる場合は、「[PowerShell スクリプトのサンプル: メッセージング ポリシーの作成と割り当て](scripts/powershell-script-teams-messaging-policy-edu.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-160">To create and assign a messaging policy in PowerShell, see [PowerShell script sample - Create and assign a messaging policy](scripts/powershell-script-teams-messaging-policy-edu.md).</span></span>|
|<span data-ttu-id="83bc9-161">どのユーザーのグループにどのメッセージング ポリシーを割り当てるかについて判断する方法は?</span><span class="sxs-lookup"><span data-stu-id="83bc9-161">How will I determine which groups of users get which messaging policy?</span></span>|<span data-ttu-id="83bc9-162">CsTeamsMessagingPolicy コマンドレットの詳細については、「[Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-162">To learn about the CsTeamsMessagingPolicy cmdlets, see [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span></span>|
||| 

### <a name="external-access"></a><span data-ttu-id="83bc9-163">外部アクセス</span><span class="sxs-lookup"><span data-stu-id="83bc9-163">External access</span></span>

<span data-ttu-id="83bc9-p108">外部アクセス (旧称: フェデレーション) を使用すると、Teams と Skype for Business のユーザーが、組織外部のユーザーと通信できるようになります。これをオンにして許可リストにドメインを追加すると、ユーザーは別のドメインおよび別の組織のユーザーと通信できます。外部アクセスは、ゲスト アクセスとは異なり、個人ではなくドメイン全体にアクセス許可を与えます。外部アクセスは、既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p108">External access (formerly known as federation) lets your Teams and Skype for Business users communicate with users who are outside of your organization. By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations. External access differs from guest access in that an entire domain is given access permission, not an individual. External access is turned off by default.</span></span>

|<span data-ttu-id="83bc9-168">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-168">Ask yourself</span></span>|<span data-ttu-id="83bc9-169">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-169">Action</span></span> |
|------------|-------|
|<ul><li><span data-ttu-id="83bc9-170">自分の組織の外部アクセスをオンにするか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-170">Will I turn on external access for my organization?</span></span></li><li><span data-ttu-id="83bc9-171">有効にする場合は、自分の組織との通信を許可するドメインを制限するか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-171">If enabled, will I limit which domains my organization can communicate with?</span></span></li></ul> |<br><span data-ttu-id="83bc9-172">外部アクセスを有効にするには、「[外部アクセスを計画する](manage-external-access.md#plan-for-external-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-172">To turn on external access, see [Plan for external access](manage-external-access.md#plan-for-external-access).</span></span>|
|||

### <a name="guest-access"></a><span data-ttu-id="83bc9-173">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="83bc9-173">Guest access</span></span>

<span data-ttu-id="83bc9-p109">Teams のゲスト アクセスを使用すると、組織の外部にいる個人がチームおよびチャネルにアクセスできるようになります。ゲスト アクセスの設定を使用すると、ゲスト ユーザーがある機能を使用できるかどうかを制御できます。ゲスト アクセスは、既定でオフになっています。詳細については、「[Teams でのゲスト アクセス](./guest-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p109">Guest access in Teams lets individuals outside your organization access teams and channels. You can use the guest access settings to control which features guest users can or can't use. Guest access is turned off by default. To learn more, see [Guest access in Teams](./guest-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="83bc9-178">外部アクセスとゲスト アクセスの詳細ついては、「[Microsoft Teams の別の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-178">For more on External access and Guest access see here - [Communicate with users from other organizations in Microsoft Teams](communicate-with-users-from-other-organizations.md)</span></span>


|<span data-ttu-id="83bc9-179">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-179">Ask yourself</span></span>|<span data-ttu-id="83bc9-180">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-180">Action</span></span> |
|------------|-------|
|<span data-ttu-id="83bc9-181">自分の組織のゲスト アクセスをオンにするか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-181">Will I turn on guest access for my organization?</span></span>|<span data-ttu-id="83bc9-182">ゲスト アクセスをオンにするに場合は、「[Teams のゲスト アクセスをオンまたはオフにする](set-up-guests.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-182">To turn on guest access, see [Turn on or off guest access in Teams](set-up-guests.md).</span></span>|
|<span data-ttu-id="83bc9-183">有効にする場合、自分の組織でゲストが使用できる機能をカスタマイズするか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-183">If enabled, will I customize the features available to guests in my organization?</span></span>|<span data-ttu-id="83bc9-184">ゲスト アクセス機能の有効/無効をカスタマイズする場合は、「[Teams のゲスト アクセスを許可する](teams-dependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-184">To customize guest access feature availability, see [Authorize guest access in Teams](teams-dependencies.md).</span></span>|
|||

### <a name="teams-settings"></a><span data-ttu-id="83bc9-185">Teams の設定</span><span class="sxs-lookup"><span data-stu-id="83bc9-185">Teams settings</span></span>

<span data-ttu-id="83bc9-p110">Teams の設定を使用すると、チームに対する電子メール統合、クラウド ストレージのオプション、組織タブ、会議室デバイスのセットアップ、検索範囲などの機能を設定できます。このような設定を変更すると、その変更は組織内のすべてのチームに適用されます。詳細については、「[Teams の設定](enable-features-office-365.md#teams-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p110">Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope. When you make changes to these settings, they apply to all the teams in your organization. To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).</span></span>

|<span data-ttu-id="83bc9-189">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-189">Ask yourself</span></span>|<span data-ttu-id="83bc9-190">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-190">Action</span></span> |
|------------|-------|
|<span data-ttu-id="83bc9-191">自分の組織に合わせて Teams の設定をカスタマイズするか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-191">Will I customize Teams settings for my organization?</span></span> | <span data-ttu-id="83bc9-192">Teams の設定とカスタマイズ方法の詳細は、「[Teams の設定](enable-features-office-365.md#teams-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-192">To learn about Teams settings and how to customize them, see [Teams settings](enable-features-office-365.md#teams-settings).</span></span>|
|||

### <a name="teams-clients"></a><span data-ttu-id="83bc9-193">Teams のクライアント</span><span class="sxs-lookup"><span data-stu-id="83bc9-193">Teams clients</span></span>

<span data-ttu-id="83bc9-p111">Teams は、Web からデスクトップ、モバイルまで複数のクライアントをサポートしています。ユーザーは既定の構成で好みのクライアントを選択できます。詳細については、「[Teams のクライアントを取得する](get-clients.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p111">Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want. To learn more, see [Get clients for Teams](get-clients.md).</span></span>

|<span data-ttu-id="83bc9-196">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-196">Ask yourself</span></span>|<span data-ttu-id="83bc9-197">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-197">Action</span></span> |
|------------|-------|
|<span data-ttu-id="83bc9-198">自分の組織に合わせて Teams クライアントの利用可能性をカスタマイズするか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-198">Will I customize Teams client availability for my organization?</span></span>|<span data-ttu-id="83bc9-199">「[Teams アプリのハードウェア要件](hardware-requirements-for-the-teams-app.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-199">Check out [Hardware requirements for the Teams app](hardware-requirements-for-the-teams-app.md).</span></span> |
|<span data-ttu-id="83bc9-200">自分の組織に合わせて Teams クライアントの設定をカスタマイズするか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-200">Will I customize Teams client settings for my organization?</span></span>|<span data-ttu-id="83bc9-201">詳細については、「[MSI を使用した Teams のインストール](msi-deployment.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-201">Learn how to [Install Teams using MSI](msi-deployment.md).</span></span>|
|||

### <a name="teams-usage-reporting"></a><span data-ttu-id="83bc9-202">Teams の使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="83bc9-202">Teams usage reporting</span></span>

<span data-ttu-id="83bc9-p112">全体管理者、Teams のサービス管理者、およびレポート閲覧者の役割は、Teams の使用状況レポートを表示できます。詳細については、「[Microsoft 365 利用状況分析](/microsoft-365/admin/usage-analytics/usage-analytics)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p112">The Global Admin, Teams Service Admin, and Reports Readers roles can view Teams usage reports. To learn more, see the [Microsoft 365 usage analytics](/microsoft-365/admin/usage-analytics/usage-analytics).</span></span>

|<span data-ttu-id="83bc9-205">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-205">Ask yourself</span></span>|<span data-ttu-id="83bc9-206">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-206">Action</span></span> |
|------------|-------|
|<br> <span data-ttu-id="83bc9-207">誰が Teams の使用状況レポートの確認を必要としていて、レポートを表示するための適切な役割が割り当てられているか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-207">Who needs to see the Teams usage reports, and do they have the correct role to view them?</span></span> |<ul><li><span data-ttu-id="83bc9-208">そのユーザーが管理者でない場合は、[レポート閲覧者の役割を割り当てます](teams-activity-reports.md#reports-reader-role)。</span><span class="sxs-lookup"><span data-stu-id="83bc9-208">If the user isn't an admin, [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="83bc9-209">Azure Active Directory で管理者の役割を割り当てる方法については、「[役割とアクセス許可](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」および「[役割の表示と割り当て](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-209">See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) to learn how to assign admin roles in Azure Active Directory.</span></span> |
|||

### <a name="teams-default-apps"></a><span data-ttu-id="83bc9-210">Teams の既定のアプリ</span><span class="sxs-lookup"><span data-stu-id="83bc9-210">Teams default apps</span></span> 

<span data-ttu-id="83bc9-p113">Teams には、複数のファースト パーティ (Microsoft 提供) のアプリとサード パーティ製アプリがあり、ユーザー参加の促進、生産性のサポート、および一般に使用されるビジネス サービスの Teams への統合のために使用できます。Teams Store からアプリを入手してください。Teams ではアプリが既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p113">Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams. Get apps from the Teams Store. Apps are turned on by default in Teams.</span></span> 

<span data-ttu-id="83bc9-214">Teams のアプリを展開および管理する方法の詳細については、[アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-214">To learn more about rolling out and managing apps in Teams, see our in-depth [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) guidance.</span></span>

## <a name="additional-deployment-decisions"></a><span data-ttu-id="83bc9-215">その他の展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-215">Additional deployment decisions</span></span>

<span data-ttu-id="83bc9-216">次の設定は、組織のニーズと構成に基づいて変更できます。</span><span class="sxs-lookup"><span data-stu-id="83bc9-216">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="teams-licensing"></a><span data-ttu-id="83bc9-217">Teams のライセンス</span><span class="sxs-lookup"><span data-stu-id="83bc9-217">Teams licensing</span></span>

<span data-ttu-id="83bc9-p114">Teams は多くの Microsoft 365 ライセンスまたは Office 365 ライセンスの一部として提供されています。Teams のライセンスの詳細については、「[Microsoft Teams サービスのサービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p114">Teams is provided as part of many Microsoft 365 or Office 365 licenses. To learn more about Teams licensing, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

|<span data-ttu-id="83bc9-220">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-220">Ask yourself</span></span>|<span data-ttu-id="83bc9-221">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-221">Action</span></span> |
|------------|-------|
|<span data-ttu-id="83bc9-222">展開しようとしている Teams のすべての機能を使用するために必要なライセンスをユーザーが所持しているか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-222">Do my users have the licenses they need in order to use all the Teams features I want to roll out?</span></span> | <span data-ttu-id="83bc9-223">ライセンス要件の詳細については、「[Microsoft Teams サービスのサービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-223">To learn about licensing requirements, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>|
|||

### <a name="exchange-and-sharepoint-interoperability"></a><span data-ttu-id="83bc9-224">Exchange と SharePoint の相互運用性</span><span class="sxs-lookup"><span data-stu-id="83bc9-224">Exchange and SharePoint interoperability</span></span>

<span data-ttu-id="83bc9-p115">Teams のすべての機能を活用するために、すべてのユーザーは Exchange Online、SharePoint Online、および Microsoft 365 グループの作成が可能になっている必要があります。次の記事では、さまざまな環境でホストされている Exchange メールボックス、Exchange と Teams の相互作用のしくみ、および SharePoint と OneDrive for Business に関する同様の考慮事項について概要を示します。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p115">For the full Teams experience, every user should be enabled for Exchange Online, SharePoint Online, and Microsoft 365 group creation. The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive for Business.</span></span>

|<span data-ttu-id="83bc9-227">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-227">Ask yourself</span></span>|<span data-ttu-id="83bc9-228">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-228">Action</span></span> |
|------------|-------|
| <span data-ttu-id="83bc9-229">現在の Exchange および SharePoint の展開で Teams の必要な機能を展開できるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-229">Will I be able to deploy the Teams features that I require with the current Exchange and SharePoint deployments?</span></span> |<span data-ttu-id="83bc9-230">Teams での Exchange と SharePoint の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-230">For more information about Exchange and SharePoint in Teams, see:</span></span><ul><li> [<span data-ttu-id="83bc9-231">Exchange と Teams の連携</span><span class="sxs-lookup"><span data-stu-id="83bc9-231">How Exchange and Teams interact</span></span>](exchange-teams-interact.md)</li><li>[<span data-ttu-id="83bc9-232">Teams との SharePoint Online と OneDrive for Business の連携</span><span class="sxs-lookup"><span data-stu-id="83bc9-232">How SharePoint Online and OneDrive for Business interact with Teams</span></span>](sharepoint-onedrive-interact.md)|
|||

### <a name="teams-limits-and-specifications"></a><span data-ttu-id="83bc9-233">Teams の制限と仕様</span><span class="sxs-lookup"><span data-stu-id="83bc9-233">Teams limits and specifications</span></span> 

<span data-ttu-id="83bc9-234">Teams のエンタープライズ展開を計画している場合は、1 つのチームの最大メンバー数やユーザーが作成可能なチーム数の上限など、関連する制限と仕様について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83bc9-234">When planning an enterprise deployment of Teams, you should take into account any relevant limitations and specifications, such as the maximum number of members in a team, the maximum number of teams a user can create, and so on.</span></span>

|<span data-ttu-id="83bc9-235">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-235">Ask yourself</span></span>|<span data-ttu-id="83bc9-236">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-236">Action</span></span> |
|------------|-------|
| <span data-ttu-id="83bc9-237">Teams の展開でどのような制限が問題になる可能性があるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-237">What limits am I likely to hit with my Teams rollout?</span></span> | <span data-ttu-id="83bc9-238">詳細については、「[Teams の制限と仕様](limits-specifications-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-238">To learn more, read [Limits and specifications for Teams](limits-specifications-teams.md).</span></span> |
|||

### <a name="urls-and-ports"></a><span data-ttu-id="83bc9-239">URL とポート</span><span class="sxs-lookup"><span data-stu-id="83bc9-239">URLs and ports</span></span>

<span data-ttu-id="83bc9-p116">インターネット トラフィックの詳細な制御を維持している組織は、Teams の適切な構成が必要になる URL、IP アドレス、ポート、およびプロトコルに関する最新のリストについて、「[URL と IP アドレス範囲](/office365/enterprise/urls-and-ip-address-ranges)」を確認してください。Microsoft は、必要なポート、URL、IP アドレスが時間の経過とともに変更する可能性があることを踏まえて、継続して Microsoft 365 サービスおよび Office 365 サービスを改善し、新機能を追加します。この情報が更新または変更されたときに通知を受け取れるように、RSS で購読することをお勧めします。少なくとも、「[チャットの展開に関する前提条件](#chat-deployment-prerequisites)」で、上記のポートを開いていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p116">Organizations that maintain fine-grained control of their internet traffic should read [URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams. Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time. We recommend that you subscribe via RSS to receive notifications when this information is updated or changed. At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).</span></span>

|<span data-ttu-id="83bc9-244">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-244">Ask yourself</span></span>|<span data-ttu-id="83bc9-245">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-245">Action</span></span> |
|------------|-------|
| <span data-ttu-id="83bc9-246">ユーザーが Teams を使用できるようにするためにインターネット アクセスのルールが必要か、それとも最低限必要なポートを開くだけで十分か?</span><span class="sxs-lookup"><span data-stu-id="83bc9-246">Do I require internet access rules to enable users to use Teams, or is it sufficient to open the minimum required ports?</span></span> | <span data-ttu-id="83bc9-247">詳細については、「[URL と IP アドレス範囲](office-365-urls-ip-address-ranges.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-247">To learn more, see [URLs and IP address ranges](office-365-urls-ip-address-ranges.md).</span></span>|
|||

### <a name="governance-naming-conventions-who-can-create-teams"></a><span data-ttu-id="83bc9-248">ガバナンス (命名規則、チームの作成が可能なユーザー)</span><span class="sxs-lookup"><span data-stu-id="83bc9-248">Governance (naming conventions, who can create teams)</span></span>

<span data-ttu-id="83bc9-p117">組織はチームの命名方法と分類方法、チームの作成が許可されるユーザー、チームの有効期限、保持、およびアーカイブに関する制御を実施するように要求することがあります。これは、ガバナンスと呼ばれます。Azure Active Directory (Azure AD) を使用して、こうした分野のそれぞれを構成できます。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p117">Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving. This is called governance. You can use Azure Active Directory (Azure AD) to configure each of these areas.</span></span>


| <span data-ttu-id="83bc9-252">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-252">Ask yourself</span></span> | <span data-ttu-id="83bc9-253">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-253">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="83bc9-254">チームの作成が可能なユーザーに関する制御の実施が必要になるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-254">Will I need to implement controls on who can create teams?</span></span>| <span data-ttu-id="83bc9-255">「[Teams でのガバナンスを計画する](plan-teams-governance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-255">Read [Plan for governance in Teams](plan-teams-governance.md).</span></span>|
|<span data-ttu-id="83bc9-256">チームの命名に関する制御の実施が必要になるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-256">Will I need to implement controls on how teams are named?</span></span>|<span data-ttu-id="83bc9-257">「[Azure Active Directory での Microsoft 365 グループに対する名前付けポリシーの強制](/azure/active-directory/users-groups-roles/groups-naming-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-257">Read [Enforce a naming policy for Microsoft 365 groups in Azure AD](/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>|
|||

### <a name="teams-application-policy-side-rail-control"></a><span data-ttu-id="83bc9-258">Teams のアプリケーション ポリシー (サイドレール制御)</span><span class="sxs-lookup"><span data-stu-id="83bc9-258">Teams application policy (side-rail control)</span></span>

<span data-ttu-id="83bc9-p118">固定アプリは Teams のサイドレールに表示されます。Teams のアプリケーション ポリシーを作成すると、選択したユーザー グループ用にカスタマイズした固定の Teams アプリのセットを事前に構成できます。既定では、**[Microsoft Teams で外部ありを利用できるようになります]** 設定がオンになっています。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p118">A pinned app shows up in the side rail in Teams. By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users. By default, the **Allow external apps in Microsoft Teams** setting is turned on.</span></span>

| <span data-ttu-id="83bc9-262">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-262">Ask yourself</span></span> | <span data-ttu-id="83bc9-263">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-263">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="83bc9-264">事前に構成した固定の Teams アプリケーションのセットを作成する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-264">Should I create preconfigured sets of pinned Teams applications?</span></span> | <span data-ttu-id="83bc9-265">「[Teams でのアプリの管理設定](admin-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-265">Read [Admin settings for apps in Teams](admin-settings.md).</span></span>|
|<span data-ttu-id="83bc9-266">該当するアプリのグループ化を受け取るグループの決定方法は?</span><span class="sxs-lookup"><span data-stu-id="83bc9-266">How will I decide which groups receive these app groupings?</span></span>|<span data-ttu-id="83bc9-267">「[Teams アプリのアクセス許可と考慮事項](app-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-267">Read [Teams apps permissions and considerations](app-permissions.md).</span></span>|
|||

### <a name="archiving-and-compliance"></a><span data-ttu-id="83bc9-268">アーカイブとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="83bc9-268">Archiving and compliance</span></span> 

<span data-ttu-id="83bc9-p119">組織によっては、チームのアーカイブ方法と、特定の種類のチームに保持されるデータの種類を制御する必要があります。既定でオンになっている Teams 設定の詳細については、「[Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p119">Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams. Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which Teams settings are turned on by default.</span></span>

| <span data-ttu-id="83bc9-271">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-271">Ask yourself</span></span> | <span data-ttu-id="83bc9-272">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-272">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="83bc9-273">チームの保持期間を構成する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-273">Will I need to configure team retention?</span></span>|<span data-ttu-id="83bc9-274">保持ポリシーを設定する場合は、「[Teams の保持ポリシーを設定する](retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-274">To set up retention policies, see [Set up Teams retention policies](retention-policies.md).</span></span>|
|<span data-ttu-id="83bc9-275">チームのアーカイブを構成する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-275">Will I need to configure team archiving?</span></span>|<span data-ttu-id="83bc9-276">チームをアーカイブまたは復元する場合は、「[チームのアーカイブまたは復元](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-276">To archive or restore a team, see [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>|
|<span data-ttu-id="83bc9-277">追加のコンプライアンス設定を構成する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-277">Will I need to configure additional compliance settings?</span></span>|<span data-ttu-id="83bc9-278">セキュリティとコンプライアンスの詳細については、「[Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-278">For more information about security and compliance, see [Overview of security and compliance in Teams](security-compliance-overview.md).</span></span>|
|||

### <a name="conditional-access"></a><span data-ttu-id="83bc9-279">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="83bc9-279">Conditional access</span></span> 

<span data-ttu-id="83bc9-p120">Teams は、主要な生産性シナリオ (会議、予定表、相互運用チャット、ファイル共有など) に関して Exchange Online、SharePoint Online、および Skype for Business Online に大きく依存しています。これらのクラウド アプリ向けに設定された条件付きアクセス ポリシーは、ユーザーが任意のクライアントで Teams に直接サインインするときに Teams に適用されます。Teams のクラウド アプリ向けに設定された条件付きアクセス ポリシーでは、ユーザーが特定のネットワークから Teams のサービスにアクセスできるかどうかなどの側面を制御します。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p120">Teams relies heavily on Exchange Online, SharePoint Online, and Skype for Business Online for core productivity scenarios, including meetings, calendars, interop chats, and file sharing. Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client. Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.</span></span>

| <span data-ttu-id="83bc9-283">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-283">Ask yourself</span></span> | <span data-ttu-id="83bc9-284">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-284">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="83bc9-285">Teams に対する条件付きアクセスを構成する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-285">Will I need to configure conditional access for Teams?</span></span>|<ul><li><span data-ttu-id="83bc9-286">アクセス ポリシーのしくみについては、「[Teams で条件付きアクセス ポリシーはどのように機能しますか?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-286">To understand how access policies work, see [How do conditional access policies work for Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</span></span></li><li><span data-ttu-id="83bc9-287">Teams の多要素認証を設定する場合は、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-287">To set up multi-factor authentication (MFA) for Teams, see:</span></span><ul><li>[<span data-ttu-id="83bc9-288">クイック スタート: Azure Active Directory の条件付きアクセスを使用して特定のアプリケーションに対して MFA を必要にする</span><span class="sxs-lookup"><span data-stu-id="83bc9-288">Quickstart: Require MFA for specific apps with Azure Active Directory conditional access</span></span>](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[<span data-ttu-id="83bc9-289">Azure Active Directory の条件付きアクセス設定に関するリファレンス</span><span class="sxs-lookup"><span data-stu-id="83bc9-289">Azure Active Directory conditional access settings reference</span></span>](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|
|||


### <a name="education-edu"></a><span data-ttu-id="83bc9-290">教育機関 (EDU)</span><span class="sxs-lookup"><span data-stu-id="83bc9-290">Education (EDU)</span></span> 

<span data-ttu-id="83bc9-291">教育機関の業務に従事する IT 担当者は、教育機関向け Teams を利用できます。この Teams には、学生、教職員、および広範な業務に応じた教育機関に固有のシナリオに適合する多数の機能が備わっています。</span><span class="sxs-lookup"><span data-stu-id="83bc9-291">IT pros working in education can take advantage of Teams for Education, which comes with a number of capabilities that have been tailored to meet education-specific scenarios for students, faculty, and the wider business.</span></span>

| <span data-ttu-id="83bc9-292">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-292">Ask yourself</span></span> | <span data-ttu-id="83bc9-293">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-293">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="83bc9-294">教育機関固有の Teams テンプレートを使用するか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-294">Will I use EDU-specific Teams templates?</span></span> |<span data-ttu-id="83bc9-295">教育機関向け Teams の詳細については、「[Microsoft Education ガバナンスに関するよく寄せられる質問 (管理者向け)](plan-teams-governance-edu.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-295">To learn more about Teams for Education, see [Microsoft Education governance FAQ for admins](plan-teams-governance-edu.md).</span></span>|
|<span data-ttu-id="83bc9-296">範囲設定された検索を展開するか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-296">Will I deploy scoped search?</span></span>|<span data-ttu-id="83bc9-297">教育機関向け Teams をセットアップする場合は、「[クイックスタート: 教育機関向け Teams の管理](teams-quick-start-edu.yml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-297">To set up Teams for EDU, see [Quickstart - Teams for Education admins](teams-quick-start-edu.yml).</span></span>|
|<span data-ttu-id="83bc9-298">ユーザー アカウントのプロビジョニングのために Teams と学校データ同期サービスを統合するか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-298">Will I integrate Teams with the School Data Sync service to provision user accounts?</span></span>|[<span data-ttu-id="83bc9-299">教育機関管理者向けの Teams のリソース</span><span class="sxs-lookup"><span data-stu-id="83bc9-299">Teams resources for Education admins</span></span>](resources-teams-edu.md)|
|||

### <a name="government---gcc-considerations"></a><span data-ttu-id="83bc9-300">政府機関: GCC に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-300">Government - GCC considerations</span></span>

<span data-ttu-id="83bc9-301">Office 365 for Government (GCC: Government Community Cloud) の使用は、米国連邦、州、地方、民族、または領土の政府機関など、政府の規制と要件の対象になるデータを扱う機関で Office 365 の展開を推進している IT 担当者の要件を満たすのに適しています。</span><span class="sxs-lookup"><span data-stu-id="83bc9-301">The use of Office 365 for Government - GCC (Government Community Cloud) is appropriate to meet the requirements of IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements.</span></span>

| <span data-ttu-id="83bc9-302">確認事項</span><span class="sxs-lookup"><span data-stu-id="83bc9-302">Ask yourself</span></span> | <span data-ttu-id="83bc9-303">アクション</span><span class="sxs-lookup"><span data-stu-id="83bc9-303">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="83bc9-304">Office 365 for Government: GCC 環境に Teams を展開する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="83bc9-304">Will I need to deploy Teams in a Office 365 for Government – GCC environment?</span></span> | <span data-ttu-id="83bc9-305">展開に関する考慮事項については、「[Office 365 for Government: GCC 展開の計画](plan-for-government-gcc.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-305">For deployment considerations, see [Plan for Office 365 Government - GCC deployments](plan-for-government-gcc.md).</span></span>|
|||

## <a name="next-steps"></a><span data-ttu-id="83bc9-306">次のステップ</span><span class="sxs-lookup"><span data-stu-id="83bc9-306">Next steps</span></span>
- <span data-ttu-id="83bc9-307">チャット、チーム、チャネル、およびアプリの[導入を推進する](adopt-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="83bc9-307">[Drive adoption](adopt-microsoft-teams-landing-page.md) of chat, teams, channels, & apps.</span></span>
- <span data-ttu-id="83bc9-p121">最初の Teams ロールアウトには、Planner などのおすすめのアプリを含めます。 Teams 導入の進行に応じて、その他の[アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)を追加してください。</span><span class="sxs-lookup"><span data-stu-id="83bc9-p121">Include featured apps - such as Planner - in your initial Teams rollout. Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
- [<span data-ttu-id="83bc9-310">ミーティングと会議を展開する</span><span class="sxs-lookup"><span data-stu-id="83bc9-310">Roll out meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="83bc9-311">クラウド ボイスを展開する</span><span class="sxs-lookup"><span data-stu-id="83bc9-311">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)