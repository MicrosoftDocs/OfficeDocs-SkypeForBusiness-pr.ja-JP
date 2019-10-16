---
title: Microsoft Teamsでチームをアーカイブまたは削除する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: チームをアーカイブする、または完全に削除する方法について説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82ba160c1b2a36d67d67b69a0d7eb71bdde4c35f
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37515916"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a><span data-ttu-id="43f0e-103">Microsoft Teamsでチームをアーカイブまたは削除する</span><span class="sxs-lookup"><span data-stu-id="43f0e-103">Archive or delete a team in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="43f0e-104">時間の経過と共に、Microsoft Teams で作成されたチームが使用できなくなったり、プロジェクトの終了時にチームをアーカイブまたは削除したりする場合があります。</span><span class="sxs-lookup"><span data-stu-id="43f0e-104">Over time, a team created in Microsoft Teams might fall out of use or you might want to archive or delete a team at the end of a project.</span></span> <span data-ttu-id="43f0e-105">Microsoft Teams の管理者である場合は、この記事に示す手順に従って、不要になったチームをアーカイブまたは削除します。</span><span class="sxs-lookup"><span data-stu-id="43f0e-105">If you're a Microsoft Teams admin, follow the steps in this article to archive or delete a team that's no longer needed.</span></span> <span data-ttu-id="43f0e-106">チームをアーカイブすると、そのチームのすべてのアクティビティは停止されますが、メンバーの追加や削除、ロールの更新を行うことはできますが、チャネル、ファイル、およびチャットでは、すべてのチームアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-106">When you archive a team, all activity for that team ceases, but you can still add or remove members and update roles and you can still view all the team activity in channels, files, and chats.</span></span> <span data-ttu-id="43f0e-107">チームを削除すると、関連付けられたチャネル、ファイル、およびチャットでのチームアクティビティも削除されます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-107">When you delete a team, team activity in associated channels, files, and chats is also deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43f0e-108">アーカイブされたチームを再アクティブ化することはできますが、削除されたチームを直接削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="43f0e-108">Archived teams can be reactivated, but you can’t directly undelete a team that has been deleted.</span></span> <span data-ttu-id="43f0e-109">チームを最初にアーカイブし、チームが不要になったことを確認するまで、削除を延期することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="43f0e-109">Consider archiving the team first, and postpone the deletion until you're sure that you no longer need the team.</span></span>

## <a name="archive-a-team"></a><span data-ttu-id="43f0e-110">チームをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="43f0e-110">Archive a team</span></span>

<span data-ttu-id="43f0e-111">チームをアーカイブするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="43f0e-111">Follow these steps to archive a team.</span></span>

