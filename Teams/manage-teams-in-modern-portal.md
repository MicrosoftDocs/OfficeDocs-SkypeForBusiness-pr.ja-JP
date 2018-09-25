---
title: マイクロソフトのチームとビジネス管理センターの Skype のチームを管理します。
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: 表示またはマイクロソフトのチームとビジネス管理センターの Skype で、チームを更新する方法について説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1dbfddf2f9cfba12943b8b2e18326de1877e1de3
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018824"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="26a16-103">マイクロソフトのチームとビジネス管理センターの Skype のチームを管理します。</span><span class="sxs-lookup"><span data-stu-id="26a16-103">Manage teams in the Microsoft Teams & Skype for Business Admin Center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="26a16-104">概要</span><span class="sxs-lookup"><span data-stu-id="26a16-104">Overview</span></span>

<span data-ttu-id="26a16-105">IT 管理者としては、表示または更新を組織が共同作業、またはを設定する各チームは、所有者のいないチームの所有者の割り当てなどの修復アクションを実行する必要がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="26a16-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="26a16-106">ビジネス管理センターの Microsoft チームの PowerShell モジュールおよびマイクロソフトのチームと Skype 経由で使用するチームを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="26a16-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="26a16-107">これら 2 つのツールセットを使用して、完全な管理機能には、次の役割の 1 つを割り当てられていることを確認の操作をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="26a16-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="26a16-108">グローバル ・ アドミニストレーター</span><span class="sxs-lookup"><span data-stu-id="26a16-108">Global Administrator</span></span>
- <span data-ttu-id="26a16-109">チーム サービス管理者</span><span class="sxs-lookup"><span data-stu-id="26a16-109">Teams Service Administrator</span></span>

