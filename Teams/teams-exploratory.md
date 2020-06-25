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
description: Microsoft Teams ライセンスが付与されていない Microsoft 365 または Office 365 ユーザーは、Exploratory Teams ライセンスを開始できます。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99017e63ae784c7c4271454829198c7c06ecfe8e
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868464"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="7fd53-103">Microsoft Teams Exploratory ライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="7fd53-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="7fd53-104">Microsoft Teams Exploratory エクスペリエンスを使用すると、Azure Active Directory (AAD) を持ち、Teams のライセンスを取得していない組織内のユーザーは、Teams の Exploratory エクスペリエンスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (AAD) and are not licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="7fd53-105">管理者は組織内のユーザーに対して、この機能をオンまたはオフに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="7fd53-106">以前の [Microsoft の商用クラウド試用版](iw-trial-teams.md) は、 Teams Exploratory エクスペリエンスに変更になりました。</span><span class="sxs-lookup"><span data-stu-id="7fd53-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="7fd53-107">Teams Exploratory エクスペリエンスの内容</span><span class="sxs-lookup"><span data-stu-id="7fd53-107">What's in the Teams Exploratory experience?</span></span>

<span data-ttu-id="7fd53-108">Teams Exploratory エクスペリエンスの一部として管理者に表示されるサービス プランは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7fd53-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>
 - <span data-ttu-id="7fd53-109">Exchange Online (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="7fd53-109">Exchange Online (Plan 1)</span></span>
 - <span data-ttu-id="7fd53-110">Microsoft 365 または Office 365 のフロー</span><span class="sxs-lookup"><span data-stu-id="7fd53-110">Flow for Microsoft 365 or Office 365</span></span>
 - <span data-ttu-id="7fd53-111">MyAnalytics を利用した分析情報</span><span class="sxs-lookup"><span data-stu-id="7fd53-111">Insights by MyAnalytics</span></span>
 - <span data-ttu-id="7fd53-112">Microsoft Forms (プラン E1)</span><span class="sxs-lookup"><span data-stu-id="7fd53-112">Microsoft Forms (Plan E1)</span></span>
 - <span data-ttu-id="7fd53-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="7fd53-113">Microsoft Planner</span></span>
 - <span data-ttu-id="7fd53-114">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="7fd53-114">Microsoft Search</span></span>
 - <span data-ttu-id="7fd53-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="7fd53-115">Microsoft StaffHub</span></span>
 - <span data-ttu-id="7fd53-116">Microsoft Stream for Microsoft 365 E1 SKU および Office 365 E1 SKU</span><span class="sxs-lookup"><span data-stu-id="7fd53-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs</span></span>
 - <span data-ttu-id="7fd53-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7fd53-117">Microsoft Teams</span></span>
 - <span data-ttu-id="7fd53-118">Microsoft 365 または Office 365 のモバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="7fd53-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
 - <span data-ttu-id="7fd53-119">Office Mobile Apps for Office 365</span><span class="sxs-lookup"><span data-stu-id="7fd53-119">Office Mobile Apps for Office 365</span></span> 
 - <span data-ttu-id="7fd53-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="7fd53-120">Office Online</span></span>
 - <span data-ttu-id="7fd53-121">PowerApps for Microsoft 365 または Office 365</span><span class="sxs-lookup"><span data-stu-id="7fd53-121">PowerApps for Microsoft 365 or Office 365</span></span>
 - <span data-ttu-id="7fd53-122">SharePoint Online (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="7fd53-122">SharePoint Online (Plan 1)</span></span>
 - <span data-ttu-id="7fd53-123">Sway</span><span class="sxs-lookup"><span data-stu-id="7fd53-123">Sway</span></span>
 - <span data-ttu-id="7fd53-124">To-Do (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="7fd53-124">To-Do (Plan 1)</span></span>
 - <span data-ttu-id="7fd53-125">Whiteboard (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="7fd53-125">Whiteboard (Plan 1)</span></span>
 - <span data-ttu-id="7fd53-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="7fd53-126">Yammer Enterprise</span></span>


## <a name="whos-eligible"></a><span data-ttu-id="7fd53-127">対象者</span><span class="sxs-lookup"><span data-stu-id="7fd53-127">Who's eligible?</span></span>

<span data-ttu-id="7fd53-128">ユーザーが管理対象の AAD ドメインのメール アドレスを持っており、現在 Teams のライセンスを持っていないかライセンスを割り当てられていない場合は、このエクスペリエンスの対象となります。</span><span class="sxs-lookup"><span data-stu-id="7fd53-128">As long as the user has a managed AAD domain email address and currently does not have/haven't been assigned a Teams license, they are eligible for this experience.</span></span> <span data-ttu-id="7fd53-129">たとえば、ユーザーが Microsoft 365 Apps for business (Teams を含まない) を持っている場合、Teams Exploratory エクスペリエンスの対象になります。</span><span class="sxs-lookup"><span data-stu-id="7fd53-129">For example, if a user has Microsoft 365 Apps for business (which doesn't include Teams), they're eligible for the Teams Exploratory experience.</span></span>

<span data-ttu-id="7fd53-130">ユーザーが (Microsoft 365 管理センターで) アプリや試用版にサインアップできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd53-130">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="7fd53-131">詳細については、この記事で後述する「[Teams Exploratory エクスペリエンスを管理する](#manage-the-teams-exploratory-experience)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd53-131">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span> 


## <a name="who-isnt-eligible"></a><span data-ttu-id="7fd53-132">対象外</span><span class="sxs-lookup"><span data-stu-id="7fd53-132">Who isn't eligible</span></span>

<span data-ttu-id="7fd53-133">シンジケート パートナー顧客である場合、または GCC、GCC High、DoD、または教育機関の顧客である場合、組織は試用版の対象ではありません。</span><span class="sxs-lookup"><span data-stu-id="7fd53-133">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="7fd53-134">ユーザーが Teams Exploratory エクスペリエンスにサインアップする方法</span><span class="sxs-lookup"><span data-stu-id="7fd53-134">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="7fd53-135">対象となるユーザーは、Teams ([teams.microsoft.com](https://teams.microsoft.com)) にサインインして Teams Exploratory エクスペリエンスにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-135">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="7fd53-136">これらのライセンスは自動的に割り当てられ、組織内の誰かが初めて Teams Exploratory エクスペリエンスを開始すると、テナント管理者に、メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-136">They will be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="7fd53-137">Teams Exploratory エクスペリエンスを管理する</span><span class="sxs-lookup"><span data-stu-id="7fd53-137">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="7fd53-138">Teams Exploratory エクスペリエンスは個々のエンド ユーザーが開始するためのものであり、エンド ユーザーの従業員に代わってこのサービスを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="7fd53-138">The Teams Exploratory experience is meant to be initiated by individual end users, and you may not initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="7fd53-139">Teams Exploratory エクスペリエンスには Exchange Online ライセンスが付属していますが、管理者が割り当てるまでユーザーに割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="7fd53-139">The Teams Exploratory experience comes with an Exchange Online license but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="7fd53-140">ユーザーにまだ Exchange ライセンスがなく、管理者がまだ Exchange Online ライセンスを割り当てていない場合、ユーザーは Teams で会議をスケジュールできず、他の Teams の機能を利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7fd53-140">If the user doesn't have an Exchange license already and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and may be missing other Teams functionality.</span></span>

<span data-ttu-id="7fd53-141">管理者は、**試用版のアプリとサービス** スイッチを使用して、エンド ユーザーが組織内で Teams Exploratory エクスペリエンスを実行できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-141">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>


### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="7fd53-142">ユーザーが試用版アプリおよびサービスをインストールできないようにする</span><span class="sxs-lookup"><span data-stu-id="7fd53-142">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="7fd53-143">ユーザーが試用版アプリとサービスをインストールできるようにする機能をオフにすると、そのユーザーは Teams Exploratory エクスペリエンスを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7fd53-143">You can turn off a user's ability to install trial apps and services, would prevent the user from running the Teams Exploratory experience.</span></span> <span data-ttu-id="7fd53-144">管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="7fd53-144">You must have admin privileges.</span></span> <span data-ttu-id="7fd53-145">管理者の役割の詳細については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](teams-exploratory.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd53-145">To learn more about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](teams-exploratory.md)</span></span>

1. <span data-ttu-id="7fd53-146">[[Microsoft 365 管理センター]](https://portal.office.com/adminportal/home) から、**[設定]** > **[設定]** に移動し、**[サービス]** を選択し、**[ユーザーが所有するアプリとサービス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fd53-146">From the [Microsoft 365 admin center](https://portal.office.com/adminportal/home), go to **Settings** > **Settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![管理センターの [サービス] ページのスクリーン ショット](media/iw-trial-services.png)

2. <span data-ttu-id="7fd53-148">**[ユーザーに試用版アプリとサービスのインストールを許可する]** チェック ボックスをクリアします。</span><span class="sxs-lookup"><span data-stu-id="7fd53-148">Clear the **Let users install trial apps and services** check box.</span></span>

    ![管理センターの [ユーザーが所有するアプリとサービス] ページのスクリーンショット](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="7fd53-150">組織が Teams Exploratory エクスペリエンスの対象外の場合は、「**ユーザーが試用版アプリとサービスをインストールできるようにする**」オプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7fd53-150">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="7fd53-151">Teams が含まれているライセンスを持つユーザーの利用可能性を管理する</span><span class="sxs-lookup"><span data-stu-id="7fd53-151">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="7fd53-152">Teams が含まれているライセンスの割り当てられたユーザーは、Teams Exploratory エクスペリエンスの対象になりません。</span><span class="sxs-lookup"><span data-stu-id="7fd53-152">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="7fd53-153">Teams のサービス プランが有効なときには、そのユーザーは Teams にログインして使用できます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-153">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="7fd53-154">サービス プランが無効になっている場合、ユーザーはサインインできず、Teams Exploratory エクスペリエンスは利用できません。</span><span class="sxs-lookup"><span data-stu-id="7fd53-154">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="7fd53-155">管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="7fd53-155">You must have admin privileges.</span></span> 

<span data-ttu-id="7fd53-156">Teams へのアクセスをオフにするには:</span><span class="sxs-lookup"><span data-stu-id="7fd53-156">To turn off access to Teams:</span></span>

1. <span data-ttu-id="7fd53-157">[Microsoft 365 管理センター](https://portal.office.com/adminportal/home)で、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fd53-157">In the [Microsoft 365 admin center](https://portal.office.com/adminportal/home), select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="7fd53-158">ユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="7fd53-158">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="7fd53-159">右側の **[製品ライセンス]** 行で、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fd53-159">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="7fd53-160">**[製品ライセンス]** ウィンドウで、**[オフ]** に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-160">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![管理センターの [製品ライセンス] ページのスクリーン ショット。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="7fd53-162">Teams Exploratory エクスペリエンスをすでに使用しているユーザーの Teams の可用性を管理する</span><span class="sxs-lookup"><span data-stu-id="7fd53-162">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="7fd53-163">ユーザーが Teams Exploratory エクスペリエンスを実行している場合は、ライセンスまたはサービス プランを削除することでそれをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-163">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span> <span data-ttu-id="7fd53-164">管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="7fd53-164">You must have admin privileges.</span></span> 

<span data-ttu-id="7fd53-165">Teams Exploratory エクスペリエンスのライセンスをオフにするには:</span><span class="sxs-lookup"><span data-stu-id="7fd53-165">To turn off the the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="7fd53-166">Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fd53-166">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="7fd53-167">ユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="7fd53-167">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="7fd53-168">右側の **[製品ライセンス]** 行で、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fd53-168">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="7fd53-169">[**製品ライセンス**] ウィンドウで、この Exploratory ライセンスのトグルを [**オフ**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-169">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>
   
    >[!Note]
    ><span data-ttu-id="7fd53-170">Teams Exploratory のトグル スイッチは、組織の最初のユーザーが Teams Exploratory エクスペリエンスを起動した後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-170">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="7fd53-171">Teams Exploratory ライセンスを持つユーザーの Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="7fd53-171">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="7fd53-172">Teams Exploratory ライセンスを持つユーザーは、通常の有料ライセンスを持つユーザーと同じように管理できます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-172">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="7fd53-173">詳細については、「[組織の Teams 設定を管理する](enable-features-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd53-173">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="7fd53-174">Teams Exploratory ライセンスからユーザーをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="7fd53-174">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="7fd53-175">Teams Exploratory ライセンスからユーザーをアップグレードするには(管理者権限が必要です)、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7fd53-175">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following:</span></span>

1. <span data-ttu-id="7fd53-176">Teams が含まれているサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="7fd53-176">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="7fd53-177">ユーザーから Teams Exploratory のサブスクリプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="7fd53-177">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="7fd53-178">新しく購入したライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-178">Assign the newly purchased license.</span></span>

<span data-ttu-id="7fd53-179">詳細については、「[Microsoft Teams サービスのサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd53-179">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="7fd53-180">Teams Exploratory ライセンスが終了し、ユーザーが Teams を含むサブスクリプションにすぐにアップグレードされない場合は、ユーザー データは削除されません。</span><span class="sxs-lookup"><span data-stu-id="7fd53-180">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, the user data is not removed.</span></span> <span data-ttu-id="7fd53-181">ユーザーは引き続き Azure Active Directory に残り、Teams 内のすべてのデータが残されたままになります。</span><span class="sxs-lookup"><span data-stu-id="7fd53-181">The user still exists in Azure Active Directory and all data within Teams still remains.</span></span> <span data-ttu-id="7fd53-182">ユーザーに新しいライセンスが割り当てられると、Teams の機能は再び有効になり、すべてのコンテンツが残ります。</span><span class="sxs-lookup"><span data-stu-id="7fd53-182">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist.</span></span> 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="7fd53-183">従来の Microsoft Teams の商用クラウドの試用版のライセンスはどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="7fd53-183">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses?</span></span>

<span data-ttu-id="7fd53-184">2020 年 2 月から、対象ユーザーは最新の Microsoft Teams Exploratory エクスペリエンスの使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-184">As of February, 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="7fd53-185">従来の Teams の商用クラウドの試用版のライセンスはすべて、試用版の有効期限が切れる前に自動的に新しいサービスに変換されます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-185">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="7fd53-186">ユーザーが初めて、有効期限が切れた Teams の商用クラウド試用版にサインインすると、そのユーザーに Teams の探索機能ライセンスが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-186">When a user signs in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to that user.</span></span> <span data-ttu-id="7fd53-187">ユーザーがサインインするまで、変換されません。</span><span class="sxs-lookup"><span data-stu-id="7fd53-187">Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="7fd53-188">Teams Exploratory ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="7fd53-188">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="7fd53-189">Powershell を使用してこのライセンスを削除する場合は、次を参照してください :「[Office 365 PowerShell を使用してユーザー アカウントからライセンスを削除する](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)」</span><span class="sxs-lookup"><span data-stu-id="7fd53-189">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="7fd53-190">管理ポータルからこのライセンスを削除する場合は、「[組織からユーザーを削除する](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd53-190">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="7fd53-191">Teams Exploratory エクスペリエンスの利用可能期間</span><span class="sxs-lookup"><span data-stu-id="7fd53-191">How long does the Teams Exploratory experience last?</span></span>

<span data-ttu-id="7fd53-192">Microsoft Teams Exploratory エクスペリエンスは、次の**契約応当日**、または 2021 年 1 月以降の**更新日**まで追加料金なしで利用可能です。</span><span class="sxs-lookup"><span data-stu-id="7fd53-192">The Microsoft Teams Exploratory experience is available at no additional cost until your next **agreement anniversary** or **renewal** on or after January 2021.</span></span> <span data-ttu-id="7fd53-193">この時点で、Microsoft Exploratory エクスペリエンス ライセンスのエンド ユーザーは、Teams を含む有料のライセンスに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd53-193">At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams.</span></span> <span data-ttu-id="7fd53-194">その後に開始したすべての Microsoft Exploratory エクスペリエンス ライセンスは、次の**契約応当日**、または**更新日**まで追加料金なしで引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-194">Any Microsoft Exploratory experience licenses initiated after that will remain available at no additional cost until your next **anniversary** or **renewal** cycle.</span></span> 

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-my-anniversary-or-renewal-date"></a><span data-ttu-id="7fd53-195">エンド ユーザーが、Microsoft Teams Exploratory エクスペリエンスを契約日、または更新日の前に開始した場合は、どうなりますか?</span><span class="sxs-lookup"><span data-stu-id="7fd53-195">What happens if an end user initiates the Microsoft Teams Exploratory experience just before my anniversary or renewal date?</span></span>

<span data-ttu-id="7fd53-196">Microsoft Teams Exploratory エクスペリエンス ライセンスの開始が、**契約応当日**、または**更新日**の 90 日以内であれば、次の契約応当日、更新日まで有料のライセンスに移行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7fd53-196">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** will not be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span> 

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="7fd53-197">契約に応当日または年次更新日がない場合 (月単位の契約など)</span><span class="sxs-lookup"><span data-stu-id="7fd53-197">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)?</span></span>

<span data-ttu-id="7fd53-198">応当日または年次更新日を含まない契約については、最初のエンド ユーザーが Microsoft Teams Exploratory エクスペリエンス ライセンスをアクティブ化した翌年が、応当日または年次更新日として扱われます。</span><span class="sxs-lookup"><span data-stu-id="7fd53-198">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date.</span></span> <span data-ttu-id="7fd53-199">Microsoft Teams Exploratory ライセンスを使用しているユーザーは、上記のポリシーに従って、その年のその日までに有料ライセンスに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd53-199">Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined above.</span></span>

<span data-ttu-id="7fd53-200">たとえば、最初のエンドユーザーが、2020 年 6 月 19 日に Microsoft Teams Exploratory をアクティブ化した場合、2021 年 6 月 19 日までにそれらのユーザーと顧客テナントのその他のすべての対象ユーザーが Teams の有料ライセンスに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd53-200">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span> 

