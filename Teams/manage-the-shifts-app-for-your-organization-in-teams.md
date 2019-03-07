---
title: Microsoft Teams で組織のシフト アプリを管理する
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 1/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Teams で組織の現場担当者向けにシフト アプリを設定および管理する方法を学びます。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 204dc5899a72b1bc1516441ca8654e7341f19942
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754528"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="4373f-103">Microsoft Teams で組織のシフト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="4373f-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4373f-104">2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="4373f-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="4373f-105">スケジュールやタスク管理などの StaffHub の機能は Microsoft Teams に構築中です。</span><span class="sxs-lookup"><span data-stu-id="4373f-105">We're building StaffHub capabilities, including schedule and task management, into Microsoft Teams.</span></span> <span data-ttu-id="4373f-106">現場担当者向けの追加機能は、段階的に Teams に公開されます。</span><span class="sxs-lookup"><span data-stu-id="4373f-106">Additional capabilities for firstline workers will roll out to Teams over time.</span></span> <span data-ttu-id="4373f-107">詳細については、「[Microsoft StaffHub の廃止](https://support.office.com/article/microsoft-staffhub-to-be-retired-30ca17f3-5502-4bc9-bb0a-bed04bb362f0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4373f-107">To learn more, see [Microsoft StaffHub to be retired](https://support.office.com/article/microsoft-staffhub-to-be-retired-30ca17f3-5502-4bc9-bb0a-bed04bb362f0).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="4373f-108">シフトの概要</span><span class="sxs-lookup"><span data-stu-id="4373f-108">Overview of Shifts</span></span>
<span data-ttu-id="4373f-109">Microsoft Teams のシフト アプリでは、現場担当者との連絡と同期を常に行えます。このアプリは、チームが迅速で効果的な時間管理とコミュニケーションを行えるようにモバイル ファーストで構築されています。</span><span class="sxs-lookup"><span data-stu-id="4373f-109">The Shifts app in Microsoft Teams keeps firstline workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="4373f-110">シフトを使用すると、現場担当者とそのマネージャーは自分のモバイル デバイスを使用して、スケジュールを管理し、連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="4373f-110">Shifts lets firstline workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="4373f-111">マネージャーは、チームのシフト スケジュールを作成、更新、および管理します。</span><span class="sxs-lookup"><span data-stu-id="4373f-111">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="4373f-112">マネージャーは、メッセージを 1 人のユーザーに送ることも ("床が汚れています" など)、チーム全体に送ることもできます ("地区本部長があと 20 分で到着します" など)。</span><span class="sxs-lookup"><span data-stu-id="4373f-112">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="4373f-113">マネージャーは、ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="4373f-113">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="4373f-114">従業員は、自分の今後のシフトの確認、自分の他にその日にスケジュールが入っている従業員の表示、シフトの入れ替えや申し出のリクエスト、および休暇のリクエストが行えます。</span><span class="sxs-lookup"><span data-stu-id="4373f-114">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="4373f-115">シフトでは現在、ゲスト ユーザーはサポートされていませんのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="4373f-115">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="4373f-116">つまり、Teams でゲスト アクセスがオンになっていると、チームのゲストをシフト スケジュールに追加することも、チームのゲストがシフト スケジュールを使用することもできません。</span><span class="sxs-lookup"><span data-stu-id="4373f-116">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="4373f-117">シフトの可用性</span><span class="sxs-lookup"><span data-stu-id="4373f-117">Availability of Shifts</span></span>

<span data-ttu-id="4373f-118">シフトは Teams を含むすべての Office 365 サブスクリプションでご利用いただけますが、いくつかの例外があります。</span><span class="sxs-lookup"><span data-stu-id="4373f-118">Shifts is available in all Office 365 subscriptions that include Teams, with a couple of exceptions.</span></span> <span data-ttu-id="4373f-119">例外となるのは、米国の Government Community Cloud (GCC) および無料版の Teams です。</span><span class="sxs-lookup"><span data-stu-id="4373f-119">The exceptions are US Government Cloud Community (GCC) and Teams free.</span></span> <span data-ttu-id="4373f-120">シフトは、Office 365 US Government または Teams の無料サービスでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="4373f-120">Shifts isn't available in Office 365 US Government or Teams free offerings.</span></span>

