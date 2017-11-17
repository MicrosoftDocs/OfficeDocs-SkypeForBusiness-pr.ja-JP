---
title: "Microsoft Teams で役割と権限を割り当てる | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "チームを作成する権限など、Microsoft Teams でチーム所有者やメンバーに役割と権限を割り当る方法について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 9cc8a72cdabacb76638acb689c6622642c524c8e
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2017
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="d2024-103">Microsoft Teams で役割と権限を割り当てる</span><span class="sxs-lookup"><span data-stu-id="d2024-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

<span data-ttu-id="d2024-p101">Microsoft Teams には、**所有者**と**メンバー**の 2 つの役割があります。既定では、新しいチームを作成するユーザーに所有者の状態が付与されます。既存の Office 365 グループからチームを作成する場合は、そのグループの権限が継承されます。</span><span class="sxs-lookup"><span data-stu-id="d2024-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="d2024-107">所有者とメンバーの権限の違いを以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d2024-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="d2024-108">チーム所有者</span><span class="sxs-lookup"><span data-stu-id="d2024-108">Team Owner</span></span>  |<span data-ttu-id="d2024-109">チーム メンバー</span><span class="sxs-lookup"><span data-stu-id="d2024-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="d2024-110">**チームの作成**</span><span class="sxs-lookup"><span data-stu-id="d2024-110">**Create team**</span></span>     |<span data-ttu-id="d2024-111">はい</span><span class="sxs-lookup"><span data-stu-id="d2024-111">Yes</span></span>        |<span data-ttu-id="d2024-112">いいえ</span><span class="sxs-lookup"><span data-stu-id="d2024-112">No</span></span>         |
|<span data-ttu-id="d2024-113">**チームを抜ける**</span><span class="sxs-lookup"><span data-stu-id="d2024-113">**Leave team**</span></span>     |<span data-ttu-id="d2024-114">はい</span><span class="sxs-lookup"><span data-stu-id="d2024-114">Yes</span></span>         |<span data-ttu-id="d2024-115">はい</span><span class="sxs-lookup"><span data-stu-id="d2024-115">Yes</span></span>         |
|<span data-ttu-id="d2024-116">**チーム名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="d2024-116">**Edit team name/description**</span></span>      |<span data-ttu-id="d2024-117">はい</span><span class="sxs-lookup"><span data-stu-id="d2024-117">Yes</span></span>         |<span data-ttu-id="d2024-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="d2024-118">No</span></span>         |
|<span data-ttu-id="d2024-119">**チームの削除**</span><span class="sxs-lookup"><span data-stu-id="d2024-119">**Delete team**</span></span>      |<span data-ttu-id="d2024-120">はい</span><span class="sxs-lookup"><span data-stu-id="d2024-120">Yes</span></span>         |<span data-ttu-id="d2024-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="d2024-121">No</span></span>         |
|<span data-ttu-id="d2024-122">**チャネルの追加**</span><span class="sxs-lookup"><span data-stu-id="d2024-122">**Add channel**</span></span>      |<span data-ttu-id="d2024-123">はい</span><span class="sxs-lookup"><span data-stu-id="d2024-123">Yes</span></span>         |<span data-ttu-id="d2024-124">はい*</span><span class="sxs-lookup"><span data-stu-id="d2024-124">Yes*</span></span>         |
|<span data-ttu-id="d2024-125">**チャネル名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="d2024-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="d2024-126">はい</span><span class="sxs-lookup"><span data-stu-id="d2024-126">Yes</span></span>         |<span data-ttu-id="d2024-127">はい*</span><span class="sxs-lookup"><span data-stu-id="d2024-127">Yes*</span></span>         |
|<span data-ttu-id="d2024-128">**チャネルの削除**</span><span class="sxs-lookup"><span data-stu-id="d2024-128">**Delete channel**</span></span>      |<span data-ttu-id="d2024-129">はい</span><span class="sxs-lookup"><span data-stu-id="d2024-129">Yes</span></span>         |<span data-ttu-id="d2024-130">はい*</span><span class="sxs-lookup"><span data-stu-id="d2024-130">Yes*</span></span>         |
|<span data-ttu-id="d2024-131">**メンバーの追加**</span><span class="sxs-lookup"><span data-stu-id="d2024-131">**Add members**</span></span>      |<span data-ttu-id="d2024-132">はい**</span><span class="sxs-lookup"><span data-stu-id="d2024-132">Yes**</span></span>         |<span data-ttu-id="d2024-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="d2024-133">No</span></span>         |
|<span data-ttu-id="d2024-134">**タブの追加**</span><span class="sxs-lookup"><span data-stu-id="d2024-134">**Add tabs**</span></span>      |<span data-ttu-id="d2024-135">はい</span><span class="sxs-lookup"><span data-stu-id="d2024-135">Yes</span></span>         |<span data-ttu-id="d2024-136">はい*</span><span class="sxs-lookup"><span data-stu-id="d2024-136">Yes*</span></span>         |
|<span data-ttu-id="d2024-137">**コネクタの追加**</span><span class="sxs-lookup"><span data-stu-id="d2024-137">**Add connectors**</span></span>      |<span data-ttu-id="d2024-138">はい</span><span class="sxs-lookup"><span data-stu-id="d2024-138">Yes</span></span>         |<span data-ttu-id="d2024-139">はい*</span><span class="sxs-lookup"><span data-stu-id="d2024-139">Yes*</span></span>         |
|<span data-ttu-id="d2024-140">**ボットの追加**</span><span class="sxs-lookup"><span data-stu-id="d2024-140">**Add bots**</span></span>      |<span data-ttu-id="d2024-141">はい</span><span class="sxs-lookup"><span data-stu-id="d2024-141">Yes</span></span>         |<span data-ttu-id="d2024-142">はい*</span><span class="sxs-lookup"><span data-stu-id="d2024-142">Yes*</span></span>         |
<span data-ttu-id="d2024-143">\* 所有者はこれらの項目をチーム レベルでオフにできます。その場合、メンバーは項目にアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="d2024-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="d2024-p102">\*\*チームへのメンバーの追加後、所有者はメンバーを所有者の状態に昇格させることもできます。また、所有者は自分のステータスをメンバーに降格させることもできます。</span><span class="sxs-lookup"><span data-stu-id="d2024-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>

| | |
|---------|---------|
|![電球アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image1.png) <br></br><span data-ttu-id="d2024-147">注意</span><span class="sxs-lookup"><span data-stu-id="d2024-147">Note</span></span>     |<span data-ttu-id="d2024-p103">所有者は [チームの表示] オプションでメンバーを所有者に昇格させることができます。1 つのチームあたりの所有者の最大数は 10 人です。</span><span class="sxs-lookup"><span data-stu-id="d2024-p103">Owners can make other members owners in the View teams option. A team can have up to 10 owners.</span></span>         |

<a name="permissions-to-create-teams"></a><span data-ttu-id="d2024-150">チームを作成するための権限</span><span class="sxs-lookup"><span data-stu-id="d2024-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="d2024-p104">既定により、Exchange Online のメールボックスを持つすべてのユーザーは Office 365 グループを作成するための権限を持つため、Microsoft Teams でもチームを作成することができます。作成と管理の権限を特定のユーザーに付与することで、新規チームの作成、すなわち新規 Office 365 グループの作成をより厳しく制御、制限することができます。</span><span class="sxs-lookup"><span data-stu-id="d2024-p104">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams. You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span>

<span data-ttu-id="d2024-153">組織でこの制限を実施する場合は、そのために必要な以下のタスクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2024-153">If your organization is interested in doing this, the instructions below outlines the tasks required to do so.</span></span>

