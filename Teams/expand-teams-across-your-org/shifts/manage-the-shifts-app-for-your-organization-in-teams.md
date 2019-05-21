---
title: Microsoft Teams で組織のシフト アプリを管理する
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 組織の Firstline Worker の Teams でシフトアプリを設定および管理する方法について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9927da9aea89eeb4d5b1b71eac2818c5deb52925
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245937"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="877f4-103">Microsoft Teams で組織のシフト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="877f4-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="877f4-104">2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="877f4-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="877f4-105">Microsoft Teams で StaffHub 機能を構築しています。</span><span class="sxs-lookup"><span data-stu-id="877f4-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="877f4-106">現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。</span><span class="sxs-lookup"><span data-stu-id="877f4-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="877f4-107">2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="877f4-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="877f4-108">StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="877f4-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="877f4-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="877f4-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="877f4-110">シフトの概要</span><span class="sxs-lookup"><span data-stu-id="877f4-110">Overview of Shifts</span></span>
<span data-ttu-id="877f4-111">Microsoft Teams の [シフト] アプリでは、Firstline Worker が接続され、同期されます。モバイル機能を搭載しているので、チームの時間管理とコミュニケーションを迅速かつ効率的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="877f4-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="877f4-112">[シフト] では、最初の行の作業者とそのマネージャーは、モバイルデバイスを使ってスケジュールを管理し、連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="877f4-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="877f4-113">マネージャーは、チームのシフト スケジュールを作成、更新、および管理します。</span><span class="sxs-lookup"><span data-stu-id="877f4-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="877f4-114">マネージャーは、メッセージを 1 人のユーザーに送ることも ("床が汚れています" など)、チーム全体に送ることもできます ("地区本部長があと 20 分で到着します" など)。</span><span class="sxs-lookup"><span data-stu-id="877f4-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="877f4-115">マネージャーは、ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="877f4-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="877f4-116">従業員は、自分の今後のシフトの確認、自分の他にその日にスケジュールが入っている従業員の表示、シフトの入れ替えや申し出のリクエスト、および休暇のリクエストが行えます。</span><span class="sxs-lookup"><span data-stu-id="877f4-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="877f4-117">シフトでは現在、ゲスト ユーザーはサポートされていませんのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="877f4-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="877f4-118">つまり、Teams でゲスト アクセスがオンになっていると、チームのゲストをシフト スケジュールに追加することも、チームのゲストがシフト スケジュールを使用することもできません。</span><span class="sxs-lookup"><span data-stu-id="877f4-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="877f4-119">シフトの可用性</span><span class="sxs-lookup"><span data-stu-id="877f4-119">Availability of Shifts</span></span>

<span data-ttu-id="877f4-120">シフトは Teams を含むすべての Office 365 サブスクリプションでご利用いただけますが、いくつかの例外があります。</span><span class="sxs-lookup"><span data-stu-id="877f4-120">Shifts is available in all Office 365 subscriptions that include Teams, with a couple of exceptions.</span></span> <span data-ttu-id="877f4-121">例外となるのは、米国の Government Community Cloud (GCC) および無料版の Teams です。</span><span class="sxs-lookup"><span data-stu-id="877f4-121">The exceptions are US Government Cloud Community (GCC) and Teams free.</span></span> <span data-ttu-id="877f4-122">シフトは、Office 365 US Government または Teams の無料サービスでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="877f4-122">Shifts isn't available in Office 365 US Government or Teams free offerings.</span></span>

