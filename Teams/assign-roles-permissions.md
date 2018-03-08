---
title: "Microsoft チームの役割および権限を割り当てる"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "チームの所有者とメンバーの役割と権限を割り当てるチームを作成するのにはアクセス許可などの Microsoft チームにする方法を学習します。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: ec15844064a88cf1e6aa8af9e510107e342dd369
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="a3204-103">Microsoft チームの役割および権限を割り当てる</span><span class="sxs-lookup"><span data-stu-id="a3204-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

<span data-ttu-id="a3204-p101">Microsoft チーム内では、2 つの役割があります:**所有者**と**メンバー**。既定では、新しいチームを作成したユーザーには、所有者のステータスが与えられます。既存の Office 365 グループからチームを作成すると、権限は継承されます。</span><span class="sxs-lookup"><span data-stu-id="a3204-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="a3204-107">次の表は、所有者とメンバーのアクセス許可の違いを示します。</span><span class="sxs-lookup"><span data-stu-id="a3204-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="a3204-108">チームの所有者</span><span class="sxs-lookup"><span data-stu-id="a3204-108">Team Owner</span></span>  |<span data-ttu-id="a3204-109">チーム メンバー</span><span class="sxs-lookup"><span data-stu-id="a3204-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a3204-110">**チームを作成します。**</span><span class="sxs-lookup"><span data-stu-id="a3204-110">**Create team**</span></span>     |<span data-ttu-id="a3204-111">○</span><span class="sxs-lookup"><span data-stu-id="a3204-111">Yes</span></span>        |<span data-ttu-id="a3204-112">×</span><span class="sxs-lookup"><span data-stu-id="a3204-112">No</span></span>         |
|<span data-ttu-id="a3204-113">**チームのままに**</span><span class="sxs-lookup"><span data-stu-id="a3204-113">**Leave team**</span></span>     |<span data-ttu-id="a3204-114">○</span><span class="sxs-lookup"><span data-stu-id="a3204-114">Yes</span></span>         |<span data-ttu-id="a3204-115">○</span><span class="sxs-lookup"><span data-stu-id="a3204-115">Yes</span></span>         |
|<span data-ttu-id="a3204-116">**チームの名前と説明を編集します。**</span><span class="sxs-lookup"><span data-stu-id="a3204-116">**Edit team name/description**</span></span>      |<span data-ttu-id="a3204-117">○</span><span class="sxs-lookup"><span data-stu-id="a3204-117">Yes</span></span>         |<span data-ttu-id="a3204-118">×</span><span class="sxs-lookup"><span data-stu-id="a3204-118">No</span></span>         |
|<span data-ttu-id="a3204-119">**チームを削除します。**</span><span class="sxs-lookup"><span data-stu-id="a3204-119">**Delete team**</span></span>      |<span data-ttu-id="a3204-120">○</span><span class="sxs-lookup"><span data-stu-id="a3204-120">Yes</span></span>         |<span data-ttu-id="a3204-121">×</span><span class="sxs-lookup"><span data-stu-id="a3204-121">No</span></span>         |
|<span data-ttu-id="a3204-122">**チャンネルを追加します。**</span><span class="sxs-lookup"><span data-stu-id="a3204-122">**Add channel**</span></span>      |<span data-ttu-id="a3204-123">○</span><span class="sxs-lookup"><span data-stu-id="a3204-123">Yes</span></span>         |<span data-ttu-id="a3204-124">○\*</span><span class="sxs-lookup"><span data-stu-id="a3204-124">Yes\*</span></span>         |
|<span data-ttu-id="a3204-125">**チャンネルの名前と説明を編集します。**</span><span class="sxs-lookup"><span data-stu-id="a3204-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="a3204-126">○</span><span class="sxs-lookup"><span data-stu-id="a3204-126">Yes</span></span>         |<span data-ttu-id="a3204-127">○\*</span><span class="sxs-lookup"><span data-stu-id="a3204-127">Yes\*</span></span>         |
|<span data-ttu-id="a3204-128">**チャンネルを削除します。**</span><span class="sxs-lookup"><span data-stu-id="a3204-128">**Delete channel**</span></span>      |<span data-ttu-id="a3204-129">○</span><span class="sxs-lookup"><span data-stu-id="a3204-129">Yes</span></span>         |<span data-ttu-id="a3204-130">○\*</span><span class="sxs-lookup"><span data-stu-id="a3204-130">Yes\*</span></span>         |
|<span data-ttu-id="a3204-131">**メンバーを追加します。**</span><span class="sxs-lookup"><span data-stu-id="a3204-131">**Add members**</span></span>      |<span data-ttu-id="a3204-132">[はい] * *</span><span class="sxs-lookup"><span data-stu-id="a3204-132">Yes**</span></span>         |<span data-ttu-id="a3204-133">×</span><span class="sxs-lookup"><span data-stu-id="a3204-133">No</span></span>         |
|<span data-ttu-id="a3204-134">**タブを追加します。**</span><span class="sxs-lookup"><span data-stu-id="a3204-134">**Add tabs**</span></span>      |<span data-ttu-id="a3204-135">○</span><span class="sxs-lookup"><span data-stu-id="a3204-135">Yes</span></span>         |<span data-ttu-id="a3204-136">○\*</span><span class="sxs-lookup"><span data-stu-id="a3204-136">Yes\*</span></span>         |
|<span data-ttu-id="a3204-137">**コネクタを追加します。**</span><span class="sxs-lookup"><span data-stu-id="a3204-137">**Add connectors**</span></span>      |<span data-ttu-id="a3204-138">○</span><span class="sxs-lookup"><span data-stu-id="a3204-138">Yes</span></span>         |<span data-ttu-id="a3204-139">○\*</span><span class="sxs-lookup"><span data-stu-id="a3204-139">Yes\*</span></span>         |
|<span data-ttu-id="a3204-140">**コンポーネントを追加します。**</span><span class="sxs-lookup"><span data-stu-id="a3204-140">**Add bots**</span></span>      |<span data-ttu-id="a3204-141">○</span><span class="sxs-lookup"><span data-stu-id="a3204-141">Yes</span></span>         |<span data-ttu-id="a3204-142">○\*</span><span class="sxs-lookup"><span data-stu-id="a3204-142">Yes\*</span></span>         |
<span data-ttu-id="a3204-143">\*これらのアイテム オフにできますチーム レベル、所有者によって場合に、メンバーにをへのアクセスはありません。</span><span class="sxs-lookup"><span data-stu-id="a3204-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="a3204-p102">\*\*チームにメンバーを追加した後所有者がメンバーを所有者のステータスに昇格させることもできます。所有者、メンバーに自分のステータスをレベル下げすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a3204-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="a3204-p103">所有者は、チームの表示] オプションで他のメンバーの所有者を作成できます。チーム最大 100 所有者ことができます。チームの管理に役立てる少なくともいくつかの所有者にことをお勧めまた、唯一の所有者が組織を離れる場合は、親グループこれもできなくなります。親グループの詳細については、[親グループに新しい所有者を割り当てる](https://support.office.com/en-us/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3204-p103">Owners can make other members owners in the View teams option. A team can have up to 100 owners. It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization. For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/en-us/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="a3204-150">チームを作成する権限</span><span class="sxs-lookup"><span data-stu-id="a3204-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="a3204-p104">既定では、Exchange Online にメールボックスを持つすべてのユーザーは、Microsoft チーム内ではチームと Office 365 グループを作成するのには権限を持っています。密接に制御でき、グループの作成および複数ユーザーの管理権限を委任することで、新しいチームの作成と Office 365 の新しいグループの作成を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="a3204-p104">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams. You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span>

