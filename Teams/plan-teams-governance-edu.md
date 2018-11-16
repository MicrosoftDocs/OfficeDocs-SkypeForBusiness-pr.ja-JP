---
title: IT プロフェッショナル向けのマイクロソフトのチームの Microsoft 教育ガバナンスに関する FAQ
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: チームを使用して、マイクロソフトの教育グループの管理者からよく寄せられる質問への回答です。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 687012404713bcbfcb8ecf86efa8af36b8eb0a59
ms.sourcegitcommit: f0dec487e2893a171c7e701bfcf598076f5245b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539066"
---
# <a name="microsoft-education-governance-faq-for-admins"></a><span data-ttu-id="2ae5b-103">管理者のマイクロソフト教育ガバナンスに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="2ae5b-103">Microsoft Education governance FAQ for admins</span></span>

> [!Tip]
> <span data-ttu-id="2ae5b-104">マイクロソフトのチームでの管理の詳細については、次のセッションを見る:[管理、管理、およびマイクロソフトのチームでのライフ サイクル](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="2ae5b-104">Watch the following session to learn about more about management in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a><span data-ttu-id="2ae5b-105">チームの作成を制御する方法は?</span><span class="sxs-lookup"><span data-stu-id="2ae5b-105">How do I control team creation?</span></span> <span data-ttu-id="2ae5b-106">ない受講者は、不適切なチームを作成しようとしています。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-106">I'm worried students are going to create inappropriate teams.</span></span>

<span data-ttu-id="2ae5b-107">不適切または誤解を招く名前を避けるために、またはチームに名前を付ける方法の多くの構造を提供するだけには、Office 365 グループ (プレビュー) で現在のポリシーの名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-107">To avoid inappropriate or misleading names, or just to provide more structure for how teams are named, you can use the Office 365 Groups naming policy (currently in preview):</span></span>

-   <span data-ttu-id="2ae5b-108">**プレフィックス、サフィックスの名前付けポリシー**プレフィックスまたはサフィックス、チーム (グループ) の名前付け規則を定義するのには**GRP_US_My Group_Engineering**を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-108">**Prefix-Suffix naming policy** You can use prefixes or suffixes to define the naming convention of teams (groups), for example, **GRP_US_My Group_Engineering**.</span></span> <span data-ttu-id="2ae5b-109">プレフィックスおよびサフィックスは文字列またはチームを作成しているユーザー名に追加されます ( **[部署]**) などのユーザー属性に固定できます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-109">The prefixes and suffixes can be fixed strings or user attributes (such as **[Department]**) that are added to the name based on the user who’s creating the team.</span></span>
-   <span data-ttu-id="2ae5b-110">**カスタム単語をブロックします。** 単語のセットをアップロードすることで作成するチームの名前を使用して、特定の組織内のユーザーがブロックされています。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-110">**Custom Blocked Words** You can upload a set of words that users in a specific organization are blocked from using in names of teams they create.</span></span> <span data-ttu-id="2ae5b-111">などには適用しないグループの名前をチームで使用されているから**最高経営責任者**、**給与**、および**人事**の用語をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-111">For example, you can block the terms **CEO**, **Payroll**, and **HR** from being used in team names for groups they don’t apply to.</span></span>
-   <span data-ttu-id="2ae5b-112">**クラス分け**組織内のユーザーが、Office 365 のグループを作成するときに設定する分類を作成します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-112">**Classification** You can create classifications that the users in your organization can set when they create an Office 365 group.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="2ae5b-113">Office 365 グループ名前付けポリシーを使用すると、1 つまたは複数の Office 365 のグループのメンバーである個々 のユーザーの Azure Active Directory プレミアム P1 ライセンスまたは EDU の Azure AD の基本的なライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-113">Using the Office 365 Groups Naming Policy requires Azure Active Directory Premium P1 licenses or Azure AD Basic EDU licenses for each unique user that is a member of one or more Office 365 groups.</span></span>

<span data-ttu-id="2ae5b-114">詳細については、 [Office のグループ ポリシーの名前を付ける](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-114">For detailed instructions, see [Office groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

> [!Note]
> <span data-ttu-id="2ae5b-115">チームは別のシステム (たとえば、学校データの同期) からの入力を使用して自動的に作成する場合は、入力データが、命名ポリシーを構成した; に準拠していることを確認します。チームには、作成は失敗します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-115">If teams are created automatically by using the input from another system (for example, School Data Sync), verify that the input data complies with the naming policy you’ve configured; if it doesn’t, team creation will fail.</span></span>

## <a name="can-i-see-who-created-a-team"></a><span data-ttu-id="2ae5b-116">チームを作成したユーザーを表示できますか。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-116">Can I see who created a team?</span></span>

<span data-ttu-id="2ae5b-117">特定のチームを作成したユーザーについては、[マイクロソフトのチームでのイベントの監査ログの検索](audit-log-events.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-117">To find out who created a specific team, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="can-i-control-who-can-create-teams"></a><span data-ttu-id="2ae5b-118">チームを作成できるユーザーを制御できますか。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-118">Can I control who can create teams?</span></span>

<span data-ttu-id="2ae5b-119">一般に、チームを作成するを防ぐことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-119">In general, we recommend against preventing anyone from creating teams.</span></span> <span data-ttu-id="2ae5b-120">チームを作成できるすべてのユーザーは、チームが幅広く採用される可能性が高くします。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-120">If everyone can create teams, Teams is more likely to be widely adopted.</span></span> <span data-ttu-id="2ae5b-121">教員、教師、または受講者は、研究グループ、または特別な関心のグループを作成するのにチームを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-121">Faculty, teachers, or students can  use Teams to create study groups or special interest groups.</span></span> <span data-ttu-id="2ae5b-122">教室の内外に受け入れられるチームに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-122">This will help Teams be accepted inside and outside of the classroom.</span></span>

<span data-ttu-id="2ae5b-123">経験では、ユーザー教育により、担当するチームの使用率です。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-123">In our experience, user education helps ensure responsible Teams usage.</span></span> <span data-ttu-id="2ae5b-124">チームの作成ではないこと匿名のユーザーを理解するとすぐに、不注意に作成するは理解し、ツールの誤用をためらう傾向があります。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-124">As soon as users understand that creating teams isn’t anonymous, they understand the implications of carelessly creating them and tend to shy away from misusing the tool.</span></span>

<span data-ttu-id="2ae5b-125">チームを作成できるユーザーを制御することを確認する場合は、 [Office 365 のグループを作成できるユーザーの管理](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-125">If you’re sure you want to control who can create teams, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a><span data-ttu-id="2ae5b-126">自動的を作成する方法各コースのチーム、半期または四半期の先頭にしますか。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-126">How do I automatically create a team for each course at the beginning of the semester or quarter?</span></span>

<span data-ttu-id="2ae5b-127">、半期または四半期ごとの開始時に、多数の新しいチームを必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-127">At the start of each semester or quarter, you’ll need a number of new teams.</span></span> <span data-ttu-id="2ae5b-128">自動的にこれらのチームを作成して、適切なユーザーを設定して、適切なアクセス許可を設定するのには自動化されたアプローチを採用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-128">It might make sense to take an automated approach to create these teams automatically, populate them with the right users, and set the right permissions:</span></span>

-   <span data-ttu-id="2ae5b-129">学校のデータの同期は、Exchange Online と SharePoint オンライン、マイクロソフトのチームおよびクラスの OneNote ノートブックのクラスのチーム、教育、および rostering Intune と単一サインオン (SSO) の統合の他の多くの学校のグループに Office 365 のグループを作成できます。サード ・ パーティ製のアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-129">School Data Sync can create Office 365 Groups for Exchange Online and SharePoint Online, class teams for Microsoft Teams and OneNote Class notebooks, school groups for Intune for Education, and rostering and single sign-on (SSO) integration for many other third-party applications.</span></span> <span data-ttu-id="2ae5b-130">[学校のデータの同期の概要](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)で詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-130">Learn more at [Overview of School Data Sync](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).</span></span>
-   <span data-ttu-id="2ae5b-131">PowerShell のチームとのチャネルを作成および設定を構成する自動的にします。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-131">With PowerShell, you can create teams and channels, and configure settings automatically.</span></span> <span data-ttu-id="2ae5b-132">詳細については、[マイクロソフト チームの PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-132">See [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
-   <span data-ttu-id="2ae5b-133">(現在のベータ版) で Microsoft グラフ API を使用して、作成、構成、クローンを作成すると、およびチームをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-133">You can use the Microsoft Graph API (currently in beta) to create, configure, clone, and archive teams.</span></span> <span data-ttu-id="2ae5b-134">詳細については、[マイクロソフトのチームで作業するのには Microsoft のグラフの API を使用](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-134">See [Use the Microsoft Graph API to work with Microsoft Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="2ae5b-135">学校のデータの同期は、唯一の先生と生徒をクラス内では、そのクラスのメンバーを参照できるように、同期クラスと[非表示のグループ メンバーシップを有効にする](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945)ごとに、Office 365 のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-135">School Data Sync creates an Office 365 group for each class synced and [enables hidden group membership](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) so only teachers and students within the class can see the members of that class.</span></span> <span data-ttu-id="2ae5b-136">別のプロセスを使用して作成する場合、クラスのグループは、同じプライバシーの要件を満たすために新規 UnifiedGroup コマンドレットの HiddenGroupMembershipEnabled パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-136">If using a different process to create class groups use the HiddenGroupMembershipEnabled parameter of the New-UnifiedGroup cmdlet to meet the same privacy requirements.</span></span>

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a><span data-ttu-id="2ae5b-137">対処チームと共同で、半期または四半期が終了したときですか。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-137">How do I deal with teams when the semester or quarter ends?</span></span>

<span data-ttu-id="2ae5b-138">学校半期または四半期が上にあるとき、チームのデータを処理する方法についてまずと思われることをお勧めします。 削除するか、いつでも利用できる受講者のコースを行った後にでもするかどうか。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-138">We recommend that you first think about how you want to handle Teams data when the school semester or quarter is over: whether to delete it or keep it available for students even after they’ve completed the course.</span></span> <span data-ttu-id="2ae5b-139">学校カレンダーに留意してください任意のポリシーを設定するは、祝日と競合しないようにします。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-139">You’ll want to keep the school calendar in mind so any policies you set don’t conflict with holidays.</span></span> <span data-ttu-id="2ae5b-140">戦略を実装するのに次のツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-140">You can use the following tools to implement your strategy:</span></span>

-   <span data-ttu-id="2ae5b-141">**リテンション ・ ポリシー:**(の一部またはすべてのユーザー) のチャットやチャンネルから古いデータが削除されるかどうかを確認するのにように指定した年齢より古いすべてのデータを削除するのにには、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-141">**Retention policy:** Use this to delete all data older than an age you specify to make sure that old data is removed from chats (for all or some users) and channels.</span></span> <span data-ttu-id="2ae5b-142">削除できませんので、コンテンツを保持するチームを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-142">You can also configure Teams to retain content so it can’t be deleted.</span></span> <span data-ttu-id="2ae5b-143">詳細については、[マイクロソフトのチームのリテンション ・ ポリシー](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-143">For more information, see [Retention policies for Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).</span></span>
-   <span data-ttu-id="2ae5b-144">**の有効期限ポリシー:** 指定の日数後に期限切れにチームを構成します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-144">**Expiry policy:** Configure teams to expire after a certain number of days.</span></span> <span data-ttu-id="2ae5b-145">有効期限の前に 30 日間のチームは、更新する必要があることは、それ以外の場合に削除されます (ただし、管理者は、さらに 30 日間削除されたチームを回復することができます)、チームのすべての所有者に通知されます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-145">Thirty days before expiration, all owners of a team are notified that their team needs to be renewed, otherwise it will be deleted (though an administrator can recover deleted teams for an additional 30 days).</span></span> <span data-ttu-id="2ae5b-146">この設定は、未使用のチームが sunsetted であることを確認するため非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-146">This setting is very useful for making sure unused teams are sunsetted.</span></span> <span data-ttu-id="2ae5b-147">[Office 365 グループの有効期限ポリシー](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-147">Learn more at [Office 365 Group Expiration Policy](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).</span></span>

-   <span data-ttu-id="2ae5b-148">**チームのアーカイブ:** この設定は、読み取り専用モードにチームを配置します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-148">**Archive team:** This setting puts teams into read-only mode.</span></span> <span data-ttu-id="2ae5b-149">まだブラウズや検索しますが、誰の新しい投稿を追加できます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-149">They can still be browsed and searched, but no one can add any new posts.</span></span> <span data-ttu-id="2ae5b-150">[アーカイブまたは復元チーム](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)は、チームのオーナーがチームをアーカイブする方法について説明します。チームの所有者では、アーカイブまたはチームを復元するには[グラフの API (ベータ版)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)も使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-150">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) describes how team owners can archive a team; Team owners can also use the [Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) to archive or restore a team.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="2ae5b-151">Office 365 のグループの有効期限ポリシーを使用して、1 つまたは複数の Office 365 のグループのメンバーである個々 のユーザーの Azure Active Directory プレミアム P1 のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-151">Using the Office 365 Groups Expiration Policy requires Azure Active Directory Premium P1 licenses for each unique user that is a member of one or more Office 365 groups.</span></span>

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a><span data-ttu-id="2ae5b-152">チームを作成するときに使用する自分の学部のチーム テンプレートがありますか。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-152">Are there team templates for my faculty members to use when creating a team?</span></span>

<span data-ttu-id="2ae5b-153">はい。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-153">Yes.</span></span> <span data-ttu-id="2ae5b-154">新しいチームを作成するとき、ユーザーは**既存のテンプレートからチームを作成**を選択でき、チーム所有者も使用可能なテンプレートから新しいチームを作成する[グラフの API (ベータ版)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-154">Users can select **Create Team from existing template** when creating a new team, and Teams owners can also use the [Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) to create a new team from the available templates.</span></span>

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a><span data-ttu-id="2ae5b-155">どのようなタスクを自動化できます PowerShell またはグラフを使用してですか。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-155">What tasks can I automate via PowerShell or Graph?</span></span>

<span data-ttu-id="2ae5b-156">[Microsoft グラフ API (ベータ版)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)は、次に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-156">The [Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) can do the following:</span></span>

-   <span data-ttu-id="2ae5b-157">チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-157">Create a team.</span></span>
-   <span data-ttu-id="2ae5b-158">メンバーおよび所有者を追加します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-158">Add members and owners.</span></span>
-   <span data-ttu-id="2ae5b-159">チャンネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-159">Add channels.</span></span>
-   <span data-ttu-id="2ae5b-160">アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-160">Add apps.</span></span>
-   <span data-ttu-id="2ae5b-161">ショートカット既存のクローンを作成してこれらの手順は、チームとすぎるのタブを取得します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-161">Shortcut those steps by cloning an existing team, and get its tabs too.</span></span>
-   <span data-ttu-id="2ae5b-162">ユーザーのリンクを作成したチームに与えます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-162">Give the user a link to the team you just created.</span></span>
-   <span data-ttu-id="2ae5b-163">不要にするときは、メンバー、所有者、チャネル、およびアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-163">Remove members, owners, channels, and apps when you no longer need them.</span></span>
-   <span data-ttu-id="2ae5b-164">チームは、アクティブでなくなったときにアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-164">Archive the team when it's no longer active.</span></span> 
-   <span data-ttu-id="2ae5b-165">チームを削除します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-165">Delete the team.</span></span>
-   <span data-ttu-id="2ae5b-166">チャネルのスレッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-166">Create a channel thread</span></span>

<span data-ttu-id="2ae5b-167">[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)では、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-167">[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) can do the following:</span></span>

-   <span data-ttu-id="2ae5b-168">チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-168">Create a team.</span></span>
-   <span data-ttu-id="2ae5b-169">メンバーおよび所有者を追加します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-169">Add members and owners.</span></span>
-   <span data-ttu-id="2ae5b-170">チャンネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-170">Add channels.</span></span>
-   <span data-ttu-id="2ae5b-171">不要にするときは、メンバー、所有者、およびチャネルを削除します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-171">Remove members, owners, and channels when you no longer need them.</span></span>
-   <span data-ttu-id="2ae5b-172">チームを削除します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-172">Delete the team.</span></span>

> [!TIP]
> <span data-ttu-id="2ae5b-173">グラフ API および PowerShell コマンドレットは常に機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-173">The Graph API and PowerShell cmdlets are constantly adding functionality.</span></span> <span data-ttu-id="2ae5b-174">機能強化については、 [Microsoft グラフ API (ベータ版)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)および[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)の記事を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-174">Make sure to check the [Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) and [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) articles often for feature enhancements.</span></span>  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a><span data-ttu-id="2ae5b-175">教職員と学生へのアクセスがあるどのようなチームの機能を制御することができますか。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-175">Can I control what Teams features my faculty and students have access to?</span></span>

<span data-ttu-id="2ae5b-176">はい。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-176">Yes.</span></span> <span data-ttu-id="2ae5b-177">ポリシーを使用してコントロール特定のメッセージ、会議、通話、およびライブ イベントの機能をユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-177">You can use policies to control specific messaging, meeting, calling, and live event features your users have access to.</span></span> <span data-ttu-id="2ae5b-178">テナント全体の設定を使用して、すべてに同じ設定を適用したり、必要な場合は、ユーザー レベルのポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-178">You can use tenant-wide settings to apply the same settings to all, or apply user-level policies if required.</span></span> 

<span data-ttu-id="2ae5b-179">チームのポリシーの詳細については、 [Office 365 の組織での Microsoft チームの管理機能](enable-features-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-179">For more details about Teams policies, see [Manage Microsoft Teams features in your Office 365 organization](enable-features-office-365.md).</span></span>
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a><span data-ttu-id="2ae5b-180">どのような外部の関係者が自分の教職員と学生との共同作業を制御することができますか。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-180">Can I control what external parties my faculty and students collaborate with?</span></span>

<span data-ttu-id="2ae5b-181">ゲスト アクセスを使用するには、テナントは、共同研究や講義のゲストの役に立ちますの外部からのユーザーを招待します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-181">You can use guest access to invite users from outside of your tenant, which can be useful for research collaboration or guest lectures:</span></span>

-   <span data-ttu-id="2ae5b-182">許可またはブロックの来園者が自分のドメインのドメイン whitelisting を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-182">Use domain whitelisting to allow or block guests based on their domain.</span></span>
-   <span data-ttu-id="2ae5b-183">特定の Office 365 のグループとチームは、来園者を招待チーム (とできることはできません) を制御するためのゲスト アクセスのオンとオフをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-183">Turn guest access on and off for particular Office 365 Groups and teams, to control which teams can (and can’t) invite guests.</span></span>
-   <span data-ttu-id="2ae5b-184">来園者の招待を送信するアラートを表示するのにには、監査ログを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-184">Use the audit log to see which alerts were sent to invited guests.</span></span>

<span data-ttu-id="2ae5b-185">詳細については、 [Office 365 のグループでのゲスト アクセス](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-185">For more information, see [Guest access in Office 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).</span></span>

## <a name="what-information-can-i-review-about-existing-teams"></a><span data-ttu-id="2ae5b-186">既存チームについて確認できる情報</span><span class="sxs-lookup"><span data-stu-id="2ae5b-186">What information can I review about existing teams?</span></span>

<span data-ttu-id="2ae5b-187">監査ログを参照して確認できます。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-187">You can check the audit logs to see:</span></span>

-   <span data-ttu-id="2ae5b-188">ユーザーは、どのチームにゲストとして招待されました。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-188">Who was invited as a guest to which team.</span></span>
-   <span data-ttu-id="2ae5b-189">チームを作成したユーザーです。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-189">Who created which team.</span></span>

<span data-ttu-id="2ae5b-190">詳細については、[マイクロソフトのチームでのイベントの監査ログの検索](audit-log-events.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-190">For more information, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a><span data-ttu-id="2ae5b-191">チームがこれほど迅速に進化します。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-191">Teams evolves so quickly.</span></span> <span data-ttu-id="2ae5b-192">最新の状態にする方法はでしょうか。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-192">How can I stay up-to-date?</span></span>

<span data-ttu-id="2ae5b-193">チームの最新の更新プログラムを取得するのには次のリソースをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2ae5b-193">We recommend the following resources to get the latest updates on Teams:</span></span>

-   [<span data-ttu-id="2ae5b-194">マイクロソフト チームの新機能</span><span class="sxs-lookup"><span data-stu-id="2ae5b-194">What's new in Microsoft Teams</span></span>](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [<span data-ttu-id="2ae5b-195">マイクロソフト チームのブログ</span><span class="sxs-lookup"><span data-stu-id="2ae5b-195">Microsoft Teams blog</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
