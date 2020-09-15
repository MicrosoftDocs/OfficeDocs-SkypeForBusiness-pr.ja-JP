---
title: Microsoft Teams 管理センターでチームを管理する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: 組織で共同作業のために設定されているチームを Microsoft Teams 管理センターで表示または更新する方法について説明します。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c736cf17d263f097e97b32f856bc83cf2fe42a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814556"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="634df-103">Microsoft Teams 管理センターでチームを管理する</span><span class="sxs-lookup"><span data-stu-id="634df-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="634df-104">概要</span><span class="sxs-lookup"><span data-stu-id="634df-104">Overview</span></span>

<span data-ttu-id="634df-105">この記事では、Microsoft Teams の管理センターでの Teams 管理ツールの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="634df-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="634df-106">管理者である場合、自分の組織で共同作業のためにセットアップしたチームを表示したり更新したりする必要性が生じます。また、所有者のいないチームに所有者を割り当てるなどの修復アクションを実行しなければならない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="634df-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="634df-107">組織のチームは、Microsoft Teams PowerShell モジュールと Microsoft Teams 管理センターの両方から管理することができます。</span><span class="sxs-lookup"><span data-stu-id="634df-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="634df-108">管理センターには、にアクセスでき <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ます。</span><span class="sxs-lookup"><span data-stu-id="634df-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="634df-109">これらの 2 つのツールセットを使用した完全な管理機能については、次の役割の 1 つが割り当てられることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="634df-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="634df-110">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="634df-110">Global Administrator</span></span>
- <span data-ttu-id="634df-111">Teams サービス管理者</span><span class="sxs-lookup"><span data-stu-id="634df-111">Teams Service Administrator</span></span>

