---
title: Microsoft Teams でチームをアーカイブまたは削除する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: この記事では、Microsoft Teams でチームをアーカイブする、または完全に削除する方法について説明します。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d3548ead35c63e2d34c47b340559c3174f1c895
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086193"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a><span data-ttu-id="bd780-103">Microsoft Teams でチームをアーカイブまたは削除する</span><span class="sxs-lookup"><span data-stu-id="bd780-103">Archive or delete a team in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="bd780-104">時間の経過と共に、Microsoft Teams で作成したチームを使用しなくなることがあります。あるいは、プロジェクトの終了時にチームをアーカイブまたは削除したい場合もあります。</span><span class="sxs-lookup"><span data-stu-id="bd780-104">Over time, a team created in Microsoft Teams might fall out of use or you might want to archive or delete a team at the end of a project.</span></span> <span data-ttu-id="bd780-105">Microsoft Teams の管理者は、この記事に示す手順に従って、不要になったチームをアーカイブまたは削除できます。</span><span class="sxs-lookup"><span data-stu-id="bd780-105">If you're a Microsoft Teams admin, follow the steps in this article to archive or delete a team that's no longer needed.</span></span>

<span data-ttu-id="bd780-106">チームをアーカイブすると、そのチームのすべてのアクティビティが停止します。</span><span class="sxs-lookup"><span data-stu-id="bd780-106">When you archive a team, all activity for that team ceases.</span></span> <span data-ttu-id="bd780-107">チームをアーカイブすると、そのチーム内のプライベート チャネルと、関連付けられたサイト コレクションもアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="bd780-107">Archiving a team also archives private channels in the team and their associated site collections.</span></span>  <span data-ttu-id="bd780-108">ただし、メンバーを追加または削除したり、ロールを更新したりすることはできます。また、標準およびプライベートのチャネル、ファイル、チャットでの、そのチームのすべてのアクティビティを表示することも可能です。</span><span class="sxs-lookup"><span data-stu-id="bd780-108">However, you can still add or remove members and update roles and you can still view all the team activity in standard and private channels, files, and chats.</span></span>

<span data-ttu-id="bd780-109">チームを削除すると、標準およびプライベートのチャネル (および関連するサイト コレクション)、ファイル、チャットでのチーム アクティビティも削除されます。</span><span class="sxs-lookup"><span data-stu-id="bd780-109">When you delete a team, team activity in standard and private channels (and associated site collections), files, and chats is also deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd780-110">アーカイブされたチームを再アクティブ化することはできますが、削除されたチームを直接復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd780-110">Archived teams can be reactivated, but you can’t directly restore a team that has been deleted.</span></span> <span data-ttu-id="bd780-111">チームをまずアーカイブし、チームが不要になったことが確実になるまで削除を延期することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="bd780-111">Consider archiving the team first, and postpone the deletion until you're sure that you no longer need the team.</span></span>

## <a name="archive-a-team"></a><span data-ttu-id="bd780-112">チームをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="bd780-112">Archive a team</span></span>

<span data-ttu-id="bd780-113">チームをアーカイブするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bd780-113">Follow these steps to archive a team.</span></span>

