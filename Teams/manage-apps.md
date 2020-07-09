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
ms.openlocfilehash: 1aa72a1720139324f53168c36f1d27a12b5cf5bb
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086214"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="3e5bc-103">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="3e5bc-103">Manage your apps in the Microsoft Teams admin center</span></span>
======================================================

<span data-ttu-id="3e5bc-104">管理者として、Microsoft Teams 管理センターの [**アプリの管理**] ページでは、組織のアプリカタログ内のすべての Teams アプリを表示して管理できます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-104">As an admin, the **Manage apps** page in the Microsoft Teams admin center is where you view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="3e5bc-105">ここでは、アプリの組織レベルの状態とプロパティの表示、新しいカスタムアプリのテナントアプリカタログへのアップロード、組織レベルでのアプリのブロックまたは許可、組織全体のアプリ設定の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-105">Here, you can see the org-level status and properties of apps, upload new custom apps to your tenant app catalog, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="3e5bc-106">**[アプリの管理]** ページでは、テナント カタログ内の使用可能なすべてのアプリを確認することができます。また、組織全体で許可またはブロックするアプリを決定するために必要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-106">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="3e5bc-107">また、[アプリのアクセス許可ポリシー](teams-app-permission-policies.md)、[アプリのセットアップ ポリシー](teams-app-setup-policies.md)、[カスタム アプリ ポリシーと設定](teams-custom-app-policies-and-settings.md)を使って、組織内の特定のユーザーに対してアプリ エクスペリエンスの構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-107">You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="3e5bc-108">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-108">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="3e5bc-109">ページにアクセスするには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-109">You must be a global admin or Teams service admin to access the page.</span></span>

> [!NOTE]
> <span data-ttu-id="3e5bc-110">Microsoft 365 Government Community Cloud (Office の GCC) 展開では、[**アプリの管理**] ページはまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-110">The **Manage apps** page isn't available yet in Microsoft 365 Government Community Cloud (GCC) deployments of Teams.</span></span>

## <a name="view-apps-in-your-tenant-app-catalog"></a><span data-ttu-id="3e5bc-111">テナントアプリカタログのアプリを表示する</span><span class="sxs-lookup"><span data-stu-id="3e5bc-111">View apps in your tenant app catalog</span></span>

<span data-ttu-id="3e5bc-112">各アプリに関する次の情報を含む、テナントアプリカタログ内のすべてのアプリを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-112">You can view every app in your tenant app catalog including the following information about each app.</span></span>

![[管理されたアプリ] ページのスクリーンショット](media/manage-apps.png)

