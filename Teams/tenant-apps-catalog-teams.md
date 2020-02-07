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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1b2fb38dcca7142cad82d290b1225e69f035bae
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836917"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="933d8-103">Microsoft Teams テナントアプリカタログでアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="933d8-103">Publish apps in the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="933d8-104">Microsoft Teams テナントのアプリカタログを使って、基幹業務アプリケーションのテストと組織への配布を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="933d8-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="933d8-105">Teams テナントアプリカタログを使用すると、組織専用に構築された基幹業務アプリケーションを配布することができ、重要なビジネス機能の実行に依存することになります。</span><span class="sxs-lookup"><span data-stu-id="933d8-105">The Teams Tenant Apps Catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="933d8-106">組織のアプリを公開するには、グローバル管理者または teams サービスの管理者ロールを持つアカウントを使用してチームクライアントにサインインし、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="933d8-106">To publish apps for your organization, sign in to your Teams client using an account with the global admin or teams service admin roles and then follow the instructions below.</span></span>

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="933d8-107">Teams クライアントからテナントアプリカタログ内のアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="933d8-107">Publish an app in the Tenant Apps Catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="933d8-108">組織のアプリを公開するには、グローバル管理者または Teams サービスの管理者ロールが有効になっているアカウントを使用して、Microsoft Teams クライアントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="933d8-108">You need to be signed in to the Microsoft Teams client with an account that has either the global admin or teams service admin role enabled to publish apps for your organization.</span></span> <span data-ttu-id="933d8-109">[管理者ロールを使用してチームを管理する](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles)方法について、詳細はこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="933d8-109">Learn more about [using administrator roles to manage Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="933d8-110">Teams アプリパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="933d8-110">Get a Teams app package</span></span>

<span data-ttu-id="933d8-111">Teams アプリパッケージは、 [Teams アプリ Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="933d8-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="933d8-112">アプリパッケージを取得したら、エンタープライズアプリカタログに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="933d8-112">Once you have the app package, you can add it to the enterprise app catalog.</span></span> <span data-ttu-id="933d8-113">テナントのすべてのユーザーがアプリカタログを表示できますが、グローバル管理者と teams サービス管理者だけが公開および管理できます。</span><span class="sxs-lookup"><span data-stu-id="933d8-113">While all users in the tenant can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="933d8-114">テナントアプリカタログに移動します。</span><span class="sxs-lookup"><span data-stu-id="933d8-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="933d8-115">Microsoft Teams クライアントを起動し、グローバルまたは Teams サービス管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="933d8-115">Start the Microsoft Teams client and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="933d8-116">アプリの左側にある [**アプリ**] を選択し、特定の組織に対応する新しいセクション (この例では、Contoso) を選びます。</span><span class="sxs-lookup"><span data-stu-id="933d8-116">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="933d8-117">組織内のユーザーは、カタログ内のアプリを表示して、メンバーになっているチームに対してアプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="933d8-117">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="933d8-119">テナントアプリカタログにアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="933d8-119">Add an app to the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="933d8-120">[**アプリ**] ページで、[ > **Contoso の\*\*\*\*カスタムアプリアップロードをアップロードする**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="933d8-120">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image02.png)

    <span data-ttu-id="933d8-122">( **[自分のアップロード] または [自分のチーム**] (*サイドローディング*と呼ばれます) を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="933d8-122">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="933d8-123">サイドローディングによって、アプリはチームまたは選択したチームのみが利用できるようになります。)</span><span class="sxs-lookup"><span data-stu-id="933d8-123">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="933d8-124">アプリパッケージに移動して選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="933d8-124">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image03.png)

<span data-ttu-id="933d8-126">テナントアプリカタログに戻ると、新しいエンタープライズアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="933d8-126">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="933d8-127">このアプリカタログには、自分と組織のメンバーのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="933d8-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="933d8-128">テナントアプリカタログのアプリを更新する</span><span class="sxs-lookup"><span data-stu-id="933d8-128">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="933d8-129">テナントアプリカタログで、[**..**.] を選びます。</span><span class="sxs-lookup"><span data-stu-id="933d8-129">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="933d8-130">更新するアプリの右上にあります。</span><span class="sxs-lookup"><span data-stu-id="933d8-130">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="933d8-131">更新されたアプリパッケージに移動して選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="933d8-131">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image04.png)

<span data-ttu-id="933d8-133">アプリはバージョン2.0 に更新されます。</span><span class="sxs-lookup"><span data-stu-id="933d8-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="933d8-134">このメニューから会社全体のアプリを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="933d8-134">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="933d8-135">Office 365 管理ポータルを使用してテナントアプリカタログを管理する</span><span class="sxs-lookup"><span data-stu-id="933d8-135">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="933d8-136">バグの修正が必要なアプリがある場合は、Microsoft 365 管理\*\* > <>\*\* > \*\*\*\* > センターを使用**して、** アプリを一時的に無効にすることができます。たとえば、"グローバル (組織全体の既定)" という > の**テナント > アプリ**は、特定のアプリをブロックし、他のユーザーをブロックして、アプリをリストに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="933d8-136">If you have apps that need bug fixes, you can temporarily disable apps through the Microsoft 365 admin center > **Teams admin center** > **Teams apps** > **Permission Policies** > <policy name, e.g. "Global (Org-wide default)"> **Tenant apps** > Block specific apps and allow all others and add your app to the list.</span></span>

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image05.png)

<span data-ttu-id="933d8-138">アプリを無効にすると、アプリを完全に削除せずに、ユーザーがアプリを操作できなくなります。</span><span class="sxs-lookup"><span data-stu-id="933d8-138">Disabling an app will block users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="933d8-139">これらのコントロールを使用すると、企業でアプリを管理するときの柔軟性と制御がさらに向上します。</span><span class="sxs-lookup"><span data-stu-id="933d8-139">These controls give you additional flexibility and control when managing apps in your enterprise.</span></span>
