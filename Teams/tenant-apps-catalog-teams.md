---
title: マイクロソフト チーム テナント アプリケーション カタログにアプリケーションを発行します。
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: マイクロソフト チームのテナントのアプリケーション カタログでアプリケーションを発行するためのガイダンスです。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5028f5f1ee848d4fa7af7e15083dc06d90f9f38a
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017962"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="0705c-103">マイクロソフト チーム テナント アプリケーション カタログにアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="0705c-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="0705c-104">マイクロソフト チームのテナントのアプリケーション カタログを使用するにはテストし、組織の基幹業務アプリケーションを配布します。</span><span class="sxs-lookup"><span data-stu-id="0705c-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="0705c-105">チーム テナント アプリケーション カタログでは、組織用に構築された基幹業務アプリケーションを配布することができに依存することは、ユーザーに重要なビジネス機能を完了します。</span><span class="sxs-lookup"><span data-stu-id="0705c-105">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="0705c-106">チーム クライアントから直接チーム テナント アプリケーション カタログにアプリケーションを発行できます。</span><span class="sxs-lookup"><span data-stu-id="0705c-106">You can publish apps to the Teams Tenant Apps Catalog directly from the Teams client.</span></span>

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="0705c-107">テナント アプリケーション カタログにチームのクライアントからアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="0705c-107">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="0705c-108">チームのアプリケーション パッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="0705c-108">Get a Teams app package</span></span>

<span data-ttu-id="0705c-109">チームのアプリケーション パッケージを作成するには、[チームの App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0705c-109">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="0705c-110">アプリケーション パッケージを作成したらは、エンタープライズ アプリケーションのカタログに追加できます。</span><span class="sxs-lookup"><span data-stu-id="0705c-110">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="0705c-111">テナント内のすべてのユーザーの中に持つことができますビュー現在のみグローバル管理者、アプリケーション カタログを発行し、管理する機能です。</span><span class="sxs-lookup"><span data-stu-id="0705c-111">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="0705c-112">(最終的には、チームを管理できるようになりますも。)</span><span class="sxs-lookup"><span data-stu-id="0705c-112">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="0705c-113">テナント アプリケーション カタログに移動します。</span><span class="sxs-lookup"><span data-stu-id="0705c-113">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="0705c-114">マイクロソフト チーム ストアから、特定の組織 (Contoso など) での新しいセクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0705c-114">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="0705c-115">ユーザーが組織内では、カタログでアプリケーションを表示でき、チームのメンバーになっているうちにそれらをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="0705c-115">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="0705c-117">テナント アプリケーション カタログにアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="0705c-117">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="0705c-118">ストアから**カスタム アプリケーションのアップロード**を選択して > **の contoso 社のアップロード**します。</span><span class="sxs-lookup"><span data-stu-id="0705c-118">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image02.png)

<span data-ttu-id="0705c-120">(することもできます**自分または自分のチームのアップロード**をアプリケーションで、またはの選択したチームにのみ使用可能な sideloading と呼ばれる。)</span><span class="sxs-lookup"><span data-stu-id="0705c-120">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="0705c-121">アプリケーション パッケージに移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="0705c-121">Navigate to the app package and select it.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image03.png)

<span data-ttu-id="0705c-123">テナント アプリケーション カタログに戻すと、新しいエンタープライズ アプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="0705c-123">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="0705c-124">組織のメンバーだけにこのアプリケーションのカタログへのアクセスがあることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="0705c-124">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="0705c-125">テナント アプリケーション カタログでアプリケーションを更新します。</span><span class="sxs-lookup"><span data-stu-id="0705c-125">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="0705c-126">テナント アプリケーション カタログからの選択 [**]**</span><span class="sxs-lookup"><span data-stu-id="0705c-126">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="0705c-127">更新するアプリケーションの右側のトップします。</span><span class="sxs-lookup"><span data-stu-id="0705c-127">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="0705c-128">更新されたアプリケーション パッケージに移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="0705c-128">Navigate to the updated app package and select it.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image04.png)

<span data-ttu-id="0705c-130">アプリケーションはバージョン 2.0 に更新されます。</span><span class="sxs-lookup"><span data-stu-id="0705c-130">The app will be revised to version 2.0.</span></span> <span data-ttu-id="0705c-131">このメニューから会社全体のアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="0705c-131">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="0705c-132">Office 365 管理ポータルを使用して、テナントのアプリケーション カタログを管理するには</span><span class="sxs-lookup"><span data-stu-id="0705c-132">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="0705c-133">バグの修正を必要とするアプリケーションがあれば、Office 365 管理ポータル アプリケーションを一時的に無効にできます。</span><span class="sxs-lookup"><span data-stu-id="0705c-133">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="0705c-134">以前の設定は、今すぐセクション社内のアプリケーションに専用です。</span><span class="sxs-lookup"><span data-stu-id="0705c-134">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="0705c-135">どのアプリケーションを有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0705c-135">You can choose which apps you want to enable or disable.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image05.png)

<span data-ttu-id="0705c-137">これは、アプリケーションを完全に削除することがなく、アプリケーションと対話するユーザーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="0705c-137">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="0705c-138">これらのコントロールは柔軟性を管理者に提供し、タイミングを制御、企業内のアプリケーションの管理。</span><span class="sxs-lookup"><span data-stu-id="0705c-138">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


