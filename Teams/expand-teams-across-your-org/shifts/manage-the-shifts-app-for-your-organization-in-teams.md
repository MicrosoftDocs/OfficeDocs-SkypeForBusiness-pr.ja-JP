---
title: 組織のシフトアプリを管理する
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織の Firstline Worker の Teams でシフトアプリを設定および管理する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c2ca24f2176547f83efb6bdce591ac71d516dca9
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416887"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="3966f-103">Microsoft Teams で組織のシフト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="3966f-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3966f-104">2020年6月30日の有効な Microsoft StaffHub は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="3966f-104">Effective June 30, 2020, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="3966f-105">Microsoft Teams で StaffHub 機能を構築しています。</span><span class="sxs-lookup"><span data-stu-id="3966f-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="3966f-106">現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="3966f-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="3966f-107">2020年6月30日に、StaffHub はすべてのユーザーに対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="3966f-107">StaffHub will stop working for all users on June 30, 2020.</span></span> <span data-ttu-id="3966f-108">ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3966f-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="3966f-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3966f-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="3966f-110">シフトの概要</span><span class="sxs-lookup"><span data-stu-id="3966f-110">Overview of Shifts</span></span>

<span data-ttu-id="3966f-111">Microsoft Teams の [シフト] アプリでは、Firstline Worker が接続され、同期されます。モバイル機能を搭載しているので、チームの時間管理とコミュニケーションを迅速かつ効率的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3966f-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="3966f-112">[シフト] では、最初の行の作業者とそのマネージャーは、モバイルデバイスを使ってスケジュールを管理し、連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="3966f-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="3966f-113">マネージャーは、チームのシフト スケジュールを作成、更新、および管理します。</span><span class="sxs-lookup"><span data-stu-id="3966f-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="3966f-114">マネージャーは、メッセージを 1 人のユーザーに送ることも ("床が汚れています" など)、チーム全体に送ることもできます ("地区本部長があと 20 分で到着します" など)。</span><span class="sxs-lookup"><span data-stu-id="3966f-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="3966f-115">マネージャーは、ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="3966f-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="3966f-116">従業員は、自分の今後のシフトの確認、自分の他にその日にスケジュールが入っている従業員の表示、シフトの入れ替えや申し出のリクエスト、および休暇のリクエストが行えます。</span><span class="sxs-lookup"><span data-stu-id="3966f-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="3966f-117">シフトでは現在、ゲスト ユーザーはサポートされていませんのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="3966f-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="3966f-118">つまり、Teams でゲスト アクセスがオンになっていると、チームのゲストをシフト スケジュールに追加することも、チームのゲストがシフト スケジュールを使用することもできません。</span><span class="sxs-lookup"><span data-stu-id="3966f-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="3966f-119">シフトの可用性</span><span class="sxs-lookup"><span data-stu-id="3966f-119">Availability of Shifts</span></span>

<span data-ttu-id="3966f-120">シフトは、Teams が利用できるすべての Enterprise Sku で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3966f-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="3966f-121">シフトのデータの場所</span><span class="sxs-lookup"><span data-stu-id="3966f-121">Location of Shifts data</span></span>

