---
title: カスタムアプリのポリシーと設定を管理する
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: b368b0f81a4ce6bcdf3416ec597b702534e4a857
ms.sourcegitcommit: 54ce623c4db792b5e33f5db00e575afc88776b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "44698277"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="63bd9-103">Microsoft Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="63bd9-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="63bd9-104">アプリ Studio を使うには、「 [C#/.NET とアプリ studio で Microsoft Teams プラットフォーム](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio)の使用を開始する」を参照してください。最後の手順はまだ機能していないため、zip をダウンロードして、 [microsoft teams にアプリパッケージをアップロード](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)する前の方法でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63bd9-104">To use App Studio see [Get started on the Microsoft Teams platform with C#/.NET and App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) The last step is not working yet, so you will need to download the zip and install it the old way at [Upload an app package to Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload).</span></span>

<span data-ttu-id="63bd9-105">管理者として、カスタムアプリポリシーと設定を使用して、組織内のユーザーが Microsoft Teams にカスタムアプリをアップロードできるユーザーを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-105">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="63bd9-106">管理者は、カスタムアプリをアップロードできるユーザーを決定し、管理者とチーム所有者は、組織内の特定のチームに対してカスタムアプリの追加を許可するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-106">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  <span data-ttu-id="63bd9-107">カスタムアプリポリシーを編集した後は、変更が有効になるまでに数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="63bd9-107">After you edit the custom app policy, it can take a few hours for changes to take effect.</span></span> <span data-ttu-id="63bd9-108">これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="63bd9-108">You must be a global admin or Teams service admin to manage these policies.</span></span>

## <a name="overview-of-custom-apps"></a><span data-ttu-id="63bd9-109">カスタムアプリの概要</span><span class="sxs-lookup"><span data-stu-id="63bd9-109">Overview of custom apps</span></span>

<span data-ttu-id="63bd9-110">ユーザーは、アプリパッケージ (.zip ファイル) を直接チームまたは個人用コンテキストでアップロードして、チームにカスタムアプリを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-110">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="63bd9-111">これは、Teams app store によってアプリを追加する方法とは異なります。</span><span class="sxs-lookup"><span data-stu-id="63bd9-111">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="63bd9-112">サイドローディングとも呼ばれるアプリパッケージをアップロードしてカスタムアプリを追加することで、アプリが開発中であることをテストして、広く配布する準備ができます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-112">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="63bd9-113">また、内部使用専用のアプリを構築して、Teams app store の Teams アプリカタログに提出することなくチームと共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-113">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![App store の [カスタムアプリのアップロード] オプションを示すスクリーンショット](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="63bd9-115">カスタムアプリのポリシーと設定</span><span class="sxs-lookup"><span data-stu-id="63bd9-115">Custom app policy and settings</span></span>

<span data-ttu-id="63bd9-116">3つのコンポーネントは、ユーザーがカスタムアプリをチームにアップロードできるかどうかを決定し、カスタムアプリをチームに追加できるユーザーと、どのチームカスタムアプリを追加できるかを細かく制御できるようにします。</span><span class="sxs-lookup"><span data-stu-id="63bd9-116">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="63bd9-117">ユーザーカスタムアプリポリシー</span><span class="sxs-lookup"><span data-stu-id="63bd9-117">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="63bd9-118">チームのカスタムアプリの設定</span><span class="sxs-lookup"><span data-stu-id="63bd9-118">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="63bd9-119">組織全体のカスタムアプリ設定</span><span class="sxs-lookup"><span data-stu-id="63bd9-119">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="63bd9-120">これらの設定は、サードパーティ製のアプリをブロックする機能には影響しません。</span><span class="sxs-lookup"><span data-stu-id="63bd9-120">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="63bd9-121">ユーザーカスタムアプリポリシー</span><span class="sxs-lookup"><span data-stu-id="63bd9-121">User custom app policy</span></span>

<span data-ttu-id="63bd9-122">[アプリのセットアップポリシー](teams-app-setup-policies.md)の一部として、管理者は、ポリシー設定を使用し、**カスタムアプリをアップロード**して、ユーザーがカスタムアプリを Teams にアップロードできるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-122">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Upload custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="63bd9-123">この設定を無効にする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="63bd9-123">If this setting is turned off:</span></span>

- <span data-ttu-id="63bd9-124">ユーザーはカスタムアプリを組織内のチームまたは個人のコンテキストでアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="63bd9-124">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="63bd9-125">ユーザーは、組織全体のカスタムアプリの設定に応じて、カスタムアプリを操作できます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-125">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="63bd9-126">この設定を有効にする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="63bd9-126">If this setting is turned on:</span></span>

- <span data-ttu-id="63bd9-127">ユーザーは、組織全体のカスタムアプリの設定に応じて、ユーザーがアプリを所有しているか、所有者である teams にカスタムアプリをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-127">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="63bd9-128">ユーザーは、カスタムアプリを個人用コンテキストにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-128">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="63bd9-129">ユーザーは、組織全体のカスタムアプリの設定に応じて、カスタムアプリを操作できます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-129">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="63bd9-130">グローバルアプリセットアップポリシーの設定を編集して、目的のアプリを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-130">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="63bd9-131">組織内のさまざまなユーザーグループのチームをカスタマイズする場合は、1つまたは複数のカスタムアプリセットアップポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-131">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="63bd9-132">ユーザー独自のアプリポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="63bd9-132">Set a user custom app policy</span></span>

1. <span data-ttu-id="63bd9-133">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="63bd9-133">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="63bd9-134">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bd9-134">Click **Add**.</span></span>
3. <span data-ttu-id="63bd9-135">**カスタムアプリのアップロード**をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="63bd9-135">Turn on or turn off **Upload custom apps**.</span></span>
4. <span data-ttu-id="63bd9-136">ポリシーに対して必要なその他の設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-136">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="63bd9-137">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bd9-137">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="63bd9-138">チームのカスタムアプリの設定</span><span class="sxs-lookup"><span data-stu-id="63bd9-138">Team custom app setting</span></span>

<span data-ttu-id="63bd9-139">管理者とチーム所有者は、チームがカスタムアプリを追加できるようにするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-139">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="63bd9-140">この設定では、メンバーがカスタムアプリを**アップロードする**ことを許可し、ユーザーのカスタムアプリポリシーと共に、特定のチームにカスタムアプリを追加できるユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="63bd9-140">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="63bd9-141">この設定を無効にする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="63bd9-141">If this setting is turned off:</span></span>

- <span data-ttu-id="63bd9-142">カスタムアプリポリシーで許可されている場合、チーム所有者はカスタムアプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-142">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="63bd9-143">チームの所有者ではないチームメンバーが、チームにカスタムアプリを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="63bd9-143">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="63bd9-144">この設定を有効にする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="63bd9-144">If this setting is turned on:</span></span>

- <span data-ttu-id="63bd9-145">カスタムアプリポリシーで許可されている場合は、チーム所有者がカスタムアプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-145">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="63bd9-146">ユーザー設定のアプリポリシーで許可されている場合は、チームの所有者ではないチームメンバーがカスタムアプリを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-146">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="63bd9-147">チームカスタムアプリの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="63bd9-147">Configure the team custom app setting</span></span>

1. <span data-ttu-id="63bd9-148">Teams で、チームに移動し、[**その他のオプション̇̇̇**  >  **管理チーム**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bd9-148">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="63bd9-149">[**設定**] をクリックし、[**メンバーの権限**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="63bd9-149">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="63bd9-150">[**メンバーによるカスタムアプリのアップロードを許可**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="63bd9-150">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![チームのカスタムアプリの設定を示すスクリーンショット](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="63bd9-152">組織全体のカスタムアプリ設定</span><span class="sxs-lookup"><span data-stu-id="63bd9-152">Org-wide custom app setting</span></span>

<span data-ttu-id="63bd9-153">[[アプリの管理](manage-apps.md)] ページの [**カスタムアプリでの操作を許可する**] は、組織内のすべてのユーザーに適用され、ユーザーがカスタムアプリをアップロードまたは操作できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="63bd9-153">The **Allow interaction with custom apps** org-wide custom app setting on the [Manage apps](manage-apps.md) page applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="63bd9-154">この設定により、ユーザーとチームのカスタムアプリのポリシーと設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-154">This setting overrides the user and team custom app policy and setting.</span></span> <span data-ttu-id="63bd9-155">これは、セキュリティイベント中にマスタオン/オフスイッチとして機能することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="63bd9-155">It's intended to serve as a master on/off switch during security events.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="63bd9-156">組織全体のカスタムアプリ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="63bd9-156">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="63bd9-157">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。</span><span class="sxs-lookup"><span data-stu-id="63bd9-157">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="63bd9-158">[**組織全体のアプリの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bd9-158">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="63bd9-159">[**カスタムアプリ**] で、[**カスタムアプリとの対話を許可する**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="63bd9-159">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![組織全体のカスタムアプリ設定を示すスクリーンショット](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="63bd9-161">カスタムアプリのポリシーと設定の連携方法</span><span class="sxs-lookup"><span data-stu-id="63bd9-161">How custom app policies and settings work together</span></span>

<span data-ttu-id="63bd9-162">次の表は、カスタムアプリのポリシーと設定、それらがどのように連携するか、および組織内のユーザーがカスタムアプリをチームにアップロードできることを制御することによる影響をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="63bd9-162">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="63bd9-163">たとえば、チーム所有者だけが、特定のチームにカスタムアプリをアップロードすることを許可するとします。</span><span class="sxs-lookup"><span data-stu-id="63bd9-163">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="63bd9-164">次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="63bd9-164">You would set the following:</span></span>
- <span data-ttu-id="63bd9-165">Microsoft Teams 管理センターで、[**カスタムアプリでの操作を許可する**] 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="63bd9-165">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="63bd9-166">[**メンバーに許可] を**オフにして、アクセスを制限するすべてのチームのカスタムアプリをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="63bd9-166">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="63bd9-167">[**カスタムアプリのアップロード**] 設定をオンにして、Microsoft Teams 管理センターでカスタムアプリセットアップポリシーを作成して割り当て、それをチーム所有者に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-167">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **Upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="63bd9-168">組織全体のカスタムアプリ設定</span><span class="sxs-lookup"><span data-stu-id="63bd9-168">Org-wide custom app setting</span></span> |<span data-ttu-id="63bd9-169">チームのカスタムアプリの設定</span><span class="sxs-lookup"><span data-stu-id="63bd9-169">Team custom app setting</span></span> |<span data-ttu-id="63bd9-170">ユーザーカスタムアプリポリシー</span><span class="sxs-lookup"><span data-stu-id="63bd9-170">User custom app policy</span></span> |<span data-ttu-id="63bd9-171">影響</span><span class="sxs-lookup"><span data-stu-id="63bd9-171">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="63bd9-172">オフ</span><span class="sxs-lookup"><span data-stu-id="63bd9-172">Off</span></span>    | <span data-ttu-id="63bd9-173">オフ</span><span class="sxs-lookup"><span data-stu-id="63bd9-173">Off</span></span>    | <span data-ttu-id="63bd9-174">オフ</span><span class="sxs-lookup"><span data-stu-id="63bd9-174">Off</span></span>     |<span data-ttu-id="63bd9-175">組織では、すべてのカスタムアプリとの相互作用がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-175">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="63bd9-176">カスタムアプリは、Teams サービス管理者またはグローバル管理者を除くすべてのユーザーがアップロードすることはできません。PowerShell を使用してカスタムアプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-176">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="63bd9-177">オフ</span><span class="sxs-lookup"><span data-stu-id="63bd9-177">Off</span></span>     | <span data-ttu-id="63bd9-178">オフ</span><span class="sxs-lookup"><span data-stu-id="63bd9-178">Off</span></span>     | <span data-ttu-id="63bd9-179">オン</span><span class="sxs-lookup"><span data-stu-id="63bd9-179">On</span></span>        |<span data-ttu-id="63bd9-180">組織では、すべてのカスタムアプリとの相互作用がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-180">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="63bd9-181">カスタムアプリは、Teams サービス管理者またはグローバル管理者を除くすべてのユーザーがアップロードすることはできません。PowerShell を使用してカスタムアプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-181">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="63bd9-182">オフ</span><span class="sxs-lookup"><span data-stu-id="63bd9-182">Off</span></span>    | <span data-ttu-id="63bd9-183">オン</span><span class="sxs-lookup"><span data-stu-id="63bd9-183">On</span></span>        | <span data-ttu-id="63bd9-184">オフ</span><span class="sxs-lookup"><span data-stu-id="63bd9-184">Off</span></span>        |<span data-ttu-id="63bd9-185">組織では、すべてのカスタムアプリとの相互作用がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-185">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="63bd9-186">カスタムアプリは、Teams サービス管理者またはグローバル管理者を除くすべてのユーザーがアップロードすることはできません。Windows PowerShell を使用して、カスタムアプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-186">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="63bd9-187">オフ</span><span class="sxs-lookup"><span data-stu-id="63bd9-187">Off</span></span>    | <span data-ttu-id="63bd9-188">オン</span><span class="sxs-lookup"><span data-stu-id="63bd9-188">On</span></span>      | <span data-ttu-id="63bd9-189">オン</span><span class="sxs-lookup"><span data-stu-id="63bd9-189">On</span></span>       |<span data-ttu-id="63bd9-190">組織では、すべてのカスタムアプリとの相互作用がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-190">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="63bd9-191">カスタムアプリは、Teams サービス管理者またはグローバル管理者を除くすべてのユーザーがアップロードすることはできません。PowerShell を使用してカスタムアプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-191">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="63bd9-192">オン</span><span class="sxs-lookup"><span data-stu-id="63bd9-192">On</span></span>    | <span data-ttu-id="63bd9-193">オフ</span><span class="sxs-lookup"><span data-stu-id="63bd9-193">Off</span></span>       | <span data-ttu-id="63bd9-194">オフ</span><span class="sxs-lookup"><span data-stu-id="63bd9-194">Off</span></span>         |  <span data-ttu-id="63bd9-195">ユーザーがカスタムアプリをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="63bd9-195">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="63bd9-196">オン</span><span class="sxs-lookup"><span data-stu-id="63bd9-196">On</span></span>     | <span data-ttu-id="63bd9-197">オフ</span><span class="sxs-lookup"><span data-stu-id="63bd9-197">Off</span></span>       | <span data-ttu-id="63bd9-198">オン</span><span class="sxs-lookup"><span data-stu-id="63bd9-198">On</span></span>         | <span data-ttu-id="63bd9-199">ユーザーがチーム所有者の場合は、チームにカスタムアプリをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-199">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="63bd9-200">ユーザーがチーム所有者ではない場合は、チームにカスタムアプリをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="63bd9-200">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="63bd9-201">ユーザーは、個人用コンテキストでカスタムアプリをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-201">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="63bd9-202">オン</span><span class="sxs-lookup"><span data-stu-id="63bd9-202">On</span></span>     | <span data-ttu-id="63bd9-203">オン</span><span class="sxs-lookup"><span data-stu-id="63bd9-203">On</span></span>     | <span data-ttu-id="63bd9-204">オフ</span><span class="sxs-lookup"><span data-stu-id="63bd9-204">Off</span></span>         | <span data-ttu-id="63bd9-205">ユーザーがカスタムアプリをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="63bd9-205">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="63bd9-206">オン</span><span class="sxs-lookup"><span data-stu-id="63bd9-206">On</span></span>    | <span data-ttu-id="63bd9-207">オン</span><span class="sxs-lookup"><span data-stu-id="63bd9-207">On</span></span>        | <span data-ttu-id="63bd9-208">オン</span><span class="sxs-lookup"><span data-stu-id="63bd9-208">On</span></span>        | <span data-ttu-id="63bd9-209">ユーザーがチーム所有者であるかどうかに関係なく、ユーザーはカスタムアプリをチームにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-209">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="63bd9-210">ユーザーは、個人用コンテキストでカスタムアプリをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="63bd9-210">The user can upload custom apps in the personal context.</span></span>       |

 ## <a name="related-topics"></a><span data-ttu-id="63bd9-211">関連項目</span><span class="sxs-lookup"><span data-stu-id="63bd9-211">Related topics</span></span>
 
- [<span data-ttu-id="63bd9-212">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="63bd9-212">Admin settings for apps in Teams</span></span>](admin-settings.md)