1.  <span data-ttu-id="d2024-154">Office 365 グループを作成するための権限を他のユーザーに付与するセキュリティ グループ (SG) を特定または作成します。</span><span class="sxs-lookup"><span data-stu-id="d2024-154">Identify or create a security group (SG) of users who will have delegated permissions to create Office 365 groups.</span></span>

    <span data-ttu-id="d2024-p105">a.  **アクション:** Office 365 でセキュリティ グループを設定し、Office 365 グループを作成できるユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="d2024-p105">a.  **Action:** Set up a security group in Office 365 so you can add your users who can create Office 365 groups.</span></span>

    <span data-ttu-id="d2024-p106">b.  詳しくは、「[作成、編集、または Office 365 管理センターでセキュリティ グループを削除します。](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d2024-p106">b.  For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>

2.  <span data-ttu-id="d2024-159">会社全体で、グループを作成するユーザーが制御されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2024-159">Verify that the company-wide control for users to create groups is enabled.</span></span>

    <span data-ttu-id="d2024-p107">a.  **アクション:** 次の PowerShell スクリプトを実行し、UsersPermissiontoCreateGroupsEnabled パラメーターが **True** であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2024-p107">a.  **Action:** Run the following PowerShell script and verify UsersPermissiontoCreateGroupsEnabled parameter is set to **True.**</span></span>

    <span data-ttu-id="d2024-162">Connect-MsolService</span><span class="sxs-lookup"><span data-stu-id="d2024-162">Connect-MsolService</span></span>

    <span data-ttu-id="d2024-163">Get-MsolCompanyInformation</span><span class="sxs-lookup"><span data-stu-id="d2024-163">Get-MsolCompanyInformation</span></span>

    <span data-ttu-id="d2024-164">b.</span><span class="sxs-lookup"><span data-stu-id="d2024-164">b.</span></span>  <span data-ttu-id="d2024-165">True でない場合は、Set-MsolCompanySettings コマンドレットを実行して **True に設定**します。</span><span class="sxs-lookup"><span data-stu-id="d2024-165">If this is not true, run the Set-MsolCompanySettings  cmdlet **to set it to True**.</span></span>
<span data-ttu-id="d2024-166">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span><span class="sxs-lookup"><span data-stu-id="d2024-166">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span></span>

    <span data-ttu-id="d2024-p109">c. 詳細については、「[Office 365 グループの作成を管理する](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d2024-p109">c. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span></span>

3.  <span data-ttu-id="d2024-169">特定したセキュリティ グループのみにグループ作成の権限を許可するように Office 365 グループの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d2024-169">Configure Office 365 Group settings to allow only identified security group has permissions to create groups</span></span>

    <span data-ttu-id="d2024-p110">a.  **アクション:** グループ作成の権限を割り当てるグループの構成を含むグループ設定オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d2024-p110">a.  **Action:** Create a group settings object that contains the configuration settings of the group that will be assigned delegated permissions to create groups.</span></span> 

    <span data-ttu-id="d2024-172">Connect-AzureAD</span><span class="sxs-lookup"><span data-stu-id="d2024-172">Connect-AzureAD</span></span>

    <span data-ttu-id="d2024-173">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span><span class="sxs-lookup"><span data-stu-id="d2024-173">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span></span>

    <span data-ttu-id="d2024-174">$Setting = $template.CreateDirectorySetting()</span><span class="sxs-lookup"><span data-stu-id="d2024-174">$Setting = $template.CreateDirectorySetting()</span></span>

    <span data-ttu-id="d2024-175">$setting["EnableGroupCreation"] = "false"</span><span class="sxs-lookup"><span data-stu-id="d2024-175">$setting["EnableGroupCreation"] = "false"</span></span>

    <span data-ttu-id="d2024-176">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span><span class="sxs-lookup"><span data-stu-id="d2024-176">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span></span>

    <span data-ttu-id="d2024-177">New-AzureADDirectorySetting -DirectorySetting $settings</span><span class="sxs-lookup"><span data-stu-id="d2024-177">New-AzureADDirectorySetting -DirectorySetting $settings</span></span>

    <span data-ttu-id="d2024-p111">b. 詳細については、「[Manage Office 365 Group Creation (Office 365 グループの作成を管理する)](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d2024-p111">b. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span></span>


||||
|---------|---------|---------|
| ![判断ポイント アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="d2024-181">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="d2024-181">Decision Point</span></span>         |<span data-ttu-id="d2024-182">Microsoft Teams のすべてのユーザーがチームを作成できますか (作成できることを推奨)?</span><span class="sxs-lookup"><span data-stu-id="d2024-182">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![次のステップ アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="d2024-184">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d2024-184">Next Steps</span></span>         |<span data-ttu-id="d2024-185">チームを作成できるユーザーを制限する場合は、Office 365 グループの既定の作成権限を変更します。</span><span class="sxs-lookup"><span data-stu-id="d2024-185">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