<span data-ttu-id="877f4-123">Teams を含む Office 365 サブスクリプションの一覧など、Teams のライセンスの詳細については、「[Teams の Office 365 ライセンス](../../Office-365-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="877f4-123">To learn more about licensing for Teams, including a list of Office 365 subscriptions that includes Teams, see [Office 365 licensing for Teams](../../Office-365-licensing.md).</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="877f4-124">シフトのデータの場所</span><span class="sxs-lookup"><span data-stu-id="877f4-124">Location of Shifts data</span></span>

<span data-ttu-id="877f4-125">現在、シフトのデータは、北米、西ヨーロッパ、およびアジア太平洋にあるデータ センターの Azure に保存されています。</span><span class="sxs-lookup"><span data-stu-id="877f4-125">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="877f4-126">データが保存される場所の詳細については、「[データの保存場所](http://o365datacentermap.azurewebsites.net/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="877f4-126">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="877f4-127">シフトのセットアップ</span><span class="sxs-lookup"><span data-stu-id="877f4-127">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="877f4-128">組織のシフトを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="877f4-128">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="877f4-129">シフトは、組織内のすべての Teams ユーザーに対して既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="877f4-129">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="877f4-130">Microsoft 365 管理センターで、ご自分の組織についてアプリをオフまたはオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="877f4-130">You can turn off or turn on the app for your organization in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="877f4-131">Office 365 管理者アカウントで Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="877f4-131">Sign in to the Microsoft 365 admin center with your Office 365 admin account.</span></span>
2. <span data-ttu-id="877f4-132">**[設定]**  >  **[サービスとアドイン]**  >  **[Microsoft Teams]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="877f4-132">Go to **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> 
3. <span data-ttu-id="877f4-133">**[テナント レベルの設定]** で **[アプリ]** を選択し、**[既定のアプリ]** の下で、**[シフト]** チェック ボックスをオンにするかオフにすることで、アプリのオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="877f4-133">Under **Tenant-wide settings**, select **Apps**, and then under **Default Apps**, clear or select the **Shifts** check box to turn off or turn on the app.</span></span> 

    <span data-ttu-id="877f4-134">![[既定のアプリ] セクションのスクリーンショット](../../media/firstline-worker-enable-disable-shifts.png "シフト アプリを含むアプリの一覧を示す、Microsoft 365 管理センターの [既定のアプリ] セクションのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="877f4-134">![Screen shot of the Default Apps section](../../media/firstline-worker-enable-disable-shifts.png "Screen shot of the Default Apps section in the Microsoft 365 admin center, showing the list of apps, including the Shifts app")</span></span>

### <a name="use-the-firstline-worker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="877f4-135">Firstline Worker アプリのセットアップポリシーを使用して、チームにシフトをピン留めする</span><span class="sxs-lookup"><span data-stu-id="877f4-135">Use the Firstline Worker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="877f4-136">アプリ セットアップ ポリシーを使用すると、組織内のユーザーにとって最も重要なアプリを強調表示するように Teams をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="877f4-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="877f4-137">ポリシーに設定されたアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="877f4-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="877f4-138">Teams には、組織内の Firstline Worker に割り当てることができる、Firstline の組み込みのワーカーアプリセットアップポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="877f4-138">Teams includes a built-in Firstline Worker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="877f4-139">既定では、ポリシーにはアクティビティ、シフト、チャット、および通話の各アプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="877f4-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="877f4-140">Firstline Worker ポリシーを表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、[ **Teams アプリ** > **アプリセットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="877f4-140">To view the Firstline Worker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="877f4-141">![Microsoft Teams 管理センターの最初のラインワーカーアプリセットアップポリシーのスクリーンショット](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 管理センターの最初のラインワーカーアプリセットアップポリシーのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="877f4-141">![Screen shot of the Firstline Worker app setup policy in the Microsoft Teams admin center](../../media/firstline-worker-app-setup-policy.png "Screen shot of the Firstline Worker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstline-worker-policy-to-individual-users"></a><span data-ttu-id="877f4-142">Firstline Worker ポリシーを個々のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="877f4-142">Assign the Firstline Worker policy to individual users</span></span>

1. <span data-ttu-id="877f4-143">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="877f4-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="877f4-144">**[割り当てられているポリシー]** の隣にある **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="877f4-144">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="877f4-145">[ **Teams アプリセットアップポリシー**] で [ **firstlineworker**] を選択し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="877f4-145">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstline-worker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="877f4-146">Firstline Worker アプリセットアップポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="877f4-146">Assign the Firstline Worker app setup policy to users in a group</span></span>

<span data-ttu-id="877f4-147">Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続することにより、セキュリティグループなどのグループ内のユーザーに Firstline Worker アプリセットアップポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="877f4-147">You can assign the Firstline Worker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="877f4-148">PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](../../teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="877f4-148">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="877f4-149">この例では、Contoso Firstline チームグループ内のすべてのユーザーに Firstline Worker アプリセットアップポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="877f4-149">In this example, we assign the Firstline Worker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="877f4-150">「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。</span><span class="sxs-lookup"><span data-stu-id="877f4-150">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="877f4-151">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="877f4-151">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="877f4-152">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="877f4-152">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="877f4-153">グループ内のすべてのユーザーを FirstlineWorker アプリセットアップポリシーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="877f4-153">Assign all users in the group to the FirstlineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="877f4-154">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="877f4-154">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="877f4-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="877f4-155">Related topics</span></span>
- [<span data-ttu-id="877f4-156">Firstline Worker のヘルプをシフトする</span><span class="sxs-lookup"><span data-stu-id="877f4-156">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
