---
title: カスタム アプリのポリシーと設定を管理する
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams でカスタム アプリをアップロードできる組織内のユーザーを制御するために、カスタム アプリのポリシーと設定を管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 4e9863508d7b10c76ed29bfcb0fec79ca7a33dc5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821007"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="5ac34-103">Microsoft Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="5ac34-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="5ac34-104">App Studio を使用するには [、「C#/.NET](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) と App Studio を使用して Microsoft Teams プラットフォームで作業を開始する」を参照してください。最後の手順はまだ機能していないので、アプリ パッケージを [Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)にアップロードするには、zip をダウンロードして古い方法でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ac34-104">To use App Studio see [Get started on the Microsoft Teams platform with C#/.NET and App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) The last step is not working yet, so you will need to download the zip and install it the old way at [Upload an app package to Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload).</span></span>

<span data-ttu-id="5ac34-105">管理者は、カスタム アプリ のポリシーと設定を使用して、組織内のユーザーが Microsoft Teams にカスタム アプリをアップロードできるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-105">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="5ac34-106">管理者はカスタム アプリをアップロードできるユーザーを決定し、管理者とチーム所有者は、組織内の特定のチームがカスタム アプリの追加を許可するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-106">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  <span data-ttu-id="5ac34-107">カスタム アプリ ポリシーを編集した後、変更が有効になまで数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5ac34-107">After you edit the custom app policy, it can take a few hours for changes to take effect.</span></span> <span data-ttu-id="5ac34-108">これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ac34-108">You must be a global admin or Teams service admin to manage these policies.</span></span>

## <a name="overview-of-custom-apps"></a><span data-ttu-id="5ac34-109">カスタム アプリの概要</span><span class="sxs-lookup"><span data-stu-id="5ac34-109">Overview of custom apps</span></span>

<span data-ttu-id="5ac34-110">ユーザーは、(.zip ファイル内の) アプリ パッケージをチームまたは個人のコンテキストで直接アップロードすることで、Teams にカスタム アプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-110">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="5ac34-111">これは、Teams アプリ ストアを通じてアプリを追加する方法とは異なります。</span><span class="sxs-lookup"><span data-stu-id="5ac34-111">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="5ac34-112">アプリ パッケージ (サイドロードとも呼ばれる) をアップロードしてカスタム アプリを追加すると、アプリを開発中にテストしてから、広く配布する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="5ac34-112">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="5ac34-113">また、Teams アプリ ストアの Teams アプリ カタログに送信せずに、内部でのみ使用するアプリを作成し、チームと共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-113">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![アプリ ストアでカスタム アプリをアップロードするオプションを示すスクリーンショット](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="5ac34-115">カスタム アプリのポリシーと設定</span><span class="sxs-lookup"><span data-stu-id="5ac34-115">Custom app policy and settings</span></span>

<span data-ttu-id="5ac34-116">3 つのコンポーネントによって、ユーザーがカスタム アプリをチームにアップロードできるかどうかが決め、カスタム アプリをチームに追加できるユーザーと追加できるチームを細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-116">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="5ac34-117">ユーザー カスタム アプリ ポリシー</span><span class="sxs-lookup"><span data-stu-id="5ac34-117">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="5ac34-118">チーム カスタム アプリの設定</span><span class="sxs-lookup"><span data-stu-id="5ac34-118">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="5ac34-119">組織全体のカスタム アプリ設定</span><span class="sxs-lookup"><span data-stu-id="5ac34-119">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="5ac34-120">これらの設定は、サード パーティ製アプリをブロックする機能には影響を与え得ない。</span><span class="sxs-lookup"><span data-stu-id="5ac34-120">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="5ac34-121">ユーザー カスタム アプリ ポリシー</span><span class="sxs-lookup"><span data-stu-id="5ac34-121">User custom app policy</span></span>

<span data-ttu-id="5ac34-122">アプリセットアップ ポリシー[の](teams-app-setup-policies.md)一部として、管理者はポリシー設定の [カスタム アプリのアップロード] を使用して、ユーザーがカスタム アプリを Teams にアップロードできるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-122">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Upload custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="5ac34-123">この設定がオフになっている場合:</span><span class="sxs-lookup"><span data-stu-id="5ac34-123">If this setting is turned off:</span></span>

- <span data-ttu-id="5ac34-124">ユーザーは、組織内のチームまたは個人のコンテキストでカスタム アプリをアップロードできません。</span><span class="sxs-lookup"><span data-stu-id="5ac34-124">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="5ac34-125">ユーザーは、組織全体のカスタム アプリ設定に応じて、カスタム アプリを操作できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-125">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="5ac34-126">この設定がオンになっている場合:</span><span class="sxs-lookup"><span data-stu-id="5ac34-126">If this setting is turned on:</span></span>

- <span data-ttu-id="5ac34-127">ユーザーは、組織全体のカスタム アプリ設定に応じて、カスタム アプリを許可するチームおよび所有者であるチームにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-127">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="5ac34-128">ユーザーはカスタム アプリを個人用コンテキストにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-128">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="5ac34-129">ユーザーは、組織全体のカスタム アプリ設定に応じて、カスタム アプリを操作できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-129">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="5ac34-130">グローバル アプリ セットアップ ポリシーの設定を編集して、必要なアプリを含めできます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-130">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="5ac34-131">組織内のユーザーのグループごとに Teams をカスタマイズする場合は、1 つ以上のカスタム アプリセットアップ ポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ac34-131">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="5ac34-132">ユーザーのカスタム アプリ ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="5ac34-132">Set a user custom app policy</span></span>

1. <span data-ttu-id="5ac34-133">Microsoft Teams 管理センターの左側のナビゲーションで **、Teams アプリのセットアップ** ポリシー  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="5ac34-133">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="5ac34-134">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ac34-134">Click **Add**.</span></span>
3. <span data-ttu-id="5ac34-135">カスタム アプリのアップロードを **オンまたはオフにします**。</span><span class="sxs-lookup"><span data-stu-id="5ac34-135">Turn on or turn off **Upload custom apps**.</span></span>
4. <span data-ttu-id="5ac34-136">ポリシーに必要なその他の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ac34-136">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="5ac34-137">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ac34-137">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="5ac34-138">チーム カスタム アプリの設定</span><span class="sxs-lookup"><span data-stu-id="5ac34-138">Team custom app setting</span></span>

<span data-ttu-id="5ac34-139">管理者とチーム所有者は、チームでカスタム アプリの追加を許可するかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-139">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="5ac34-140">この設定では、 **カスタム アプリ** のアップロードをメンバーに許可し、ユーザーのカスタム アプリ ポリシーと共に、特定のチームにカスタム アプリを追加できるユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="5ac34-140">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="5ac34-141">この設定がオフになっている場合:</span><span class="sxs-lookup"><span data-stu-id="5ac34-141">If this setting is turned off:</span></span>

- <span data-ttu-id="5ac34-142">カスタム アプリ ポリシーで許可されている場合、チーム所有者はカスタム アプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-142">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="5ac34-143">チーム所有者ではないチーム メンバーは、チームにカスタム アプリを追加できない。</span><span class="sxs-lookup"><span data-stu-id="5ac34-143">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="5ac34-144">この設定がオンになっている場合:</span><span class="sxs-lookup"><span data-stu-id="5ac34-144">If this setting is turned on:</span></span>

- <span data-ttu-id="5ac34-145">カスタム アプリ ポリシーで許可されている場合、チーム所有者はカスタム アプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-145">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="5ac34-146">チーム所有者ではないチーム メンバーは、カスタム アプリ ポリシーで許可されている場合、カスタム アプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-146">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="5ac34-147">チームのカスタム アプリ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="5ac34-147">Configure the team custom app setting</span></span>

1. <span data-ttu-id="5ac34-148">Teams でチームに移動し、[その他のオプション **] をクリックします。**  >  </span><span class="sxs-lookup"><span data-stu-id="5ac34-148">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="5ac34-149">[設定 **] を** クリックし、[メンバーのアクセス **許可] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="5ac34-149">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="5ac34-150">[カスタム アプリのアップロードを **メンバーに許可する] チェック ボックスをオンまたは** オフにします。</span><span class="sxs-lookup"><span data-stu-id="5ac34-150">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![チームのカスタム アプリの設定を示すスクリーンショット](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="5ac34-152">組織全体のカスタム アプリ設定</span><span class="sxs-lookup"><span data-stu-id="5ac34-152">Org-wide custom app setting</span></span>

<span data-ttu-id="5ac34-153">[**アプリの管理**] ページの [カスタム アプリの [](manage-apps.md)組織全体のカスタム アプリの操作を許可する] 設定は、組織内のすべてのユーザーに適用され、カスタム アプリをアップロードまたは操作できるかどうかが適用されます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-153">The **Allow interaction with custom apps** org-wide custom app setting on the [Manage apps](manage-apps.md) page applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="5ac34-154">この設定は、ユーザーとチームのカスタム アプリ ポリシー設定のマスター オン/オフ スイッチとして機能します。</span><span class="sxs-lookup"><span data-stu-id="5ac34-154">This setting acts as a master on/off switch for the user and team custom app policy settings.</span></span> <span data-ttu-id="5ac34-155">これは、セキュリティ イベント中にマスターのオン/オフ スイッチとして機能することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="5ac34-155">It's intended to serve as a master on/off switch during security events.</span></span> <span data-ttu-id="5ac34-156">そのため、ユーザーとチームのカスタム アプリ ポリシー設定が有効になっている場合でも、組織全体のカスタム アプリ設定が有効になっていない限り、ユーザーとチームのカスタム アプリ ポリシー設定は有効になりません。</span><span class="sxs-lookup"><span data-stu-id="5ac34-156">As such, user and team custom app policy settings will not take effect unless the org-wide custom app setting is enabled even if user and team custom app policy settings are enabled.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="5ac34-157">組織全体のカスタム アプリ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="5ac34-157">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="5ac34-158">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="5ac34-158">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="5ac34-159">[組織 **全体のアプリ設定] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5ac34-159">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="5ac34-160">[ **カスタム アプリ] で**、カスタム アプリとの対話を **許可する機能をオンまたはオフにします**。</span><span class="sxs-lookup"><span data-stu-id="5ac34-160">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![組織全体のカスタム アプリ設定を示すスクリーンショット](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="5ac34-162">カスタム アプリのポリシーと設定の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="5ac34-162">How custom app policies and settings work together</span></span>

<span data-ttu-id="5ac34-163">次の表は、カスタム アプリのポリシーと設定、アプリの組み合わせ方法、および組織内でカスタム アプリを Teams にアップロードできるユーザーの制御に対する組み合わせ効果をまとめた一覧です。</span><span class="sxs-lookup"><span data-stu-id="5ac34-163">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="5ac34-164">たとえば、チーム所有者だけがカスタム アプリを特定のチームにアップロードできるとします。</span><span class="sxs-lookup"><span data-stu-id="5ac34-164">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="5ac34-165">次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="5ac34-165">You would set the following:</span></span>
- <span data-ttu-id="5ac34-166">Microsoft Teams 管理 **センターで、[カスタム アプリの** 操作を許可する] 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="5ac34-166">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="5ac34-167">アクセスを制限 **するチームごとに、カスタム アプリ** のアップロードをメンバーに許可する機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="5ac34-167">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="5ac34-168">[カスタム アプリのアップロード] 設定をオンにした状態で、Microsoft Teams 管理センターでカスタム アプリセットアップ ポリシーを作成して割り当て、チームの所有者に割り当てる。 </span><span class="sxs-lookup"><span data-stu-id="5ac34-168">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **Upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="5ac34-169">組織全体のカスタム アプリ設定</span><span class="sxs-lookup"><span data-stu-id="5ac34-169">Org-wide custom app setting</span></span> |<span data-ttu-id="5ac34-170">チーム カスタム アプリの設定</span><span class="sxs-lookup"><span data-stu-id="5ac34-170">Team custom app setting</span></span> |<span data-ttu-id="5ac34-171">ユーザー カスタム アプリ ポリシー</span><span class="sxs-lookup"><span data-stu-id="5ac34-171">User custom app policy</span></span> |<span data-ttu-id="5ac34-172">効果</span><span class="sxs-lookup"><span data-stu-id="5ac34-172">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="5ac34-173">オフ</span><span class="sxs-lookup"><span data-stu-id="5ac34-173">Off</span></span>    | <span data-ttu-id="5ac34-174">オフ</span><span class="sxs-lookup"><span data-stu-id="5ac34-174">Off</span></span>    | <span data-ttu-id="5ac34-175">オフ</span><span class="sxs-lookup"><span data-stu-id="5ac34-175">Off</span></span>     |<span data-ttu-id="5ac34-176">組織では、すべてのカスタム アプリの操作がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-176">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="5ac34-177">カスタム アプリは、Teams サービス管理者またはグローバル管理者以外のユーザーがアップロードできません。PowerShell を使用してカスタム アプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-177">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="5ac34-178">オフ</span><span class="sxs-lookup"><span data-stu-id="5ac34-178">Off</span></span>     | <span data-ttu-id="5ac34-179">オフ</span><span class="sxs-lookup"><span data-stu-id="5ac34-179">Off</span></span>     | <span data-ttu-id="5ac34-180">オン</span><span class="sxs-lookup"><span data-stu-id="5ac34-180">On</span></span>        |<span data-ttu-id="5ac34-181">組織では、すべてのカスタム アプリの操作がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-181">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="5ac34-182">カスタム アプリは、Teams サービス管理者またはグローバル管理者以外のユーザーがアップロードできません。PowerShell を使用してカスタム アプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-182">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="5ac34-183">オフ</span><span class="sxs-lookup"><span data-stu-id="5ac34-183">Off</span></span>    | <span data-ttu-id="5ac34-184">オン</span><span class="sxs-lookup"><span data-stu-id="5ac34-184">On</span></span>        | <span data-ttu-id="5ac34-185">オフ</span><span class="sxs-lookup"><span data-stu-id="5ac34-185">Off</span></span>        |<span data-ttu-id="5ac34-186">組織では、すべてのカスタム アプリの操作がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-186">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="5ac34-187">カスタム アプリは、Teams サービス管理者またはグローバル管理者以外のユーザーがアップロードできません。カスタム アプリをWindows PowerShellアプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-187">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="5ac34-188">オフ</span><span class="sxs-lookup"><span data-stu-id="5ac34-188">Off</span></span>    | <span data-ttu-id="5ac34-189">オン</span><span class="sxs-lookup"><span data-stu-id="5ac34-189">On</span></span>      | <span data-ttu-id="5ac34-190">オン</span><span class="sxs-lookup"><span data-stu-id="5ac34-190">On</span></span>       |<span data-ttu-id="5ac34-191">組織では、すべてのカスタム アプリの操作がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-191">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="5ac34-192">カスタム アプリは、Teams サービス管理者またはグローバル管理者以外のユーザーがアップロードできません。PowerShell を使用してカスタム アプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-192">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="5ac34-193">オン</span><span class="sxs-lookup"><span data-stu-id="5ac34-193">On</span></span>    | <span data-ttu-id="5ac34-194">オフ</span><span class="sxs-lookup"><span data-stu-id="5ac34-194">Off</span></span>       | <span data-ttu-id="5ac34-195">オフ</span><span class="sxs-lookup"><span data-stu-id="5ac34-195">Off</span></span>         |  <span data-ttu-id="5ac34-196">ユーザーがカスタム アプリをアップロードできない。</span><span class="sxs-lookup"><span data-stu-id="5ac34-196">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="5ac34-197">オン</span><span class="sxs-lookup"><span data-stu-id="5ac34-197">On</span></span>     | <span data-ttu-id="5ac34-198">オフ</span><span class="sxs-lookup"><span data-stu-id="5ac34-198">Off</span></span>       | <span data-ttu-id="5ac34-199">オン</span><span class="sxs-lookup"><span data-stu-id="5ac34-199">On</span></span>         | <span data-ttu-id="5ac34-200">ユーザーがチーム所有者である場合は、カスタム アプリをチームにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-200">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="5ac34-201">ユーザーがチーム所有者ではない場合、カスタム アプリをチームにアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5ac34-201">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="5ac34-202">ユーザーは、個人用コンテキストでカスタム アプリをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-202">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="5ac34-203">オン</span><span class="sxs-lookup"><span data-stu-id="5ac34-203">On</span></span>     | <span data-ttu-id="5ac34-204">オン</span><span class="sxs-lookup"><span data-stu-id="5ac34-204">On</span></span>     | <span data-ttu-id="5ac34-205">オフ</span><span class="sxs-lookup"><span data-stu-id="5ac34-205">Off</span></span>         | <span data-ttu-id="5ac34-206">ユーザーがカスタム アプリをアップロードできない。</span><span class="sxs-lookup"><span data-stu-id="5ac34-206">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="5ac34-207">オン</span><span class="sxs-lookup"><span data-stu-id="5ac34-207">On</span></span>    | <span data-ttu-id="5ac34-208">オン</span><span class="sxs-lookup"><span data-stu-id="5ac34-208">On</span></span>        | <span data-ttu-id="5ac34-209">オン</span><span class="sxs-lookup"><span data-stu-id="5ac34-209">On</span></span>        | <span data-ttu-id="5ac34-210">ユーザーがチーム所有者かどうかに関係なく、ユーザーはカスタム アプリをチームにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-210">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="5ac34-211">ユーザーは、個人用コンテキストでカスタム アプリをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="5ac34-211">The user can upload custom apps in the personal context.</span></span>       |

## <a name="related-topics"></a><span data-ttu-id="5ac34-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ac34-212">Related topics</span></span>
 
[<span data-ttu-id="5ac34-213">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="5ac34-213">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="5ac34-214"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5ac34-214">Assign policies to your users in Teams</span></span>](assign-policies.md)