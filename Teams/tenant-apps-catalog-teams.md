---
title: Microsoft Teams テナントアプリカタログでアプリを公開する
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
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
ms.openlocfilehash: 5d016fd1c341774115b9b68edafcc47a63e42b0d
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221326"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="28b33-103">Microsoft Teams テナントアプリカタログでアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="28b33-103">Publish apps in the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="28b33-104">Microsoft Teams テナントのアプリカタログを使って、基幹業務アプリケーションのテストと組織への配布を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="28b33-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="28b33-105">Teams テナントアプリカタログを使用すると、組織専用に構築された基幹業務アプリケーションを配布することができ、重要なビジネス機能の実行に依存することになります。</span><span class="sxs-lookup"><span data-stu-id="28b33-105">The Teams Tenant Apps Catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="28b33-106">組織のアプリを公開するには、グローバル管理者の資格情報を使用してチームクライアントにサインインし、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="28b33-106">To publish apps for your organization, sign in to your Teams client using your global admin credentials and then follow the instructions below.</span></span>

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="28b33-107">Teams クライアントからテナントアプリカタログ内のアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="28b33-107">Publish an app in the Tenant Apps Catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="28b33-108">組織のアプリを公開するには、グローバル管理者の資格情報を使用して Microsoft Teams クライアントにサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="28b33-108">You need to be signed in to the Microsoft Teams client using your global admin credentials to publish apps for your organization.</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="28b33-109">Teams アプリパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="28b33-109">Get a Teams app package</span></span>

<span data-ttu-id="28b33-110">Teams アプリパッケージは、 [Teams アプリ Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="28b33-110">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="28b33-111">アプリパッケージを取得したら、エンタープライズアプリカタログに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="28b33-111">Once you have the app package, you can add it to the enterprise app catalog.</span></span> <span data-ttu-id="28b33-112">テナントのすべてのユーザーがアプリカタログを表示できますが、現時点では、グローバル管理者のみが公開と管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="28b33-112">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="28b33-113">(最終的には、チームの管理者がこの操作を実行できるようになります)。</span><span class="sxs-lookup"><span data-stu-id="28b33-113">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="28b33-114">テナントアプリカタログに移動します。</span><span class="sxs-lookup"><span data-stu-id="28b33-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="28b33-115">Microsoft Teams クライアントを起動して、グローバル管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="28b33-115">Start the Microsoft Teams client and sign-in using your global admin credentials.</span></span> <span data-ttu-id="28b33-116">Microsoft Teams ストアで、特定の組織に対応する新しいセクション (この例では Contoso) を選びます。</span><span class="sxs-lookup"><span data-stu-id="28b33-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="28b33-117">組織内のユーザーは、カタログ内のアプリを表示して、メンバーになっているチームに対してアプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="28b33-117">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="28b33-119">テナントアプリカタログにアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="28b33-119">Add an app to the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="28b33-120">ストアで、[ > **Contoso の\*\*\*\*カスタムアプリアップロードのアップロード**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="28b33-120">From the store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image02.png)

    <span data-ttu-id="28b33-122">( **[自分のアップロード] または [自分のチーム**] (*サイドローディング*と呼ばれます) を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="28b33-122">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="28b33-123">サイドローディングによって、アプリはチームまたは選択したチームのみが利用できるようになります。)</span><span class="sxs-lookup"><span data-stu-id="28b33-123">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="28b33-124">アプリパッケージに移動して選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28b33-124">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image03.png)

<span data-ttu-id="28b33-126">テナントアプリカタログに戻ると、新しいエンタープライズアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="28b33-126">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="28b33-127">このアプリカタログには、自分と組織のメンバーのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="28b33-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="28b33-128">テナントアプリカタログのアプリを更新する</span><span class="sxs-lookup"><span data-stu-id="28b33-128">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="28b33-129">テナントアプリカタログで、[**..**.] を選びます。</span><span class="sxs-lookup"><span data-stu-id="28b33-129">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="28b33-130">更新するアプリの右上にあります。</span><span class="sxs-lookup"><span data-stu-id="28b33-130">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="28b33-131">更新されたアプリパッケージに移動して選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28b33-131">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image04.png)

<span data-ttu-id="28b33-133">アプリはバージョン2.0 に更新されます。</span><span class="sxs-lookup"><span data-stu-id="28b33-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="28b33-134">このメニューから会社全体のアプリを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="28b33-134">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="28b33-135">Office 365 管理ポータルを使用してテナントアプリカタログを管理する</span><span class="sxs-lookup"><span data-stu-id="28b33-135">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="28b33-136">バグ修正が必要なアプリがある場合は、Office 365 管理ポータルを通じてアプリを一時的に無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="28b33-136">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="28b33-137">[**設定** > **サービス & アドインの** > **Microsoft Teams**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28b33-137">Select **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="28b33-138">以前の設定に加えて、お客様の会社のアプリ専用のセクションが追加されました。</span><span class="sxs-lookup"><span data-stu-id="28b33-138">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="28b33-139">有効または無効にするアプリを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="28b33-139">You can choose which apps you want to enable or disable.</span></span>

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image05.png)

<span data-ttu-id="28b33-141">アプリを無効にすると、アプリを完全に削除せずに、ユーザーがアプリを操作できなくなります。</span><span class="sxs-lookup"><span data-stu-id="28b33-141">Disabling an app will block users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="28b33-142">これらのコントロールを使用すると、企業でアプリを管理するときの柔軟性と制御がさらに向上します。</span><span class="sxs-lookup"><span data-stu-id="28b33-142">These controls give you additional flexibility and control when managing apps in your enterprise.</span></span>
