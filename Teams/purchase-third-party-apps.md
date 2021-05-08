---
title: サード パーティ製アプリを購入Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava
search.appverid: MET150
f1keywords: ''
description: 管理センターでサード パーティ製アプリをTeamsする方法Microsoft Teams確認します。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 57530ec952b6bbe806e685d0980fcee3a21d1887
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117685"
---
<a name="purchase-third-party-apps-for-teams"></a><span data-ttu-id="a2232-103">サード パーティ製アプリを購入Teams</span><span class="sxs-lookup"><span data-stu-id="a2232-103">Purchase third-party apps for Teams</span></span>
======================================================

> [!NOTE]
> <span data-ttu-id="a2232-104">この機能は現在、米国でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2232-104">This feature is currently only available in the United States.</span></span>

<span data-ttu-id="a2232-105">Teamsは無料でインストールできます。一部のアプリでは、アプリの完全な機能とスコープを体験するために購入サービス サブスクリプションが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2232-105">Teams apps are free to install and some may require purchasing service subscriptions to experience the app's full functionality and scope.</span></span> <span data-ttu-id="a2232-106">これらのサービス サブスクリプションは、サービスとしてのソフトウェア (SaaS) オファーと呼ばれるサービスであり[、AppSource](https://appsource.microsoft.com/)を通じて購入し、現在は管理センターからMicrosoft Teams利用できます。</span><span class="sxs-lookup"><span data-stu-id="a2232-106">These service subscriptions are called Software as a Service (SaaS) offers, which are available for purchase through [AppSource](https://appsource.microsoft.com/) and now through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="a2232-107">Microsoft Teams [](manage-apps.md)管理センターの [アプリの管理] ページでは、組織のすべてのアプリTeams表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="a2232-107">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="a2232-108">たとえば、アプリの組織レベルの状態とプロパティの表示、組織のアプリ ストアへの新しいカスタム アプリのアップロード、組織レベルでのアプリのブロックまたは許可、組織全体のアプリ設定の管理を行います。</span><span class="sxs-lookup"><span data-stu-id="a2232-108">For example, you can see the org-level status and properties of apps, upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="a2232-109">ここでは、組織内のユーザー向けサード パーティ製アプリによって提供されるサービスのライセンスを購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2232-109">Here, you can also purchase licenses for services offered by third-party apps for users in your organization.</span></span> <span data-ttu-id="a2232-110">表 **の [** ライセンス] 列は、アプリが SaaS サブスクリプションを購入できるかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="a2232-110">The **Licenses** column in the table indicates whether an app offers a SaaS subscription for purchase.</span></span>

:::image type="content" source="media/purchase-third-party-apps-list.png" alt-text="SaaS サブスクリプションを持つサード パーティ製アプリを示すスクリーンショット":::

## <a name="search-for-and-purchase-services-for-a-third-party-app"></a><span data-ttu-id="a2232-112">サード パーティ製アプリのサービスを検索して購入する</span><span class="sxs-lookup"><span data-stu-id="a2232-112">Search for and purchase services for a third-party app</span></span>

1. <span data-ttu-id="a2232-113">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="a2232-113">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="a2232-114">ページにアクセスするには、グローバル管理者Teamsサービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2232-114">You must be a global admin or Teams service admin to access the page.</span></span>
2. <span data-ttu-id="a2232-115">必要なアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="a2232-115">Search for the app that you want.</span></span> <span data-ttu-id="a2232-116">有料 SaaS サブスクリプションを持つアプリを識別するには、[ライセンス] 列を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="a2232-116">To identify apps that have a paid SaaS subscription, look in the **Licenses** column.</span></span> <span data-ttu-id="a2232-117">各アプリには、次のいずれかの値があります。</span><span class="sxs-lookup"><span data-stu-id="a2232-117">Each app will have one of the following values:</span></span>
    - <span data-ttu-id="a2232-118">**今すぐ購入**: アプリは SaaS サブスクリプションを提供し、購入できます。</span><span class="sxs-lookup"><span data-stu-id="a2232-118">**Purchase now**: The app offers a SaaS subscription and is available to purchase.</span></span>  
    - <span data-ttu-id="a2232-119">**購入:** アプリは SaaS サブスクリプションを提供し、そのライセンスを購入しました。</span><span class="sxs-lookup"><span data-stu-id="a2232-119">**Purchased**: The app offers a SaaS subscription and you've purchased licenses for it.</span></span>
    - <span data-ttu-id="a2232-120">**- :** アプリは SaaS サブスクリプションを提供しない。</span><span class="sxs-lookup"><span data-stu-id="a2232-120">**- -**: The app doesn't offer a SaaS subscription.</span></span>
