---
title: 組織は、マイクロソフトのチームでのシフトのアプリケーションを管理します。
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 1/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 設定し、組織内の先頭行の作業者のチームでシフトのアプリケーションを管理する方法について説明します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fdd9c47e54c9ce51e736363eb47227614824a4c
ms.sourcegitcommit: 768c7b5f0aaa4b38a0b98c7c9ff904ffedd2e9b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2019
ms.locfileid: "27893358"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="c0aaa-103">組織は、マイクロソフトのチームでのシフトのアプリケーションを管理します。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0aaa-104">効果的な 2019 年 10 月 1日マイクロソフトの StaffHub は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="c0aaa-105">StaffHub 機能、マイクロソフトのチームに、スケジュールとタスクの管理などが進められています。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-105">We're building StaffHub capabilities, including schedule and task management, into Microsoft Teams.</span></span> <span data-ttu-id="c0aaa-106">先頭行の作業者の他の機能ロール チームに時間の経過と共にします。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-106">Additional capabilities for firstline workers will roll out to Teams over time.</span></span> <span data-ttu-id="c0aaa-107">詳細については、[不要になったマイクロソフトの StaffHub](https://support.office.com/article/microsoft-staffhub-to-be-retired-30ca17f3-5502-4bc9-bb0a-bed04bb362f0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-107">To learn more, see [Microsoft StaffHub to be retired](https://support.office.com/article/microsoft-staffhub-to-be-retired-30ca17f3-5502-4bc9-bb0a-bed04bb362f0).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="c0aaa-108">シフトの概要</span><span class="sxs-lookup"><span data-stu-id="c0aaa-108">Overview of Shifts</span></span>
<span data-ttu-id="c0aaa-109">マイクロソフトのチームでシフトのアプリケーションは、接続されているとの同期作業者の先頭行を保持します。モバイルを最初にビルド時間を迅速かつ効果的な管理とチームのための通信用です。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-109">The Shifts app in Microsoft Teams keeps firstline workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="c0aaa-110">シフトでは、先頭行の作業者とマネージャーが自分のモバイル デバイスを使用してスケジュールを管理し、コミュニケーションをします。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-110">Shifts lets firstline workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="c0aaa-111">マネージャーを作成するには、更新、およびチームのシフト スケジュールを管理します。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-111">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="c0aaa-112">1 人のユーザーにメッセージを送信することができます (「は、算術、現場で」) または全体のチーム (「地域の GM が到着 20 分で」)。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-112">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="c0aaa-113">ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-113">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="c0aaa-114">従業員の今後の変化を表示することができます 1 日に予定されている他のメンバーを参照してください、スワップまたは、shift キーを押しを提供し、オフ時間を要求する要求です。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-114">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="c0aaa-115">あるシフト現在サポートしていないゲスト ユーザーを知っているが重要です。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-115">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="c0aaa-116">つまり、チームでは、来園者に追加するにはチームでゲスト アクセスが有効になっているときに shift キーを押しのスケジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-116">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="c0aaa-117">シフトの可用性</span><span class="sxs-lookup"><span data-stu-id="c0aaa-117">Availability of Shifts</span></span>

<span data-ttu-id="c0aaa-118">シフトは、例外の 2 つのチームを含むすべての Office 365 サブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-118">Shifts is available in all Office 365 subscriptions that include Teams, with a couple of exceptions.</span></span> <span data-ttu-id="c0aaa-119">米国政府クラウド コミュニティ (GCC) および無料のチームは、例外があります。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-119">The exceptions are US Government Cloud Community (GCC) and Teams free.</span></span> <span data-ttu-id="c0aaa-120">シフトが Office 365 の米国政府機関では使用できません。 または、チームが製品を解放します。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-120">Shifts isn't available in Office 365 US Government or Teams free offerings.</span></span>

