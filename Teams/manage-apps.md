---
title: Microsoft Teams 管理センターでアプリを管理する
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Microsoft Teams 管理センターの [アプリの管理] ページで Teams アプリを管理する方法について説明します。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: ab00f4ee445a5711a272ed5b4e2eea104012a7bd
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161915"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="32f01-103">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="32f01-103">Manage your apps in the Microsoft Teams admin center</span></span>
======================================================

<span data-ttu-id="32f01-104">管理者として、Microsoft Teams 管理センターの [**アプリの管理**] ページでは、組織のアプリカタログ内のすべての Teams アプリを表示して管理できます。</span><span class="sxs-lookup"><span data-stu-id="32f01-104">As an admin, the **Manage apps** page in the Microsoft Teams admin center is where you view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="32f01-105">ここでは、アプリの組織レベルの状態とプロパティの表示、新しいカスタムアプリのテナントアプリカタログへのアップロード、組織レベルでのアプリのブロックまたは許可、組織全体のアプリ設定の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="32f01-105">Here, you can see the org-level status and properties of apps, upload new custom apps to your tenant app catalog, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="32f01-106">[**アプリの管理**] ページでは、テナントカタログで利用可能なすべてのアプリを表示することができます。また、組織全体で許可またはブロックするアプリを決定するために必要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="32f01-106">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="32f01-107">次に、[アプリのアクセス許可ポリシー](teams-app-permission-policies.md)、[アプリセットアップポリシー](teams-app-setup-policies.md)、[カスタムアプリポリシーと設定](teams-custom-app-policies-and-settings.md)を使用して、組織内の特定のユーザーのアプリエクスペリエンスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="32f01-107">You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="32f01-108">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** > の**管理**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="32f01-108">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="32f01-109">ページにアクセスするには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="32f01-109">You must be a global admin or Teams service admin to access the page.</span></span>

## <a name="view-apps-in-your-tenant-app-catalog"></a><span data-ttu-id="32f01-110">テナントアプリカタログのアプリを表示する</span><span class="sxs-lookup"><span data-stu-id="32f01-110">View apps in your tenant app catalog</span></span>

<span data-ttu-id="32f01-111">各アプリに関する次の情報を含む、テナントアプリカタログ内のすべてのアプリを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="32f01-111">You can view every app in your tenant app catalog including the following information about each app.</span></span>

![[管理されたアプリ] ページのスクリーンショット](media/manage-apps.png)

- <span data-ttu-id="32f01-113">**Name**: アプリ名。</span><span class="sxs-lookup"><span data-stu-id="32f01-113">**Name**: The app name.</span></span> <span data-ttu-id="32f01-114">アプリ名をクリックすると、アプリの詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32f01-114">Click the app name to see more information about the app.</span></span> <span data-ttu-id="32f01-115">これには、アプリの説明、許可されているかブロックされているか、アプリに適用されるカテゴリ、証明の状態、サポートされている機能、アプリ ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="32f01-115">This includes a description of the app, whether it's allowed or blocked, version, categories that apply to the app, certification status, supported capabilities, and app ID.</span></span> <span data-ttu-id="32f01-116">以下は、実行例です。</span><span class="sxs-lookup"><span data-stu-id="32f01-116">Here's an example:</span></span><br><span data-ttu-id="32f01-117"> 
![アプリの [アプリの詳細] ページのスクリーンショット](media/manage-apps-app-details.png)</span><span class="sxs-lookup"><span data-stu-id="32f01-117"> 
![Screenshot of the apps details page for an app](media/manage-apps-app-details.png)</span></span>
- <span data-ttu-id="32f01-118">**認定**: アプリが認定を受けると、 **Microsoft 365 公認**または**発行元の構成証明**のいずれかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32f01-118">**Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**.</span></span> <span data-ttu-id="32f01-119">リンクをクリックすると、アプリの認定の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32f01-119">Click the link to view certification details for the app.</span></span> <span data-ttu-id="32f01-120">"**--**" が表示される場合は、アプリの認定情報がありません。</span><span class="sxs-lookup"><span data-stu-id="32f01-120">If you see "**--**", we don't have certification information for the app.</span></span> <span data-ttu-id="32f01-121">Teams での認定アプリの詳細については、「 [Microsoft 365 App 認定プログラム](https://docs.microsoft.com/teams-app-certification/all-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32f01-121">To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](https://docs.microsoft.com/teams-app-certification/all-apps).</span></span>  
- <span data-ttu-id="32f01-122">**カテゴリ**: アプリに適用されるカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="32f01-122">**Categories**: Categories that apply to the app.</span></span>
- <span data-ttu-id="32f01-123">**アプリの状態**: 組織レベルでのアプリの状態。次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="32f01-123">**App status**: Status of the app at the org level, which can be one of the following:</span></span>
    - <span data-ttu-id="32f01-124">**許可**: アプリは、組織内のすべてのユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="32f01-124">**Allowed**: The app is available for all users in your organization.</span></span>
    - <span data-ttu-id="32f01-125">**ブロック**: アプリはブロックされ、組織内のどのユーザーに対しても使用できません。</span><span class="sxs-lookup"><span data-stu-id="32f01-125">**Blocked**: The app is blocked and not available for any users in your organization.</span></span><br>