<span data-ttu-id="4373f-121">Teams を含む Office 365 サブスクリプションの一覧など、Teams のライセンスの詳細については、「[Teams の Office 365 ライセンス](Office-365-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4373f-121">To learn more about licensing for Teams, including a list of Office 365 subscriptions that includes Teams, see [Office 365 licensing for Teams](Office-365-licensing.md).</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="4373f-122">シフトのデータの場所</span><span class="sxs-lookup"><span data-stu-id="4373f-122">Location of Shifts data</span></span>

<span data-ttu-id="4373f-123">現在、シフトのデータは、北米、西ヨーロッパ、およびアジア太平洋にあるデータ センターの Azure に保存されています。</span><span class="sxs-lookup"><span data-stu-id="4373f-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="4373f-124">データが保存される場所の詳細については、「[データの保存場所](http://o365datacentermap.azurewebsites.net/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4373f-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="4373f-125">シフトのセットアップ</span><span class="sxs-lookup"><span data-stu-id="4373f-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="4373f-126">組織のシフトを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="4373f-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="4373f-127">シフトは、組織内のすべての Teams ユーザーに対して既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4373f-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="4373f-128">Microsoft 365 管理センターで、ご自分の組織についてアプリをオフまたはオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4373f-128">You can turn off or turn on apps for Teams in Tenant-wide settings in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="4373f-129">Office 365 管理者アカウントで Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="4373f-129">Sign in to the Microsoft 365 admin center with your Office 365 admin account.</span></span>
2. <span data-ttu-id="4373f-130">**[設定]**  >  **[サービスとアドイン]**  >  **[Microsoft Teams]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4373f-130">Go to **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> 
3. <span data-ttu-id="4373f-131">**[テナント レベルの設定]** で **[アプリ]** を選択し、**[既定のアプリ]** の下で、**[シフト]** チェック ボックスをオンにするかオフにすることで、アプリのオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="4373f-131">Under **Tenant-wide settings**, select **Apps**, and then under **Default Apps**, clear or select the **Shifts** check box to turn off or turn on the app.</span></span> 

    <span data-ttu-id="4373f-132">![[既定のアプリ] セクションのスクリーンショット](media/firstline-worker-enable-disable-shifts.png "シフト アプリを含むアプリの一覧を示す、Microsoft 365 管理センターの [既定のアプリ] セクションのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="4373f-132">![Screen shot of the Default Apps section](media/firstline-worker-enable-disable-shifts.png "Screen shot of the Default Apps section in the Microsoft 365 admin center, showing the list of apps, including the Shifts app")</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="4373f-133">FirstLineWorker のアプリ セットアップ ポリシーを使用してシフトを Teams にピン留めする</span><span class="sxs-lookup"><span data-stu-id="4373f-133">Use the FirstLineWorker app setup policy to pin Shifts to Teams</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="4373f-134">アプリ セットアップ ポリシーを使用すると、組織内のユーザーにとって最も重要なアプリを強調表示するように Teams をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="4373f-134">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="4373f-135">ポリシーに設定されたアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4373f-135">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="4373f-136">Teams には組み込みの FirstLineWorker アプリ セットアップ ポリシーが含まれており、これを組織内の現場担当者に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4373f-136">Teams includes a built-in FirstLineWorker app setup policy that you can assign to firstline workers in your organization.</span></span> <span data-ttu-id="4373f-137">既定では、ポリシーにはアクティビティ、シフト、チャット、および通話の各アプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4373f-137">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="4373f-138">FirstLineWorker ポリシーを表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]**  >  **[アプリ セットアップ ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4373f-138">To view the FirstLineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="4373f-139">![Microsoft Teams 管理センターの FirstLineWorker アプリ セットアップ ポリシーのスクリーンショット](media/firstline-worker-app-setup-policy.png "Microsoft Teams 管理センターの FirstLineWorker アプリ セットアップ ポリシーのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="4373f-139">![Screen shot of the FirstLineWorker app setup policy in the Microsoft Teams admin center](media/firstline-worker-app-setup-policy.png "Screen shot of the FirstLineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="4373f-140">個々のユーザーに FirstLineWorker ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4373f-140">Assign the FirstLineWorker policy to individual users</span></span>

1. <span data-ttu-id="4373f-141">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4373f-141">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="4373f-142">**[割り当てられているポリシー]** の隣にある **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4373f-142">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="4373f-143">**[Teams アプリのセットアップ ポリシー]** で、**[FirstLineWorker]** を選び、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4373f-143">Under **Teams App Setup policy**, select **FirstLineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="4373f-144">FirstLineWorker アプリのセットアップ ポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4373f-144">Assign the FirstLineWorker app setup policy to users in a group</span></span>

<span data-ttu-id="4373f-145">Azure Active Directory PowerShell for Graph モジュールおよび Skype for Business PowerShell モジュールに接続することで、セキュリティ グループなどのグループ内のユーザーに FirstLineWorker アプリのセットアップ ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4373f-145">You can assign the FirstLineWorker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="4373f-146">PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4373f-146">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="4373f-147">この例では、FirstLineWorker アプリのセットアップ ポリシーを Contoso 現場チーム グループのすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4373f-147">In this example, we assign the FirstLineWorker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="4373f-148">「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。</span><span class="sxs-lookup"><span data-stu-id="4373f-148">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="4373f-149">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="4373f-149">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="4373f-150">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="4373f-150">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="4373f-151">FirstLineWorker アプリのセットアップ ポリシーにグループ内のすべてのユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4373f-151">Assign all users in the group to the FirstLineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstLineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="4373f-152">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4373f-152">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4373f-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="4373f-153">Related topics</span></span>
- [<span data-ttu-id="4373f-154">現場担当者とマネージャー向けのシフトに関するヘルプ</span><span class="sxs-lookup"><span data-stu-id="4373f-154">Shifts Help for firstline workers and managers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)