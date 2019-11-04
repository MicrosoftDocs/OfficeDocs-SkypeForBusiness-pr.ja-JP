---
title: Microsoft Teams 管理センターでチームを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Microsoft Teams の管理センターで自分のチームの表示や更新を行う方法を説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fea7081ee66cbd7b103f4292f577aaf5d841e11
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "37571936"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="d80fc-103">Microsoft Teams 管理センターでチームを管理する</span><span class="sxs-lookup"><span data-stu-id="d80fc-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="d80fc-104">概要</span><span class="sxs-lookup"><span data-stu-id="d80fc-104">Overview</span></span>

<span data-ttu-id="d80fc-105">管理者として、組織が共同作業のためにセットアップしたチームを表示または更新する必要がある場合、または ownerless teams の所有者を割り当てるなどの修復アクションを実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d80fc-105">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="d80fc-106">組織のチームは、Microsoft Teams PowerShell モジュールと Microsoft Teams 管理センターの両方から管理することができます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="d80fc-107">これらの 2 つのツールセットを使用した完全な管理機能については、次の役割の 1 つが割り当てられることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d80fc-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="d80fc-108">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="d80fc-108">Global Administrator</span></span>
- <span data-ttu-id="d80fc-109">Teams サービス管理者</span><span class="sxs-lookup"><span data-stu-id="d80fc-109">Teams Service Administrator</span></span>

