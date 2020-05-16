---
title: Microsoft Teams でのリソース固有の同意
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織のチーム所有者がアプリに同意するかどうかを制御するために構成する必要がある設定について説明します。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54a0565f5126c899ed5fbf9527aa30f83c3bee3b
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256601"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="7c7b4-103">Microsoft Teams でのリソース固有の同意</span><span class="sxs-lookup"><span data-stu-id="7c7b4-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="7c7b4-104">Microsoft Teams でリソース固有の同意を得ることで、チームの所有者は、チームデータへのアクセスをアプリに承認することができます。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="7c7b4-105">このようなアクセスの例としては、チャネルメッセージの読み取り、チャネルの作成と削除、チャネルタブの作成と削除などがあります。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="7c7b4-106">管理者として、Azure Active Directory (Azure AD) PowerShell モジュールまたは Azure portal と Microsoft Teams 管理センターを使用して構成した設定によって、組織のチーム所有者が同意を得ることができるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="7c7b4-107">チーム所有者がアプリに同意することを許可するかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="7c7b4-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="7c7b4-108">チーム所有者がアプリに同意するかどうかを制御するために設定する必要がある設定を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="7c7b4-109">次の設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="7c7b4-110">Azure AD の設定</span><span class="sxs-lookup"><span data-stu-id="7c7b4-110">Settings in Azure AD</span></span>

<span data-ttu-id="7c7b4-111">次の2つの設定では、チーム所有者がアプリに同意できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c7b4-112">これらの設定を変更しても、既に同意が付与されているアプリのデータアクセスには影響しません。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="7c7b4-113">たとえば、これらの設定を構成して、チームの所有者が同意しないようにした場合、これらの変更では、既に許可されているデータアクセスが削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="7c7b4-114">"ユーザーの代わりに会社データにアクセスするアプリに同意することができます" 設定</span><span class="sxs-lookup"><span data-stu-id="7c7b4-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="7c7b4-115">この設定は、組織内のユーザーがアプリに代わって承認できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="7c7b4-116">チーム所有者が同意を得ることができるようにするには、 **[はい]** に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="7c7b4-117">この設定を管理するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="7c7b4-118">Azure ポータルで、[**エンタープライズアプリケーション**の  >  **ユーザー設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="7c7b4-119">[**エンタープライズアプリケーション**] では、ユーザーが [**いいえ**] または **[はい]** に**代わって会社のデータにアクセスするアプリに同意できる**ように設定します。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="7c7b4-120">PowerShell を使用してこの設定を管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="7c7b4-121">詳細については、「[ユーザーコンテンツをアプリケーションに構成](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-121">To learn more, see [Configure user content to applications](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="7c7b4-122">"Enablegroup固有の同意" の設定</span><span class="sxs-lookup"><span data-stu-id="7c7b4-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="7c7b4-123">この設定は、組織内のユーザーが所有しているグループの会社データにアクセスするアプリに同意するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="7c7b4-124">チーム所有者が同意を得るためには、この設定を有効にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="7c7b4-125">PowerShell を使用してこの設定を管理する手順については、「[グループデータにアクセスするアプリにグループの所有者の同意を構成](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="7c7b4-126">Microsoft Teams 管理センターの設定</span><span class="sxs-lookup"><span data-stu-id="7c7b4-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="7c7b4-127">Azure AD の設定に加えて、[アプリ[の管理]](manage-apps.md#allow-and-block-apps)ページで、アプリがブロックされているか許可されているかにかかわらず、[アプリ[の管理] ページで](manage-apps.md)の[組織全体のアプリの設定](manage-apps.md#manage-org-wide-app-settings)、チーム所有者に割り当てられたアプリの[アクセス許可ポリシー](teams-app-permission-policies.md)が、チーム所有者が同意を得るかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c7b4-128">これらの設定を変更しても、既に同意が付与されているアプリのデータアクセスには影響しません。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="7c7b4-129">たとえば、サードパーティ製のアプリを無効にした場合や、特定のアプリをブロックしてチームの所有者が同意を得られないようにした場合、これらの変更では、既に許可されているデータアクセスは削除されません。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="7c7b4-130">組織全体のアプリ設定で [サードパーティ製アプリを許可する] 設定</span><span class="sxs-lookup"><span data-stu-id="7c7b4-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="7c7b4-131">この組織全体のアプリの設定では、組織内のユーザーがサードパーティ製のアプリを使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="7c7b4-132">チーム所有者が同意を得るためには、この設定が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="7c7b4-133">この設定を管理するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="7c7b4-134">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動し、  >  **Manage apps**[**組織全体のアプリの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="7c7b4-135">[**サードパーティ製のアプリ**] の下で、[**サードパーティ製のアプリを許可する**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    ![[Teams でサードパーティ製のアプリを許可する] 設定のスクリーンショット](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="7c7b4-137">変更が有効になるまで最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="7c7b4-138">組織レベルでアプリを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="7c7b4-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="7c7b4-139">[[アプリの管理](manage-apps.md#allow-and-block-apps)] ページでアプリをブロックまたは許可すると、そのアプリは組織内のすべてのユーザーに対してブロックまたは許可されます。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="7c7b4-140">チーム所有者は、アプリが許可されている場合にのみ、アプリへの同意を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="7c7b4-141">組織レベルでアプリを許可またはブロックするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="7c7b4-142">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="7c7b4-143">[アプリの管理] ページでアプリを選択し、[**ブロック**] をクリックしてアプリをブロックするか、[**許可**] をクリックして許可します。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![組織全体の設定でブロックされているアプリのスクリーンショット](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="7c7b4-145">チーム所有者に割り当てられているアプリのアクセス許可ポリシー</span><span class="sxs-lookup"><span data-stu-id="7c7b4-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="7c7b4-146">チーム所有者は、アプリのアクセス許可ポリシーによって実行が許可されているアプリに対してのみ同意を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="7c7b4-147">チーム所有者に割り当てられているアプリのアクセス許可ポリシーを表示および管理するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="7c7b4-148">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="7c7b4-149">チーム所有者の表示名をダブルクリックし、[**ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="7c7b4-150">チーム所有者に割り当てられているポリシーが [**アプリのアクセス許可ポリシー**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="7c7b4-151">別のポリシーを割り当てるには、[**編集**] をクリックし、割り当てるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="7c7b4-152">チーム所有者に割り当てられているポリシーの設定を編集するには、ポリシー名をクリックして、必要な変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="7c7b4-153">カスタムアプリのアップロード</span><span class="sxs-lookup"><span data-stu-id="7c7b4-153">Uploading custom apps</span></span>

<span data-ttu-id="7c7b4-154">リソース固有の同意を使っているカスタムアプリ (とも呼ばれる) をアップロードする場合は、アプリがインストールされているテナントから取得される必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="7c7b4-155">つまり、Azure AD アプリの登録はこのテナントからのものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="7c7b4-156">グローバル管理者はこの制限から除外され、任意のテナントからチーム (サイドローディング) またはテナントアプリカタログに直接、カスタムアプリをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="7c7b4-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7c7b4-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c7b4-157">Related topics</span></span>

- [<span data-ttu-id="7c7b4-158">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="7c7b4-158">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="7c7b4-159">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="7c7b4-159">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="7c7b4-160">Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="7c7b4-160">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