3. <span data-ttu-id="a2232-121">アプリが見つけたら、[今すぐ **購入] を** クリックして、アプリの詳細ページの **[プラン** と価格] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="a2232-121">When you find the app, click **Purchase now** to go to the **Plans and pricing** tab of the app details page.</span></span> <span data-ttu-id="a2232-122">アプリの SaaS プランのプランと価格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="a2232-122">Review the plans and pricing information for the SaaS offer for the app.</span></span> <span data-ttu-id="a2232-123">詳細が必要な場合は、[詳細 **]** リンクをクリックして AppSource のアプリのページに [移動します](https://appsource.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="a2232-123">If you need more information, click the **learn more** link to go to the app's page on [AppSource](https://appsource.microsoft.com/).</span></span>  
4. <span data-ttu-id="a2232-124">プランを購入するには、[今すぐ購入] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a2232-124">To buy a plan, click **Purchase now**.</span></span> <span data-ttu-id="a2232-125">アプリに関連付けられているオファーの購入エクスペリエンスにTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="a2232-125">You'll be redirected to the purchase experience for the offer associated with the Teams app.</span></span> <span data-ttu-id="a2232-126">ここで、サービスまたは SaaS オファーの購入を完了します。</span><span class="sxs-lookup"><span data-stu-id="a2232-126">This is where you'll complete your purchase of the service or SaaS offer.</span></span>
5. <span data-ttu-id="a2232-127">必要なプランを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2232-127">Choose the plan that you want.</span></span> <span data-ttu-id="a2232-128">SaaS プランに複数のプランが含まれる場合は、[変更 **]** をクリックして利用可能なプランの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2232-128">If the SaaS offer includes more than one plan, click **Change** to see the list of available plans.</span></span>
6. <span data-ttu-id="a2232-129">請求期間 (月 **または** 年)を選択し、購入するユーザー ライセンスの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="a2232-129">Select your billing term (either **Monthly** or **Yearly**), and then enter the number of user licenses that you want to buy.</span></span>
7. <span data-ttu-id="a2232-130">支払い方法を入力します。</span><span class="sxs-lookup"><span data-stu-id="a2232-130">Enter your payment method.</span></span>
8. <span data-ttu-id="a2232-131">準備ができたら、[注文] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a2232-131">When you're ready, select **Place order**.</span></span>
9. <span data-ttu-id="a2232-132">[ **今すぐ構成]** をクリックして、発行元の Web サイトでサブスクリプションをアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="a2232-132">Click **Configure now** to activate your subscription on the publisher's website.</span></span>

<span data-ttu-id="a2232-133">Teams アプリに関連付けられている SaaS オファーを購入すると、アプリの詳細ページの [プランと価格]タブで次の購入の詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a2232-133">After you've purchased the SaaS offer associated with the Teams app, you can view the following purchase details on the **Plans and pricing** tab of the app details page.</span></span>

- <span data-ttu-id="a2232-134">**ライセンスのライセンス認証日**: ライセンスがアクティブ化された日付。</span><span class="sxs-lookup"><span data-stu-id="a2232-134">**License activation date**: Date on which your license was activated.</span></span> <span data-ttu-id="a2232-135">アカウントがまだ設定されていない場合は、サブスクリプションのアクティブ化が保留中 **と表示されます**。</span><span class="sxs-lookup"><span data-stu-id="a2232-135">If your account isn't yet set up, this shows as **Subscription pending activation**.</span></span>
- <span data-ttu-id="a2232-136">**ライセンス**: 購入したライセンスの数。</span><span class="sxs-lookup"><span data-stu-id="a2232-136">**Licenses**: Number of licenses you purchased.</span></span>

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="アプリの詳細ページの [プランと価格] タブのスクリーンショット":::

<span data-ttu-id="a2232-138">[**ライセンスの管理]** を選択して Microsoft 365 管理センターに移動し、購入したライセンスを表示および管理し、ユーザーのライセンス割り当てを管理します。</span><span class="sxs-lookup"><span data-stu-id="a2232-138">Select **Manage licenses** to go to the Microsoft 365 admin center to view and manage the licenses you purchased and to manage license assignments for users.</span></span>

<span data-ttu-id="a2232-139">グローバル管理者は組織内のすべてのユーザーが行った購入を表示できるのに対し、Teams サービス管理者は自分で行った購入のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a2232-139">Global admins can view the purchases made by anyone in the organization whereas Teams service admins can only view the purchases made by themselves.</span></span>  

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a><span data-ttu-id="a2232-140">Microsoft Teams 管理センターと AppSource で一覧表示して販売する、Teams アプリの SaaS オファーがありますか?</span><span class="sxs-lookup"><span data-stu-id="a2232-140">Have a SaaS offer for a Teams app that you want to list and sell in the Microsoft Teams admin center and AppSource?</span></span>

<span data-ttu-id="a2232-141">開発者は、アプリに関連付けられた SaaS オファー Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="a2232-141">Developers can create SaaS offers associated with their Teams apps.</span></span> <span data-ttu-id="a2232-142">これらのオファーはパートナー センターを[通じて](https://partner.microsoft.com)公開され、組織は[AppSource](https://appsource.microsoft.com/)と管理センターから購入Microsoft Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="a2232-142">These offers are published through [Partner Center](https://partner.microsoft.com) and are available for organizations to purchase through [AppSource](https://appsource.microsoft.com/) and the Microsoft Teams admin center.</span></span>
 
<span data-ttu-id="a2232-143">サード パーティ製アプリ開発者は [、「SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer) オファーを作成する」を参照して詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a2232-143">Third-party app developers can go to [Create a SaaS offer](/azure/marketplace/partner-center-portal/create-new-saas-offer) for more information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2232-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a2232-144">Related topics</span></span>

- [<span data-ttu-id="a2232-145">管理センターでアプリMicrosoft Teams管理する</span><span class="sxs-lookup"><span data-stu-id="a2232-145">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="a2232-146">SaaS オファーを作成する</span><span class="sxs-lookup"><span data-stu-id="a2232-146">Create a SaaS offer</span></span>](/azure/marketplace/partner-center-portal/create-new-saas-offer)