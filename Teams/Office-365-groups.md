---
title: Microsoft 365グループとMicrosoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: グループとグループ メンバーシップMicrosoft 365グループとグループ メンバーシップの組み合Microsoft Teams。
ms.openlocfilehash: d258fa4252f6bbb02d2b9a8211dd5919c2d7a67b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105243"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="37314-103">Microsoft 365グループとMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="37314-103">Microsoft 365 Groups and Microsoft Teams</span></span>

<span data-ttu-id="37314-104">Microsoft 365グループは、アプリケーション間メンバーシップ サービスで、Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="37314-104">Microsoft 365 Groups is the cross-application membership service in Microsoft 365.</span></span> <span data-ttu-id="37314-105">基本的なレベルでは、Microsoft 365 グループは Azure Active Directory 内のオブジェクトであり、メンバーの一覧と、SharePoint チーム サイト、共有 Exchange メールボックス、Planner、Power BI ワークスペースなどの関連ワークロードとの結合を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="37314-105">At a basic level, a Microsoft 365 Group is an object in Azure Active Directory with a list of members and a coupling to related workloads including a SharePoint team site, shared Exchange mailbox, Planner and Power BI workspace.</span></span> <span data-ttu-id="37314-106">Active Directory の他のグループ ベースのセキュリティ オブジェクトと同様に、グループにユーザーを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="37314-106">You can add or remove people to the group just as you would any other group-based security object in Active Directory.</span></span>

