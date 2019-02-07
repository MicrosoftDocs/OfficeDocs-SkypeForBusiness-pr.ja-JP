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
ms.openlocfilehash: 14ab474289e5a677e1125df7146ba7c5a6fc2ca1
ms.sourcegitcommit: f0dec487e2893a171c7e701bfcf598076f5245b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539058"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="1e094-103">Microsoft Teams と Skype for Business の管理センターのチームを管理する</span><span class="sxs-lookup"><span data-stu-id="1e094-103">Manage teams in the Microsoft Teams & Skype for Business Admin Center</span></span>
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a><span data-ttu-id="1e094-104">概要</span><span class="sxs-lookup"><span data-stu-id="1e094-104">Overview</span></span>

<span data-ttu-id="1e094-105">IT 管理者である場合、自分の組織で共同作業のためにセットアップされたチームを表示所有者したり更新したりする必要が発生する可能性があります。また、所有者のいないチームに対して所有者を割り当てるなどの修復アクションを実行する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="1e094-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="1e094-106">Microsoft Teams PowerShell モジュールおよび Microsoft Teams と Skype for Business の管理センターを通して、組織で使用されたチームを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="1e094-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="1e094-107">これらの 2 つのツールセットを使用した完全な管理機能については、次の役割の 1 つが割り当てられることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e094-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="1e094-108">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="1e094-108">Global Administrator</span></span>
- <span data-ttu-id="1e094-109">Teams サービス管理者</span><span class="sxs-lookup"><span data-stu-id="1e094-109">Teams Service Administrator</span></span>

<span data-ttu-id="1e094-110">自分のアカウントに対して、管理のために試用版でない Teams のライセンスが割り当てられていることを確認する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="1e094-110">You should also make sure that your account has been assigned a non-trial Teams license for management.</span></span> <span data-ttu-id="1e094-111">既知の問題に関連して、自分のアカウントに割り当てられている管理者ロールが **1 つ**だけであることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e094-111">As part of a known issue, you should make sure that your account has only **one** admin role assigned.</span></span>  <span data-ttu-id="1e094-112">Microsoft Teams の管理者ロールの詳細については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」をご覧ください。PowerShell コマンドレットの使用方法の詳細については、「[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1e094-112">You can learn more about admin roles in Microsoft Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="1e094-113">この記事では、Microsoft Teams と Skype for Business の管理センターでの管理ツールの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="1e094-113">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="1e094-114">Teams の概要グリッド</span><span class="sxs-lookup"><span data-stu-id="1e094-114">Teams overview grid</span></span>

<span data-ttu-id="1e094-115">チームの管理ツールは、Microsoft Teams と Skype for Business の管理センターの **Teams** ノードの下にあります。</span><span class="sxs-lookup"><span data-stu-id="1e094-115">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="1e094-116">(管理センターでは、[**Teams**] > [**Manage teams (チームの管理)**] を選択します。)各チームは Offfice 365 グループによって支えられていて、このノードは自分の組織内で Microsoft Teams に対応しているグループの表示を提供します。</span><span class="sxs-lookup"><span data-stu-id="1e094-116">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="1e094-117">以前に作成されたチームが、このビューに確実に表示されるようにするための埋め戻し処理を現在行っています。</span><span class="sxs-lookup"><span data-stu-id="1e094-117">We are in the process of backfilling previously created Teams to ensure that they will show up in this view.</span></span>

