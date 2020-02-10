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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7aa3969d3943598c8e5657e1fcb94730179f57fe
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837687"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="a736f-103">Microsoft Teams Exploratory ライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="a736f-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="a736f-104">Microsoft Teams Exploratory エクスペリエンスを使用すると、Azure Active Directory (AAD) を持ち、Teams のライセンスを取得していない組織内のユーザーは、Teams の Exploratory エクスペリエンスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="a736f-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (AAD) and are not licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="a736f-105">管理者は組織内のユーザーに対して、この機能をオンまたはオフに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="a736f-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="a736f-106">以前の [Microsoft の商用クラウドの試用版](iw-trial-teams.md)は、Teams Exploratory エクスペリエンスと呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="a736f-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now called The Teams Exploratory experience.</span></span>

<span data-ttu-id="a736f-107">[!INCLUDE [preview-feature](includes/preview-feature.md)] このエクスペリエンスは、2020 年 1 月中旬から利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="a736f-107">[!INCLUDE [preview-feature](includes/preview-feature.md)] This experience will be available starting in mid January, 2020.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="a736f-108">Teams Exploratory エクスペリエンスの内容</span><span class="sxs-lookup"><span data-stu-id="a736f-108">What's in the Teams Exploratory experience?</span></span>

<span data-ttu-id="a736f-109">Teams Exploratory エクスペリエンスに含まれるサービス プランは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a736f-109">The service plans included in the Teams Exploratory experience are:</span></span>
 - <span data-ttu-id="a736f-110">Exchange Online (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="a736f-110">Exchange Online (Plan 1)</span></span>
 - <span data-ttu-id="a736f-111">Office 365 のフロー</span><span class="sxs-lookup"><span data-stu-id="a736f-111">Flow for Office 365</span></span>
 - <span data-ttu-id="a736f-112">MyAnalytics を利用した分析情報</span><span class="sxs-lookup"><span data-stu-id="a736f-112">Insights by MyAnalytics</span></span>
 - <span data-ttu-id="a736f-113">Microsoft Forms (プラン E1)</span><span class="sxs-lookup"><span data-stu-id="a736f-113">Microsoft Forms (Plan E1)</span></span>
 - <span data-ttu-id="a736f-114">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="a736f-114">Microsoft Planner</span></span>
 - <span data-ttu-id="a736f-115">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="a736f-115">Microsoft Search</span></span>
 - <span data-ttu-id="a736f-116">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="a736f-116">Microsoft StaffHub</span></span>
 - <span data-ttu-id="a736f-117">Microsoft Stream for O365 E1 SKU</span><span class="sxs-lookup"><span data-stu-id="a736f-117">Microsoft Stream for O365 E1 SKU</span></span>
 - <span data-ttu-id="a736f-118">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a736f-118">Microsoft Teams</span></span>
 - <span data-ttu-id="a736f-119">Mobile Device Management for Office 365</span><span class="sxs-lookup"><span data-stu-id="a736f-119">Mobile Device Management for Office 365</span></span>
 - <span data-ttu-id="a736f-120">Office Mobile Apps for Office 365</span><span class="sxs-lookup"><span data-stu-id="a736f-120">Office Mobile Apps for Office 365</span></span> 
 - <span data-ttu-id="a736f-121">Office Online</span><span class="sxs-lookup"><span data-stu-id="a736f-121">Office Online</span></span>
 - <span data-ttu-id="a736f-122">Office 365 向けの PowerApps</span><span class="sxs-lookup"><span data-stu-id="a736f-122">PowerApps for Office 365</span></span>
 - <span data-ttu-id="a736f-123">SharePoint Online (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="a736f-123">SharePoint Online (Plan 1)</span></span>
 - <span data-ttu-id="a736f-124">Sway</span><span class="sxs-lookup"><span data-stu-id="a736f-124">Sway</span></span>
 - <span data-ttu-id="a736f-125">To-Do (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="a736f-125">To-Do (Plan 1)</span></span>
 - <span data-ttu-id="a736f-126">Whiteboard (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="a736f-126">Whiteboard (Plan 1)</span></span>
 - <span data-ttu-id="a736f-127">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="a736f-127">Yammer Enterprise</span></span>


## <a name="whos-eligible"></a><span data-ttu-id="a736f-128">対象者</span><span class="sxs-lookup"><span data-stu-id="a736f-128">Who's eligible?</span></span>

<span data-ttu-id="a736f-129">ユーザーが (Microsoft 365 管理センターで) アプリや試用版にサインアップできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a736f-129">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="a736f-130">詳細については、この記事で後述する「[Teams Exploratory エクスペリエンスを管理する](#manage-the-teams-exploratory-experience)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a736f-130">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span> 

<span data-ttu-id="a736f-131">Teams を含む Office 365 ライセンスを持っていないユーザーは、Teams Exploratory エクスペリエンスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="a736f-131">Users who don't have an Office 365 license that includes Teams can initiate the Teams Exploratory experience.</span></span> <span data-ttu-id="a736f-132">たとえば、ユーザーが Office 365 Business (Teams を含まない) を持っている場合、ユーザーは Teams Exploratory エクスペリエンスの対象になります。</span><span class="sxs-lookup"><span data-stu-id="a736f-132">For example, if a user has Office 365 Business (which doesn't include Teams), they're eligible for the Teams Exploratory experience.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="a736f-133">対象外</span><span class="sxs-lookup"><span data-stu-id="a736f-133">Who isn't eligible</span></span>

<span data-ttu-id="a736f-134">シンジケート パートナー顧客である場合、または GCC、GCC High、DoD、または教育機関の顧客である場合、組織は試用版の対象ではありません。</span><span class="sxs-lookup"><span data-stu-id="a736f-134">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="a736f-135">ユーザーが Teams Exploratory エクスペリエンスにサインアップする方法</span><span class="sxs-lookup"><span data-stu-id="a736f-135">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="a736f-136">対象となるユーザーは、Teams ([teams.microsoft.com](https://teams.microsoft.com)) にサインインして Teams Exploratory エクスペリエンスにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="a736f-136">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="a736f-137">これらのライセンスは自動的に割り当てられ、組織内の誰かが初めて Teams Exploratory エクスペリエンスを開始すると、テナント管理者に、メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="a736f-137">They will be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="a736f-138">Teams Exploratory エクスペリエンスを管理する</span><span class="sxs-lookup"><span data-stu-id="a736f-138">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="a736f-139">Teams Exploratory エクスペリエンスは個々のエンド ユーザーが開始するためのものであり、エンド ユーザーの従業員に代わってこのサービスを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="a736f-139">The Teams Exploratory experience is meant to be initiated by individual end users, and you may not initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="a736f-140">Teams Exploratory エクスペリエンスには Exchange Online ライセンスが付属していますが、管理者が割り当てるまでユーザーに割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="a736f-140">The Teams Exploratory experience comes with an Exchange Online license but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="a736f-141">ユーザーにまだ Exchange ライセンスがなく、管理者がまだ Exchange Online ライセンスを割り当てていない場合、ユーザーは Teams で会議をスケジュールできず、他の Teams の機能を利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a736f-141">If the user doesn't have an Exchange license already and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and may be missing other Teams functionality.</span></span>

<span data-ttu-id="a736f-142">管理者は、**試用版のアプリとサービス** スイッチを使用して、エンド ユーザーが組織内で Teams Exploratory エクスペリエンスを実行できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a736f-142">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>


### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="a736f-143">ユーザーが試用版アプリおよびサービスをインストールできないようにする</span><span class="sxs-lookup"><span data-stu-id="a736f-143">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="a736f-144">試用版アプリとサービスをインストールするユーザーの機能をオフにすると、ユーザーが Teams Exploratory エクスペリエンスを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a736f-144">You can turn off a user’s ability to install trial apps and services, would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="a736f-145">[[Microsoft 365 管理センター]](https://portal.office.com/adminportal/home) から、**[設定]** > **[設定]** に移動し、**[サービス]** を選択し、**[ユーザーが所有するアプリとサービス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a736f-145">From the [Microsoft 365 admin center](https://portal.office.com/adminportal/home), go to **Settings** > **Settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![管理センターの [サービス] ページのスクリーン ショット](media/iw-trial-services.png)

2. <span data-ttu-id="a736f-147">**[ユーザーに試用版アプリとサービスのインストールを許可する]** チェック ボックスをクリアします。</span><span class="sxs-lookup"><span data-stu-id="a736f-147">Clear the **Let users install trial apps and services** check box.</span></span>

    ![管理センターの [ユーザーが所有するアプリとサービス] ページのスクリーンショット](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="a736f-149">組織が Teams Exploratory エクスペリエンスの対象外の場合は、「**ユーザーが試用版アプリとサービスをインストールできるようにする**」オプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a736f-149">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="a736f-150">Teams が含まれているライセンスを持つユーザーの利用可能性を管理する</span><span class="sxs-lookup"><span data-stu-id="a736f-150">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="a736f-151">Teams が含まれているライセンスの割り当てられたユーザーは、Teams Exploratory エクスペリエンスの対象になりません。</span><span class="sxs-lookup"><span data-stu-id="a736f-151">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="a736f-152">Teams のサービス プランが有効なときには、そのユーザーは Teams にログインして使用できます。</span><span class="sxs-lookup"><span data-stu-id="a736f-152">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="a736f-153">サービス プランが無効になっている場合、ユーザーはサインインできず、Teams Exploratory エクスペリエンスは利用できません。</span><span class="sxs-lookup"><span data-stu-id="a736f-153">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span>

<span data-ttu-id="a736f-154">Teams へのアクセスをオフにするには:</span><span class="sxs-lookup"><span data-stu-id="a736f-154">To turn off access to Teams:</span></span>

1. <span data-ttu-id="a736f-155">Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a736f-155">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="a736f-156">ユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a736f-156">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="a736f-157">右側の **[製品ライセンス]** 行で、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a736f-157">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="a736f-158">**[製品ライセンス]** ウィンドウで、**[オフ]** に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a736f-158">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![管理センターの [製品ライセンス] ページのスクリーン ショット。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="a736f-160">Teams Exploratory エクスペリエンスをすでに使用しているユーザーの Teams の可用性を管理する</span><span class="sxs-lookup"><span data-stu-id="a736f-160">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="a736f-161">ユーザーが Teams Exploratory エクスペリエンスを実行している場合は、ライセンスまたはサービス プランを削除することでそれをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="a736f-161">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span>

<span data-ttu-id="a736f-162">Teams Exploratory エクスペリエンスのライセンスをオフにするには:</span><span class="sxs-lookup"><span data-stu-id="a736f-162">To turn off the the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="a736f-163">Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a736f-163">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="a736f-164">ユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a736f-164">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="a736f-165">右側の **[製品ライセンス]** 行で、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a736f-165">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="a736f-166">[**製品ライセンス**] ウィンドウで、この Exploratory ライセンスのトグルを [**オフ**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a736f-166">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>
   
    >[!Note]
    ><span data-ttu-id="a736f-167">Teams Exploratory のトグル スイッチは、組織の最初のユーザーが Teams Exploratory エクスペリエンスを起動した後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a736f-167">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="a736f-168">Teams Exploratory ライセンスを持つユーザーの Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="a736f-168">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="a736f-169">Teams Exploratory ライセンスを持つユーザーは、通常の有料ライセンスを持つユーザーと同じように管理できます。</span><span class="sxs-lookup"><span data-stu-id="a736f-169">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="a736f-170">詳細については、「[組織の Teams 設定を管理する](enable-features-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a736f-170">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="a736f-171">Teams Exploratory ライセンスからユーザーをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="a736f-171">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="a736f-172">Teams Exploratory ライセンスからユーザーをアップグレードするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a736f-172">To upgrade users from the Teams Exploratory license, do the following:</span></span>

1. <span data-ttu-id="a736f-173">Teams が含まれているサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="a736f-173">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="a736f-174">ユーザーから Teams Exploratory のサブスクリプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="a736f-174">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="a736f-175">新しく購入したライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a736f-175">Assign the newly purchased license.</span></span>

<span data-ttu-id="a736f-176">詳細については、「[Microsoft Teams 用の Office 365 ライセンス](Office-365-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a736f-176">For more information, see [Office 365 licensing for Microsoft Teams](Office-365-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a736f-177">Teams Exploratory ライセンスが終了し、Teams を含むサブスクリプションにユーザーがすぐにアップグレードされない場合は、ユーザー データは削除されません。</span><span class="sxs-lookup"><span data-stu-id="a736f-177">If the Teams Exploratory license ends and a user is not immediately upgraded to a subscription that includes Teams, the user data is not removed.</span></span> <span data-ttu-id="a736f-178">ユーザーは引き続き Azure Active Directory に残り、Teams 内のすべてのデータが残されたままになります。</span><span class="sxs-lookup"><span data-stu-id="a736f-178">The user still exists in Azure Active Directory and all data within Teams still remains.</span></span> <span data-ttu-id="a736f-179">ユーザーに新しいライセンスが割り当てられると、Teams の機能は再び有効になり、すべてのコンテンツが残ります。</span><span class="sxs-lookup"><span data-stu-id="a736f-179">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist.</span></span> 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="a736f-180">従来の Microsoft Teams の商用クラウドの試用版のライセンスはどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="a736f-180">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses?</span></span>

<span data-ttu-id="a736f-181">2020 年 1 月中旬から、対象ユーザーは最新の Microsoft Teams Exploratory エクスペリエンスの使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="a736f-181">As of mid January, 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="a736f-182">従来の Teams の商用クラウドの試用版のライセンスはすべて、試用版の有効期限が切れる前に自動的に新しいサービスに変換されます。</span><span class="sxs-lookup"><span data-stu-id="a736f-182">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="a736f-183">Teams Exploratory ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="a736f-183">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="a736f-184">Powershell を使用してこのライセンスを削除する場合は、次を参照してください :「[Office 365 PowerShell を使用してユーザー アカウントからライセンスを削除する](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)」</span><span class="sxs-lookup"><span data-stu-id="a736f-184">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="a736f-185">管理ポータルからこのライセンスを削除する場合は、次を参照してください :「[一般法人向け Office 365 のユーザーからライセンスを削除する](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)」</span><span class="sxs-lookup"><span data-stu-id="a736f-185">If you would like to remove this license through the admin portal, see: [Remove licenses from users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)</span></span>
