---
title: Microsoft Teams で役割と権限を割り当てる
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: チームを作成する権限など、Microsoft Teams でチーム所有者やメンバーに役割と権限を割り当る方法について説明します。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0c0e64dc4a112c6f2c9ded4c68b45eb0740b5f3
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="f9b72-103">Microsoft Teams で役割と権限を割り当てる</span><span class="sxs-lookup"><span data-stu-id="f9b72-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f9b72-p101">Microsoft Teams には、**所有者**と**メンバー**の 2 つの役割があります。既定では、新しいチームを作成するユーザーに所有者の状態が付与されます。既存の Office 365 グループからチームを作成する場合は、そのグループの権限が継承されます。</span><span class="sxs-lookup"><span data-stu-id="f9b72-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="f9b72-107">所有者とメンバーの権限の違いを以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="f9b72-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="f9b72-108">チーム所有者</span><span class="sxs-lookup"><span data-stu-id="f9b72-108">Team Owner</span></span>  |<span data-ttu-id="f9b72-109">チーム メンバー</span><span class="sxs-lookup"><span data-stu-id="f9b72-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f9b72-110">**チームの作成**</span><span class="sxs-lookup"><span data-stu-id="f9b72-110">**Create team**</span></span>     |<span data-ttu-id="f9b72-111">はい</span><span class="sxs-lookup"><span data-stu-id="f9b72-111">Yes</span></span>        |<span data-ttu-id="f9b72-112">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9b72-112">No</span></span>         |
|<span data-ttu-id="f9b72-113">**チームを抜ける**</span><span class="sxs-lookup"><span data-stu-id="f9b72-113">**Leave team**</span></span>     |<span data-ttu-id="f9b72-114">はい</span><span class="sxs-lookup"><span data-stu-id="f9b72-114">Yes</span></span>         |<span data-ttu-id="f9b72-115">はい</span><span class="sxs-lookup"><span data-stu-id="f9b72-115">Yes</span></span>         |
|<span data-ttu-id="f9b72-116">**チーム名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="f9b72-116">**Edit team name/description**</span></span>      |<span data-ttu-id="f9b72-117">はい</span><span class="sxs-lookup"><span data-stu-id="f9b72-117">Yes</span></span>         |<span data-ttu-id="f9b72-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9b72-118">No</span></span>         |
|<span data-ttu-id="f9b72-119">**チームの削除**</span><span class="sxs-lookup"><span data-stu-id="f9b72-119">**Delete team**</span></span>      |<span data-ttu-id="f9b72-120">はい</span><span class="sxs-lookup"><span data-stu-id="f9b72-120">Yes</span></span>         |<span data-ttu-id="f9b72-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9b72-121">No</span></span>         |
|<span data-ttu-id="f9b72-122">**チャネルの追加**</span><span class="sxs-lookup"><span data-stu-id="f9b72-122">**Add channel**</span></span>      |<span data-ttu-id="f9b72-123">はい</span><span class="sxs-lookup"><span data-stu-id="f9b72-123">Yes</span></span>         |<span data-ttu-id="f9b72-124">はい\*</span><span class="sxs-lookup"><span data-stu-id="f9b72-124">Yes\*</span></span>         |
|<span data-ttu-id="f9b72-125">**チャネル名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="f9b72-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="f9b72-126">はい</span><span class="sxs-lookup"><span data-stu-id="f9b72-126">Yes</span></span>         |<span data-ttu-id="f9b72-127">はい\*</span><span class="sxs-lookup"><span data-stu-id="f9b72-127">Yes\*</span></span>         |
|<span data-ttu-id="f9b72-128">**チャネルの削除**</span><span class="sxs-lookup"><span data-stu-id="f9b72-128">**Delete channel**</span></span>      |<span data-ttu-id="f9b72-129">はい</span><span class="sxs-lookup"><span data-stu-id="f9b72-129">Yes</span></span>         |<span data-ttu-id="f9b72-130">はい\*</span><span class="sxs-lookup"><span data-stu-id="f9b72-130">Yes\*</span></span>         |
|<span data-ttu-id="f9b72-131">**メンバーの追加**</span><span class="sxs-lookup"><span data-stu-id="f9b72-131">**Add members**</span></span>      |<span data-ttu-id="f9b72-132">はい**</span><span class="sxs-lookup"><span data-stu-id="f9b72-132">Yes**</span></span>         |<span data-ttu-id="f9b72-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9b72-133">No</span></span>         |
|<span data-ttu-id="f9b72-134">**タブの追加**</span><span class="sxs-lookup"><span data-stu-id="f9b72-134">**Add tabs**</span></span>      |<span data-ttu-id="f9b72-135">はい</span><span class="sxs-lookup"><span data-stu-id="f9b72-135">Yes</span></span>         |<span data-ttu-id="f9b72-136">はい\*</span><span class="sxs-lookup"><span data-stu-id="f9b72-136">Yes\*</span></span>         |
|<span data-ttu-id="f9b72-137">**コネクタの追加**</span><span class="sxs-lookup"><span data-stu-id="f9b72-137">**Add connectors**</span></span>      |<span data-ttu-id="f9b72-138">はい</span><span class="sxs-lookup"><span data-stu-id="f9b72-138">Yes</span></span>         |<span data-ttu-id="f9b72-139">はい\*</span><span class="sxs-lookup"><span data-stu-id="f9b72-139">Yes\*</span></span>         |
|<span data-ttu-id="f9b72-140">**ボットの追加**</span><span class="sxs-lookup"><span data-stu-id="f9b72-140">**Add bots**</span></span>      |<span data-ttu-id="f9b72-141">はい</span><span class="sxs-lookup"><span data-stu-id="f9b72-141">Yes</span></span>         |<span data-ttu-id="f9b72-142">はい\*</span><span class="sxs-lookup"><span data-stu-id="f9b72-142">Yes\*</span></span>         |
<span data-ttu-id="f9b72-143">\* 所有者はこれらの項目をチーム レベルでオフにできます。その場合、メンバーは項目にアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="f9b72-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="f9b72-p102">\*\*チームへのメンバーの追加後、所有者はメンバーを所有者の状態に昇格させることもできます。また、所有者は自分のステータスをメンバーに降格させることもできます。</span><span class="sxs-lookup"><span data-stu-id="f9b72-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="f9b72-146">所有者は [チームの表示] オプションでメンバーを所有者に昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="f9b72-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="f9b72-147">1 つのチームで最大 100 人の所有者を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="f9b72-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="f9b72-148">チームを管理しやすくするために、複数名の所有者を含めることをお勧めします。所有者が 1 人だけの場合、その所有者が組織からいなくなると、グループが孤立した状態になってしまいます。複数の所有者がいれば、これを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="f9b72-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="f9b72-149">孤立したグループの詳細については、「[孤立したグループに新しい所有者を割り当てる](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9b72-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="f9b72-150">チームを作成するためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f9b72-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="f9b72-p104">既定により、Exchange Online のメールボックスを持つすべてのユーザーは Office 365 グループを作成するための権限を持つため、Microsoft Teams でもチームを作成することができます。作成と管理の権限を特定のユーザーに付与することで、新規チームの作成、すなわち新規 Office 365 グループの作成をより厳しく制御、制限することができます。</span><span class="sxs-lookup"><span data-stu-id="f9b72-p104">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams. You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span>

