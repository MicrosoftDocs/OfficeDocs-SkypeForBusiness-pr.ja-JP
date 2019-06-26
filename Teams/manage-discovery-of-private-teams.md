---
title: Microsoft Teams でプライベート チームの検索を管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/20/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: チームギャラリーと検索結果の提案を通じて、プライベートチームを Microsoft Teams ユーザーが検出できるかどうかを制御する方法について説明します。
ms.openlocfilehash: c938830f4f59345863d3f84570b387f07f4b08fc
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221233"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="5b0b3-103">Microsoft Teams でプライベート チームの検索を管理する</span><span class="sxs-lookup"><span data-stu-id="5b0b3-103">Manage discovery of private teams in Microsoft Teams</span></span>

> [!INCLUDE [preview feature](includes/preview-feature.md)] 

<span data-ttu-id="5b0b3-104">管理者とチーム所有者は、組織内の Microsoft Teams ユーザーがプライベートチームを検出できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="5b0b3-105">プライベートチームが検出可能になると、検索結果として表示され、チームギャラリーの候補には Teams の公開チームと共に含まれます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="5b0b3-106">これにより、ユーザーは参加するプライベートチームを簡単に検索して見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="5b0b3-107">ユーザーはプライベートチームへの参加を要求することができ、チーム所有者はその要求を承認または拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-107">Users can request to join a private team, and a team owner can then approve or deny the request.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="5b0b3-108">チーム内のパブリックチーム、プライベートチーム、および探索の概要</span><span class="sxs-lookup"><span data-stu-id="5b0b3-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="5b0b3-109">ほとんどの組織には次のような種類のチームがあります。パブリックチーム、見つけやすいプライベートチーム、非検出可能なプライベートチーム。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-109">Most organizations have the following kinds of teams: public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![チームギャラリーのスクリーンショット](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="5b0b3-111">パブリックチーム</span><span class="sxs-lookup"><span data-stu-id="5b0b3-111">Public teams</span></span>

<span data-ttu-id="5b0b3-112">パブリックチームは、組織内のすべてのユーザーが参加できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="5b0b3-113">パブリックチームは teams ギャラリーの全員に表示され、ユーザーはチーム所有者から承認を得ることなくパブリックチームに参加することができます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-113">Public teams are visible to everyone in the teams gallery, and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="5b0b3-114">パブリックチームの例としては、技術ニュース、チームと製品についてのフィードバックを得るためのチーム、およびユーザーが作業を行っているチームのチームなどがあります。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-114">Examples of public teams include a team to discuss technology news, a team to get feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="5b0b3-115">検出可能なプライベートチーム</span><span class="sxs-lookup"><span data-stu-id="5b0b3-115">Discoverable private teams</span></span>

<span data-ttu-id="5b0b3-116">検出可能なプライベートチームを参加できるのは、チーム所有者がそのメンバーにユーザーを追加した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="5b0b3-117">プライベートチームを見つけられるようにすると、チームギャラリーのおすすめチームと検索結果のリストにチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="5b0b3-118">組織内のすべてのユーザーが知っている、またはチーム内のファイルへのアクセスを管理する必要があるという、組織内のプロジェクトとグループに、検出可能なプライベートチームを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="5b0b3-119">例としては、人事部門のチーム、組織内のすべての管理者のチーム、マネージャーと直属の部下のチームなどがあります。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-119">Examples include a team for your HR department, a team for all managers in your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="5b0b3-120">非検出可能なプライベートチーム</span><span class="sxs-lookup"><span data-stu-id="5b0b3-120">Non-discoverable private teams</span></span>

