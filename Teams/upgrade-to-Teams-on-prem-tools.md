---
title: Skype for Business オンプレミス展開から Teams へのアップグレード - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams へのアップグレード
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf51019aad5b2deb6239c698623475263241b3f
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940674"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="a399f-103">IT 管理者の Teams にアップグレードするためのツール &mdash;</span><span class="sxs-lookup"><span data-stu-id="a399f-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="a399f-104">この記事では、Teams にアップグレードするためのツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a399f-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="a399f-105">この記事では、IT 管理者向けのアップグレードの概念と実装について説明します。</span><span class="sxs-lookup"><span data-stu-id="a399f-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="a399f-106">概要</span><span class="sxs-lookup"><span data-stu-id="a399f-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="a399f-107">アップグレード方法</span><span class="sxs-lookup"><span data-stu-id="a399f-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="a399f-108">**アップグレードを管理するためのツール**   (この記事)</span><span class="sxs-lookup"><span data-stu-id="a399f-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="a399f-109">Skype for Business オンプレミスの組織に関するその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="a399f-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="a399f-110">アップグレードを実装する</span><span class="sxs-lookup"><span data-stu-id="a399f-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="a399f-111">公衆交換電話網 (PSTN) に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="a399f-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="a399f-112">さらに、次の記事では、アップグレードの重要な概念と共存の動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="a399f-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="a399f-113">Teams と Skype for Business の共存</span><span class="sxs-lookup"><span data-stu-id="a399f-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="a399f-114">共存モード-参照</span><span class="sxs-lookup"><span data-stu-id="a399f-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="a399f-115">Teams のクライアント エクスペリエンスおよび共存モードへの準拠</span><span class="sxs-lookup"><span data-stu-id="a399f-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="a399f-116">アップグレードの管理ツール</span><span class="sxs-lookup"><span data-stu-id="a399f-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="a399f-117">どちらのアップグレード方法を選んだ場合でも、 [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)を使って、ユーザーの共存モードを制御する、チームへの切り替えを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a399f-117">Whichever upgrade method you choose, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="a399f-118">各モードの詳細については、「[共存モード](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a399f-118">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="a399f-119">[Skype for Business] モードを使って select 機能切り替えを実行するか、または既定の孤島構成から teams Sonly モードにアップグレードするか、TeamsUpgradePolicy はプライマリツールになります。</span><span class="sxs-lookup"><span data-stu-id="a399f-119">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool.</span></span> <span data-ttu-id="a399f-120">Teams の他のポリシーと同じように、TeamsUpgradePolicy をユーザーに直接割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a399f-120">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="a399f-121">また、ポリシーをテナント全体の既定値として設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a399f-121">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="a399f-122">ユーザーへの割り当ては、テナントの既定の設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a399f-122">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="a399f-123">ポリシーは、Teams の管理コンソールと PowerShell で管理できます。</span><span class="sxs-lookup"><span data-stu-id="a399f-123">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="a399f-124">ユーザーが Skype for Business Online またはオンプレミスのどちらを使用している場合でも、TeamsUpgradePolicy の任意のモードをユーザーに割り当てることができます。 **ただし、TeamsOnly モードは、既に skype For Business online に所属しているユーザーにのみ割り当てる**ことができます。</span><span class="sxs-lookup"><span data-stu-id="a399f-124">You can assign any mode of TeamsUpgradePolicy to users whether the user is homed in Skype for Business Online or on-premises, **except that TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="a399f-125">これは、Skype for Business ユーザーとフェデレーションと Microsoft 365 電話システム機能の相互運用機能は、ユーザーが Skype for Business Online を使用している場合にのみ可能であるためです。</span><span class="sxs-lookup"><span data-stu-id="a399f-125">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span>

