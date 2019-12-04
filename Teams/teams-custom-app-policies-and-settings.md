---
title: Microsoft Teams のカスタム アプリのポリシーと設定を管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: カスタムアプリポリシーと設定を管理して、組織内のユーザーが Microsoft Teams でカスタムアプリをアップロードできるユーザーを制御する方法について説明します。
f1keywords:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
ms.openlocfilehash: 8a4d7b60485f9411faeb46f8745735039f4dd21b
ms.sourcegitcommit: 57304ac641931eed87e649555fd5eb5e58732dc5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "39679317"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="0d3cd-103">Microsoft Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="0d3cd-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="0d3cd-104">アプリ Studio を使うには、「 [C#/.NET とアプリ studio で Microsoft Teams プラットフォーム](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio)の使用を開始する」を参照してください。最後の手順はまだ機能していないため、zip をダウンロードして、 [microsoft teams にアプリパッケージをアップロード](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)する前の方法でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-104">To use App Studio see [Get started on the Microsoft Teams platform with C#/.NET and App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) The last step is not working yet, so you will need to download the zip and install it the old way at [Upload an app package to Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload).</span></span>

<span data-ttu-id="0d3cd-105">管理者として、カスタムアプリポリシーと設定を使用して、組織内のユーザーが Microsoft Teams にカスタムアプリをアップロードできるユーザーを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-105">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="0d3cd-106">管理者は、カスタムアプリをアップロードできるユーザーを決定し、管理者とチーム所有者は、組織内の特定のチームに対してカスタムアプリの追加を許可するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-106">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  <span data-ttu-id="0d3cd-107">カスタムアプリポリシーを編集した後は、変更が有効になるまで最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-107">After you edit the Custom App policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="overview-of-custom-apps"></a><span data-ttu-id="0d3cd-108">カスタムアプリの概要</span><span class="sxs-lookup"><span data-stu-id="0d3cd-108">Overview of custom apps</span></span>

<span data-ttu-id="0d3cd-109">ユーザーは、アプリパッケージ (.zip ファイル) を直接チームまたは個人用コンテキストでアップロードして、チームにカスタムアプリを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-109">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="0d3cd-110">これは、Teams app store によってアプリを追加する方法とは異なります。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-110">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="0d3cd-111">サイドローディングとも呼ばれるアプリパッケージをアップロードしてカスタムアプリを追加することで、アプリが開発中であることをテストして、広く配布する準備ができます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-111">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="0d3cd-112">また、内部使用専用のアプリを構築して、Teams app store の Teams アプリカタログに提出することなくチームと共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-112">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![App store の [カスタムアプリのアップロード] オプションを示すスクリーンショット](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="0d3cd-114">カスタムアプリのポリシーと設定</span><span class="sxs-lookup"><span data-stu-id="0d3cd-114">Custom app policy and settings</span></span>

<span data-ttu-id="0d3cd-115">3つのコンポーネントは、ユーザーがカスタムアプリをチームにアップロードできるかどうかを決定し、カスタムアプリをチームに追加できるユーザーと、どのチームカスタムアプリを追加できるかを細かく制御できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-115">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="0d3cd-116">ユーザーカスタムアプリポリシー</span><span class="sxs-lookup"><span data-stu-id="0d3cd-116">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="0d3cd-117">チームのカスタムアプリの設定</span><span class="sxs-lookup"><span data-stu-id="0d3cd-117">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="0d3cd-118">組織全体のカスタムアプリ設定</span><span class="sxs-lookup"><span data-stu-id="0d3cd-118">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="0d3cd-119">これらの設定は、サードパーティ製のアプリをブロックする機能には影響しません。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-119">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="0d3cd-120">ユーザーカスタムアプリポリシー</span><span class="sxs-lookup"><span data-stu-id="0d3cd-120">User custom app policy</span></span>

<span data-ttu-id="0d3cd-121">[アプリセットアップポリシー](teams-app-setup-policies.md)の一部として、管理者は、ポリシー設定を使用して、**カスタムアプリのアップロードを許可**することができます。これにより、ユーザーがカスタムアプリを Teams にアップロードできるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-121">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Allow uploading custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="0d3cd-122">この設定を無効にする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-122">If this setting is turned off:</span></span>

- <span data-ttu-id="0d3cd-123">ユーザーはカスタムアプリを組織内のチームまたは個人のコンテキストでアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-123">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="0d3cd-124">ユーザーは、組織全体のカスタムアプリの設定に応じて、カスタムアプリを操作できます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-124">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="0d3cd-125">この設定を有効にする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-125">If this setting is turned on:</span></span>

- <span data-ttu-id="0d3cd-126">ユーザーは、組織全体のカスタムアプリの設定に応じて、ユーザーがアプリを所有しているか、所有者である teams にカスタムアプリをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-126">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="0d3cd-127">ユーザーは、カスタムアプリを個人用コンテキストにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-127">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="0d3cd-128">ユーザーは、組織全体のカスタムアプリの設定に応じて、カスタムアプリを操作できます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-128">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="0d3cd-129">グローバルアプリセットアップポリシーの設定を編集して、目的のアプリを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-129">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="0d3cd-130">組織内のさまざまなユーザーグループのチームをカスタマイズする場合は、1つまたは複数のカスタムアプリセットアップポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-130">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="0d3cd-131">ユーザー独自のアプリポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="0d3cd-131">Set a user custom app policy</span></span>

1. <span data-ttu-id="0d3cd-132">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** > **セットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-132">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="0d3cd-133">[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-133">Click **Add**.</span></span>
3. <span data-ttu-id="0d3cd-134">[**カスタムアプリのアップロードを許可する**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-134">Turn on or turn off **Allow uploading custom apps**.</span></span>
4. <span data-ttu-id="0d3cd-135">ポリシーに対して必要なその他の設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-135">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="0d3cd-136">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-136">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="0d3cd-137">チームのカスタムアプリの設定</span><span class="sxs-lookup"><span data-stu-id="0d3cd-137">Team custom app setting</span></span>

<span data-ttu-id="0d3cd-138">管理者とチーム所有者は、チームがカスタムアプリを追加できるようにするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-138">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="0d3cd-139">この設定では、メンバーがカスタムアプリを**アップロードする**ことを許可し、ユーザーのカスタムアプリポリシーと共に、特定のチームにカスタムアプリを追加できるユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-139">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="0d3cd-140">この設定を無効にする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-140">If this setting is turned off:</span></span>

- <span data-ttu-id="0d3cd-141">カスタムアプリポリシーで許可されている場合、チーム所有者はカスタムアプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-141">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="0d3cd-142">チームの所有者ではないチームメンバーが、チームにカスタムアプリを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-142">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="0d3cd-143">この設定を有効にする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-143">If this setting is turned on:</span></span>

- <span data-ttu-id="0d3cd-144">カスタムアプリポリシーで許可されている場合は、チーム所有者がカスタムアプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-144">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="0d3cd-145">ユーザー設定のアプリポリシーで許可されている場合は、チームの所有者ではないチームメンバーがカスタムアプリを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-145">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="0d3cd-146">チームカスタムアプリの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="0d3cd-146">Configure the team custom app setting</span></span>

1. <span data-ttu-id="0d3cd-147">Teams で、チームに移動し、[**その他のオプション̇̇̇** > **管理チーム**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-147">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="0d3cd-148">[**設定**] をクリックし、[**メンバーの権限**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-148">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="0d3cd-149">[**メンバーによるカスタムアプリのアップロードを許可**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-149">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![チームのカスタムアプリの設定を示すスクリーンショット](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="0d3cd-151">組織全体のカスタムアプリ設定</span><span class="sxs-lookup"><span data-stu-id="0d3cd-151">Org-wide custom app setting</span></span>

<span data-ttu-id="0d3cd-152">組織全体のカスタムアプリ設定、**カスタムアプリとの操作を許可する**は、組織内のすべてのユーザーに適用され、ユーザーがカスタムアプリをアップロードまたは操作できるかどうかを管理します。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-152">The org-wide custom app setting, **Allow interaction with custom apps**, applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="0d3cd-153">この設定により、ユーザーとチームのカスタムアプリのポリシーと設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-153">This setting overrides the user and team custom app policy and setting.</span></span> <span data-ttu-id="0d3cd-154">これは、セキュリティイベント中にマスタオン/オフスイッチとして機能することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-154">It's intended to serve as a master on/off switch during security events.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="0d3cd-155">組織全体のカスタムアプリ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="0d3cd-155">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="0d3cd-156">[Microsoft Teams 管理センター](https://admin.teams.microsoft.com/)の左のナビゲーションで、[**チームアプリ** > の**アクセス許可ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-156">In the left navigation of the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="0d3cd-157">[**組織全体のアプリの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-157">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="0d3cd-158">[**カスタムアプリ**] で、[**カスタムアプリとの対話を許可する**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-158">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![組織全体のカスタムアプリ設定を示すスクリーンショット](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="0d3cd-160">カスタムアプリのポリシーと設定の連携方法</span><span class="sxs-lookup"><span data-stu-id="0d3cd-160">How custom app policies and settings work together</span></span>

<span data-ttu-id="0d3cd-161">次の表は、カスタムアプリのポリシーと設定、それらがどのように連携するか、および組織内のユーザーがカスタムアプリをチームにアップロードできることを制御することによる影響をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-161">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="0d3cd-162">たとえば、チーム所有者だけが、特定のチームにカスタムアプリをアップロードすることを許可するとします。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-162">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="0d3cd-163">次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-163">You would set the following:</span></span>
- <span data-ttu-id="0d3cd-164">Microsoft Teams 管理センターで、[**カスタムアプリでの操作を許可する**] 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-164">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="0d3cd-165">[**メンバーに許可] を**オフにして、アクセスを制限するすべてのチームのカスタムアプリをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-165">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="0d3cd-166">**ユーザーが [カスタムアプリをアップロードする**] 設定をオンにして、チームの所有者に割り当てることができるように、Microsoft Teams 管理センターでカスタムアプリセットアップポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-166">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **User can upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="0d3cd-167">組織全体のカスタムアプリ設定</span><span class="sxs-lookup"><span data-stu-id="0d3cd-167">Org-wide custom app setting</span></span> |<span data-ttu-id="0d3cd-168">チームのカスタムアプリの設定</span><span class="sxs-lookup"><span data-stu-id="0d3cd-168">Team custom app setting</span></span> |<span data-ttu-id="0d3cd-169">ユーザーカスタムアプリポリシー</span><span class="sxs-lookup"><span data-stu-id="0d3cd-169">User custom app policy</span></span> |<span data-ttu-id="0d3cd-170">影響</span><span class="sxs-lookup"><span data-stu-id="0d3cd-170">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="0d3cd-171">オフ</span><span class="sxs-lookup"><span data-stu-id="0d3cd-171">Off</span></span>    | <span data-ttu-id="0d3cd-172">オフ</span><span class="sxs-lookup"><span data-stu-id="0d3cd-172">Off</span></span>    | <span data-ttu-id="0d3cd-173">オフ</span><span class="sxs-lookup"><span data-stu-id="0d3cd-173">Off</span></span>     |<span data-ttu-id="0d3cd-174">組織では、すべてのカスタムアプリとの相互作用がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-174">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="0d3cd-175">カスタムアプリをすべてのユーザーがアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-175">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="0d3cd-176">PowerShell を使用してカスタムアプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-176">You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="0d3cd-177">オフ</span><span class="sxs-lookup"><span data-stu-id="0d3cd-177">Off</span></span>     | <span data-ttu-id="0d3cd-178">オフ</span><span class="sxs-lookup"><span data-stu-id="0d3cd-178">Off</span></span>     | <span data-ttu-id="0d3cd-179">オン</span><span class="sxs-lookup"><span data-stu-id="0d3cd-179">On</span></span>        |<span data-ttu-id="0d3cd-180">組織では、すべてのカスタムアプリとの相互作用がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-180">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="0d3cd-181">カスタムアプリをすべてのユーザーがアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-181">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="0d3cd-182">PowerShell を使用してカスタムアプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-182">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="0d3cd-183">オフ</span><span class="sxs-lookup"><span data-stu-id="0d3cd-183">Off</span></span>    | <span data-ttu-id="0d3cd-184">オン</span><span class="sxs-lookup"><span data-stu-id="0d3cd-184">On</span></span>        | <span data-ttu-id="0d3cd-185">オフ</span><span class="sxs-lookup"><span data-stu-id="0d3cd-185">Off</span></span>        |<span data-ttu-id="0d3cd-186">組織では、すべてのカスタムアプリとの相互作用がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-186">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="0d3cd-187">カスタムアプリをすべてのユーザーがアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-187">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="0d3cd-188">Windows PowerShell を使用して、カスタムアプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-188">You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="0d3cd-189">オフ</span><span class="sxs-lookup"><span data-stu-id="0d3cd-189">Off</span></span>    | <span data-ttu-id="0d3cd-190">オン</span><span class="sxs-lookup"><span data-stu-id="0d3cd-190">On</span></span>      | <span data-ttu-id="0d3cd-191">オン</span><span class="sxs-lookup"><span data-stu-id="0d3cd-191">On</span></span>       |<span data-ttu-id="0d3cd-192">組織では、すべてのカスタムアプリとの相互作用がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-192">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="0d3cd-193">カスタムアプリをすべてのユーザーがアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-193">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="0d3cd-194">PowerShell を使用してカスタムアプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-194">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="0d3cd-195">オン</span><span class="sxs-lookup"><span data-stu-id="0d3cd-195">On</span></span>    | <span data-ttu-id="0d3cd-196">オフ</span><span class="sxs-lookup"><span data-stu-id="0d3cd-196">Off</span></span>       | <span data-ttu-id="0d3cd-197">オフ</span><span class="sxs-lookup"><span data-stu-id="0d3cd-197">Off</span></span>         |  <span data-ttu-id="0d3cd-198">ユーザーがカスタムアプリをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-198">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="0d3cd-199">オン</span><span class="sxs-lookup"><span data-stu-id="0d3cd-199">On</span></span>     | <span data-ttu-id="0d3cd-200">オフ</span><span class="sxs-lookup"><span data-stu-id="0d3cd-200">Off</span></span>       | <span data-ttu-id="0d3cd-201">オン</span><span class="sxs-lookup"><span data-stu-id="0d3cd-201">On</span></span>         | <span data-ttu-id="0d3cd-202">ユーザーがチーム所有者の場合は、チームにカスタムアプリをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-202">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="0d3cd-203">ユーザーがチーム所有者ではない場合は、チームにカスタムアプリをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-203">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="0d3cd-204">ユーザーは、個人用コンテキストでカスタムアプリをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-204">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="0d3cd-205">オン</span><span class="sxs-lookup"><span data-stu-id="0d3cd-205">On</span></span>     | <span data-ttu-id="0d3cd-206">オン</span><span class="sxs-lookup"><span data-stu-id="0d3cd-206">On</span></span>     | <span data-ttu-id="0d3cd-207">オフ</span><span class="sxs-lookup"><span data-stu-id="0d3cd-207">Off</span></span>         | <span data-ttu-id="0d3cd-208">ユーザーがカスタムアプリをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-208">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="0d3cd-209">オン</span><span class="sxs-lookup"><span data-stu-id="0d3cd-209">On</span></span>    | <span data-ttu-id="0d3cd-210">オン</span><span class="sxs-lookup"><span data-stu-id="0d3cd-210">On</span></span>        | <span data-ttu-id="0d3cd-211">オン</span><span class="sxs-lookup"><span data-stu-id="0d3cd-211">On</span></span>        | <span data-ttu-id="0d3cd-212">ユーザーがチーム所有者であるかどうかに関係なく、ユーザーはカスタムアプリをチームにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-212">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="0d3cd-213">ユーザーは、個人用コンテキストでカスタムアプリをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-213">The user can upload custom apps in the personal context.</span></span>       |

 ## <a name="related-topics"></a><span data-ttu-id="0d3cd-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d3cd-214">Related topics</span></span>
- [<span data-ttu-id="0d3cd-215">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="0d3cd-215">Admin settings for apps in Teams</span></span>](admin-settings.md)
