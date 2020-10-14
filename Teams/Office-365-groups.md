---
title: Microsoft 365 グループおよび Microsoft Teams
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
description: Microsoft 365 グループとグループメンバーシップが Microsoft Teams とどのように連携するかについて説明します。
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456081"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="105fe-103">Microsoft 365 グループおよび Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="105fe-103">Microsoft 365 Groups and Microsoft Teams</span></span>

<span data-ttu-id="105fe-104">Microsoft 365 グループは、Microsoft 365 のクロスアプリケーションメンバーシップサービスです。</span><span class="sxs-lookup"><span data-stu-id="105fe-104">Microsoft 365 Groups is the cross-application membership service in Microsoft 365.</span></span> <span data-ttu-id="105fe-105">基本的なレベルでは、Microsoft 365 グループは Azure Active Directory 内のオブジェクトであり、メンバーの一覧と、SharePoint チームサイト、共有 Exchange メールボックス、Planner、Power BI workspace などの関連ワークロードへの結合です。</span><span class="sxs-lookup"><span data-stu-id="105fe-105">At a basic level, a Microsoft 365 Group is an object in Azure Active Directory with a list of members and a coupling to related workloads including a SharePoint team site, shared Exchange mailbox, Planner and Power BI workspace.</span></span> <span data-ttu-id="105fe-106">Active Directory の他のグループベースのセキュリティオブジェクトと同様に、グループにユーザーを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="105fe-106">You can add or remove people to the group just as you would any other group-based security object in Active Directory.</span></span>

