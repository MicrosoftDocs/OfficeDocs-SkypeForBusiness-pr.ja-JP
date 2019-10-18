---
title: Microsoft Teams テナントアプリカタログでアプリを公開する
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Microsoft Teams テナントアプリカタログにアプリを公開するためのガイダンス。
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5affe464ac300d0084916ad8ec0044ca74f8fa6b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570082"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="f89ef-103">Microsoft Teams テナントアプリカタログでアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="f89ef-103">Publish apps in the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="f89ef-104">Microsoft Teams テナントのアプリカタログを使って、基幹業務アプリケーションのテストと組織への配布を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="f89ef-105">Teams テナントアプリカタログを使用すると、組織専用に構築された基幹業務アプリケーションを配布することができ、重要なビジネス機能の実行に依存することになります。</span><span class="sxs-lookup"><span data-stu-id="f89ef-105">The Teams Tenant Apps Catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="f89ef-106">組織のアプリを公開するには、グローバル管理者または teams サービスの管理者ロールを持つアカウントを使用してチームクライアントにサインインし、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f89ef-106">To publish apps for your organization, sign in to your Teams client using an account with the global admin or teams service admin roles and then follow the instructions below.</span></span>

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="f89ef-107">Teams クライアントからテナントアプリカタログ内のアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="f89ef-107">Publish an app in the Tenant Apps Catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="f89ef-108">組織のアプリを公開するには、グローバル管理者または Teams サービスの管理者ロールが有効になっているアカウントを使用して、Microsoft Teams クライアントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f89ef-108">You need to be signed in to the Microsoft Teams client with an account that has either the global admin or teams service admin role enabled to publish apps for your organization.</span></span> <span data-ttu-id="f89ef-109">[管理者ロールを使用してチームを管理する](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles)方法について、詳細はこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f89ef-109">Learn more about [using administrator roles to manage Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="f89ef-110">Teams アプリパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="f89ef-110">Get a Teams app package</span></span>

<span data-ttu-id="f89ef-111">Teams アプリパッケージは、 [Teams アプリ Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="f89ef-112">アプリパッケージを取得したら、エンタープライズアプリカタログに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-112">Once you have the app package, you can add it to the enterprise app catalog.</span></span> <span data-ttu-id="f89ef-113">テナントのすべてのユーザーがアプリカタログを表示できますが、グローバル管理者と teams サービス管理者だけが公開および管理できます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-113">While all users in the tenant can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="f89ef-114">テナントアプリカタログに移動します。</span><span class="sxs-lookup"><span data-stu-id="f89ef-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="f89ef-115">Microsoft Teams クライアントを起動し、グローバルまたは Teams サービス管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="f89ef-115">Start the Microsoft Teams client and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="f89ef-116">Microsoft Teams ストアで、特定の組織に対応する新しいセクション (この例では Contoso) を選びます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="f89ef-117">組織内のユーザーは、カタログ内のアプリを表示して、メンバーになっているチームに対してアプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-117">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="f89ef-119">テナントアプリカタログにアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="f89ef-119">Add an app to the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="f89ef-120">ストアで、[ > **Contoso の\*\*\*\*カスタムアプリアップロードのアップロード**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-120">From the store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image02.png)

    <span data-ttu-id="f89ef-122">( **[自分のアップロード] または [自分のチーム**] (*サイドローディング*と呼ばれます) を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-122">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="f89ef-123">サイドローディングによって、アプリはチームまたは選択したチームのみが利用できるようになります。)</span><span class="sxs-lookup"><span data-stu-id="f89ef-123">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="f89ef-124">アプリパッケージに移動して選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f89ef-124">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image03.png)

<span data-ttu-id="f89ef-126">テナントアプリカタログに戻ると、新しいエンタープライズアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-126">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="f89ef-127">このアプリカタログには、自分と組織のメンバーのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="f89ef-128">テナントアプリカタログのアプリを更新する</span><span class="sxs-lookup"><span data-stu-id="f89ef-128">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="f89ef-129">テナントアプリカタログで、[**..**.] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-129">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="f89ef-130">更新するアプリの右上にあります。</span><span class="sxs-lookup"><span data-stu-id="f89ef-130">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="f89ef-131">更新されたアプリパッケージに移動して選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f89ef-131">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image04.png)

<span data-ttu-id="f89ef-133">アプリはバージョン2.0 に更新されます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="f89ef-134">このメニューから会社全体のアプリを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-134">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="f89ef-135">Office 365 管理ポータルを使用してテナントアプリカタログを管理する</span><span class="sxs-lookup"><span data-stu-id="f89ef-135">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="f89ef-136">バグ修正が必要なアプリがある場合は、Office 365 管理ポータルを通じてアプリを一時的に無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-136">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="f89ef-137">[**設定** > **サービス & アドインの** > **Microsoft Teams**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f89ef-137">Select **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="f89ef-138">以前の設定に加えて、お客様の会社のアプリ専用のセクションが追加されました。</span><span class="sxs-lookup"><span data-stu-id="f89ef-138">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="f89ef-139">有効または無効にするアプリを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="f89ef-139">You can choose which apps you want to enable or disable.</span></span>

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image05.png)

<span data-ttu-id="f89ef-141">アプリを無効にすると、アプリを完全に削除せずに、ユーザーがアプリを操作できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f89ef-141">Disabling an app will block users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="f89ef-142">これらのコントロールを使用すると、企業でアプリを管理するときの柔軟性と制御がさらに向上します。</span><span class="sxs-lookup"><span data-stu-id="f89ef-142">These controls give you additional flexibility and control when managing apps in your enterprise.</span></span>
