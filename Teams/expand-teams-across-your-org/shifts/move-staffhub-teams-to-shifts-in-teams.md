---
title: StaffHub チーム を Microsoft Teams のシフトに移動する
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub のチームとスケジュール データを Microsoft Teams のシフトに移動する方法を説明します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780810"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="6a9f4-103">Microsoft StaffHub のチームを Microsoft Teams のシフトに移動する</span><span class="sxs-lookup"><span data-stu-id="6a9f4-103">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a9f4-104">2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="6a9f4-105">Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="6a9f4-106">現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="6a9f4-107">StaffHub は、2019 年 10 月 1 日以降すべてのユーザーがご利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="6a9f4-108">ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="6a9f4-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="6a9f4-110">Teams 内のシフト アプリでは、スケジュール管理と日ごと常に発生し続けるシフトの入れ替えや取り消しのための簡単なアプローチが提供されます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="6a9f4-111">チーム メンバーはアプリを使用して複数のデバイスからスケジュールやシフトの情報に直接アクセスでき、基本設定、スケジュール管理、休暇の申請などの操作を行えます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="6a9f4-112">この記事では、組織の StaffHub のチームとスケジュール データを Teams 内のシフトに移動させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="6a9f4-113">取り扱う内容:</span><span class="sxs-lookup"><span data-stu-id="6a9f4-113">It covers:</span></span>

