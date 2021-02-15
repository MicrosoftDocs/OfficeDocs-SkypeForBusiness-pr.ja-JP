---
title: Microsoft Teams Exploratory エクスペリエンスを管理する
author: SerdarSoysal
ms.author: serdars
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
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9aa7b0a26e947eaa961db5d5be3b793d50474867
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196471"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="33a17-103">Microsoft Teams Exploratory ライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="33a17-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="33a17-104">Microsoft Teams Exploratory エクスペリエンスを使用すると、Azure Active Directory (Azure AD) を持ち、Teams のライセンスを取得していない組織内のユーザーは、Teams の Exploratory エクスペリエンスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="33a17-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="33a17-105">管理者は組織内のユーザーに対して、この機能をオンまたはオフに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="33a17-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="33a17-106">以前の [Microsoft の商用クラウド試用版](iw-trial-teams.md) は、 Teams Exploratory エクスペリエンスに変更になりました。</span><span class="sxs-lookup"><span data-stu-id="33a17-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="33a17-107">Teams Exploratory エクスペリエンスの内容</span><span class="sxs-lookup"><span data-stu-id="33a17-107">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="33a17-108">Teams Exploratory エクスペリエンスの一部として管理者に表示されるサービス プランは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="33a17-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="33a17-109">Exchange Online (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="33a17-109">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="33a17-110">Microsoft 365 または Office 365 のフロー</span><span class="sxs-lookup"><span data-stu-id="33a17-110">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="33a17-111">MyAnalytics を利用した分析情報</span><span class="sxs-lookup"><span data-stu-id="33a17-111">Insights by MyAnalytics</span></span>
- <span data-ttu-id="33a17-112">Microsoft Forms (プラン E1)</span><span class="sxs-lookup"><span data-stu-id="33a17-112">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="33a17-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="33a17-113">Microsoft Planner</span></span>
- <span data-ttu-id="33a17-114">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="33a17-114">Microsoft Search</span></span>
- <span data-ttu-id="33a17-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="33a17-115">Microsoft StaffHub</span></span>
- <span data-ttu-id="33a17-116">Microsoft Stream for Microsoft 365 E1 SKU および Office 365 E1 SKU <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="33a17-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="33a17-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="33a17-117">Microsoft Teams</span></span>
- <span data-ttu-id="33a17-118">Microsoft 365 または Office 365 のモバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="33a17-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="33a17-119">Office Mobile Apps for Office 365</span><span class="sxs-lookup"><span data-stu-id="33a17-119">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="33a17-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="33a17-120">Office Online</span></span>
- <span data-ttu-id="33a17-121">PowerApps for Microsoft 365 または Office 365</span><span class="sxs-lookup"><span data-stu-id="33a17-121">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="33a17-122">SharePoint Online (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="33a17-122">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="33a17-123">Sway</span><span class="sxs-lookup"><span data-stu-id="33a17-123">Sway</span></span>
- <span data-ttu-id="33a17-124">To-Do (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="33a17-124">To-Do (Plan 1)</span></span>
- <span data-ttu-id="33a17-125">Whiteboard (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="33a17-125">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="33a17-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="33a17-126">Yammer Enterprise</span></span>

  <span data-ttu-id="33a17-127"><sup>1</sup> Microsoft Stream の使用から [会議の記録用の OneDrive for Business および SharePoint](tmr-meeting-recording-change.md) への変更は段階的なアプローチになります。</span><span class="sxs-lookup"><span data-stu-id="33a17-127"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="33a17-128">起動時に、この機能に加入できるようになります。</span><span class="sxs-lookup"><span data-stu-id="33a17-128">At launch, you'll be able to opt in to this experience.</span></span> <span data-ttu-id="33a17-129">ストリームの使用を続ける場合は、11 月に脱退する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a17-129">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="33a17-130">2021 年の初めには、新しい会議を記録するためにすべてのお客様に OneDrive for Business と SharePoint を使用していただく必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a17-130">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="33a17-131">対象者</span><span class="sxs-lookup"><span data-stu-id="33a17-131">Who's eligible</span></span>

<span data-ttu-id="33a17-132">Teams Exploratory エクスペリエンスの抽出条件を満たすユーザーは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="33a17-132">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="33a17-133">管理された Azure AD ドメインのメールアドレスをお持ちである。</span><span class="sxs-lookup"><span data-stu-id="33a17-133">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="33a17-134">有料サブスクリプションのテナントに所属している。</span><span class="sxs-lookup"><span data-stu-id="33a17-134">Belong to a tenant with a paid subscription.</span></span>
- <span data-ttu-id="33a17-135">アクティブな Teams ライセンスを持っていない。</span><span class="sxs-lookup"><span data-stu-id="33a17-135">Do not have an active Teams license.</span></span>
- <span data-ttu-id="33a17-136">ライセンスの割り当てポリシーが作成されたテナントに存在していない。</span><span class="sxs-lookup"><span data-stu-id="33a17-136">Are not in a tenant where a license assignment policy was created.</span></span>

<span data-ttu-id="33a17-137">ユーザーが (Microsoft 365 管理センターで) アプリや試用版にサインアップできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a17-137">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="33a17-138">詳細については、この記事で後述する「[Teams Exploratory エクスペリエンスを管理する](#manage-the-teams-exploratory-experience)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33a17-138">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="33a17-139">対象外</span><span class="sxs-lookup"><span data-stu-id="33a17-139">Who isn't eligible</span></span>

<span data-ttu-id="33a17-140">抽出条件を満たさないユーザーは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="33a17-140">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="33a17-141">現在までに有料版、無料版、試用版ライセンスでの Teams を所有していたことがある</span><span class="sxs-lookup"><span data-stu-id="33a17-141">Currently or previously had Teams from a paid, unpaid, or trial license</span></span>
- <span data-ttu-id="33a17-142">特別 COVID プランを 1 回以上利用した/受け取ったテナントに所属している。</span><span class="sxs-lookup"><span data-stu-id="33a17-142">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="33a17-143">シンジケート パートナー顧客である場合、または GCC、GCC High、DoD、または教育機関の顧客である場合、組織は試用版の対象ではありません。</span><span class="sxs-lookup"><span data-stu-id="33a17-143">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="33a17-144">ユーザーが Teams Exploratory エクスペリエンスにサインアップする方法</span><span class="sxs-lookup"><span data-stu-id="33a17-144">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="33a17-145">対象となるユーザーは、デスクトップまたは Web から Teams ([teams.microsoft.com](https://teams.microsoft.com)) にサインインして Teams Exploratory エクスペリエンスにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="33a17-145">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="33a17-146">現時点では、モバイルを通した探索の有効化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="33a17-146">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="33a17-147">サインアップを完了すると、このライセンスは自動的に割り当てられ、組織内の誰かが初めて Teams Exploratory エクスペリエンスを開始すると、テナント管理者に、メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="33a17-147">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="33a17-148">Teams Exploratory エクスペリエンスを管理する</span><span class="sxs-lookup"><span data-stu-id="33a17-148">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="33a17-149">Teams Exploratory エクスペリエンスは個々のエンド ユーザーが開始するためのものであり、エンド ユーザーの従業員に代わってこのサービスを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="33a17-149">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="33a17-150">Teams Exploratory エクスペリエンスには Exchange Online ライセンスが付属していますが、管理者が割り当てるまでユーザーに割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="33a17-150">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="33a17-151">ユーザーにまだ Exchange ライセンスがなく、管理者がまだ Exchange Online ライセンスを割り当てていない場合、ユーザーは Teams で会議をスケジュールできず、他の Teams の機能を利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33a17-151">If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="33a17-152">管理者は、**試用版のアプリとサービス** スイッチを使用して、エンド ユーザーが組織内で Teams Exploratory エクスペリエンスを実行できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="33a17-152">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="33a17-153">ユーザーが試用版アプリおよびサービスをインストールできないようにする</span><span class="sxs-lookup"><span data-stu-id="33a17-153">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="33a17-154">ユーザーが試用版アプリとサービスをインストールできるようにする機能をオフにすると、そのユーザーは Teams Exploratory エクスペリエンスを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="33a17-154">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="33a17-155">Microsoft 365 管理センターから **[設定]** > **[組織の設定]** に移動し、**[サービス]** を選択し、**[ユーザー所有のアプリとサービス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33a17-155">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![管理センターの [サービス] ページ](media/iw-trial-services.png)

2. <span data-ttu-id="33a17-157">**[ユーザーに試用版アプリとサービスのインストールを許可する]** のチェック マークをクリアします。</span><span class="sxs-lookup"><span data-stu-id="33a17-157">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![管理センターの [ユーザーが所有するアプリとサービス] ページ](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="33a17-159">組織が Teams Exploratory エクスペリエンスの対象外の場合は、「**ユーザーが試用版アプリとサービスをインストールできるようにする**」オプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="33a17-159">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="33a17-160">Teams が含まれているライセンスを持つユーザーの利用可能性を管理する</span><span class="sxs-lookup"><span data-stu-id="33a17-160">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="33a17-161">Teams が含まれているライセンスの割り当てられたユーザーは、Teams Exploratory エクスペリエンスの対象になりません。</span><span class="sxs-lookup"><span data-stu-id="33a17-161">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="33a17-162">Teams のサービス プランが有効なときには、そのユーザーは Teams にログインして使用できます。</span><span class="sxs-lookup"><span data-stu-id="33a17-162">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="33a17-163">サービス プランが無効になっている場合、ユーザーはサインインできず、Teams Exploratory エクスペリエンスは利用できません。</span><span class="sxs-lookup"><span data-stu-id="33a17-163">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="33a17-164">管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="33a17-164">You must have admin privileges.</span></span>

<span data-ttu-id="33a17-165">Teams へのアクセスをオフにするには:</span><span class="sxs-lookup"><span data-stu-id="33a17-165">To turn off access to Teams:</span></span>

1. <span data-ttu-id="33a17-166">Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33a17-166">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="33a17-167">ユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="33a17-167">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="33a17-168">[**製品のライセンス**] 行で、[**編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="33a17-168">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="33a17-169">**[製品ライセンス]** ウィンドウで、**[オフ]** に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="33a17-169">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![管理センターの [製品ライセンス] ページ。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="33a17-171">Teams Exploratory エクスペリエンスをすでに使用しているユーザーの Teams の可用性を管理する</span><span class="sxs-lookup"><span data-stu-id="33a17-171">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="33a17-172">ユーザーが Teams Exploratory エクスペリエンスを実行している場合は、ライセンスまたはサービス プランを削除することでそれをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="33a17-172">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span> <span data-ttu-id="33a17-173">管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="33a17-173">You must have admin privileges.</span></span>

<span data-ttu-id="33a17-174">Teams Exploratory エクスペリエンスのライセンスをオフにするには:</span><span class="sxs-lookup"><span data-stu-id="33a17-174">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="33a17-175">Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33a17-175">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="33a17-176">ユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="33a17-176">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="33a17-177">[**製品のライセンス**] 行で、[**編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="33a17-177">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="33a17-178">[**製品ライセンス**] ウィンドウで、この Exploratory ライセンスのトグルを [**オフ**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="33a17-178">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    >[!Note]
    ><span data-ttu-id="33a17-179">Teams Exploratory のトグル スイッチは、組織の最初のユーザーが Teams Exploratory エクスペリエンスを起動した後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="33a17-179">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="33a17-180">Teams Exploratory ライセンスを持つユーザーの Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="33a17-180">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="33a17-181">Teams Exploratory ライセンスを持つユーザーは、通常の有料ライセンスを持つユーザーと同じように管理できます。</span><span class="sxs-lookup"><span data-stu-id="33a17-181">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="33a17-182">詳細については、「[組織の Teams 設定を管理する](enable-features-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33a17-182">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="33a17-183">Teams Exploratory ライセンスからユーザーをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="33a17-183">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="33a17-184">Teams Exploratory ライセンスからユーザーをアップグレードするには(管理者権限が必要です)、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="33a17-184">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="33a17-185">Teams が含まれているサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="33a17-185">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="33a17-186">ユーザーから Teams Exploratory のサブスクリプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="33a17-186">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="33a17-187">新しく購入したライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="33a17-187">Assign the newly purchased license.</span></span>

<span data-ttu-id="33a17-188">詳細については、「[Microsoft Teams サービスのサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33a17-188">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="33a17-189">Teams Exploratory ライセンスが終了し、ユーザーが Teams を含むサブスクリプションにすぐにアップグレードされない場合は、30 日間の猶予期間が設定され、30 日経過後にデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="33a17-189">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted.</span></span> <span data-ttu-id="33a17-190">ユーザーは引き続き Azure Active Directory に残ります。</span><span class="sxs-lookup"><span data-stu-id="33a17-190">The user still exists in Azure Active Directory.</span></span> <span data-ttu-id="33a17-191">ユーザーに新しいライセンスが割り当てられると、Teams の機能は再び有効になり、猶予期間のタイムフレーム内にユーザーが追加された場合はすべてのコンテンツが残ります。</span><span class="sxs-lookup"><span data-stu-id="33a17-191">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="33a17-192">従来の Microsoft Teams の商用クラウドの試用版のライセンスはどうなりますか</span><span class="sxs-lookup"><span data-stu-id="33a17-192">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="33a17-193">2020 年 2 月から、対象ユーザーは最新の Microsoft Teams Exploratory エクスペリエンスの使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="33a17-193">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="33a17-194">従来の Teams の商用クラウドの試用版のライセンスはすべて、試用版の有効期限が切れる前に自動的に新しいサービスに変換されます。</span><span class="sxs-lookup"><span data-stu-id="33a17-194">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="33a17-195">ユーザーが初めて、有効期限が切れた Teams の商用クラウドの試用版にサインインすると、そのユーザーに Teams Exploratory ライセンスが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="33a17-195">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users.</span></span> <span data-ttu-id="33a17-196">ユーザーがサインインするまで、変換されません。</span><span class="sxs-lookup"><span data-stu-id="33a17-196">Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="33a17-197">Teams Exploratory ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="33a17-197">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="33a17-198">Powershell を使用してこのライセンスを削除する場合は、次を参照してください :「[Office 365 PowerShell を使用してユーザー アカウントからライセンスを削除する](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)」</span><span class="sxs-lookup"><span data-stu-id="33a17-198">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="33a17-199">管理ポータルからこのライセンスを削除する場合は、「[組織からユーザーを削除する](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33a17-199">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="33a17-200">データ保持ポリシーとは</span><span class="sxs-lookup"><span data-stu-id="33a17-200">What is the data retention policy</span></span>

<span data-ttu-id="33a17-201">詳細については、「[Microsoft 365 サブスクリプション情報](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33a17-201">See [Microsoft 365 subscription information](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="33a17-202">Teams Exploratory エクスペリエンスの利用可能期間</span><span class="sxs-lookup"><span data-stu-id="33a17-202">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="33a17-203">2021 年初頭の時点で、Teams Exploratory は、すべての新規のお客様を対象とした (最初のユーザー サインアップから) 12 か月のサブスクリプションとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="33a17-203">As of early 2021, Teams Exploratory is available as a 12 month subscription (from initial user sign-up) for all new customers.</span></span> <span data-ttu-id="33a17-204">新しい Teams Exploratory サブスクリプションは、組織の最初のユーザーが Teams Exploratory にサインアップしたときに開始され、12 か月後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="33a17-204">The new Teams Exploratory subscription starts when the first user in an organization signs-up for Teams Exploratory and it will expire after 12 months.</span></span> <span data-ttu-id="33a17-205">有効期限は同じテナントのすべてのユーザーに適用されます。12 か月の期間は最初のユーザーのサインアップした日付から開始します。</span><span class="sxs-lookup"><span data-stu-id="33a17-205">The expiry date will apply to all users in the same tenant as the 12-month term begins on the first user's sign-up date.</span></span>

> [!NOTE]
> <span data-ttu-id="33a17-206">エクスペリエンスの終了日は組織レベルで構成されます。つまり、同じ組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="33a17-206">The end date for the experience is configured at an organization level, meaning it will apply to all users in the same organization.</span></span> <span data-ttu-id="33a17-207">たとえば、ユーザー 1 が 2021 年 1 月 1 日にサブスクリプションにサインアップしたとします。</span><span class="sxs-lookup"><span data-stu-id="33a17-207">For example, User 1 signs up for the subscription on January 1, 2021.</span></span> <span data-ttu-id="33a17-208">これにより、2021 年 12 月 31 日を終了日とするサブスクリプションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="33a17-208">This initiates a subscription end-date of December 31, 2021.</span></span> <span data-ttu-id="33a17-209">別のユーザーであるユーザー 2 が、2021 年 10 月 1 日にサブスクリプションにサインアップした場合、</span><span class="sxs-lookup"><span data-stu-id="33a17-209">Another user, User 2, signs up for the subscription on October 1, 2021.</span></span> <span data-ttu-id="33a17-210">ユーザー 2 は Teams Exploratory を 2 か月間使用できます。これは、ユーザー 1 と同じ組織のサブスクリプションでは、終了日が 2021 年 12 月 31 日となるためです。</span><span class="sxs-lookup"><span data-stu-id="33a17-210">User 2 can use Teams Exploratory for two months, as their end-date will be December 31, 2021 because they're under the same organization's subscription as User 1.</span></span>

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a><span data-ttu-id="33a17-211">12 か月の Teams Exploratory エクスペリエンスの終了時に管理者がすべきこと</span><span class="sxs-lookup"><span data-stu-id="33a17-211">What should administrators do at the end of the 12 month Teams Exploratory experience</span></span>

<span data-ttu-id="33a17-212">12 か月のサブスクリプションの終了時に、管理者はすべての Teams Exploratory ユーザーを Teams を含む有料ライセンスに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a17-212">At the end of the 12 month subscription, administrators should convert all Teams Exploratory users to a paid license that includes Teams.</span></span> <span data-ttu-id="33a17-213">ユーザー エクスペリエンスの中断を回避するために、Teams Exploratory サブスクリプションの有効期限が切れる前にこの処理を完了しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="33a17-213">It is vital to ensure this is completed before the Teams Exploratory subscription expires to avoid any disruption to user's experience.</span></span>

<span data-ttu-id="33a17-214">詳細については、この記事の上記の「[Teams Exploratory ライセンスからユーザーをアップグレードする](#upgrade-users-from-the-teams-exploratory-license))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33a17-214">For more information, see [Upgrade users from the Teams Exploratory license](#upgrade-users-from-the-teams-exploratory-license)), above in this article.</span></span>