1. <span data-ttu-id="43f0e-112">Microsoft Teams 管理センターで、[**チーム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="43f0e-112">In the Microsoft Teams admin center, select **Teams**.</span></span>
2. <span data-ttu-id="43f0e-113">チーム名をクリックしてチームを選びます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-113">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="43f0e-114">[**アーカイブ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-114">Select **Archive**.</span></span> <span data-ttu-id="43f0e-115">次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-115">The following message will appear.</span></span>

    ![Teams アーカイブメッセージのスクリーンショット](media/teams-archive-message.png)

4. <span data-ttu-id="43f0e-117">チームの SharePoint サイトを読み取り専用にする場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="43f0e-117">If you would like to make the SharePoint site for the team read-only, select the check box.</span></span>
5. <span data-ttu-id="43f0e-118">[**アーカイブ**] を選択して、チームをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="43f0e-118">Select **Archive** to archive the team.</span></span> <span data-ttu-id="43f0e-119">チームの状態は [**アーカイブ**済み」に変わります。</span><span class="sxs-lookup"><span data-stu-id="43f0e-119">The team’s status will change to **Archived**.</span></span>

## <a name="make-an-archived-team-active"></a><span data-ttu-id="43f0e-120">アーカイブしたチームをアクティブにする</span><span class="sxs-lookup"><span data-stu-id="43f0e-120">Make an archived team active</span></span>

<span data-ttu-id="43f0e-121">次の手順に従って、アーカイブされているチームを再度アクティブにします。</span><span class="sxs-lookup"><span data-stu-id="43f0e-121">Follow these steps to make an archived team active again.</span></span>

1. <span data-ttu-id="43f0e-122">Microsoft Teams 管理センターで、[**チーム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="43f0e-122">In the Microsoft Teams admin center, select **Teams**.</span></span>
2. <span data-ttu-id="43f0e-123">チーム名をクリックしてチームを選びます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-123">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="43f0e-124">[**アーカイブ**解除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="43f0e-124">Select **Unarchive**.</span></span> <span data-ttu-id="43f0e-125">チームの状態が [**アクティブ**」に変わります。</span><span class="sxs-lookup"><span data-stu-id="43f0e-125">The team’s status will change to **Active**.</span></span>

## <a name="delete-a-team"></a><span data-ttu-id="43f0e-126">チームを削除する</span><span class="sxs-lookup"><span data-stu-id="43f0e-126">Delete a team</span></span>

<span data-ttu-id="43f0e-127">今後チームが必要とならない場合は、アーカイブするのではなく、削除することができます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-127">If the team will not be required in the future, then you can delete it rather than archiving it.</span></span> <span data-ttu-id="43f0e-128">チームを削除するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="43f0e-128">Follow these steps to delete a team.</span></span>

1.  <span data-ttu-id="43f0e-129">Microsoft Teams 管理センターで、[**チーム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="43f0e-129">In the Microsoft Teams admin center, select **Teams**.</span></span>
2.  <span data-ttu-id="43f0e-130">チーム名をクリックしてチームを選びます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-130">Select a team by clicking the team name.</span></span>
3.  <span data-ttu-id="43f0e-131">[**削除**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-131">Select **Delete**.</span></span> <span data-ttu-id="43f0e-132">確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-132">A confirmation message will appear.</span></span>
4.  <span data-ttu-id="43f0e-133">チームを完全に削除するには、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="43f0e-133">Select **Delete** to permanently delete the team.</span></span>

## <a name="restore-a-deleted-team"></a><span data-ttu-id="43f0e-134">削除されたチームを復元する</span><span class="sxs-lookup"><span data-stu-id="43f0e-134">Restore a deleted team</span></span>

<span data-ttu-id="43f0e-135">チームに関連付けられている Office 365 グループを復元して、削除されたチームを復元するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="43f0e-135">Follow these steps to restore a deleted team by restoring the Office 365 group that's associated with the team.</span></span> <span data-ttu-id="43f0e-136">既定では、削除された Office 365 グループは30日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-136">By default, a deleted Office 365 group is retained for 30 days.</span></span> <span data-ttu-id="43f0e-137">この30日間の期間は、グループを復元できるため、"ソフト削除" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-137">This 30-day period is called "soft-delete" because you can restore the group.</span></span> <span data-ttu-id="43f0e-138">詳細については、「[削除済みの Office 365 グループを復元](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43f0e-138">To learn more, see [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="install-the-azureadpreview-module"></a><span data-ttu-id="43f0e-139">AzureADPreview モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="43f0e-139">Install the AzureADPreview module</span></span>

1. <span data-ttu-id="43f0e-140">管理者として Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-140">Open Windows PowerShell as an admin.</span></span>
2. <span data-ttu-id="43f0e-141">以前のバージョンの AzureADPreview モジュールがインストールされているか、AzureAD モジュールがインストールされている場合は、次のいずれかを実行してアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="43f0e-141">If you have an earlier version of the AzureADPreview module installed or the AzureAD module installed, uninstall it by running one of the following:</span></span>

    ``` 
    Uninstall-Module AzureADPreview
    ```

    ```
    Uninstall-Module AzureAD
    ```
3. <span data-ttu-id="43f0e-142">次を実行して、最新バージョンの AzureADPreview モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="43f0e-142">Install the latest version of the AzureADPreview module by running the following:</span></span>

    ```
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-office-365-group"></a><span data-ttu-id="43f0e-143">削除された Office 365 グループを復元する</span><span class="sxs-lookup"><span data-stu-id="43f0e-143">Restore the deleted Office 365 group</span></span>

1. <span data-ttu-id="43f0e-144">Azure AD に接続するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="43f0e-144">Connect to Azure AD by running the following:</span></span>
    ```
    Connect-AzureAD
    ```
    <span data-ttu-id="43f0e-145">メッセージが表示されたら、管理者アカウントとパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="43f0e-145">When you're prompted, sign in using your admin account and password.</span></span>  
2. <span data-ttu-id="43f0e-146">次を実行すると、30日の保持期間内のすべてのソフト削除された Office 365 グループの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-146">Run the following to display a list of all soft-deleted Office 365 groups that are still within the 30-day retention period.</span></span> <span data-ttu-id="43f0e-147">多数のグループがある場合は、 **-All $True**パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="43f0e-147">Use the **-All $True** parameter if you have a lot of groups.</span></span>
    ```
    Get-AzureADMSDeletedGroup
    ``` 
3. <span data-ttu-id="43f0e-148">復元するグループを見つけて、Id をメモします。</span><span class="sxs-lookup"><span data-stu-id="43f0e-148">Find the group that you want to restore, and then make a note of the Id.</span></span>
4. <span data-ttu-id="43f0e-149">グループを復元するには、次を実行します。 [Id] はグループ Id です。</span><span class="sxs-lookup"><span data-stu-id="43f0e-149">Run the following to restore the group, where [Id] is the group Id.</span></span>
    ```
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  <span data-ttu-id="43f0e-150">グループが正常に復元されたことを確認するには、次を実行します。 [Id] はグループ Id です。</span><span class="sxs-lookup"><span data-stu-id="43f0e-150">Run the following to verify the group was successfully restored, where [Id] is the group Id.</span></span>
    ```
    Get-AzureADGroup -ObjectId [Id]
    ```

    <span data-ttu-id="43f0e-151">復元プロセスが完了するまでに最大で24時間かかる場合があります。その後、タブやチャネルなど、チームに関連付けられたチームとコンテンツが Teams に表示されます。</span><span class="sxs-lookup"><span data-stu-id="43f0e-151">It can take up to 24 hours for the restore process to complete, after which the team and content associated with the team, including tabs and channels, is displayed in Teams.</span></span>