<span data-ttu-id="5b0b3-121">非検出可能なプライベートチームは、チーム所有者がそのメンバーにユーザーを追加した場合にのみ参加することができます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="5b0b3-122">プライベートチームを見つけることができない場合は、おすすめチームの一覧に表示されず、teams ギャラリーの検索結果から削除されます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="5b0b3-123">検出不能なチームを使用して、機密性の高い機密のトピックで共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="5b0b3-124">例としては、組織の戦略的方向性の変化について話し合うために、今後の買収とチームに相談するチームが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="5b0b3-125">新しいプライベートチームが検出可能であるかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="5b0b3-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="5b0b3-126">チーム所有者は、チームの検出設定を構成することにより、チーム所有者がプライベートチームを作成して検出できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="5b0b3-127">既定では、新しいプライベートチームは検索可能であり、見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="5b0b3-128">チーム所有者が検索結果と候補にプライベートチームを表示しないようにする場合、所有者は、**このチーム**の隣にある [**設定の変更**] を選択して設定をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-128">If the team owner doesn't want the private team to show up in search results and suggestions, the owner can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![新しいプライベートチームの検出設定のスクリーンショット](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="5b0b3-130">既存のプライベートチームが検出可能であるかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="5b0b3-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="5b0b3-131">チーム所有者は、既存のプライベートチームの検出設定をチーム設定で直接設定できます。また、管理者は PowerShell を使用してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="5b0b3-132">チームの設定</span><span class="sxs-lookup"><span data-stu-id="5b0b3-132">In team settings</span></span>

<span data-ttu-id="5b0b3-133">Teams で、プライベートチームに移動し、[**その他のオプション** > ] をクリックして**チームを管理**します。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-133">In Teams, go to the private team, click **More options** > **Manage team**.</span></span> <span data-ttu-id="5b0b3-134">[**設定**] タブで、[**チーム探索**] を展開し、[検出**を有効にする**] チェックボックスをオフまたはオンにします。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![既存のプライベートチームの検出設定のスクリーンショット](media/private-team-discovery-existing-team.png)

### <a name="using-powershell-coming-soon"></a><span data-ttu-id="5b0b3-136">PowerShell を使用する (近日公開)</span><span class="sxs-lookup"><span data-stu-id="5b0b3-136">Using PowerShell (coming soon)</span></span>

<span data-ttu-id="5b0b3-137">**[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** コマンドレットを使用して、既存のプライベートチームの検出設定をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-137">Use the **[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="5b0b3-138">チームを検出できるようにする方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-138">Here's an example of how to make a team discoverable:</span></span>
```
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
```
<span data-ttu-id="5b0b3-139">スクリプトでこのコマンドレットを使用して、既存のプライベートチームの検出設定を一括で設定することができます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="5b0b3-140">ユーザーがプライベートチームを検出できるようにするかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="5b0b3-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="5b0b3-141">管理者として、組織内のどのユーザーが検索結果やチームの候補でプライベートチームを見つけられるかを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="5b0b3-142">**[新しい-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** コマンドレットを使用してポリシーを作成し、ユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-142">Create a policy by using the **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="5b0b3-143">ポリシーを割り当てられたユーザーが検索結果と提案で検出可能なプライベートチームを表示できるようにするには、 **Allowprivateteamdiscovery**パラメーターを**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="5b0b3-144">**Allowprivateteamdiscovery**パラメーターを**false**に設定すると、検索結果およびポリシーが割り当てられたユーザーの候補から、検出可能なプライベートチームがすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="5b0b3-145">既定では、組織内のすべてのユーザーに対して**Allowprivateteamdiscovery**が**true**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="5b0b3-146">この例では、VendorPolicy という名前のポリシーを作成して、ユーザーが検出可能なプライベートチームを検出できないようにします。次に、vendoruser1 という名前のユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span> 
```
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> <span data-ttu-id="5b0b3-147">検出されないプライベートチームは、ポリシーの設定に関係なく、検索結果と候補には表示されません。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="5b0b3-148">たとえば、プライベートチームの検出設定を無効にした場合、そのユーザーのポリシー設定で**Allowprivateteamdiscovery**パラメーターが**true**に設定されているにもかかわらず、ユーザーはチームを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="5b0b3-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5b0b3-149">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5b0b3-149">Related topics</span></span>
- [<span data-ttu-id="5b0b3-150">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="5b0b3-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)