---
title: マイクロソフトのチームでの秘密のチームの検索を管理します。
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: プライベート チームをチームのギャラリーおよび検索結果内の提案をマイクロソフトのチームのユーザーが検出できるかどうかを制御する方法について説明します。
ms.openlocfilehash: 3609a592c3c940e9f7cbec6ca5c58fd072322c46
ms.sourcegitcommit: 0bb55cad74b15fc821ae916799aa8c0cb13dd31d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2019
ms.locfileid: "33497954"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="ff499-103">マイクロソフトのチームでの秘密のチームの検索を管理します。</span><span class="sxs-lookup"><span data-stu-id="ff499-103">Manage discovery of private teams in Microsoft Teams</span></span>

> [!INCLUDE [preview feature](includes/preview-feature.md)] 

<span data-ttu-id="ff499-104">管理者とチームの所有者は、マイクロソフトのチームのユーザーが組織内でプライベート チームを検出できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="ff499-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="ff499-105">プライベート チームが検出すると、検索結果に表示し、チーム内のパブリックのチームと共にチームのギャラリーで提案に含まれています。</span><span class="sxs-lookup"><span data-stu-id="ff499-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="ff499-106">これによりのプライベート チームに参加するを検索するを容易にします。</span><span class="sxs-lookup"><span data-stu-id="ff499-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="ff499-107">チームの所有者を承認または拒否できますし、プライベート チームに参加するユーザーを要求できます。</span><span class="sxs-lookup"><span data-stu-id="ff499-107">Users can request to join a private team which a team owner can then approve or deny.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="ff499-108">チームのパブリック、プライベート チームは、チーム内の探索の概要</span><span class="sxs-lookup"><span data-stu-id="ff499-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="ff499-109">組織には、次のようなチームのチームの公開、検出可能なプライベート チーム、および検出可能ではないプライベート チームがあります。</span><span class="sxs-lookup"><span data-stu-id="ff499-109">Most organizations have the following kinds of teams - public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![チーム ギャラリー](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="ff499-111">パブリック チーム</span><span class="sxs-lookup"><span data-stu-id="ff499-111">Public teams</span></span>

<span data-ttu-id="ff499-112">パブリックのチームは、参加するのには、組織内のすべてのユーザーに使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff499-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="ff499-113">パブリックのチームは、チームのギャラリー内のすべてのユーザーに表示し、チームの所有者の承認を得ることがなくユーザーがパブリックのチームに参加できます。</span><span class="sxs-lookup"><span data-stu-id="ff499-113">Public teams are visible to everyone in the teams gallery and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="ff499-114">パブリック チームの例には、テクノロジー、製品、ドッグフードのフィードバックを取得するためのチームとチームの作業をユーザー設定することでニュースを説明するためのチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff499-114">Examples of public teams include a team to discuss news in technology, a team to get dogfood feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="ff499-115">検出可能なプライベート ・ チーム</span><span class="sxs-lookup"><span data-stu-id="ff499-115">Discoverable private teams</span></span>

<span data-ttu-id="ff499-116">検出可能なプライベート チームは、チーム所有者がそれらにユーザーを追加するときのみ結合できます。</span><span class="sxs-lookup"><span data-stu-id="ff499-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="ff499-117">プライベート チームを検出可能にすると、候補のチームとチームのギャラリーでの検索結果の一覧で、チームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff499-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="ff499-118">プロジェクトとチーム内のファイルを制御する必要があります、すべてのユーザーを認識しており、会話へのアクセスを組織内のグループの検出可能なプライベート チームを使用します。</span><span class="sxs-lookup"><span data-stu-id="ff499-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="ff499-119">など、人事部のチーム、組織のマネージャーにすべてのチームとチームのマネージャーと、直属の部下。</span><span class="sxs-lookup"><span data-stu-id="ff499-119">Examples include a team for your HR department, a team for all managers at your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="ff499-120">非検出が可能なプライベート ・ チーム</span><span class="sxs-lookup"><span data-stu-id="ff499-120">Non-discoverable private teams</span></span>

<span data-ttu-id="ff499-121">非検出のプライベート チームを結合するにはチームの所有者にするユーザーを追加するときです。</span><span class="sxs-lookup"><span data-stu-id="ff499-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="ff499-122">プライベート チームをしない検出可能にすると、提案されたチームのリストから非表示になってので、チームのギャラリーでの検索結果から削除ください。</span><span class="sxs-lookup"><span data-stu-id="ff499-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="ff499-123">機密および機密度の高いトピックを共有するには、検出可能ではないチームを使用します。</span><span class="sxs-lookup"><span data-stu-id="ff499-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="ff499-124">例としては、今後取得を説明するためのチームや組織の戦略的方向性の変更を説明するためのチームです。</span><span class="sxs-lookup"><span data-stu-id="ff499-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="ff499-125">新しいプライベート チームが検出可能であるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="ff499-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="ff499-126">チームの所有者は、プライベート チームを作成するときは、チームの検出設定を構成することで見つけやすいように選択できます。</span><span class="sxs-lookup"><span data-stu-id="ff499-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="ff499-127">既定では、新しいプライベート チームは、検索で見つけやすいです。</span><span class="sxs-lookup"><span data-stu-id="ff499-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="ff499-128">チームの所有者に、検索結果と推奨事項表示するのにはプライベート チームが希望しない場合は場合、は、**このチームは検索で見つけやすい**の横にある **[設定の変更**を選択して設定を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="ff499-128">If the team owner doesn't want the private team to show up in search results and suggestions, they can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![新しいプライベート チームの探索の設定](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="ff499-130">既存のプライベート チームが検出可能であるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="ff499-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="ff499-131">PowerShell を使用して行うことができます管理者とチームの所有者は、チームの設定で直接既存のプライベート チームの探索の設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="ff499-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="ff499-132">チームの設定で</span><span class="sxs-lookup"><span data-stu-id="ff499-132">In team settings</span></span>

<span data-ttu-id="ff499-133">プライベート チームにはチームで、**複数のオプションの ˙˙˙**をクリックして > **チームを管理**します。</span><span class="sxs-lookup"><span data-stu-id="ff499-133">In Teams, go to the private team, click **More options ˙˙˙** > **Manage team**.</span></span> <span data-ttu-id="ff499-134">[**設定**] タブで、展開**チームの探索**とし、オンまたはオフ**の検出を有効にする**] チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="ff499-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![既存のプライベート チームの探索の設定](media/private-team-discovery-existing-team.png)

