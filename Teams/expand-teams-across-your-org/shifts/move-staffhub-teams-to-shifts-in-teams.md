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
description: Microsoft StaffHub チームを移動し、マイクロソフトのチームの変化へのデータのスケジュールを設定する方法について説明します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14f94428ddeba7b5a648b4b8dbd7bd5ef8fae0e4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32246101"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="9b62e-103">マイクロソフト チームの変化に、マイクロソフトの StaffHub チームを移動します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b62e-104">2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="9b62e-105">マイクロソフトのチームに StaffHub 機能が進められています。</span><span class="sxs-lookup"><span data-stu-id="9b62e-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="9b62e-106">今日では、チームには、スケジュール管理のためのシフトのアプリケーションが含まれていて、その他の機能が時間の経過と共に展開されます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="9b62e-107">StaffHub は、2019 年 10 月 1 日ですべてのユーザーの作業を停止します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="9b62e-108">StaffHub を開こうとするとすべての人がチームをダウンロードすることを指示するメッセージ表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="9b62e-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b62e-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="9b62e-110">この資料で説明した機能は、まだリリースされていません。</span><span class="sxs-lookup"><span data-stu-id="9b62e-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="9b62e-111">発表されてはまもなく、2019 の 4 月の最後の方です。</span><span class="sxs-lookup"><span data-stu-id="9b62e-111">It's been announced, and is coming soon, towards the end of April 2019.</span></span> <span data-ttu-id="9b62e-112">管理者にする場合を調べることができますこのが使用できます ( [Microsoft 365 管理センター](https://portal.office.com/adminportal/home)) のメッセージ センターにするとします。</span><span class="sxs-lookup"><span data-stu-id="9b62e-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="9b62e-113">チームでシフトのアプリケーションでは、スケジュール、および shift キーを交換し、日常的に発生するキャンセルの一定のフローを管理するための単純なアプローチを提供します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="9b62e-114">チーム メンバーは、スケジュールにアクセスできるし、shift キーを押しの情報直接アプリケーションでは、プレファレンスを設定するようにデバイスの間で彼らのスケジュールを管理オフ時間を要求します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="9b62e-115">この資料では、組織の StaffHub チームを移動し、チームの変化へのデータのスケジュールを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="9b62e-116">1 つまたは 2 つの StaffHub チームと共同で小規模なビジネスや StaffHub チームの何百もの大規模な企業であれ、ここにある管理者ガイドを成功に導くための移行チームを支援する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b62e-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="9b62e-117">この資料の手順を実行するのにはグローバル管理者でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="9b62e-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="9b62e-118">実行していない場合必要がある[StaffHub 退職に関する FAQ](microsoft-staffhub-to-be-retired.md)を参照する必要があります質問に対する回答を得ます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="9b62e-119">チームの移動について理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b62e-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="9b62e-120">チームに移行する時期</span><span class="sxs-lookup"><span data-stu-id="9b62e-120">When to move to Teams</span></span>

<span data-ttu-id="9b62e-121">効果的な 2019 年 10 月 1日 StaffHub は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="9b62e-122">今日のチームの使用を開始し、組織のチームと StaffHub からのユーザーの移行を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b62e-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="9b62e-123">スケジュール管理を使用する最も一般的に使用される機能は、StaffHub をされていることをお勧めシフト アプリケーションを使用して、チームで前方に移動します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="9b62e-124">チームにどのような移動します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-124">What is moved to Teams</span></span>

<span data-ttu-id="9b62e-125">チームには、ユーザーの詳細情報、スケジュール情報、およびチャットとファイルのデータが移行します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="9b62e-126">これには、チームのメンバーシップ、チームのスケジュール、およびチャットおよび過去 90 日間のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="9b62e-127">StaffHub のすべてのチームには、対応する Office 365 のグループが必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b62e-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="9b62e-128">StaffHub チームには、それに関連付けられている Office 365 グループが割り当てられていない、1 つの移行をサポートする自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="9b62e-129">チームとチームと StaffHub の間でグループの名前付けの違いを指定するには、チーム内の別のチーム名を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="9b62e-130">チームに StaffHub からのチームを移行してユーザーは、彼らのスケジュールへのアクセスを StaffHub でチームの変化にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="9b62e-131">システム停止を最小限に抑えるとするを採用し、チームを促進する組織全体でこの変更を通信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b62e-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span>

## <a name="prepare"></a><span data-ttu-id="9b62e-132">準備</span><span class="sxs-lookup"><span data-stu-id="9b62e-132">Prepare</span></span>

<span data-ttu-id="9b62e-133">チームへの移行を準備するには。</span><span class="sxs-lookup"><span data-stu-id="9b62e-133">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="9b62e-134">Teams のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9b62e-134">Assign Teams licenses</span></span>