1. <span data-ttu-id="bd780-114">の管理センターで <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 、[ **Teams**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd780-114">In the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>, select **Teams**.</span></span>
2. <span data-ttu-id="bd780-115">チーム名をクリックして、チームを選びます。</span><span class="sxs-lookup"><span data-stu-id="bd780-115">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="bd780-116">[**アーカイブ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bd780-116">Select **Archive**.</span></span> <span data-ttu-id="bd780-117">次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd780-117">The following message will appear.</span></span>

    ![Teams のアーカイブ メッセージのスクリーンショット](media/teams-archive-message.png)

4. <span data-ttu-id="bd780-119">チームに関連付けられている SharePoint サイトと Wiki タブのコンテンツをユーザーが編集できないようにするには、[**チームメンバーに対して sharepoint サイトを読み取り**専用にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd780-119">To prevent people from editing the content in the SharePoint site and Wiki tab associated with the team, select **Make the SharePoint site read-only for team members**.</span></span> <span data-ttu-id="bd780-120">(チームの所有者は、このコンテンツを引き続き編集できます)。</span><span class="sxs-lookup"><span data-stu-id="bd780-120">(Teams owners will still be able to edit this content.)</span></span>
5. <span data-ttu-id="bd780-121">[**アーカイブ**] を選択して、チームをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="bd780-121">Select **Archive** to archive the team.</span></span> <span data-ttu-id="bd780-122">チームの状態が [**アーカイブ済み**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="bd780-122">The team’s status will change to **Archived**.</span></span>

## <a name="make-an-archived-team-active"></a><span data-ttu-id="bd780-123">アーカイブしたチームをアクティブにする</span><span class="sxs-lookup"><span data-stu-id="bd780-123">Make an archived team active</span></span>

<span data-ttu-id="bd780-124">次の手順に従って、アーカイブされているチームを再度アクティブにします。</span><span class="sxs-lookup"><span data-stu-id="bd780-124">Follow these steps to make an archived team active again.</span></span>

1. <span data-ttu-id="bd780-125"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>で、[**チーム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd780-125">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, select **Teams**.</span></span>
2. <span data-ttu-id="bd780-126">チーム名をクリックして、チームを選びます。</span><span class="sxs-lookup"><span data-stu-id="bd780-126">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="bd780-127">[**アーカイブ解除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd780-127">Select **Unarchive**.</span></span> <span data-ttu-id="bd780-128">チームの状態が [**アクティブ**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="bd780-128">The team’s status will change to **Active**.</span></span>

## <a name="delete-a-team"></a><span data-ttu-id="bd780-129">チームを削除する</span><span class="sxs-lookup"><span data-stu-id="bd780-129">Delete a team</span></span>

<span data-ttu-id="bd780-130">今後チームが必要にならない場合、アーカイブではなく、削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bd780-130">If the team will not be required in the future, then you can delete it rather than archiving it.</span></span> <span data-ttu-id="bd780-131">チームを削除するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bd780-131">Follow these steps to delete a team.</span></span>

1.  <span data-ttu-id="bd780-132"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>で、[**チーム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd780-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, select **Teams**.</span></span>
2.  <span data-ttu-id="bd780-133">チーム名をクリックして、チームを選びます。</span><span class="sxs-lookup"><span data-stu-id="bd780-133">Select a team by clicking the team name.</span></span>
3.  <span data-ttu-id="bd780-134">[**削除**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bd780-134">Select **Delete**.</span></span> <span data-ttu-id="bd780-135">確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd780-135">A confirmation message will appear.</span></span>
4.  <span data-ttu-id="bd780-136">チームを完全に削除するには、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd780-136">Select **Delete** to permanently delete the team.</span></span>

## <a name="restore-a-deleted-team"></a><span data-ttu-id="bd780-137">削除したチームを復元する</span><span class="sxs-lookup"><span data-stu-id="bd780-137">Restore a deleted team</span></span>

<span data-ttu-id="bd780-138">チームに関連付けられている Microsoft 365 グループを復元して、削除されたチームを復元するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bd780-138">Follow these steps to restore a deleted team by restoring the Microsoft 365 group that's associated with the team.</span></span> <span data-ttu-id="bd780-139">チームの Microsoft 365 グループを復元すると、タブ、標準チャネル、プライベートチャネル、関連付けられたサイトコレクションなどのチームコンテンツが復元されます。</span><span class="sxs-lookup"><span data-stu-id="bd780-139">Restoring the Microsoft 365 group for a team restores team content, including tabs, standard channels, and private channels and their associated site collections.</span></span>

<span data-ttu-id="bd780-140">既定では、削除された Microsoft 365 グループは30日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="bd780-140">By default, a deleted Microsoft 365 group is retained for 30 days.</span></span> <span data-ttu-id="bd780-141">この 30 日の期間は、グループを復元できるため、「ソフト削除」と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="bd780-141">This 30-day period is called "soft-delete" because you can restore the group.</span></span> <span data-ttu-id="bd780-142">詳細については、「[削除したグループを復元](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd780-142">To learn more, see [Restore a deleted Group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="install-the-azureadpreview-module"></a><span data-ttu-id="bd780-143">AzureADPreview モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="bd780-143">Install the AzureADPreview module</span></span>

1. <span data-ttu-id="bd780-144">管理者として Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="bd780-144">Open Windows PowerShell as an admin.</span></span>
2. <span data-ttu-id="bd780-145">以前のバージョンの AzureADPreview モジュールがインストールされているか、AzureAD モジュールがインストールされている場合は、次のいずれかを実行してアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="bd780-145">If you have an earlier version of the AzureADPreview module installed or the AzureAD module installed, uninstall it by running one of the following:</span></span>

    ```PowerShell 
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. <span data-ttu-id="bd780-146">次を実行して、最新バージョンの AzureADPreview モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bd780-146">Install the latest version of the AzureADPreview module by running the following:</span></span>

    ```PowerShell
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-microsoft-365-group"></a><span data-ttu-id="bd780-147">削除された Microsoft 365 グループを復元する</span><span class="sxs-lookup"><span data-stu-id="bd780-147">Restore the deleted Microsoft 365 group</span></span>

1. <span data-ttu-id="bd780-148">Azure AD に接続するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="bd780-148">Connect to Azure AD by running the following:</span></span>
    ```PowerShell
    Connect-AzureAD
    ```
    <span data-ttu-id="bd780-149">メッセージが表示されたら、管理者アカウントとパスワードを使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="bd780-149">When you're prompted, sign in using your admin account and password.</span></span>  
2. <span data-ttu-id="bd780-150">次を実行して、30日の保持期間内のすべてのソフト削除された Microsoft 365 グループの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd780-150">Run the following to display a list of all soft-deleted Microsoft 365 groups that are still within the 30-day retention period.</span></span> <span data-ttu-id="bd780-151">多数のグループがある場合は、**-All $True** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd780-151">Use the **-All $True** parameter if you have a lot of groups.</span></span>
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ``` 
3. <span data-ttu-id="bd780-152">復元するグループを見つけて、ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="bd780-152">Find the group that you want to restore, and then make a note of the Id.</span></span>
4. <span data-ttu-id="bd780-153">グループを復元するには、次のようにします。[Id] はグループ ID です。</span><span class="sxs-lookup"><span data-stu-id="bd780-153">Run the following to restore the group, where [Id] is the group Id.</span></span>
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  <span data-ttu-id="bd780-154">グループが正常に復元されたことを確認するには、次を実行します。[Id] はグループ ID です。</span><span class="sxs-lookup"><span data-stu-id="bd780-154">Run the following to verify the group was successfully restored, where [Id] is the group Id.</span></span>
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    <span data-ttu-id="bd780-155">復元プロセスが完了するまで、最大で 24 時間かかる場合があります。その後、タブやチャネルなど、該当するチームに関連付けられたチームとコンテンツが Teams に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd780-155">It can take up to 24 hours for the restore process to complete, after which the team and content associated with the team, including tabs and channels, is displayed in Teams.</span></span>