### <a name="using-powershell-coming-soon"></a><span data-ttu-id="ff499-136">(準備中) PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="ff499-136">Using PowerShell (coming soon)</span></span>

<span data-ttu-id="ff499-137">**セット チーム**コマンドレットを使用して、オフにするか、既存のプライベート チームの探索の設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="ff499-137">Use the **Set-Team** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="ff499-138">チームを検出可能にする方法の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="ff499-138">Here's an example of how to make a team discoverable:</span></span>

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
<span data-ttu-id="ff499-139">大量の既存のプライベート チームの検出設定を設定するのには、スクリプト内でこのコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff499-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="ff499-140">プライベート チームを見つけることができるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="ff499-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="ff499-141">管理者として、組織内のどのユーザーが検索結果にプライベート チームとチームの候補を検出できるを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="ff499-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="ff499-142">**新規 CsTeamsChannelsPolicy**コマンドレットを使用してポリシーを作成し、ユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ff499-142">Create a policy by using the **New-CsTeamsChannelsPolicy** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="ff499-143">に**true を指定**して、検索結果と推奨事項のプライベート チームで検出可能なポリシーが割り当てられているユーザーを許可するには、 **AllowPrivateTeamDiscovery**パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="ff499-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="ff499-144">検索結果と、ポリシーが割り当てられているユーザーの意見から検出可能なすべてのプライベート チームを削除する**AllowPrivateTeamDiscovery**パラメーターを**false**に設定します。</span><span class="sxs-lookup"><span data-stu-id="ff499-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="ff499-145">既定では、 **AllowPrivateTeamDiscovery**は**true**組織内のすべてのユーザーに設定します。</span><span class="sxs-lookup"><span data-stu-id="ff499-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="ff499-146">この例では、発見可能な状態で行われるすべてのプライベート チームを検出できないようにする VendorPolicy をという名前のポリシーを作成し、vendoruser1 をという名前のユーザーにポリシーを割り当てることです。</span><span class="sxs-lookup"><span data-stu-id="ff499-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span> 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> <span data-ttu-id="ff499-147">検索結果やご提案、ポリシーの設定で、検出可能ではないプライベート チームを表示しません。</span><span class="sxs-lookup"><span data-stu-id="ff499-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="ff499-148">たとえば、プライベート チームの探索の設定をオフにする場合ユーザーは、チームを発見することに**は true**これらのユーザー ポリシーの設定で、 **AllowPrivateTeamDiscovery**パラメーターが設定されていても。</span><span class="sxs-lookup"><span data-stu-id="ff499-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ff499-149">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ff499-149">Related topics</span></span>
- [<span data-ttu-id="ff499-150">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="ff499-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)