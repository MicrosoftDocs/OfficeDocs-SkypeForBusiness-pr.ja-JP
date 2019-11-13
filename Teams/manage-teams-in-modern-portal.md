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
ms.openlocfilehash: 0c7adfc2762d632f600f2982445f381139263894
ms.sourcegitcommit: ed7439d03e37c9c0184daf5215a68c5492932a83
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "38290937"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="9e28b-103">Microsoft Teams 管理センターでチームを管理する</span><span class="sxs-lookup"><span data-stu-id="9e28b-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="9e28b-104">概要</span><span class="sxs-lookup"><span data-stu-id="9e28b-104">Overview</span></span>

<span data-ttu-id="9e28b-105">この記事では、Microsoft Teams 管理センターの Teams の管理ツールの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e28b-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span> <span data-ttu-id="9e28b-106">この短いビデオを見ていきます (3 分)。</span><span class="sxs-lookup"><span data-stu-id="9e28b-106">Start by watching this short video (3 minutes):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yi]

<span data-ttu-id="9e28b-107">管理者として、組織が共同作業のためにセットアップしたチームを表示または更新する必要がある場合、または ownerless teams の所有者を割り当てるなどの修復アクションを実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e28b-107">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="9e28b-108">組織のチームは、Microsoft Teams PowerShell モジュールと Microsoft Teams 管理センターの両方から管理することができます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-108">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="9e28b-109">これらの 2 つのツールセットを使用した完全な管理機能については、次の役割の 1 つが割り当てられることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e28b-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="9e28b-110">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="9e28b-110">Global Administrator</span></span>
- <span data-ttu-id="9e28b-111">Teams サービス管理者</span><span class="sxs-lookup"><span data-stu-id="9e28b-111">Teams Service Administrator</span></span>