![Microsoft 365 グループと関連サービスを示す図](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

<span data-ttu-id="105fe-108">既定では、Microsoft 365 のユーザーはグループの作成と管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="105fe-108">By default, users in Microsoft 365 can create and manage groups.</span></span> <span data-ttu-id="105fe-109">Microsoft 365 グループの詳細については、「 [microsoft 365 グループ](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) および microsoft [365 の IT アーキテクト向けグループ](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="105fe-109">For more information about Microsoft 365 Groups, see [Learn about Microsoft 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) poster.</span></span>

## <a name="how-microsoft-365-groups-work-with-teams"></a><span data-ttu-id="105fe-110">Microsoft 365 グループが Teams と連携する方法</span><span class="sxs-lookup"><span data-stu-id="105fe-110">How Microsoft 365 Groups work with Teams</span></span>

<span data-ttu-id="105fe-111">チームを作成するときに、チームのメンバーシップを管理するために Microsoft 365 グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="105fe-111">When you create a team, a Microsoft 365 group is created to manage team membership.</span></span> <span data-ttu-id="105fe-112">SharePoint サイト、Power BI workspace などのグループ関連サービスは、同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="105fe-112">The group's related services, such as a SharePoint site, Power BI workspace, etc. are created at the same time.</span></span>

<span data-ttu-id="105fe-113">チームを作成するユーザーは、そのグループの所有者である場合は、既存の Microsoft 365 グループを使用することを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="105fe-113">People who create teams can choose to use an existing Microsoft 365 group if they are an owner of that group.</span></span> <span data-ttu-id="105fe-114">チーム内の各チャネルには、ドキュメントライブラリ内の個別のフォルダーがあります。</span><span class="sxs-lookup"><span data-stu-id="105fe-114">Each channel in the team has a separate folder in the document library.</span></span> <span data-ttu-id="105fe-115">ドキュメントライブラリで直接フォルダーを作成しても、チーム内にチャネルは作成されません。</span><span class="sxs-lookup"><span data-stu-id="105fe-115">Creating folders directly in the document library does not create channels in the team.</span></span>

<span data-ttu-id="105fe-116">Outlook または SharePoint で Microsoft 365 グループを作成すると、Outlook にグループメールボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="105fe-116">When creating a Microsoft 365 group in Outlook or SharePoint, the group mailbox is visible in Outlook.</span></span> <span data-ttu-id="105fe-117">Teams でチームを作成する場合、グループのメールボックスは既定で非表示になっています。</span><span class="sxs-lookup"><span data-stu-id="105fe-117">When creating a team in Teams, the group mailbox is hidden by default.</span></span> <span data-ttu-id="105fe-118">**HiddenFromExchangeClientsEnabled**パラメーターを指定して[get-unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup)コマンドレットを使用して、メールボックスを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="105fe-118">You can use the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet with the **HiddenFromExchangeClientsEnabled** parameter to make a mailbox visible.</span></span>

## <a name="group-membership"></a><span data-ttu-id="105fe-119">グループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="105fe-119">Group membership</span></span>

<span data-ttu-id="105fe-120">チームのメンバーを削除すると、Microsoft 365 グループからも削除されます。</span><span class="sxs-lookup"><span data-stu-id="105fe-120">If you remove a member of a team, they are removed from the Microsoft 365 group as well.</span></span> <span data-ttu-id="105fe-121">グループから削除すると、チームクライアントからチームとチャネルが直ちに削除されます。</span><span class="sxs-lookup"><span data-stu-id="105fe-121">Removal from the group immediately removes the team and channels from the Teams client.</span></span> <span data-ttu-id="105fe-122">Microsoft 365 管理センターを使用してグループからユーザーを削除すると、SharePoint Online ドキュメントライブラリ、Yammer グループ、共有 OneNote などの他の共同作業の側面にはアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="105fe-122">If you remove a person from a group using the Microsoft 365 admin center, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer group, or shared OneNote.</span></span> <span data-ttu-id="105fe-123">ただし、チームのチャット機能へのアクセス権は、約2時間で引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="105fe-123">However, they will still have access to the team's chat functionality for approximately two hours.</span></span>

<span data-ttu-id="105fe-124">チームメンバーを管理するためのベストプラクティスとして、チームクライアントに対してそれらを追加および削除して、他のグループに接続されたワークロードのアクセス許可の更新がすばやく行われるようにします。</span><span class="sxs-lookup"><span data-stu-id="105fe-124">As a best practice for managing team members, add and remove them from the Teams client to ensure that permissions updates for other group-connected workloads occur quickly.</span></span> <span data-ttu-id="105fe-125">Teams クライアントの外部でチームメンバーを追加または削除する場合 (Microsoft 365 管理センター、Azure AD、または Exchange Online PowerShell を使用して)、変更が Teams に反映されるまでに最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="105fe-125">If you add or remove team members outside of the Teams client (by using the Microsoft 365 admin center, Azure AD, or Exchange Online PowerShell), it can take up to 24 hours for changes to be reflected in Teams.</span></span>

## <a name="deleting-groups-and-teams"></a><span data-ttu-id="105fe-126">グループとチームを削除する</span><span class="sxs-lookup"><span data-stu-id="105fe-126">Deleting groups and teams</span></span>

<span data-ttu-id="105fe-127">Microsoft 365 グループを削除すると、永続的な Outlook/OWA の会話と Teams の会議出席依頼のメールボックスのエイリアスが削除され、SharePoint サイトの削除のマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="105fe-127">Deleting a Microsoft 365 group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion.</span></span> <span data-ttu-id="105fe-128">チームの削除と Outlook への影響の間は、約20分かかります。</span><span class="sxs-lookup"><span data-stu-id="105fe-128">It takes approximately 20 minutes between the removal of a team and its effect on Outlook.</span></span> <span data-ttu-id="105fe-129">チームクライアントからチームを削除すると、チームのメンバーになっているすべてのユーザーに直ちにチームが削除されます。</span><span class="sxs-lookup"><span data-stu-id="105fe-129">Deleting a team from the Teams client will remove it immediately from view to all who are members of the team.</span></span> <span data-ttu-id="105fe-130">チーム機能が有効になっている Microsoft 365 グループのメンバーを削除した場合は、削除された対象ユーザーのチームクライアントでチームがビューから削除されるまでに約2時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="105fe-130">If you remove members of a Microsoft 365 Group that has had Teams functionality enabled on it, there could be a delay of approximately two hours before the team is removed from view in the Teams client for the affected people who were removed.</span></span>

<span data-ttu-id="105fe-131">グループとチームのライフサイクルの終了オプションの詳細については、「  [グループ、チーム、Yammer のライフサイクルの終了オプション](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) 」と「 [Microsoft teams でチームをアーカイブまたは削除](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="105fe-131">For details about groups and teams end of lifecycle options, see  [End of lifecycle options for groups, teams, and Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) and [Archive or delete a team in Microsoft Teams](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team).</span></span>

## <a name="related-topics"></a><span data-ttu-id="105fe-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="105fe-132">Related topics</span></span>

[<span data-ttu-id="105fe-133">Microsoft Teams の基礎 (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="105fe-133">Foundations of Microsoft Teams (video)</span></span>](https://aka.ms/teams-foundations)

[<span data-ttu-id="105fe-134">削除したグループを復元する</span><span class="sxs-lookup"><span data-stu-id="105fe-134">Restore a deleted Group</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)