<span data-ttu-id="26a16-110">マイクロソフトのチームでの管理者の役割に関する詳細については、[ここでは](using-admin-roles.md)、詳細情報を参照および[コマンドレットのリファレンスをマイクロソフトのチーム](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)のチームを管理するための PowerShell コマンドレットを使用する方法について。</span><span class="sxs-lookup"><span data-stu-id="26a16-110">You can learn more about admin roles in Microsoft Teams [here](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="26a16-111">この資料では、マイクロソフトのチームとビジネス管理センターの Skype でのチームの管理ツールの概要について説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="26a16-111">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="26a16-112">チーム概要グリッド</span><span class="sxs-lookup"><span data-stu-id="26a16-112">Teams overview grid</span></span>

<span data-ttu-id="26a16-113">チームの管理ツールは、マイクロソフトのチームと Skype ビジネス管理センターの [**チーム**] ノードの下。</span><span class="sxs-lookup"><span data-stu-id="26a16-113">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="26a16-114">(管理センターで、**チーム**を選択します > **チームを管理**します)。各チームは、Office 365 のグループでバックアップし、チームが有効になっている組織で Microsoft をされているすべてのグループをこのノードで表示します。</span><span class="sxs-lookup"><span data-stu-id="26a16-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of all groups that have been Microsoft Teams-enabled in your organization.</span></span>

![チーム概要グリッド](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="26a16-116">グリッドには、次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="26a16-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="26a16-117">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="26a16-117">**Team name**</span></span>
- <span data-ttu-id="26a16-118">**チャネル**の既定の一般的なチャネルを含む、チーム内のすべてのチャネルの数です。</span><span class="sxs-lookup"><span data-stu-id="26a16-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="26a16-119">**ユーザー**の所有者、来園者、および、テナントからのメンバーを含む、総ユーザー数のカウントです。</span><span class="sxs-lookup"><span data-stu-id="26a16-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="26a16-120">**所有者**- このチームの所有者の数です。</span><span class="sxs-lookup"><span data-stu-id="26a16-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="26a16-121">**来園者**がこのチームのメンバーである Azure Active Directory の B2B のゲスト ユーザーの数です。</span><span class="sxs-lookup"><span data-stu-id="26a16-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="26a16-122">**プライバシー** - Office 365 のバックアップ グループの AccessType。</span><span class="sxs-lookup"><span data-stu-id="26a16-122">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="26a16-123">検索</span><span class="sxs-lookup"><span data-stu-id="26a16-123">Search</span></span>

<span data-ttu-id="26a16-124">検索は現在「を開始」の文字列をサポートしていると、**チーム名**フィールドを検索します。</span><span class="sxs-lookup"><span data-stu-id="26a16-124">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="26a16-125">編集</span><span class="sxs-lookup"><span data-stu-id="26a16-125">Edit</span></span>

<span data-ttu-id="26a16-126">グリッドからチームを選択し、[**編集**] ボタンでは、グループとチームに固有の設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="26a16-126">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![チームを編集します。](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="26a16-128">チーム プロファイル</span><span class="sxs-lookup"><span data-stu-id="26a16-128">Team profile</span></span>

<span data-ttu-id="26a16-129">チーム名をクリックすると、チームの主な概要グリッドから任意のチームのチームのプロファイル ページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="26a16-129">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="26a16-130">メンバー、所有者、および来園者のチームに所属するチームのプロファイル ページを示しています (および O365 グループのバックアップを作成)、およびチームのチャネルとの設定。</span><span class="sxs-lookup"><span data-stu-id="26a16-130">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="26a16-131">チームのプロファイル] ページで、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="26a16-131">From the team profile page, you can:</span></span>

- <span data-ttu-id="26a16-132">追加またはメンバーとの所有者を削除します。</span><span class="sxs-lookup"><span data-stu-id="26a16-132">Add or remove members and owners.</span></span>
- <span data-ttu-id="26a16-133">追加またはチャンネル (全般的なチャネルを削除することはできませんに注意してください) を削除します。</span><span class="sxs-lookup"><span data-stu-id="26a16-133">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="26a16-134">チームを更新し、設定をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="26a16-134">Update team and group settings.</span></span>
 
![チーム プロファイル](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="26a16-136">チームを変更をします。</span><span class="sxs-lookup"><span data-stu-id="26a16-136">Making changes to teams</span></span>

<span data-ttu-id="26a16-137">チームの次の要素を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="26a16-137">You can change the following elements of a team:</span></span>
- <span data-ttu-id="26a16-138">**チーム内のユーザー**の追加またはメンバーの削除、および昇格したり、所有者のレベルを下げる</span><span class="sxs-lookup"><span data-stu-id="26a16-138">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="26a16-139">**チャネル**に新しいチャネルを追加または既存のチャンネルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="26a16-139">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="26a16-140">デフォルトの「一般」チャネルを削除することはできませんし、1 回作成するチャネルの名前説明ではないのみを編集できます。</span><span class="sxs-lookup"><span data-stu-id="26a16-140">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="26a16-141">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="26a16-141">**Team name**</span></span>
- <span data-ttu-id="26a16-142">**チームの説明**</span><span class="sxs-lookup"><span data-stu-id="26a16-142">**Team description**</span></span>
- <span data-ttu-id="26a16-143">**チームの写真**</span><span class="sxs-lookup"><span data-stu-id="26a16-143">**Team photo**</span></span>
- <span data-ttu-id="26a16-144">**チームのプライバシー**がパブリックまたはプライベート</span><span class="sxs-lookup"><span data-stu-id="26a16-144">**Team privacy** - public or private</span></span>
- <span data-ttu-id="26a16-145">**チームのクラス分け**に支えられて、Office 365 のグループの分類</span><span class="sxs-lookup"><span data-stu-id="26a16-145">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="26a16-146">**チーム メンバーの設定**の選択のチーム メンバーの設定</span><span class="sxs-lookup"><span data-stu-id="26a16-146">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="26a16-147">チームに加えた変更が記録されます。</span><span class="sxs-lookup"><span data-stu-id="26a16-147">The changes that you make to a team are logged.</span></span> <span data-ttu-id="26a16-148">(名前、説明、写真、プライバシー、分類、またはチーム メンバーを変更する)、グループの設定を変更する場合これらの変更の原因は、監査のパイプラインを通過します。</span><span class="sxs-lookup"><span data-stu-id="26a16-148">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="26a16-149">チームに固有の設定に対するアクションを実行する場合、変更を追跡し、チームの全般的なチャネルの原因です。</span><span class="sxs-lookup"><span data-stu-id="26a16-149">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>


## <a name="learn-more"></a><span data-ttu-id="26a16-150">詳細情報</span><span class="sxs-lookup"><span data-stu-id="26a16-150">Learn more</span></span>

[<span data-ttu-id="26a16-151">マイクロソフト チーム コマンドレットのリファレンス</span><span class="sxs-lookup"><span data-stu-id="26a16-151">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="26a16-152">マイクロソフトのチームでの管理者の役割</span><span class="sxs-lookup"><span data-stu-id="26a16-152">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

