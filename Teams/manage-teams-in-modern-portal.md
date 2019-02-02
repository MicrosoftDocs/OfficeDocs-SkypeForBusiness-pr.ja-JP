---
title: Microsoft Teams と Skype for Business の管理センターのチームを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Microsoft Teams と Skype for Business の管理センターで自分のチームの表示や更新を行う方法を説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: df8e60f8a5d7aaf2638e1220baf1c41a59075ae0
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706443"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="2dc70-103">Microsoft Teams と Skype for Business の管理センターのチームを管理する</span><span class="sxs-lookup"><span data-stu-id="2dc70-103">Manage teams in the Microsoft Teams & Skype for Business Admin Center</span></span>
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a><span data-ttu-id="2dc70-104">概要</span><span class="sxs-lookup"><span data-stu-id="2dc70-104">Overview</span></span>

<span data-ttu-id="2dc70-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span><span class="sxs-lookup"><span data-stu-id="2dc70-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="2dc70-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="2dc70-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="2dc70-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span><span class="sxs-lookup"><span data-stu-id="2dc70-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="2dc70-108">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="2dc70-108">Global Administrator</span></span>
- <span data-ttu-id="2dc70-109">Teams サービス管理者</span><span class="sxs-lookup"><span data-stu-id="2dc70-109">Teams Service Administrator</span></span>

<span data-ttu-id="2dc70-110">You should also make sure that your account has been assigned a non-trial Teams license for management.</span><span class="sxs-lookup"><span data-stu-id="2dc70-110">You should also make sure that your account has been assigned a non-trial Teams license for management.</span></span> <span data-ttu-id="2dc70-111">As part of a known issue, you should make sure that your account has only **one** admin role assigned.</span><span class="sxs-lookup"><span data-stu-id="2dc70-111">As part of a known issue, you should make sure that your account has only **one** admin role assigned.</span></span>  <span data-ttu-id="2dc70-112">You can learn more about admin roles in Microsoft Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="2dc70-112">You can learn more about admin roles in Microsoft Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="2dc70-113">この記事では、Microsoft Teams と Skype for Business の管理センターでの管理ツールの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="2dc70-113">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="2dc70-114">Teams の概要グリッド</span><span class="sxs-lookup"><span data-stu-id="2dc70-114">Teams overview grid</span></span>

<span data-ttu-id="2dc70-115">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="2dc70-115">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="2dc70-116">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span><span class="sxs-lookup"><span data-stu-id="2dc70-116">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="2dc70-117">以前に作成されたチームが、このビューに確実に表示されるようにするための埋め戻し処理を現在行っています。</span><span class="sxs-lookup"><span data-stu-id="2dc70-117">We are in the process of backfilling previously created Teams to ensure that they will show up in this view.</span></span>

