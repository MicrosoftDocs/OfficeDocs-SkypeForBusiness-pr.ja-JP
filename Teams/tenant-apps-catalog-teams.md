---
title: Microsoft Teams テナント アプリ カタログにアプリを公開する
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/15/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Microsoft Teams テナントアプリカタログにアプリを公開するためのガイダンス。
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.apppolicies.publishtenantapps
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebc26292e41328589f302127980f4a303efd46a2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226712"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="ed9cd-103">Microsoft Teams テナント アプリ カタログにアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="ed9cd-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="ed9cd-104">Microsoft Teams テナントのアプリカタログを使って、基幹業務アプリケーションのテストと組織への配布を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="ed9cd-105">Teams テナントアプリカタログを使うと、組織専用に構築された基幹業務アプリケーションを配布できます。また、重要なビジネス機能をユーザーに対して実行することに依存します。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-105">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="ed9cd-106">グローバル管理者の資格情報を使用してチームクライアントにサインインし、組織のアプリを公開します。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-106">Sign in to your Teams client using your global admin credentials and publish apps for your organization.</span></span> 

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="ed9cd-107">Teams クライアントからテナントアプリカタログにアプリを発行する</span><span class="sxs-lookup"><span data-stu-id="ed9cd-107">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

<span data-ttu-id="ed9cd-108">注: 組織のアプリを公開するには、グローバル管理者の資格情報を使用して Microsoft Teams クライアントにサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-108">NOTE: You need to be signed in to the Microsoft Teams client using your global admin credentials to publish apps for your organization.</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="ed9cd-109">Teams アプリパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="ed9cd-109">Get a Teams app package</span></span>

<span data-ttu-id="ed9cd-110">Teams アプリパッケージは、 [Teams アプリ Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-110">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="ed9cd-111">アプリパッケージを取得したら、エンタープライズアプリカタログに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-111">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="ed9cd-112">テナントのすべてのユーザーがアプリカタログを表示できますが、現時点では、グローバル管理者のみが公開と管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-112">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="ed9cd-113">(最終的には、チームの管理者がこの操作を実行できるようになります)。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-113">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="ed9cd-114">テナントアプリカタログに移動します。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="ed9cd-115">Microsoft Teams クライアントを起動して、グローバル管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-115">Launch the Microsoft Teams client and sign-in using your global admin credentials.</span></span> <span data-ttu-id="ed9cd-116">Microsoft Teams ストアで、特定の組織に対応する新しいセクション (この例では Contoso) を選びます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="ed9cd-117">組織内のユーザーは、カタログ内のアプリを表示して、メンバーになっているチームにインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-117">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="ed9cd-119">テナントアプリカタログにアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="ed9cd-119">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="ed9cd-120">ストアで、[ > **Contoso の\*\*\*\*カスタムアプリアップロードのアップロード**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-120">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image02.png)

<span data-ttu-id="ed9cd-122">([**自分のアップロード] または [自分のチーム**(サイドローディングと呼ばれる)] を選択して、アプリを自分または選択したチームのみが利用できるようにすることもできます。)</span><span class="sxs-lookup"><span data-stu-id="ed9cd-122">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="ed9cd-123">アプリパッケージに移動して選択します。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-123">Navigate to the app package and select it.</span></span>

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image03.png)

<span data-ttu-id="ed9cd-125">テナントアプリカタログに戻ると、新しいエンタープライズアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-125">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="ed9cd-126">このアプリカタログには、自分と組織のメンバーのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-126">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="ed9cd-127">テナントアプリカタログのアプリを更新する</span><span class="sxs-lookup"><span data-stu-id="ed9cd-127">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="ed9cd-128">テナントアプリカタログで、[**..**.] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-128">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="ed9cd-129">更新するアプリの右上にあります。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-129">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="ed9cd-130">更新されたアプリパッケージに移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-130">Navigate to the updated app package and select it.</span></span>

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image04.png)

<span data-ttu-id="ed9cd-132">アプリはバージョン2.0 に更新されます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-132">The app will be revised to version 2.0.</span></span> <span data-ttu-id="ed9cd-133">このメニューから会社全体のアプリを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-133">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="ed9cd-134">Office 365 管理ポータルを使用してテナントアプリカタログを管理する</span><span class="sxs-lookup"><span data-stu-id="ed9cd-134">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="ed9cd-135">バグの修正が必要なアプリがある場合は、Office 365 管理ポータルを使用してアプリを一時的に無効にすることができます。 [**設定** > **サービス & アドイン** > の**Microsoft Teams**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-135">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal, select **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="ed9cd-136">以前の設定に加えて、お客様の会社のアプリ専用のセクションが追加されました。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-136">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="ed9cd-137">有効または無効にするアプリを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-137">You can choose which apps you want to enable or disable.</span></span>

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image05.png)

<span data-ttu-id="ed9cd-139">これにより、ユーザーはアプリを完全に削除せずに、アプリとやり取りすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-139">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="ed9cd-140">これらのコントロールを使うと、管理者は、企業のアプリのガバナンスをさらに柔軟に管理できます。</span><span class="sxs-lookup"><span data-stu-id="ed9cd-140">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


