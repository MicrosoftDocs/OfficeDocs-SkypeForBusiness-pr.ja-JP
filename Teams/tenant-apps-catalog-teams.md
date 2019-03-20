---
title: Microsoft Teams テナント アプリ カタログにアプリを公開する
author: lolaj
ms.author: lolaj
manager: serdars
ms.date: 03/15/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: マイクロソフト チームのテナントのアプリケーション カタログでアプリケーションを発行するためのガイダンスです。
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.apppolicies.publishtenantapps
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 909ed249ea4e408cbddcd52824a7cb0047504613
ms.sourcegitcommit: 28dd9b8ca3de35a73e4d6923eff5546925435b8b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30684073"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="2723e-103">Microsoft Teams テナント アプリ カタログにアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="2723e-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="2723e-104">マイクロソフト チームのテナントのアプリケーション カタログを使用するにはテストし、組織の基幹業務アプリケーションを配布します。</span><span class="sxs-lookup"><span data-stu-id="2723e-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="2723e-105">チーム テナント アプリケーション カタログでは、組織用に構築された基幹業務アプリケーションを配布することができに依存することは、ユーザーに重要なビジネス機能を完了します。</span><span class="sxs-lookup"><span data-stu-id="2723e-105">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="2723e-106">グローバル管理者の資格情報を使用して、チームのクライアントにサインインし、組織のアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="2723e-106">Sign in to your Teams client using your global admin credentials and publish apps for your organization.</span></span> 

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="2723e-107">テナント アプリケーション カタログにチームのクライアントからアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="2723e-107">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

<span data-ttu-id="2723e-108">注: 組織のアプリケーションを発行するのには、グローバル管理者の資格情報を使用してマイクロソフトのチームのクライアントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2723e-108">NOTE: You need to be signed in to the Microsoft Teams client using your global admin credentials to publish apps for your organization.</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="2723e-109">チームのアプリケーション パッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="2723e-109">Get a Teams app package</span></span>

<span data-ttu-id="2723e-110">チームのアプリケーション パッケージを作成するには、[チームの App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)を使用します。</span><span class="sxs-lookup"><span data-stu-id="2723e-110">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="2723e-111">アプリケーション パッケージを作成したらは、エンタープライズ アプリケーションのカタログに追加できます。</span><span class="sxs-lookup"><span data-stu-id="2723e-111">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="2723e-112">テナント内のすべてのユーザーの中に持つことができますビュー現在のみグローバル管理者、アプリケーション カタログを発行し、管理する機能です。</span><span class="sxs-lookup"><span data-stu-id="2723e-112">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="2723e-113">(最終的には、チームを管理できるようになりますも。)</span><span class="sxs-lookup"><span data-stu-id="2723e-113">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="2723e-114">テナント アプリケーション カタログに移動します。</span><span class="sxs-lookup"><span data-stu-id="2723e-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="2723e-115">マイクロソフト チームのクライアントを起動し、グローバル管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="2723e-115">Launch the Microsoft Teams client and sign-in using your global admin credentials.</span></span> <span data-ttu-id="2723e-116">マイクロソフト チーム ストアから、特定の組織 (Contoso など) での新しいセクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2723e-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="2723e-117">ユーザーが組織内では、カタログでアプリケーションを表示でき、チームのメンバーになっているうちにそれらをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="2723e-117">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="2723e-119">テナント アプリケーション カタログにアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="2723e-119">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="2723e-120">ストアから**カスタム アプリケーションのアップロード**を選択して > **の contoso 社のアップロード**します。</span><span class="sxs-lookup"><span data-stu-id="2723e-120">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image02.png)

<span data-ttu-id="2723e-122">(することもできます**自分または自分のチームのアップロード**をアプリケーションで、またはの選択したチームにのみ使用可能な sideloading と呼ばれる。)</span><span class="sxs-lookup"><span data-stu-id="2723e-122">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="2723e-123">アプリケーション パッケージに移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="2723e-123">Navigate to the app package and select it.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image03.png)

<span data-ttu-id="2723e-125">テナント アプリケーション カタログに戻すと、新しいエンタープライズ アプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="2723e-125">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="2723e-126">組織のメンバーだけにこのアプリケーションのカタログへのアクセスがあることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="2723e-126">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="2723e-127">テナント アプリケーション カタログでアプリケーションを更新します。</span><span class="sxs-lookup"><span data-stu-id="2723e-127">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="2723e-128">テナント アプリケーション カタログからの選択 [**]**</span><span class="sxs-lookup"><span data-stu-id="2723e-128">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="2723e-129">更新するアプリケーションの右側のトップします。</span><span class="sxs-lookup"><span data-stu-id="2723e-129">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="2723e-130">更新されたアプリケーション パッケージに移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="2723e-130">Navigate to the updated app package and select it.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image04.png)

<span data-ttu-id="2723e-132">アプリケーションはバージョン 2.0 に更新されます。</span><span class="sxs-lookup"><span data-stu-id="2723e-132">The app will be revised to version 2.0.</span></span> <span data-ttu-id="2723e-133">このメニューから会社全体のアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="2723e-133">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="2723e-134">Office 365 管理ポータルを使用して、テナントのアプリケーション カタログを管理するには</span><span class="sxs-lookup"><span data-stu-id="2723e-134">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="2723e-135">一時的に Office 365 管理ポータル アプリケーションを無効にすることができます**設定**を選択してバグの修正を必要とするアプリケーションがあれば、 > **サービス & アドイン** > **マイクロソフトのチーム**です。</span><span class="sxs-lookup"><span data-stu-id="2723e-135">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal, select **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="2723e-136">以前の設定は、今すぐセクション社内のアプリケーションに専用です。</span><span class="sxs-lookup"><span data-stu-id="2723e-136">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="2723e-137">どのアプリケーションを有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2723e-137">You can choose which apps you want to enable or disable.</span></span>

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image05.png)

<span data-ttu-id="2723e-139">これは、アプリケーションを完全に削除することがなく、アプリケーションと対話するユーザーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="2723e-139">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="2723e-140">これらのコントロールは柔軟性を管理者に提供し、タイミングを制御、企業内のアプリケーションの管理。</span><span class="sxs-lookup"><span data-stu-id="2723e-140">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


