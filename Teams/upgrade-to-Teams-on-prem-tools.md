---
title: Skype for Business オンプレミス展開から Teams にアップグレードするためのツール
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams にアップグレードするためのツール
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5585a2d2995b2f7d470c4d07eab3f5bb7f1934c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097503"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="d0b1d-103">IT 管理者向け Teams &mdash; にアップグレードするためのツール</span><span class="sxs-lookup"><span data-stu-id="d0b1d-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="d0b1d-104">この記事では、Skype for Business から Teams にアップグレードするためのツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-104">This article describes tools for upgrading to Teams from Skype for Business.</span></span> 

<span data-ttu-id="d0b1d-105">アップグレードを開始する前に、アップグレードの重要な概念と共存動作について説明する次の記事をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-105">Before beginning your upgrade, Microsoft recommends the following articles that describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="d0b1d-106">Teams と Skype for Business の共存</span><span class="sxs-lookup"><span data-stu-id="d0b1d-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="d0b1d-107">共存モード - リファレンス</span><span class="sxs-lookup"><span data-stu-id="d0b1d-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="d0b1d-108">Teams のクライアント エクスペリエンスおよび共存モードへの準拠</span><span class="sxs-lookup"><span data-stu-id="d0b1d-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="d0b1d-109">アップグレードの管理ツール</span><span class="sxs-lookup"><span data-stu-id="d0b1d-109">Tools for managing the upgrade</span></span>

