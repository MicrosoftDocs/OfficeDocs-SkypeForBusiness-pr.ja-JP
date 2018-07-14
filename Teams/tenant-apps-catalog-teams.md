---
title: マイクロソフト チーム テナント アプリケーション カタログにアプリケーションを発行します。
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: マイクロソフト チームのテナントのアプリケーション カタログでアプリケーションを発行するためのガイダンスです。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11db7dec3122de3eb783152483a1575cf92dc585
ms.sourcegitcommit: 11adc15c5191d7bf6bb37058cae3d54649c25e97
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2018
ms.locfileid: "20363906"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="9966b-103">マイクロソフト チーム テナント アプリケーション カタログにアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="9966b-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="9966b-104">マイクロソフト チームのテナントのアプリケーション カタログを使用するにはテストし、組織の基幹業務アプリケーションを配布します。</span><span class="sxs-lookup"><span data-stu-id="9966b-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="9966b-105">チーム テナント アプリケーション カタログでは、組織用に構築された基幹業務アプリケーションを配布することができに依存することは、ユーザーに重要なビジネス機能を完了します。</span><span class="sxs-lookup"><span data-stu-id="9966b-105">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="9966b-106">チーム クライアントから直接チーム テナント アプリケーション カタログにアプリケーションを発行できます。</span><span class="sxs-lookup"><span data-stu-id="9966b-106">You can publish apps to the Teams Tenant Apps Catalog directly from the Teams client.</span></span>

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="9966b-107">テナント アプリケーション カタログにチームのクライアントからアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="9966b-107">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="9966b-108">チームのアプリケーション パッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="9966b-108">Get a Teams app package</span></span>

<span data-ttu-id="9966b-109">チームのアプリケーション パッケージを作成するには、[チームの App Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9966b-109">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="9966b-110">アプリケーション パッケージを作成したらは、エンタープライズ アプリケーションのカタログに追加できます。</span><span class="sxs-lookup"><span data-stu-id="9966b-110">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="9966b-111">テナント内のすべてのユーザーは、アプリケーションのカタログを表示できますが、ときにそれを管理することがある管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="9966b-111">While all users in the tenant can view the app catalog, only admins have the ability to manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="9966b-112">テナント アプリケーション カタログに移動します。</span><span class="sxs-lookup"><span data-stu-id="9966b-112">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="9966b-113">マイクロソフト チーム ストアから、特定の組織 (Contoso など) での新しいセクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9966b-113">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="9966b-114">ユーザーが組織内では、カタログでアプリケーションを表示でき、チームのメンバーになっているうちにそれらをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="9966b-114">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="9966b-116">テナント アプリケーション カタログにアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="9966b-116">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="9966b-117">ストアから**カスタム アプリケーションのアップロード**を選択して > **の contoso 社のアップロード**します。</span><span class="sxs-lookup"><span data-stu-id="9966b-117">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image02.png)

<span data-ttu-id="9966b-119">(することもできます**自分または自分のチームのアップロード**をアプリケーションで、またはの選択したチームにのみ使用可能な sideloading と呼ばれる。)</span><span class="sxs-lookup"><span data-stu-id="9966b-119">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="9966b-120">アプリケーション パッケージに移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="9966b-120">Navigate to the app package and select it.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image03.png)

<span data-ttu-id="9966b-122">テナント アプリケーション カタログに戻すと、新しいエンタープライズ アプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="9966b-122">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="9966b-123">組織のメンバーだけにこのアプリケーションのカタログへのアクセスがあることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="9966b-123">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="9966b-124">テナント アプリケーション カタログでアプリケーションを更新します。</span><span class="sxs-lookup"><span data-stu-id="9966b-124">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="9966b-125">テナント アプリケーション カタログからの選択 [**]**</span><span class="sxs-lookup"><span data-stu-id="9966b-125">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="9966b-126">更新するアプリケーションの右側のトップします。</span><span class="sxs-lookup"><span data-stu-id="9966b-126">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="9966b-127">更新されたアプリケーション パッケージに移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="9966b-127">Navigate to the updated app package and select it.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image04.png)

<span data-ttu-id="9966b-129">アプリケーションはバージョン 2.0 に更新されます。</span><span class="sxs-lookup"><span data-stu-id="9966b-129">The app will be revised to version 2.0.</span></span> <span data-ttu-id="9966b-130">このメニューから会社全体のアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="9966b-130">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="9966b-131">Office 365 管理ポータルを使用して、テナントのアプリケーション カタログを管理するには</span><span class="sxs-lookup"><span data-stu-id="9966b-131">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="9966b-132">バグの修正を必要とするアプリケーションがあれば、Office 365 管理ポータル アプリケーションを一時的に無効にできます。</span><span class="sxs-lookup"><span data-stu-id="9966b-132">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="9966b-133">以前の設定は、今すぐセクション社内のアプリケーションに専用です。</span><span class="sxs-lookup"><span data-stu-id="9966b-133">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="9966b-134">どのアプリケーションを有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9966b-134">You can choose which apps you want to enable or disable.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image05.png)

<span data-ttu-id="9966b-136">これは、アプリケーションを完全に削除することがなく、アプリケーションと対話するユーザーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="9966b-136">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="9966b-137">これらのコントロールは柔軟性を管理者に提供し、タイミングを制御、企業内のアプリケーションの管理。</span><span class="sxs-lookup"><span data-stu-id="9966b-137">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


