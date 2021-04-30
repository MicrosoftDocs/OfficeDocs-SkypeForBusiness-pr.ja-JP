---
title: Microsoft Education のガバナンスに関するよくある質問 (管理者向け)
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Teamsを使用している Microsoft Education グループの管理者からよく寄せられる質問にお答えします。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ada92509adc0f066bf957ddaa8f5de8dd0c47653
ms.sourcegitcommit: 8906fc384cd13255972df53d2a07d12589154d42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2021
ms.locfileid: "52085849"
---
# <a name="microsoft-education-governance-faq-for-admins"></a><span data-ttu-id="590d2-103">Microsoft Education のガバナンスに関するよくある質問 (管理者向け)</span><span class="sxs-lookup"><span data-stu-id="590d2-103">Microsoft Education governance FAQ for admins</span></span>

> [!Tip]
> <span data-ttu-id="590d2-104">Microsoft Teams での管理の詳細については、次のセッションをご覧ください。[Microsoft Teams でのガバナンス、管理、およびライフサイクル](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="590d2-104">Watch the following session to learn about more about management in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a><span data-ttu-id="590d2-105">チームの作成を制御するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="590d2-105">How do I control team creation?</span></span> <span data-ttu-id="590d2-106">学生が不適切なチームを作成するのではないかと心配です。</span><span class="sxs-lookup"><span data-stu-id="590d2-106">I'm worried students are going to create inappropriate teams.</span></span>

<span data-ttu-id="590d2-107">不適切な名前や誤解を招く名前を避けるため、またはチームの名前の構造を追加するために、Microsoft 365 グループ名前付けポリシー (現在プレビュー中) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="590d2-107">To avoid inappropriate or misleading names, or just to provide more structure for how teams are named, you can use the Microsoft 365 Groups naming policy (currently in preview):</span></span>

-   <span data-ttu-id="590d2-108">**プレフィックス/サフィックスの名前付けポリシー** プレフィックスまたはサフィックスを使用して、チーム (グループ) の名前付け規則を定義できます (例: **GRP_US_My Group_Engineering**)</span><span class="sxs-lookup"><span data-stu-id="590d2-108">**Prefix-Suffix naming policy** You can use prefixes or suffixes to define the naming convention of teams (groups), for example, **GRP_US_My Group_Engineering**.</span></span> <span data-ttu-id="590d2-109">プレフィックスとサフィックスには、チームを作成しているユーザーに基づいて名前に追加される固定文字列またはユーザー属性 ([ **部門] など)** を指定できます。</span><span class="sxs-lookup"><span data-stu-id="590d2-109">The prefixes and suffixes can be fixed strings or user attributes (such as **[Department]**) that are added to the name based on the user who's creating the team.</span></span>
-   <span data-ttu-id="590d2-110">**カスタムのブロックする単語** 特定の組織のユーザーが作成したチームの名前で使用をブロックする単語のセットをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="590d2-110">**Custom Blocked Words** You can upload a set of words that users in a specific organization are blocked from using in names of teams they create.</span></span> <span data-ttu-id="590d2-111">たとえば、CEO、Payroll、HR という用語が、適用されないグループのチーム名で使用されるのをブロックできます。 </span><span class="sxs-lookup"><span data-stu-id="590d2-111">For example, you can block the terms **CEO**, **Payroll**, and **HR** from being used in team names for groups they don't apply to.</span></span>
-   <span data-ttu-id="590d2-112">**分類** 組織内のユーザーがグループを作成するときに設定できる分類をMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="590d2-112">**Classification** You can create classifications that the users in your organization can set when they create a Microsoft 365 Group.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="590d2-113">Microsoft 365 グループ名前付けポリシーを使用するには、1 つ以上の Microsoft 365 グループのメンバーである一意のユーザーごとに、Azure Active Directory プレミアム P1 ライセンスまたは Azure AD Basic EDU ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="590d2-113">Using the Microsoft 365 Groups Naming Policy requires Azure Active Directory Premium P1 licenses or Azure AD Basic EDU licenses for each unique user that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="590d2-114">詳しい手順については、「[Office グループの名前付けポリシー](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="590d2-114">For detailed instructions, see [Office groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

> [!Note]
> <span data-ttu-id="590d2-115">チームが別のシステムからの入力 (学校データ同期 など) を使用して自動的に作成される場合は、入力データが構成した名前付けポリシーに準拠していることを確認します。作成しない場合、チームの作成は失敗します。</span><span class="sxs-lookup"><span data-stu-id="590d2-115">If teams are created automatically by using the input from another system (for example, School Data Sync), verify that the input data complies with the naming policy you've configured; if it doesn't, team creation will fail.</span></span>

## <a name="can-i-see-who-created-a-team"></a><span data-ttu-id="590d2-116">チームを作成したユーザーを確認できますか?</span><span class="sxs-lookup"><span data-stu-id="590d2-116">Can I see who created a team?</span></span>

<span data-ttu-id="590d2-117">特定のチームの作成者を確認するには、「[Microsoft Teams でイベントの監査ログを検索する](audit-log-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="590d2-117">To find out who created a specific team, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="can-i-control-who-can-create-teams"></a><span data-ttu-id="590d2-118">チームを作成できるユーザーを制御できますか?</span><span class="sxs-lookup"><span data-stu-id="590d2-118">Can I control who can create teams?</span></span>

<span data-ttu-id="590d2-119">一般的に、誰もチームを作成できないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="590d2-119">In general, we recommend against preventing anyone from creating teams.</span></span> <span data-ttu-id="590d2-120">すべてのユーザーがチームを作成できるのであれば、Teams はより広く導入されるでしょう。</span><span class="sxs-lookup"><span data-stu-id="590d2-120">If everyone can create teams, Teams is more likely to be widely adopted.</span></span> <span data-ttu-id="590d2-121">教職員、教師、生徒は Teams を使用して研究グループや特別な目的のグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="590d2-121">Faculty, teachers, or students can  use Teams to create study groups or special interest groups.</span></span> <span data-ttu-id="590d2-122">これにより、Teams は教室の内外で受け入れられるようになります。</span><span class="sxs-lookup"><span data-stu-id="590d2-122">This will help Teams be accepted inside and outside of the classroom.</span></span>

<span data-ttu-id="590d2-123">私たちの経験では、ユーザー教育は責任ある Teams の使用を確実にするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="590d2-123">In our experience, user education helps ensure responsible Teams usage.</span></span> <span data-ttu-id="590d2-124">ユーザーは、チームの作成が匿名ではないと理解するとすぐに、チームを不注意に作成する意味を理解し、ツールの誤用を敬遠する傾向があります。</span><span class="sxs-lookup"><span data-stu-id="590d2-124">As soon as users understand that creating teams isn't anonymous, they understand the implications of carelessly creating them and tend to shy away from misusing the tool.</span></span>

<span data-ttu-id="590d2-125">チームを作成できるユーザーを制御する必要がある場合は、「グループを作成できるユーザーを管理する」を[Microsoft 365してください](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="590d2-125">If you're sure you want to control who can create teams, see [Manage who can create Microsoft 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a><span data-ttu-id="590d2-126">学期または四半期の開始時にコースごとにチームを自動的に作成するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="590d2-126">How do I automatically create a team for each course at the beginning of the semester or quarter?</span></span>

<span data-ttu-id="590d2-127">各学期または四半期の始めには、新しいチームが多数必要です。</span><span class="sxs-lookup"><span data-stu-id="590d2-127">At the start of each semester or quarter, you'll need a number of new teams.</span></span> <span data-ttu-id="590d2-128">これらのチームを自動的に作成し、適切なユーザーを選択し、適切な権限を設定するという自動化されたアプローチは適切かもしれません。</span><span class="sxs-lookup"><span data-stu-id="590d2-128">It might make sense to take an automated approach to create these teams automatically, populate them with the right users, and set the right permissions:</span></span>

-   <span data-ttu-id="590d2-129">学校データ同期 Exchange Online および SharePoint Online 用の Microsoft 365 グループ、Microsoft Teams および OneNote クラス ノートブックのクラス チーム、Intune for Education の学校グループ、他の多くのサード パーティ アプリケーションの登録とシングル サインオン (SSO) 統合を作成できます。</span><span class="sxs-lookup"><span data-stu-id="590d2-129">School Data Sync can create Microsoft 365 Groups for Exchange Online and SharePoint Online, class teams for Microsoft Teams and OneNote Class notebooks, school groups for Intune for Education, and rostering and single sign-on (SSO) integration for many other third-party applications.</span></span> <span data-ttu-id="590d2-130">詳細については、「[School Data Sync の概要](/schooldatasync/overview-of-school-data-sync)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="590d2-130">Learn more at [Overview of School Data Sync](/schooldatasync/overview-of-school-data-sync).</span></span>
-   <span data-ttu-id="590d2-131">PowerShell を使用すると、チームやチャネルを作成して、設定を自動的に構成できます。</span><span class="sxs-lookup"><span data-stu-id="590d2-131">With PowerShell, you can create teams and channels, and configure settings automatically.</span></span> <span data-ttu-id="590d2-132">詳細については、「[Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="590d2-132">See [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
-   <span data-ttu-id="590d2-133">Microsoft Graph API (現在ベータ版) を使用して、チームの作成、構成、複製、アーカイブを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="590d2-133">You can use the Microsoft Graph API (currently in beta) to create, configure, clone, and archive teams.</span></span> <span data-ttu-id="590d2-134">詳細については、「[Microsoft Graph API を使用して Microsoft Teams で作業する](/graph/api/resources/teams-api-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="590d2-134">See [Use the Microsoft Graph API to work with Microsoft Teams](/graph/api/resources/teams-api-overview) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="590d2-135">学校データ同期クラスごとに Microsoft 365 グループを作成し、非表示のグループ メンバーシップを有効[](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945)にし、クラス内の教師と学生だけがそのクラスのメンバーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="590d2-135">School Data Sync creates a Microsoft 365 Group for each class synced and [enables hidden group membership](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) so only teachers and students within the class can see the members of that class.</span></span> <span data-ttu-id="590d2-136">別のプロセスを使用してクラス グループを作成している場合は、New-UnifiedGroup コマンドレットの HiddenGroupMembershipEnabled パラメーターを使用して、同じプライバシー要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="590d2-136">If using a different process to create class groups use the HiddenGroupMembershipEnabled parameter of the New-UnifiedGroup cmdlet to meet the same privacy requirements.</span></span>

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a><span data-ttu-id="590d2-137">学期や四半期が終わったときにチームにどのような対処すればよいですか?</span><span class="sxs-lookup"><span data-stu-id="590d2-137">How do I deal with teams when the semester or quarter ends?</span></span>

<span data-ttu-id="590d2-138">学校の学期または四半期が終了した場合に、Teams データを処理する方法を最初に考えすることをお勧めします。コースを完了した後でも、そのデータを削除するか、学生が使用できるかどうかを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="590d2-138">We recommend that you first think about how you want to handle Teams data when the school semester or quarter is over: whether to delete it or keep it available for students even after they've completed the course.</span></span> <span data-ttu-id="590d2-139">設定したポリシーが休日と競合しないので、学校の予定表を念頭に置いておきたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="590d2-139">You'll want to keep the school calendar in mind so any policies you set don't conflict with holidays.</span></span> <span data-ttu-id="590d2-140">戦略の実装には次のツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="590d2-140">You can use the following tools to implement your strategy:</span></span>

-   <span data-ttu-id="590d2-141">**アイテム保持ポリシー:** 指定した期間を経過したすべての古いデータが削除されます。古いデータがチャット (すべてまたは一部のユーザー用) およびチャンネルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="590d2-141">**Retention policy:** Use this to delete all data older than an age you specify to make sure that old data is removed from chats (for all or some users) and channels.</span></span> <span data-ttu-id="590d2-142">コンテンツを削除Teamsコンテンツを保持する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="590d2-142">You can also configure Teams to retain content so it can't be deleted.</span></span> <span data-ttu-id="590d2-143">詳細については、「[Microsoft Teams の保持ポリシー](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="590d2-143">For more information, see [Retention policies for Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).</span></span>
-   <span data-ttu-id="590d2-144">**有効期限ポリシー:** 特定の日数が経過した後に、期限切れになるようにチームを構成します。</span><span class="sxs-lookup"><span data-stu-id="590d2-144">**Expiry policy:** Configure teams to expire after a certain number of days.</span></span> <span data-ttu-id="590d2-145">有効期限の 30 日前に、チームのすべての所有者に、チームの更新が必要であることが通知されます。それ以外の場合は、削除されます (管理者は、削除されたチームをさらに 30 日間復元できます)。</span><span class="sxs-lookup"><span data-stu-id="590d2-145">Thirty days before expiration, all owners of a team are notified that their team needs to be renewed, otherwise it will be deleted (though an administrator can recover deleted teams for an additional 30 days).</span></span> <span data-ttu-id="590d2-146">この設定は、未使用のチームが使用されていない状況を確認するのに非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="590d2-146">This setting is very useful for making sure unused teams are sunsetted.</span></span> <span data-ttu-id="590d2-147">詳細については、「有効期限ポリシー [Microsoft 365」を参照してください](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)。</span><span class="sxs-lookup"><span data-stu-id="590d2-147">Learn more at [Microsoft 365 group Expiration Policy](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).</span></span>

-   <span data-ttu-id="590d2-148">**チームをアーカイブする:** この設定で、チームは読み取り専用モードになります。</span><span class="sxs-lookup"><span data-stu-id="590d2-148">**Archive team:** This setting puts teams into read-only mode.</span></span> <span data-ttu-id="590d2-149">参照して検索することはできますが、新しい投稿を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="590d2-149">They can still be browsed and searched, but no one can add any new posts.</span></span> <span data-ttu-id="590d2-150">「[チームをアーカイブする、または復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)」は、チームの所有者がチームをアーカイブする方法を説明します。チームの所有者は、 「[Graph API (ベータ)](/graph/api/resources/teams-api-overview)」を使用してチームをアーカイブまたは復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="590d2-150">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) describes how team owners can archive a team; Team owners can also use the [Graph API (beta)](/graph/api/resources/teams-api-overview) to archive or restore a team.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="590d2-151">グループ有効期限ポリシー Microsoft 365使用するには、Azure Active Directory プレミアムグループのメンバーである一意のユーザーごとに P1 ライセンスをMicrosoft 365必要があります。</span><span class="sxs-lookup"><span data-stu-id="590d2-151">Using the Microsoft 365 Groups Expiration Policy requires Azure Active Directory Premium P1 licenses for each unique user that is a member of one or more Microsoft 365 groups.</span></span>

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a><span data-ttu-id="590d2-152">チームを作成するときに教職員用に使用できるチームのテンプレートはありますか?</span><span class="sxs-lookup"><span data-stu-id="590d2-152">Are there team templates for my faculty members to use when creating a team?</span></span>

<span data-ttu-id="590d2-153">はい。</span><span class="sxs-lookup"><span data-stu-id="590d2-153">Yes.</span></span> <span data-ttu-id="590d2-154">ユーザーは新しいチームを作成するときに **既存のテンプレートからチームを作成する** ことを選択でき、Teams の所有者も使用可能なテンプレートから [Graph API (ベータ版)](/graph/api/resources/teams-api-overview) を使用して新しいチームを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="590d2-154">Users can select **Create Team from existing template** when creating a new team, and Teams owners can also use the [Graph API (beta)](/graph/api/resources/teams-api-overview) to create a new team from the available templates.</span></span>

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a><span data-ttu-id="590d2-155">PowerShell や Graph を介して自動化できるタスクは何がありますか?</span><span class="sxs-lookup"><span data-stu-id="590d2-155">What tasks can I automate via PowerShell or Graph?</span></span>

<span data-ttu-id="590d2-156">[Microsoft Graph API (ベータ版)](/graph/api/resources/teams-api-overview) で、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="590d2-156">The [Microsoft Graph API (beta)](/graph/api/resources/teams-api-overview) can do the following:</span></span>

-   <span data-ttu-id="590d2-157">チームの作成。</span><span class="sxs-lookup"><span data-stu-id="590d2-157">Create a team.</span></span>
-   <span data-ttu-id="590d2-158">メンバーおよび所有者の追加。</span><span class="sxs-lookup"><span data-stu-id="590d2-158">Add members and owners.</span></span>
-   <span data-ttu-id="590d2-159">チャネルの追加。</span><span class="sxs-lookup"><span data-stu-id="590d2-159">Add channels.</span></span>
-   <span data-ttu-id="590d2-160">アプリの追加。</span><span class="sxs-lookup"><span data-stu-id="590d2-160">Add apps.</span></span>
-   <span data-ttu-id="590d2-161">既存のチームを複製してこれらのステップを短縮し、そのタブも取得。</span><span class="sxs-lookup"><span data-stu-id="590d2-161">Shortcut those steps by cloning an existing team, and get its tabs too.</span></span>
-   <span data-ttu-id="590d2-162">作成したばかりのチームへのリンクをユーザーに提供。</span><span class="sxs-lookup"><span data-stu-id="590d2-162">Give the user a link to the team you just created.</span></span>
-   <span data-ttu-id="590d2-163">不要になったメンバー、所有者、チャネル、アプリの削除。</span><span class="sxs-lookup"><span data-stu-id="590d2-163">Remove members, owners, channels, and apps when you no longer need them.</span></span>
-   <span data-ttu-id="590d2-164">アクティブでなくなったチームのアーカイブ。</span><span class="sxs-lookup"><span data-stu-id="590d2-164">Archive the team when it's no longer active.</span></span> 
-   <span data-ttu-id="590d2-165">チームの削除。</span><span class="sxs-lookup"><span data-stu-id="590d2-165">Delete the team.</span></span>
-   <span data-ttu-id="590d2-166">チャネル スレッドの作成</span><span class="sxs-lookup"><span data-stu-id="590d2-166">Create a channel thread</span></span>

<span data-ttu-id="590d2-167">[PowerShell](/powershell/module/teams/?view=teams-ps) では、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="590d2-167">[PowerShell](/powershell/module/teams/?view=teams-ps) can do the following:</span></span>

-   <span data-ttu-id="590d2-168">チームの作成。</span><span class="sxs-lookup"><span data-stu-id="590d2-168">Create a team.</span></span>
-   <span data-ttu-id="590d2-169">メンバーおよび所有者の追加。</span><span class="sxs-lookup"><span data-stu-id="590d2-169">Add members and owners.</span></span>
-   <span data-ttu-id="590d2-170">チャネルの追加。</span><span class="sxs-lookup"><span data-stu-id="590d2-170">Add channels.</span></span>
-   <span data-ttu-id="590d2-171">不要になったメンバー、所有者、チャネルの削除。</span><span class="sxs-lookup"><span data-stu-id="590d2-171">Remove members, owners, and channels when you no longer need them.</span></span>
-   <span data-ttu-id="590d2-172">チームの削除。</span><span class="sxs-lookup"><span data-stu-id="590d2-172">Delete the team.</span></span>

> [!TIP]
> <span data-ttu-id="590d2-173">Graph API と PowerShell コマンドレットで継続的に機能を追加。</span><span class="sxs-lookup"><span data-stu-id="590d2-173">The Graph API and PowerShell cmdlets are constantly adding functionality.</span></span> <span data-ttu-id="590d2-174">機能拡張については、「[Microsoft Graph API (ベータ版)](/graph/api/resources/teams-api-overview)」および 「[PowerShell](/powershell/module/teams/?view=teams-ps)」の記事をよく確認してください。</span><span class="sxs-lookup"><span data-stu-id="590d2-174">Make sure to check the [Microsoft Graph API (beta)](/graph/api/resources/teams-api-overview) and [PowerShell](/powershell/module/teams/?view=teams-ps) articles often for feature enhancements.</span></span>  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a><span data-ttu-id="590d2-175">教職員と学生がどの Teams の機能にアクセスできるかを制御できますか?</span><span class="sxs-lookup"><span data-stu-id="590d2-175">Can I control what Teams features my faculty and students have access to?</span></span>

<span data-ttu-id="590d2-176">はい。</span><span class="sxs-lookup"><span data-stu-id="590d2-176">Yes.</span></span> <span data-ttu-id="590d2-177">ポリシーを使用して、ユーザーがアクセスする特定のメッセージ、会議、通話、ライブ イベント機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="590d2-177">You can use policies to control specific messaging, meeting, calling, and live event features your users have access to.</span></span> <span data-ttu-id="590d2-178">テナント全体の設定を使用して、同じ設定をすべてに適用するか、必要に応じてユーザーレベルのポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="590d2-178">You can use tenant-wide settings to apply the same settings to all, or apply user-level policies if required.</span></span> 

<span data-ttu-id="590d2-179">Teams のポリシーの詳細については、「[組織の Microsoft Teams の設定を管理する](enable-features-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="590d2-179">For more details about Teams policies, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a><span data-ttu-id="590d2-180">教職員と学生が共同作業を行う外部関係者を制御できますか?</span><span class="sxs-lookup"><span data-stu-id="590d2-180">Can I control what external parties my faculty and students collaborate with?</span></span>

<span data-ttu-id="590d2-181">ゲスト アクセスを使用すると、テナント外のユーザーを招待することができます。これは、研究の共同作業や来客の講義に便利です。</span><span class="sxs-lookup"><span data-stu-id="590d2-181">You can use guest access to invite users from outside of your tenant, which can be useful for research collaboration or guest lectures:</span></span>

-   <span data-ttu-id="590d2-182">ドメインの許可リストを使用して、ドメインに基づいてゲストを許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="590d2-182">Use a domain allowlist to allow or block guests based on their domain.</span></span>
-   <span data-ttu-id="590d2-183">特定のグループとチームに対してMicrosoft 365アクセスをオンまたはオフにし、ゲストを招待できる (および招待できない) チームを制御します。</span><span class="sxs-lookup"><span data-stu-id="590d2-183">Turn guest access on and off for particular Microsoft 365 Groups and teams, to control which teams can (and can't) invite guests.</span></span>
-   <span data-ttu-id="590d2-184">監査ログを使用して、招待されたゲストに送信された警告を確認します。</span><span class="sxs-lookup"><span data-stu-id="590d2-184">Use the audit log to see which alerts were sent to invited guests.</span></span>

<span data-ttu-id="590d2-185">詳細については、「グループ内のゲスト アクセス[」をMicrosoft 365してください](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)。</span><span class="sxs-lookup"><span data-stu-id="590d2-185">For more information, see [Guest access in Microsoft 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).</span></span>

## <a name="what-information-can-i-review-about-existing-teams"></a><span data-ttu-id="590d2-186">既存のチームについてどのような情報を確認できますか?</span><span class="sxs-lookup"><span data-stu-id="590d2-186">What information can I review about existing teams?</span></span>

<span data-ttu-id="590d2-187">監査ログを確認すると、次の事項を確認できます。</span><span class="sxs-lookup"><span data-stu-id="590d2-187">You can check the audit logs to see:</span></span>

-   <span data-ttu-id="590d2-188">誰がどのチームにゲストとして招待されたか。</span><span class="sxs-lookup"><span data-stu-id="590d2-188">Who was invited as a guest to which team.</span></span>
-   <span data-ttu-id="590d2-189">誰がどのチームを作成したのか。</span><span class="sxs-lookup"><span data-stu-id="590d2-189">Who created which team.</span></span>

<span data-ttu-id="590d2-190">詳細については、「[Microsoft Teams でイベントの監査ログを検索する](audit-log-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="590d2-190">For more information, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a><span data-ttu-id="590d2-191">Teams は急速に進化しています。</span><span class="sxs-lookup"><span data-stu-id="590d2-191">Teams evolves so quickly.</span></span> <span data-ttu-id="590d2-192">最新の状態を維持するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="590d2-192">How can I stay up-to-date?</span></span>

<span data-ttu-id="590d2-193">Teams の最新の更新プログラムを取得するには、次のリソースをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="590d2-193">We recommend the following resources to get the latest updates on Teams:</span></span>

-   [<span data-ttu-id="590d2-194">Microsoft Teams の新機能</span><span class="sxs-lookup"><span data-stu-id="590d2-194">What's new in Microsoft Teams</span></span>](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [<span data-ttu-id="590d2-195">Microsoft Teams のブログ</span><span class="sxs-lookup"><span data-stu-id="590d2-195">Microsoft Teams blog</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)