![グループとMicrosoft 365サービスを示す図](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

<span data-ttu-id="37314-108">既定では、グループのMicrosoft 365グループを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="37314-108">By default, users in Microsoft 365 can create and manage groups.</span></span> <span data-ttu-id="37314-109">グループグループの詳細Microsoft 365、IT アーキテ[](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)クトポスターの「Microsoft 365 グループ」と「Microsoft 365[について」を参照](teams-architecture-solutions-posters.md#groups-in-microsoft-365)してください。</span><span class="sxs-lookup"><span data-stu-id="37314-109">For more information about Microsoft 365 Groups, see [Learn about Microsoft 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) poster.</span></span>

## <a name="how-microsoft-365-groups-work-with-teams"></a><span data-ttu-id="37314-110">グループMicrosoft 365を使用するTeams</span><span class="sxs-lookup"><span data-stu-id="37314-110">How Microsoft 365 Groups work with Teams</span></span>

<span data-ttu-id="37314-111">チームを作成すると、チーム メンバーシップMicrosoft 365グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="37314-111">When you create a team, a Microsoft 365 group is created to manage team membership.</span></span> <span data-ttu-id="37314-112">グループの関連サービス (SharePoint、Power BIなど) が同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="37314-112">The group's related services, such as a SharePoint site, Power BI workspace, etc. are created at the same time.</span></span>

<span data-ttu-id="37314-113">チームを作成するユーザーは、そのグループの所有者Microsoft 365既存のチーム グループを使用できます。</span><span class="sxs-lookup"><span data-stu-id="37314-113">People who create teams can choose to use an existing Microsoft 365 group if they are an owner of that group.</span></span> <span data-ttu-id="37314-114">チーム内の各チャネルには、ドキュメント ライブラリ内に個別のフォルダーがあります。</span><span class="sxs-lookup"><span data-stu-id="37314-114">Each channel in the team has a separate folder in the document library.</span></span> <span data-ttu-id="37314-115">ドキュメント ライブラリにフォルダーを直接作成しても、チーム内にチャネルは作成されません。</span><span class="sxs-lookup"><span data-stu-id="37314-115">Creating folders directly in the document library does not create channels in the team.</span></span>

<span data-ttu-id="37314-116">グループまたはグループMicrosoft 365グループOutlook作成SharePointグループ メールボックスは、グループメールボックスにOutlook。</span><span class="sxs-lookup"><span data-stu-id="37314-116">When creating a Microsoft 365 group in Outlook or SharePoint, the group mailbox is visible in Outlook.</span></span> <span data-ttu-id="37314-117">既定では、グループ メールボックスTeamsチームを作成するときに非表示になります。</span><span class="sxs-lookup"><span data-stu-id="37314-117">When creating a team in Teams, the group mailbox is hidden by default.</span></span> <span data-ttu-id="37314-118">[Set-UnifiedGroup コマンドレット](/powershell/module/exchange/users-and-groups/set-unifiedgroup)と **HiddenFromExchangeClientsEnabled** パラメーターを使用して、メールボックスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="37314-118">You can use the [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet with the **HiddenFromExchangeClientsEnabled** parameter to make a mailbox visible.</span></span>

## <a name="group-membership"></a><span data-ttu-id="37314-119">グループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="37314-119">Group membership</span></span>

<span data-ttu-id="37314-120">チームのメンバーを削除すると、チームのメンバー Microsoft 365削除されます。</span><span class="sxs-lookup"><span data-stu-id="37314-120">If you remove a member of a team, they are removed from the Microsoft 365 group as well.</span></span> <span data-ttu-id="37314-121">グループから削除すると、チームとチャネルがクライアントからすぐにTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="37314-121">Removal from the group immediately removes the team and channels from the Teams client.</span></span> <span data-ttu-id="37314-122">Microsoft 365 管理センターを使用してグループからユーザーを削除すると、SharePoint Online ドキュメント ライブラリ、Yammer グループ、共有 OneNote などの他の共同作業面にアクセスできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="37314-122">If you remove a person from a group using the Microsoft 365 admin center, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer group, or shared OneNote.</span></span> <span data-ttu-id="37314-123">ただし、チームのチャット機能には約 2 時間アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="37314-123">However, they will still have access to the team's chat functionality for approximately two hours.</span></span>

<span data-ttu-id="37314-124">チーム メンバーを管理するためのベスト プラクティスとして、Teams クライアントにチーム メンバーを追加して削除し、他のグループに接続されたワークロードのアクセス許可の更新が迅速に行われるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="37314-124">As a best practice for managing team members, add and remove them from the Teams client to ensure that permissions updates for other group-connected workloads occur quickly.</span></span> <span data-ttu-id="37314-125">(Microsoft 365 管理センター、Azure AD、または Exchange Online PowerShell を使用して) Teams クライアントの外部でチーム メンバーを追加または削除した場合、変更が Teams に反映されるのに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="37314-125">If you add or remove team members outside of the Teams client (by using the Microsoft 365 admin center, Azure AD, or Exchange Online PowerShell), it can take up to 24 hours for changes to be reflected in Teams.</span></span>

## <a name="deleting-groups-and-teams"></a><span data-ttu-id="37314-126">グループとチームの削除</span><span class="sxs-lookup"><span data-stu-id="37314-126">Deleting groups and teams</span></span>

<span data-ttu-id="37314-127">Microsoft 365 グループを削除すると、永続的な Outlook/OWA の会話と Teams 会議への招待のメールボックス エイリアスが削除され、SharePoint サイトが削除用にマークされます。</span><span class="sxs-lookup"><span data-stu-id="37314-127">Deleting a Microsoft 365 group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion.</span></span> <span data-ttu-id="37314-128">チームの削除からチームへの影響まで約 20 分かかりますOutlook。</span><span class="sxs-lookup"><span data-stu-id="37314-128">It takes approximately 20 minutes between the removal of a team and its effect on Outlook.</span></span> <span data-ttu-id="37314-129">クライアントからチームを削除Teams、チームのメンバー全員に対してすぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="37314-129">Deleting a team from the Teams client will remove it immediately from view to all who are members of the team.</span></span> <span data-ttu-id="37314-130">Teams 機能が有効になっている Microsoft 365 グループのメンバーを削除した場合、影響を受けたユーザーが削除された場合、Teams クライアントでチームがビューから削除されるのに約 2 時間の遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="37314-130">If you remove members of a Microsoft 365 Group that has had Teams functionality enabled on it, there could be a delay of approximately two hours before the team is removed from view in the Teams client for the affected people who were removed.</span></span>

<span data-ttu-id="37314-131">グループとチームのライフサイクル終了オプションの詳細については、「グループ[](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)、チーム、およびグループのライフサイクルの終了オプション」および「Yammer チームをアーカイブまたは削除する」[を](./archive-or-delete-a-team.md)参照Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="37314-131">For details about groups and teams end of lifecycle options, see  [End of lifecycle options for groups, teams, and Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) and [Archive or delete a team in Microsoft Teams](./archive-or-delete-a-team.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="37314-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="37314-132">Related topics</span></span>

[<span data-ttu-id="37314-133">Microsoft Teamsの基礎 (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="37314-133">Foundations of Microsoft Teams (video)</span></span>](https://aka.ms/teams-foundations)

[<span data-ttu-id="37314-134">削除されたグループを復元する</span><span class="sxs-lookup"><span data-stu-id="37314-134">Restore a deleted Group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)