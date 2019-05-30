---
title: Microsoft Teams のカスタム アプリのポリシーと設定を管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/18/2019
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: カスタムアプリポリシーと設定を管理して、組織内のユーザーが Microsoft Teams でカスタムアプリをアップロードできるユーザーを制御する方法について説明します。
ms.openlocfilehash: c1aa7489761fb27f525fbb6eb8f2056ae3dd33c8
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548662"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="87919-103">Microsoft Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="87919-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

> [!NOTE]
> <span data-ttu-id="87919-104">Microsoft Teams でアプリを管理するための現在の方法については、「[組織の Microsoft teams の設定を管理](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87919-104">For the current method of managing apps in Microsoft Teams, see [Manage Microsoft Teams settings for your organization](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365).</span></span>

<span data-ttu-id="87919-105">管理者として、カスタムアプリポリシーと設定を使用して、組織内のユーザーが Microsoft Teams にカスタムアプリをアップロードできるユーザーを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="87919-105">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="87919-106">管理者は、カスタムアプリをアップロードできるユーザーを決定し、管理者とチーム所有者は、組織内の特定のチームに対してカスタムアプリの追加を許可するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="87919-106">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  

## <a name="overview-of-custom-apps"></a><span data-ttu-id="87919-107">カスタムアプリの概要</span><span class="sxs-lookup"><span data-stu-id="87919-107">Overview of custom apps</span></span>

<span data-ttu-id="87919-108">ユーザーは、アプリパッケージ (.zip ファイル) を直接チームまたは個人用コンテキストでアップロードして、チームにカスタムアプリを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="87919-108">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="87919-109">これは、Teams app store によってアプリを追加する方法とは異なります。</span><span class="sxs-lookup"><span data-stu-id="87919-109">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="87919-110">サイドローディングとも呼ばれるアプリパッケージをアップロードしてカスタムアプリを追加することで、アプリが開発中であることをテストして、広く配布する準備ができます。</span><span class="sxs-lookup"><span data-stu-id="87919-110">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="87919-111">また、内部使用専用のアプリを構築して、Teams app store の Teams アプリカタログに提出することなくチームと共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="87919-111">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![App store の [カスタムアプリのアップロード] オプションを示すスクリーンショット](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="87919-113">カスタムアプリのポリシーと設定</span><span class="sxs-lookup"><span data-stu-id="87919-113">Custom app policy and settings</span></span>

<span data-ttu-id="87919-114">3つのコンポーネントは、ユーザーがカスタムアプリをチームにアップロードできるかどうかを決定し、カスタムアプリをチームに追加できるユーザーと、どのチームカスタムアプリを追加できるかを細かく制御できるようにします。</span><span class="sxs-lookup"><span data-stu-id="87919-114">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="87919-115">ユーザーカスタムアプリポリシー</span><span class="sxs-lookup"><span data-stu-id="87919-115">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="87919-116">チームのカスタムアプリの設定</span><span class="sxs-lookup"><span data-stu-id="87919-116">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="87919-117">組織全体のカスタムアプリ設定</span><span class="sxs-lookup"><span data-stu-id="87919-117">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="87919-118">これらの設定は、サードパーティ製のアプリをブロックする機能には影響しません。</span><span class="sxs-lookup"><span data-stu-id="87919-118">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="87919-119">ユーザーカスタムアプリポリシー</span><span class="sxs-lookup"><span data-stu-id="87919-119">User custom app policy</span></span>

<span data-ttu-id="87919-120">[アプリセットアップポリシー](teams-app-setup-policies.md)の一部として、管理者は、ポリシー設定を使用して、**カスタムアプリのアップロードを許可**することができます。これにより、ユーザーがカスタムアプリを Teams にアップロードできるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="87919-120">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Allow uploading custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="87919-121">この設定を無効にする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="87919-121">If this setting is turned off:</span></span>

- <span data-ttu-id="87919-122">ユーザーはカスタムアプリを組織内のチームまたは個人のコンテキストでアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="87919-122">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="87919-123">ユーザーは、組織全体のカスタムアプリの設定に応じて、カスタムアプリを操作できます。</span><span class="sxs-lookup"><span data-stu-id="87919-123">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="87919-124">この設定を有効にする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="87919-124">If this setting is turned on:</span></span>

- <span data-ttu-id="87919-125">ユーザーは、組織全体のカスタムアプリの設定に応じて、ユーザーがアプリを所有しているか、所有者である teams にカスタムアプリをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="87919-125">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="87919-126">ユーザーは、カスタムアプリを個人用コンテキストにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="87919-126">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="87919-127">ユーザーは、組織全体のカスタムアプリの設定に応じて、カスタムアプリを操作できます。</span><span class="sxs-lookup"><span data-stu-id="87919-127">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="87919-128">グローバルアプリセットアップポリシーの設定を編集して、目的のアプリを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="87919-128">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="87919-129">組織内のさまざまなユーザーグループのチームをカスタマイズする場合は、1つまたは複数のカスタムアプリセットアップポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="87919-129">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="87919-130">ユーザー独自のアプリポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="87919-130">Set a user custom app policy</span></span>

1. <span data-ttu-id="87919-131">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** > **セットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="87919-131">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="87919-132">[**新しいポリシー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="87919-132">Select **New policy**.</span></span>
3. <span data-ttu-id="87919-133">[**カスタムアプリのアップロードを許可する**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="87919-133">Turn on or turn off **Allow uploading custom apps**.</span></span>
4. <span data-ttu-id="87919-134">ポリシーに対して必要なその他の設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="87919-134">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="87919-135">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87919-135">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="87919-136">チームのカスタムアプリの設定</span><span class="sxs-lookup"><span data-stu-id="87919-136">Team custom app setting</span></span>

<span data-ttu-id="87919-137">管理者とチーム所有者は、チームがカスタムアプリを追加できるようにするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="87919-137">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="87919-138">この設定では、メンバーがカスタムアプリを**アップロードする**ことを許可し、ユーザーのカスタムアプリポリシーと共に、特定のチームにカスタムアプリを追加できるユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="87919-138">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="87919-139">この設定を無効にする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="87919-139">If this setting is turned off:</span></span>

- <span data-ttu-id="87919-140">カスタムアプリポリシーで許可されている場合、チーム所有者はカスタムアプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="87919-140">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="87919-141">チームの所有者ではないチームメンバーが、チームにカスタムアプリを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="87919-141">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="87919-142">この設定を有効にする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="87919-142">If this setting is turned on:</span></span>

- <span data-ttu-id="87919-143">カスタムアプリポリシーで許可されている場合は、チーム所有者がカスタムアプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="87919-143">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="87919-144">ユーザー設定のアプリポリシーで許可されている場合は、チームの所有者ではないチームメンバーがカスタムアプリを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="87919-144">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="87919-145">チームカスタムアプリの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="87919-145">Configure the team custom app setting</span></span>

1. <span data-ttu-id="87919-146">Teams で、チームに移動し、[**その他のオプション̇̇̇** > **管理チーム**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87919-146">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="87919-147">[**設定**] をクリックし、[**メンバーの権限**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="87919-147">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="87919-148">[**メンバーによるカスタムアプリのアップロードを許可**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="87919-148">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![チームのカスタムアプリの設定を示すスクリーンショット](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="87919-150">組織全体のカスタムアプリ設定</span><span class="sxs-lookup"><span data-stu-id="87919-150">Org-wide custom app setting</span></span>

<span data-ttu-id="87919-151">組織全体のカスタムアプリ設定、**カスタムアプリとの操作を許可する**は、組織内のすべてのユーザーに適用され、ユーザーがカスタムアプリをアップロードまたは操作できるかどうかを管理します。</span><span class="sxs-lookup"><span data-stu-id="87919-151">The org-wide custom app setting, **Allow interaction with custom apps**, applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="87919-152">この設定により、ユーザーとチームのカスタムアプリのポリシーと設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="87919-152">This setting overrides the user and team custom app policy and setting.</span></span> <span data-ttu-id="87919-153">これは、セキュリティイベント中にマスタオン/オフスイッチとして機能することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="87919-153">It's intended to serve as a master on/off switch during security events.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="87919-154">組織全体のカスタムアプリ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="87919-154">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="87919-155">Microsoft Teams 管理センターの左のナビゲーションで、[**チームアプリ** > の**アクセス許可ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="87919-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="87919-156">[**組織全体のアプリの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87919-156">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="87919-157">[**カスタムアプリ**] で、[**カスタムアプリとの対話を許可する**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="87919-157">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![組織全体のカスタムアプリ設定を示すスクリーンショット](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="87919-159">カスタムアプリのポリシーと設定の連携方法</span><span class="sxs-lookup"><span data-stu-id="87919-159">How custom app policies and settings work together</span></span>

<span data-ttu-id="87919-160">次の表は、カスタムアプリのポリシーと設定、それらがどのように連携するか、および組織内のユーザーがカスタムアプリをチームにアップロードできることを制御することによる影響をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="87919-160">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="87919-161">たとえば、チーム所有者だけが、特定のチームにカスタムアプリをアップロードすることを許可するとします。</span><span class="sxs-lookup"><span data-stu-id="87919-161">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="87919-162">次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="87919-162">You would set the following:</span></span>
- <span data-ttu-id="87919-163">Microsoft Teams 管理センターで、[**カスタムアプリでの操作を許可する**] 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="87919-163">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="87919-164">[**メンバーに許可] を**オフにして、アクセスを制限するすべてのチームのカスタムアプリをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="87919-164">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="87919-165">**ユーザーが [カスタムアプリをアップロードする**] 設定をオンにして、チームの所有者に割り当てることができるように、Microsoft Teams 管理センターでカスタムアプリセットアップポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="87919-165">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **User can upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="87919-166">組織全体のカスタムアプリ設定</span><span class="sxs-lookup"><span data-stu-id="87919-166">Org-wide custom app setting</span></span> |<span data-ttu-id="87919-167">チームのカスタムアプリの設定</span><span class="sxs-lookup"><span data-stu-id="87919-167">Team custom app setting</span></span> |<span data-ttu-id="87919-168">ユーザーカスタムアプリポリシー</span><span class="sxs-lookup"><span data-stu-id="87919-168">User custom app policy</span></span> |<span data-ttu-id="87919-169">影響</span><span class="sxs-lookup"><span data-stu-id="87919-169">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="87919-170">オフ</span><span class="sxs-lookup"><span data-stu-id="87919-170">Off</span></span>    | <span data-ttu-id="87919-171">オフ</span><span class="sxs-lookup"><span data-stu-id="87919-171">Off</span></span>    | <span data-ttu-id="87919-172">オフ</span><span class="sxs-lookup"><span data-stu-id="87919-172">Off</span></span>     |<span data-ttu-id="87919-173">組織では、すべてのカスタムアプリとの相互作用がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="87919-173">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="87919-174">カスタムアプリをすべてのユーザーがアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="87919-174">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="87919-175">PowerShell を使用してカスタムアプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="87919-175">You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="87919-176">オフ</span><span class="sxs-lookup"><span data-stu-id="87919-176">Off</span></span>     | <span data-ttu-id="87919-177">オフ</span><span class="sxs-lookup"><span data-stu-id="87919-177">Off</span></span>     | <span data-ttu-id="87919-178">オン</span><span class="sxs-lookup"><span data-stu-id="87919-178">On</span></span>        |<span data-ttu-id="87919-179">組織では、すべてのカスタムアプリとの相互作用がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="87919-179">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="87919-180">カスタムアプリをすべてのユーザーがアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="87919-180">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="87919-181">PowerShell を使用してカスタムアプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="87919-181">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="87919-182">オフ</span><span class="sxs-lookup"><span data-stu-id="87919-182">Off</span></span>    | <span data-ttu-id="87919-183">オン</span><span class="sxs-lookup"><span data-stu-id="87919-183">On</span></span>        | <span data-ttu-id="87919-184">オフ</span><span class="sxs-lookup"><span data-stu-id="87919-184">Off</span></span>        |<span data-ttu-id="87919-185">組織では、すべてのカスタムアプリとの相互作用がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="87919-185">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="87919-186">カスタムアプリをすべてのユーザーがアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="87919-186">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="87919-187">Windows PowerShell を使用して、カスタムアプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="87919-187">You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="87919-188">オフ</span><span class="sxs-lookup"><span data-stu-id="87919-188">Off</span></span>    | <span data-ttu-id="87919-189">オン</span><span class="sxs-lookup"><span data-stu-id="87919-189">On</span></span>      | <span data-ttu-id="87919-190">オン</span><span class="sxs-lookup"><span data-stu-id="87919-190">On</span></span>       |<span data-ttu-id="87919-191">組織では、すべてのカスタムアプリとの相互作用がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="87919-191">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="87919-192">カスタムアプリをすべてのユーザーがアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="87919-192">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="87919-193">PowerShell を使用してカスタムアプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="87919-193">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="87919-194">オン</span><span class="sxs-lookup"><span data-stu-id="87919-194">On</span></span>    | <span data-ttu-id="87919-195">オフ</span><span class="sxs-lookup"><span data-stu-id="87919-195">Off</span></span>       | <span data-ttu-id="87919-196">オフ</span><span class="sxs-lookup"><span data-stu-id="87919-196">Off</span></span>         |  <span data-ttu-id="87919-197">ユーザーがカスタムアプリをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="87919-197">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="87919-198">オン</span><span class="sxs-lookup"><span data-stu-id="87919-198">On</span></span>     | <span data-ttu-id="87919-199">オフ</span><span class="sxs-lookup"><span data-stu-id="87919-199">Off</span></span>       | <span data-ttu-id="87919-200">オン</span><span class="sxs-lookup"><span data-stu-id="87919-200">On</span></span>         | <span data-ttu-id="87919-201">ユーザーがチーム所有者の場合は、チームにカスタムアプリをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="87919-201">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="87919-202">ユーザーがチーム所有者ではない場合は、チームにカスタムアプリをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="87919-202">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="87919-203">ユーザーは、個人用コンテキストでカスタムアプリをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="87919-203">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="87919-204">オン</span><span class="sxs-lookup"><span data-stu-id="87919-204">On</span></span>     | <span data-ttu-id="87919-205">オン</span><span class="sxs-lookup"><span data-stu-id="87919-205">On</span></span>     | <span data-ttu-id="87919-206">オフ</span><span class="sxs-lookup"><span data-stu-id="87919-206">Off</span></span>         | <span data-ttu-id="87919-207">ユーザーがカスタムアプリをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="87919-207">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="87919-208">オン</span><span class="sxs-lookup"><span data-stu-id="87919-208">On</span></span>    | <span data-ttu-id="87919-209">オン</span><span class="sxs-lookup"><span data-stu-id="87919-209">On</span></span>        | <span data-ttu-id="87919-210">オン</span><span class="sxs-lookup"><span data-stu-id="87919-210">On</span></span>        | <span data-ttu-id="87919-211">ユーザーがチーム所有者であるかどうかに関係なく、ユーザーはカスタムアプリをチームにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="87919-211">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="87919-212">ユーザーは、個人用コンテキストでカスタムアプリをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="87919-212">The user can upload custom apps in the personal context.</span></span>       |

 ## <a name="related-topics"></a><span data-ttu-id="87919-213">関連トピック</span><span class="sxs-lookup"><span data-stu-id="87919-213">Related topics</span></span>
- [<span data-ttu-id="87919-214">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="87919-214">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="87919-215">Microsoft Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="87919-215">Manage app setup policies in Microsoft Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="87919-216">Microsoft Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="87919-216">Manage app permission policies in Microsoft Teams</span></span>](teams-app-permission-policies.md)
