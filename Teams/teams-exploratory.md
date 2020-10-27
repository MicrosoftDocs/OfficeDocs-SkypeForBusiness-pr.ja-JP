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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 35ebe9f93321b67806b9fd777aba948f83954c04
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753582"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="74b4d-103">Microsoft Teams Exploratory ライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="74b4d-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="74b4d-104">Microsoft Teams Exploratory エクスペリエンスを使用すると、Azure Active Directory (Azure AD) を持ち、Teams のライセンスを取得していない組織内のユーザーは、Teams の Exploratory エクスペリエンスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="74b4d-105">管理者は組織内のユーザーに対して、この機能をオンまたはオフに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="74b4d-106">以前の [Microsoft の商用クラウド試用版](iw-trial-teams.md) は、 Teams Exploratory エクスペリエンスに変更になりました。</span><span class="sxs-lookup"><span data-stu-id="74b4d-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="74b4d-107">Teams Exploratory エクスペリエンスの内容</span><span class="sxs-lookup"><span data-stu-id="74b4d-107">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="74b4d-108">Teams Exploratory エクスペリエンスの一部として管理者に表示されるサービス プランは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="74b4d-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="74b4d-109">Exchange Online (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="74b4d-109">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="74b4d-110">Microsoft 365 または Office 365 のフロー</span><span class="sxs-lookup"><span data-stu-id="74b4d-110">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="74b4d-111">MyAnalytics を利用した分析情報</span><span class="sxs-lookup"><span data-stu-id="74b4d-111">Insights by MyAnalytics</span></span>
- <span data-ttu-id="74b4d-112">Microsoft Forms (プラン E1)</span><span class="sxs-lookup"><span data-stu-id="74b4d-112">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="74b4d-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="74b4d-113">Microsoft Planner</span></span>
- <span data-ttu-id="74b4d-114">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="74b4d-114">Microsoft Search</span></span>
- <span data-ttu-id="74b4d-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="74b4d-115">Microsoft StaffHub</span></span>
- <span data-ttu-id="74b4d-116">Microsoft Stream for Microsoft 365 E1 SKU および Office 365 E1 SKU <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="74b4d-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="74b4d-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74b4d-117">Microsoft Teams</span></span>
- <span data-ttu-id="74b4d-118">Microsoft 365 または Office 365 のモバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="74b4d-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="74b4d-119">Office Mobile Apps for Office 365</span><span class="sxs-lookup"><span data-stu-id="74b4d-119">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="74b4d-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="74b4d-120">Office Online</span></span>
- <span data-ttu-id="74b4d-121">PowerApps for Microsoft 365 または Office 365</span><span class="sxs-lookup"><span data-stu-id="74b4d-121">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="74b4d-122">SharePoint Online (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="74b4d-122">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="74b4d-123">Sway</span><span class="sxs-lookup"><span data-stu-id="74b4d-123">Sway</span></span>
- <span data-ttu-id="74b4d-124">To-Do (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="74b4d-124">To-Do (Plan 1)</span></span>
- <span data-ttu-id="74b4d-125">Whiteboard (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="74b4d-125">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="74b4d-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="74b4d-126">Yammer Enterprise</span></span>

  <span data-ttu-id="74b4d-127"><sup>1</sup> Microsoft Stream の使用から [会議の記録用の OneDrive for Business および SharePoint](tmr-meeting-recording-change.md) への変更は段階的なアプローチになります。</span><span class="sxs-lookup"><span data-stu-id="74b4d-127"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="74b4d-128">起動時にこの機能に加入できるようになります。</span><span class="sxs-lookup"><span data-stu-id="74b4d-128">At launch you'll be able to opt in to this experience.</span></span> <span data-ttu-id="74b4d-129">ストリームの使用を続ける場合は、11 月に脱退する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74b4d-129">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="74b4d-130">2021 年の初めには、新しい会議を記録するためにすべてのお客様に OneDrive for Business と SharePoint を使用していただく必要があります。</span><span class="sxs-lookup"><span data-stu-id="74b4d-130">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="74b4d-131">対象者</span><span class="sxs-lookup"><span data-stu-id="74b4d-131">Who's eligible</span></span>

<span data-ttu-id="74b4d-132">Teams Exploratory エクスペリエンスの抽出条件を満たすユーザーは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="74b4d-132">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="74b4d-133">管理された Azure AD ドメインのメールアドレスをお持ちである。</span><span class="sxs-lookup"><span data-stu-id="74b4d-133">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="74b4d-134">有料サブスクリプションのテナントに所属している。</span><span class="sxs-lookup"><span data-stu-id="74b4d-134">Belong to a tenant with a paid subscription.</span></span>

<span data-ttu-id="74b4d-135">ユーザーが (Microsoft 365 管理センターで) アプリや試用版にサインアップできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="74b4d-135">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="74b4d-136">詳細については、この記事で後述する「[Teams Exploratory エクスペリエンスを管理する](#manage-the-teams-exploratory-experience)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74b4d-136">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="74b4d-137">対象外</span><span class="sxs-lookup"><span data-stu-id="74b4d-137">Who isn't eligible</span></span>

<span data-ttu-id="74b4d-138">抽出条件を満たさないユーザーは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="74b4d-138">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="74b4d-139">Teams のライセンスを所有しているか、または以前に有料の Teams ライセンスを所有していた。</span><span class="sxs-lookup"><span data-stu-id="74b4d-139">Have a Teams license or previously had a paid Teams license.</span></span>
- <span data-ttu-id="74b4d-140">無料試用版または COVID 無料試用版を使用している。</span><span class="sxs-lookup"><span data-stu-id="74b4d-140">Are using a trial or COVID trial offer.</span></span>
- <span data-ttu-id="74b4d-141">1 つ以上の特別 COVID 無料試用版プランのテナントに所属している。</span><span class="sxs-lookup"><span data-stu-id="74b4d-141">Are in a tenant that has at least one special COVID trial offer.</span></span>

<span data-ttu-id="74b4d-142">シンジケート パートナー顧客である場合、または GCC、GCC High、DoD、または教育機関の顧客である場合、組織は試用版の対象ではありません。</span><span class="sxs-lookup"><span data-stu-id="74b4d-142">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="74b4d-143">ユーザーが Teams Exploratory エクスペリエンスにサインアップする方法</span><span class="sxs-lookup"><span data-stu-id="74b4d-143">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="74b4d-144">対象となるユーザーは、Teams ([teams.microsoft.com](https://teams.microsoft.com)) にサインインして Teams Exploratory エクスペリエンスにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-144">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="74b4d-145">このライセンスは自動的に割り当てられ、組織内の誰かが初めて Teams Exploratory エクスペリエンスを開始すると、テナント管理者に、メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-145">They'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="74b4d-146">Teams Exploratory エクスペリエンスを管理する</span><span class="sxs-lookup"><span data-stu-id="74b4d-146">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="74b4d-147">Teams Exploratory エクスペリエンスは個々のエンド ユーザーが開始するためのものであり、エンド ユーザーの従業員に代わってこのサービスを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="74b4d-147">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="74b4d-148">Teams Exploratory エクスペリエンスには Exchange Online ライセンスが付属していますが、管理者が割り当てるまでユーザーに割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="74b4d-148">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="74b4d-149">ユーザーにまだ Exchange ライセンスがなく、管理者がまだ Exchange Online ライセンスを割り当てていない場合、ユーザーは Teams で会議をスケジュールできず、他の Teams の機能を利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74b4d-149">If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="74b4d-150">管理者は、 **試用版のアプリとサービス** スイッチを使用して、エンド ユーザーが組織内で Teams Exploratory エクスペリエンスを実行できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-150">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="74b4d-151">ユーザーが試用版アプリおよびサービスをインストールできないようにする</span><span class="sxs-lookup"><span data-stu-id="74b4d-151">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="74b4d-152">ユーザーが試用版アプリとサービスをインストールできるようにする機能をオフにすると、そのユーザーは Teams Exploratory エクスペリエンスを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="74b4d-152">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="74b4d-153">Microsoft 365 管理センターから **[設定]** > **[組織の設定]** に移動し、 **[サービス]** を選択し、 **[ユーザー所有のアプリとサービス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="74b4d-153">From the Microsoft 365 admin center, go to **Settings** > **Org settings** , select **Services** , and then select **User owned apps and services** .</span></span>

    ![管理センターの [サービス] ページ](media/iw-trial-services.png)

2. <span data-ttu-id="74b4d-155">**[ユーザーに試用版アプリとサービスのインストールを許可する]** チェック ボックスをクリアします。</span><span class="sxs-lookup"><span data-stu-id="74b4d-155">Clear the **Let users install trial apps and services** check box.</span></span>

    ![管理センターの [ユーザーが所有するアプリとサービス] ページ](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="74b4d-157">組織が Teams Exploratory エクスペリエンスの対象外の場合は、「 **ユーザーが試用版アプリとサービスをインストールできるようにする** 」オプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="74b4d-157">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="74b4d-158">Teams が含まれているライセンスを持つユーザーの利用可能性を管理する</span><span class="sxs-lookup"><span data-stu-id="74b4d-158">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="74b4d-159">Teams が含まれているライセンスの割り当てられたユーザーは、Teams Exploratory エクスペリエンスの対象になりません。</span><span class="sxs-lookup"><span data-stu-id="74b4d-159">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="74b4d-160">Teams のサービス プランが有効なときには、そのユーザーは Teams にログインして使用できます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-160">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="74b4d-161">サービス プランが無効になっている場合、ユーザーはサインインできず、Teams Exploratory エクスペリエンスは利用できません。</span><span class="sxs-lookup"><span data-stu-id="74b4d-161">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="74b4d-162">管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="74b4d-162">You must have admin privileges.</span></span>

<span data-ttu-id="74b4d-163">Teams へのアクセスをオフにするには:</span><span class="sxs-lookup"><span data-stu-id="74b4d-163">To turn off access to Teams:</span></span>

1. <span data-ttu-id="74b4d-164">Microsoft 365 管理センターで、 **[ユーザー]** > **[アクティブ ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="74b4d-164">In the Microsoft 365 admin center, select **Users** > **Active users** .</span></span>

2. <span data-ttu-id="74b4d-165">ユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="74b4d-165">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="74b4d-166">[ **製品のライセンス** ] 行で、[ **編集** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-166">In the **Product licenses** row, choose **Edit** .</span></span>

4. <span data-ttu-id="74b4d-167">**[製品ライセンス]** ウィンドウで、 **[オフ]** に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-167">In the **Product licenses** pane, switch the toggle to **Off** .</span></span>

    ![管理センターの [製品ライセンス] ページ。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="74b4d-169">Teams Exploratory エクスペリエンスをすでに使用しているユーザーの Teams の可用性を管理する</span><span class="sxs-lookup"><span data-stu-id="74b4d-169">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="74b4d-170">ユーザーが Teams Exploratory エクスペリエンスを実行している場合は、ライセンスまたはサービス プランを削除することでそれをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-170">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span> <span data-ttu-id="74b4d-171">管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="74b4d-171">You must have admin privileges.</span></span>

<span data-ttu-id="74b4d-172">Teams Exploratory エクスペリエンスのライセンスをオフにするには:</span><span class="sxs-lookup"><span data-stu-id="74b4d-172">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="74b4d-173">Microsoft 365 管理センターで、 **[ユーザー]** > **[アクティブ ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="74b4d-173">In the Microsoft 365 admin center, select **Users** > **Active users** .</span></span>

2. <span data-ttu-id="74b4d-174">ユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="74b4d-174">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="74b4d-175">[ **製品のライセンス** ] 行で、[ **編集** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-175">In the **Product licenses** row, choose **Edit** .</span></span>

4. <span data-ttu-id="74b4d-176">[ **製品ライセンス** ] ウィンドウで、この Exploratory ライセンスのトグルを [ **オフ** ] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-176">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off** .</span></span>

    >[!Note]
    ><span data-ttu-id="74b4d-177">Teams Exploratory のトグル スイッチは、組織の最初のユーザーが Teams Exploratory エクスペリエンスを起動した後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-177">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="74b4d-178">Teams Exploratory ライセンスを持つユーザーの Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="74b4d-178">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="74b4d-179">Teams Exploratory ライセンスを持つユーザーは、通常の有料ライセンスを持つユーザーと同じように管理できます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-179">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="74b4d-180">詳細については、「[組織の Teams 設定を管理する](enable-features-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74b4d-180">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="74b4d-181">Teams Exploratory ライセンスからユーザーをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="74b4d-181">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="74b4d-182">Teams Exploratory ライセンスからユーザーをアップグレードするには(管理者権限が必要です)、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="74b4d-182">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="74b4d-183">Teams が含まれているサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="74b4d-183">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="74b4d-184">ユーザーから Teams Exploratory のサブスクリプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="74b4d-184">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="74b4d-185">新しく購入したライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-185">Assign the newly purchased license.</span></span>

<span data-ttu-id="74b4d-186">詳細については、「[Microsoft Teams サービスのサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74b4d-186">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="74b4d-187">Teams Exploratory ライセンスが終了し、ユーザーが Teams を含むサブスクリプションにすぐにアップグレードされない場合は、30 日間の猶予期間が設定され、30 日経過後にデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-187">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted.</span></span> <span data-ttu-id="74b4d-188">ユーザーは引き続き Azure Active Directory に残ります。</span><span class="sxs-lookup"><span data-stu-id="74b4d-188">The user still exists in Azure Active Directory.</span></span> <span data-ttu-id="74b4d-189">ユーザーに新しいライセンスが割り当てられると、Teams の機能は再び有効になり、猶予期間のタイムフレーム内にユーザーが追加された場合はすべてのコンテンツが残ります。</span><span class="sxs-lookup"><span data-stu-id="74b4d-189">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="74b4d-190">従来の Microsoft Teams の商用クラウドの試用版のライセンスはどうなりますか</span><span class="sxs-lookup"><span data-stu-id="74b4d-190">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="74b4d-191">2020 年 2 月から、対象ユーザーは最新の Microsoft Teams Exploratory エクスペリエンスの使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-191">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="74b4d-192">従来の Teams の商用クラウドの試用版のライセンスはすべて、試用版の有効期限が切れる前に自動的に新しいサービスに変換されます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-192">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="74b4d-193">ユーザーが初めて、有効期限が切れた Teams の商用クラウドの試用版にサインインすると、そのユーザーに Teams Exploratory ライセンスが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-193">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users.</span></span> <span data-ttu-id="74b4d-194">ユーザーがサインインするまで、変換されません。</span><span class="sxs-lookup"><span data-stu-id="74b4d-194">Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="74b4d-195">Teams Exploratory ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="74b4d-195">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="74b4d-196">Powershell を使用してこのライセンスを削除する場合は、次を参照してください :「[Office 365 PowerShell を使用してユーザー アカウントからライセンスを削除する](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)」</span><span class="sxs-lookup"><span data-stu-id="74b4d-196">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="74b4d-197">管理ポータルからこのライセンスを削除する場合は、「[組織からユーザーを削除する](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74b4d-197">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="74b4d-198">データ保持ポリシーとは何ですか?</span><span class="sxs-lookup"><span data-stu-id="74b4d-198">What is the data retention policy?</span></span>

<span data-ttu-id="74b4d-199">詳細については、「[Microsoft 365 サブスクリプション情報](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74b4d-199">See [Microsoft 365 subscription information](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="74b4d-200">Teams Exploratory エクスペリエンスの利用可能期間</span><span class="sxs-lookup"><span data-stu-id="74b4d-200">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="74b4d-201">Microsoft Teams Exploratory エクスペリエンスは、次の **契約応当日** 、または 2021 年 1 月以降の **更新日** まで追加料金なしで利用可能です。</span><span class="sxs-lookup"><span data-stu-id="74b4d-201">The Microsoft Teams Exploratory experience is available at no additional cost until your next **agreement anniversary** or **renewal** on or after January 2021.</span></span> <span data-ttu-id="74b4d-202">この時点で、Microsoft Exploratory エクスペリエンス ライセンスのエンド ユーザーは、Teams を含む有料のライセンスに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74b4d-202">At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams.</span></span> <span data-ttu-id="74b4d-203">その後に開始したすべての Microsoft Exploratory エクスペリエンス ライセンスは、次の **契約応当日** 、または **更新日** まで追加料金なしで引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-203">Any Microsoft Exploratory experience licenses initiated after that will remain available at no additional cost until your next **anniversary** or **renewal** cycle.</span></span>

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a><span data-ttu-id="74b4d-204">エンド ユーザーが、Microsoft Teams Exploratory エクスペリエンスを契約日、または更新日の前に開始した場合は、どうなりますか</span><span class="sxs-lookup"><span data-stu-id="74b4d-204">What happens if an end user initiates the Microsoft Teams Exploratory experience just before the anniversary or renewal date</span></span>

<span data-ttu-id="74b4d-205">Microsoft Teams Exploratory エクスペリエンス ライセンスの開始が、 **契約応当日** 、または **更新日** の 90 日以内であれば、次の契約応当日、更新日まで有料のライセンスに移行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="74b4d-205">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** won't be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span>

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="74b4d-206">契約に応当日または年次更新日がない場合 (月単位の契約など)</span><span class="sxs-lookup"><span data-stu-id="74b4d-206">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)</span></span>

<span data-ttu-id="74b4d-207">応当日または年次更新日を含まない契約については、最初のエンド ユーザーが Microsoft Teams Exploratory エクスペリエンス ライセンスをアクティブ化した翌年が、応当日または年次更新日として扱われます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-207">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end-user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date.</span></span> <span data-ttu-id="74b4d-208">Microsoft Teams Exploratory ライセンスを使用しているユーザーは、この記事のポリシーに従って、その年のその日までに有料ライセンスに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74b4d-208">Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined in this article.</span></span>

<span data-ttu-id="74b4d-209">たとえば、最初のエンドユーザーが、2020 年 6 月 19 日に Microsoft Teams Exploratory をアクティブ化した場合、2021 年 6 月 19 日までにそれらのユーザーと顧客テナントのその他のすべての対象ユーザーが Teams の有料ライセンスに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74b4d-209">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span>

> [!Note]
> <span data-ttu-id="74b4d-210">お客様は、以前の Exploratory 試用版ライセンスの有効期限が終了してから 3 か月間、新しい Exploratory 試用版ライセンスは無効になり、起動がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="74b4d-210">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>
