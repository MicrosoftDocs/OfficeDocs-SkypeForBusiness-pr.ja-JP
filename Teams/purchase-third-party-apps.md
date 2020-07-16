---
title: Microsoft Teams 管理センターでの Teams のサードパーティ製アプリの購入サービス
author: LanaChin
ms.author: v-lanac
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
description: Microsoft Teams 管理センターの [アプリの管理] ページで、Teams のサードパーティ製アプリのサービスを購入する方法について説明します。
appliesto:
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ab917c57578a854ef5bf6c591229ac35a7e98fe9
ms.sourcegitcommit: 92a1158a4ade08d7168691b7f8b44a33df090afb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146113"
---
<a name="purchase-services-for-teams-third-party-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="53809-103">Microsoft Teams 管理センターでの Teams のサードパーティ製アプリの購入サービス</span><span class="sxs-lookup"><span data-stu-id="53809-103">Purchase services for Teams third-party apps in the Microsoft Teams admin center</span></span>
======================================================

> [!NOTE]
> <span data-ttu-id="53809-104">現時点では、この機能は米国でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="53809-104">This feature is currently only available in the United States.</span></span>

<span data-ttu-id="53809-105">Teams アプリは無料でインストールでき、アプリの完全な機能と範囲を体験するためにサービスの購入が必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="53809-105">Teams apps are free to install and some may require purchasing service subscriptions to experience the app's full functionality and scope.</span></span> <span data-ttu-id="53809-106">これらのサービス月額プランは、サービス (SaaS) オファーとして提供されます。これは、[アプリソース](https://appsource.microsoft.com/)と、Microsoft Teams 管理センターを通じて購入することができます。</span><span class="sxs-lookup"><span data-stu-id="53809-106">These service subscriptions are called Software as a Service (SaaS) offers, which are available for purchase through [AppSource](https://appsource.microsoft.com/) and now through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="53809-107">Microsoft Teams 管理センターの [[アプリの管理](manage-apps.md)] ページでは、組織のすべての Teams アプリを表示して管理できます。</span><span class="sxs-lookup"><span data-stu-id="53809-107">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="53809-108">たとえば、アプリの組織レベルの状態とプロパティの表示、新しいカスタムアプリの組織のアプリストアへのアップロード、組織レベルでのアプリのブロックまたは許可、組織全体のアプリ設定の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="53809-108">For example, you can see the org-level status and properties of apps, upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="53809-109">ここでは、組織内のユーザーに対してサードパーティ製のアプリによって提供されるサービスのライセンスを購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="53809-109">Here, you can also purchase licenses for services offered by third-party apps for users in your organization.</span></span> <span data-ttu-id="53809-110">表の [**ライセンス**数の列には、アプリでの購入に SaaS サブスクリプションが提供されているかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="53809-110">The **Licenses** column in the table indicates whether an app offers a SaaS subscription for purchase.</span></span>

## <a name="search-for-and-purchase-services-for-a-third-party-app"></a><span data-ttu-id="53809-111">サードパーティ製のアプリを検索してサービスを購入する</span><span class="sxs-lookup"><span data-stu-id="53809-111">Search for and purchase services for a third-party app</span></span>

1. <span data-ttu-id="53809-112">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。</span><span class="sxs-lookup"><span data-stu-id="53809-112">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="53809-113">ページにアクセスするには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="53809-113">You must be a global admin or Teams service admin to access the page.</span></span>
2. <span data-ttu-id="53809-114">目的のアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="53809-114">Search for the app that you want.</span></span> <span data-ttu-id="53809-115">有料 SaaS サブスクリプションを持っているアプリを特定するには、[**ライセンス**] 列を確認します。</span><span class="sxs-lookup"><span data-stu-id="53809-115">To identify apps that have a paid SaaS subscription, look in the **Licenses** column.</span></span> <span data-ttu-id="53809-116">各アプリには、次のいずれかの値があります。</span><span class="sxs-lookup"><span data-stu-id="53809-116">Each app will have one of the following values:</span></span>
    - <span data-ttu-id="53809-117">**今すぐ購入**: アプリは SaaS サブスクリプションを提供し、購入することができます。</span><span class="sxs-lookup"><span data-stu-id="53809-117">**Purchase now**: The app offers a SaaS subscription and is available to purchase.</span></span>  
    - <span data-ttu-id="53809-118">**購入**済み: アプリには SaaS サブスクリプションが用意されており、ライセンスを購入しています。</span><span class="sxs-lookup"><span data-stu-id="53809-118">**Purchased**: The app offers a SaaS subscription and you've purchased licenses for it.</span></span>
    - <span data-ttu-id="53809-119">**-----------** アプリは SaaS サブスクリプションを提供しません。</span><span class="sxs-lookup"><span data-stu-id="53809-119">**- -**: The app doesn't offer a SaaS subscription.</span></span>