<span data-ttu-id="3966f-122">現在、シフトのデータは、北米、西ヨーロッパ、およびアジア太平洋にあるデータ センターの Azure に保存されています。</span><span class="sxs-lookup"><span data-stu-id="3966f-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="3966f-123">データが保存される場所の詳細については、「[データの保存場所](http://o365datacentermap.azurewebsites.net/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3966f-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="3966f-124">シフトのセットアップ</span><span class="sxs-lookup"><span data-stu-id="3966f-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="3966f-125">組織のシフトを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="3966f-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="3966f-126">シフトは、組織内のすべての Teams ユーザーに対して既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="3966f-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="3966f-127">Microsoft Teams 管理センターの [[アプリの管理](../../manage-apps.md)] ページで、組織レベルでアプリをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3966f-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="3966f-128">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。</span><span class="sxs-lookup"><span data-stu-id="3966f-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="3966f-129">アプリの一覧で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3966f-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="3966f-130">組織のシフトをオフにするには、[シフト] アプリを検索して選択し、[**ブロック**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3966f-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="3966f-131">組織のシフトを有効にするには、[シフト] アプリを検索して選択し、[**許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3966f-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="3966f-132">組織内の特定のユーザーのシフトを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="3966f-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="3966f-133">組織内の特定のユーザーによるシフトの使用を許可またはブロックするには、[[アプリの管理](../../manage-apps.md)] ページで組織のシフトが有効になっていることを確認してから、カスタムのアプリのアクセス許可ポリシーを作成して、それらのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3966f-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="3966f-134">詳細については、「 [Teams でアプリのアクセス許可ポリシーを管理](../../teams-app-permission-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3966f-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="3966f-135">FirstlineWorker アプリのセットアップポリシーを使用して、チームにシフトをピン留めする</span><span class="sxs-lookup"><span data-stu-id="3966f-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="3966f-136">アプリ セットアップ ポリシーを使用すると、組織内のユーザーにとって最も重要なアプリを強調表示するように Teams をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3966f-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="3966f-137">ポリシーに設定されたアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3966f-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="3966f-138">Teams には、組織内の Firstline Worker に割り当てることができる、FirstlineWorker アプリセットアップポリシーが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="3966f-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="3966f-139">既定では、ポリシーにはアクティビティ、シフト、チャット、および通話の各アプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3966f-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="3966f-140">Firstlineworker ポリシーを表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、[ **Teams アプリ**  >  **アプリセットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3966f-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="3966f-141">![FirstlineWorker アプリセットアップポリシーのスクリーンショット](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 管理センターの FirstlineWorker アプリセットアップポリシーのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="3966f-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-users"></a><span data-ttu-id="3966f-142">FirstlineWorker ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3966f-142">Assign the FirstlineWorker policy to users</span></span>

<span data-ttu-id="3966f-143">FirstlineWorker アプリのセットアップポリシーを1人のユーザーに割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3966f-143">To assign the FirstlineWorker app setup policy to one user:</span></span>

1. <span data-ttu-id="3966f-144">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3966f-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="3966f-145">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3966f-145">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="3966f-146">[**アプリセットアップポリシー**] で [ **firstlineworker**] を選択し、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3966f-146">Under **App setup policy**, select **FirstlineWorker**, and then click **Apply**.</span></span>

<span data-ttu-id="3966f-147">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3966f-147">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="3966f-148">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="3966f-148">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="3966f-149">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3966f-149">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="3966f-150">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3966f-150">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="3966f-151">[**設定の編集**] をクリックし、[**アプリセットアップポリシー**] で [ **firstlineworker**] を選択し、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3966f-151">Click **Edit settings**, under **App setup policy**, select **FirstlineWorker**, and then click **Apply**.</span></span>  

<span data-ttu-id="3966f-152">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="3966f-152">Or, you can also do the following:</span></span>

1. <span data-ttu-id="3966f-153">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3966f-153">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="3966f-154">ポリシー名の左側をクリックして、FirstlineWorker ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3966f-154">Select the FirstlineWorker policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="3966f-155">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3966f-155">Select **Manage users**.</span></span>
4. <span data-ttu-id="3966f-156">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3966f-156">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="3966f-157">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3966f-157">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="3966f-158">ユーザーの追加が完了したら、[**適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3966f-158">After you finish adding users, select **Apply**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a><span data-ttu-id="3966f-159">FirstlineWorker アプリのセットアップポリシーをグループのユーザーメンバーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3966f-159">Assign the FirstlineWorker app setup policy to user members of a group</span></span>

<span data-ttu-id="3966f-160">最初の Lineworker アプリのセットアップポリシーは、セキュリティグループなどのグループのユーザーメンバーに割り当てることができます。これには、Graph モジュール用の Azure Active Directory PowerShell と Skype for Business PowerShell モジュールに接続します。</span><span class="sxs-lookup"><span data-stu-id="3966f-160">You can assign the FirstlineWorker app setup policy to user members of a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="3966f-161">PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](../../teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3966f-161">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="3966f-162">この例では、Contoso Firstline チームグループのすべてのユーザーメンバーに FirstlineWorker アプリセットアップポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3966f-162">In this example, we assign the FirstlineWorker app setup policy to all user members of the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="3966f-163">「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。</span><span class="sxs-lookup"><span data-stu-id="3966f-163">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="3966f-164">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="3966f-164">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="3966f-165">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="3966f-165">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="3966f-166">グループのすべてのユーザーメンバーに FirstlineWorker アプリセットアップポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3966f-166">Assign the FirstlineWorker app setup policy to all user members of the group.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="3966f-167">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3966f-167">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="3966f-168">監査ログでシフトイベントを検索する</span><span class="sxs-lookup"><span data-stu-id="3966f-168">Search the audit log for Shifts events</span></span>

<span data-ttu-id="3966f-169">**(プレビュー段階)**</span><span class="sxs-lookup"><span data-stu-id="3966f-169">**(in preview)**</span></span>

<span data-ttu-id="3966f-170">監査ログを検索して、組織内のシフトアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="3966f-170">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="3966f-171">監査ログを検索し、監査ログに記録されている[シフトアクティビティ](../../audit-log-events.md#shifts-in-teams-activities)の一覧を表示する方法の詳細については、「 [Teams のイベントの監査ログを検索](../../audit-log-events.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3966f-171">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="3966f-172">監査ログを検索する前に、まず[セキュリティ & コンプライアンスセンター](https://protection.office.com)で監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3966f-172">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="3966f-173">詳細については、「[監査ログの検索を有効または無効に](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3966f-173">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="3966f-174">監査データは、監査を有効にした時点でのみ利用可能であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3966f-174">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3966f-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="3966f-175">Related topics</span></span>

- [<span data-ttu-id="3966f-176">Firstline Worker のヘルプをシフトする</span><span class="sxs-lookup"><span data-stu-id="3966f-176">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="3966f-177">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3966f-177">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
