---
title: 商用クラウドの試用提供を管理する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Microsoft Teams のライセンスが付与されていない Microsoft 365 ユーザーまたは Office 365 ユーザーが Teams の 1 年間試用版を開始する方法について説明します。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9f541eb0bd6970a54bad5272a26ec3a3449d2a13
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552633"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a><span data-ttu-id="6d675-103">Microsoft Teams の商用クラウドの試用提供を管理する</span><span class="sxs-lookup"><span data-stu-id="6d675-103">Manage the Microsoft Teams Commercial Cloud Trial offer</span></span>
=======================================================

<span data-ttu-id="6d675-104">Microsoft Teams の商用クラウド試用版は、製品の 1 年間試用版を開始するための Microsoft Teams ライセンスを所有していない、組織内の既存の Microsoft 365 ユーザーまたは Office 365 ユーザーを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="6d675-104">The Microsoft Teams Commercial Cloud Trial offers existing Microsoft 365 or Office 365 users in your organization who are not licensed for Microsoft Teams to initiate a 1-year trial of the product.</span></span> <span data-ttu-id="6d675-105">管理者は組織内のユーザーに対して、この機能をオンまたはオフに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="6d675-105">Admins can switch this feature on or off for users in their organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d675-106">Microsoft Teams の商用クラウド試用版は、2020 年 1 月から Microsoft Teams Exploratory に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="6d675-106">The Microsoft Teams Commercial Cloud Trial will be replaced by Microsoft Teams Exploratory beginning in January 2020.</span></span> <span data-ttu-id="6d675-107">この新しいサービスの詳細については、「[Teams Exploratory のライセンスを管理する](teams-exploratory.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6d675-107">To learn about this new offer, read [Manage Teams Exploratory license](teams-exploratory.md).</span></span>

## <a name="whats-in-the-offer"></a><span data-ttu-id="6d675-108">オファーの内容</span><span class="sxs-lookup"><span data-stu-id="6d675-108">What's in the offer</span></span>

<span data-ttu-id="6d675-109">このオファーに含まれるサービス プランは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6d675-109">The service plans included in this offer are:</span></span>

- <span data-ttu-id="6d675-110">Exchange の基礎</span><span class="sxs-lookup"><span data-stu-id="6d675-110">Exchange Foundation</span></span>
- <span data-ttu-id="6d675-111">Office 365 プラン 1 のフロー</span><span class="sxs-lookup"><span data-stu-id="6d675-111">Flow for Office 365 Plan 1</span></span>
- <span data-ttu-id="6d675-112">フォーム</span><span class="sxs-lookup"><span data-stu-id="6d675-112">Forms</span></span>
- <span data-ttu-id="6d675-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="6d675-113">Microsoft Planner</span></span>
- <span data-ttu-id="6d675-114">Microsoft Teams (Teams1、Teams IW)</span><span class="sxs-lookup"><span data-stu-id="6d675-114">Microsoft Teams (Teams1, Teams IW)</span></span>
- <span data-ttu-id="6d675-115">Office</span><span class="sxs-lookup"><span data-stu-id="6d675-115">Office</span></span> 
- <span data-ttu-id="6d675-116">PowerApps for Office 365 プラン 1</span><span class="sxs-lookup"><span data-stu-id="6d675-116">PowerApps for Office 365 Plan 1</span></span>
- <span data-ttu-id="6d675-117">SharePoint Online Kiosk</span><span class="sxs-lookup"><span data-stu-id="6d675-117">SharePoint Online Kiosk</span></span>
- <span data-ttu-id="6d675-118">Stream</span><span class="sxs-lookup"><span data-stu-id="6d675-118">Stream</span></span>
- <span data-ttu-id="6d675-119">Sway</span><span class="sxs-lookup"><span data-stu-id="6d675-119">Sway</span></span>
- <span data-ttu-id="6d675-120">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="6d675-120">Whiteboard</span></span>
- <span data-ttu-id="6d675-121">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="6d675-121">Yammer Enterprise</span></span> 

<span data-ttu-id="6d675-122">試用版では、組織全体に 1 年間の試用版サブスクリプションを付与します。</span><span class="sxs-lookup"><span data-stu-id="6d675-122">The trial grants a one-year trial subscription to your entire organization.</span></span> <span data-ttu-id="6d675-123">割り当てられたライセンスごとに、試用版では 2 GB の SharePoint Online 記憶域が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6d675-123">For each license assigned, the trial allocates 2 GB of SharePoint Online storage.</span></span> 