<span data-ttu-id="9b62e-135">各ユーザーは[、対象となる計画](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)からアクティブな Microsoft 365 または Office 365 のライセンスが必要し、チームのライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b62e-135">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="9b62e-136">チームのライセンスをユーザーに割り当て、それらにアクセス チーム。</span><span class="sxs-lookup"><span data-stu-id="9b62e-136">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="9b62e-137">Microsoft 365 の管理センターでのチームのライセンスを管理します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-137">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9b62e-138">詳細については、[チームへのユーザー アクセスの管理](../../user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b62e-138">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9b62e-139">組織は、ビジネスの Skype を使用しているすべてのユーザーをチームに移動する準備がわからない場合は、ビジネスの Skype と共にチームを実行できるよう、先頭行者のチームを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-139">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="9b62e-140">*島*と呼ばれるこの共存モードでは、各クライアント アプリケーションは、別のソリューションとして動作します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-140">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="9b62e-141">詳細については、[チームの理解とビジネスの共存と相互運用性の Skype](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b62e-141">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="9b62e-142">Azure AD 内の id を持たない StaffHub ユーザーのアカウントをプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="9b62e-142">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="9b62e-143">各マネージャーとチーム メンバーに、Azure Active directory (AD の Azure) の id が必要です。</span><span class="sxs-lookup"><span data-stu-id="9b62e-143">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="9b62e-144">ユーザー Azure AD で id を持っていない場合、は、それらのアカウントを準備します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-144">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="9b62e-145">これを行うには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-145">Here's how.</span></span>

- <span data-ttu-id="9b62e-146">StaffHub チーム所有者およびマネージャーはダミーか、アクティブでないアカウントを変換し、StaffHub チームの設定] ページで有効な upn のユーザーの電子メール アドレスを変更することによって StaffHub でプロビジョニングされているアカウントにリンクします。</span><span class="sxs-lookup"><span data-stu-id="9b62e-146">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="9b62e-147">StaffHub チームの準備ではないアカウントを削除し、アカウントを追加、[削除 StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps)コマンドレットは、UPN を使用してバックアップし、管理者は、[追加 StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps)を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-147">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="9b62e-148">StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="9b62e-148">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="9b62e-149">いない場合は、 [StaffHub の PowerShell モジュールをインストール](install-the-staffhub-powershell-module.md)します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-149">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="9b62e-150">StaffHub チームを移動すると、移動要求は、常に前提条件をチェックします。</span><span class="sxs-lookup"><span data-stu-id="9b62e-150">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="9b62e-151">移動要求が失敗する理由の理由を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-151">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="9b62e-152">サインインしているユーザーは、グローバル管理者ではありません。</span><span class="sxs-lookup"><span data-stu-id="9b62e-152">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="9b62e-153">チームはテナント内のすべてのユーザーに対して無効になります。</span><span class="sxs-lookup"><span data-stu-id="9b62e-153">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="9b62e-154">テナントで office 365 のグループの作成が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="9b62e-154">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="9b62e-155">StaffHub 別子ですが正しくないか、メンバーが存在しません。</span><span class="sxs-lookup"><span data-stu-id="9b62e-155">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="9b62e-156">StaffHub チームには、Azure AD のアカウントにリンクされていないメンバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b62e-156">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="9b62e-157">パイロットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-157">Run a pilot</span></span>

<span data-ttu-id="9b62e-158">早期採用者のグループの 2 つまたは 3 つの StaffHub チームを移動することによって開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b62e-158">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="9b62e-159">パイロットを実行すると、移行計画を調整し、チーム、組織内のすべての StaffHub のチームに移動する準備ができていることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-159">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="9b62e-160">組織全体での採用を推進を支援できるエキスパートを識別します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-160">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="9b62e-161">段階的なアプローチを必要としている中小企業の場合、このセクションの手順は、StaffHub からのチームに、スイッチを確認する必要がありますすべてで可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9b62e-161">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="9b62e-162">パイロット チームを特定します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-162">Identify pilot teams</span></span>

<span data-ttu-id="9b62e-163">パイロット チームの 2 つまたは 3 つの識別にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9b62e-163">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="9b62e-164">すべてのチーム メンバーは、スケジュールの管理し通信を行い、お互いの共同作業をチームでシフトを使用してにコミットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b62e-164">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="9b62e-165">エキスパートのチームを識別します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-165">Identify team champions</span></span>

