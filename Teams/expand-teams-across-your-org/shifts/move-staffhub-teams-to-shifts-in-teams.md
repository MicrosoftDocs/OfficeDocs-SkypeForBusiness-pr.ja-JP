---
title: StaffHub チーム を Microsoft Teams のシフトに移動する
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu, gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub のチームとスケジュール データを Microsoft Teams のシフトに移動する方法を説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- SPO_Content
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4060dae11ad90793c6124b1b37971b15437caf39
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825755"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="70a8b-103">Microsoft StaffHub のチームを Microsoft Teams のシフトに移動する</span><span class="sxs-lookup"><span data-stu-id="70a8b-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70a8b-104">2019 年 12 月 31 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="70a8b-105">Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="70a8b-106">現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="70a8b-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="70a8b-107">StaffHub は、2019 年 12 月 31 日以降すべてのユーザーがご利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="70a8b-108">ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="70a8b-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="70a8b-110">Teams 内のシフト アプリでは、スケジュール管理と日ごと常に発生し続けるシフトの入れ替えや取り消しのための簡単なアプローチが提供されます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="70a8b-111">チーム メンバーはアプリを使用して複数のデバイスからスケジュールやシフトの情報に直接アクセスでき、基本設定、スケジュール管理、休暇の申請などの操作を行えます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="70a8b-112">この記事では、組織の StaffHub のチームとスケジュール データを Teams 内のシフトに移動させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="70a8b-113">取り扱う内容:</span><span class="sxs-lookup"><span data-stu-id="70a8b-113">It covers:</span></span>

