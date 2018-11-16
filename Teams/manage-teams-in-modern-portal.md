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
ms.openlocfilehash: 14ab474289e5a677e1125df7146ba7c5a6fc2ca1
ms.sourcegitcommit: f0dec487e2893a171c7e701bfcf598076f5245b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539058"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="75ec4-103">マイクロソフトのチームとビジネス管理センターの Skype のチームを管理します。</span><span class="sxs-lookup"><span data-stu-id="75ec4-103">Manage teams in the Microsoft Teams & Skype for Business Admin Center</span></span>
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a><span data-ttu-id="75ec4-104">概要</span><span class="sxs-lookup"><span data-stu-id="75ec4-104">Overview</span></span>

<span data-ttu-id="75ec4-105">IT 管理者としては、表示または更新を組織が共同作業、またはを設定する各チームは、所有者のいないチームの所有者の割り当てなどの修復アクションを実行する必要がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="75ec4-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="75ec4-106">ビジネス管理センターの Microsoft チームの PowerShell モジュールおよびマイクロソフトのチームと Skype 経由で使用するチームを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="75ec4-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="75ec4-107">これら 2 つのツールセットを使用して、完全な管理機能には、次の役割の 1 つを割り当てられていることを確認の操作をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="75ec4-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="75ec4-108">グローバル ・ アドミニストレーター</span><span class="sxs-lookup"><span data-stu-id="75ec4-108">Global Administrator</span></span>
- <span data-ttu-id="75ec4-109">Teams サービス管理者</span><span class="sxs-lookup"><span data-stu-id="75ec4-109">Teams Service Administrator</span></span>

<span data-ttu-id="75ec4-110">アカウント管理の製品版のチームのライセンスが割り当てられていることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75ec4-110">You should also make sure that your account has been assigned a non-trial Teams license for management.</span></span> <span data-ttu-id="75ec4-111">既知の問題の一部としてには、管理者の役割が割り当てられている、アカウントが 1 **1 つ**であることを確認の操作をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="75ec4-111">As part of a known issue, you should make sure that your account has only **one** admin role assigned.</span></span>  <span data-ttu-id="75ec4-112">[チームを管理する管理者の役割を使用して、マイクロソフトのチーム](using-admin-roles.md)では、マイクロソフト チームの管理者の役割に関する詳細については、および詳細を確認できる[コマンドレットのリファレンスをマイクロソフトのチーム](https://docs.microsoft.com/powershell/teams/?view=teams-ps)のチームを管理するための PowerShell コマンドレットを使用する方法について。</span><span class="sxs-lookup"><span data-stu-id="75ec4-112">You can learn more about admin roles in Microsoft Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="75ec4-113">この資料では、マイクロソフトのチームとビジネス管理センターの Skype でのチームの管理ツールの概要について説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="75ec4-113">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="75ec4-114">チーム概要グリッド</span><span class="sxs-lookup"><span data-stu-id="75ec4-114">Teams overview grid</span></span>

<span data-ttu-id="75ec4-115">チームの管理ツールは、マイクロソフトのチームと Skype ビジネス管理センターの [**チーム**] ノードの下。</span><span class="sxs-lookup"><span data-stu-id="75ec4-115">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="75ec4-116">(管理センターで、**チーム**を選択します > **チームを管理**します)。各チームは、Office 365 のグループでバックアップし、このノードには、チームが有効になっている組織で Microsoft をされているグループのビューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="75ec4-116">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="75ec4-117">私たちは、バックフィル元のチームがこのビューで表示はことを確認する以前に作成しています。</span><span class="sxs-lookup"><span data-stu-id="75ec4-117">We are in the process of backfilling previously created Teams to ensure that they will show up in this view.</span></span>