![Teams の概要グリッド](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="1e094-119">このグリッドには、次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e094-119">The grid displays the following properties:</span></span>

- <span data-ttu-id="1e094-120">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="1e094-120">**Team name**</span></span>
- <span data-ttu-id="1e094-121">**チャネル** - 既定の全般チャネルを含む、チーム内のすべてのチャネルの数。</span><span class="sxs-lookup"><span data-stu-id="1e094-121">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="1e094-122">**ユーザー** - テナントの所有者、ゲスト、およびメンバーを含む合計ユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="1e094-122">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="1e094-123">**所有者** - このチームの所有者の数。</span><span class="sxs-lookup"><span data-stu-id="1e094-123">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="1e094-124">**ゲスト** - このチームのメンバーである、Azure Active Directory B2B ゲスト ユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="1e094-124">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="1e094-125">**プライバシー** - 背後にある Office 365 グループの AccessType </span><span class="sxs-lookup"><span data-stu-id="1e094-125">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="1e094-126">検索</span><span class="sxs-lookup"><span data-stu-id="1e094-126">Search</span></span>

<span data-ttu-id="1e094-127">検索では現在「Begins with (次で始まる)」文字列をサポートされていて、[**Team name (チーム名)**] フィールドの検索を行います。</span><span class="sxs-lookup"><span data-stu-id="1e094-127">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="1e094-128">編集</span><span class="sxs-lookup"><span data-stu-id="1e094-128">Edit</span></span>

<span data-ttu-id="1e094-129">グリッドからチームを選択し、[**編集**] ボタンを選択することによって、グループおよびチーム固有の設定を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="1e094-129">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![チームの編集](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="1e094-131">チーム プロフィール</span><span class="sxs-lookup"><span data-stu-id="1e094-131">Team profile</span></span>

<span data-ttu-id="1e094-132">メインのチームの概要グリッドから、チーム名をクリックすることによって、任意のチームのチーム プロフィール ページに移動することができます</span><span class="sxs-lookup"><span data-stu-id="1e094-132">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="1e094-133">チーム プロフィール ページには、チームのチャネルと設定に加えて、チーム (およびそれをサポートする Office 365 グループ) に属しているメンバー、所有者、およびゲストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e094-133">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="1e094-134">チーム プロフィール ページから、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1e094-134">From the team profile page, you can:</span></span>

- <span data-ttu-id="1e094-135">メンバーおよび所有者の追加または削除。</span><span class="sxs-lookup"><span data-stu-id="1e094-135">Add or remove members and owners.</span></span>
- <span data-ttu-id="1e094-136">チャネルの追加または削除 (全般チャネルを削除することはできません)</span><span class="sxs-lookup"><span data-stu-id="1e094-136">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="1e094-137">チームおよびグループの設定の更新。</span><span class="sxs-lookup"><span data-stu-id="1e094-137">Update team and group settings.</span></span>
 
![チーム プロフィール](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="1e094-139">チームに対する変更</span><span class="sxs-lookup"><span data-stu-id="1e094-139">Making changes to teams</span></span>

<span data-ttu-id="1e094-140">チームの次の要素を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="1e094-140">You can change the following elements of a team:</span></span>
- <span data-ttu-id="1e094-141">**チーム内のユーザー** - メンバーの追加や削除、昇格または降格を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1e094-141">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="1e094-142">**チャネル** - 新しいチャネルを追加したり既存のチャネルを削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="1e094-142">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="1e094-143">既定の「全般」チャネルを削除することはできません。作成したチャネルについては、チャネル名のみを編集することができます。説明を編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="1e094-143">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="1e094-144">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="1e094-144">**Team name**</span></span>
- <span data-ttu-id="1e094-145">**チームの説明**</span><span class="sxs-lookup"><span data-stu-id="1e094-145">**Team description**</span></span>
- <span data-ttu-id="1e094-146">**チームのプライバシー** - パブリックまたはプライベート</span><span class="sxs-lookup"><span data-stu-id="1e094-146">**Team privacy** - public or private</span></span>
- <span data-ttu-id="1e094-147">**チームの分類** - 自分の Office 365 グループの分類に基づきます</span><span class="sxs-lookup"><span data-stu-id="1e094-147">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="1e094-148">**チーム メンバーの設定** - チーム メンバーの設定を選択します</span><span class="sxs-lookup"><span data-stu-id="1e094-148">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="1e094-149">チームに対して行う変更はログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="1e094-149">The changes that you make to a team are logged.</span></span> <span data-ttu-id="1e094-150">グループ設定 (名前、説明、写真、プライバシー、分類、またはチーム メンバー) を変更する場合、これらの変更は監査パイプラインを通して自分自身によるものとされます。</span><span class="sxs-lookup"><span data-stu-id="1e094-150">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="1e094-151">Teams 固有の設定に対するアクションを実行している場合、自分による変更は、チームの全般チャネル内で記録され、自分自身によるものとされます。</span><span class="sxs-lookup"><span data-stu-id="1e094-151">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>


## <a name="learn-more"></a><span data-ttu-id="1e094-152">詳細情報</span><span class="sxs-lookup"><span data-stu-id="1e094-152">Learn more</span></span>

[<span data-ttu-id="1e094-153">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="1e094-153">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="1e094-154">Microsoft Teams の管理者ロール</span><span class="sxs-lookup"><span data-stu-id="1e094-154">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

