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
ms.openlocfilehash: 8c83d985a277c8341565e44878ba03385e23a358
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904999"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="3800a-103">Microsoft Teams 管理センターでチームを管理する</span><span class="sxs-lookup"><span data-stu-id="3800a-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="3800a-104">概要</span><span class="sxs-lookup"><span data-stu-id="3800a-104">Overview</span></span>

<span data-ttu-id="3800a-105">この記事では、Microsoft Teams の管理センターでの Teams 管理ツールの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="3800a-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="3800a-106">管理者である場合、自分の組織で共同作業のためにセットアップしたチームを表示したり更新したりする必要性が生じます。また、所有者のいないチームに所有者を割り当てるなどの修復アクションを実行しなければならない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="3800a-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="3800a-107">組織のチームは、Microsoft Teams PowerShell モジュールと Microsoft Teams 管理センターの両方から管理することができます。</span><span class="sxs-lookup"><span data-stu-id="3800a-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="3800a-108">これらの 2 つのツールセットを使用した完全な管理機能については、次の役割の 1 つが割り当てられることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3800a-108">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="3800a-109">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="3800a-109">Global Administrator</span></span>
- <span data-ttu-id="3800a-110">Teams サービス管理者</span><span class="sxs-lookup"><span data-stu-id="3800a-110">Teams Service Administrator</span></span>