![Teams の概要グリッド](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="2dc70-119">このグリッドには、次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2dc70-119">The grid displays the following properties:</span></span>

- <span data-ttu-id="2dc70-120">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="2dc70-120">**Team name**</span></span>
- <span data-ttu-id="2dc70-121">**チャネル** - 既定の全般チャネルを含む、チーム内のすべてのチャネルの数。</span><span class="sxs-lookup"><span data-stu-id="2dc70-121">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="2dc70-122">**ユーザー** - テナントの所有者、ゲスト、およびメンバーを含む合計ユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="2dc70-122">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="2dc70-123">**所有者** - このチームの所有者の数。</span><span class="sxs-lookup"><span data-stu-id="2dc70-123">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="2dc70-124">**ゲスト** - このチームのメンバーである、Azure Active Directory B2B ゲスト ユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="2dc70-124">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="2dc70-125">**プライバシー** - 背後にある Office 365 グループの AccessType </span><span class="sxs-lookup"><span data-stu-id="2dc70-125">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="2dc70-126">検索</span><span class="sxs-lookup"><span data-stu-id="2dc70-126">Search</span></span>

<span data-ttu-id="2dc70-127">検索では現在「Begins with (次で始まる)」文字列をサポートされていて、[**Team name (チーム名)**] フィールドの検索を行います。</span><span class="sxs-lookup"><span data-stu-id="2dc70-127">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="2dc70-128">編集</span><span class="sxs-lookup"><span data-stu-id="2dc70-128">Edit</span></span>

<span data-ttu-id="2dc70-129">グリッドからチームを選択し、[**編集**] ボタンを選択することによって、グループおよびチーム固有の設定を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="2dc70-129">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![チームの編集](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="2dc70-131">チーム プロフィール</span><span class="sxs-lookup"><span data-stu-id="2dc70-131">Team profile</span></span>

<span data-ttu-id="2dc70-132">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span><span class="sxs-lookup"><span data-stu-id="2dc70-132">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="2dc70-133">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span><span class="sxs-lookup"><span data-stu-id="2dc70-133">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="2dc70-134">From the team profile page, you can:</span><span class="sxs-lookup"><span data-stu-id="2dc70-134">From the team profile page, you can:</span></span>

- <span data-ttu-id="2dc70-135">メンバーおよび所有者の追加または削除。</span><span class="sxs-lookup"><span data-stu-id="2dc70-135">Add or remove members and owners.</span></span>
- <span data-ttu-id="2dc70-136">チャネルの追加または削除 (全般チャネルを削除することはできません)</span><span class="sxs-lookup"><span data-stu-id="2dc70-136">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="2dc70-137">チームおよびグループの設定の更新。</span><span class="sxs-lookup"><span data-stu-id="2dc70-137">Update team and group settings.</span></span>
 
![チーム プロフィール](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="2dc70-139">チームに対する変更</span><span class="sxs-lookup"><span data-stu-id="2dc70-139">Making changes to teams</span></span>

<span data-ttu-id="2dc70-140">チームの次の要素を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="2dc70-140">You can change the following elements of a team:</span></span>
- <span data-ttu-id="2dc70-141">**チーム内のユーザー** - メンバーの追加や削除、昇格または降格を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2dc70-141">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="2dc70-142">**Channels** - you can add new channels or remove existing channels.</span><span class="sxs-lookup"><span data-stu-id="2dc70-142">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="2dc70-143">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span><span class="sxs-lookup"><span data-stu-id="2dc70-143">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="2dc70-144">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="2dc70-144">**Team name**</span></span>
- <span data-ttu-id="2dc70-145">**チームの説明**</span><span class="sxs-lookup"><span data-stu-id="2dc70-145">**Team description**</span></span>
- <span data-ttu-id="2dc70-146">**チームのプライバシー** - パブリックまたはプライベート</span><span class="sxs-lookup"><span data-stu-id="2dc70-146">**Team privacy** - public or private</span></span>
- <span data-ttu-id="2dc70-147">**チームの分類** - 自分の Office 365 グループの分類に基づきます</span><span class="sxs-lookup"><span data-stu-id="2dc70-147">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="2dc70-148">**チーム メンバーの設定** - チーム メンバーの設定を選択します</span><span class="sxs-lookup"><span data-stu-id="2dc70-148">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="2dc70-149">The changes that you make to a team are logged.</span><span class="sxs-lookup"><span data-stu-id="2dc70-149">The changes that you make to a team are logged.</span></span> <span data-ttu-id="2dc70-150">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span><span class="sxs-lookup"><span data-stu-id="2dc70-150">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="2dc70-151">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span><span class="sxs-lookup"><span data-stu-id="2dc70-151">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2dc70-152">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2dc70-152">Troubleshooting</span></span>

<span data-ttu-id="2dc70-153">**問題: チームのチーム概要グリッドに表示されません。**</span><span class="sxs-lookup"><span data-stu-id="2dc70-153">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="2dc70-154">Skype ビジネス管理センターの Microsoft チームの & を入力すると**チーム**のオプション] の下のチームの一部はチーム概要グリッド内の一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="2dc70-154">When you enter the Microsoft Teams & Skype for Business Admin Center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="2dc70-155">**原因**: この問題と、チームが正しくない (まだ) プロファイリングが行われたが認識するために不足しているプロパティにつながることがシステムによって発生します。</span><span class="sxs-lookup"><span data-stu-id="2dc70-155">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="2dc70-156">**解決方法: は、MS グラフを使用して適切な値にプロパティを設定する手動で**</span><span class="sxs-lookup"><span data-stu-id="2dc70-156">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="2dc70-157">**{グループ id}** 問題の実際のグループ Id のクエリで、Exchange Online の powershell を使用して取得することができますを"**ExternalDirectoryObjectId**"属性として **「[Get UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)」** コマンドレットに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2dc70-157">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="2dc70-158">アクセス[グラフのエクスプ ローラー](https://developer.microsoft.com/en-us/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="2dc70-158">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="2dc70-159">メニューの左側にあるグラフのエクスプ ローラーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2dc70-159">Sign in to Graph Explorer on the left-hand side menu</span></span>

3. <span data-ttu-id="2dc70-160">クエリ行を変更: 修正プログラム _gt v1.0 _gthttps://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="2dc70-160">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="2dc70-161">要求の本文に次の値を追加します {"resourceProvisioningOptions": ["チーム"]}。</span><span class="sxs-lookup"><span data-stu-id="2dc70-161">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="2dc70-162">右上でクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="2dc70-162">Run the Query on the Top-Right.</span></span>

6. <span data-ttu-id="2dc70-163">チームの概要をチームは、マイクロソフトのチームの & のビジネス管理センターでは、Skype で正しく表示されるを確認します。</span><span class="sxs-lookup"><span data-stu-id="2dc70-163">Confirm the team appears correctly back on the Microsoft Teams & Skype for Business Admin Center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="2dc70-164">詳細情報</span><span class="sxs-lookup"><span data-stu-id="2dc70-164">Learn more</span></span>

[<span data-ttu-id="2dc70-165">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="2dc70-165">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="2dc70-166">Microsoft Teams の管理者ロール</span><span class="sxs-lookup"><span data-stu-id="2dc70-166">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

