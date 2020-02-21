---
title: Microsoft Teams テナントアプリカタログでアプリを公開する
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Microsoft Teams テナントアプリカタログでアプリを公開するためのガイダンス。
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
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161616"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a><span data-ttu-id="94b8c-103">Microsoft Teams テナントアプリカタログでアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="94b8c-103">Publish apps in the Microsoft Teams tenant app catalog</span></span>
=======================================================

<span data-ttu-id="94b8c-104">Microsoft Teams テナントアプリカタログを使用して、基幹業務アプリケーションのテストと組織への配布を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-104">You can use the Microsoft Teams tenant app catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="94b8c-105">Teams テナントアプリカタログを使用すると、組織専用に構築された基幹業務アプリケーションを配布することができ、重要なビジネス機能の実行に依存することになります。</span><span class="sxs-lookup"><span data-stu-id="94b8c-105">The Teams tenant app catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="94b8c-106">組織のアプリを公開するには、グローバル管理者または teams サービスの管理者の役割を持つアカウントを使用して Teams クライアントにサインインし、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="94b8c-106">To publish apps for your organization, sign in to the Teams client using an account with either the global admin or teams service admin role and then follow the steps below.</span></span>

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a><span data-ttu-id="94b8c-107">Teams クライアントからテナントアプリカタログ内のアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="94b8c-107">Publish an app in the tenant app catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="94b8c-108">次の手順では、Teams クライアントを使用してアプリを公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="94b8c-108">These steps describe how to publish an app by using the Teams client.</span></span> <span data-ttu-id="94b8c-109">Microsoft Teams 管理センターの [アプリの**管理**] ページでアプリを公開することもできます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-109">You can also publish an app on the **Manage apps** page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="94b8c-110">詳細については、「 [Teams でアプリを管理](manage-apps.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94b8c-110">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="94b8c-111">Teams アプリパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="94b8c-111">Get a Teams app package</span></span>

<span data-ttu-id="94b8c-112">Teams アプリパッケージは、 [Teams アプリ Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-112">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="94b8c-113">アプリパッケージを取得したら、テナントアプリカタログに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-113">Once you have the app package, you can add it to the tenant app catalog.</span></span> <span data-ttu-id="94b8c-114">組織内のすべてのユーザーがアプリカタログを表示できますが、グローバル管理者と teams サービス管理者のみが公開および管理できます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-114">While all users in your organization can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-app-catalog"></a><span data-ttu-id="94b8c-115">テナントアプリカタログに移動する</span><span class="sxs-lookup"><span data-stu-id="94b8c-115">Go to the tenant app catalog</span></span>

<span data-ttu-id="94b8c-116">Teams を起動し、グローバルまたは teams サービス管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="94b8c-116">Start Teams and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="94b8c-117">アプリの左側にある [**アプリ**] を選択し、特定の組織に対応する新しいセクション (この例では、Contoso) を選びます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-117">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="94b8c-118">組織内のユーザーは、カタログ内のアプリを表示して、メンバーになっているチームに対してアプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-118">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a><span data-ttu-id="94b8c-120">テナントアプリカタログにアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="94b8c-120">Add an app to the tenant app catalog</span></span>

1. <span data-ttu-id="94b8c-121">[**アプリ**] ページで、[ > **Contoso の\*\*\*\*カスタムアプリアップロードをアップロードする**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-121">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image02.png)

    <span data-ttu-id="94b8c-123">( **[自分のアップロード] または [自分のチーム**] (*サイドローディング*と呼ばれます) を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-123">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="94b8c-124">サイドローディングによって、アプリはチームまたは選択したチームのみが利用できるようになります。)</span><span class="sxs-lookup"><span data-stu-id="94b8c-124">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="94b8c-125">アプリパッケージに移動して選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94b8c-125">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image03.png)

<span data-ttu-id="94b8c-127">テナントアプリカタログに戻ると、新しいエンタープライズアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-127">When you go back to your tenant app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="94b8c-128">このアプリカタログには、自分と組織のメンバーのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-128">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-app-catalog"></a><span data-ttu-id="94b8c-129">テナントアプリカタログのアプリを更新する</span><span class="sxs-lookup"><span data-stu-id="94b8c-129">Update an app in the tenant app catalog</span></span>

1. <span data-ttu-id="94b8c-130">テナントのアプリカタログで、[**..**.] を選びます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-130">From your tenant app catalog, select “**…**”</span></span> <span data-ttu-id="94b8c-131">更新するアプリの右上にあります。</span><span class="sxs-lookup"><span data-stu-id="94b8c-131">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="94b8c-132">更新されたアプリパッケージに移動して選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94b8c-132">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image04.png)

<span data-ttu-id="94b8c-134">アプリはバージョン2.0 に更新されます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-134">The app will be revised to version 2.0.</span></span> <span data-ttu-id="94b8c-135">このメニューから会社全体のアプリを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-135">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a><span data-ttu-id="94b8c-136">Microsoft Teams 管理センターを使用して、テナントアプリカタログを管理する</span><span class="sxs-lookup"><span data-stu-id="94b8c-136">Use the Microsoft Teams admin center to manage the tenant app catalog</span></span>

<span data-ttu-id="94b8c-137">バグ修正が必要なアプリがある場合は、アプリのアクセス許可ポリシーでユーザーのアプリを一時的に無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-137">If you have apps that need bug fixes, you can temporarily disable apps for users in an app permission policy.</span></span>

1. <span data-ttu-id="94b8c-138">Microsoft Teams 管理センターの左のナビゲーションで、[**チームアプリ** > の**アクセス許可ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="94b8c-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="94b8c-139">編集するアプリのアクセス許可ポリシーを選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94b8c-139">Select the app permission policy that you want to edit, and then click **Edit**.</span></span>
3. <span data-ttu-id="94b8c-140">[**テナントアプリ**] で、[**特定のアプリをブロックし、他のアプリを許可**する] を選択し、ブロックするアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="94b8c-140">Under **Tenant apps**, select **Block specific apps and allow all others**, and then add the apps that you want to block.</span></span>

<span data-ttu-id="94b8c-141">アプリを無効にすると、ユーザーはアプリを完全に削除せずに、アプリとやり取りすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="94b8c-141">Disabling an app blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="94b8c-142">これらのコントロールを使うと、組織のアプリを管理するときに、さらに柔軟性と制御ができます。</span><span class="sxs-lookup"><span data-stu-id="94b8c-142">These controls give you additional flexibility and control when managing apps in your organization.</span></span>

<span data-ttu-id="94b8c-143">詳細については、「 [Teams でアプリのアクセス許可ポリシーを管理](teams-app-permission-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94b8c-143">To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>