<span data-ttu-id="3800a-111">Teams での管理者の役割の詳細については、「[ Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」をご覧ください。また、PowerShell コマンドレットを使用してチームを管理する方法の詳細については、「[Microsoft Teams コマンドレットのリファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3800a-111">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="3800a-112">Teams の概要グリッド</span><span class="sxs-lookup"><span data-stu-id="3800a-112">Teams overview grid</span></span>

<span data-ttu-id="3800a-113">チームの管理ツールは、Microsoft Teams 管理センターの [**Teams**] ノードの下にあります。</span><span class="sxs-lookup"><span data-stu-id="3800a-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="3800a-114">(管理センターでは、[**Teams**] > [**Manage teams (チームの管理)**] を選択します。)各チームは Offfice 365 グループによって支えられていて、このノードは自分の組織内で Microsoft Teams に対応しているグループの表示を提供します。</span><span class="sxs-lookup"><span data-stu-id="3800a-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Teams の概要グリッドのスクリーンショット](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="3800a-116">このグリッドには、次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3800a-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="3800a-117">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="3800a-117">**Team name**</span></span>
- <span data-ttu-id="3800a-118">**チャネル** - 既定の全般チャネルを含む、チーム内のすべてのチャネルの数。</span><span class="sxs-lookup"><span data-stu-id="3800a-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="3800a-119">**チーム メンバー** - テナントの所有者、ゲスト、メンバーを含む合計ユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="3800a-119">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="3800a-120">**所有者** - このチームの所有者の数。</span><span class="sxs-lookup"><span data-stu-id="3800a-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="3800a-121">**ゲスト** - このチームのメンバーである、Azure Active Directory B2B ゲスト ユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="3800a-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="3800a-122">**プライバシー** - 基となる Office 365 グループの可視性/AccessType。</span><span class="sxs-lookup"><span data-stu-id="3800a-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="3800a-123">**状態** - このチームの状態がアーカイブ済みかアクティブか。</span><span class="sxs-lookup"><span data-stu-id="3800a-123">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="3800a-124">チームのアーカイブに関する詳細については、「[チームをアーカイブまたは復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3800a-124">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="3800a-125">**説明** - 基となる Office 365 グループの説明。</span><span class="sxs-lookup"><span data-stu-id="3800a-125">**Description** - the description of the backing Office 365 group.</span></span>
- <span data-ttu-id="3800a-126">**分類** - 基となる Office 365 の グループに割り当てられている分類 (組織内で使用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="3800a-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span> <span data-ttu-id="3800a-127">分類の詳細については、「[組織の Office グループに対する分類を作成する](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3800a-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="3800a-128">**GroupID** - 基となる Office 365 グループの一意の GroupID。</span><span class="sxs-lookup"><span data-stu-id="3800a-128">**GroupID** - the unique GroupID of the backing Office 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="3800a-129">グリッドにこれらのプロパティがすべて表示されない場合は、**[列の編集]** アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3800a-129">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="3800a-130">**[列の編集]** ウィンドウで、トグルを使用してグリッドの列のオンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="3800a-130">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="3800a-131">完了したら、**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3800a-131">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="3800a-132">追加</span><span class="sxs-lookup"><span data-stu-id="3800a-132">Add</span></span>

<span data-ttu-id="3800a-133">新しいチームを追加するには、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3800a-133">To add a new team, click **Add**.</span></span> <span data-ttu-id="3800a-134">**[新しいチームの追加]** ウィンドウで、チームの名前と説明を入力し、プライベート チームかパブリック チームのどちらにするかを決定し、分類を設定します。</span><span class="sxs-lookup"><span data-stu-id="3800a-134">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="3800a-135">編集</span><span class="sxs-lookup"><span data-stu-id="3800a-135">Edit</span></span>

<span data-ttu-id="3800a-136">グループおよびチーム固有の設定を編集するには、チーム名の左側をクリックしてチームを選択し、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3800a-136">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="3800a-137">アーカイブ</span><span class="sxs-lookup"><span data-stu-id="3800a-137">Archive</span></span>

<span data-ttu-id="3800a-138">チームをアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="3800a-138">You can archive a team.</span></span> <span data-ttu-id="3800a-139">チームをアーカイブすると、チームは Microsoft Teams 内で読み取り専用モードに切り替わります。</span><span class="sxs-lookup"><span data-stu-id="3800a-139">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="3800a-140">管理者は組織の代理として、チームのアーカイブやアーカイブの解除を管理センターで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3800a-140">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="3800a-141">削除</span><span class="sxs-lookup"><span data-stu-id="3800a-141">Delete</span></span>

<span data-ttu-id="3800a-142">チームを削除すると、チームとそれに対応する Office 365 グループが論理的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="3800a-142">Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span> <span data-ttu-id="3800a-143">誤って削除したチームを復元するには、「[削除された Office 365 グループを復元する](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="3800a-143">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>

### <a name="search"></a><span data-ttu-id="3800a-144">検索</span><span class="sxs-lookup"><span data-stu-id="3800a-144">Search</span></span>

<span data-ttu-id="3800a-145">検索では現在「Begins with (次で始まる)」文字列をサポートされていて、[**Team name (チーム名)**] フィールドの検索を行います。</span><span class="sxs-lookup"><span data-stu-id="3800a-145">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="3800a-146">チーム プロフィール</span><span class="sxs-lookup"><span data-stu-id="3800a-146">Team profile</span></span>

<span data-ttu-id="3800a-147">メインのチームの概要グリッドから、チーム名をクリックすることによって、任意のチームのチーム プロフィール ページに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="3800a-147">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="3800a-148">チームプロファイルページには、チーム (およびそのバッキング Office 365 グループ) に属しているメンバー、所有者、ゲスト、およびチームのチャネルと設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3800a-148">The team profile page shows the members, owners, and guests that belong to the team (and its backing Office 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="3800a-149">チーム プロフィール ページから、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3800a-149">From the team profile page, you can:</span></span>

- <span data-ttu-id="3800a-150">メンバーおよび所有者の追加または削除。</span><span class="sxs-lookup"><span data-stu-id="3800a-150">Add or remove members and owners.</span></span>
- <span data-ttu-id="3800a-151">チャネルの追加または削除 (全般チャネルを削除することはできません)。</span><span class="sxs-lookup"><span data-stu-id="3800a-151">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="3800a-152">チームおよびグループの設定の変更。</span><span class="sxs-lookup"><span data-stu-id="3800a-152">Change team and group settings.</span></span>
 
![チーム プロフィールの例のスクリーンショット](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="3800a-154">チームに対する変更</span><span class="sxs-lookup"><span data-stu-id="3800a-154">Making changes to teams</span></span>

<span data-ttu-id="3800a-155">チームのプロフィールのページで、チームの次の要素を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="3800a-155">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="3800a-156">**メンバー** - メンバーの追加や削除、所有者の昇格または降格を行います。</span><span class="sxs-lookup"><span data-stu-id="3800a-156">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="3800a-157">**チャネル** - 新しいチャネルの追加、既存チャネルの編集や削除を行います。</span><span class="sxs-lookup"><span data-stu-id="3800a-157">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="3800a-158">既定の全般チャネルを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="3800a-158">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="3800a-159">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="3800a-159">**Team name**</span></span>
- <span data-ttu-id="3800a-160">**説明**</span><span class="sxs-lookup"><span data-stu-id="3800a-160">**Description**</span></span>
- <span data-ttu-id="3800a-161">**プライバシー** - チームをパブリックかプライベートに設定します。</span><span class="sxs-lookup"><span data-stu-id="3800a-161">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="3800a-162">**分類** - これは自分の Office 365 グループの分類に基づいています。</span><span class="sxs-lookup"><span data-stu-id="3800a-162">**Classification** - this is backed by your Office 365 group classifications.</span></span> <span data-ttu-id="3800a-163">**[社外秘]**、**[非常に機密性の高い社外秘]**、または **[一般]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3800a-163">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="3800a-164">**会話の設定** - 送信されたメッセージをメンバーが編集および削除できるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="3800a-164">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="3800a-165">**チャネルの設定** - メンバーが新しいチャネルを作成したり、既存のチャネルを編集したりできるかどうかを設定します。また、タブ、コネクタ、アプリの追加、編集、削除も行えます。</span><span class="sxs-lookup"><span data-stu-id="3800a-165">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="3800a-166">チームに対して行う変更はログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="3800a-166">The changes that you make to a team are logged.</span></span> <span data-ttu-id="3800a-167">グループ設定 (名前、説明、写真、プライバシー、分類、またはチーム メンバー) を変更する場合、これらの変更は監査パイプラインを通して自分自身によるものとされます。</span><span class="sxs-lookup"><span data-stu-id="3800a-167">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="3800a-168">Teams 固有の設定に対するアクションを実行している場合、自分による変更は、チームの全般チャネル内で記録され、自分自身によるものとされます。</span><span class="sxs-lookup"><span data-stu-id="3800a-168">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="3800a-169">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3800a-169">Troubleshooting</span></span>

<span data-ttu-id="3800a-170">**問題: チームがチームの概要グリッドに表示されない**</span><span class="sxs-lookup"><span data-stu-id="3800a-170">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="3800a-171">チームの概要グリッド内のチーム一覧に、一部のチームが表示されない。</span><span class="sxs-lookup"><span data-stu-id="3800a-171">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="3800a-172">**原因**: この問題は、チームがシステムによって不適切にプロファイルされた場合 (またはまだプロファイルされていない場合) に発生し、チームを認識するためのプロパティが見つからない状態を作ります。</span><span class="sxs-lookup"><span data-stu-id="3800a-172">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="3800a-173">**解決方法: MS Graph でプロパティを適切な値に手動で設定します。**</span><span class="sxs-lookup"><span data-stu-id="3800a-173">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="3800a-174">該当する GroupId に対するクエリで **{groupid}** を置き換えます。{groupid} は、Exchange Online powershell で "**ExternalDirectoryObjectId**" 属性として **"[Get-unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** コマンドレットを使用して取得できます。　</span><span class="sxs-lookup"><span data-stu-id="3800a-174">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="3800a-175">[Graph エクスプローラー](https://developer.microsoft.com/graph/graph-explorer)にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3800a-175">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="3800a-176">左側のメニューで、Graph エクスプローラーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="3800a-176">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="3800a-177">クエリの行を、PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid} に変更します。</span><span class="sxs-lookup"><span data-stu-id="3800a-177">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="3800a-178">リクエストの本文に、次の値を追加します: {"resourceProvisioningOptions": ["Team"]}</span><span class="sxs-lookup"><span data-stu-id="3800a-178">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="3800a-179">右上のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3800a-179">Run the query on the top-right.</span></span>

6. <span data-ttu-id="3800a-180">Microsoft Teams 管理センターのチームの概要ページで、チームが正しく表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3800a-180">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="3800a-181">詳細情報</span><span class="sxs-lookup"><span data-stu-id="3800a-181">Learn more</span></span>

- [<span data-ttu-id="3800a-182">Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="3800a-182">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="3800a-183">Teams の管理者ロールを使用して Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="3800a-183">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="3800a-184">Teams でのライフサイクル管理を計画する</span><span class="sxs-lookup"><span data-stu-id="3800a-184">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