## <a name="who-is-eligible"></a><span data-ttu-id="6d675-124">対象者</span><span class="sxs-lookup"><span data-stu-id="6d675-124">Who is eligible</span></span>

<span data-ttu-id="6d675-125">ユーザーが (Microsoft 365 管理センターで) アプリや試用版にサインアップできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d675-125">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="6d675-126">詳細については、この記事で後述する「[試用版を管理する](#manage-the-trial)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d675-126">For more information, see [Manage the trial](#manage-the-trial), later in this article.</span></span> 

<span data-ttu-id="6d675-127">Teams を含むMicrosoft 365 または Office 365 ライセンスを所有していないユーザーは、Microsoft Teams 商用クラウド試用版のオファーを開始できます。</span><span class="sxs-lookup"><span data-stu-id="6d675-127">Users who do not have a Microsoft 365 or Office 365 license that includes Teams can initiate the Microsoft Teams Commercial Cloud Trial offer.</span></span> <span data-ttu-id="6d675-128">たとえば、ユーザーが Microsoft 365 Apps for business (Teams を含まない) を所有している場合、ユーザーは試用版の対象になります。</span><span class="sxs-lookup"><span data-stu-id="6d675-128">For example, if a user has Microsoft 365 Apps for business (which doesn't include Teams), they are eligible for the trial.</span></span>

## <a name="who-is-not-eligible"></a><span data-ttu-id="6d675-129">対象外</span><span class="sxs-lookup"><span data-stu-id="6d675-129">Who is not eligible</span></span>

<span data-ttu-id="6d675-130">シンジケート パートナー顧客である場合、または GCC、GCC High、DoD、または教育機関の顧客である場合、あなたの組織は試用版の対象ではありません。</span><span class="sxs-lookup"><span data-stu-id="6d675-130">Your organization is not eligible for the trial if you are a Syndication Partner Customer or if you are a GCC, GCC High, DoD, or EDU customer.</span></span>

<span data-ttu-id="6d675-131">組織が Microsoft Teams 商用クラウド試用版オファーの対象外の場合は、**[ユーザーに試用版アプリとサービスのインストールを許可する]** スイッチは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6d675-131">If your organization is ineligible for the Microsoft Teams Commercial Cloud Trial offer, you will not see the **Let users install trial apps and services** switch.</span></span>

## <a name="how-users-sign-up-for-the-trial"></a><span data-ttu-id="6d675-132">ユーザーが試用版にサインアップする方法</span><span class="sxs-lookup"><span data-stu-id="6d675-132">How users sign up for the trial</span></span>

<span data-ttu-id="6d675-133">対象となるユーザーは、Teams ([teams.microsoft.com](https://teams.microsoft.com)) にサインインして試用版オファーにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="6d675-133">Eligible users can sign up for the trial offer by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="6d675-134">試用版を開始するために、次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d675-134">They will see the following screen to start the trial.</span></span> 

![Teams IW 試用版のスタート ページのスクリーン ショット。](media/iw-trial-start-screen.png)

<span data-ttu-id="6d675-136">組織内のすべての試用版は、最初のユーザーが試用版にサインアップした日付と同じ開始日と終了日を共有します。</span><span class="sxs-lookup"><span data-stu-id="6d675-136">All trials within your organization share the same start and end dates, which is the date the first user signed up for the trial.</span></span> <span data-ttu-id="6d675-137">たとえば、ユーザー A が 2019 年 1 月 25 日に最初の試用を開始し、ユーザー B が 2019 年 6 月 3 日に試用を開始した場合は、2020 年 1 月 25 日にどちらのユーザーの試用も期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="6d675-137">For example, if user A starts the first trial on January 25, 2019 and user B starts a trial on June 3, 2019, both users' trial will expire on January 25, 2020.</span></span>

## <a name="manage-the-trial"></a><a name="manage-the-trial"></a><span data-ttu-id="6d675-138">試用版の管理</span><span class="sxs-lookup"><span data-stu-id="6d675-138">Manage the trial</span></span>

<span data-ttu-id="6d675-139">Teams 試用版は個々のエンド ユーザーが開始するためのものであり、エンド ユーザーの従業員に代わって Teams 試用版の提供を開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="6d675-139">The Teams Trial is meant to be initiated by individual end users, and you may not initiate the Teams Trial offer on behalf of end-user employees.</span></span>

<span data-ttu-id="6d675-140">管理者はエンド ユーザーが組織内で試用版アプリおよびサービスを要求できないようにすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="6d675-140">Admins can disable the ability for end users to claim trial apps and services within their organization.</span></span> <span data-ttu-id="6d675-141">現時点では、この記事で説明している試用版が、このカテゴリの唯一の試用版ですが、将来、別の同様のプログラムに適用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6d675-141">Currently, the trial described in this article is the only trial in this category, but it might apply to other similar programs in the future.</span></span> 

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="6d675-142">ユーザーが試用版アプリおよびサービスをインストールできないようにする</span><span class="sxs-lookup"><span data-stu-id="6d675-142">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="6d675-143">試用版のアプリとサービスをインストールするユーザー機能をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="6d675-143">You can turn off a user's ability to install trial apps and services.</span></span>

1. <span data-ttu-id="6d675-144">[[Microsoft 365 管理センター]](https://portal.office.com/adminportal/home)から **[設定]** > から **[組織の設定[** に移動し、\*\*[サービス] **を選択し、**[ユーザー所有のアプリとサービス] \*\*を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d675-144">From the [Microsoft 365 admin center](https://portal.office.com/adminportal/home), go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![管理センターの [サービス] ページのスクリーン ショット](media/iw-trial-services.png)

2. <span data-ttu-id="6d675-146">**[ユーザーに試用版アプリとサービスのインストールを許可する]** チェック ボックスをクリアします。</span><span class="sxs-lookup"><span data-stu-id="6d675-146">Clear the **Let users install trial apps and services** check box.</span></span>

    ![管理センターの [ユーザーが所有するアプリとサービス] ページのスクリーンショット](media/iw-trial-user-owned-apps-services.png)


### <a name="manage-trial-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="6d675-148">Teams が含まれているライセンスを持つユーザーの試用版利用可能性を管理する</span><span class="sxs-lookup"><span data-stu-id="6d675-148">Manage trial availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="6d675-149">Teams が含まれているライセンスの割り当てられたユーザーは、試用版の対象になりません。</span><span class="sxs-lookup"><span data-stu-id="6d675-149">A user who is assigned a license that includes Teams is not eligible for the trial.</span></span> <span data-ttu-id="6d675-150">Teams のサービス プランが有効なときには、そのユーザーは Teams にログインして使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d675-150">When the Teams service plan is enabled, the user can sign in and use Teams.</span></span> <span data-ttu-id="6d675-151">サービス プランが無効な場合、そのユーザーはログインすることも、試用版のオプションが表示されることもありません。</span><span class="sxs-lookup"><span data-stu-id="6d675-151">If the service plan is disabled, the user cannot sign in and is not presented with the trial option either.</span></span>

<span data-ttu-id="6d675-152">Teams へのアクセスをオフにするには:</span><span class="sxs-lookup"><span data-stu-id="6d675-152">To turn off access to Teams:</span></span>

1. <span data-ttu-id="6d675-153">Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d675-153">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="6d675-154">ユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="6d675-154">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="6d675-155">右側の **[製品ライセンス]** 行で、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d675-155">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="6d675-156">**[製品ライセンス]** ウィンドウで、**[オフ]** に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="6d675-156">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![管理センターの [製品ライセンス] ページのスクリーン ショット。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-already-claimed-the-trial"></a><span data-ttu-id="6d675-158">既に試用版を要求しているユーザーの Teams の利用可能性を管理する</span><span class="sxs-lookup"><span data-stu-id="6d675-158">Manage Teams availability for users who already claimed the trial</span></span>

<span data-ttu-id="6d675-159">ユーザーが Teams 試用版のライセンスを要求していた場合は、そのライセンスまたはサービス プランを削除することで試用版ライセンスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="6d675-159">If a user has claimed a Teams trial license, you can remove it by removing the license or service plan.</span></span>

<span data-ttu-id="6d675-160">試用版ライセンスをオフにするには:</span><span class="sxs-lookup"><span data-stu-id="6d675-160">To turn off the trial license:</span></span>

1. <span data-ttu-id="6d675-161">Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d675-161">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="6d675-162">ユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="6d675-162">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="6d675-163">右側の **[製品ライセンス]** 行で、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d675-163">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="6d675-164">**[製品ライセンス]** ウィンドウで、**[オフ]** に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="6d675-164">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![[ライセンス] ウィンドウの Teams 試用版ライセンスの設定を示すスクリーンショット](media/iW-trial-enable-4.png)
    
    >[!Note]
    ><span data-ttu-id="6d675-166">Microsoft Teams の試用版の切り替えスイッチは、組織内の最初のユーザーが試用版にサインアップした後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d675-166">The Microsoft Teams Trial toggle switch will appear after the first user in the organization signs up for the trial.</span></span>

### <a name="manage-teams-for-users-who-have-the-trial-license"></a><span data-ttu-id="6d675-167">試用版ライセンスを持つユーザーの Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="6d675-167">Manage Teams for users who have the trial license</span></span>

<span data-ttu-id="6d675-168">試用版ライセンスを持っているユーザーは、通常の有料ライセンスを持っているユーザーと同じように管理できます。</span><span class="sxs-lookup"><span data-stu-id="6d675-168">You can manage users who have a trial license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="6d675-169">詳細については、[組織のMicrosoft Teams 設定の管理](enable-features-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d675-169">For more information, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-trial-license"></a><span data-ttu-id="6d675-170">試用版ライセンスからユーザーをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="6d675-170">Upgrade users from the trial license</span></span>

<span data-ttu-id="6d675-171">試用版ライセンスからユーザーをアップグレードするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6d675-171">To upgrade users from the trial license, do the following:</span></span>

1. <span data-ttu-id="6d675-172">Teams が含まれているサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="6d675-172">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="6d675-173">ユーザーから Teams 試用版のサブスクリプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="6d675-173">Remove the Teams trial subscription from the user.</span></span>

3. <span data-ttu-id="6d675-174">新しく購入したライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6d675-174">Assign the newly purchased license.</span></span>

<span data-ttu-id="6d675-175">詳細については、「[Microsoft Teams サービスのサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d675-175">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="6d675-176">試用期間が終了し、Teams を含むサブスクリプションにユーザーがすぐにアップグレードされない場合は、ユーザー データは削除されません。</span><span class="sxs-lookup"><span data-stu-id="6d675-176">If the trial ends and a user is not immediately upgraded to a subscription that includes teams, the user data is not removed.</span></span> <span data-ttu-id="6d675-177">ユーザーは引き続き Azure Active Directory に残り、Teams 内のすべてのデータが残されたままになります。</span><span class="sxs-lookup"><span data-stu-id="6d675-177">The user still exists in Azure Active Directory and all data within Teams still remains.</span></span> <span data-ttu-id="6d675-178">ユーザーに新しいライセンスが割り当てられると、Teams の機能は再び有効になり、すべてのコンテンツが残ります。</span><span class="sxs-lookup"><span data-stu-id="6d675-178">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist.</span></span> 

### <a name="remove-a-legacy-microsoft-teams-trial-license"></a><span data-ttu-id="6d675-179">従来の Microsoft Teams 試用版ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="6d675-179">Remove a legacy Microsoft Teams Trial license</span></span>

<span data-ttu-id="6d675-180">2019 年 4 月 22 日の時点で、ユーザーは Microsoft Teams の商用クラウドの試用版ライセンスの要求を開始できます。</span><span class="sxs-lookup"><span data-stu-id="6d675-180">As of April 22, 2019, users can begin claiming the latest Microsoft Teams Commercial Cloud Trial license.</span></span> <span data-ttu-id="6d675-181">従来の試用版ライセンスから最新の試用版ライセンスへと組織内のユーザーを移行させる場合、まず各ユーザーの従来の Microsoft Teams 試用版ライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d675-181">If you would like to move users in your organization off of the legacy trial license and onto the latest one, you will need to first remove the legacy Microsoft Teams Trial license from each user.</span></span> <span data-ttu-id="6d675-182">従来のライセンスを削除すると、影響を受けた各ユーザーは、更新済みの Microsoft Teams の商用クラウドの試用版ライセンスを要求できます。</span><span class="sxs-lookup"><span data-stu-id="6d675-182">Once the legacy license is removed, each affected user can claim the updated Microsoft Teams Commercial Cloud Trial license.</span></span>

- <span data-ttu-id="6d675-183">Powershell を用いてこのライセンスを削除する場合は、次を参照してください :「[Microsoft 365 または Office 365 PowerShell を使用してユーザー アカウントからライセンスを削除する](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)」</span><span class="sxs-lookup"><span data-stu-id="6d675-183">If you would like to remove this license via PowerShell, see: [Remove licenses from user accounts with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="6d675-184">管理ポータルからこのライセンスを削除する場合は、「[組織からユーザーを削除する](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d675-184">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>
