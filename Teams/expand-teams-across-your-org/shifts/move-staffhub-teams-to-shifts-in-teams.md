---
title: 'StaffHub teams を Microsoft Teams の Shifts に移動する '
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub teams を移動して、Microsoft Teams のシフトにデータをスケジュールする方法について説明します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780810"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="9a039-103">Microsoft Teams で Microsoft StaffHub teams をシフトに移行する</span><span class="sxs-lookup"><span data-stu-id="9a039-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a039-104">2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="9a039-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="9a039-105">Microsoft Teams で StaffHub 機能を構築しています。</span><span class="sxs-lookup"><span data-stu-id="9a039-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="9a039-106">現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。</span><span class="sxs-lookup"><span data-stu-id="9a039-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="9a039-107">2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="9a039-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="9a039-108">StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9a039-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="9a039-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="9a039-110">Teams のシフトアプリは、スケジュールを管理するための簡単なアプローチを提供します。また、1日のうちに発生するシフト交換とキャンセルの流れを定期的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9a039-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="9a039-111">チームメンバーは、アプリやデバイス間で直接、スケジュールとシフト情報にアクセスして、ユーザー設定の設定、スケジュールの管理、休暇のリクエストを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9a039-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="9a039-112">この記事では、組織の StaffHub teams を移動して、チーム内のシフトにデータをスケジュールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a039-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="9a039-113">次の内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a039-113">It covers:</span></span>