<span data-ttu-id="a399f-126">オンプレミスに所属する Skype for Business アカウントを持つユーザーは、Skype for Business オンプレミスのツールセットに含まれる Move-CsUser を使用して、Skype for Business Online か直接 Teams のどちらかの[オンラインに移行する必要があります](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="a399f-126">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="a399f-127">これらのユーザーは、1 つか 2 つのステップで TeamsOnly に移行できます。</span><span class="sxs-lookup"><span data-stu-id="a399f-127">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="a399f-128">1 ステップ: Move-CsUser で  -MoveToTeams スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="a399f-128">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="a399f-129">これには、CU8 以降の Skype for Business Server 2019 または Skype for Business Server 2015 が必要です。</span><span class="sxs-lookup"><span data-stu-id="a399f-129">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="a399f-130">2 ステップ: Move-CsUser を実行した後で、TeamsUpgradePolicy を使用して、そのユーザーに TeamsOnly モードを付与します。</span><span class="sxs-lookup"><span data-stu-id="a399f-130">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="a399f-131">他のポリシーとは異なり、Microsoft 365 または Office 365 では、TeamsUpgradePolicy の新しいインスタンスを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="a399f-131">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="a399f-132">既存のインスタンスはすべて、このサービスに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="a399f-132">All the existing instances are built into the service.</span></span>  <span data-ttu-id="a399f-133">(モードは、TeamsUpgradePolicy 内のプロパティであり、ポリシー インスタンスの名前ではありません)。ポリシー インスタンスの名前がモードと同一である場合もありますが、必ず一致するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a399f-133">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="a399f-134">特に、ユーザーに TeamsOnly モードを割り当てる場合は、TeamsUpgradePolicy の UpgradeToTeams インスタンスをそのユーザーに付与します。</span><span class="sxs-lookup"><span data-stu-id="a399f-134">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="a399f-135">すべてのインスタンスの一覧を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a399f-135">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="a399f-136">オンライン ユーザーを TeamsOnly モードにアップグレードするには、次のようにして UpgradeToTeams インスタンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a399f-136">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="a399f-137">オンプレミスの Skype for Business ユーザーを TeamsOnly モードにアップグレードするには、次のようにしてオンプレミス ツールセットに含まれる Move-CsUser を使用します。</span><span class="sxs-lookup"><span data-stu-id="a399f-137">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="a399f-138">ユーザーごとに明示的に付与されているユーザー (その設定が優先される) を除くテナント内のすべてのユーザーのモードを変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a399f-138">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="a399f-139">Skype for Business アカウントを使用しているユーザーがいる場合は、オンプレミスの Skype for Business アカウントを持つすべてのユーザーに、他のモードを明示的に割り当てない限り、チームのテナントレベルで teams Sonly モードを割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="a399f-139">If you have any users with Skype for Business accounts on-premises, you must not assign TeamsOnly mode at the tenant level, unless you explicitly assign some other mode to all users with on-premises Skype for Business accounts.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="a399f-140">Skype for Business クライアントで通知を使用する</span><span class="sxs-lookup"><span data-stu-id="a399f-140">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="a399f-141">管理者は、Skype for Business クライアントでエンド ユーザー通知を提供して、ユーザーがまもなく Teams にアップグレードされることを通知できます。次の図にサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="a399f-141">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="a399f-142">たとえば、管理者は、ユーザーのグループを TeamsOnly モードにアップグレードしようと考えている日の 1 週間前に、そのグループのユーザーに対する通知をオンにできます。</span><span class="sxs-lookup"><span data-stu-id="a399f-142">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="a399f-143">これらの通知は、TeamsUpgradePolicy のインスタンスを使用し、NotifySfbUsers=true に設定して有効にできます。</span><span class="sxs-lookup"><span data-stu-id="a399f-143">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="a399f-144">TeamsOnly 以外のすべてのモードでは、実際には、NotifySfbUsers の 2 つの値に対応する 2 つのインスタンスがモードごとに存在します。</span><span class="sxs-lookup"><span data-stu-id="a399f-144">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="a399f-145">TeamsOnly 以外のすべてのモードでは、実際には、NotifySfbUsers の 2 つの値に対応する 2 つのインスタンスがモードごとに存在します。</span><span class="sxs-lookup"><span data-stu-id="a399f-145">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![通知を示す図](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="a399f-147">ユーザーが Skype for Business Online に所属している場合は、そのユーザーと同じモードを持つポリシー インスタンスを割り当てるだけです。ただし、NotifySfbUsers=true に設定します。</span><span class="sxs-lookup"><span data-stu-id="a399f-147">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="a399f-148">ユーザーが Skype for Business Server オンプレミスに所属している場合は、オンプレミスのツールセットを使用する必要があります。Skype for Business Server 2019 か、または Skype for Business Server 2015 用の CU8 が必要になります。</span><span class="sxs-lookup"><span data-stu-id="a399f-148">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="a399f-149">オンプレミスの Skype for Business Server を使用しているユーザーの場合、TeamsUpgradePolicy のオンラインインスタンスの mode プロパティは有効ですが、NotifySfbUsers プロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="a399f-149">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="a399f-150">通知が必要な場合は、クライアントの動作を制御するために、オンプレミスの TeamsUpgradePolicy のインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a399f-150">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="a399f-151">オンプレミスの PowerShell ウィンドウで、TeamsUpgradePolicy の新しいインスタンスを作成し、次のようにして NotifySfbUsers=true に設定します。</span><span class="sxs-lookup"><span data-stu-id="a399f-151">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="a399f-152">次に、同じオンプレミスの PowerShell ウィンドウを使用して、その新しいポリシーを目的のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a399f-152">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="a399f-153">会議の移行</span><span class="sxs-lookup"><span data-stu-id="a399f-153">Meeting migration</span></span>

<span data-ttu-id="a399f-154">ユーザーが TeamsOnly に移行されると、既定では、そのユーザーによって開催された既存の Skype for Business 会議は Teams に変換されます。</span><span class="sxs-lookup"><span data-stu-id="a399f-154">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="a399f-155">この規定の動作は、ユーザーに TeamsOnly モードを割り当てる際に必要に応じて無効にできます。</span><span class="sxs-lookup"><span data-stu-id="a399f-155">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="a399f-156">ユーザーをオンプレミスから移行する場合、そのオンライン ユーザー アカウントで機能するように会議をクラウドに移行する必要がありますが、-MoveToTeams を指定していない場合、その会議は Skype for Business 会議として移行され、Teams には変換されません。</span><span class="sxs-lookup"><span data-stu-id="a399f-156">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="a399f-157">TeamsOnly モードをテナント レベルで割り当てる場合は、どのユーザーに対しても会議の移行はトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="a399f-157">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="a399f-158">テナント レベルで TeamsOnly モードを割り当てて会議を移行する場合は、PowerShell を使用してテナント内のユーザーのリストを取得し (必要なフィルターを指定して Get-CsOnlineUser を使用するなど)、その後に、それらのユーザーそれぞれにループ処理を実行して、Start-CsExMeetingMigration を使用して会議の移行をトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="a399f-158">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="a399f-159">詳細については、「[Meeting Migration Service (MMS) の使用](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a399f-159">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="a399f-160">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a399f-160">Related links</span></span>

[<span data-ttu-id="a399f-161">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="a399f-161">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="a399f-162">Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する</span><span class="sxs-lookup"><span data-stu-id="a399f-162">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="a399f-163">オンプレミスとクラウドの間でユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="a399f-163">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="a399f-164">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="a399f-164">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="a399f-165">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="a399f-165">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="a399f-166">会議移行サービス (MMS) を使用する</span><span class="sxs-lookup"><span data-stu-id="a399f-166">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