<span data-ttu-id="32f01-126">この列は、以前は**組織全体の設定**ウィンドウにあるアプリの許可された状態とブロック状態を表していることを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="32f01-126">It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane.</span></span> <span data-ttu-id="32f01-127">これで、[**アプリの管理**] ページで、組織全体でアプリの表示、ブロック、許可を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="32f01-127">You now view, block, and allow apps at the org-wide on the **Manage apps** page.</span></span> 
- <span data-ttu-id="32f01-128">**バージョン**: アプリのバージョン。</span><span class="sxs-lookup"><span data-stu-id="32f01-128">**Version**: App version.</span></span>

<span data-ttu-id="32f01-129">表に必要な情報を表示するには、右上隅の [**列の編集**] をクリックして、表に列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="32f01-129">To see the information that you want in the table, click **Edit Column** in the upper-right corner to add or remove columns to the table.</span></span>

## <a name="upload-a-new-app"></a><span data-ttu-id="32f01-130">新しいアプリをアップロードする</span><span class="sxs-lookup"><span data-stu-id="32f01-130">Upload a new app</span></span>

<span data-ttu-id="32f01-131">新しいカスタムアプリをテナントアプリカタログにアップロードするには、[**新しいアプリのアップロード**] をクリックして、アプリパッケージを .zip 形式でアップロードします。</span><span class="sxs-lookup"><span data-stu-id="32f01-131">To upload a new custom app to your tenant app catalog, click **Upload new app** to upload your app package in .zip format.</span></span> <span data-ttu-id="32f01-132">アプリはアップロードされた後は強調表示されません。テナントカタログを検索して見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="32f01-132">The app isn't highlighted after it's uploaded so you'll need to search your tenant catalog to find it.</span></span>