<span data-ttu-id="a3204-153">組織がこれに関心を持っていない場合のアウトラインは以下の手順、タスクが必要これを行う。</span><span class="sxs-lookup"><span data-stu-id="a3204-153">If your organization is interested in doing this, the instructions below outlines the tasks required to do so.</span></span>

1.  <span data-ttu-id="a3204-154">特定するか、Office 365 グループを作成する権限を委任しているユーザーのセキュリティ グループ (ストレージ ・ グループ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="a3204-154">Identify or create a security group (SG) of users who will have delegated permissions to create Office 365 groups.</span></span>

    <span data-ttu-id="a3204-p105">a:**アクション:** Office 365 グループを作成するユーザーを追加できるように、Office 365 でのセキュリティ グループを設定します。</span><span class="sxs-lookup"><span data-stu-id="a3204-p105">a.  **Action:** Set up a security group in Office 365 so you can add your users who can create Office 365 groups.</span></span>

    <span data-ttu-id="a3204-p106">b. の詳細については、[作成、編集、または Office 365 管理センターでセキュリティ グループを削除する](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3204-p106">b.  For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>

2.  <span data-ttu-id="a3204-159">グループを作成するユーザーの全社的コントロールが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3204-159">Verify that the company-wide control for users to create groups is enabled.</span></span>

    <span data-ttu-id="a3204-p107">a:**アクション:**次の PowerShell スクリプトを実行し、UsersPermissiontoCreateGroupsEnabled パラメーターを設定することを確認**True** 。</span><span class="sxs-lookup"><span data-stu-id="a3204-p107">a.  **Action:** Run the following PowerShell script and verify UsersPermissiontoCreateGroupsEnabled parameter is set to **True.**</span></span>

    <span data-ttu-id="a3204-162">接続 MsolService</span><span class="sxs-lookup"><span data-stu-id="a3204-162">Connect-MsolService</span></span>

    <span data-ttu-id="a3204-163">Get-msolcompanyinformation</span><span class="sxs-lookup"><span data-stu-id="a3204-163">Get-MsolCompanyInformation</span></span>

    <span data-ttu-id="a3204-p108">b. でない場合は true、実行 Set-msolcompanysettings コマンドレット**を True に設定**します。Set-msolcompanysettings-UsersPermissionToCreateGroupsEnabled $True</span><span class="sxs-lookup"><span data-stu-id="a3204-p108">b.  If this is not true, run the Set-MsolCompanySettings  cmdlet **to set it to True**. Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span></span>

    <span data-ttu-id="a3204-p109">c. の詳細についてを参照してください: [Office 365 グループの作成を管理](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings)します。</span><span class="sxs-lookup"><span data-stu-id="a3204-p109">c. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span></span>

3.  <span data-ttu-id="a3204-169">特定のセキュリティ グループのみがグループを作成する権限を許可する Office 365 のグループの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a3204-169">Configure Office 365 Group settings to allow only identified security group has permissions to create groups</span></span>

    <span data-ttu-id="a3204-p110">a:**アクション:**グループを作成するのには、委任されたアクセス許可を設定するグループの設定を含むグループの設定のオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a3204-p110">a.  **Action:** Create a group settings object that contains the configuration settings of the group that will be assigned delegated permissions to create groups.</span></span> 

    <span data-ttu-id="a3204-172">接続 AzureAD</span><span class="sxs-lookup"><span data-stu-id="a3204-172">Connect-AzureAD</span></span>

    <span data-ttu-id="a3204-173">$Template = get AzureADDirectorySettingTemplate-Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span><span class="sxs-lookup"><span data-stu-id="a3204-173">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span></span>

    <span data-ttu-id="a3204-174">$Setting = $template します。CreateDirectorySetting()</span><span class="sxs-lookup"><span data-stu-id="a3204-174">$Setting = $template.CreateDirectorySetting()</span></span>

    <span data-ttu-id="a3204-175">$setting ["EnableGroupCreation"] ="false"</span><span class="sxs-lookup"><span data-stu-id="a3204-175">$setting["EnableGroupCreation"] = "false"</span></span>

    <span data-ttu-id="a3204-176">$setting ["GroupCreationAllowedGroupId"] ="&lt;グループを作成するグループのオブジェクト Id 許可 >"</span><span class="sxs-lookup"><span data-stu-id="a3204-176">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span></span>

    <span data-ttu-id="a3204-177">新しい-AzureADDirectorySetting-DirectorySetting $settings</span><span class="sxs-lookup"><span data-stu-id="a3204-177">New-AzureADDirectorySetting -DirectorySetting $settings</span></span>

    <span data-ttu-id="a3204-p111">b. の詳細についてを参照してください: [Office 365 グループの作成を管理します。](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span><span class="sxs-lookup"><span data-stu-id="a3204-p111">b. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span></span>


||||
|---------|---------|---------|
| ![判断するポイントをタップします。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="a3204-181">判断するポイント</span><span class="sxs-lookup"><span data-stu-id="a3204-181">Decision Point</span></span>         |<span data-ttu-id="a3204-182">Microsoft チームのすべてのユーザーは (推奨) チームを作成できるようになりますか。</span><span class="sxs-lookup"><span data-stu-id="a3204-182">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![次の手順をタップします。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="a3204-184">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a3204-184">Next Steps</span></span>         |<span data-ttu-id="a3204-185">Office 365 のグループを作成するには、チームを作成できるユーザーを制限する必要がある場合の既定の権限を変更します。</span><span class="sxs-lookup"><span data-stu-id="a3204-185">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
