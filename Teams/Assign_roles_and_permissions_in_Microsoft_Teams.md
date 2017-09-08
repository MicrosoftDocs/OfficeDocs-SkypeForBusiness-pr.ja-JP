---
title: "Microsoft Teams で役割と権限を割り当てる | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: solution
ms.prod: teams
description: "チームを作成する権限など、Microsoft Teams でチーム所有者やメンバーに役割と権限を割り当る方法について説明します。"
ms.openlocfilehash: 9367148bb98e5b36f43c512e4955827a63fc8863
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="17368-103">Microsoft Teams で役割と権限を割り当てる</span><span class="sxs-lookup"><span data-stu-id="17368-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

<span data-ttu-id="17368-p101">Microsoft Teams には、**所有者**と**メンバー**の 2 つの役割があります。既定では、新しいチームを作成するユーザーに所有者の状態が付与されます。既存の Office 365 グループからチームを作成する場合は、そのグループの権限が継承されます。</span><span class="sxs-lookup"><span data-stu-id="17368-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="17368-107">所有者とメンバーの権限の違いを以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="17368-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="17368-108">チーム所有者</span><span class="sxs-lookup"><span data-stu-id="17368-108">Team Owner</span></span>  |<span data-ttu-id="17368-109">チーム メンバー</span><span class="sxs-lookup"><span data-stu-id="17368-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="17368-110">**チームの作成**</span><span class="sxs-lookup"><span data-stu-id="17368-110">**Create team**</span></span>     |<span data-ttu-id="17368-111">はい</span><span class="sxs-lookup"><span data-stu-id="17368-111">Yes</span></span>        |<span data-ttu-id="17368-112">いいえ</span><span class="sxs-lookup"><span data-stu-id="17368-112">No</span></span>         |
|<span data-ttu-id="17368-113">**チームを抜ける**</span><span class="sxs-lookup"><span data-stu-id="17368-113">**Leave team**</span></span>     |<span data-ttu-id="17368-114">はい</span><span class="sxs-lookup"><span data-stu-id="17368-114">Yes</span></span>         |<span data-ttu-id="17368-115">はい</span><span class="sxs-lookup"><span data-stu-id="17368-115">Yes</span></span>         |
|<span data-ttu-id="17368-116">**チーム名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="17368-116">**Edit team name/description**</span></span>      |<span data-ttu-id="17368-117">はい</span><span class="sxs-lookup"><span data-stu-id="17368-117">Yes</span></span>         |<span data-ttu-id="17368-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="17368-118">No</span></span>         |
|<span data-ttu-id="17368-119">**チームの削除**</span><span class="sxs-lookup"><span data-stu-id="17368-119">**Delete team**</span></span>      |<span data-ttu-id="17368-120">はい</span><span class="sxs-lookup"><span data-stu-id="17368-120">Yes</span></span>         |<span data-ttu-id="17368-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="17368-121">No</span></span>         |
|<span data-ttu-id="17368-122">**チャネルの追加**</span><span class="sxs-lookup"><span data-stu-id="17368-122">**Add channel**</span></span>      |<span data-ttu-id="17368-123">はい</span><span class="sxs-lookup"><span data-stu-id="17368-123">Yes</span></span>         |<span data-ttu-id="17368-124">はい*</span><span class="sxs-lookup"><span data-stu-id="17368-124">Yes*</span></span>         |
|<span data-ttu-id="17368-125">**チャネル名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="17368-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="17368-126">はい</span><span class="sxs-lookup"><span data-stu-id="17368-126">Yes</span></span>         |<span data-ttu-id="17368-127">はい*</span><span class="sxs-lookup"><span data-stu-id="17368-127">Yes*</span></span>         |
|<span data-ttu-id="17368-128">**チャネルの削除**</span><span class="sxs-lookup"><span data-stu-id="17368-128">**Delete channel**</span></span>      |<span data-ttu-id="17368-129">はい</span><span class="sxs-lookup"><span data-stu-id="17368-129">Yes</span></span>         |<span data-ttu-id="17368-130">はい*</span><span class="sxs-lookup"><span data-stu-id="17368-130">Yes*</span></span>         |
|<span data-ttu-id="17368-131">**メンバーの追加**</span><span class="sxs-lookup"><span data-stu-id="17368-131">**Add members**</span></span>      |<span data-ttu-id="17368-132">はい**</span><span class="sxs-lookup"><span data-stu-id="17368-132">Yes</span></span>         |<span data-ttu-id="17368-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="17368-133">No</span></span>         |
|<span data-ttu-id="17368-134">**タブの追加**</span><span class="sxs-lookup"><span data-stu-id="17368-134">**Add tabs**</span></span>      |<span data-ttu-id="17368-135">はい</span><span class="sxs-lookup"><span data-stu-id="17368-135">Yes</span></span>         |<span data-ttu-id="17368-136">はい*</span><span class="sxs-lookup"><span data-stu-id="17368-136">Yes*</span></span>         |
|<span data-ttu-id="17368-137">**コネクタの追加**</span><span class="sxs-lookup"><span data-stu-id="17368-137">**Add connectors**</span></span>      |<span data-ttu-id="17368-138">はい</span><span class="sxs-lookup"><span data-stu-id="17368-138">Yes</span></span>         |<span data-ttu-id="17368-139">はい*</span><span class="sxs-lookup"><span data-stu-id="17368-139">Yes*</span></span>         |
|<span data-ttu-id="17368-140">**ボットの追加**</span><span class="sxs-lookup"><span data-stu-id="17368-140">**Add bots**</span></span>      |<span data-ttu-id="17368-141">はい</span><span class="sxs-lookup"><span data-stu-id="17368-141">Yes</span></span>         |<span data-ttu-id="17368-142">はい*</span><span class="sxs-lookup"><span data-stu-id="17368-142">Yes*</span></span>         |
<span data-ttu-id="17368-143">\* 所有者はこれらの項目をチーム レベルでオフにできます。その場合、メンバーは項目にアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="17368-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="17368-p102">\*\*チームへのメンバーの追加後、所有者はメンバーを所有者の状態に昇格させることもできます。また、所有者は自分のステータスをメンバーに降格させることもできます。</span><span class="sxs-lookup"><span data-stu-id="17368-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>