- <span data-ttu-id="3e5bc-114">**Name**: アプリ名。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-114">**Name**: The app name.</span></span> <span data-ttu-id="3e5bc-115">アプリ名をクリックすると、アプリの詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-115">Click the app name to see more information about the app.</span></span> <span data-ttu-id="3e5bc-116">これには、アプリの説明、許可されているかブロックされているか、アプリに適用されるカテゴリ、証明の状態、サポートされている機能、アプリ ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-116">This includes a description of the app, whether it's allowed or blocked, version, categories that apply to the app, certification status, supported capabilities, and app ID.</span></span> <span data-ttu-id="3e5bc-117">以下は、実行例です。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-117">Here's an example:</span></span><br><span data-ttu-id="3e5bc-118"> 
![アプリの [アプリの詳細] ページのスクリーンショット](media/manage-apps-app-details.png)</span><span class="sxs-lookup"><span data-stu-id="3e5bc-118"> 
![Screenshot of the apps details page for an app](media/manage-apps-app-details.png)</span></span>
- <span data-ttu-id="3e5bc-119">**認定**: アプリが認定を受けると、 **Microsoft 365 公認**または**発行元の構成証明**のいずれかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-119">**Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**.</span></span> <span data-ttu-id="3e5bc-120">リンクをクリックすると、アプリの認定の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-120">Click the link to view certification details for the app.</span></span> <span data-ttu-id="3e5bc-121">"" が表示される場合は **--** 、アプリの認定情報がありません。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-121">If you see "**--**", we don't have certification information for the app.</span></span> <span data-ttu-id="3e5bc-122">Teams での認定アプリの詳細については、「 [Microsoft 365 App 認定プログラム](https://docs.microsoft.com/teams-app-certification/all-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-122">To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](https://docs.microsoft.com/teams-app-certification/all-apps).</span></span>  
- <span data-ttu-id="3e5bc-123">**カテゴリ**: アプリに適用されるカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-123">**Categories**: Categories that apply to the app.</span></span>
- <span data-ttu-id="3e5bc-124">**アプリの状態**: 組織レベルでのアプリの状態。次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-124">**App status**: Status of the app at the org level, which can be one of the following:</span></span>
    - <span data-ttu-id="3e5bc-125">**許可**: アプリは、組織内のすべてのユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-125">**Allowed**: The app is available for all users in your organization.</span></span>
    - <span data-ttu-id="3e5bc-126">**ブロック**: アプリはブロックされ、組織内のどのユーザーに対しても使用できません。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-126">**Blocked**: The app is blocked and not available for any users in your organization.</span></span>
    - <span data-ttu-id="3e5bc-127">ブロックされた**組織全体**: アプリは組織全体のアプリ設定でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-127">**Blocked org-wide**: The app is blocked in org-wide app settings.</span></span> <br>
<span data-ttu-id="3e5bc-128">この列は、以前は**組織全体の設定**ウィンドウにあるアプリの許可された状態とブロック状態を表していることを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-128">It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane.</span></span> <span data-ttu-id="3e5bc-129">これで、[**アプリの管理**] ページで、組織全体でアプリの表示、ブロック、許可を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-129">You now view, block, and allow apps at the org-wide on the **Manage apps** page.</span></span> 
- <span data-ttu-id="3e5bc-130">**バージョン**: アプリのバージョン。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-130">**Version**: App version.</span></span>

<span data-ttu-id="3e5bc-131">表に必要な情報を表示するには、右上隅の [**列の編集**] をクリックして、表に列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-131">To see the information that you want in the table, click **Edit Column** in the upper-right corner to add or remove columns to the table.</span></span>

## <a name="upload-a-new-app"></a><span data-ttu-id="3e5bc-132">新しいアプリをアップロードする</span><span class="sxs-lookup"><span data-stu-id="3e5bc-132">Upload a new app</span></span>

<span data-ttu-id="3e5bc-133">アプリカタログを使って、組織専用に構築されたカスタムアプリケーションのテストと配布を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-133">You can use your app catalog to test and distribute custom applications that are built specifically for your organization.</span></span> <span data-ttu-id="3e5bc-134">Teams アプリパッケージは、 [Teams アプリ Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-134">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="3e5bc-135">アプリパッケージがある場合は、アプリカタログに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-135">When you have the app package, you can add it to the your app catalog.</span></span> <span data-ttu-id="3e5bc-136">組織内のすべてのユーザーがアプリカタログを表示できますが、グローバル管理者と Teams サービス管理者のみが公開および管理できます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-136">While all users in your organization can view the app catalog, only global admins and Teams service admins can publish and manage it.</span></span>

<span data-ttu-id="3e5bc-137">新しいカスタムアプリをテナントアプリカタログにアップロードするには、[**新しいアプリのアップロード**] をクリックして、アプリパッケージを .zip 形式でアップロードします。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-137">To upload a new custom app to your tenant app catalog, click **Upload new app** to upload your app package in .zip format.</span></span> <span data-ttu-id="3e5bc-138">アプリはアップロードされた後は強調表示されません。アプリカタログを検索して見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-138">The app isn't highlighted after it's uploaded so you'll need to search your app catalog to find it.</span></span>

<span data-ttu-id="3e5bc-139">アップロードした後にアプリを更新するには、[**アプリの管理**] ページのアプリの一覧でアプリ名をクリックし、[**更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-139">To update an app after it's uploaded, in the list of apps on the **Manage apps** page, click the app name, and then click **Update**.</span></span> <span data-ttu-id="3e5bc-140">この操作を行うと、アプリカタログの既存のアプリは置き換えられ、すべてのアプリのアクセス許可ポリシーとアプリのセットアップポリシーは、更新されたアプリに適用されたままになります。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-140">Doing this replaces the existing app in your app catalog and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="3e5bc-141">詳細については、「 [Teams でカスタムアプリを管理](manage-your-custom-apps.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-141">To learn more, see [Manage your custom apps in Teams](manage-your-custom-apps.md).</span></span>

## <a name="allow-and-block-apps"></a><span data-ttu-id="3e5bc-142">アプリを許可または禁止する</span><span class="sxs-lookup"><span data-stu-id="3e5bc-142">Allow and block apps</span></span>

<span data-ttu-id="3e5bc-143">[**アプリの管理**] ページでは、組織レベルで個別のアプリを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-143">The **Manage apps** page is where you allow or block individual apps at the org level.</span></span> <span data-ttu-id="3e5bc-144">利用可能なすべてのアプリとその現在の組織レベルアプリの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-144">It shows every available app and its current org-level app status.</span></span> <span data-ttu-id="3e5bc-145">(組織レベルでのアプリのブロックと許可は、**組織全体のアプリ設定**ウィンドウからここに移動されています)。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-145">(Blocking and allowing apps at the org level has moved from the **Org-wide app settings** pane to here.)</span></span>

<span data-ttu-id="3e5bc-146">アプリを許可またはブロックするには、アプリを選択し、[**許可**] または [**禁止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-146">To allow or block an app, select it, and then click **Allow** or **Block**.</span></span> <span data-ttu-id="3e5bc-147">アプリをブロックすると、そのアプリとのすべての操作が無効になり、組織内のユーザーのチームにアプリが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-147">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for any users in your organization.</span></span>

<span data-ttu-id="3e5bc-148">[**アプリの管理**] ページでアプリをブロックまたは許可すると、そのアプリは組織内のすべてのユーザーに対してブロックまたは許可されます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-148">When you block or allow an app on the **Manage apps** page, that app is blocked or allowed for all users in your organization.</span></span>  <span data-ttu-id="3e5bc-149">Teams アプリのアクセス許可ポリシーでアプリをブロックまたは許可すると、そのポリシーが割り当てられているユーザーに対してはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-149">When you block or allow an app in a Teams app permission policy, it's blocked or allowed for users who are assigned that policy.</span></span> <span data-ttu-id="3e5bc-150">ユーザーがアプリをインストールして操作できるようにするには、[**アプリの管理**] ページとユーザーに割り当てられているアプリのアクセス許可ポリシーで、組織レベルでアプリを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-150">For a user to be able to install and interact with any app, you must allow the app at the org level on the **Manage apps** page and in the app permission policy that's assigned to the user.</span></span>

 > [!NOTE]
 > <span data-ttu-id="3e5bc-151">アプリをアンインストールするには、アプリを右クリックし、[**アンインストール**] をクリックするか、左 side の [**その他のアプリ**] メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-151">To uninstall an app, right-click on the app and then click **Uninstall** or use the **More apps** menu on the lefthand side.</span></span> 

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="3e5bc-152">組織全体のアプリ設定を管理する</span><span class="sxs-lookup"><span data-stu-id="3e5bc-152">Manage org-wide app settings</span></span>

<span data-ttu-id="3e5bc-153">組織全体のアプリ設定を使用して、ユーザーがサードパーティ製のアプリをインストールできるかどうかを制御し、ユーザーが組織のカスタムアプリをアップロードまたは操作できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-153">Use org-wide app settings to control whether users can install third-party apps and whether users can upload or interact with custom  apps in your organization.</span></span> <span data-ttu-id="3e5bc-154">組織全体のアプリの設定では、すべてのユーザーに対する動作が管理され、ユーザーに割り当てられている他のアプリのアクセス許可ポリシーは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-154">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="3e5bc-155">これらを使って、悪意のあるアプリや問題のあるアプリを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-155">You can use them to control malicious or problematic apps.</span></span>

> [!NOTE]
> <span data-ttu-id="3e5bc-156">Teams の Microsoft 365 Government-GCC 展開で組織全体のアプリ設定を使用する方法については、「 [teams でアプリのアクセス許可ポリシーを管理](teams-app-permission-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-156">To learn how to use org-wide app settings in Microsoft 365 Government - GCC deployments of Teams, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="3e5bc-157">[**アプリの管理**] ページで、[**組織全体のアプリの設定**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-157">On the **Manage apps** page, select **Org-wide app settings**.</span></span> <span data-ttu-id="3e5bc-158">次に、パネルで設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-158">You can then configure the settings you want in the panel.</span></span>

    ![組織全体のアプリ設定のスクリーンショット](media/manage-apps-org-wide-app-settings.png)
    
2. <span data-ttu-id="3e5bc-160">サード**パーティ**製のアプリで、次の設定を有効または無効にして、サードパーティ製のアプリへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-160">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="3e5bc-161">**サードパーティ製のアプリを許可する**: ユーザーがサードパーティ製のアプリを使えるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-161">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="3e5bc-162">この設定をオフにした場合、ユーザーはサードパーティ製のアプリをインストールまたは使用することができません。また、これらのアプリのアプリの状態は、表のブロックされた**組織全体**として表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-162">If you turn off this setting, your users won't be able to install or use any third-party apps and the app status of these apps is displayed as **Blocked org-wide** in the table.</span></span>

        <span data-ttu-id="3e5bc-163">許可されている**サードパーティ製のアプリ**が無効になっている場合は、[発信 web フック](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)は無効になります。つまり、ユーザーはこれらのアプリを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-163">When **Allow third-party apps** is off, [outgoing webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) are disabled, which means that users can't create them.</span></span> <span data-ttu-id="3e5bc-164">この設定をオンにすると、ユーザーのアプリのアクセス許可ポリシーで設定をオンまたはオフにした場合でも、すべてのユーザーに対して送信 web フックが有効になります。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-164">When this setting is on, outgoing webhooks are enabled for all users regardless of whether the setting is on or off in the users' app permission policy.</span></span>
    - <span data-ttu-id="3e5bc-165">**既定でストアに公開**されている新しいサードパーティのアプリを許可します。これは、teams app store に公開された新しいサードパーティアプリが teams で自動的に使用できるようになるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-165">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="3e5bc-166">このオプションを設定するには、サードパーティ製のアプリを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-166">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="3e5bc-167">[**カスタムアプリ**] の下で、[**カスタムアプリとの対話を許可する**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-167">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="3e5bc-168">この設定は、ユーザーがカスタムアプリを操作できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-168">This setting controls whether users can interact with custom apps.</span></span> <span data-ttu-id="3e5bc-169">詳細については、「 [Teams でカスタムアプリポリシーと設定を管理](teams-custom-app-policies-and-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-169">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
4. <span data-ttu-id="3e5bc-170">組織全体のアプリ設定を有効にするには、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e5bc-170">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3e5bc-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e5bc-171">Related topics</span></span>

- [<span data-ttu-id="3e5bc-172">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="3e5bc-172">Admin settings for apps in Teams</span></span>](admin-settings.md)