<span data-ttu-id="d80fc-110">Teams での管理者の役割の詳細については、「[ Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」をご覧ください。また、PowerShell コマンドレットを使用してチームを管理する方法の詳細については、「[Microsoft Teams コマンドレットのリファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d80fc-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>

<span data-ttu-id="d80fc-111">この記事では、Microsoft Teams の管理センターでのチーム 管理ツールの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="d80fc-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="d80fc-112">Teams の概要グリッド</span><span class="sxs-lookup"><span data-stu-id="d80fc-112">Teams overview grid</span></span>

<span data-ttu-id="d80fc-113">チームの管理ツールは、Microsoft Teams 管理センターの [**Teams**] ノードの下にあります。</span><span class="sxs-lookup"><span data-stu-id="d80fc-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d80fc-114">(管理センターでは、[**Teams**] > [**Manage teams (チームの管理)**] を選択します。)各チームは Offfice 365 グループによって支えられていて、このノードは自分の組織内で Microsoft Teams に対応しているグループの表示を提供します。</span><span class="sxs-lookup"><span data-stu-id="d80fc-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![チームの概要グリッドのスクリーンショット](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="d80fc-116">このグリッドには、次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="d80fc-117">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="d80fc-117">**Team name**</span></span>
- <span data-ttu-id="d80fc-118">**チャネル** - 既定の全般チャネルを含む、チーム内のすべてのチャネルの数。</span><span class="sxs-lookup"><span data-stu-id="d80fc-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="d80fc-119">**チームメンバー** -テナントの所有者、ゲスト、メンバーを含む、ユーザーの合計数です。</span><span class="sxs-lookup"><span data-stu-id="d80fc-119">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="d80fc-120">**所有者** - このチームの所有者の数。</span><span class="sxs-lookup"><span data-stu-id="d80fc-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="d80fc-121">**ゲスト** - このチームのメンバーである、Azure Active Directory B2B ゲスト ユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="d80fc-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="d80fc-122">**プライバシー** - 基となる Office 365 グループの可視性/AccessType。</span><span class="sxs-lookup"><span data-stu-id="d80fc-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="d80fc-123">**状態** - このチームの状態がアーカイブ済みかアクティブか。</span><span class="sxs-lookup"><span data-stu-id="d80fc-123">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="d80fc-124">チームのアーカイブの詳細について[は、「チームをアーカイブまたは復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d80fc-124">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="d80fc-125">[ **Description** ]-バッキング Office 365 グループの説明。</span><span class="sxs-lookup"><span data-stu-id="d80fc-125">**Description** - the description of the backing Office 365 group.</span></span>
- <span data-ttu-id="d80fc-126">**分類** - 基となる Office 365 の グループに割り当てられている分類 (組織内で使用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="d80fc-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span> <span data-ttu-id="d80fc-127">分類の詳細については、「[組織の Office グループに対する分類を作成する](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d80fc-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="d80fc-128">**Groupid** -バッキング Office 365 グループの固有の groupid。</span><span class="sxs-lookup"><span data-stu-id="d80fc-128">**GroupID** - the unique GroupID of the backing Office 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="d80fc-129">グリッドにこれらのプロパティがすべて表示されない場合は、[**列の編集**] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d80fc-129">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="d80fc-130">[**列の編集**] ウィンドウで、トグルを使用して、グリッドの列のオンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-130">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="d80fc-131">完了したら、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d80fc-131">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="d80fc-132">追加</span><span class="sxs-lookup"><span data-stu-id="d80fc-132">Add</span></span>

<span data-ttu-id="d80fc-133">新しいチームを追加するには、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d80fc-133">To add a new team, click **Add**.</span></span> <span data-ttu-id="d80fc-134">[**新しいチームの追加**] ウィンドウで、チームに名前と説明を入力し、プライベートチームとパブリックチームのどちらにするかを設定し、分類を設定します。</span><span class="sxs-lookup"><span data-stu-id="d80fc-134">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="d80fc-135">編集</span><span class="sxs-lookup"><span data-stu-id="d80fc-135">Edit</span></span>

<span data-ttu-id="d80fc-136">グループおよびチーム固有の設定を編集するには、チーム名の左側をクリックしてチームを選択し、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d80fc-136">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="d80fc-137">アーカイブ</span><span class="sxs-lookup"><span data-stu-id="d80fc-137">Archive</span></span>

<span data-ttu-id="d80fc-138">チームをアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-138">You can archive a team.</span></span> <span data-ttu-id="d80fc-139">チームをアーカイブすると、チームはチーム内で読み取り専用モードになります。</span><span class="sxs-lookup"><span data-stu-id="d80fc-139">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="d80fc-140">管理センターでは、管理者として、組織の代理としてチームをアーカイブしたり、整理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-140">As an admin, you can archive and unarchive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="d80fc-141">削除</span><span class="sxs-lookup"><span data-stu-id="d80fc-141">Delete</span></span>

<span data-ttu-id="d80fc-142">チームを削除すると、チームと対応する Office 365 グループのソフト削除となります。</span><span class="sxs-lookup"><span data-stu-id="d80fc-142">Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span> <span data-ttu-id="d80fc-143">誤って削除されたチームを復元するには、「[削除された Office 365 グループを復元](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d80fc-143">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>

### <a name="search"></a><span data-ttu-id="d80fc-144">検索</span><span class="sxs-lookup"><span data-stu-id="d80fc-144">Search</span></span>

<span data-ttu-id="d80fc-145">検索では現在「Begins with (次で始まる)」文字列をサポートされていて、[**Team name (チーム名)**] フィールドの検索を行います。</span><span class="sxs-lookup"><span data-stu-id="d80fc-145">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="d80fc-146">チーム プロフィール</span><span class="sxs-lookup"><span data-stu-id="d80fc-146">Team profile</span></span>

<span data-ttu-id="d80fc-147">チーム名をクリックすると、チームのメインの概要グリッドからチームプロファイルページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-147">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="d80fc-148">チームプロファイルページには、チーム (およびそのバッキング Office 365 グループ) に属しているメンバー、所有者、ゲスト、およびチームのチャネルと設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-148">The team profile page shows the members, owners, and guests that belong to the team (and its backing Office 365 group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="d80fc-149">チーム プロフィール ページから、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-149">From the team profile page, you can:</span></span>

- <span data-ttu-id="d80fc-150">メンバーおよび所有者の追加または削除。</span><span class="sxs-lookup"><span data-stu-id="d80fc-150">Add or remove members and owners.</span></span>
- <span data-ttu-id="d80fc-151">チャネルを追加または削除する (一般的なチャネルは削除できないことに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="d80fc-151">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="d80fc-152">チームとグループの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="d80fc-152">Change team and group settings.</span></span>
 
![チームプロファイルの例のスクリーンショット](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="d80fc-154">チームに対する変更</span><span class="sxs-lookup"><span data-stu-id="d80fc-154">Making changes to teams</span></span>

<span data-ttu-id="d80fc-155">チームのプロファイルページで、チームの次の要素を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-155">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="d80fc-156">**メンバー** -メンバーの追加または削除、所有者のレベル上げまたはレベル下げを行います。</span><span class="sxs-lookup"><span data-stu-id="d80fc-156">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="d80fc-157">**チャネル**-新しいチャネルを追加し、既存のチャネルを編集または削除します。</span><span class="sxs-lookup"><span data-stu-id="d80fc-157">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="d80fc-158">既定の [全般] チャネルは削除できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d80fc-158">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="d80fc-159">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="d80fc-159">**Team name**</span></span>
- <span data-ttu-id="d80fc-160">**説明**</span><span class="sxs-lookup"><span data-stu-id="d80fc-160">**Description**</span></span>
- <span data-ttu-id="d80fc-161">[**プライバシー** -チームが公開または非公開のどちらであるかを設定します。</span><span class="sxs-lookup"><span data-stu-id="d80fc-161">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="d80fc-162">**分類**-これは、Office 365 グループの分類によってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-162">**Classification** - this is backed by your Office 365 group classifications.</span></span> <span data-ttu-id="d80fc-163">[**社外秘**]、[**機密性の高い**]、または **[標準**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-163">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="d80fc-164">[**スレッドの設定**]-送信されたメッセージをメンバーが編集および削除できるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="d80fc-164">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="d80fc-165">[**チャネルの設定**]-メンバーが新しいチャネルを作成したり、既存のチャネルを編集したりできるかどうかを設定します。また、タブ、コネクタ、アプリを追加、編集、削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-165">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="d80fc-166">チームに対して行う変更はログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-166">The changes that you make to a team are logged.</span></span> <span data-ttu-id="d80fc-167">グループ設定 (名前、説明、写真、プライバシー、分類、またはチームメンバーの変更) を変更する場合、変更は監査パイプラインによって表示されます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-167">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="d80fc-168">チーム固有の設定に対して操作を実行している場合、変更はチームの [全般] チャネルで管理され、自分に帰属しています。</span><span class="sxs-lookup"><span data-stu-id="d80fc-168">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d80fc-169">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d80fc-169">Troubleshooting</span></span>

<span data-ttu-id="d80fc-170">**問題: チームの概要グリッドでチームが見つからない**</span><span class="sxs-lookup"><span data-stu-id="d80fc-170">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="d80fc-171">チームの概要グリッドのチームの一覧に一部のチームが表示されない。</span><span class="sxs-lookup"><span data-stu-id="d80fc-171">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="d80fc-172">**原因**: この問題は、チームがシステムによって不適切にプロファイルされた場合 (またはまだプロファイルされていない場合) に発生し、チームを認識するためのプロパティが見つからない状態を作ります。</span><span class="sxs-lookup"><span data-stu-id="d80fc-172">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="d80fc-173">**解決方法: MS Graph でプロパティを適切な値に手動で設定します。**</span><span class="sxs-lookup"><span data-stu-id="d80fc-173">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="d80fc-174">該当する GroupId に対するクエリで **{groupid}** を置き換えます。{groupid} は、Exchange Online powershell で "**ExternalDirectoryObjectId**" 属性として **"[Get-unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** コマンドレットを使用して取得できます。　</span><span class="sxs-lookup"><span data-stu-id="d80fc-174">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="d80fc-175">Access [Graph エクスプローラー](https://developer.microsoft.com/en-us/graph/graph-explorer)。</span><span class="sxs-lookup"><span data-stu-id="d80fc-175">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer).</span></span>

2. <span data-ttu-id="d80fc-176">左側のメニューで、[Graph エクスプローラー] にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d80fc-176">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="d80fc-177">クエリ行を次のように変更します。 https://graph.microsoft.com/v1.0/groups/{groupid}[PATCH > v 1.0 > を選びます。</span><span class="sxs-lookup"><span data-stu-id="d80fc-177">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="d80fc-178">要求本文に次の値を追加します: {"Resourceてオプション": ["Team"]}</span><span class="sxs-lookup"><span data-stu-id="d80fc-178">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="d80fc-179">右上のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="d80fc-179">Run the query on the top-right.</span></span>

6. <span data-ttu-id="d80fc-180">[Microsoft Teams 管理センター-チームの概要」でチームが正しく表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d80fc-180">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="d80fc-181">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d80fc-181">Learn more</span></span>

- [<span data-ttu-id="d80fc-182">Teams コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="d80fc-182">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="d80fc-183">チーム管理者ロールを使用してチームを管理する</span><span class="sxs-lookup"><span data-stu-id="d80fc-183">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="d80fc-184">Teams でのライフサイクル管理を計画する</span><span class="sxs-lookup"><span data-stu-id="d80fc-184">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