| | |
|---------|---------|
|![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image1.png) <br></br><span data-ttu-id="17368-146">注意</span><span class="sxs-lookup"><span data-stu-id="17368-146">Note:</span></span>     |<span data-ttu-id="17368-p103">所有者は [チームの表示] オプションでメンバーを所有者に昇格させることができます。1 つのチームあたりの所有者の最大数は 10 人です。</span><span class="sxs-lookup"><span data-stu-id="17368-p103">Owners can make other members owners in the View teams option. A team can have up to 10 owners.</span></span>         |

<a name="permissions-to-create-teams"></a><span data-ttu-id="17368-149">チームを作成するための権限</span><span class="sxs-lookup"><span data-stu-id="17368-149">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="17368-p104">既定により、Exchange Online のメールボックスを持つすべてのユーザーは Office 365 グループを作成するための権限を持つため、Microsoft Teams でもチームを作成することができます。作成と管理の権限を特定のユーザーに付与することで、新規チームの作成、すなわち新規 Office 365 グループの作成をより厳しく制御、制限することができます。</span><span class="sxs-lookup"><span data-stu-id="17368-p104">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams. You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span>

<span data-ttu-id="17368-152">組織でこの制限を実施する場合は、そのために必要な以下のタスクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="17368-152">If your organization is interested in doing this, the instructions below outlines the tasks required to do so.</span></span>