3. <span data-ttu-id="53809-120">アプリが見つかったら、[**今すぐ購入**] をクリックして、[アプリの詳細] ページの [**プランと価格**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="53809-120">When you find the app, click **Purchase now** to go to the **Plans and pricing** tab of the app details page.</span></span> <span data-ttu-id="53809-121">アプリの SaaS サービスの計画と価格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="53809-121">Review the plans and pricing information for the SaaS offer for the app.</span></span> <span data-ttu-id="53809-122">詳細情報が必要な場合は、[**詳細**情報] リンクをクリックして、 [appsource](https://appsource.microsoft.com/)のアプリのページに移動します。</span><span class="sxs-lookup"><span data-stu-id="53809-122">If you need more information, click the **learn more** link to go to the app's page on [AppSource](https://appsource.microsoft.com/).</span></span>  
4. <span data-ttu-id="53809-123">プランを購入するには、[**今すぐ購入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53809-123">To buy a plan, click **Purchase now**.</span></span> <span data-ttu-id="53809-124">Teams アプリに関連付けられたプランの購入エクスペリエンスにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="53809-124">You'll be redirected to the purchase experience for the offer associated with the Teams app.</span></span> <span data-ttu-id="53809-125">ここでは、サービスまたは SaaS 提供の購入を完了します。</span><span class="sxs-lookup"><span data-stu-id="53809-125">This is where you'll complete your purchase of the service or SaaS offer.</span></span>
5. <span data-ttu-id="53809-126">目的のプランを選択します。</span><span class="sxs-lookup"><span data-stu-id="53809-126">Choose the plan that you want.</span></span> <span data-ttu-id="53809-127">SaaS オファーに複数のプランが含まれている場合は、[**変更**] をクリックすると、利用可能なプランの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="53809-127">If the SaaS offer includes more than one plan, click **Change** to see the list of available plans.</span></span>
6. <span data-ttu-id="53809-128">支払い条件 (**毎月**または**年次**のいずれか) を選択し、購入するユーザーライセンスの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="53809-128">Select your billing term (either **Monthly** or **Yearly**), and then enter the number of user licenses that you want to buy.</span></span>
7. <span data-ttu-id="53809-129">支払い方法を入力します。</span><span class="sxs-lookup"><span data-stu-id="53809-129">Enter your payment method.</span></span>
8. <span data-ttu-id="53809-130">準備ができたら、[**注文**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53809-130">When you're ready, select **Place order**.</span></span>
9. <span data-ttu-id="53809-131">[**今すぐ構成**] をクリックして、パブリッシャーの web サイトでサブスクリプションをアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="53809-131">Click **Configure now** to activate your subscription on the publisher's website.</span></span>

<span data-ttu-id="53809-132">Teams アプリに関連付けられている SaaS サービスを購入したら、[**アプリの管理**] ページで次の購入の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="53809-132">After you've purchased the SaaS offer associated with the Teams app, you can view the following purchase details on the **Manage apps** page.</span></span>

- <span data-ttu-id="53809-133">**ライセンス認証日**: ライセンスが有効化された日付。</span><span class="sxs-lookup"><span data-stu-id="53809-133">**License activation date**: Date on which your license was activated.</span></span> <span data-ttu-id="53809-134">アカウントがまだ設定されていない場合は、**サブスクリプションの有効化が保留中**であることを示します。</span><span class="sxs-lookup"><span data-stu-id="53809-134">If your account isn't yet set up, this shows as **Subscription pending activation**.</span></span>
- <span data-ttu-id="53809-135">**ライセンス**数: 購入したライセンスの数。</span><span class="sxs-lookup"><span data-stu-id="53809-135">**Licenses**: Number of licenses you purchased.</span></span>

<span data-ttu-id="53809-136">[**ライセンスの管理**] を選択して、Microsoft 365 管理センターに移動し、購入したライセンスを表示して管理し、ユーザーのライセンスの割り当てを管理します。</span><span class="sxs-lookup"><span data-stu-id="53809-136">Select **Manage licenses** to go to the Microsoft 365 admin center to view and manage the licenses you purchased and to manage license assignments for users.</span></span>

<span data-ttu-id="53809-137">グローバル管理者は、組織内のすべての人によって行われた購入を表示できます。 Teams サービス管理者は、自分が行った購入のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="53809-137">Global admins can view the purchases made by anyone in the organization whereas Teams service admins can only view the purchases made by themselves.</span></span>  

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a><span data-ttu-id="53809-138">Microsoft Teams 管理センターと AppSource でリストして販売したい Teams アプリのために SaaS が提供されていますか?</span><span class="sxs-lookup"><span data-stu-id="53809-138">Have a SaaS offer for a Teams app that you want to list and sell in the Microsoft Teams admin center and AppSource?</span></span>

<span data-ttu-id="53809-139">開発者は、チームアプリに関連付けられた SaaS の提供を作成できます。</span><span class="sxs-lookup"><span data-stu-id="53809-139">Developers can create SaaS offers associated with their Teams apps.</span></span> <span data-ttu-id="53809-140">これらのサービスは、[パートナーセンター](https://partner.microsoft.com)を通じて公開され、組織が[Appsource](https://appsource.microsoft.com/)および Microsoft Teams 管理センターを通じて購入することができます。</span><span class="sxs-lookup"><span data-stu-id="53809-140">These offers are published through [Partner Center](https://partner.microsoft.com) and are available for organizations to purchase through [AppSource](https://appsource.microsoft.com/) and the Microsoft Teams admin center.</span></span>
 
<span data-ttu-id="53809-141">サードパーティのアプリ開発者は、詳細について[、市販の市場で新しい Saas サービスを作成](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer)できます。</span><span class="sxs-lookup"><span data-stu-id="53809-141">Third-party app developers can go to [Create a new Saas offer in the commercial marketplace](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer) for more information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="53809-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="53809-142">Related topics</span></span>