<span data-ttu-id="9b62e-166">パイロット チーム間でのエキスパートを特定し、シフトを浸透させるために参加します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-166">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="9b62e-167">チームのエキスパートが, それらの動作に関するサポートとガイダンスをチーム メンバーに提供する独自のな学習項目を共有します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-167">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="9b62e-168">エキスパートのチームは、チームの所有者または管理者にあります。</span><span class="sxs-lookup"><span data-stu-id="9b62e-168">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="9b62e-169">チーム チャンピオンには、チーム メンバー[チームのクライアントを取得](../../get-clients.md)するすべてのユーザーの専用の時間を設定、チームにサインインするのには、シフトでスケジュールを確認し、お互いにチャットを開始する必要がありますを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-169">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="9b62e-170">StaffHub に慣れているユーザーになります起動してすぐにシフトで。</span><span class="sxs-lookup"><span data-stu-id="9b62e-170">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="9b62e-171">指定することもに[シフトのため](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)に追加のヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-171">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="9b62e-172">(準備中) StaffHub チームを移動します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-172">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="9b62e-173">一度に 1 つの StaffHub チームを移動するのには次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-173">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="9b62e-174">パイロット チームが、この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b62e-174">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="9b62e-175">後で、組織内のすべての StaffHub のチームに移動する準備ができたら、 [StaffHub チームを移動する](#move-your-staffhub-teams-coming-soon)手順について、一度に複数のチームを移動参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b62e-175">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="9b62e-176">StaffHub チームを移動するのには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-176">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="9b62e-177">ここでは、StaffHub チームをチームに移動する要求を送信するときのような応答の例です。</span><span class="sxs-lookup"><span data-stu-id="9b62e-177">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="9b62e-178">移動要求のステータスを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-178">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="9b62e-179">ここでは、移動の実行中のときのような応答の例です。</span><span class="sxs-lookup"><span data-stu-id="9b62e-179">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="9b62e-180">チームに StaffHub からの移行を行う</span><span class="sxs-lookup"><span data-stu-id="9b62e-180">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="9b62e-181">意識を向上させる</span><span class="sxs-lookup"><span data-stu-id="9b62e-181">Raise awareness</span></span>

<span data-ttu-id="9b62e-182">パイロット チームより先に進む準備ができたらし、チーム、組織の StaffHub のチームに移動することが重要、組織全体で変更を最初に通信します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-182">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="9b62e-183">意識を向上させる、刺激を生成し、プロジェクトに適用するには、シフトとチームへの移行に関する単語を拡散します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-183">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="9b62e-184">(近日公開予定)、StaffHub チームを移動します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-184">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="9b62e-185">StaffHub チームを一括で移動するのには次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-185">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="9b62e-186">組織内のすべての StaffHub のチームを移動したり、特定の StaffHub チームを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-186">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="9b62e-187">StaffHub チームが 1 つずつ移動する場合は、 [StaffHub チームの移動](#move-a-staffhub-team-coming-soon)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b62e-187">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="9b62e-188">(準備中) すべての StaffHub チームを移動します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-188">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="9b62e-189">組織のすべての StaffHub チームの一覧を取得するのには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-189">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="9b62e-190">次に、すべてのチームを移動するのには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-190">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="9b62e-191">ここでは、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="9b62e-191">Here's an example of the response.</span></span>

<span data-ttu-id="9b62e-192">チームへ既に移動されたか、チーム内に既に存在するすべてのチームのジョブ Id は null になります""ジョブは、そのチームの移動に提出する必要があるようです。</span><span class="sxs-lookup"><span data-stu-id="9b62e-192">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="9b62e-193">(準備中) 特定の StaffHub チームを移動します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-193">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="9b62e-194">組織内のすべての StaffHub チームの Id の一覧を取得するのには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-194">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="9b62e-195">によって返される結果に、`Get-StaffHubteamsForTenant`コマンドレットを実行する前、移動するには、チーム Id」を選択し、コンマ区切り値 (CSV) ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-195">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="9b62e-196">ここでは、CSV ファイルの書式設定方法の例です。</span><span class="sxs-lookup"><span data-stu-id="9b62e-196">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="9b62e-197">Id</span><span class="sxs-lookup"><span data-stu-id="9b62e-197">Id</span></span>  |
|---------|
|<span data-ttu-id="9b62e-198">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="9b62e-198">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="9b62e-199">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="9b62e-199">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="9b62e-200">TEAM_b42d0fa2-0 fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="9b62e-200">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="9b62e-201">TEAM_b42d0fa2-0 fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="9b62e-201">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="9b62e-202">CSV ファイルを作成した後は、CSV ファイルで指定したチームを移動するのには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-202">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="9b62e-203">(準備中) チーム、StaffHub チームに移動することを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-203">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="9b62e-204">シフトで、組織のすべてのチームの一覧を取得するのには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-204">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="9b62e-205">チームの使用率を監視します。</span><span class="sxs-lookup"><span data-stu-id="9b62e-205">Monitor Teams usage</span></span>

<span data-ttu-id="9b62e-206">利用状況レポートの使用パターンを理解し、組織全体でのトレーニングとコミュニケーションの取り組みに優先順位をどこに情報を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-206">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="9b62e-207">シフトはチームのアプリケーションであるため、チームのレポートでの使用状況を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9b62e-207">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="9b62e-208">詳細については、[チームは、マイクロソフト チームの管理センターに報告](../../teams-analytics-and-reports/teams-reporting-reference.md)し、 [Microsoft 365 の管理センターでチームの活動レポート](../../teams-activity-reports.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b62e-208">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9b62e-209">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9b62e-209">Related topics</span></span>
- [<span data-ttu-id="9b62e-210">Microsoft StaffHub はまもなく廃止予定です</span><span class="sxs-lookup"><span data-stu-id="9b62e-210">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="9b62e-211">Microsoft Teams で組織のシフト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="9b62e-211">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="9b62e-212">StaffHub PowerShell 参照</span><span class="sxs-lookup"><span data-stu-id="9b62e-212">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