- [<span data-ttu-id="6a9f4-114">Teams への移行について知っておくべき事項</span><span class="sxs-lookup"><span data-stu-id="6a9f4-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="6a9f4-115">準備</span><span class="sxs-lookup"><span data-stu-id="6a9f4-115">Prepare Schema</span></span>](#prepare)
- [<span data-ttu-id="6a9f4-116">パイロットの実施</span><span class="sxs-lookup"><span data-stu-id="6a9f4-116">Conduct a user pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="6a9f4-117">パイロットを終了しすべての StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="6a9f4-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="6a9f4-118">Teams の使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="6a9f4-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="6a9f4-119">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6a9f4-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="6a9f4-120">この管理者向けガイダンスには Teams への移行を成功させるために必要な情報が含まれ、少数の StaffHub チームを運用する小規模な事業のお客様にも、StaffHub チームが何百もある大企業のお客様にもご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="6a9f4-121">この記事の手順を実行するには、全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="6a9f4-122">「[StaffHub の廃止に関するよくあるご質問](microsoft-staffhub-to-be-retired.md)」をまだご覧になられていない場合はご覧いただき、不明点に関する答えをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="6a9f4-123">Teams への移行について知っておくべき事項</span><span class="sxs-lookup"><span data-stu-id="6a9f4-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="6a9f4-124">Teams に移行する時期</span><span class="sxs-lookup"><span data-stu-id="6a9f4-124">When to move to Teams</span></span>

<span data-ttu-id="6a9f4-125">2019 年 10 月 1 日より、StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-125">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="6a9f4-126">Teams の使用を今から開始し、組織のチームとユーザーの StaffHub からの移行を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="6a9f4-127">StaffHub で最もよく使用される機能はスケジュール管理であるため、今後は Teams 内のシフト アプリを使用されることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="6a9f4-128">Teams に移動する内容</span><span class="sxs-lookup"><span data-stu-id="6a9f4-128">What is moved to Teams</span></span>

<span data-ttu-id="6a9f4-129">Teams に移動されるのは、ユーザーの詳細情報、スケジュール情報、チャットおよびファイルのデータです。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-129">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="6a9f4-130">これには、チーム メンバーシップ、チーム スケジュール、および過去 90 日間のチャットとファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-130">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="6a9f4-131">各 StaffHub チームには、対応する Office 365 グループが必要です。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-131">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="6a9f4-132">StaffHub チームに Office 365 グループが関連付けられていない場合は、移行を支援するために自動的にグループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-132">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="6a9f4-133">Teams と StaffHub ではチームとグループの名前の付け方に違いがあるため、Teams ではチーム名が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-133">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="6a9f4-134">チームを StaffHub から Teams に移動すると、ユーザーは StaffHub のスケジュールにはアクセスできなくなり、Teams 内のシフトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-134">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="6a9f4-135">中断を最小限に抑え、Teams の導入をユーザーに促すために、この変更について組織全体に伝達することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-135">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="6a9f4-136">Azure AD Premium を使用している場合は、[レポートを実行](run-report-to-show-staffhub-usage.md)して、組織の StaffHub ユーザーのうち、この変更について知っておく必要があるユーザーのリストを取得できます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-136">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="6a9f4-137">StaffHub チームを Teams に移動した後は、それをロールバックするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-137">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="6a9f4-138">チームを移動するときのユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="6a9f4-138">User experience when you move a team</span></span>

<span data-ttu-id="6a9f4-139">StaffHub から Teams 内のシフトにチームが切り替えられる際のユーザーのダウンタイムは、ほんのわずかです (あったとしても、1 秒未満です)。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-139">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="6a9f4-140">ユーザーは、Teams への移行が完了するまで StaffHub を引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-140">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="6a9f4-141">移行が完了すると、チームのスケジュールにアクセスするには Teams 内のシフトの使用を開始する必要があることを通知するメッセージがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-141">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="6a9f4-142">StaffHub チームが Teams に移行した後に StaffHub でユーザーに表示されるメッセージの例です。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-142">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="6a9f4-143">![ユーザーに表示されるメッセージの例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "StaffHub チームが Teams に移行した後に StaffHub でユーザーに表示されるメッセージの例")</span><span class="sxs-lookup"><span data-stu-id="6a9f4-143">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="6a9f4-144">準備</span><span class="sxs-lookup"><span data-stu-id="6a9f4-144">Prepare Schema</span></span>

<span data-ttu-id="6a9f4-145">Teams に移動するための準備を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-145">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="6a9f4-146">前提条件を満たしていることを確認する</span><span class="sxs-lookup"><span data-stu-id="6a9f4-146">Ensure that deployment prerequisites are met</span></span>

<span data-ttu-id="6a9f4-147">StaffHub チームを Teams に移動する前に、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-147">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="6a9f4-148">サインインしているユーザーが全体管理者であること。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-148">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="6a9f4-149">Teams がテナント内のすべてのユーザーに対して有効化されていること。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-149">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="6a9f4-150">Office 365 グループの作成がテナントで有効になっていること。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-150">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="6a9f4-151">StaffHub の teamId が有効であること。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-151">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="6a9f4-152">StaffHub チームにメンバーが含まれていること。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-152">The StaffHub team contains members.</span></span> 
- <span data-ttu-id="6a9f4-153">すべての StaffHub チーム メンバーが、Azure AD アカウントにリンクされていること。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-153">All StaffHub team members are linked to an Azure AD account.</span></span> 

<span data-ttu-id="6a9f4-154">これらの前提条件を満たしていない場合、移動要求は失敗します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-154">If these prerequisites aren't met, the move request will fail.</span></span> 

### <a name="assign-teams-licenses"></a><span data-ttu-id="6a9f4-155">Teams のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6a9f4-155">Assign Teams licenses</span></span>

<span data-ttu-id="6a9f4-156">各ユーザーは、[対象プラン](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)の有効な Microsoft 365 または Office 365 ライセンスを持っている必要があり、Teams ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-156">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="6a9f4-157">Teams ライセンスを割り当てられたユーザーは Teams にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-157">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="6a9f4-158">Teams ライセンスの管理は、Microsoft 365 管理センターで行います。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-158">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6a9f4-159">詳細については、「[Microsoft Teams へのユーザー アクセスを管理する](../../user-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-159">To learn more, see [Manage user access to Microsoft Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6a9f4-160">Skype for Business を使用している組織ですべてのユーザーを Teams に移行する準備ができていない場合は、現場担当者に対して Teams を有効にし、これらのユーザーが Teams を Skype for Business と併用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-160">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="6a9f4-161">「*アイランド*」と呼ばれるこの共存モードでは、各クライアント アプリが別個のソリューションとして動作します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-161">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="6a9f4-162">詳細については、「[Microsoft Teams と Skype for Business の共存と相互運用性について](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-162">To learn more, read [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="6a9f4-163">StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="6a9f4-163">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="6a9f4-164">[StaffHub PowerShell モジュールのインストールがまだの場合は、インストールします](install-the-staffhub-powershell-module.md)。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-164">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="6a9f4-165">Azure AD の ID を持たない StaffHub ユーザーのアカウントをプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="6a9f4-165">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="6a9f4-166">各マネージャーとチームメンバーは、Azure Active Directory (Azure AD) で ID を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-166">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="6a9f4-167">ユーザーが Azure AD で ID を持っていない場合は、アカウントをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-167">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="6a9f4-168">これを行うには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-168">Here's how.</span></span> 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a><span data-ttu-id="6a9f4-169">Azure AD アカウントがプロビジョニングされていないチーム メンバーが所属する StaffHub チーム内のすべてのユーザーのリストを取得する</span><span class="sxs-lookup"><span data-stu-id="6a9f4-169">Get a list of all users on StaffHub teams that have team members that aren't provisioned with an Azure AD account</span></span>

<span data-ttu-id="6a9f4-170">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-170">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a><span data-ttu-id="6a9f4-171">アカウントをプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="6a9f4-171">Provision the account</span></span>

<span data-ttu-id="6a9f4-172">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-172">Do one of the following:</span></span>

- <span data-ttu-id="6a9f4-173">アカウントを、プロビジョニングされたアカウントに変換してリンクします。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-173">Convert and link the account to a provisioned account.</span></span>

  <span data-ttu-id="6a9f4-174">StaffHub チームの所有者と管理者は、StaffHub チーム設定ページでユーザーのメールアドレスを有効な UPN に変更することで、ダミーまたは非アクティブなアカウントを変換して、プロビジョニングされた StaffHub のアカウントにリンクできます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-174">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="6a9f4-175">プロビジョニングされていないアカウントを削除し、UPN を使用してアカウントを追加し直します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-175">Remove the non-provisioned account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="6a9f4-176">[Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) コマンドレットを実行して、StaffHub チームからプロビジョニングされていないアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-176">Run the [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="6a9f4-177">[Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) コマンドレットを実行し、UPN を使用して StaffHub チームにアカウントを追加し直します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-177">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span> 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="6a9f4-178">FirstLineWorker アプリのセットアップ ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="6a9f4-178">Assign the FirstLineWorker app setup policy to users in a group</span></span>

<span data-ttu-id="6a9f4-179">Teams には、組織の現場担当者にとって最も重要なアプリをハイライトするために Teams をカスタマイズするのに使用できる、FirstlineWorker アプリ セットアップ ポリシーが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-179">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="6a9f4-180">このポリシーをユーザーに割り当てると、すばやく簡単にアクセスできるよう、ポリシー内のアプリがチームのアプリ バーに固定されます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-180">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="6a9f4-181">Teams に追加された他のアプリは、Teams のデスクトップと Web クライアントで [**その他のアプリ**] をクリックすると表示されます。Teams モバイル クライアントの場合は、上方向にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-181">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="6a9f4-182">既定では、FirstlineWorker アプリのセットアップ ポリシーには、アクティビティ、シフト、チャット、および通話の各アプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-182">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="6a9f4-183">FirstlineWorker アプリのセットアップ ポリシーをユーザーに割り当てる手順については、「[FirstlineWorker アプリのセットアップ ポリシーを使用して Teams にシフトをピン留めする](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-183">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="6a9f4-184">ポリシーの割り当て後、それが有効になるまで最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-184">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="6a9f4-185">StaffHub のチームとユーザーを Teams に移動する少なくとも 1 週間前までにこの手順を完了しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-185">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="6a9f4-186">ユーザーが Teams にサインインしたら、シフト アプリがユーザーに表示され、アクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-186">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="6a9f4-187">また、アプリのカスタム セットアップ ポリシーを作成し、アプリのグローバル セットアップ ポリシーでその設定を編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-187">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="6a9f4-188">詳細については、「[Teams アプリのセットアップ ポリシーを管理する](../../teams-app-setup-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-188">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="6a9f4-189">Teams にユーザーをオンボードする</span><span class="sxs-lookup"><span data-stu-id="6a9f4-189">Onboard users to Teams</span></span>

<span data-ttu-id="6a9f4-190">オンボードディング戦略の一環として、ユーザーが Teams を理解できるよう、トレーニングとガイダンスをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-190">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="6a9f4-191">Teams のクライアントの入手先やトレーニングおよびサポートを受けられる場所がわかるように、次のリソースをユーザーと共有します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-191">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="6a9f4-192">Teams の Web クライアント</span><span class="sxs-lookup"><span data-stu-id="6a9f4-192">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="6a9f4-193">デスクトップとモバイル クライアントのダウンロード リンク</span><span class="sxs-lookup"><span data-stu-id="6a9f4-193">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="6a9f4-194">Teams のトレーニング用ビデオ</span><span class="sxs-lookup"><span data-stu-id="6a9f4-194">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="6a9f4-195">Teams のヘルプ ドキュメント</span><span class="sxs-lookup"><span data-stu-id="6a9f4-195">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="6a9f4-196">Teams の展開と Teams の導入推進に関するガイダンスは、「[Microsoft Teams の展開方法](../../How-to-roll-out-teams.md)」および「[Microsoft Teams を導入する](../../adopt-microsoft-teams-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-196">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="6a9f4-197">パイロットの実施</span><span class="sxs-lookup"><span data-stu-id="6a9f4-197">Conduct a user pilot</span></span>

<span data-ttu-id="6a9f4-198">早期導入者の限られたグループとして、手始めに 2 つか 3 つの StaffHub チームの移行を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-198">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="6a9f4-199">パイロットの実施により、移行計画を微調整し、組織のすべての StaffHub チームをチームに移行する準備を整えられます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-199">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="6a9f4-200">また、先導役となるユーザーを特定して、組織全体での導入の促進につなげることもできます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-200">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="6a9f4-201">小規模なビジネスであるために段階的な手法を必要としない場合、StaffHub から Teams への切り替えに必要な手順は、すべてこのセクションで説明されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-201">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="6a9f4-202">パイロット チームの特定</span><span class="sxs-lookup"><span data-stu-id="6a9f4-202">Identify pilot teams</span></span>

<span data-ttu-id="6a9f4-203">パイロット チームを特定するためにユーザーに連絡をとります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-203">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="6a9f4-204">スケジュールの管理やチーム内での連絡と共同作業に Teams 内のシフトを使用することに、チーム メンバー全員がコミットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-204">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="6a9f4-205">Teams の先導者の特定</span><span class="sxs-lookup"><span data-stu-id="6a9f4-205">Identify team champions</span></span>

<span data-ttu-id="6a9f4-206">パイロット チームの中で先導者を特定し、シフトを普及させるための協力を依頼します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-206">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="6a9f4-207">Teams の先導者は、業務に熱心に取り組み、自身の知見をチーム メンバーと共有してサポートやガイダンスを提供できるユーザーたちです。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-207">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="6a9f4-208">Teams の先導者には、チームの所有者またはマネージャーがなれます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-208">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="6a9f4-209">すべてのユーザーが [Teams のクライアントを入手](../../get-clients.md)し、Teams にサインインして自分のスケジュールをシフトでチェックし、他のメンバーとチャットを開始できるよう、Teams の先導者はチーム メンバーの設定が行われていることをしっかり時間をかけて確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-209">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="6a9f4-210">StaffHub に慣れているユーザーは、シフトをすばやく稼働させられます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-210">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="6a9f4-211">追加のヘルプが必要なユーザーには、「[シフトのヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)」を参照するよう伝えることもできます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-211">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="6a9f4-212">特定のStaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="6a9f4-212">Move a StaffHub team</span></span>

<span data-ttu-id="6a9f4-213">これらの手順を使用して、一度に 1 チームずつ StaffHub チームを移動します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-213">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="6a9f4-214">このアプローチをパイロット チームについて使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-214">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="6a9f4-215">後に、組織のすべての StaffHub チームを移動する準備ができた場合は、一度に複数のチームを移動させる手順ついて、「[StaffHub チームを移動する](#move-your-staffhub-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-215">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="6a9f4-216">StaffHub チームを移動するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-216">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="6a9f4-217">例:</span><span class="sxs-lookup"><span data-stu-id="6a9f4-217">Example</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="6a9f4-218">StaffHub チームを Teams に移動する要求を送信した際に返される応答の例です。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-218">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="6a9f4-219">移動要求の状態を確認するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-219">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="6a9f4-220">例:</span><span class="sxs-lookup"><span data-stu-id="6a9f4-220">Example</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="6a9f4-221">移動の進行中に返される応答の例です。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-221">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="6a9f4-222">StaffHub チームから Teams にファイルを移動する</span><span class="sxs-lookup"><span data-stu-id="6a9f4-222">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="6a9f4-223">この手順は、Teams に移動する StaffHub チームが、やはり Teams に移動させたいファイルを持っている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-223">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="6a9f4-224">ファイルは SharePoint Online 内で直接移動する方法でも、PowerShell を使用する方法でも移動できます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-224">You can move files directly in SharePoint Online or by using PowerShell.</span></span> 

#### <a name="in-sharepoint-online"></a><span data-ttu-id="6a9f4-225">SharePoint Online 内で行う場合</span><span class="sxs-lookup"><span data-stu-id="6a9f4-225">In SharePoint Online</span></span>

<span data-ttu-id="6a9f4-226">「[SharePoint Online でファイルを移動する方法](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-226">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="6a9f4-227">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="6a9f4-227">Using Windows PowerShell</span></span>

<span data-ttu-id="6a9f4-228">まだの場合、[SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588) をダウンロードしてインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-228">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="6a9f4-229">ファイルを移動するために必要なコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-229">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="6a9f4-230">[Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) コマンドレットを使用して、SharePoint Online チームサイトに接続します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-230">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="6a9f4-231">StaffHub から Teams に移動する各ファイルに対して [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) コマンドレットを使用してファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-231">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="6a9f4-232">複数のファイルを移動するには、ファイルをループして、ループに対して 2 つ目のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-232">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="6a9f4-233">セッションがアクティブなままの場合は、最初のコマンドを繰り返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-233">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="6a9f4-234">パイロットを終了しすべての StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="6a9f4-234">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="6a9f4-235">認知度を上げる</span><span class="sxs-lookup"><span data-stu-id="6a9f4-235">Raise awareness</span></span>

<span data-ttu-id="6a9f4-236">パイロット チームの移動を終了し組織の StaffHub チームをチームに移行する準備ができた場合は、変更について組織全体に通知することが重要です。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-236">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="6a9f4-237">シフトと Teams への移行に関する情報を広めて認知度を上げ、期待感を高めることによって導入の促進を図ります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-237">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="6a9f4-238">StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="6a9f4-238">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

<span data-ttu-id="6a9f4-239">これらの手順を使用して、StaffHub チームを一括移動します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-239">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="6a9f4-240">組織のすべての StaffHub チームを移動する方法も、特定の StaffHub チームを移動する方法も選べます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-240">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="6a9f4-241">StaffHub チームを1つずつ移動する場合は、「[StaffHub チームを移動する](#move-a-staffhub-team)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-241">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="6a9f4-242">すべての StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="6a9f4-242">Move all StaffHub teams</span></span>

<span data-ttu-id="6a9f4-243">次を実行して、組織内のすべての StaffHub チームのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-243">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="6a9f4-244">次を実行してすべてのチームを移動します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-244">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="6a9f4-245">応答の例を下に示します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-245">Here's an example of the response.</span></span>

<span data-ttu-id="6a9f4-246">既に Teams に移動されたか既に Teams に存在するチームの場合、そうしたチームを移動するためのジョブを送信する必要がないため、jobId は "null" になります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-246">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="6a9f4-247">特定の StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="6a9f4-247">Move specific StaffHub teams</span></span>

<span data-ttu-id="6a9f4-248">次を実行して、組織内のすべての StaffHub チームの ID のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-248">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="6a9f4-249">先ほど実行した `Get-StaffHubteamsForTenant` コマンドレットによって返された結果で移動するチーム ID を選択し、コンマ区切り値 (CSV) ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-249">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="6a9f4-250">CSV ファイルで必要な書式設定の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-250">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="6a9f4-251">ID</span><span class="sxs-lookup"><span data-stu-id="6a9f4-251">ID</span></span>  |
|---------|
|<span data-ttu-id="6a9f4-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="6a9f4-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="6a9f4-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="6a9f4-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="6a9f4-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="6a9f4-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="6a9f4-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="6a9f4-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="6a9f4-256">CSV ファイルを作成したら、次のコマンドを実行して CSV ファイルで指定したチームを移動します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-256">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="6a9f4-257">StaffHub チームが Teams に移動したことを確認する</span><span class="sxs-lookup"><span data-stu-id="6a9f4-257">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="6a9f4-258">次を実行して、組織内のすべてのシフトのチームのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-258">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="6a9f4-259">StaffHub チームから Teams にファイルを移動する</span><span class="sxs-lookup"><span data-stu-id="6a9f4-259">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="6a9f4-260">移動した StaffHub チームに Teams に移動するファイルが含まれている場合は、「[StaffHub チームから Teams にファイルを移動する](#move-files-from-a-staffhub-team-to-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-260">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="6a9f4-261">Teams の使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="6a9f4-261">Monitor Teams usage</span></span>

<span data-ttu-id="6a9f4-262">使用状況レポートは、使用パターンを正しく理解するために役立ち、組織全体でのトレーニングとコミュニケーションの取り組みに関する優先順位を決定するのに活用できる見識を提供します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-262">Usage reports can help you better understand usage patterns, and along with user feedback, give you insights to inform your wider rollout and where to prioritize training and communication efforts.</span></span> <span data-ttu-id="6a9f4-263">シフトは Teams 内のアプリであるため、その使用状況は Teams のレポート上で確認できます。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-263">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="6a9f4-264">詳細については、「[Microsoft Teams 管理センターでの Teams のレポート](../../teams-analytics-and-reports/teams-reporting-reference.md) 」および「[Microsoft 365 管理センターでの Teams のアクティビティ レポート](../../teams-activity-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-264">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6a9f4-265">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6a9f4-265">Troubleshooting</span></span> 

<span data-ttu-id="6a9f4-266">**StaffHub から Teams にファイルを移動しようとすると、"アクセスは拒否されました" というエラー メッセージが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="6a9f4-266">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="6a9f4-267">これは、自分がメンバーでないプライベートの Office 365 グループ内のファイルを移動しようとした場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-267">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="6a9f4-268">該当する場合は、[AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) コマンドレットを使用して自分自身を StaffHub チームに追加してからファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-268">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="6a9f4-269">ファイルの移動後は、[Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) コマンドレットを使用して、チームから自分自身を削除します。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-269">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="6a9f4-270">**StaffHub から Teams にファイルを移動しようとすると、[全般] フォルダーが存在しないというエラーが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="6a9f4-270">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="6a9f4-271">次のコマンドを実行して [全般] フォルダーを SharePoint に追加してから、もう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="6a9f4-271">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="6a9f4-272">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a9f4-272">Related topics</span></span>
- [<span data-ttu-id="6a9f4-273">Microsoft Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="6a9f4-273">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="6a9f4-274">Microsoft StaffHub はまもなく廃止予定です</span><span class="sxs-lookup"><span data-stu-id="6a9f4-274">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="6a9f4-275">Microsoft Teams で組織のシフト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="6a9f4-275">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="6a9f4-276">StaffHub PowerShell のリファレンス</span><span class="sxs-lookup"><span data-stu-id="6a9f4-276">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