- [<span data-ttu-id="9a039-114">Teams への移行について知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="9a039-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="9a039-115">備える</span><span class="sxs-lookup"><span data-stu-id="9a039-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="9a039-116">パイロットの実施</span><span class="sxs-lookup"><span data-stu-id="9a039-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="9a039-117">パイロット以外の場所に移動して、すべての StaffHub teams を移動する</span><span class="sxs-lookup"><span data-stu-id="9a039-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="9a039-118">チームの利用状況を監視する</span><span class="sxs-lookup"><span data-stu-id="9a039-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="9a039-119">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9a039-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="9a039-120">1人または2人の StaffHub チームを持つ小規模企業でも、数百人の StaffHub teams を持つ大企業でも、チームへの移行を成功させるために必要な管理ガイダンスが記載されています。</span><span class="sxs-lookup"><span data-stu-id="9a039-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="9a039-121">この記事の手順を実行するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a039-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="9a039-122">まだインストールしていない場合は、 [StaffHub 定年](microsoft-staffhub-to-be-retired.md)に関する faq を参照して、お客様からの質問に回答してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="9a039-123">Teams への移行について知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="9a039-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="9a039-124">Teams に移動する場合</span><span class="sxs-lookup"><span data-stu-id="9a039-124">When to move to Teams</span></span>

<span data-ttu-id="9a039-125">2019年10月1日、StaffHub は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="9a039-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="9a039-126">今すぐ Teams の使用を開始して、組織のチームとユーザーを StaffHub から移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9a039-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="9a039-127">StaffHub でスケジュール管理が最も一般的に使用される機能である場合は、チームでのシフトアプリの使用を進めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9a039-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="9a039-128">Teams に移動されるもの</span><span class="sxs-lookup"><span data-stu-id="9a039-128">What is moved to Teams</span></span>

<span data-ttu-id="9a039-129">ユーザの詳細、スケジュール情報、チャットとファイルデータは Teams に移行されます。</span><span class="sxs-lookup"><span data-stu-id="9a039-129">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="9a039-130">これには、チームメンバーシップ、チームのスケジュール、および過去90日間のチャットとファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9a039-130">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="9a039-131">すべての StaffHub チームには、対応する Office 365 グループが必要です。</span><span class="sxs-lookup"><span data-stu-id="9a039-131">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="9a039-132">StaffHub チームに Office 365 グループが関連付けられていない場合は、移行をサポートするために、1つが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="9a039-132">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="9a039-133">Teams と StaffHub の間でのチームとグループの名前の違いにより、Teams に異なるチーム名が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="9a039-133">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="9a039-134">チームを StaffHub から Teams に移行すると、ユーザーは StaffHub のスケジュールにアクセスできなくなり、Teams のシフトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="9a039-134">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="9a039-135">この変更を組織全体で伝達することをお勧めします。中断を最小限に抑え、ユーザーにチームの採用と検討を促します。</span><span class="sxs-lookup"><span data-stu-id="9a039-135">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="9a039-136">Azure AD Premium を使用している場合は、[レポートを実行](run-report-to-show-staffhub-usage.md)して、この変更について知っておく必要がある、組織内の StaffHub ユーザーの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="9a039-136">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="9a039-137">StaffHub チームを Teams に移動しても、ロールバックオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="9a039-137">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="9a039-138">チームを移動するときのユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="9a039-138">User experience when you move a team</span></span>

<span data-ttu-id="9a039-139">チームの StaffHub からシフトへの切り替えが発生した場合、ユーザーに対してダウンタイム (1 秒未満) が最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="9a039-139">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="9a039-140">チームへの移動が完了するまで、ユーザーは StaffHub を引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9a039-140">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="9a039-141">移動が完了すると、チームメンバーにメッセージが表示され、チームのスケジュールにアクセスするためにチームのシフトの使用を開始する必要があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="9a039-141">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="9a039-142">ここでは、StaffHub チームが Teams に移動した後に StaffHub に表示されるメッセージの例を示します。</span><span class="sxs-lookup"><span data-stu-id="9a039-142">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="9a039-143">![ユーザーに表示されるメッセージの例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "StaffHub チームが Teams に移動した後に StaffHub に表示されるメッセージの例")</span><span class="sxs-lookup"><span data-stu-id="9a039-143">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="9a039-144">備える</span><span class="sxs-lookup"><span data-stu-id="9a039-144">Prepare</span></span>

<span data-ttu-id="9a039-145">ここでは、Teams への移行を準備する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a039-145">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="9a039-146">前提条件が満たされていることを確認する</span><span class="sxs-lookup"><span data-stu-id="9a039-146">Check that prerequisites are met</span></span>

<span data-ttu-id="9a039-147">StaffHub チームを Teams に移動する前に、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-147">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="9a039-148">サインインしたユーザーはグローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="9a039-148">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="9a039-149">チームは、テナント内のすべてのユーザーに対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9a039-149">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="9a039-150">テナントで Office 365 グループの作成が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9a039-150">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="9a039-151">StaffHub teamId が有効です。</span><span class="sxs-lookup"><span data-stu-id="9a039-151">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="9a039-152">StaffHub チームにはメンバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9a039-152">The StaffHub team contains members.</span></span> 
- <span data-ttu-id="9a039-153">すべての StaffHub チームメンバーは、Azure AD アカウントにリンクされています。</span><span class="sxs-lookup"><span data-stu-id="9a039-153">All StaffHub team members are linked to an Azure AD account.</span></span> 

<span data-ttu-id="9a039-154">これらの前提条件が満たされない場合、移動要求は失敗します。</span><span class="sxs-lookup"><span data-stu-id="9a039-154">If these prerequisites aren't met, the move request will fail.</span></span> 

### <a name="assign-teams-licenses"></a><span data-ttu-id="9a039-155">Teams のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9a039-155">Assign Teams licenses</span></span>

<span data-ttu-id="9a039-156">各ユーザーは、ライセンス付与された有効な Microsoft 365 [](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)または Office 365 ライセンスを所有している必要があります。また、Teams ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a039-156">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="9a039-157">Teams ライセンスをユーザーに割り当てると、チームにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9a039-157">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="9a039-158">Teams のライセンスは、Microsoft 365 管理センターで管理します。</span><span class="sxs-lookup"><span data-stu-id="9a039-158">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9a039-159">詳細については、「[チームへのユーザーアクセスを管理](../../user-access.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-159">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9a039-160">組織で Skype for Business を使用していて、すべてのユーザーをチームに移行する準備ができていない場合は、最初に Skype for Business を使用してチームを実行できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9a039-160">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="9a039-161">この共存モード (*孤島*) では、各クライアントアプリは個別のソリューションとして動作します。</span><span class="sxs-lookup"><span data-stu-id="9a039-161">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="9a039-162">詳細については、「[チームと Skype For business の共存と相互運用性につい](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-162">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="9a039-163">StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="9a039-163">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="9a039-164">まだインストールしていない場合は、 [StaffHub PowerShell モジュールをインストール](install-the-staffhub-powershell-module.md)します。</span><span class="sxs-lookup"><span data-stu-id="9a039-164">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="9a039-165">Azure AD で id を持っていない StaffHub ユーザーのアカウントをプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="9a039-165">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="9a039-166">各マネージャーとチームメンバーは、Azure Active Directory (Azure AD) で id を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a039-166">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="9a039-167">ユーザーがまだ Azure AD で id を持っていない場合は、アカウントをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="9a039-167">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="9a039-168">これを行うには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a039-168">Here's how.</span></span> 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a><span data-ttu-id="9a039-169">Azure AD アカウントでプロビジョニングされていないチームメンバーを持つ StaffHub teams 上のすべてのユーザーの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="9a039-169">Get a list of all users on StaffHub teams that have team members that aren't provisioned with an Azure AD account</span></span>

<span data-ttu-id="9a039-170">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a039-170">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a><span data-ttu-id="9a039-171">アカウントをプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="9a039-171">Provision the account</span></span>

<span data-ttu-id="9a039-172">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9a039-172">Do one of the following:</span></span>

- <span data-ttu-id="9a039-173">アカウントをプロビジョニングされたアカウントに変換してリンクします。</span><span class="sxs-lookup"><span data-stu-id="9a039-173">Convert and link the account to a provisioned account.</span></span>

  <span data-ttu-id="9a039-174">StaffHub チーム所有者と管理者は、ダミーまたは非アクティブなアカウントを変換して、StaffHub のプロビジョニングされたアカウントにユーザーのメールアドレスを変更することで、StaffHub チーム設定] ページの有効な UPN に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9a039-174">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="9a039-175">プロビジョニングされていないアカウントを削除し、UPN を使用してアカウントをもう一度追加します。</span><span class="sxs-lookup"><span data-stu-id="9a039-175">Remove the non-provisioned account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="9a039-176">StaffHub チームからプロビジョニングされていないアカウントを削除するには、 [StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a039-176">Run the [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="9a039-177">UPN を使用して StaffHub チームにアカウントを戻すには、 [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a039-177">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span> 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="9a039-178">FirstlineWorker アプリのセットアップポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="9a039-178">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="9a039-179">Teams には、組織内の最初の社員にとって最も重要なアプリを強調表示するために、チームをカスタマイズするために使用できる、標準の Lineworker アプリのセットアップポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9a039-179">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="9a039-180">このポリシーをユーザーに割り当てると、ポリシーに含まれるアプリが、すばやく簡単にアクセスできるように Teams のアプリバーに固定されます。</span><span class="sxs-lookup"><span data-stu-id="9a039-180">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="9a039-181">他のチームに追加されたアプリは、[...] をクリックしてアプリバーに表示されます。 \*\*\*\* Teams のデスクトップと web クライアントでのアプリの増加、および teams のモバイルクライアントでの追加アプリ。</span><span class="sxs-lookup"><span data-stu-id="9a039-181">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="9a039-182">既定では、FirstlineWorker アプリのセットアップポリシーには、アクティビティ、シフト、チャット、通話アプリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9a039-182">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="9a039-183">FirstlineWorker アプリのセットアップポリシーをユーザーに割り当てる手順については、「 [firstlineworker アプリのセットアップポリシーを使用してチームへのシフトを固定](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-183">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="9a039-184">ポリシーを割り当てた後は、最長24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9a039-184">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="9a039-185">StaffHub teams とユーザーを Teams に移行する前に、少なくとも1週間以上この手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9a039-185">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="9a039-186">ユーザーが Teams を使用している場合は、シフトアプリを表示してアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a039-186">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="9a039-187">また、カスタムアプリセットアップポリシーを作成して、グローバルアプリセットアップポリシーの設定を編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="9a039-187">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="9a039-188">詳細については、「[Teams でアプリの設定ポリシーを管理する](../../teams-app-setup-policies.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-188">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="9a039-189">チームへのオンボードユーザー</span><span class="sxs-lookup"><span data-stu-id="9a039-189">Onboard users to Teams</span></span>

<span data-ttu-id="9a039-190">オンボード戦略の一環として、チームに慣れてもらうためのトレーニングとガイダンスをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="9a039-190">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="9a039-191">次のリソースをユーザーと共有して、チームのクライアント、トレーニング、サポートを取得する場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="9a039-191">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="9a039-192">Teams の Web クライアント</span><span class="sxs-lookup"><span data-stu-id="9a039-192">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="9a039-193">デスクトップとモバイル クライアントのダウンロード リンク</span><span class="sxs-lookup"><span data-stu-id="9a039-193">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="9a039-194">Teams のトレーニング用ビデオ</span><span class="sxs-lookup"><span data-stu-id="9a039-194">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="9a039-195">Teams のヘルプ ドキュメント</span><span class="sxs-lookup"><span data-stu-id="9a039-195">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="9a039-196">チームを展開してチームを導入するためのガイダンスについては、「チームをロールアウトして[チームを採用](../../adopt-microsoft-teams-landing-page.md)[する方法](../../How-to-roll-out-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-196">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="9a039-197">パイロットの実施</span><span class="sxs-lookup"><span data-stu-id="9a039-197">Conduct a pilot</span></span>

<span data-ttu-id="9a039-198">最初に、2つまたは3つの StaffHub teams を、最早採用者のグループごとに移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9a039-198">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="9a039-199">パイロットを実行すると、移行計画を調整して、組織のすべての StaffHub チームをチームに移行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9a039-199">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="9a039-200">また、組織全体での導入を促進できるエキスパートも特定します。</span><span class="sxs-lookup"><span data-stu-id="9a039-200">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="9a039-201">段階的アプローチを必要としない小規模企業の場合は、このセクションの手順に従って、StaffHub から Teams に切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a039-201">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="9a039-202">パイロットチームの特定</span><span class="sxs-lookup"><span data-stu-id="9a039-202">Identify pilot teams</span></span>

<span data-ttu-id="9a039-203">パイロットチームの2つまたは3つを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-203">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="9a039-204">すべてのチームメンバーは、チームでシフトを使用して、スケジュールを管理し、相互に通信して共同作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a039-204">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="9a039-205">チームのチャンピオンの特定</span><span class="sxs-lookup"><span data-stu-id="9a039-205">Identify team champions</span></span>

<span data-ttu-id="9a039-206">パイロットチーム全体のチャンピオンを特定し、啓蒙シフトを支援するために参加します。</span><span class="sxs-lookup"><span data-stu-id="9a039-206">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="9a039-207">チームの支持者は、チームメンバーのサポートとガイダンスを提供するために、独自の高い知識を共有しています。</span><span class="sxs-lookup"><span data-stu-id="9a039-207">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="9a039-208">チームチャンピオンはチームの所有者または管理者になることができます。</span><span class="sxs-lookup"><span data-stu-id="9a039-208">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="9a039-209">チームのメンバーがチームの[クライアントを取得](../../get-clients.md)し、teams にサインインして、スケジュールをシフトで確認し、互いにチャットを開始するためには、チームメンバーが設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a039-209">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="9a039-210">すでに StaffHub に慣れているユーザーは、シフトですぐに稼動することになります。</span><span class="sxs-lookup"><span data-stu-id="9a039-210">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="9a039-211">その他のヘルプについては、[[シフトヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)] をポイントすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9a039-211">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="9a039-212">StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="9a039-212">Move a StaffHub team</span></span>

<span data-ttu-id="9a039-213">次の手順を使用して、一度に1つの StaffHub チームを移動します。</span><span class="sxs-lookup"><span data-stu-id="9a039-213">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="9a039-214">パイロットチームでは、この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9a039-214">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="9a039-215">後で、組織のすべての StaffHub チームを移行する準備ができたら、「複数のチームを一度に移動する」の手順については、「 [StaffHub teams を移行](#move-your-staffhub-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-215">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="9a039-216">StaffHub チームを移動するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a039-216">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="9a039-217">次</span><span class="sxs-lookup"><span data-stu-id="9a039-217">Example:</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="9a039-218">次に示すのは、StaffHub チームを Teams に移動する要求を送信するときに表示される応答の例です。</span><span class="sxs-lookup"><span data-stu-id="9a039-218">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="9a039-219">移動要求の状態を確認するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a039-219">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="9a039-220">次</span><span class="sxs-lookup"><span data-stu-id="9a039-220">Example:</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="9a039-221">次に示すのは、移動が進行中の場合に表示される応答の例です。</span><span class="sxs-lookup"><span data-stu-id="9a039-221">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="9a039-222">StaffHub チームから Teams にファイルを移動する</span><span class="sxs-lookup"><span data-stu-id="9a039-222">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="9a039-223">この手順は、Teams に移動した StaffHub チームが、Teams にも移動するファイルを持っている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9a039-223">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="9a039-224">SharePoint Online または PowerShell を使用して、ファイルを直接移動できます。</span><span class="sxs-lookup"><span data-stu-id="9a039-224">You can move files directly in SharePoint Online or by using PowerShell.</span></span> 

#### <a name="in-sharepoint-online"></a><span data-ttu-id="9a039-225">SharePoint Online の場合</span><span class="sxs-lookup"><span data-stu-id="9a039-225">In SharePoint Online</span></span>

<span data-ttu-id="9a039-226">[SharePoint Online でファイルを移動する方法に](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)ついて説明します。</span><span class="sxs-lookup"><span data-stu-id="9a039-226">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="9a039-227">PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="9a039-227">Using PowerShell</span></span>

<span data-ttu-id="9a039-228">[SharePoint Online 管理シェル](https://www.microsoft.com/download/details.aspx?id=35588)をダウンロードしてインストールします (まだインストールしていない場合)。</span><span class="sxs-lookup"><span data-stu-id="9a039-228">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="9a039-229">ファイルを移動するために必要なコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9a039-229">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="9a039-230">[Connect-admin.sharepoint.com](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps)コマンドレットを使用して、SharePoint Online チームサイトに接続します。</span><span class="sxs-lookup"><span data-stu-id="9a039-230">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="9a039-231">StaffHub から Teams に移動する各ファイルについて、 [PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile)コマンドレットを使用してファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="9a039-231">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="9a039-232">複数のファイルを移動するには、ファイルをループして、ループの2番目のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a039-232">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="9a039-233">セッションがアクティブな場合は、最初のコマンドを繰り返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9a039-233">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="9a039-234">パイロット以外の場所に移動して、すべての StaffHub teams を移動する</span><span class="sxs-lookup"><span data-stu-id="9a039-234">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="9a039-235">認識を高める</span><span class="sxs-lookup"><span data-stu-id="9a039-235">Raise awareness</span></span>

<span data-ttu-id="9a039-236">パイロットチームを超えて組織の StaffHub チームをチームに移行する準備ができたら、まず組織全体で変更を伝えることが重要です。</span><span class="sxs-lookup"><span data-stu-id="9a039-236">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="9a039-237">シフトについての単語を広げ、チームへの切り替えを行って、認知度を上げ、興奮を生み出し、導入を推進します。</span><span class="sxs-lookup"><span data-stu-id="9a039-237">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="9a039-238">StaffHub teams を移動する</span><span class="sxs-lookup"><span data-stu-id="9a039-238">Move your StaffHub teams</span></span>

<span data-ttu-id="9a039-239">次の手順を使用して、StaffHub teams をまとめて移動します。</span><span class="sxs-lookup"><span data-stu-id="9a039-239">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="9a039-240">組織のすべての StaffHub チームを移動するか、または特定の StaffHub teams を移動するかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="9a039-240">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="9a039-241">StaffHub teams を1つずつ移動する方法については、「 [StaffHub チームを移行](#move-a-staffhub-team)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-241">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="9a039-242">すべての StaffHub teams を移動する</span><span class="sxs-lookup"><span data-stu-id="9a039-242">Move all StaffHub teams</span></span>

<span data-ttu-id="9a039-243">組織内のすべての StaffHub teams の一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a039-243">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="9a039-244">次に、次のことを実行してすべてのチームを移動します。</span><span class="sxs-lookup"><span data-stu-id="9a039-244">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="9a039-245">応答の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9a039-245">Here's an example of the response.</span></span>

<span data-ttu-id="9a039-246">既に Teams に移動されているか、Teams に既に存在しているチームの場合は、そのチームに移動するためにジョブを送信する必要がないため、jobId は "null" になります。</span><span class="sxs-lookup"><span data-stu-id="9a039-246">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="9a039-247">特定の StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="9a039-247">Move specific StaffHub teams</span></span>

<span data-ttu-id="9a039-248">組織内のすべての StaffHub チーム Id の一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a039-248">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="9a039-249">前に実行した`Get-StaffHubteamsForTenant`コマンドレットによって返された結果で、移動するチーム id を選択し、コンマ区切り値 (CSV) ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="9a039-249">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="9a039-250">CSV ファイルを書式設定する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9a039-250">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="9a039-251">Id</span><span class="sxs-lookup"><span data-stu-id="9a039-251">Id</span></span>  |
|---------|
|<span data-ttu-id="9a039-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="9a039-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="9a039-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="9a039-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="9a039-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="9a039-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="9a039-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="9a039-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="9a039-256">CSV ファイルを作成したら、CSV ファイルで指定したチームを移動するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="9a039-256">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="9a039-257">StaffHub teams が Teams に移行されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="9a039-257">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="9a039-258">組織内のすべてのチームの一覧を取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a039-258">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="9a039-259">StaffHub teams から Teams にファイルを移動する</span><span class="sxs-lookup"><span data-stu-id="9a039-259">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="9a039-260">移動した StaffHub teams に、Teams にも移動するファイルが含まれている場合は、「 [StaffHub チームからチームにファイルを移動](#move-files-from-a-staffhub-team-to-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-260">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="9a039-261">チームの利用状況を監視する</span><span class="sxs-lookup"><span data-stu-id="9a039-261">Monitor Teams usage</span></span>

<span data-ttu-id="9a039-262">利用状況レポートは、使用パターンをより理解しやすくするのに役立ちます。また、組織全体でトレーニングとコミュニケーション作業の優先順位を決定する場所について理解を深めます。</span><span class="sxs-lookup"><span data-stu-id="9a039-262">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="9a039-263">シフトは Teams のアプリであるため、チームレポートで利用状況を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9a039-263">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="9a039-264">詳細については、microsoft [teams 管理センターのチームレポート](../../teams-analytics-and-reports/teams-reporting-reference.md)と、 [microsoft 365 管理センターの teams アクティビティレポート](../../teams-activity-reports.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-264">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9a039-265">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9a039-265">Troubleshooting</span></span> 

<span data-ttu-id="9a039-266">**StaffHub から Teams にファイルを移動しようとすると、"アクセス許可は拒否されました" というエラーメッセージが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="9a039-266">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="9a039-267">この問題は、自分がメンバーでないプライベートの Office 365 グループでファイルを移動しようとしている場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="9a039-267">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="9a039-268">この場合は、 [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember)コマンドレットを使用して StaffHub チームに自分を追加してから、ファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="9a039-268">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="9a039-269">ファイルを移動した後、 [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember)コマンドレットを使用してチームから自分自身を削除します。</span><span class="sxs-lookup"><span data-stu-id="9a039-269">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="9a039-270">**StaffHub から Teams にファイルを移動しようとすると、[全般] フォルダーが存在しないというエラーが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="9a039-270">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="9a039-271">次のコマンドを実行して、[全般] フォルダーを SharePoint に追加してから、もう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="9a039-271">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="9a039-272">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9a039-272">Related topics</span></span>
- [<span data-ttu-id="9a039-273">Microsoft Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="9a039-273">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="9a039-274">Microsoft StaffHub はまもなく廃止予定です</span><span class="sxs-lookup"><span data-stu-id="9a039-274">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="9a039-275">Microsoft Teams で組織のシフト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="9a039-275">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="9a039-276">StaffHub PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="9a039-276">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
