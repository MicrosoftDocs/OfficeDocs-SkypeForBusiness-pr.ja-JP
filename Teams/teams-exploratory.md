---
title: Microsoft Teams Exploratory エクスペリエンスを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Microsoft Teams ライセンスが付与されていない Office 365 ユーザーは、Exploratory Teams ライセンスを開始できます。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4991945d47ecda85964068530118bcf3ef1f616a
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43749794"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="83a4b-103">Microsoft Teams Exploratory ライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="83a4b-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="83a4b-104">Microsoft Teams Exploratory エクスペリエンスを使用すると、Azure Active Directory (AAD) を持ち、Teams のライセンスを取得していない組織内のユーザーは、Teams の Exploratory エクスペリエンスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (AAD) and are not licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="83a4b-105">管理者は組織内のユーザーに対して、この機能をオンまたはオフに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="83a4b-106">以前の [Microsoft の商用クラウド試用版](iw-trial-teams.md) は、 Teams Exploratory エクスペリエンスに変更になりました。</span><span class="sxs-lookup"><span data-stu-id="83a4b-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="83a4b-107">Teams Exploratory エクスペリエンスの内容</span><span class="sxs-lookup"><span data-stu-id="83a4b-107">What's in the Teams Exploratory experience?</span></span>

<span data-ttu-id="83a4b-108">Teams Exploratory エクスペリエンスの一部として管理者に表示されるサービス プランは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="83a4b-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>
 - <span data-ttu-id="83a4b-109">Exchange Online (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="83a4b-109">Exchange Online (Plan 1)</span></span>
 - <span data-ttu-id="83a4b-110">Office 365 のフロー</span><span class="sxs-lookup"><span data-stu-id="83a4b-110">Flow for Office 365</span></span>
 - <span data-ttu-id="83a4b-111">MyAnalytics を利用した分析情報</span><span class="sxs-lookup"><span data-stu-id="83a4b-111">Insights by MyAnalytics</span></span>
 - <span data-ttu-id="83a4b-112">Microsoft Forms (プラン E1)</span><span class="sxs-lookup"><span data-stu-id="83a4b-112">Microsoft Forms (Plan E1)</span></span>
 - <span data-ttu-id="83a4b-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="83a4b-113">Microsoft Planner</span></span>
 - <span data-ttu-id="83a4b-114">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="83a4b-114">Microsoft Search</span></span>
 - <span data-ttu-id="83a4b-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="83a4b-115">Microsoft StaffHub</span></span>
 - <span data-ttu-id="83a4b-116">Microsoft Stream for O365 E1 SKU</span><span class="sxs-lookup"><span data-stu-id="83a4b-116">Microsoft Stream for O365 E1 SKU</span></span>
 - <span data-ttu-id="83a4b-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="83a4b-117">Microsoft Teams</span></span>
 - <span data-ttu-id="83a4b-118">Mobile Device Management for Office 365</span><span class="sxs-lookup"><span data-stu-id="83a4b-118">Mobile Device Management for Office 365</span></span>
 - <span data-ttu-id="83a4b-119">Office Mobile Apps for Office 365</span><span class="sxs-lookup"><span data-stu-id="83a4b-119">Office Mobile Apps for Office 365</span></span> 
 - <span data-ttu-id="83a4b-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="83a4b-120">Office Online</span></span>
 - <span data-ttu-id="83a4b-121">Office 365 向けの PowerApps</span><span class="sxs-lookup"><span data-stu-id="83a4b-121">PowerApps for Office 365</span></span>
 - <span data-ttu-id="83a4b-122">SharePoint Online (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="83a4b-122">SharePoint Online (Plan 1)</span></span>
 - <span data-ttu-id="83a4b-123">Sway</span><span class="sxs-lookup"><span data-stu-id="83a4b-123">Sway</span></span>
 - <span data-ttu-id="83a4b-124">To-Do (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="83a4b-124">To-Do (Plan 1)</span></span>
 - <span data-ttu-id="83a4b-125">Whiteboard (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="83a4b-125">Whiteboard (Plan 1)</span></span>
 - <span data-ttu-id="83a4b-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="83a4b-126">Yammer Enterprise</span></span>


## <a name="whos-eligible"></a><span data-ttu-id="83a4b-127">対象者</span><span class="sxs-lookup"><span data-stu-id="83a4b-127">Who's eligible?</span></span>

<span data-ttu-id="83a4b-128">ユーザーが管理対象の AAD ドメインのメール アドレスを持っており、現在 Teams のライセンスを持っていないかライセンスを割り当てられていない場合は、このエクスペリエンスの対象となります。</span><span class="sxs-lookup"><span data-stu-id="83a4b-128">As long as the user has a managed AAD domain email address and currently does not have/haven't been assigned a Teams license, they are eligible for this experience.</span></span> <span data-ttu-id="83a4b-129">たとえば、ユーザーが Office 365 Business (Teams を含まない) を持っている場合、Teams Exploratory エクスペリエンスの対象になります。</span><span class="sxs-lookup"><span data-stu-id="83a4b-129">For example, if a user has Office 365 Business (which doesn't include Teams), they're eligible for the Teams Exploratory experience.</span></span>

<span data-ttu-id="83a4b-130">ユーザーが (Microsoft 365 管理センターで) アプリや試用版にサインアップできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a4b-130">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="83a4b-131">詳細については、この記事で後述する「[Teams Exploratory エクスペリエンスを管理する](#manage-the-teams-exploratory-experience)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83a4b-131">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span> 


## <a name="who-isnt-eligible"></a><span data-ttu-id="83a4b-132">対象外</span><span class="sxs-lookup"><span data-stu-id="83a4b-132">Who isn't eligible</span></span>

<span data-ttu-id="83a4b-133">シンジケート パートナー顧客である場合、または GCC、GCC High、DoD、または教育機関の顧客である場合、組織は試用版の対象ではありません。</span><span class="sxs-lookup"><span data-stu-id="83a4b-133">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="83a4b-134">ユーザーが Teams Exploratory エクスペリエンスにサインアップする方法</span><span class="sxs-lookup"><span data-stu-id="83a4b-134">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="83a4b-135">対象となるユーザーは、Teams ([teams.microsoft.com](https://teams.microsoft.com)) にサインインして Teams Exploratory エクスペリエンスにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-135">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="83a4b-136">これらのライセンスは自動的に割り当てられ、組織内の誰かが初めて Teams Exploratory エクスペリエンスを開始すると、テナント管理者に、メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-136">They will be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="83a4b-137">Teams Exploratory エクスペリエンスを管理する</span><span class="sxs-lookup"><span data-stu-id="83a4b-137">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="83a4b-138">Teams Exploratory エクスペリエンスは個々のエンド ユーザーが開始するためのものであり、エンド ユーザーの従業員に代わってこのサービスを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="83a4b-138">The Teams Exploratory experience is meant to be initiated by individual end users, and you may not initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="83a4b-139">Teams Exploratory エクスペリエンスには Exchange Online ライセンスが付属していますが、管理者が割り当てるまでユーザーに割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="83a4b-139">The Teams Exploratory experience comes with an Exchange Online license but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="83a4b-140">ユーザーにまだ Exchange ライセンスがなく、管理者がまだ Exchange Online ライセンスを割り当てていない場合、ユーザーは Teams で会議をスケジュールできず、他の Teams の機能を利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83a4b-140">If the user doesn't have an Exchange license already and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and may be missing other Teams functionality.</span></span>

<span data-ttu-id="83a4b-141">管理者は、**試用版のアプリとサービス** スイッチを使用して、エンド ユーザーが組織内で Teams Exploratory エクスペリエンスを実行できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-141">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>


### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="83a4b-142">ユーザーが試用版アプリおよびサービスをインストールできないようにする</span><span class="sxs-lookup"><span data-stu-id="83a4b-142">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="83a4b-143">ユーザーが試用版アプリとサービスをインストールできるようにする機能をオフにすると、そのユーザーは Teams Exploratory エクスペリエンスを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="83a4b-143">You can turn off a user's ability to install trial apps and services, would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="83a4b-144">[[Microsoft 365 管理センター]](https://portal.office.com/adminportal/home) から、**[設定]** > **[設定]** に移動し、**[サービス]** を選択し、**[ユーザーが所有するアプリとサービス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="83a4b-144">From the [Microsoft 365 admin center](https://portal.office.com/adminportal/home), go to **Settings** > **Settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![管理センターの [サービス] ページのスクリーン ショット](media/iw-trial-services.png)

2. <span data-ttu-id="83a4b-146">**[ユーザーに試用版アプリとサービスのインストールを許可する]** チェック ボックスをクリアします。</span><span class="sxs-lookup"><span data-stu-id="83a4b-146">Clear the **Let users install trial apps and services** check box.</span></span>

    ![管理センターの [ユーザーが所有するアプリとサービス] ページのスクリーンショット](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="83a4b-148">組織が Teams Exploratory エクスペリエンスの対象外の場合は、「**ユーザーが試用版アプリとサービスをインストールできるようにする**」オプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="83a4b-148">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="83a4b-149">Teams が含まれているライセンスを持つユーザーの利用可能性を管理する</span><span class="sxs-lookup"><span data-stu-id="83a4b-149">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="83a4b-150">Teams が含まれているライセンスの割り当てられたユーザーは、Teams Exploratory エクスペリエンスの対象になりません。</span><span class="sxs-lookup"><span data-stu-id="83a4b-150">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="83a4b-151">Teams のサービス プランが有効なときには、そのユーザーは Teams にログインして使用できます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-151">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="83a4b-152">サービス プランが無効になっている場合、ユーザーはサインインできず、Teams Exploratory エクスペリエンスは利用できません。</span><span class="sxs-lookup"><span data-stu-id="83a4b-152">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span>

<span data-ttu-id="83a4b-153">Teams へのアクセスをオフにするには:</span><span class="sxs-lookup"><span data-stu-id="83a4b-153">To turn off access to Teams:</span></span>

1. <span data-ttu-id="83a4b-154">Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="83a4b-154">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="83a4b-155">ユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="83a4b-155">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="83a4b-156">右側の **[製品ライセンス]** 行で、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="83a4b-156">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="83a4b-157">**[製品ライセンス]** ウィンドウで、**[オフ]** に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-157">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![管理センターの [製品ライセンス] ページのスクリーン ショット。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="83a4b-159">Teams Exploratory エクスペリエンスをすでに使用しているユーザーの Teams の可用性を管理する</span><span class="sxs-lookup"><span data-stu-id="83a4b-159">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="83a4b-160">ユーザーが Teams Exploratory エクスペリエンスを実行している場合は、ライセンスまたはサービス プランを削除することでそれをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-160">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span>

<span data-ttu-id="83a4b-161">Teams Exploratory エクスペリエンスのライセンスをオフにするには:</span><span class="sxs-lookup"><span data-stu-id="83a4b-161">To turn off the the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="83a4b-162">Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="83a4b-162">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="83a4b-163">ユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="83a4b-163">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="83a4b-164">右側の **[製品ライセンス]** 行で、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="83a4b-164">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="83a4b-165">[**製品ライセンス**] ウィンドウで、この Exploratory ライセンスのトグルを [**オフ**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-165">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>
   
    >[!Note]
    ><span data-ttu-id="83a4b-166">Teams Exploratory のトグル スイッチは、組織の最初のユーザーが Teams Exploratory エクスペリエンスを起動した後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-166">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="83a4b-167">Teams Exploratory ライセンスを持つユーザーの Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="83a4b-167">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="83a4b-168">Teams Exploratory ライセンスを持つユーザーは、通常の有料ライセンスを持つユーザーと同じように管理できます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-168">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="83a4b-169">詳細については、「[組織の Teams 設定を管理する](enable-features-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83a4b-169">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="83a4b-170">Teams Exploratory ライセンスからユーザーをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="83a4b-170">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="83a4b-171">Teams Exploratory ライセンスからユーザーをアップグレードするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="83a4b-171">To upgrade users from the Teams Exploratory license, do the following:</span></span>

1. <span data-ttu-id="83a4b-172">Teams が含まれているサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="83a4b-172">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="83a4b-173">ユーザーから Teams Exploratory のサブスクリプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="83a4b-173">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="83a4b-174">新しく購入したライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-174">Assign the newly purchased license.</span></span>

<span data-ttu-id="83a4b-175">詳細については、「[Microsoft Teams 用の Office 365 ライセンス](Office-365-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83a4b-175">For more information, see [Office 365 licensing for Microsoft Teams](Office-365-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="83a4b-176">Teams Exploratory ライセンスが終了し、ユーザーが Teams を含むサブスクリプションにすぐにアップグレードされない場合は、ユーザー データは削除されません。</span><span class="sxs-lookup"><span data-stu-id="83a4b-176">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, the user data is not removed.</span></span> <span data-ttu-id="83a4b-177">ユーザーは引き続き Azure Active Directory に残り、Teams 内のすべてのデータが残されたままになります。</span><span class="sxs-lookup"><span data-stu-id="83a4b-177">The user still exists in Azure Active Directory and all data within Teams still remains.</span></span> <span data-ttu-id="83a4b-178">ユーザーに新しいライセンスが割り当てられると、Teams の機能は再び有効になり、すべてのコンテンツが残ります。</span><span class="sxs-lookup"><span data-stu-id="83a4b-178">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist.</span></span> 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="83a4b-179">従来の Microsoft Teams の商用クラウドの試用版のライセンスはどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="83a4b-179">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses?</span></span>

<span data-ttu-id="83a4b-180">2020 年 2 月から、対象ユーザーは最新の Microsoft Teams Exploratory エクスペリエンスの使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-180">As of February, 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="83a4b-181">従来の Teams の商用クラウドの試用版のライセンスはすべて、試用版の有効期限が切れる前に自動的に新しいサービスに変換されます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-181">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="83a4b-182">Teams Exploratory ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="83a4b-182">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="83a4b-183">Powershell を使用してこのライセンスを削除する場合は、次を参照してください :「[Office 365 PowerShell を使用してユーザー アカウントからライセンスを削除する](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)」</span><span class="sxs-lookup"><span data-stu-id="83a4b-183">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="83a4b-184">管理ポータルからこのライセンスを削除する場合は、次を参照してください :「[一般法人向け Office 365 のユーザーからライセンスを削除する](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)」</span><span class="sxs-lookup"><span data-stu-id="83a4b-184">If you would like to remove this license through the admin portal, see: [Remove licenses from users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="83a4b-185">Teams Exploratory エクスペリエンスの利用可能期間</span><span class="sxs-lookup"><span data-stu-id="83a4b-185">How long does the Teams Exploratory experience last?</span></span>

<span data-ttu-id="83a4b-186">Microsoft Teams Exploratory エクスペリエンスは、次の**契約応当日**、または 2021 年 1 月以降の**更新日**まで追加料金なしで利用可能です。</span><span class="sxs-lookup"><span data-stu-id="83a4b-186">The Microsoft Teams Exploratory experience is available at no additional cost until your next **agreement anniversary** or **renewal** on or after January 2021.</span></span> <span data-ttu-id="83a4b-187">この時点で、Microsoft Exploratory エクスペリエンス ライセンスのエンド ユーザーは、Teams を含む有料のライセンスに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a4b-187">At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams.</span></span> <span data-ttu-id="83a4b-188">その後に開始したすべての Microsoft Exploratory エクスペリエンス ライセンスは、次の**契約応当日**、または**更新日**まで追加料金なしで引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="83a4b-188">Any Microsoft Exploratory experience licenses initiated after that will remain available at no additional cost until your next **anniversary** or **renewal** cycle.</span></span> 

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-my-anniversary-or-renewal-date"></a><span data-ttu-id="83a4b-189">エンド ユーザーが、Microsoft Teams Exploratory エクスペリエンスを契約日、または更新日の前に開始した場合は、どうなりますか?</span><span class="sxs-lookup"><span data-stu-id="83a4b-189">What happens if an end user initiates the Microsoft Teams Exploratory experience just before my anniversary or renewal date?</span></span>

<span data-ttu-id="83a4b-190">Microsoft Teams Exploratory エクスペリエンス ライセンスの開始が、**契約応当日**、または**更新日**の 90 日以内であれば、次の契約応当日、更新日まで有料のライセンスに移行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="83a4b-190">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** will not be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span> 
