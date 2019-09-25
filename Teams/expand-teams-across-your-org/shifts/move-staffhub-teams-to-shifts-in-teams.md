---
title: 'StaffHub teams を Microsoft Teams の Shifts に移動する '
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub teams を移動して、Microsoft Teams のシフトにデータをスケジュールする方法について説明します。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf9776dbf5a5992354f542436b4904d53d58508
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142047"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="6a5de-103">Microsoft Teams で Microsoft StaffHub teams をシフトに移行する</span><span class="sxs-lookup"><span data-stu-id="6a5de-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a5de-104">2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="6a5de-105">Microsoft Teams で StaffHub 機能を構築しています。</span><span class="sxs-lookup"><span data-stu-id="6a5de-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="6a5de-106">現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="6a5de-107">2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="6a5de-108">StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="6a5de-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="6a5de-110">Teams のシフトアプリは、スケジュールを管理するための簡単なアプローチを提供します。また、1日のうちに発生するシフト交換とキャンセルの流れを定期的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="6a5de-111">チームメンバーは、アプリやデバイス間で直接、スケジュールとシフト情報にアクセスして、ユーザー設定の設定、スケジュールの管理、休暇のリクエストを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="6a5de-112">この記事では、組織の StaffHub teams を移動して、チーム内のシフトにデータをスケジュールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="6a5de-113">次の内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-113">It covers:</span></span>