<span data-ttu-id="634df-112">Teams での管理者の役割の詳細については、「[ Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」をご覧ください。また、PowerShell コマンドレットを使用してチームを管理する方法の詳細については、「[Microsoft Teams コマンドレットのリファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="634df-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="634df-113">Teams の概要グリッド</span><span class="sxs-lookup"><span data-stu-id="634df-113">Teams overview grid</span></span>

<span data-ttu-id="634df-114">チームの管理ツールは、Microsoft Teams 管理センターの [**Teams**] ノードの下にあります。</span><span class="sxs-lookup"><span data-stu-id="634df-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="634df-115">(管理センターで、[ **Teams**  >  ] を選択します)**チームを管理**します。)各チームは Microsoft 365 グループによってサポートされており、このノードには、組織で Microsoft Teams が有効になっているグループのビューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="634df-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Teams の概要グリッドのスクリーンショット](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="634df-117">このグリッドには、次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="634df-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="634df-118">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="634df-118">**Team name**</span></span>
- <span data-ttu-id="634df-119">**チャネル** - 既定の全般チャネルを含む、チーム内のすべてのチャネルの数。</span><span class="sxs-lookup"><span data-stu-id="634df-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="634df-120">**チーム メンバー** - テナントの所有者、ゲスト、メンバーを含む合計ユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="634df-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="634df-121">**所有者** - このチームの所有者の数。</span><span class="sxs-lookup"><span data-stu-id="634df-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="634df-122">**ゲスト** - このチームのメンバーである、Azure Active Directory B2B ゲスト ユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="634df-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="634df-123">**プライバシー** -バッキング Microsoft 365 グループの可視性/AccessType。</span><span class="sxs-lookup"><span data-stu-id="634df-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="634df-124">**状態** - このチームの状態がアーカイブ済みかアクティブか。</span><span class="sxs-lookup"><span data-stu-id="634df-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="634df-125">チームのアーカイブに関する詳細については、「[チームをアーカイブまたは復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="634df-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="634df-126">[ **Description** ]-バッキング Microsoft 365 グループの説明。</span><span class="sxs-lookup"><span data-stu-id="634df-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="634df-127">**分類** : バッキング Microsoft 365 グループに割り当てられている (組織で使用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="634df-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="634df-128">分類の詳細については、「[組織の Office グループに対する分類を作成する](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="634df-128">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="634df-129">**Groupid** -バッキング Microsoft 365 グループの固有の groupid。</span><span class="sxs-lookup"><span data-stu-id="634df-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="634df-130">グリッドにこれらのプロパティがすべて表示されない場合は、**[列の編集]** アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="634df-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="634df-131">**[列の編集]** ウィンドウで、トグルを使用してグリッドの列のオンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="634df-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="634df-132">完了したら、**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="634df-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="634df-133">追加</span><span class="sxs-lookup"><span data-stu-id="634df-133">Add</span></span>

<span data-ttu-id="634df-134">新しいチームを追加するには、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="634df-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="634df-135">**[新しいチームの追加]** ウィンドウで、チームの名前と説明を入力し、プライベート チームかパブリック チームのどちらにするかを決定し、分類を設定します。</span><span class="sxs-lookup"><span data-stu-id="634df-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

> [!NOTE]
> <span data-ttu-id="634df-136">新しく作成されたチームは、Outlook などの他のクライアントの操作とは異なり、Teams 管理センターですぐに管理できます。</span><span class="sxs-lookup"><span data-stu-id="634df-136">Newly created teams can be managed right away in the Teams Admin Center, unlike the experience in other clients like, Outlook.</span></span>

### <a name="edit"></a><span data-ttu-id="634df-137">編集</span><span class="sxs-lookup"><span data-stu-id="634df-137">Edit</span></span>

<span data-ttu-id="634df-138">グループおよびチーム固有の設定を編集するには、チーム名の左側をクリックしてチームを選択し、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="634df-138">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="634df-139">アーカイブ</span><span class="sxs-lookup"><span data-stu-id="634df-139">Archive</span></span>

<span data-ttu-id="634df-140">チームをアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="634df-140">You can archive a team.</span></span> <span data-ttu-id="634df-141">チームをアーカイブすると、チームは Microsoft Teams 内で読み取り専用モードに切り替わります。</span><span class="sxs-lookup"><span data-stu-id="634df-141">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="634df-142">管理者は組織の代理として、チームのアーカイブやアーカイブの解除を管理センターで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="634df-142">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="634df-143">削除</span><span class="sxs-lookup"><span data-stu-id="634df-143">Delete</span></span>

<span data-ttu-id="634df-144">チームを削除すると、チームと対応する Microsoft 365 グループのソフト削除となります。</span><span class="sxs-lookup"><span data-stu-id="634df-144">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="634df-145">誤って削除されたチームを復元するには、「 [削除されたグループを復元](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="634df-145">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="634df-146">検索</span><span class="sxs-lookup"><span data-stu-id="634df-146">Search</span></span>

<span data-ttu-id="634df-147">検索では現在「Begins with (次で始まる)」文字列をサポートされていて、[**Team name (チーム名)**] フィールドの検索を行います。</span><span class="sxs-lookup"><span data-stu-id="634df-147">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="634df-148">チーム プロフィール</span><span class="sxs-lookup"><span data-stu-id="634df-148">Team profile</span></span>

<span data-ttu-id="634df-149">メインのチームの概要グリッドから、チーム名をクリックすることによって、任意のチームのチーム プロフィール ページに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="634df-149">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="634df-150">[チームプロファイル] ページには、チーム (およびそのバッキング Microsoft 365 グループ) に属するメンバー、所有者、ゲスト、およびチームのチャネルと設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="634df-150">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="634df-151">チーム プロフィール ページから、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="634df-151">From the team profile page, you can:</span></span>

- <span data-ttu-id="634df-152">メンバーおよび所有者の追加または削除。</span><span class="sxs-lookup"><span data-stu-id="634df-152">Add or remove members and owners.</span></span>
- <span data-ttu-id="634df-153">チャネルの追加または削除 (全般チャネルを削除することはできません)。</span><span class="sxs-lookup"><span data-stu-id="634df-153">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="634df-154">チームおよびグループの設定の変更。</span><span class="sxs-lookup"><span data-stu-id="634df-154">Change team and group settings.</span></span>
 
![チーム プロフィールの例のスクリーンショット](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="634df-156">チームに対する変更</span><span class="sxs-lookup"><span data-stu-id="634df-156">Making changes to teams</span></span>

<span data-ttu-id="634df-157">チームのプロフィールのページで、チームの次の要素を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="634df-157">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="634df-158">**メンバー** - メンバーの追加や削除、所有者の昇格または降格を行います。</span><span class="sxs-lookup"><span data-stu-id="634df-158">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="634df-159">**チャネル** - 新しいチャネルの追加、既存チャネルの編集や削除を行います。</span><span class="sxs-lookup"><span data-stu-id="634df-159">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="634df-160">既定の全般チャネルを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="634df-160">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="634df-161">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="634df-161">**Team name**</span></span>
- <span data-ttu-id="634df-162">**説明**</span><span class="sxs-lookup"><span data-stu-id="634df-162">**Description**</span></span>
- <span data-ttu-id="634df-163">**プライバシー** - チームをパブリックかプライベートに設定します。</span><span class="sxs-lookup"><span data-stu-id="634df-163">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="634df-164">**分類** -これは Microsoft 365 グループの分類によってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="634df-164">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="634df-165">**[社外秘]**、**[非常に機密性の高い社外秘]**、または **[一般]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="634df-165">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="634df-166">**会話の設定** - 送信されたメッセージをメンバーが編集および削除できるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="634df-166">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="634df-167">**チャネルの設定** - メンバーが新しいチャネルを作成したり、既存のチャネルを編集したりできるかどうかを設定します。また、タブ、コネクタ、アプリの追加、編集、削除も行えます。</span><span class="sxs-lookup"><span data-stu-id="634df-167">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="634df-168">チームに対して行う変更はログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="634df-168">The changes that you make to a team are logged.</span></span> <span data-ttu-id="634df-169">グループ設定 (名前、説明、写真、プライバシー、分類、またはチーム メンバー) を変更する場合、これらの変更は監査パイプラインを通して自分自身によるものとされます。</span><span class="sxs-lookup"><span data-stu-id="634df-169">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="634df-170">Teams 固有の設定に対するアクションを実行している場合、自分による変更は、チームの全般チャネル内で記録され、自分自身によるものとされます。</span><span class="sxs-lookup"><span data-stu-id="634df-170">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="634df-171">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="634df-171">Troubleshooting</span></span>

<span data-ttu-id="634df-172">**問題: チームがチームの概要グリッドに表示されない**</span><span class="sxs-lookup"><span data-stu-id="634df-172">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="634df-173">チームの概要グリッド内のチーム一覧に、一部のチームが表示されない。</span><span class="sxs-lookup"><span data-stu-id="634df-173">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="634df-174">**原因**: この問題は、チームがシステムによって不適切にプロファイルされた場合 (またはまだプロファイルされていない場合) に発生し、チームを認識するためのプロパティが見つからない状態を作ります。</span><span class="sxs-lookup"><span data-stu-id="634df-174">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="634df-175">**解決方法: MS Graph でプロパティを適切な値に手動で設定します。**</span><span class="sxs-lookup"><span data-stu-id="634df-175">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="634df-176">該当する GroupId に対するクエリで **{groupid}** を置き換えます。{groupid} は、Exchange Online powershell で "**ExternalDirectoryObjectId**" 属性として **"[Get-unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** コマンドレットを使用して取得できます。　</span><span class="sxs-lookup"><span data-stu-id="634df-176">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="634df-177">[Graph エクスプローラー](https://developer.microsoft.com/graph/graph-explorer)にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="634df-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="634df-178">左側のメニューで、Graph エクスプローラーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="634df-178">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="634df-179">クエリの行を、PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid} に変更します。</span><span class="sxs-lookup"><span data-stu-id="634df-179">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="634df-180">リクエストの本文に、次の値を追加します: {"resourceProvisioningOptions": ["Team"]}</span><span class="sxs-lookup"><span data-stu-id="634df-180">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="634df-181">右上のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="634df-181">Run the query on the top-right.</span></span>

6. <span data-ttu-id="634df-182">Microsoft Teams 管理センターのチームの概要ページで、チームが正しく表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="634df-182">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="634df-183">詳細情報</span><span class="sxs-lookup"><span data-stu-id="634df-183">Learn more</span></span>

- [<span data-ttu-id="634df-184">Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="634df-184">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="634df-185">Teams の管理者ロールを使用して Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="634df-185">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="634df-186">Teams でのライフサイクル管理を計画する</span><span class="sxs-lookup"><span data-stu-id="634df-186">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