<span data-ttu-id="9e28b-112">Teams での管理者の役割の詳細については、「[ Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」をご覧ください。また、PowerShell コマンドレットを使用してチームを管理する方法の詳細については、「[Microsoft Teams コマンドレットのリファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9e28b-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="9e28b-113">Teams の概要グリッド</span><span class="sxs-lookup"><span data-stu-id="9e28b-113">Teams overview grid</span></span>

<span data-ttu-id="9e28b-114">チームの管理ツールは、Microsoft Teams 管理センターの [**Teams**] ノードの下にあります。</span><span class="sxs-lookup"><span data-stu-id="9e28b-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="9e28b-115">(管理センターでは、[**Teams**] > [**Manage teams (チームの管理)**] を選択します。)各チームは Offfice 365 グループによって支えられていて、このノードは自分の組織内で Microsoft Teams に対応しているグループの表示を提供します。</span><span class="sxs-lookup"><span data-stu-id="9e28b-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![チームの概要グリッドのスクリーンショット](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="9e28b-117">このグリッドには、次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="9e28b-118">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="9e28b-118">**Team name**</span></span>
- <span data-ttu-id="9e28b-119">**チャネル** - 既定の全般チャネルを含む、チーム内のすべてのチャネルの数。</span><span class="sxs-lookup"><span data-stu-id="9e28b-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="9e28b-120">**チームメンバー** -テナントの所有者、ゲスト、メンバーを含む、ユーザーの合計数です。</span><span class="sxs-lookup"><span data-stu-id="9e28b-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="9e28b-121">**所有者** - このチームの所有者の数。</span><span class="sxs-lookup"><span data-stu-id="9e28b-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="9e28b-122">**ゲスト** - このチームのメンバーである、Azure Active Directory B2B ゲスト ユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="9e28b-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="9e28b-123">**プライバシー** - 基となる Office 365 グループの可視性/AccessType。</span><span class="sxs-lookup"><span data-stu-id="9e28b-123">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="9e28b-124">**状態** - このチームの状態がアーカイブ済みかアクティブか。</span><span class="sxs-lookup"><span data-stu-id="9e28b-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="9e28b-125">チームのアーカイブの詳細について[は、「チームをアーカイブまたは復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e28b-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="9e28b-126">[ **Description** ]-バッキング Office 365 グループの説明。</span><span class="sxs-lookup"><span data-stu-id="9e28b-126">**Description** - the description of the backing Office 365 group.</span></span>
- <span data-ttu-id="9e28b-127">**分類** - 基となる Office 365 の グループに割り当てられている分類 (組織内で使用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="9e28b-127">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span> <span data-ttu-id="9e28b-128">分類の詳細については、「[組織の Office グループに対する分類を作成する](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e28b-128">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="9e28b-129">**Groupid** -バッキング Office 365 グループの固有の groupid。</span><span class="sxs-lookup"><span data-stu-id="9e28b-129">**GroupID** - the unique GroupID of the backing Office 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="9e28b-130">グリッドにこれらのプロパティがすべて表示されない場合は、[**列の編集**] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e28b-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="9e28b-131">[**列の編集**] ウィンドウで、トグルを使用して、グリッドの列のオンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="9e28b-132">完了したら、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e28b-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="9e28b-133">追加</span><span class="sxs-lookup"><span data-stu-id="9e28b-133">Add</span></span>

<span data-ttu-id="9e28b-134">新しいチームを追加するには、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e28b-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="9e28b-135">[**新しいチームの追加**] ウィンドウで、チームに名前と説明を入力し、プライベートチームとパブリックチームのどちらにするかを設定し、分類を設定します。</span><span class="sxs-lookup"><span data-stu-id="9e28b-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="9e28b-136">編集</span><span class="sxs-lookup"><span data-stu-id="9e28b-136">Edit</span></span>

<span data-ttu-id="9e28b-137">グループおよびチーム固有の設定を編集するには、チーム名の左側をクリックしてチームを選択し、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e28b-137">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="9e28b-138">アーカイブ</span><span class="sxs-lookup"><span data-stu-id="9e28b-138">Archive</span></span>

<span data-ttu-id="9e28b-139">チームをアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-139">You can archive a team.</span></span> <span data-ttu-id="9e28b-140">チームをアーカイブすると、チームはチーム内で読み取り専用モードになります。</span><span class="sxs-lookup"><span data-stu-id="9e28b-140">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="9e28b-141">管理センターでは、管理者として、組織の代理としてチームのアーカイブやアーカイブの解除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-141">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="9e28b-142">削除</span><span class="sxs-lookup"><span data-stu-id="9e28b-142">Delete</span></span>

<span data-ttu-id="9e28b-143">チームを削除すると、チームと対応する Office 365 グループのソフト削除となります。</span><span class="sxs-lookup"><span data-stu-id="9e28b-143">Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span> <span data-ttu-id="9e28b-144">誤って削除されたチームを復元するには、「[削除された Office 365 グループを復元](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9e28b-144">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>

### <a name="search"></a><span data-ttu-id="9e28b-145">検索</span><span class="sxs-lookup"><span data-stu-id="9e28b-145">Search</span></span>

<span data-ttu-id="9e28b-146">検索では現在「Begins with (次で始まる)」文字列をサポートされていて、[**Team name (チーム名)**] フィールドの検索を行います。</span><span class="sxs-lookup"><span data-stu-id="9e28b-146">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="9e28b-147">チーム プロフィール</span><span class="sxs-lookup"><span data-stu-id="9e28b-147">Team profile</span></span>

<span data-ttu-id="9e28b-148">チーム名をクリックすると、チームのメインの概要グリッドからチームプロファイルページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-148">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="9e28b-149">チームプロファイルページには、チーム (およびそのバッキング Office 365 グループ) に属しているメンバー、所有者、ゲスト、およびチームのチャネルと設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-149">The team profile page shows the members, owners, and guests that belong to the team (and its backing Office 365 group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="9e28b-150">チーム プロフィール ページから、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-150">From the team profile page, you can:</span></span>

- <span data-ttu-id="9e28b-151">メンバーおよび所有者の追加または削除。</span><span class="sxs-lookup"><span data-stu-id="9e28b-151">Add or remove members and owners.</span></span>
- <span data-ttu-id="9e28b-152">チャネルを追加または削除する (一般的なチャネルは削除できないことに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="9e28b-152">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="9e28b-153">チームとグループの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="9e28b-153">Change team and group settings.</span></span>
 
![チームプロファイルの例のスクリーンショット](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="9e28b-155">チームに対する変更</span><span class="sxs-lookup"><span data-stu-id="9e28b-155">Making changes to teams</span></span>

<span data-ttu-id="9e28b-156">チームのプロファイルページで、チームの次の要素を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-156">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="9e28b-157">**メンバー** -メンバーの追加または削除、所有者のレベル上げまたはレベル下げを行います。</span><span class="sxs-lookup"><span data-stu-id="9e28b-157">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="9e28b-158">**チャネル**-新しいチャネルを追加し、既存のチャネルを編集または削除します。</span><span class="sxs-lookup"><span data-stu-id="9e28b-158">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="9e28b-159">既定の [全般] チャネルは削除できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9e28b-159">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="9e28b-160">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="9e28b-160">**Team name**</span></span>
- <span data-ttu-id="9e28b-161">**説明**</span><span class="sxs-lookup"><span data-stu-id="9e28b-161">**Description**</span></span>
- <span data-ttu-id="9e28b-162">[**プライバシー** -チームが公開または非公開のどちらであるかを設定します。</span><span class="sxs-lookup"><span data-stu-id="9e28b-162">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="9e28b-163">**分類**-これは、Office 365 グループの分類によってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-163">**Classification** - this is backed by your Office 365 group classifications.</span></span> <span data-ttu-id="9e28b-164">[**社外秘**]、[**機密性の高い**]、または **[標準**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-164">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="9e28b-165">[**スレッドの設定**]-送信されたメッセージをメンバーが編集および削除できるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="9e28b-165">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="9e28b-166">[**チャネルの設定**]-メンバーが新しいチャネルを作成したり、既存のチャネルを編集したりできるかどうかを設定します。また、タブ、コネクタ、アプリを追加、編集、削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-166">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="9e28b-167">チームに対して行う変更はログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-167">The changes that you make to a team are logged.</span></span> <span data-ttu-id="9e28b-168">グループ設定 (名前、説明、写真、プライバシー、分類、またはチームメンバーの変更) を変更する場合、変更は監査パイプラインによって表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-168">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="9e28b-169">チーム固有の設定に対して操作を実行している場合、変更はチームの [全般] チャネルで管理され、自分に帰属しています。</span><span class="sxs-lookup"><span data-stu-id="9e28b-169">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9e28b-170">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9e28b-170">Troubleshooting</span></span>

<span data-ttu-id="9e28b-171">**問題: チームの概要グリッドでチームが見つからない**</span><span class="sxs-lookup"><span data-stu-id="9e28b-171">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="9e28b-172">チームの概要グリッドのチームの一覧に一部のチームが表示されない。</span><span class="sxs-lookup"><span data-stu-id="9e28b-172">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="9e28b-173">**原因**: この問題は、チームがシステムによって不適切にプロファイルされた場合 (またはまだプロファイルされていない場合) に発生し、チームを認識するためのプロパティが見つからない状態を作ります。</span><span class="sxs-lookup"><span data-stu-id="9e28b-173">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="9e28b-174">**解決方法: MS Graph でプロパティを適切な値に手動で設定します。**</span><span class="sxs-lookup"><span data-stu-id="9e28b-174">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="9e28b-175">該当する GroupId に対するクエリで **{groupid}** を置き換えます。{groupid} は、Exchange Online powershell で "**ExternalDirectoryObjectId**" 属性として **"[Get-unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** コマンドレットを使用して取得できます。　</span><span class="sxs-lookup"><span data-stu-id="9e28b-175">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="9e28b-176">Access [Graph エクスプローラー](https://developer.microsoft.com/graph/graph-explorer)。</span><span class="sxs-lookup"><span data-stu-id="9e28b-176">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="9e28b-177">左側のメニューで、[Graph エクスプローラー] にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9e28b-177">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="9e28b-178">クエリ行を次のように変更します。 https://graph.microsoft.com/v1.0/groups/{groupid}[PATCH > v 1.0 > を選びます。</span><span class="sxs-lookup"><span data-stu-id="9e28b-178">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="9e28b-179">要求本文に次の値を追加します: {"Resourceてオプション": ["Team"]}</span><span class="sxs-lookup"><span data-stu-id="9e28b-179">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="9e28b-180">右上のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="9e28b-180">Run the query on the top-right.</span></span>

6. <span data-ttu-id="9e28b-181">[Microsoft Teams 管理センター-チームの概要」でチームが正しく表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e28b-181">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="9e28b-182">詳細情報</span><span class="sxs-lookup"><span data-stu-id="9e28b-182">Learn more</span></span>

- [<span data-ttu-id="9e28b-183">Teams コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="9e28b-183">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="9e28b-184">チーム管理者ロールを使用してチームを管理する</span><span class="sxs-lookup"><span data-stu-id="9e28b-184">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="9e28b-185">Teams でのライフサイクル管理を計画する</span><span class="sxs-lookup"><span data-stu-id="9e28b-185">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