- [<span data-ttu-id="6a5de-114">Teams への移行について知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="6a5de-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="6a5de-115">備える</span><span class="sxs-lookup"><span data-stu-id="6a5de-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="6a5de-116">パイロットの実施</span><span class="sxs-lookup"><span data-stu-id="6a5de-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="6a5de-117">パイロット以外の場所に移動して、すべての StaffHub teams を移動する</span><span class="sxs-lookup"><span data-stu-id="6a5de-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="6a5de-118">チームの利用状況を監視する</span><span class="sxs-lookup"><span data-stu-id="6a5de-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="6a5de-119">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6a5de-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="6a5de-120">1人または2人の StaffHub チームを持つ小規模企業でも、数百人の StaffHub teams を持つ大企業でも、チームへの移行を成功させるために必要な管理ガイダンスが記載されています。</span><span class="sxs-lookup"><span data-stu-id="6a5de-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="6a5de-121">この記事の手順を実行するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="6a5de-122">まだインストールしていない場合は、 [StaffHub 定年](microsoft-staffhub-to-be-retired.md)に関する faq を参照して、お客様からの質問に回答してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="6a5de-123">Teams への移行について知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="6a5de-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="6a5de-124">Teams に移動する場合</span><span class="sxs-lookup"><span data-stu-id="6a5de-124">When to move to Teams</span></span>

<span data-ttu-id="6a5de-125">2019年10月1日、StaffHub は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="6a5de-126">今すぐ Teams の使用を開始して、組織のチームとユーザーを StaffHub から移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a5de-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="6a5de-127">StaffHub でスケジュール管理が最も一般的に使用される機能である場合は、チームでのシフトアプリの使用を進めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a5de-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="6a5de-128">Teams に移動されるもの</span><span class="sxs-lookup"><span data-stu-id="6a5de-128">What is moved to Teams</span></span>

<span data-ttu-id="6a5de-129">StaffHub チームを移動すると、チームメンバーシップ、ユーザーの詳細、チームのスケジュール、チャットデータが Teams に移動します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="6a5de-130">StaffHub チームを移動すると、ファイルが移動されません。</span><span class="sxs-lookup"><span data-stu-id="6a5de-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="6a5de-131">StaffHub チームに、teams にも移動するファイルが含まれている場合は、ファイルを別の手順で移動します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="6a5de-132">すべての StaffHub チームには、対応する Office 365 グループが必要です。</span><span class="sxs-lookup"><span data-stu-id="6a5de-132">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="6a5de-133">StaffHub チームに Office 365 グループが関連付けられていない場合は、移行をサポートするために、1つが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-133">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="6a5de-134">Teams と StaffHub の間でのチームとグループの名前の違いにより、Teams に異なるチーム名が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-134">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="6a5de-135">チームを StaffHub から Teams に移行すると、ユーザーは StaffHub のスケジュールにアクセスできなくなり、Teams のシフトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-135">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="6a5de-136">この変更を組織全体で伝達することをお勧めします。中断を最小限に抑え、ユーザーにチームの採用と検討を促します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-136">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="6a5de-137">Azure AD Premium を使用している場合は、[レポートを実行](run-report-to-show-staffhub-usage.md)して、この変更について知っておく必要がある、組織内の StaffHub ユーザーの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-137">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="6a5de-138">StaffHub チームを Teams に移動しても、ロールバックオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="6a5de-138">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="6a5de-139">チームを移動するときのユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="6a5de-139">User experience when you move a team</span></span>

<span data-ttu-id="6a5de-140">チームの StaffHub からシフトへの切り替えが発生した場合、ユーザーに対してダウンタイム (1 秒未満) が最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-140">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="6a5de-141">チームへの移動が完了するまで、ユーザーは StaffHub を引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-141">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="6a5de-142">移動が完了すると、チームメンバーにメッセージが表示され、チームのスケジュールにアクセスするためにチームのシフトの使用を開始する必要があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-142">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="6a5de-143">ここでは、StaffHub チームが Teams に移動した後に StaffHub に表示されるメッセージの例を示します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-143">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="6a5de-144">![ユーザーに表示されるメッセージの例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "StaffHub チームが Teams に移動した後に StaffHub に表示されるメッセージの例")</span><span class="sxs-lookup"><span data-stu-id="6a5de-144">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="6a5de-145">備える</span><span class="sxs-lookup"><span data-stu-id="6a5de-145">Prepare</span></span>

<span data-ttu-id="6a5de-146">ここでは、Teams への移行を準備する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-146">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="6a5de-147">前提条件が満たされていることを確認する</span><span class="sxs-lookup"><span data-stu-id="6a5de-147">Check that prerequisites are met</span></span>

<span data-ttu-id="6a5de-148">StaffHub チームを Teams に移動する前に、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-148">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="6a5de-149">サインインしたユーザーはグローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="6a5de-149">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="6a5de-150">チームは、テナント内のすべてのユーザーに対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6a5de-150">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="6a5de-151">テナントで Office 365 グループの作成が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6a5de-151">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="6a5de-152">StaffHub teamId が有効です。</span><span class="sxs-lookup"><span data-stu-id="6a5de-152">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="6a5de-153">StaffHub チームにはメンバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6a5de-153">The StaffHub team contains members.</span></span>
- <span data-ttu-id="6a5de-154">すべての StaffHub チームメンバーは、Azure AD アカウントにリンクされています。</span><span class="sxs-lookup"><span data-stu-id="6a5de-154">All StaffHub team members are linked to an Azure AD account.</span></span>

<span data-ttu-id="6a5de-155">これらの前提条件が満たされない場合、移動要求は失敗します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-155">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="6a5de-156">Teams のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6a5de-156">Assign Teams licenses</span></span>

<span data-ttu-id="6a5de-157">各ユーザーは、ライセンス付与された有効な Microsoft 365 または Office 365 ライセンスを所有している必要があります。[また、Teams](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-157">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="6a5de-158">Teams ライセンスをユーザーに割り当てると、チームにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-158">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="6a5de-159">Teams のライセンスは、Microsoft 365 管理センターで管理します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-159">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6a5de-160">詳細については、「[チームへのユーザーアクセスを管理](../../user-access.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-160">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6a5de-161">組織で Skype for Business を使用していて、すべてのユーザーをチームに移行する準備ができていない場合は、最初に Skype for Business を使用してチームを実行できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-161">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="6a5de-162">この共存モード (*孤島*) では、各クライアントアプリは個別のソリューションとして動作します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-162">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="6a5de-163">詳細については、「[チームと Skype For business の共存と相互運用性につい](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-163">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a><span data-ttu-id="6a5de-164">プレリリース版の StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="6a5de-164">Install the prerelease version of the StaffHub PowerShell module</span></span>

<span data-ttu-id="6a5de-165">まだインストールしていない場合は、[プレリリース版の StaffHub PowerShell モジュールをインストール](install-the-staffhub-powershell-module.md)します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-165">If you haven't already, [install the prerelease version of the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

<span data-ttu-id="6a5de-166">StaffHub teams を Teams に移行するには、プレリリース版のモジュールがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-166">You must have the prerelease version of the module installed to move your StaffHub teams to Teams.</span></span>

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="6a5de-167">StaffHub チームメンバーがない場合に、Azure AD アカウントをリンクさせる</span><span class="sxs-lookup"><span data-stu-id="6a5de-167">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="6a5de-168">各 StaffHub チームメンバーは、Azure Active Directory (Azure AD) アカウントにリンクされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-168">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="6a5de-169">次のシナリオのいずれかが適用されている場合、組織内のユーザーは Azure AD アカウントにリンクされません。</span><span class="sxs-lookup"><span data-stu-id="6a5de-169">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="6a5de-170">チーム所有者が、Azure AD アカウントを持っていないユーザーを追加しました。</span><span class="sxs-lookup"><span data-stu-id="6a5de-170">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="6a5de-171">チーム所有者が、ユーザーを StaffHub チームに招待し、そのユーザーが招待を承諾しなかった。</span><span class="sxs-lookup"><span data-stu-id="6a5de-171">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="6a5de-172">これらのユーザーに Azure AD アカウントをリンクさせることができます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-172">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="6a5de-173">これを行うには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-173">Here's how.</span></span>

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-linked-to-an-azure-ad-account"></a><span data-ttu-id="6a5de-174">Azure AD アカウントにリンクされていないチームメンバーを持つ StaffHub teams 上のすべてのユーザーの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="6a5de-174">Get a list of all users on StaffHub teams that have team members that aren't linked to an Azure AD account</span></span>

<span data-ttu-id="6a5de-175">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-175">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="link-the-account"></a><span data-ttu-id="6a5de-176">アカウントをリンクする</span><span class="sxs-lookup"><span data-stu-id="6a5de-176">Link the account</span></span>

<span data-ttu-id="6a5de-177">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6a5de-177">Do one of the following:</span></span>

- <span data-ttu-id="6a5de-178">アカウントを変換してリンクします。</span><span class="sxs-lookup"><span data-stu-id="6a5de-178">Convert and link the account.</span></span>

  <span data-ttu-id="6a5de-179">StaffHub チーム所有者と管理者は、ユーザーのメールアドレスを StaffHub チームの設定ページで有効な UPN に変更することによって、非アクティブなアカウントを変換し、StaffHub の Azure AD アカウントにリンクすることができます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-179">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="6a5de-180">リンクされていないアカウントを削除し、UPN を使用してアカウントをもう一度追加します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-180">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="6a5de-181">StaffHub チームからプロビジョニングされていないアカウントを削除するには、 [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-181">Run the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="6a5de-182">UPN を使用して StaffHub チームにアカウントを戻すには、 [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-182">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="6a5de-183">リンクされていないユーザーアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-183">Remove the unlinked user account.</span></span> <span data-ttu-id="6a5de-184">このオプションを使用すると、ユーザーアカウントは不要になります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-184">Use this option the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="6a5de-185">FirstlineWorker アプリのセットアップポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="6a5de-185">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="6a5de-186">Teams には、組織内の最初の社員にとって最も重要なアプリを強調表示するために、チームをカスタマイズするために使用できる、標準の Lineworker アプリのセットアップポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6a5de-186">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="6a5de-187">このポリシーをユーザーに割り当てると、ポリシーに含まれるアプリが、すばやく簡単にアクセスできるように Teams のアプリバーに固定されます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-187">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="6a5de-188">他のチームに追加されたアプリは、[...] をクリックしてアプリバーに表示されます。 \*\*\*\* Teams のデスクトップと web クライアントでのアプリの増加、および teams のモバイルクライアントでの追加アプリ。</span><span class="sxs-lookup"><span data-stu-id="6a5de-188">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="6a5de-189">既定では、FirstlineWorker アプリのセットアップポリシーには、アクティビティ、シフト、チャット、通話アプリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-189">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="6a5de-190">FirstlineWorker アプリのセットアップポリシーをユーザーに割り当てる手順については、「 [firstlineworker アプリのセットアップポリシーを使用してチームへのシフトを固定](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-190">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="6a5de-191">ポリシーを割り当てた後は、最長24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-191">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="6a5de-192">StaffHub teams とユーザーを Teams に移行する前に、少なくとも1週間以上この手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a5de-192">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="6a5de-193">ユーザーが Teams を使用している場合は、シフトアプリを表示してアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-193">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="6a5de-194">また、カスタムアプリセットアップポリシーを作成して、グローバルアプリセットアップポリシーの設定を編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-194">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="6a5de-195">詳細については、「[Teams でアプリの設定ポリシーを管理する](../../teams-app-setup-policies.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-195">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="6a5de-196">チームへのオンボードユーザー</span><span class="sxs-lookup"><span data-stu-id="6a5de-196">Onboard users to Teams</span></span>

<span data-ttu-id="6a5de-197">オンボード戦略の一環として、チームに慣れてもらうためのトレーニングとガイダンスをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-197">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="6a5de-198">次のリソースをユーザーと共有して、チームのクライアント、トレーニング、サポートを取得する場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-198">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="6a5de-199">Teams の Web クライアント</span><span class="sxs-lookup"><span data-stu-id="6a5de-199">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="6a5de-200">デスクトップとモバイル クライアントのダウンロード リンク</span><span class="sxs-lookup"><span data-stu-id="6a5de-200">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="6a5de-201">Teams のトレーニング用ビデオ</span><span class="sxs-lookup"><span data-stu-id="6a5de-201">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="6a5de-202">Teams のヘルプ ドキュメント</span><span class="sxs-lookup"><span data-stu-id="6a5de-202">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="6a5de-203">チームを展開してチームを導入するためのガイダンスについては、「チームをロールアウトして[チームを採用](../../adopt-microsoft-teams-landing-page.md)[する方法](../../How-to-roll-out-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-203">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="6a5de-204">パイロットの実施</span><span class="sxs-lookup"><span data-stu-id="6a5de-204">Conduct a pilot</span></span>

<span data-ttu-id="6a5de-205">最初に、2つまたは3つの StaffHub teams を、最早採用者のグループごとに移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a5de-205">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="6a5de-206">パイロットを実行すると、移行計画を調整して、組織のすべての StaffHub チームをチームに移行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-206">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="6a5de-207">また、組織全体での導入を促進できるエキスパートも特定します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-207">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="6a5de-208">段階的アプローチを必要としない小規模企業の場合は、このセクションの手順に従って、StaffHub から Teams に切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-208">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="6a5de-209">パイロットチームの特定</span><span class="sxs-lookup"><span data-stu-id="6a5de-209">Identify pilot teams</span></span>

<span data-ttu-id="6a5de-210">パイロットチームの2つまたは3つを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-210">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="6a5de-211">すべてのチームメンバーは、チームでシフトを使用して、スケジュールを管理し、相互に通信して共同作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-211">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="6a5de-212">チームのチャンピオンの特定</span><span class="sxs-lookup"><span data-stu-id="6a5de-212">Identify team champions</span></span>

<span data-ttu-id="6a5de-213">パイロットチーム全体のチャンピオンを特定し、啓蒙シフトを支援するために参加します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-213">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="6a5de-214">チームの支持者は、チームメンバーのサポートとガイダンスを提供するために、独自の高い知識を共有しています。</span><span class="sxs-lookup"><span data-stu-id="6a5de-214">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="6a5de-215">チームチャンピオンはチームの所有者または管理者になることができます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-215">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="6a5de-216">チームのメンバーがチームの[クライアントを取得](../../get-clients.md)し、teams にサインインして、スケジュールをシフトで確認し、互いにチャットを開始するためには、チームメンバーが設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-216">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="6a5de-217">すでに StaffHub に慣れているユーザーは、シフトですぐに稼動することになります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-217">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="6a5de-218">その他のヘルプについては、[[シフトヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)] をポイントすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-218">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="6a5de-219">StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="6a5de-219">Move a StaffHub team</span></span>

<span data-ttu-id="6a5de-220">次の手順を使用して、一度に1つの StaffHub チームを移動します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-220">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="6a5de-221">パイロットチームでは、この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a5de-221">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="6a5de-222">後で、組織のすべての StaffHub チームを移行する準備ができたら、「複数のチームを一度に移動する」の手順については、「 [StaffHub teams を移行](#move-your-staffhub-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-222">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="6a5de-223">StaffHub チームを移動するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-223">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="6a5de-224">次</span><span class="sxs-lookup"><span data-stu-id="6a5de-224">Example:</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="6a5de-225">次に示すのは、StaffHub チームを Teams に移動する要求を送信するときに表示される応答の例です。</span><span class="sxs-lookup"><span data-stu-id="6a5de-225">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="6a5de-226">移動要求の状態を確認するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-226">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="6a5de-227">次</span><span class="sxs-lookup"><span data-stu-id="6a5de-227">Example:</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="6a5de-228">次に示すのは、移動が進行中の場合に表示される応答の例です。</span><span class="sxs-lookup"><span data-stu-id="6a5de-228">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="6a5de-229">StaffHub チームから Teams にファイルを移動する</span><span class="sxs-lookup"><span data-stu-id="6a5de-229">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="6a5de-230">この手順は、Teams に移動した StaffHub チームが、Teams にも移動するファイルを持っている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-230">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="6a5de-231">SharePoint Online または PowerShell を使用して、ファイルを直接移動できます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-231">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="6a5de-232">SharePoint Online の場合</span><span class="sxs-lookup"><span data-stu-id="6a5de-232">In SharePoint Online</span></span>

<span data-ttu-id="6a5de-233">[SharePoint Online でファイルを移動する方法に](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)ついて説明します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-233">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="6a5de-234">PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="6a5de-234">Using PowerShell</span></span>

<span data-ttu-id="6a5de-235">[SharePoint Online 管理シェル](https://www.microsoft.com/download/details.aspx?id=35588)をダウンロードしてインストールします (まだインストールしていない場合)。</span><span class="sxs-lookup"><span data-stu-id="6a5de-235">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="6a5de-236">ファイルを移動するために必要なコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6a5de-236">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="6a5de-237">[Connect-admin.sharepoint.com](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps)コマンドレットを使用して、SharePoint Online チームサイトに接続します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-237">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="6a5de-238">StaffHub から Teams に移動する各ファイルについて、 [PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile)コマンドレットを使用してファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-238">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="6a5de-239">複数のファイルを移動するには、ファイルをループして、ループの2番目のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-239">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="6a5de-240">セッションがアクティブな場合は、最初のコマンドを繰り返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6a5de-240">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="6a5de-241">パイロット以外の場所に移動して、すべての StaffHub teams を移動する</span><span class="sxs-lookup"><span data-stu-id="6a5de-241">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="6a5de-242">認識を高める</span><span class="sxs-lookup"><span data-stu-id="6a5de-242">Raise awareness</span></span>

<span data-ttu-id="6a5de-243">パイロットチームを超えて組織の StaffHub チームをチームに移行する準備ができたら、まず組織全体で変更を伝えることが重要です。</span><span class="sxs-lookup"><span data-stu-id="6a5de-243">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="6a5de-244">シフトについての単語を広げ、チームへの切り替えを行って、認知度を上げ、興奮を生み出し、導入を推進します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-244">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="6a5de-245">StaffHub teams を移動する</span><span class="sxs-lookup"><span data-stu-id="6a5de-245">Move your StaffHub teams</span></span>

<span data-ttu-id="6a5de-246">次の手順を使用して、StaffHub teams をまとめて移動します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-246">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="6a5de-247">組織のすべての StaffHub チームを移動するか、または特定の StaffHub teams を移動するかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-247">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="6a5de-248">StaffHub teams を1つずつ移動する方法については、「 [StaffHub チームを移行](#move-a-staffhub-team)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-248">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="6a5de-249">すべての StaffHub teams を移動する</span><span class="sxs-lookup"><span data-stu-id="6a5de-249">Move all StaffHub teams</span></span>

<span data-ttu-id="6a5de-250">組織内のすべての StaffHub teams の一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-250">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

<span data-ttu-id="6a5de-251">次に、次のことを実行してすべてのチームを移動します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-251">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="6a5de-252">応答の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-252">Here's an example of the response.</span></span>

<span data-ttu-id="6a5de-253">既に Teams に移動されているか、Teams に既に存在しているチームの場合は、そのチームに移動するためにジョブを送信する必要がないため、jobId は "null" になります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-253">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="6a5de-254">特定の StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="6a5de-254">Move specific StaffHub teams</span></span>

<span data-ttu-id="6a5de-255">組織内のすべての StaffHub チーム Id の一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-255">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="6a5de-256">前に実行した`Get-StaffHubteamsForTenant`コマンドレットによって返された結果で、移動するチーム id を選択し、コンマ区切り値 (CSV) ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-256">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="6a5de-257">CSV ファイルを書式設定する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-257">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="6a5de-258">Id</span><span class="sxs-lookup"><span data-stu-id="6a5de-258">Id</span></span>  |
|---------|
|<span data-ttu-id="6a5de-259">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="6a5de-259">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="6a5de-260">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="6a5de-260">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="6a5de-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="6a5de-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="6a5de-262">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="6a5de-262">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="6a5de-263">CSV ファイルを作成したら、CSV ファイルで指定したチームを移動するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-263">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="6a5de-264">StaffHub teams が Teams に移行されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="6a5de-264">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="6a5de-265">組織内のすべてのチームの一覧を取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-265">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="6a5de-266">StaffHub teams から Teams にファイルを移動する</span><span class="sxs-lookup"><span data-stu-id="6a5de-266">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="6a5de-267">移動した StaffHub teams に、Teams にも移動するファイルが含まれている場合は、「 [StaffHub チームからチームにファイルを移動](#move-files-from-a-staffhub-team-to-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-267">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="6a5de-268">チームの利用状況を監視する</span><span class="sxs-lookup"><span data-stu-id="6a5de-268">Monitor Teams usage</span></span>

<span data-ttu-id="6a5de-269">利用状況レポートは、使用パターンをより理解しやすくするのに役立ちます。また、組織全体でトレーニングとコミュニケーション作業の優先順位を決定する場所について理解を深めます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-269">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="6a5de-270">チーム全体の利用状況、ユーザーが Teams で実行するアクティビティの種類、ユーザーが Teams に接続する方法などのレポートを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6a5de-270">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="6a5de-271">詳細については、microsoft [teams 管理センターのチームレポート](../../teams-analytics-and-reports/teams-reporting-reference.md)と、 [microsoft 365 管理センターの teams アクティビティレポート](../../teams-activity-reports.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-271">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6a5de-272">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6a5de-272">Troubleshooting</span></span>

<span data-ttu-id="6a5de-273">**StaffHub から Teams にファイルを移動しようとすると、"アクセス許可は拒否されました" というエラーメッセージが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="6a5de-273">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="6a5de-274">この問題は、自分がメンバーでないプライベートの Office 365 グループでファイルを移動しようとしている場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="6a5de-274">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="6a5de-275">この場合は、 [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember)コマンドレットを使用して StaffHub チームに自分を追加してから、ファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-275">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="6a5de-276">ファイルを移動した後、 [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember)コマンドレットを使用してチームから自分自身を削除します。</span><span class="sxs-lookup"><span data-stu-id="6a5de-276">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="6a5de-277">**StaffHub から Teams にファイルを移動しようとすると、[全般] フォルダーが存在しないというエラーが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="6a5de-277">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="6a5de-278">次のコマンドを実行して、[全般] フォルダーを SharePoint に追加してから、もう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="6a5de-278">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="6a5de-279">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6a5de-279">Related topics</span></span>
- [<span data-ttu-id="6a5de-280">Microsoft Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="6a5de-280">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="6a5de-281">Microsoft StaffHub はまもなく廃止予定です</span><span class="sxs-lookup"><span data-stu-id="6a5de-281">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="6a5de-282">Microsoft Teams で組織のシフト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="6a5de-282">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="6a5de-283">StaffHub PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="6a5de-283">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
