---
title: Microsoft Teams でのリソース固有の同意
author: cichur
ms.author: v-cichur
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織内のチームの所有者がアプリに同意できるかどうかを制御するために構成する必要がある設定について学習します。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6267f4b42890716ca31fd1b44de435af50ad6ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815677"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="8a36e-103">Microsoft Teams でのリソース固有の同意</span><span class="sxs-lookup"><span data-stu-id="8a36e-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="8a36e-104">Microsoft Teams のリソース固有の同意により、チーム所有者はアプリに対してチーム データへのアクセスに同意できます。</span><span class="sxs-lookup"><span data-stu-id="8a36e-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="8a36e-105">そのようなアクセスの例としては、チャネル メッセージの読み取り、チャネルの作成と削除、チャネル タブの作成と削除を行う機能があります。</span><span class="sxs-lookup"><span data-stu-id="8a36e-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="8a36e-106">管理者は、Azure Active Directory (Azure AD) PowerShell モジュールまたは Azure ポータルと Microsoft Teams 管理センターを使用して構成した設定を使用して、組織内のチーム所有者が同意できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8a36e-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="8a36e-107">チーム所有者がアプリに同意できるかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="8a36e-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="8a36e-108">チーム所有者がアプリに同意できるかどうかを制御するために設定する必要がある設定を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8a36e-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="8a36e-109">次のすべての設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8a36e-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="8a36e-110">Azure AD の設定</span><span class="sxs-lookup"><span data-stu-id="8a36e-110">Settings in Azure AD</span></span>