<span data-ttu-id="c0aaa-121">チームのライセンスに関する詳細については、 [Office 365 のライセンスのチームを](Office-365-licensing.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-121">To learn more about licensing for Teams, see [Office 365 licensing for Teams](Office-365-licensing.md).</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="c0aaa-122">シフトを設定します</span><span class="sxs-lookup"><span data-stu-id="c0aaa-122">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="c0aaa-123">有効にするか、組織内のシフトを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-123">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="c0aaa-124">シフトは、組織内のチームのすべてのユーザーに対して既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-124">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="c0aaa-125">オフにするか、Microsoft 365 の管理ページで、組織のアプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-125">You can turn off or turn on the app for your organization in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="c0aaa-126">Office 365 管理者アカウントを使用して Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-126">Sign in to the Microsoft 365 admin center with your Office 365 admin account.</span></span>
2. <span data-ttu-id="c0aaa-127">**設定**に > **サービスおよびアドイン** > **マイクロソフトのチーム**です。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-127">Go to **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> 
3. <span data-ttu-id="c0aaa-128">**テナント全体の設定**、[**アプリケーション**を選択して [**既定のアプリケーション**をオフにしたり、**シフト**するチェック ボックスをオフにするか、アプリケーションを有効にするを選択します。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-128">Under **Tenant-wide settings**, select **Apps**, and then under **Default Apps**, clear or select the **Shifts** check box to turn off or turn on the app.</span></span> 

    <span data-ttu-id="c0aaa-129">![アプリケーションの既定のセクションのスクリーン ショット](media/firstline-worker-enable-disable-shifts.png "シフトのアプリケーションを含む、アプリケーションの一覧を示す Microsoft 365 管理センターで [アプリケーションの既定のセクションのスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="c0aaa-129">![Screen shot of the Default Apps section](media/firstline-worker-enable-disable-shifts.png "Screen shot of the Default Apps section in the Microsoft 365 admin center, showing the list of apps, including the Shifts app")</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="c0aaa-130">チームに暗証番号 (pin) のシフトに FirstLineWorker アプリケーションの設定のポリシーを使用してください。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-130">Use the FirstLineWorker app setup policy to pin Shifts to Teams</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="c0aaa-131">アプリケーション設定のポリシーを使用して、チームは、組織内のユーザーの最も重要なアプリケーションを強調表示をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-131">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="c0aaa-132">ポリシーの設定のアプリケーションが、アプリケーション バーに固定されている&mdash;チームのデスクトップ クライアント側にし、チームのモバイル クライアントの下部にあるバー&mdash;、迅速かつ容易にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-132">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="c0aaa-133">チームには、組み込み FirstLineWorker アプリケーションの設定ポリシー、組織内の先頭行の作業者に割り当てることができますが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-133">Teams includes a built-in FirstLineWorker app setup policy that you can assign to firstline workers in your organization.</span></span> <span data-ttu-id="c0aaa-134">既定では、ポリシーには、アクティビティ、シフト、チャット、および通話のアプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-134">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="c0aaa-135">ポリシーを表示する、FirstLineWorker、マイクロソフトのチームとビジネス管理センターの Skype の左側のナビゲーションでは、**チームのアプリケーション**に移動 > **アプリケーションの設定のポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-135">To view the FirstLineWorker policy, in the left navigation of the Microsoft Teams & Skype for Business Admin Center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="c0aaa-136">![マイクロソフト チームとビジネス管理センターの Skype では、FirstLineWorker アプリケーション セットアップ ポリシーのスクリーン ショット](media/firstline-worker-app-setup-policy.png "マイクロソフト チームとビジネス管理センターの Skype では、FirstLineWorker アプリケーション セットアップ ポリシーのスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="c0aaa-136">![Screen shot of the FirstLineWorker app setup policy in the Microsoft Teams & Skype for Business Admin Center](media/firstline-worker-app-setup-policy.png "Screen shot of the FirstLineWorker app setup policy in the Microsoft Teams & Skype for Business Admin Center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="c0aaa-137">FirstLineWorker ポリシーを個々 のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-137">Assign the FirstLineWorker policy to individual users</span></span>

1. <span data-ttu-id="c0aaa-138">マイクロソフトのチームとビジネス管理センターの Skype の左側のナビゲーションでは、**ユーザー**に移動し、し、[ユーザー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-138">In the left navigation of the Microsoft Teams & Skype for Business Admin Center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="c0aaa-139">**割り当てポリシー**] の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-139">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="c0aaa-140">**チームのアプリケーション設定のポリシー**では、 **FirstLineWorker**を選択し、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-140">Under **Teams App Setup policy**, select **FirstLineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="c0aaa-141">FirstLineWorker アプリケーションの設定のポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c0aaa-141">Assign the FirstLineWorker app setup policy to users in a group</span></span>

<span data-ttu-id="c0aaa-142">グラフ モジュールの Azure Active Directory PowerShell およびビジネスの PowerShell モジュールの Skype への接続で、セキュリティ グループなど、グループ内のユーザーに FirstLineWorker アプリケーションの設定のポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-142">You can assign the FirstLineWorker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="c0aaa-143">PowerShell を使用して、チームを管理する詳細については、[チームの PowerShell の概要](teams-powershell-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-143">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="c0aaa-144">この例では、contoso 社の先頭行のチームのグループ内のすべてのユーザーに FirstLineWorker アプリケーションの設定のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-144">In this example, we assign the FirstLineWorker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="c0aaa-145">[1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスへの接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)の手順を実行して、まずグラフ モジュールの Azure Active Directory PowerShell およびビジネスの PowerShell モジュールの Skype に接続することを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-145">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="c0aaa-146">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-146">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="c0aaa-147">指定されたグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-147">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="c0aaa-148">FirstLineWorker アプリケーションの設定のポリシーをグループ内のすべてのユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-148">Assign all users in the group to the FirstLineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstLineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="c0aaa-149">数によっては、グループ内のメンバーのこのコマンドは、実行するのに数分をかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-149">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c0aaa-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c0aaa-150">Related topics</span></span>
- [<span data-ttu-id="c0aaa-151">シフトについては、先頭行の作業者と管理者</span><span class="sxs-lookup"><span data-stu-id="c0aaa-151">Shifts Help for firstline workers and managers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)