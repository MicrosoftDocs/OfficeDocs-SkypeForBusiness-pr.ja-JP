---
title: 'StaffHub teams を Microsoft Teams の Shifts に移動する '
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 3/29/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub teams を移動して、Microsoft Teams のシフトにデータをスケジュールする方法について説明します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74a9b23479f5357c0014ef5ef88b3f5da03ace7f
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865053"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="2b726-103">Microsoft Teams で Microsoft StaffHub teams をシフトに移行する</span><span class="sxs-lookup"><span data-stu-id="2b726-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b726-104">2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="2b726-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="2b726-105">Microsoft Teams で StaffHub 機能を構築しています。</span><span class="sxs-lookup"><span data-stu-id="2b726-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="2b726-106">現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。</span><span class="sxs-lookup"><span data-stu-id="2b726-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="2b726-107">2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="2b726-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="2b726-108">StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b726-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="2b726-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b726-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="2b726-110">この記事で説明されている機能は、まだリリースされていません。</span><span class="sxs-lookup"><span data-stu-id="2b726-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="2b726-111">これは発表されました。まもなく、2019年5月の中央に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b726-111">It's been announced, and is coming soon, towards the middle of May 2019.</span></span> <span data-ttu-id="2b726-112">管理者の場合は、この機能がメッセージセンター ( [Microsoft 365 管理センター](https://portal.office.com/adminportal/home)) で利用可能になるタイミングを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2b726-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="2b726-113">Teams のシフトアプリは、スケジュールを管理するための簡単なアプローチを提供します。また、1日のうちに発生するシフト交換とキャンセルの流れを定期的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2b726-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="2b726-114">チームメンバーは、アプリやデバイス間で直接、スケジュールとシフト情報にアクセスして、ユーザー設定の設定、スケジュールの管理、休暇のリクエストを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2b726-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="2b726-115">この記事では、組織の StaffHub teams を移動して、チーム内のシフトにデータをスケジュールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b726-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="2b726-116">1人または2人の StaffHub チームを持つ小規模企業でも、数百人の StaffHub teams を持つ大企業でも、チームへの移行を成功させるために必要な管理ガイダンスが記載されています。</span><span class="sxs-lookup"><span data-stu-id="2b726-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="2b726-117">この記事の手順を実行するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b726-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="2b726-118">まだインストールしていない場合は、 [StaffHub 定年](microsoft-staffhub-to-be-retired.md)に関する faq を参照して、お客様からの質問に回答してください。</span><span class="sxs-lookup"><span data-stu-id="2b726-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="2b726-119">Teams への移行について知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="2b726-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="2b726-120">Teams に移動する場合</span><span class="sxs-lookup"><span data-stu-id="2b726-120">When to move to Teams</span></span>

<span data-ttu-id="2b726-121">2019年10月1日、StaffHub は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="2b726-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="2b726-122">今すぐ Teams の使用を開始して、組織のチームとユーザーを StaffHub から移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b726-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="2b726-123">StaffHub でスケジュール管理が最も一般的に使用される機能である場合は、チームでのシフトアプリの使用を進めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b726-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="2b726-124">Teams に移動されるもの</span><span class="sxs-lookup"><span data-stu-id="2b726-124">What is moved to Teams</span></span>

<span data-ttu-id="2b726-125">ユーザの詳細、スケジュール情報、チャットとファイルデータは Teams に移行されます。</span><span class="sxs-lookup"><span data-stu-id="2b726-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="2b726-126">これには、チームメンバーシップ、チームのスケジュール、および過去90日間のチャットとファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b726-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="2b726-127">すべての StaffHub チームには、対応する Office 365 グループが必要です。</span><span class="sxs-lookup"><span data-stu-id="2b726-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="2b726-128">StaffHub チームに Office 365 グループが関連付けられていない場合は、移行をサポートするために、1つが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="2b726-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="2b726-129">Teams と StaffHub の間でのチームとグループの名前の違いにより、Teams に異なるチーム名が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2b726-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="2b726-130">チームを StaffHub から Teams に移行すると、ユーザーは StaffHub のスケジュールにアクセスできなくなり、Teams のシフトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="2b726-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="2b726-131">この変更を組織全体で伝達することをお勧めします。中断を最小限に抑え、ユーザーにチームの採用と検討を促します。</span><span class="sxs-lookup"><span data-stu-id="2b726-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="2b726-132">Azure AD Premium を使用している場合は、[レポートを実行](run-report-to-show-staffhub-usage.md)して、この変更について知っておく必要がある、組織内の StaffHub ユーザーの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="2b726-132">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="2b726-133">StaffHub チームを Teams に移動しても、ロールバックオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="2b726-133">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="2b726-134">チームを移動するときのユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="2b726-134">User experience when you move a team</span></span>