<span data-ttu-id="f9b72-153">組織でこの制限を実施する場合は、そのために必要な以下のタスクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9b72-153">If your organization is interested in doing this, the instructions below outlines the tasks required to do so.</span></span>

1.  <span data-ttu-id="f9b72-154">Office 365 グループを作成するための権限を他のユーザーに付与するセキュリティ グループ (SG) を特定または作成します。</span><span class="sxs-lookup"><span data-stu-id="f9b72-154">Identify or create a security group (SG) of users who will have delegated permissions to create Office 365 groups.</span></span>

    <span data-ttu-id="f9b72-p105">a.  **アクション:** Office 365 でセキュリティ グループを設定し、Office 365 グループを作成できるユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f9b72-p105">a.  **Action:** Set up a security group in Office 365 so you can add your users who can create Office 365 groups.</span></span>

    <span data-ttu-id="f9b72-p106">b.  詳しくは、「[作成、編集、または Office 365 管理センターでセキュリティ グループを削除します。](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9b72-p106">b.  For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>

2.  <span data-ttu-id="f9b72-159">会社全体で、グループを作成するユーザーが制御されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9b72-159">Verify that the company-wide control for users to create groups is enabled.</span></span>

    <span data-ttu-id="f9b72-p107">a.  **アクション:** 次の PowerShell スクリプトを実行し、UsersPermissiontoCreateGroupsEnabled パラメーターが **True** であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9b72-p107">a.  **Action:** Run the following PowerShell script and verify UsersPermissiontoCreateGroupsEnabled parameter is set to **True.**</span></span>

    ```
    Connect-MsolService

    Get-MsolCompanyInformation
    ```

    <span data-ttu-id="f9b72-162">b.</span><span class="sxs-lookup"><span data-stu-id="f9b72-162">b.</span></span>  <span data-ttu-id="f9b72-163">True でない場合は、Set-MsolCompanySettings コマンドレットを実行して **True に設定**します。</span><span class="sxs-lookup"><span data-stu-id="f9b72-163">If this is not true, run the Set-MsolCompanySettings  cmdlet **to set it to True**.</span></span>
<span data-ttu-id="f9b72-164">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span><span class="sxs-lookup"><span data-stu-id="f9b72-164">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span></span>

    <span data-ttu-id="f9b72-p109">c. 詳細については、「[Office 365 グループの作成を管理する](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9b72-p109">c. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span></span>

3.  <span data-ttu-id="f9b72-167">特定したセキュリティ グループのみにグループ作成の権限を許可するように Office 365 グループの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f9b72-167">Configure Office 365 Group settings to allow only identified security group has permissions to create groups</span></span>

    <span data-ttu-id="f9b72-p110">a.  **アクション:** グループ作成の権限を割り当てるグループの構成を含むグループ設定オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9b72-p110">a.  **Action:** Create a group settings object that contains the configuration settings of the group that will be assigned delegated permissions to create groups.</span></span> 

    ```
    Connect-AzureAD

    $Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b

    $Setting = $template.CreateDirectorySetting()

    $setting["EnableGroupCreation"] = "true"

    $setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"

    New-AzureADDirectorySetting -DirectorySetting $settings
    ```

    <span data-ttu-id="f9b72-170">b.</span><span class="sxs-lookup"><span data-stu-id="f9b72-170">b.</span></span> <span data-ttu-id="f9b72-171">詳細については、「[Office 365 グループの作成を管理する](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9b72-171">For more information, see: [Manage Office 365 Group Creation](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3).</span></span>


||||
|---------|---------|---------|
| ![判断ポイント アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="f9b72-173">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="f9b72-173">Decision Point</span></span>         |<span data-ttu-id="f9b72-174">Microsoft Teams のすべてのユーザーがチームを作成できますか (作成できることを推奨)?</span><span class="sxs-lookup"><span data-stu-id="f9b72-174">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![次のステップ アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="f9b72-176">次のステップ</span><span class="sxs-lookup"><span data-stu-id="f9b72-176">Next Steps</span></span>         |<span data-ttu-id="f9b72-177">チームを作成できるユーザーを制限する場合は、Office 365 グループの既定の作成権限を変更します。</span><span class="sxs-lookup"><span data-stu-id="f9b72-177">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