<span data-ttu-id="d0b1d-110">どのアップグレード方法を選択する場合でも、Skype for Business Online を既に持っているユーザーの場合は、ユーザーの共存モードを制御する [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)を使用して TeamsOnly への移行を管理します。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-110">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="d0b1d-111">Skype for Business Server のオンプレミス アカウントを持つユーザーの場合は、ユーザーをクラウド `Move-CsUser` [に移動するためにも使用します](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-111">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="d0b1d-112">各モードの詳細については、「[共存モード](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-112">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d0b1d-113">現在 Skype for Business Online Connector を使用してサービスを管理している場合は、Teams PowerShell モジュールに移動し、既存の PowerShell スクリプトを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-113">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="d0b1d-114">詳細 [については、「Skype for Business Online Connector から Teams PowerShell](teams-powershell-move-from-sfbo.md) モジュールに移動する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-114">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="d0b1d-115">Skype for Business モードを使用して選択機能の移行を実行する場合でも、既定の Islands 構成から TeamsOnly モードにアップグレードする場合でも、TeamsUpgradePolicy は Skype for Business Online を既に使用しているユーザーの主なツールです。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-115">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="d0b1d-116">Teams の他のポリシーと同様に、TeamsUpgradePolicy をユーザーに直接割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-116">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="d0b1d-117">また、テナント全体の既定値としてポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-117">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="d0b1d-118">ユーザーへの割り当ては、テナントの既定の設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-118">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="d0b1d-119">Teams 管理コンソールと PowerShell でポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-119">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="d0b1d-120">また、TeamsOnly モードを除く TeamsUpgradePolicy の任意のモードを、Skype for Business オンプレミスのユーザーに割り当てすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-120">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="d0b1d-121">**TeamsOnly モードは、Skype for Business Online** に既に参加しているユーザーにのみ割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-121">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="d0b1d-122">これは、Skype for Business ユーザーとフェデレーションおよび Microsoft 365 電話システムの機能との相互運用が可能になるのは、ユーザーが Skype for Business Online にログインしている場合に限り可能だからです。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-122">This is because interop with Skype for Business users and federation and Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="d0b1d-123">さらに、Skype for Business オンプレミス展開がある場合 (Office 365 以外の場所をポイントする lyncdiscover DNS レコードの存在によって検出される) 場合は、テナント全体の既定値として **TeamsOnly** モードを割り当てできません。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-123">In addition, **you can't assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="d0b1d-124">オンプレミスに所属する Skype for Business アカウントを持つユーザーは、Skype for Business オンプレミスのツールセットに含まれる Move-CsUser を使用して、Skype for Business Online か直接 Teams のどちらかの[オンラインに移行する必要があります](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-124">Users with Skype for Business accounts homed on-premises [must be moved online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="d0b1d-125">これらのユーザーは、1 つか 2 つのステップで TeamsOnly に移行できます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-125">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="d0b1d-126">1 ステップ: Move-CsUser で  -MoveToTeams スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-126">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="d0b1d-127">これには、CU8 以降の Skype for Business Server 2019 または Skype for Business Server 2015 が必要です。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-127">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="d0b1d-128">2 ステップ: Move-CsUser を実行した後で、TeamsUpgradePolicy を使用して、そのユーザーに TeamsOnly モードを付与します。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-128">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="d0b1d-129">他のポリシーとは異なり、Microsoft 365 または Office 365 で TeamsUpgradePolicy の新しいインスタンスを作成するはできません。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-129">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="d0b1d-130">既存のインスタンスはすべて、このサービスに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-130">All the existing instances are built into the service.</span></span>  <span data-ttu-id="d0b1d-131">(モードは、TeamsUpgradePolicy 内のプロパティであり、ポリシー インスタンスの名前ではありません)。ポリシー インスタンスの名前がモードと同一である場合もありますが、必ず一致するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-131">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="d0b1d-132">特に、ユーザーに TeamsOnly モードを割り当てる場合は、TeamsUpgradePolicy の UpgradeToTeams インスタンスをそのユーザーに付与します。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-132">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="d0b1d-133">すべてのインスタンスの一覧を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-133">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="d0b1d-134">オンライン ユーザーを TeamsOnly モードにアップグレードするには、次のようにして UpgradeToTeams インスタンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-134">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="d0b1d-135">オンプレミスの Skype for Business ユーザーを TeamsOnly モードにアップグレードするには、次のようにしてオンプレミス ツールセットに含まれる Move-CsUser を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-135">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="d0b1d-136">ユーザーごとに明示的に付与されているユーザー (その設定が優先される) を除くテナント内のすべてのユーザーのモードを変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-136">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="d0b1d-137">Skype for Business アカウントを持つユーザーがオンプレミスにある場合、テナント レベルで TeamsOnly モードを割り当てすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-137">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="d0b1d-138">Move-CsUser を使用して、これらのユーザーをクラウドに個別に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-138">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="d0b1d-139">Skype for Business クライアントで通知を使用する</span><span class="sxs-lookup"><span data-stu-id="d0b1d-139">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="d0b1d-140">管理者は、Skype for Business クライアントでエンド ユーザー通知を提供して、ユーザーがまもなく Teams にアップグレードされることを通知できます。次の図にサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-140">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="d0b1d-141">たとえば、管理者は、ユーザーのグループを TeamsOnly モードにアップグレードしようと考えている日の 1 週間前に、そのグループのユーザーに対する通知をオンにできます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-141">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="d0b1d-142">これらの通知は、TeamsUpgradePolicy のインスタンスを使用し、NotifySfbUsers=true に設定して有効にできます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-142">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="d0b1d-143">TeamsOnly 以外のすべてのモードでは、実際には、NotifySfbUsers の 2 つの値に対応する 2 つのインスタンスがモードごとに存在します。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-143">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="d0b1d-144">TeamsOnly 以外のすべてのモードでは、実際には、NotifySfbUsers の 2 つの値に対応する 2 つのインスタンスがモードごとに存在します。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-144">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![通知を示す図](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="d0b1d-146">ユーザーが Skype for Business Online に所属している場合は、そのユーザーと同じモードを持つポリシー インスタンスを割り当てるだけです。ただし、NotifySfbUsers=true に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-146">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="d0b1d-147">ユーザーが Skype for Business Server オンプレミスに所属している場合は、オンプレミスのツールセットを使用する必要があります。Skype for Business Server 2019 か、または Skype for Business Server 2015 用の CU8 が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-147">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="d0b1d-148">オンプレミスの Skype for Business Server にホームされているユーザーの場合、TeamsUpgradePolicy のオンライン インスタンスのモード プロパティは尊重されますが、NotifySfbUsers プロパティは適用されません。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-148">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="d0b1d-149">通知が必要な場合は、クライアントの動作を制御するために、TeamsUpgradePolicy のオンプレミス インスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-149">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="d0b1d-150">オンプレミスの PowerShell ウィンドウで、TeamsUpgradePolicy の新しいインスタンスを作成し、次のようにして NotifySfbUsers=true に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-150">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="d0b1d-151">次に、同じオンプレミスの PowerShell ウィンドウを使用して、その新しいポリシーを目的のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-151">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="d0b1d-152">会議の移行</span><span class="sxs-lookup"><span data-stu-id="d0b1d-152">Meeting migration</span></span>

<span data-ttu-id="d0b1d-153">ユーザーが TeamsOnly に移行されると、既定では、そのユーザーによって開催された既存の Skype for Business 会議は Teams に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-153">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="d0b1d-154">この規定の動作は、ユーザーに TeamsOnly モードを割り当てる際に必要に応じて無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-154">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="d0b1d-155">ユーザーをオンプレミスから移行する場合、そのオンライン ユーザー アカウントで機能するように会議をクラウドに移行する必要がありますが、-MoveToTeams を指定していない場合、その会議は Skype for Business 会議として移行され、Teams には変換されません。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-155">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="d0b1d-156">TeamsOnly モードをテナント レベルで割り当てる場合は、どのユーザーに対しても会議の移行はトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-156">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="d0b1d-157">テナント レベルで TeamsOnly モードを割り当てて会議を移行する場合は、PowerShell を使用してテナント内のユーザーのリストを取得し (必要なフィルターを指定して Get-CsOnlineUser を使用するなど)、その後に、それらのユーザーそれぞれにループ処理を実行して、Start-CsExMeetingMigration を使用して会議の移行をトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-157">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="d0b1d-158">詳細については、「[Meeting Migration Service (MMS) の使用](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0b1d-158">For details, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="d0b1d-159">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d0b1d-159">Related links</span></span>

[<span data-ttu-id="d0b1d-160">共存モード - リファレンス</span><span class="sxs-lookup"><span data-stu-id="d0b1d-160">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="d0b1d-161">Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する</span><span class="sxs-lookup"><span data-stu-id="d0b1d-161">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="d0b1d-162">オンプレミスとクラウドの間でユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="d0b1d-162">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="d0b1d-163">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="d0b1d-163">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="d0b1d-164">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="d0b1d-164">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="d0b1d-165">会議移行サービス (MMS) を使用する</span><span class="sxs-lookup"><span data-stu-id="d0b1d-165">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)