<span data-ttu-id="2b726-135">チームの StaffHub からシフトへの切り替えが発生した場合、ユーザーに対してダウンタイム (1 秒未満) が最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="2b726-135">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="2b726-136">チームへの移動が完了するまで、ユーザーは StaffHub を引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2b726-136">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="2b726-137">移動が完了すると、チームメンバーにメッセージが表示され、チームのスケジュールにアクセスするためにチームのシフトの使用を開始する必要があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2b726-137">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="2b726-138">次に、ユーザーに表示されるメッセージの例を示します。</span><span class="sxs-lookup"><span data-stu-id="2b726-138">Here's an example of the message that users see.</span></span>

<span data-ttu-id="2b726-139">![StaffHub チームが Teams に移動した後に StaffHub に表示されるメッセージの例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "StaffHub チームが Teams に移動した後に StaffHub に表示されるメッセージの例")</span><span class="sxs-lookup"><span data-stu-id="2b726-139">![Example of the message that users see in StaffHub after the StaffHub team is moved to Teams. ](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="2b726-140">備える</span><span class="sxs-lookup"><span data-stu-id="2b726-140">Prepare</span></span>

<span data-ttu-id="2b726-141">ここでは、Teams への移行を準備する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b726-141">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="2b726-142">Teams のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2b726-142">Assign Teams licenses</span></span>

<span data-ttu-id="2b726-143">各ユーザーは、ライセンス付与された有効な Microsoft 365 [](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)または Office 365 ライセンスを所有している必要があります。また、Teams ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b726-143">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="2b726-144">Teams ライセンスをユーザーに割り当てると、チームにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2b726-144">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="2b726-145">Teams のライセンスは、Microsoft 365 管理センターで管理します。</span><span class="sxs-lookup"><span data-stu-id="2b726-145">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="2b726-146">詳細については、「[チームへのユーザーアクセスを管理](../../user-access.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b726-146">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2b726-147">組織で Skype for Business を使用していて、すべてのユーザーをチームに移行する準備ができていない場合は、最初に Skype for Business を使用してチームを実行できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b726-147">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="2b726-148">この共存モード (*孤島*) では、各クライアントアプリは個別のソリューションとして動作します。</span><span class="sxs-lookup"><span data-stu-id="2b726-148">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="2b726-149">詳細については、「[チームと Skype For business の共存と相互運用性につい](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b726-149">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="2b726-150">Azure AD で id を持っていない StaffHub ユーザーのアカウントをプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="2b726-150">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="2b726-151">各マネージャーとチームメンバーは、Azure Active Directory (Azure AD) で id を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b726-151">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="2b726-152">ユーザーがまだ Azure AD で id を持っていない場合は、アカウントをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="2b726-152">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="2b726-153">これを行うには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b726-153">Here's how.</span></span>

- <span data-ttu-id="2b726-154">StaffHub チーム所有者と管理者は、ダミーまたは非アクティブなアカウントを変換して、StaffHub のプロビジョニングされたアカウントにユーザーのメールアドレスを変更することで、StaffHub チーム設定] ページの有効な UPN に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="2b726-154">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="2b726-155">管理者は、 [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps)と[StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps)のコマンドレットを実行して、StaffHub チームからプロビジョニングされていないアカウントを削除し、UPN を使用してアカウントを追加し直すことができます。</span><span class="sxs-lookup"><span data-stu-id="2b726-155">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="2b726-156">StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="2b726-156">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="2b726-157">まだインストールしていない場合は、 [StaffHub PowerShell モジュールをインストール](install-the-staffhub-powershell-module.md)します。</span><span class="sxs-lookup"><span data-stu-id="2b726-157">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="2b726-158">StaffHub チームを移動すると、移動要求によって前提条件が確認されます。</span><span class="sxs-lookup"><span data-stu-id="2b726-158">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="2b726-159">次に、移動要求が失敗する理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b726-159">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="2b726-160">サインインしたユーザーはグローバル管理者ではない</span><span class="sxs-lookup"><span data-stu-id="2b726-160">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="2b726-161">テナントのすべてのユーザーに対してチームが無効になっている</span><span class="sxs-lookup"><span data-stu-id="2b726-161">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="2b726-162">テナントで Office 365 グループの作成が無効になっている</span><span class="sxs-lookup"><span data-stu-id="2b726-162">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="2b726-163">StaffHub teamId が有効ではないか、メンバーがいません</span><span class="sxs-lookup"><span data-stu-id="2b726-163">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="2b726-164">StaffHub チームには、Azure AD アカウントにリンクされていないメンバーが含まれています</span><span class="sxs-lookup"><span data-stu-id="2b726-164">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="2b726-165">パイロットを実行する</span><span class="sxs-lookup"><span data-stu-id="2b726-165">Run a pilot</span></span>

<span data-ttu-id="2b726-166">最初に、2つまたは3つの StaffHub teams を、最早採用者のグループごとに移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b726-166">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="2b726-167">パイロットを実行すると、移行計画を調整して、組織のすべての StaffHub チームをチームに移行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2b726-167">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="2b726-168">また、組織全体での導入を促進できるエキスパートも特定します。</span><span class="sxs-lookup"><span data-stu-id="2b726-168">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="2b726-169">段階的アプローチを必要としない小規模企業の場合は、このセクションの手順に従って、StaffHub から Teams に切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b726-169">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="2b726-170">パイロットチームの特定</span><span class="sxs-lookup"><span data-stu-id="2b726-170">Identify pilot teams</span></span>

<span data-ttu-id="2b726-171">パイロットチームの2つまたは3つを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2b726-171">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="2b726-172">すべてのチームメンバーは、チームでシフトを使用して、スケジュールを管理し、相互に通信して共同作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b726-172">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="2b726-173">チームのチャンピオンの特定</span><span class="sxs-lookup"><span data-stu-id="2b726-173">Identify team champions</span></span>

<span data-ttu-id="2b726-174">パイロットチーム全体のチャンピオンを特定し、啓蒙シフトを支援するために参加します。</span><span class="sxs-lookup"><span data-stu-id="2b726-174">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="2b726-175">チームの支持者は、チームメンバーのサポートとガイダンスを提供するために、独自の高い知識を共有しています。</span><span class="sxs-lookup"><span data-stu-id="2b726-175">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="2b726-176">チームチャンピオンはチームの所有者または管理者になることができます。</span><span class="sxs-lookup"><span data-stu-id="2b726-176">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="2b726-177">チームのメンバーがチームの[クライアントを取得](../../get-clients.md)し、teams にサインインして、スケジュールをシフトで確認し、互いにチャットを開始するためには、チームメンバーが設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b726-177">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="2b726-178">すでに StaffHub に慣れているユーザーは、シフトですぐに稼動することになります。</span><span class="sxs-lookup"><span data-stu-id="2b726-178">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="2b726-179">その他のヘルプについては、[[シフトヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)] をポイントすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2b726-179">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="2b726-180">StaffHub チームを移動する (近日公開)</span><span class="sxs-lookup"><span data-stu-id="2b726-180">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="2b726-181">次の手順を使用して、一度に1つの StaffHub チームを移動します。</span><span class="sxs-lookup"><span data-stu-id="2b726-181">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="2b726-182">パイロットチームでは、この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b726-182">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="2b726-183">後で、組織のすべての StaffHub チームを移行する準備ができたら、「複数のチームを一度に移動する」の手順については、「 [StaffHub teams を移行](#move-your-staffhub-teams-coming-soon)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b726-183">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="2b726-184">StaffHub チームを移動するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b726-184">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="2b726-185">次に示すのは、StaffHub チームを Teams に移動する要求を送信するときに表示される応答の例です。</span><span class="sxs-lookup"><span data-stu-id="2b726-185">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="2b726-186">移動要求の状態を確認するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b726-186">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="2b726-187">次に示すのは、移動が進行中の場合に表示される応答の例です。</span><span class="sxs-lookup"><span data-stu-id="2b726-187">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="2b726-188">StaffHub から Teams への切り替えを行う</span><span class="sxs-lookup"><span data-stu-id="2b726-188">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="2b726-189">認識を高める</span><span class="sxs-lookup"><span data-stu-id="2b726-189">Raise awareness</span></span>

<span data-ttu-id="2b726-190">パイロットチームを超えて組織の StaffHub チームをチームに移行する準備ができたら、まず組織全体で変更を伝えることが重要です。</span><span class="sxs-lookup"><span data-stu-id="2b726-190">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="2b726-191">シフトについての単語を広げ、チームへの切り替えを行って、認知度を上げ、興奮を生み出し、導入を推進します。</span><span class="sxs-lookup"><span data-stu-id="2b726-191">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="2b726-192">StaffHub teams を移動する (近日公開)</span><span class="sxs-lookup"><span data-stu-id="2b726-192">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="2b726-193">次の手順を使用して、StaffHub teams をまとめて移動します。</span><span class="sxs-lookup"><span data-stu-id="2b726-193">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="2b726-194">組織のすべての StaffHub チームを移動するか、または特定の StaffHub teams を移動するかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="2b726-194">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="2b726-195">StaffHub teams を1つずつ移動する方法については、「 [StaffHub チームを移行](#move-a-staffhub-team-coming-soon)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b726-195">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="2b726-196">すべての StaffHub teams を移動する (近日公開)</span><span class="sxs-lookup"><span data-stu-id="2b726-196">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="2b726-197">組織内のすべての StaffHub teams の一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b726-197">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="2b726-198">次に、次のことを実行してすべてのチームを移動します。</span><span class="sxs-lookup"><span data-stu-id="2b726-198">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="2b726-199">応答の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2b726-199">Here's an example of the response.</span></span>

<span data-ttu-id="2b726-200">既に Teams に移動されているか、Teams に既に存在しているチームの場合は、そのチームに移動するためにジョブを送信する必要がないため、jobId は "null" になります。</span><span class="sxs-lookup"><span data-stu-id="2b726-200">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="2b726-201">特定の StaffHub チームを移動する (近日公開)</span><span class="sxs-lookup"><span data-stu-id="2b726-201">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="2b726-202">組織内のすべての StaffHub チーム Id の一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b726-202">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="2b726-203">前に実行した`Get-StaffHubteamsForTenant`コマンドレットによって返された結果で、移動するチーム id を選択し、コンマ区切り値 (CSV) ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="2b726-203">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="2b726-204">CSV ファイルを書式設定する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2b726-204">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="2b726-205">Id</span><span class="sxs-lookup"><span data-stu-id="2b726-205">Id</span></span>  |
|---------|
|<span data-ttu-id="2b726-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="2b726-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="2b726-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="2b726-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="2b726-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="2b726-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="2b726-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="2b726-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="2b726-210">CSV ファイルを作成したら、CSV ファイルで指定したチームを移動するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="2b726-210">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="2b726-211">StaffHub teams が Teams に移行されたことを確認する (近日公開)</span><span class="sxs-lookup"><span data-stu-id="2b726-211">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="2b726-212">組織内のすべてのチームの一覧を取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b726-212">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="2b726-213">チームの利用状況を監視する</span><span class="sxs-lookup"><span data-stu-id="2b726-213">Monitor Teams usage</span></span>

<span data-ttu-id="2b726-214">利用状況レポートは、使用パターンをより理解しやすくするのに役立ちます。また、組織全体でトレーニングとコミュニケーション作業の優先順位を決定する場所について理解を深めます。</span><span class="sxs-lookup"><span data-stu-id="2b726-214">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="2b726-215">シフトは Teams のアプリであるため、チームレポートで利用状況を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2b726-215">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="2b726-216">詳細については、microsoft [teams 管理センターのチームレポート](../../teams-analytics-and-reports/teams-reporting-reference.md)と、 [microsoft 365 管理センターの teams アクティビティレポート](../../teams-activity-reports.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b726-216">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2b726-217">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2b726-217">Related topics</span></span>
- [<span data-ttu-id="2b726-218">Microsoft StaffHub はまもなく廃止予定です</span><span class="sxs-lookup"><span data-stu-id="2b726-218">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="2b726-219">Microsoft Teams で組織のシフト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="2b726-219">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="2b726-220">StaffHub PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="2b726-220">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