- [<span data-ttu-id="70a8b-114">Teams への移行について知っておくべき事項</span><span class="sxs-lookup"><span data-stu-id="70a8b-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="70a8b-115">準備</span><span class="sxs-lookup"><span data-stu-id="70a8b-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="70a8b-116">パイロットの実施</span><span class="sxs-lookup"><span data-stu-id="70a8b-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="70a8b-117">パイロットを終了しすべての StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="70a8b-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="70a8b-118">Teams の使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="70a8b-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="70a8b-119">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="70a8b-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="70a8b-120">この管理者向けガイダンスには Teams への移行を成功させるために必要な情報が含まれ、少数の StaffHub チームを運用する小規模な事業のお客様にも、StaffHub チームが何百もある大企業のお客様にもご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="70a8b-121">この記事の手順を実行するには、全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="70a8b-122">「[StaffHub の廃止に関するよくあるご質問](microsoft-staffhub-to-be-retired.md)」をまだご覧になられていない場合はご覧いただき、不明点に関する答えをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="70a8b-123">Teams への移行について知っておくべき事項</span><span class="sxs-lookup"><span data-stu-id="70a8b-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="70a8b-124">Teams に移行する時期</span><span class="sxs-lookup"><span data-stu-id="70a8b-124">When to move to Teams</span></span>

<span data-ttu-id="70a8b-125">2019 年 12 月 31 日より、StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-125">Effective December 31, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="70a8b-126">Teams の使用を今から開始し、組織のチームとユーザーの StaffHub からの移行を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="70a8b-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="70a8b-127">StaffHub で最もよく使用される機能はスケジュール管理であるため、今後は Teams 内のシフト アプリを使用されることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="70a8b-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="70a8b-128">Teams に移動する内容</span><span class="sxs-lookup"><span data-stu-id="70a8b-128">What is moved to Teams</span></span>

<span data-ttu-id="70a8b-129">StaffHub チームを移動すると、チーム メンバーシップ、ユーザーの詳細、チームのスケジュール、およびチャット データが Teams に移動します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="70a8b-130">StaffHub チームを移動しても、ファイルは移動しません。</span><span class="sxs-lookup"><span data-stu-id="70a8b-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="70a8b-131">チームに移動したいファイルが StaffHub チームに含まれている場合は、別の手順でファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="70a8b-132">各 StaffHub チームには、対応する Office 365 グループが必要です。</span><span class="sxs-lookup"><span data-stu-id="70a8b-132">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="70a8b-133">StaffHub チームが Office 365 グループに関連付けられている場合、チームを移動すると、グループのプライバシー設定が保持されます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-133">If a StaffHub team is associated with an Office 365 Group, the privacy setting of the group is retained when you move the team.</span></span> <span data-ttu-id="70a8b-134">StaffHub チームに Office 365 グループが関連付けられていない場合は、移行を支援するためにプライバシー設定が [プライベート] のグループが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-134">If a StaffHub team doesn't have an Office 365 Group associated with it, a group with a privacy setting of Private is automatically created for you to support the transition.</span></span>  <span data-ttu-id="70a8b-135">Teams と StaffHub ではチームとグループの名前の付け方に違いがあるため、Teams ではチーム名が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-135">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span> 

<span data-ttu-id="70a8b-136">チームを StaffHub から Teams に移動すると、ユーザーは StaffHub のスケジュールにはアクセスできなくなり、Teams 内のシフトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-136">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="70a8b-137">中断を最小限に抑え、Teams の導入をユーザーに促すために、この変更について組織全体に伝達することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="70a8b-137">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="70a8b-138">Azure AD Premium を使用している場合は、[レポートを実行](run-report-to-show-staffhub-usage.md)して、組織の StaffHub ユーザーのうち、この変更について知っておく必要があるユーザーのリストを取得できます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-138">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="70a8b-139">StaffHub チームを Teams に移動した後は、それをロールバックするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="70a8b-139">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="70a8b-140">チームを移動するときのユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="70a8b-140">User experience when you move a team</span></span>

<span data-ttu-id="70a8b-141">StaffHub から Teams 内のシフトにチームが切り替えられる際のユーザーのダウンタイムは、ほんのわずかです (あったとしても、1 秒未満です)。</span><span class="sxs-lookup"><span data-stu-id="70a8b-141">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="70a8b-142">ユーザーは、Teams への移行が完了するまで StaffHub を引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-142">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="70a8b-143">移行が完了すると、チームのスケジュールにアクセスするには Teams 内のシフトの使用を開始する必要があることを通知するメッセージがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-143">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="70a8b-144">StaffHub チームが Teams に移行した後に StaffHub でユーザーに表示されるメッセージの例です。</span><span class="sxs-lookup"><span data-stu-id="70a8b-144">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="70a8b-145">![ユーザーに表示されるメッセージの例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "StaffHub チームが Teams に移行した後に StaffHub でユーザーに表示されるメッセージの例")</span><span class="sxs-lookup"><span data-stu-id="70a8b-145">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="70a8b-146">準備</span><span class="sxs-lookup"><span data-stu-id="70a8b-146">Prepare</span></span>

<span data-ttu-id="70a8b-147">Teams に移動するための準備を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-147">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="70a8b-148">前提条件を満たしていることを確認する</span><span class="sxs-lookup"><span data-stu-id="70a8b-148">Check that prerequisites are met</span></span>

<span data-ttu-id="70a8b-149">StaffHub チームを Teams に移動する前に、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-149">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="70a8b-150">サインインしているユーザーが全体管理者であること。</span><span class="sxs-lookup"><span data-stu-id="70a8b-150">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="70a8b-151">Teams がテナント内のすべてのユーザーに対して有効化されていること。</span><span class="sxs-lookup"><span data-stu-id="70a8b-151">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="70a8b-152">Office 365 グループの作成がテナントで有効になっていること。</span><span class="sxs-lookup"><span data-stu-id="70a8b-152">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="70a8b-153">StaffHub の teamId が有効であること。</span><span class="sxs-lookup"><span data-stu-id="70a8b-153">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="70a8b-154">StaffHub チームには少なくとも 1 人のチーム所有者がいること。</span><span class="sxs-lookup"><span data-stu-id="70a8b-154">The StaffHub team has at least one team owner.</span></span>
- <span data-ttu-id="70a8b-155">StaffHub チームにメンバーが含まれていること。</span><span class="sxs-lookup"><span data-stu-id="70a8b-155">The StaffHub team contains members.</span></span>
- <span data-ttu-id="70a8b-156">すべての StaffHub チーム メンバーが、Azure AD アカウントにリンクされていること。</span><span class="sxs-lookup"><span data-stu-id="70a8b-156">All StaffHub team members are linked to an Azure AD account.</span></span>
- <span data-ttu-id="70a8b-157">すべての StaffHub チーム メンバーに Teams ライセンスが割り当てられていること。</span><span class="sxs-lookup"><span data-stu-id="70a8b-157">All StaffHub team members are assigned a Teams license.</span></span>  

<span data-ttu-id="70a8b-158">これらの前提条件を満たしていない場合、移動の要求は失敗します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-158">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="70a8b-159">Teams のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="70a8b-159">Assign Teams licenses</span></span>

<span data-ttu-id="70a8b-160">各ユーザーは、[対象プラン](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)の有効な Microsoft 365 または Office 365 ライセンスを持っている必要があり、Teams ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-160">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="70a8b-161">Teams ライセンスを割り当てられたユーザーは Teams にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-161">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="70a8b-162">Teams ライセンスの管理は、Microsoft 365 管理センターで行います。</span><span class="sxs-lookup"><span data-stu-id="70a8b-162">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="70a8b-163">詳細については、「[Microsoft Teams へのユーザー アクセスを管理する](../../user-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-163">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="70a8b-164">Skype for Business を使用している組織ですべてのユーザーを Teams に移行する準備ができていない場合は、現場担当者に対して Teams を有効にし、これらのユーザーが Teams を Skype for Business と併用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="70a8b-164">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="70a8b-165">「*アイランド*」と呼ばれるこの共存モードでは、各クライアント アプリが別個のソリューションとして動作します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-165">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="70a8b-166">詳細については、「[Microsoft Teams と Skype for Business の共存と相互運用性について](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-166">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a><span data-ttu-id="70a8b-167">StaffHub PowerShell モジュールのプレリリース版をインストールする</span><span class="sxs-lookup"><span data-stu-id="70a8b-167">Install the prerelease version of the StaffHub PowerShell module</span></span>

<span data-ttu-id="70a8b-168">[StaffHub PowerShell モジュールのプレリリース版のインストールがまだの場合は、インストールします](install-the-staffhub-powershell-module.md)。</span><span class="sxs-lookup"><span data-stu-id="70a8b-168">If you haven't already, [install the prerelease version of the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="70a8b-169">StaffHub チームを Teams に移行するには、プレリリース版のモジュールがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-169">You must have the prerelease version of the module installed to move your StaffHub teams to Teams.</span></span>

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="70a8b-170">リンクがない StaffHub チーム メンバーの Azure AD アカウントをリンクする</span><span class="sxs-lookup"><span data-stu-id="70a8b-170">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="70a8b-171">各 StaffHub チーム メンバーは、Azure Active Directory （Azure AD） アカウントにリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-171">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="70a8b-172">次のシナリオのいずれかに該当する場合、組織内のユーザーは Azure AD アカウントにリンクされません。</span><span class="sxs-lookup"><span data-stu-id="70a8b-172">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="70a8b-173">チームの所有者が、Azure AD アカウントを持っていないユーザーを追加しました。</span><span class="sxs-lookup"><span data-stu-id="70a8b-173">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="70a8b-174">チームの所有者がユーザーを StaffHub チームに招待しましたが、そのユーザーは招待を承諾しませんでした。</span><span class="sxs-lookup"><span data-stu-id="70a8b-174">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="70a8b-175">これらのユーザーには非アクティブなアカウントがあり、Unknown、Invited、または InviteRejected のユーザー状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-175">These users have inactive accounts and show a user state of Unknown, Invited, or InviteRejected.</span></span> <span data-ttu-id="70a8b-176">これらのユーザーの Azure AD アカウントをリンクできます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-176">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="70a8b-177">これを行うには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-177">Here's how.</span></span>

#### <a name="get-a-list-of-all-inactive-accounts-on-staffhub-teams"></a><span data-ttu-id="70a8b-178">StaffHub チームで非アクティブなすべてのアカウントのリストを取得する</span><span class="sxs-lookup"><span data-stu-id="70a8b-178">Get a list of all inactive accounts on StaffHub teams</span></span>

<span data-ttu-id="70a8b-179">次の一連のコマンドを実行して、StaffHub チームのすべての非アクティブなアカウントのリストを取得し、CSV ファイルにリストをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="70a8b-179">Run the following series of commands to get a list of all inactive accounts on StaffHub teams and export the list to a CSV file.</span></span> <span data-ttu-id="70a8b-180">各コマンドは個別に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-180">Each command should be run separately.</span></span>

```PowerShell
$InvitedUsersObject = @()

$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }

foreach($team in $StaffHubTeams[0])
{ 
    Write-host $team.name
    $StaffHubUsers = Get-StaffHubMember -TeamId $team.Id | where {$_.State -eq "Invited"}
    foreach($StaffHubUser in $StaffHubUsers) {
        $InvitedUsersObject  += New-Object PsObject -Property @{
          "TeamID"="$($team.Id)"
          "TeamName"="$($team.name)"
          "MemberID"="$($StaffHubUser.Id)"
            }
    }
}

$InvitedUsersObject | SELECT * | export-csv InvitedUsers.csv -NoTypeInformation  
```

#### <a name="link-the-account"></a><span data-ttu-id="70a8b-181">アカウントをリンクする</span><span class="sxs-lookup"><span data-stu-id="70a8b-181">Link the account</span></span>

<span data-ttu-id="70a8b-182">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-182">Do one of the following:</span></span>

- <span data-ttu-id="70a8b-183">アカウントを変換してリンクします。</span><span class="sxs-lookup"><span data-stu-id="70a8b-183">Convert and link the account.</span></span>

  <span data-ttu-id="70a8b-184">StaffHub チームの所有者と管理者は、StaffHub チーム設定ページでユーザーのメール アドレスを有効な UPN に変更することで、非アクティブなアカウントを変換して、StaffHub の Azure AD アカウントにリンクできます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-184">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="70a8b-185">リンクされていないアカウントを削除し、UPN を使用してアカウントを追加し直します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-185">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="70a8b-186">[Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) コマンドレットを実行して、StaffHub チームからプロビジョニングされていないアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-186">Run the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="70a8b-187">[Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) コマンドレットを実行し、UPN を使用して StaffHub チームにアカウントを追加し直します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-187">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="70a8b-188">非アクティブなアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-188">Remove the inactive account.</span></span> <span data-ttu-id="70a8b-189">ユーザー アカウントが不要になった場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-189">Use this option if the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="70a8b-190">FirstLineWorker アプリのセットアップ ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="70a8b-190">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="70a8b-191">Teams には、組織の現場担当者にとって最も重要なアプリをハイライトするために Teams をカスタマイズするのに使用できる、FirstlineWorker アプリ セットアップ ポリシーが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="70a8b-191">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="70a8b-192">このポリシーをユーザーに割り当てると、すばやく簡単にアクセスできるよう、ポリシー内のアプリがチームのアプリ バーに固定されます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-192">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="70a8b-193">Teams に追加された他のアプリは、Teams のデスクトップと Web クライアントで [**その他のアプリ**] をクリックすると表示されます。Teams モバイル クライアントの場合は、上方向にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="70a8b-193">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="70a8b-194">既定では、FirstlineWorker アプリのセットアップ ポリシーには、アクティビティ、シフト、チャット、および通話の各アプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="70a8b-194">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="70a8b-195">FirstlineWorker アプリのセットアップ ポリシーをユーザーに割り当てる手順については、「[FirstlineWorker アプリのセットアップ ポリシーを使用して Teams にシフトをピン留めする](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-195">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="70a8b-196">ポリシーの割り当て後、それが有効になるまで最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-196">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="70a8b-197">StaffHub のチームとユーザーを Teams に移動する少なくとも 1 週間前までにこの手順を完了しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="70a8b-197">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="70a8b-198">ユーザーが Teams にサインインしたら、シフト アプリがユーザーに表示され、アクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-198">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="70a8b-199">また、アプリのカスタム セットアップ ポリシーを作成し、アプリのグローバル セットアップ ポリシーでその設定を編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-199">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="70a8b-200">詳細については、「[Teams アプリのセットアップ ポリシーを管理する](../../teams-app-setup-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-200">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="70a8b-201">Teams にユーザーをオンボードする</span><span class="sxs-lookup"><span data-stu-id="70a8b-201">Onboard users to Teams</span></span>

<span data-ttu-id="70a8b-202">オンボードディング戦略の一環として、ユーザーが Teams を理解できるよう、トレーニングとガイダンスをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-202">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="70a8b-203">Teams のクライアントの入手先やトレーニングおよびサポートを受けられる場所がわかるように、次のリソースをユーザーと共有します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-203">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="70a8b-204">Teams の Web クライアント</span><span class="sxs-lookup"><span data-stu-id="70a8b-204">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="70a8b-205">デスクトップとモバイル クライアントのダウンロード リンク</span><span class="sxs-lookup"><span data-stu-id="70a8b-205">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="70a8b-206">Teams のトレーニング用ビデオ</span><span class="sxs-lookup"><span data-stu-id="70a8b-206">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="70a8b-207">Teams のヘルプ ドキュメント</span><span class="sxs-lookup"><span data-stu-id="70a8b-207">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="70a8b-208">Teams の展開と Teams の導入推進に関するガイダンスは、「[Microsoft Teams の展開方法](../../How-to-roll-out-teams.md)」および「[Microsoft Teams を導入する](../../adopt-microsoft-teams-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-208">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="70a8b-209">パイロットの実施</span><span class="sxs-lookup"><span data-stu-id="70a8b-209">Conduct a pilot</span></span>

<span data-ttu-id="70a8b-210">早期導入者の限られたグループとして、手始めに 2 つか 3 つの StaffHub チームの移行を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="70a8b-210">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="70a8b-211">パイロットの実施により、移行計画を微調整し、組織のすべての StaffHub チームをチームに移行する準備を整えられます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-211">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="70a8b-212">また、先導役となるユーザーを特定して、組織全体での導入の促進につなげることもできます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-212">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="70a8b-213">小規模なビジネスであるために段階的な手法を必要としない場合、StaffHub から Teams への切り替えに必要な手順は、すべてこのセクションで説明されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-213">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="70a8b-214">パイロット チームの特定</span><span class="sxs-lookup"><span data-stu-id="70a8b-214">Identify pilot teams</span></span>

<span data-ttu-id="70a8b-215">パイロット チームを特定するためにユーザーに連絡をとります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-215">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="70a8b-216">スケジュールの管理やチーム内での連絡と共同作業に Teams 内のシフトを使用することに、チーム メンバー全員がコミットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-216">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="70a8b-217">Teams の先導者の特定</span><span class="sxs-lookup"><span data-stu-id="70a8b-217">Identify team champions</span></span>

<span data-ttu-id="70a8b-218">パイロット チームの中で先導者を特定し、シフトを普及させるための協力を依頼します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-218">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="70a8b-219">Teams の先導者は、業務に熱心に取り組み、自身の知見をチーム メンバーと共有してサポートやガイダンスを提供できるユーザーたちです。</span><span class="sxs-lookup"><span data-stu-id="70a8b-219">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="70a8b-220">Teams の先導者には、チームの所有者またはマネージャーがなれます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-220">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="70a8b-221">すべてのユーザーが [Teams のクライアントを入手](../../get-clients.md)し、Teams にサインインして自分のスケジュールをシフトでチェックし、他のメンバーとチャットを開始できるよう、Teams の先導者はチーム メンバーの設定が行われていることをしっかり時間をかけて確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-221">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="70a8b-222">StaffHub に慣れているユーザーは、シフトをすばやく稼働させられます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-222">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="70a8b-223">追加のヘルプが必要なユーザーには、「[シフトのヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)」を参照するよう伝えることもできます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-223">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="70a8b-224">特定のStaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="70a8b-224">Move a StaffHub team</span></span>

<span data-ttu-id="70a8b-225">これらの手順を使用して、一度に 1 チームずつ StaffHub チームを移動します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-225">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="70a8b-226">このアプローチをパイロット チームについて使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="70a8b-226">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="70a8b-227">後に、組織のすべての StaffHub チームを移動する準備ができた場合は、一度に複数のチームを移動させる手順ついて、「[StaffHub チームを移動する](#move-your-staffhub-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-227">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="70a8b-228">StaffHub チームを移動するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-228">Run the following to move a StaffHub team.</span></span>

```PowerShell
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="70a8b-229">例:</span><span class="sxs-lookup"><span data-stu-id="70a8b-229">Example:</span></span>

```PowerShell
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="70a8b-230">StaffHub チームを Teams に移動する要求を送信した際に返される応答の例です。</span><span class="sxs-lookup"><span data-stu-id="70a8b-230">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```output
 jobId                                      teamId                                      teamAlreadyInMicrosofteams  
---------------------------------------    ----------------------------------------    ---------------------------          
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="70a8b-231">移動要求の状態を確認するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-231">To check the status of a move request, run the following.</span></span>

```PowerShell
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="70a8b-232">例:</span><span class="sxs-lookup"><span data-stu-id="70a8b-232">Example:</span></span>

```PowerShell
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="70a8b-233">移動の進行中に返される応答の例です。</span><span class="sxs-lookup"><span data-stu-id="70a8b-233">Here's an example of the response you get when a move is in progress.</span></span>

```output
jobId                                     status       teamId                                     isO365GroupCreated  Error
----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="70a8b-234">StaffHub チームから Teams にファイルを移動する</span><span class="sxs-lookup"><span data-stu-id="70a8b-234">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="70a8b-235">この手順は、Teams に移動する StaffHub チームが、やはり Teams に移動させたいファイルを持っている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-235">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="70a8b-236">ファイルは SharePoint Online 内で直接移動する方法でも、PowerShell を使用する方法でも移動できます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-236">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="70a8b-237">SharePoint Online 内で行う場合</span><span class="sxs-lookup"><span data-stu-id="70a8b-237">In SharePoint Online</span></span>

<span data-ttu-id="70a8b-238">「[SharePoint Online でファイルを移動する方法](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-238">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="70a8b-239">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="70a8b-239">Using PowerShell</span></span>

<span data-ttu-id="70a8b-240">まだの場合、[SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588) をダウンロードしてインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-240">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="70a8b-241">ファイルを移動するために必要なコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="70a8b-241">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="70a8b-242">[Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) コマンドレットを使用して、SharePoint Online チームサイトに接続します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-242">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```PowerShell
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="70a8b-243">StaffHub から Teams に移動する各ファイルに対して [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) コマンドレットを使用してファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-243">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```PowerShell
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="70a8b-244">複数のファイルを移動するには、ファイルをループして、ループに対して 2 つ目のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-244">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="70a8b-245">セッションがアクティブなままの場合は、最初のコマンドを繰り返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="70a8b-245">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="70a8b-246">パイロットを終了しすべての StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="70a8b-246">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="70a8b-247">認知度を上げる</span><span class="sxs-lookup"><span data-stu-id="70a8b-247">Raise awareness</span></span>

<span data-ttu-id="70a8b-248">パイロット チームの移動を終了し組織の StaffHub チームをチームに移行する準備ができた場合は、変更について組織全体に通知することが重要です。</span><span class="sxs-lookup"><span data-stu-id="70a8b-248">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="70a8b-249">シフトと Teams への移行に関する情報を広めて認知度を上げ、期待感を高めることによって導入の促進を図ります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-249">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="70a8b-250">StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="70a8b-250">Move your StaffHub teams</span></span>

<span data-ttu-id="70a8b-251">これらの手順を使用して、StaffHub チームを一括移動します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-251">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="70a8b-252">組織のすべての StaffHub チームを移動する方法も、特定の StaffHub チームを移動する方法も選べます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-252">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="70a8b-253">StaffHub チームを1つずつ移動する場合は、「[StaffHub チームを移動する](#move-a-staffhub-team)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-253">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="70a8b-254">すべての StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="70a8b-254">Move all StaffHub teams</span></span>

<span data-ttu-id="70a8b-255">次を実行して、組織内のすべての StaffHub チームのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-255">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```PowerShell
$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

<span data-ttu-id="70a8b-256">次を実行してすべてのチームを移動します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-256">Then, run the following to move all teams.</span></span>

```PowerShell
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="70a8b-257">応答の例を下に示します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-257">Here's an example of the response.</span></span>

<span data-ttu-id="70a8b-258">既に Teams に移動されたか既に Teams に存在するチームの場合、そうしたチームを移動するためのジョブを送信する必要がないため、jobId は "null" になります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-258">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```output
jobId                                      teamId                                      teamAlreadyInMicrosofteams  
----------------------------------------   -----------------------------------------   --------------------------         
null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="70a8b-259">特定の StaffHub チームを移動する</span><span class="sxs-lookup"><span data-stu-id="70a8b-259">Move specific StaffHub teams</span></span>

<span data-ttu-id="70a8b-260">次を実行して、組織内のすべての StaffHub チームの ID のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-260">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="70a8b-261">先ほど実行した `Get-StaffHubteamsForTenant` コマンドレットによって返された結果で移動するチーム ID を選択し、コンマ区切り値 (CSV) ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-261">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="70a8b-262">CSV ファイルで必要な書式設定の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-262">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="70a8b-263">ID</span><span class="sxs-lookup"><span data-stu-id="70a8b-263">Id</span></span>  |
|---------|
|<span data-ttu-id="70a8b-264">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="70a8b-264">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="70a8b-265">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="70a8b-265">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="70a8b-266">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="70a8b-266">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="70a8b-267">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="70a8b-267">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="70a8b-268">CSV ファイルを作成したら、次のコマンドを実行して CSV ファイルで指定したチームを移動します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-268">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```PowerShell
$StaffHubTeams = Import-Csv .\teams.csv

foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="70a8b-269">StaffHub チームが Teams に移動したことを確認する</span><span class="sxs-lookup"><span data-stu-id="70a8b-269">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="70a8b-270">次を実行して、組織内のすべてのシフトのチームのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-270">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="70a8b-271">StaffHub チームから Teams にファイルを移動する</span><span class="sxs-lookup"><span data-stu-id="70a8b-271">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="70a8b-272">移動した StaffHub チームに Teams に移動するファイルが含まれている場合は、「[StaffHub チームから Teams にファイルを移動する](#move-files-from-a-staffhub-team-to-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-272">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="70a8b-273">Teams の使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="70a8b-273">Monitor Teams usage</span></span>

<span data-ttu-id="70a8b-274">使用状況レポートは、使用パターンを正しく理解するために役立ち、組織全体でのトレーニングとコミュニケーションの取り組みに関する優先順位を決定するのに活用できる見識を提供します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-274">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="70a8b-275">Teams 全体の使用状況、ユーザーが Teams で実行するアクティビティの種類、ユーザーが Teams に接続する方法などを示すレポートを実行できます。</span><span class="sxs-lookup"><span data-stu-id="70a8b-275">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="70a8b-276">詳細については、「[Microsoft Teams 管理センターでの Teams のレポート](../../teams-analytics-and-reports/teams-reporting-reference.md) 」および「[Microsoft 365 管理センターでの Teams のアクティビティ レポート](../../teams-activity-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-276">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="70a8b-277">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="70a8b-277">Troubleshooting</span></span>

<span data-ttu-id="70a8b-278">**失敗エラーの詳細情報を取得する方法**</span><span class="sxs-lookup"><span data-stu-id="70a8b-278">**How to get more information about failure errors**</span></span>

<span data-ttu-id="70a8b-279">チームを移動するときに発生する「失敗」エラーの詳細情報を取得するには、次を実行してください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-279">Run the following to get more information about "Failure" errors that occur when you try to move a team:</span></span>

```PowerShell
Move-StaffHubTeam -TeamId <TeamId>

$res = Get-TeamMigrationJobStatus -JobId <JobId>

$res.Status
```

<span data-ttu-id="70a8b-280">次のいずれかの状態が返されます。成功、失敗、処理中、処理待ち。</span><span class="sxs-lookup"><span data-stu-id="70a8b-280">You'll see one of the following statuses returned: Success, Failure, InProgress, Queued.</span></span>

<span data-ttu-id="70a8b-281">「失敗」が返された場合は、次を実行してエラーの詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-281">If "Failure" is returned, run the following to get more information about the error:</span></span>

```PowerShell
$res.Result.Error.Innererror
```

<span data-ttu-id="70a8b-282">**StaffHub チームを移動するときに、状態が「失敗」と表示され、「ユーザーに該当するSKUカテゴリを取得できませんでした」というエラー メッセージが表示される**</span><span class="sxs-lookup"><span data-stu-id="70a8b-282">**When you try to move a StaffHub team, the status shows as "Failure" and you receive a "Failed to retrieve applicable SKU categories for the user" error message**</span></span>

<span data-ttu-id="70a8b-283">1 人以上のチーム メンバーが Teams ライセンスを持っていない場合に、この問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-283">This can occur if one or more team members don't have a Teams license.</span></span> <span data-ttu-id="70a8b-284">portal.office.com に移動し、グループを見つけ、グループ メンバーに Teams ライセンスが割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-284">Go to portal.office.com, find the group, and then confirm that group members are assigned a Teams license.</span></span>

<span data-ttu-id="70a8b-285">**StaffHub チームを移動するときに、状態が「失敗」と表示され、「チーム所有者が見つかりません」というエラー メッセージが表示される**</span><span class="sxs-lookup"><span data-stu-id="70a8b-285">**When you try to move a StaffHub team, the status shows as "Failure" and you receive a "Team owner not found" error message**</span></span>

<span data-ttu-id="70a8b-286">StaffHub チームに関連付けられているグループにチーム所有者がいない場合に、この問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-286">This can occur if the group that's associated with the StaffHub team doesn't have a team owner.</span></span> <span data-ttu-id="70a8b-287">portal.office.com に移動し、グループを見つけ、1 人以上の所有者をグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-287">Go to portal.office.com, find the group, and then add one or more owners to the group.</span></span>

<span data-ttu-id="70a8b-288">**StaffHub から Teams にファイルを移動しようとすると、"アクセスは拒否されました" というエラー メッセージが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="70a8b-288">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="70a8b-289">これは、自分がメンバーでないプライベートの Office 365 グループ内のファイルを移動しようとした場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="70a8b-289">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="70a8b-290">該当する場合は、[AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) コマンドレットを使用して自分自身を StaffHub チームに追加してからファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-290">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="70a8b-291">ファイルの移動後は、[Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) コマンドレットを使用して、チームから自分自身を削除します。</span><span class="sxs-lookup"><span data-stu-id="70a8b-291">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="70a8b-292">**StaffHub から Teams にファイルを移動しようとすると、[全般] フォルダーが存在しないというエラーが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="70a8b-292">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="70a8b-293">次のコマンドを実行して [全般] フォルダーを SharePoint に追加してから、もう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="70a8b-293">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```PowerShell
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="70a8b-294">関連項目</span><span class="sxs-lookup"><span data-stu-id="70a8b-294">Related topics</span></span>
- [<span data-ttu-id="70a8b-295">Microsoft Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="70a8b-295">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="70a8b-296">Microsoft StaffHub はまもなく廃止予定です</span><span class="sxs-lookup"><span data-stu-id="70a8b-296">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="70a8b-297">Microsoft Teams で組織のシフト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="70a8b-297">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="70a8b-298">StaffHub PowerShell のリファレンス</span><span class="sxs-lookup"><span data-stu-id="70a8b-298">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