<span data-ttu-id="32f01-133">[Teams のデスクトップクライアントを使用](tenant-apps-catalog-teams.md#go-to-the-tenant-app-catalog)して、アプリをアップロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="32f01-133">You can also upload apps by [using the Teams desktop client](tenant-apps-catalog-teams.md#go-to-the-tenant-app-catalog).</span></span> <span data-ttu-id="32f01-134">詳細については、「 [Teams で基幹業務アプリを管理](manage-your-lob-apps.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32f01-134">To learn more, see [Manage your line-of-business apps in Teams](manage-your-lob-apps.md).</span></span>

## <a name="allow-and-block-apps"></a><span data-ttu-id="32f01-135">アプリを許可または禁止する</span><span class="sxs-lookup"><span data-stu-id="32f01-135">Allow and block apps</span></span>

<span data-ttu-id="32f01-136">[**アプリの管理**] ページでは、組織レベルで個別のアプリを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="32f01-136">The **Manage apps** page is where you allow or block individual apps at the org level.</span></span> <span data-ttu-id="32f01-137">利用可能なすべてのアプリとその現在の組織レベルアプリの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32f01-137">It shows every available app and its current org-level app status.</span></span> <span data-ttu-id="32f01-138">(組織レベルでのアプリのブロックと許可は、**組織全体のアプリ設定**ウィンドウからここに移動されています)。</span><span class="sxs-lookup"><span data-stu-id="32f01-138">(Blocking and allowing apps at the org level has moved from the **Org-wide app settings** pane to here.)</span></span>

<span data-ttu-id="32f01-139">アプリを許可またはブロックするには、アプリを選択し、[**許可**] または [**禁止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32f01-139">To allow or block an app, select it, and then click **Allow** or **Block**.</span></span> <span data-ttu-id="32f01-140">アプリをブロックすると、そのアプリとのすべての操作が無効になり、組織内のユーザーのチームにアプリが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="32f01-140">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for any users in your organization.</span></span>

<span data-ttu-id="32f01-141">[**アプリの管理**] ページでアプリをブロックまたは許可すると、そのアプリは組織内のすべてのユーザーに対してブロックまたは許可されます。</span><span class="sxs-lookup"><span data-stu-id="32f01-141">When you block or allow an app on the **Manage apps** page, that app is blocked or allowed for all users in your organization.</span></span>  <span data-ttu-id="32f01-142">Teams アプリのアクセス許可ポリシーでアプリをブロックまたは許可すると、そのポリシーが割り当てられているユーザーに対してはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="32f01-142">When you block or allow an app in a Teams app permission policy, it's blocked or allowed for users who are assigned that policy.</span></span> <span data-ttu-id="32f01-143">ユーザーがアプリをインストールして操作できるようにするには、[**アプリの管理**] ページとユーザーに割り当てられているアプリのアクセス許可ポリシーで、組織レベルでアプリを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32f01-143">For a user to be able to install and interact with any app, you must allow the app at the org level on the **Manage apps** page and in the app permission policy that's assigned to the user.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="32f01-144">組織全体のアプリ設定を管理する</span><span class="sxs-lookup"><span data-stu-id="32f01-144">Manage org-wide app settings</span></span>

<span data-ttu-id="32f01-145">組織全体のアプリ設定を使用して、ユーザーがサードパーティ製のアプリをインストールできるかどうかを制御し、ユーザーが組織のカスタムアプリをアップロードまたは操作できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="32f01-145">Use org-wide app settings to control whether users can install third-party apps and whether users can upload or interact with custom  apps in your organization.</span></span> <span data-ttu-id="32f01-146">組織全体のアプリの設定では、すべてのユーザーに対する動作が管理され、ユーザーに割り当てられている他のアプリのアクセス許可ポリシーは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="32f01-146">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="32f01-147">これらを使って、悪意のあるアプリや問題のあるアプリを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="32f01-147">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="32f01-148">[**アプリの管理**] ページで、[**組織全体のアプリの設定**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="32f01-148">On the **Manage apps** page, select **Org-wide app settings**.</span></span> <span data-ttu-id="32f01-149">次に、パネルで設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="32f01-149">You can then configure the settings you want in the panel.</span></span>

    ![組織全体のアプリ設定のスクリーンショット](media/manage-apps-org-wide-app-settings.png)
    
2. <span data-ttu-id="32f01-151">サード**パーティ**製のアプリで、次の設定を有効または無効にして、サードパーティ製のアプリへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="32f01-151">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="32f01-152">**Teams でサードパーティ製アプリを許可する**: ユーザーがサードパーティ製のアプリを使えるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="32f01-152">**Allow third-party apps in Teams**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="32f01-153">この設定をオフにすると、ユーザーはサードパーティ製のアプリをインストールまたは使用することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="32f01-153">If you turn off this setting, your users won't be able to install or use any third-party apps.</span></span> <span data-ttu-id="32f01-154">許可したアプリについては、状態は**許可されているが、組織全体**では無効です。</span><span class="sxs-lookup"><span data-stu-id="32f01-154">For apps that you allowed, the status shows as **Allowed but disabled org-wide**.</span></span>
    
    - <span data-ttu-id="32f01-155">**既定でストアに公開**されている新しいサードパーティのアプリを許可します。これは、teams app store に公開された新しいサードパーティアプリが teams で自動的に使用できるようになるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="32f01-155">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="32f01-156">このオプションを設定するには、サードパーティ製のアプリを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32f01-156">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="32f01-157">[**カスタムアプリ**] の下で、[**カスタムアプリとの対話を許可する**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="32f01-157">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="32f01-158">この設定は、ユーザーがカスタムアプリを操作できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="32f01-158">This setting controls whether users can interact with custom apps.</span></span> <span data-ttu-id="32f01-159">詳細については、「 [Teams でカスタムアプリポリシーと設定を管理](teams-custom-app-policies-and-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32f01-159">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
4. <span data-ttu-id="32f01-160">組織全体のアプリ設定を有効にするには、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32f01-160">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="related-topics"></a><span data-ttu-id="32f01-161">関連トピック</span><span class="sxs-lookup"><span data-stu-id="32f01-161">Related topics</span></span>

- [<span data-ttu-id="32f01-162">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="32f01-162">Admin settings for apps in Teams</span></span>](admin-settings.md)