<span data-ttu-id="8a36e-111">次の 2 つの設定は、チーム所有者がアプリに同意できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8a36e-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a36e-112">これらの設定を変更しても、既に同意が付与されているアプリのデータ アクセスには影響しません。</span><span class="sxs-lookup"><span data-stu-id="8a36e-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="8a36e-113">たとえば、チーム所有者が同意を許可しない設定を構成した場合、これらの変更によって既に付与されているデータ アクセスは削除されません。</span><span class="sxs-lookup"><span data-stu-id="8a36e-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="8a36e-114">[ユーザーは自分の代わりに会社のデータにアクセスするアプリに同意できます] 設定</span><span class="sxs-lookup"><span data-stu-id="8a36e-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="8a36e-115">この設定は、組織内のユーザーが代わりにアプリに同意できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8a36e-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="8a36e-116">チーム所有者が同意を提供するには、この設定を [はい] に設定する必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="8a36e-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="8a36e-117">この設定を管理するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8a36e-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="8a36e-118">Azure Portal で、Enterprise アプリケーション **のユーザー設定に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="8a36e-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="8a36e-119">[**エンタープライズ アプリケーション] で、[** いいえ] または **[は** い] に代わって会社のデータにアクセスするアプリにユーザーが同意 **できます。**</span><span class="sxs-lookup"><span data-stu-id="8a36e-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="8a36e-120">PowerShell を使用してこの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="8a36e-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="8a36e-121">詳細については、「アプリケーションにユーザー [コンテンツを構成する」を参照してください](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)。</span><span class="sxs-lookup"><span data-stu-id="8a36e-121">To learn more, see [Configure user content to applications](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="8a36e-122">"EnableGroupGroupGroupConsent" 設定</span><span class="sxs-lookup"><span data-stu-id="8a36e-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="8a36e-123">この設定では、組織内のユーザーが、所有するグループの会社データにアクセスするアプリに同意できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8a36e-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="8a36e-124">チーム所有者が同意するには、この設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a36e-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="8a36e-125">PowerShell を使用してこの設定を管理する手順については、「グループ データにアクセスするアプリに対するグループ所有者の同意を構成する [」を参照してください](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)。</span><span class="sxs-lookup"><span data-stu-id="8a36e-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="8a36e-126">Microsoft Teams 管理センターの設定</span><span class="sxs-lookup"><span data-stu-id="8a36e-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="8a36e-127">Azure AD の設定に加えて、[アプリ[](manage-apps.md#manage-org-wide-app-settings)の管理] ページの組織[](manage-apps.md)全体のアプリ設定、[アプリの管理] ページでアプリがブロックまたは許可されるかどうか、チーム所有者[](teams-app-permission-policies.md)に割り当てられたアプリのアクセス許可ポリシーによって、チーム所有者が同意できるかどうかが決定されます。 [](manage-apps.md#allow-and-block-apps)</span><span class="sxs-lookup"><span data-stu-id="8a36e-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a36e-128">これらの設定を変更しても、既に同意が付与されているアプリのデータ アクセスには影響しません。</span><span class="sxs-lookup"><span data-stu-id="8a36e-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="8a36e-129">たとえば、サードパーティ製アプリを組織全体で無効にした場合や、特定のアプリをブロックしてチーム所有者が同意を得るのを防ぐ場合、これらの変更により、既に付与されているデータ アクセスは削除されません。</span><span class="sxs-lookup"><span data-stu-id="8a36e-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="8a36e-130">組織全体のアプリ設定の [サード パーティ製アプリを許可する] 設定</span><span class="sxs-lookup"><span data-stu-id="8a36e-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="8a36e-131">この組織全体のアプリ設定では、組織内のユーザーがサードパーティ製アプリを使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8a36e-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="8a36e-132">チーム所有者が同意を提供するには、この設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a36e-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="8a36e-133">この設定を管理するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8a36e-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="8a36e-134">Microsoft Teams 管理センターの左側のナビゲーションで **、Teams** アプリの [アプリの管理] に移動し、[組織全体のアプリ設定] を  >  **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8a36e-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="8a36e-135">[ **サード パーティ製アプリ] で**、サード パーティ製アプリを許可 **する機能をオフまたはオンにします**。</span><span class="sxs-lookup"><span data-stu-id="8a36e-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    ![[Teams でサード パーティ製のアプリを許可する] 設定のスクリーンショット](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="8a36e-137">変更が有効になるまで最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8a36e-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="8a36e-138">組織レベルでアプリを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="8a36e-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="8a36e-139">[アプリの管理] ページでアプリ[](manage-apps.md#allow-and-block-apps)をブロックまたは許可すると、そのアプリは組織内のすべてのユーザーに対してブロックまたは許可されます。</span><span class="sxs-lookup"><span data-stu-id="8a36e-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="8a36e-140">チームの所有者は、アプリが許可されている場合にのみ、アプリに同意できます。</span><span class="sxs-lookup"><span data-stu-id="8a36e-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="8a36e-141">組織レベルでアプリを許可またはブロックするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8a36e-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="8a36e-142">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="8a36e-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="8a36e-143">[アプリの管理] ページでアプリを選び、[ブロック] をクリックしてブロックするか、[許可] をクリックしてアプリを許可します。</span><span class="sxs-lookup"><span data-stu-id="8a36e-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![組織全体の設定でブロックされたアプリのスクリーンショット](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="8a36e-145">チーム所有者に割り当てられたアプリのアクセス許可ポリシー</span><span class="sxs-lookup"><span data-stu-id="8a36e-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="8a36e-146">チーム所有者は、アプリのアクセス許可ポリシーで実行が許可されているアプリにのみ同意できます。</span><span class="sxs-lookup"><span data-stu-id="8a36e-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="8a36e-147">チーム所有者に割り当てられているアプリのアクセス許可ポリシーを表示および管理するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8a36e-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="8a36e-148">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="8a36e-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="8a36e-149">チーム所有者の表示名をダブルクリックし、[ポリシー] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8a36e-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="8a36e-150">チーム所有者に割り当てられたポリシーは、[アプリのアクセス許可ポリシー] **の下に表示されます**。</span><span class="sxs-lookup"><span data-stu-id="8a36e-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="8a36e-151">別のポリシーを割り当てるには、[編集] **をクリック** し、割り当てるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8a36e-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="8a36e-152">チーム所有者に割り当てられているポリシーの設定を編集するには、ポリシー名をクリックし、必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="8a36e-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="8a36e-153">カスタム アプリのアップロード</span><span class="sxs-lookup"><span data-stu-id="8a36e-153">Uploading custom apps</span></span>

<span data-ttu-id="8a36e-154">リソース固有の同意を使用するカスタム アプリ (サイドロードとも呼ばれる) をアップロードする場合、アプリはインストール先のテナントから取得される必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a36e-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="8a36e-155">言い換えると、Azure ADアプリの登録は、このテナントから行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a36e-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="8a36e-156">グローバル管理者は、この制限から除外され、任意のテナントからカスタム アプリをチーム (サイドロード) またはテナント アプリ カタログに直接アップロードできます。</span><span class="sxs-lookup"><span data-stu-id="8a36e-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8a36e-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a36e-157">Related topics</span></span>

- [<span data-ttu-id="8a36e-158">利用可能な RSC アクセス許可</span><span class="sxs-lookup"><span data-stu-id="8a36e-158">Available RSC permissions</span></span>](https://aka.ms/teams-rsc)
- [<span data-ttu-id="8a36e-159">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="8a36e-159">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="8a36e-160">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="8a36e-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="8a36e-161">Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="8a36e-161">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