1.  <span data-ttu-id="17368-153">Office 365 グループを作成するための権限を他のユーザーに付与するセキュリティ グループ (SG) を特定または作成します。</span><span class="sxs-lookup"><span data-stu-id="17368-153">Identify or create a security group (SG) of users who will have delegated permissions to create Office 365 groups.</span></span>

    <span data-ttu-id="17368-p105">a.  **アクション:** Office 365 でセキュリティ グループを設定し、Office 365 グループを作成できるユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="17368-p105">a.  **Action:** Set up a security group in Office 365 so you can add your users who can create Office 365 groups.</span></span>

    <span data-ttu-id="17368-p106">b.  詳しくは、「[作成、編集、または Office 365 管理センターでセキュリティ グループを削除します。](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="17368-p106">b.  For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>

2.  <span data-ttu-id="17368-158">会社全体で、グループを作成するユーザーが制御されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="17368-158">Verify that the company-wide control for users to create groups is enabled.</span></span>

    <span data-ttu-id="17368-p107">a.  **アクション:** 次の PowerShell スクリプトを実行し、UsersPermissiontoCreateGroupsEnabled パラメーターが **True** であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="17368-p107">a.  **Action:** Run the following PowerShell script and verify UsersPermissiontoCreateGroupsEnabled parameter is set to **True.**</span></span>

    <span data-ttu-id="17368-161">Connect-MsolService</span><span class="sxs-lookup"><span data-stu-id="17368-161">Connect-MsolService</span></span>

    <span data-ttu-id="17368-162">Get-MsolCompanyInformation</span><span class="sxs-lookup"><span data-stu-id="17368-162">Get-MsolCompanyInformation</span></span>

    <span data-ttu-id="17368-p108">b.  True でない場合は、Set-MsolCompanySettings コマンドレットを実行して **True に設定**します。Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span><span class="sxs-lookup"><span data-stu-id="17368-p108">b.  If this is not true, run the Set-MsolCompanySettings  cmdet **to set it to True**. Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span></span>


    <span data-ttu-id="17368-p109">c. 詳しくは、「[Manage Office 365 Group Creation (Office 365 グループの作成を管理する)](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="17368-p109">c. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span></span>

<!-- -->

3.  <span data-ttu-id="17368-168">特定したセキュリティ グループのみにグループ作成の権限を許可するように Office 365 グループの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="17368-168">Configure Office 365 Group settings to allow only identified security group has permissions to create groups</span></span>

    <span data-ttu-id="17368-p110">a.  **アクション:** グループ作成の権限を割り当てるグループの構成を含むグループ設定オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="17368-p110">a.  **Action:** Create a group settings object that contains the configuration settings of the group that will be assigned delegated permissions to create groups.</span></span> 

    <span data-ttu-id="17368-171">Connect-AzureAD</span><span class="sxs-lookup"><span data-stu-id="17368-171">Connect-AzureAD</span></span>

    <span data-ttu-id="17368-172">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span><span class="sxs-lookup"><span data-stu-id="17368-172">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span></span>

    <span data-ttu-id="17368-173">$Setting = $template.CreateDirectorySetting()</span><span class="sxs-lookup"><span data-stu-id="17368-173">$Setting = $template.CreateDirectorySetting()</span></span>

    <span data-ttu-id="17368-174">$setting["EnableGroupCreation"] = "false"</span><span class="sxs-lookup"><span data-stu-id="17368-174">$setting["EnableGroupCreation"] = "false"</span></span>

    <span data-ttu-id="17368-175">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span><span class="sxs-lookup"><span data-stu-id="17368-175">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span></span>

    <span data-ttu-id="17368-176">New-AzureADDirectorySetting -DirectorySetting $settings</span><span class="sxs-lookup"><span data-stu-id="17368-176">New-AzureADDirectorySetting -DirectorySetting $settings</span></span>

    <span data-ttu-id="17368-p111">b. 詳しくは、「[Manage Office 365 Group Creation (Office 365 グループの作成を管理する)](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="17368-p111">b. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span></span>


||||
|---------|---------|---------|
| ![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="17368-179">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="17368-179">Policy Decision Point</span></span>         |<span data-ttu-id="17368-180">Microsoft Teams のすべてのユーザーがチームを作成できますか (作成できることを推奨)?</span><span class="sxs-lookup"><span data-stu-id="17368-180">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="17368-181">次のステップ</span><span class="sxs-lookup"><span data-stu-id="17368-181">Next Steps</span></span>         |<span data-ttu-id="17368-182">チームを作成できるユーザーを制限する場合は、Office 365 グループの既定の作成権限を変更します。</span><span class="sxs-lookup"><span data-stu-id="17368-182">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |

