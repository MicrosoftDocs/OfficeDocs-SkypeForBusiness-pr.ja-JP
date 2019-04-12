---
title: Microsoft Teams 管理センターでチームを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Microsoft Teams の管理センターで自分のチームの表示や更新を行う方法を説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d2903e65e4ef4876f41d367ce961530020e775c
ms.sourcegitcommit: 38b501cedfe5fa4ab0126f58926fe2ce4f0cdd0c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "31740927"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b0c27-103">Microsoft Teams 管理センターでチームを管理する</span><span class="sxs-lookup"><span data-stu-id="b0c27-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="b0c27-104">概要</span><span class="sxs-lookup"><span data-stu-id="b0c27-104">Overview</span></span>

<span data-ttu-id="b0c27-105">IT 管理者である場合、自分の組織で共同作業のためにセットアップされたチームを表示所有者したり更新したりする必要が発生する可能性があります。また、所有者のいないチームに対して所有者を割り当てるなどの修復アクションを実行する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b0c27-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="b0c27-106">Microsoft Teams PowerShell モジュールおよび Microsoft Teams の管理センターを通して、組織で使用されたチームを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b0c27-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="b0c27-107">これらの 2 つのツールセットを使用した完全な管理機能については、次の役割の 1 つが割り当てられることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0c27-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="b0c27-108">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="b0c27-108">Global Administrator</span></span>
- <span data-ttu-id="b0c27-109">Teams サービス管理者</span><span class="sxs-lookup"><span data-stu-id="b0c27-109">Teams Service Administrator</span></span>

<span data-ttu-id="b0c27-110">チーム内での管理者の役割の詳細については、[ Microsoft Teamsの管理者ロールを使用してチームを管理する](using-admin-roles.md)をご覧ください。また、PowerShell コマンドレットを使用してチームを管理する方法の詳細については、 [Microsoft Teams コマンドレットのリファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b0c27-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="b0c27-111">この記事では、Microsoft Teams の管理センターでの管理ツールの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="b0c27-111">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="b0c27-112">Teams の概要リスト</span><span class="sxs-lookup"><span data-stu-id="b0c27-112">Teams overview grid</span></span>

<span data-ttu-id="b0c27-113">チームの管理ツールは、Microsoft Teams の管理センターの **Teams** ノードの下にあります。</span><span class="sxs-lookup"><span data-stu-id="b0c27-113">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="b0c27-114">(管理センターでは、[**Teams**] > [**Manage teams (チームの管理)**] を選択します。)各チームは Offfice 365 グループによって支えられていて、このノードは自分の組織内で Microsoft Teams に対応しているグループの表示を提供します。</span><span class="sxs-lookup"><span data-stu-id="b0c27-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Teams の概要グリッド](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="b0c27-116">このグリッドには、次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0c27-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="b0c27-117">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="b0c27-117">**Team name**</span></span>
- <span data-ttu-id="b0c27-118">**チャネル** - 既定の全般チャネルを含む、チーム内のすべてのチャネルの数。</span><span class="sxs-lookup"><span data-stu-id="b0c27-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="b0c27-119">**ユーザー** - テナントの所有者、ゲスト、およびメンバーを含む合計ユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="b0c27-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="b0c27-120">**所有者** - このチームの所有者の数。</span><span class="sxs-lookup"><span data-stu-id="b0c27-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="b0c27-121">**ゲスト** - このチームのメンバーである、Azure Active Directory B2B ゲスト ユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="b0c27-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="b0c27-122">**プライバシー** - バックアップする Office 365 グループの表示可否/アクセスタイプ。</span><span class="sxs-lookup"><span data-stu-id="b0c27-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="b0c27-123">**状態**-このチームがアーカイブされているかアクティブか。</span><span class="sxs-lookup"><span data-stu-id="b0c27-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="b0c27-124">チームのアーカイブに関する詳細については、[チームをアーカイブまたは復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c27-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="b0c27-125">**グループ ID** - バックアップするOffice 365 グループの一意のグループ ID</span><span class="sxs-lookup"><span data-stu-id="b0c27-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="b0c27-126">**分類**- バックアップする Office 365 の グループに割り当てられている分類 (組織内で使用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="b0c27-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="b0c27-127">分類の詳細については、[組織の Office グループに対する分類を作成する](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c27-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="b0c27-128">**説明**-Office 365 グループのバックアップの説明</span><span class="sxs-lookup"><span data-stu-id="b0c27-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="b0c27-129">検索</span><span class="sxs-lookup"><span data-stu-id="b0c27-129">Search</span></span>

<span data-ttu-id="b0c27-130">検索では現在「Begins with (次で始まる)」文字列をサポートされていて、[**Team name (チーム名)**] フィールドの検索を行います。</span><span class="sxs-lookup"><span data-stu-id="b0c27-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="b0c27-131">編集</span><span class="sxs-lookup"><span data-stu-id="b0c27-131">Edit</span></span>

<span data-ttu-id="b0c27-132">グリッドからチームを選択し、[**編集**] ボタンを選択することによって、グループおよびチーム固有の設定を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="b0c27-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![チームの編集](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="b0c27-134">チーム プロフィール</span><span class="sxs-lookup"><span data-stu-id="b0c27-134">Team profile</span></span>

<span data-ttu-id="b0c27-135">メインのチームの概要グリッドから、チーム名をクリックすることによって、任意のチームのチーム プロフィール ページに移動することができます</span><span class="sxs-lookup"><span data-stu-id="b0c27-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="b0c27-136">チーム プロフィール ページには、チームのチャネルと設定に加えて、チーム (およびそれをサポートする Office 365 グループ) に属しているメンバー、所有者、およびゲストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0c27-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="b0c27-137">チーム プロフィール ページから、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b0c27-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="b0c27-138">メンバーおよび所有者の追加または削除。</span><span class="sxs-lookup"><span data-stu-id="b0c27-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="b0c27-139">チャネルの追加または削除 (全般チャネルを削除することはできません)</span><span class="sxs-lookup"><span data-stu-id="b0c27-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="b0c27-140">チームおよびグループの設定の更新。</span><span class="sxs-lookup"><span data-stu-id="b0c27-140">Update team and group settings.</span></span>
 
![チーム プロフィール](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="b0c27-142">チームに対する変更</span><span class="sxs-lookup"><span data-stu-id="b0c27-142">Making changes to teams</span></span>

<span data-ttu-id="b0c27-143">チームの次の要素を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b0c27-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="b0c27-144">**チーム内のユーザー** - メンバーの追加や削除、昇格または降格を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b0c27-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="b0c27-145">**チャネル** - 新しいチャネルを追加したり既存のチャネルを削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b0c27-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="b0c27-146">既定の「全般」チャネルを削除することはできません。作成したチャネルについては、チャネル名のみを編集することができます。説明を編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="b0c27-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="b0c27-147">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="b0c27-147">**Team name**</span></span>
- <span data-ttu-id="b0c27-148">**チームの説明**</span><span class="sxs-lookup"><span data-stu-id="b0c27-148">**Team description**</span></span>
- <span data-ttu-id="b0c27-149">**チームのプライバシー** - パブリックまたはプライベート</span><span class="sxs-lookup"><span data-stu-id="b0c27-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="b0c27-150">**チームの分類** - 自分の Office 365 グループの分類に基づきます</span><span class="sxs-lookup"><span data-stu-id="b0c27-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="b0c27-151">**チーム メンバーの設定** - チーム メンバーの設定を選択します</span><span class="sxs-lookup"><span data-stu-id="b0c27-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="b0c27-152">その他サポートされているチームへの変更</span><span class="sxs-lookup"><span data-stu-id="b0c27-152">Other supported changes to teams</span></span>

- <span data-ttu-id="b0c27-153">**削除** - チームとそれに対応する Office 365 グループを論理的に削除します。</span><span class="sxs-lookup"><span data-stu-id="b0c27-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="b0c27-154">誤って削除したチームを復元するには、[削除した Office 365 グループの復元](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide) の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b0c27-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="b0c27-155">**アーカイブ** - Microsoft Teams 内での読み取り専用モードに、チームをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="b0c27-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="b0c27-156">管理者は管理ポータルを通じ、組織を代表してチームを アーカイブしたりアーカイブを解除したりできます。</span><span class="sxs-lookup"><span data-stu-id="b0c27-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="b0c27-157">チームに対して行う変更はログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="b0c27-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="b0c27-158">グループ設定 (名前、説明、写真、プライバシー、分類、またはチーム メンバー) を変更する場合、これらの変更は監査パイプラインを通して自分自身によるものとされます。</span><span class="sxs-lookup"><span data-stu-id="b0c27-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="b0c27-159">Teams 固有の設定に対するアクションを実行している場合、自分による変更は、チームの全般チャネル内で記録され、自分自身によるものとされます。</span><span class="sxs-lookup"><span data-stu-id="b0c27-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b0c27-160">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b0c27-160">Troubleshooting</span></span>

<span data-ttu-id="b0c27-161">**問題: チームがチームの概要リストに表示されません。**</span><span class="sxs-lookup"><span data-stu-id="b0c27-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="b0c27-162">Microsoft Teams の管理センターに入ると、**チーム**のオプションの下にあるチームの概要リストに、一部のチームの一部が表示されません。</span><span class="sxs-lookup"><span data-stu-id="b0c27-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="b0c27-163">**原因**: この問題は、チームがシステムによって適切に（もしくはまだ）プロファイルされていない場合、 システムが認識するためのプロパティが見つからないために起こります。</span><span class="sxs-lookup"><span data-stu-id="b0c27-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="b0c27-164">**解決方法: MS Graph でプロパティを適切な値に手動で設定します。**</span><span class="sxs-lookup"><span data-stu-id="b0c27-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="b0c27-165">Exchange Online powershell を通じて取得できる問題のグループ ID のクエリで、 **"[Get-unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** コマンドレットと、"**ExternalDirectoryObjectId**"属性を使って **{グループ id}** を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="b0c27-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="b0c27-166">[Graph エクスプローラー](https://developer.microsoft.com/ja-JP/graph/graph-explorer)にアクセスします</span><span class="sxs-lookup"><span data-stu-id="b0c27-166">Access [Graph Explorer](https://developer.microsoft.com/ja-JP/graph/graph-explorer)</span></span>

2. <span data-ttu-id="b0c27-167">左側のメニューで、Graph エクスプ ローラーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="b0c27-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="b0c27-168">クエリの行を変更: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="b0c27-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="b0c27-169">リクエストの本文に、次の値を追加: {"resourceProvisioningOptions": ["Team"]}</span><span class="sxs-lookup"><span data-stu-id="b0c27-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="b0c27-170">右上のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0c27-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="b0c27-171">Microsoft Teams 管理センター - チームの概要のページで、チームが正しく表示されているか確認します。</span><span class="sxs-lookup"><span data-stu-id="b0c27-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="b0c27-172">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b0c27-172">Learn more</span></span>

[<span data-ttu-id="b0c27-173">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="b0c27-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="b0c27-174">Microsoft Teams の管理者ロール</span><span class="sxs-lookup"><span data-stu-id="b0c27-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

