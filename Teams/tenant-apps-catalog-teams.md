---
title: マイクロソフト チーム テナント アプリケーション カタログにアプリケーションを発行します。
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: マイクロソフト チームのテナントのアプリケーション カタログでアプリケーションを発行するためのガイダンスです。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 298caf3cee6fe6af38f22ef9ac7dd85991fd6dba
ms.sourcegitcommit: b42a6a56a0e1e4be1239174c1c3b4ab86517d043
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "20050458"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="a7ec7-103">マイクロソフト チーム テナント アプリケーション カタログにアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

> [!IMPORTANT]
> <span data-ttu-id="a7ec7-104">このページでは、プレリリース版の機能の説明し、リリース前に大幅に変更される可能性が暫定的なコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-104">This page describes a pre-release feature and contains preliminary content that might change substantially before it is released.</span></span> <span data-ttu-id="a7ec7-105">任意のスクリーン ショットでは、プレース ホルダーであるし、ものと異なって表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-105">Any screenshots are placeholders and might look different than what you see.</span></span>

<span data-ttu-id="a7ec7-106">マイクロソフト チームのテナントのアプリケーション カタログを使用するにはテストし、組織の基幹業務アプリケーションを配布します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-106">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="a7ec7-107">チーム テナント アプリケーション カタログでは、組織用に構築された基幹業務アプリケーションを配布することができに依存することは、ユーザーに重要なビジネス機能を完了します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-107">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="a7ec7-108">チーム クライアントから直接チーム テナント アプリケーション カタログにアプリケーションを発行できます。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-108">You can publish apps to the Teams Tenant Apps Catalog directly from the Teams client.</span></span>

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="a7ec7-109">テナント アプリケーション カタログにチームのクライアントからアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-109">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="a7ec7-110">チームのアプリケーション パッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-110">Get a Teams app package</span></span>

<span data-ttu-id="a7ec7-111">チームのアプリケーション パッケージを作成するには、[チームの App Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio)を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="a7ec7-112">アプリケーション パッケージを作成したらは、エンタープライズ アプリケーションのカタログに追加できます。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-112">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="a7ec7-113">テナント内のすべてのユーザーは、アプリケーションのカタログを表示できますが、ときにそれを管理することがある管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-113">While all users in the tenant can view the app catalog, only admins have the ability to manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="a7ec7-114">テナント アプリケーション カタログに移動します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="a7ec7-115">マイクロソフト チーム ストアから、特定の組織 (Contoso など) での新しいセクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-115">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="a7ec7-116">ユーザーが組織内では、カタログでアプリケーションを表示でき、チームのメンバーになっているうちにそれらをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-116">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="a7ec7-118">テナント アプリケーション カタログにアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-118">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="a7ec7-119">ストアから**カスタム アプリケーションのアップロード**を選択して > **の contoso 社のアップロード**します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-119">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image02.png)

<span data-ttu-id="a7ec7-121">(することもできます**自分または自分のチームのアップロード**をアプリケーションで、またはの選択したチームにのみ使用可能な sideloading と呼ばれる。)</span><span class="sxs-lookup"><span data-stu-id="a7ec7-121">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="a7ec7-122">アプリケーション パッケージに移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-122">Navigate to the app package and select it.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image03.png)

<span data-ttu-id="a7ec7-124">テナント アプリケーション カタログに戻すと、新しいエンタープライズ アプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-124">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="a7ec7-125">組織のメンバーだけにこのアプリケーションのカタログへのアクセスがあることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-125">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="a7ec7-126">テナント アプリケーション カタログでアプリケーションを更新します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-126">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="a7ec7-127">テナント アプリケーション カタログからの選択 [**]**</span><span class="sxs-lookup"><span data-stu-id="a7ec7-127">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="a7ec7-128">更新するアプリケーションの右側のトップします。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-128">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="a7ec7-129">更新されたアプリケーション パッケージに移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-129">Navigate to the updated app package and select it.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image04.png)

<span data-ttu-id="a7ec7-131">アプリケーションはバージョン 2.0 に更新されます。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-131">The app will be revised to version 2.0.</span></span> <span data-ttu-id="a7ec7-132">このメニューから会社全体のアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-132">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="a7ec7-133">Office 365 管理ポータルを使用して、テナントのアプリケーション カタログを管理するには</span><span class="sxs-lookup"><span data-stu-id="a7ec7-133">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="a7ec7-134">バグの修正を必要とするアプリケーションがあれば、Office 365 管理ポータル アプリケーションを一時的に無効にできます。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-134">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="a7ec7-135">以前の設定は、今すぐセクション社内のアプリケーションに専用です。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-135">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="a7ec7-136">どのアプリケーションを有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-136">You can choose which apps you want to enable or disable.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image05.png)

<span data-ttu-id="a7ec7-138">これは、アプリケーションを完全に削除することがなく、アプリケーションと対話するユーザーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-138">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="a7ec7-139">これらのコントロールは柔軟性を管理者に提供し、タイミングを制御、企業内のアプリケーションの管理。</span><span class="sxs-lookup"><span data-stu-id="a7ec7-139">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