![チーム概要グリッド](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="75ec4-119">グリッドには、次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75ec4-119">The grid displays the following properties:</span></span>

- <span data-ttu-id="75ec4-120">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="75ec4-120">**Team name**</span></span>
- <span data-ttu-id="75ec4-121">**チャネル**の既定の一般的なチャネルを含む、チーム内のすべてのチャネルの数です。</span><span class="sxs-lookup"><span data-stu-id="75ec4-121">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="75ec4-122">**ユーザー**の所有者、来園者、および、テナントからのメンバーを含む、総ユーザー数のカウントです。</span><span class="sxs-lookup"><span data-stu-id="75ec4-122">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="75ec4-123">**所有者**- このチームの所有者の数です。</span><span class="sxs-lookup"><span data-stu-id="75ec4-123">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="75ec4-124">**来園者**がこのチームのメンバーである Azure Active Directory の B2B のゲスト ユーザーの数です。</span><span class="sxs-lookup"><span data-stu-id="75ec4-124">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="75ec4-125">**プライバシー** - Office 365 のバックアップ グループの AccessType。</span><span class="sxs-lookup"><span data-stu-id="75ec4-125">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="75ec4-126">検索</span><span class="sxs-lookup"><span data-stu-id="75ec4-126">Search</span></span>

<span data-ttu-id="75ec4-127">検索は現在「を開始」の文字列をサポートしていると、**チーム名**フィールドを検索します。</span><span class="sxs-lookup"><span data-stu-id="75ec4-127">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="75ec4-128">編集</span><span class="sxs-lookup"><span data-stu-id="75ec4-128">Edit</span></span>

<span data-ttu-id="75ec4-129">グリッドからチームを選択し、[**編集**] ボタンでは、グループとチームに固有の設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="75ec4-129">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![チームを編集します。](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="75ec4-131">チーム プロファイル</span><span class="sxs-lookup"><span data-stu-id="75ec4-131">Team profile</span></span>

<span data-ttu-id="75ec4-132">チーム名をクリックすると、チームの主な概要グリッドから任意のチームのチームのプロファイル ページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="75ec4-132">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="75ec4-133">メンバー、所有者、および来園者のチームに所属するチームのプロファイル ページを示しています (および O365 グループのバックアップを作成)、およびチームのチャネルとの設定。</span><span class="sxs-lookup"><span data-stu-id="75ec4-133">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="75ec4-134">チームのプロファイル] ページで、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="75ec4-134">From the team profile page, you can:</span></span>

- <span data-ttu-id="75ec4-135">追加またはメンバーとの所有者を削除します。</span><span class="sxs-lookup"><span data-stu-id="75ec4-135">Add or remove members and owners.</span></span>
- <span data-ttu-id="75ec4-136">追加またはチャンネル (全般的なチャネルを削除することはできませんに注意してください) を削除します。</span><span class="sxs-lookup"><span data-stu-id="75ec4-136">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="75ec4-137">チームを更新し、設定をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="75ec4-137">Update team and group settings.</span></span>
 
![チーム プロファイル](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="75ec4-139">チームを変更をします。</span><span class="sxs-lookup"><span data-stu-id="75ec4-139">Making changes to teams</span></span>

<span data-ttu-id="75ec4-140">チームの次の要素を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="75ec4-140">You can change the following elements of a team:</span></span>
- <span data-ttu-id="75ec4-141">**チーム内のユーザー**の追加またはメンバーの削除、および昇格したり、所有者のレベルを下げる</span><span class="sxs-lookup"><span data-stu-id="75ec4-141">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="75ec4-142">**チャネル**に新しいチャネルを追加または既存のチャンネルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="75ec4-142">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="75ec4-143">デフォルトの「一般」チャネルを削除することはできませんし、1 回作成するチャネルの名前説明ではないのみを編集できます。</span><span class="sxs-lookup"><span data-stu-id="75ec4-143">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="75ec4-144">**チーム名**</span><span class="sxs-lookup"><span data-stu-id="75ec4-144">**Team name**</span></span>
- <span data-ttu-id="75ec4-145">**チームの説明**</span><span class="sxs-lookup"><span data-stu-id="75ec4-145">**Team description**</span></span>
- <span data-ttu-id="75ec4-146">**チームのプライバシー**がパブリックまたはプライベート</span><span class="sxs-lookup"><span data-stu-id="75ec4-146">**Team privacy** - public or private</span></span>
- <span data-ttu-id="75ec4-147">**チームのクラス分け**に支えられて、Office 365 のグループの分類</span><span class="sxs-lookup"><span data-stu-id="75ec4-147">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="75ec4-148">**チーム メンバーの設定**の選択のチーム メンバーの設定</span><span class="sxs-lookup"><span data-stu-id="75ec4-148">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="75ec4-149">チームに加えた変更が記録されます。</span><span class="sxs-lookup"><span data-stu-id="75ec4-149">The changes that you make to a team are logged.</span></span> <span data-ttu-id="75ec4-150">(名前、説明、写真、プライバシー、分類、またはチーム メンバーを変更する)、グループの設定を変更する場合これらの変更の原因は、監査のパイプラインを通過します。</span><span class="sxs-lookup"><span data-stu-id="75ec4-150">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="75ec4-151">チームに固有の設定に対するアクションを実行する場合、変更を追跡し、チームの全般的なチャネルの原因です。</span><span class="sxs-lookup"><span data-stu-id="75ec4-151">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>


## <a name="learn-more"></a><span data-ttu-id="75ec4-152">詳細情報</span><span class="sxs-lookup"><span data-stu-id="75ec4-152">Learn more</span></span>

[<span data-ttu-id="75ec4-153">マイクロソフト チーム コマンドレットのリファレンス</span><span class="sxs-lookup"><span data-stu-id="75ec4-153">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="75ec4-154">マイクロソフトのチームでの管理者の役割</span><span class="sxs-lookup"><span data-stu-id="75ec4-154">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

