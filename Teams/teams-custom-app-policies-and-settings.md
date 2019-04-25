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
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: カスタム アプリケーションのポリシーと、組織のマイクロソフトのチームでカスタム アプリケーションをアップロードできるユーザーを制御する設定を管理する方法について説明します。
ms.openlocfilehash: 3cbd517cdfe8066eebff0164457c8e2e3aa37a5d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32224631"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="ebf3b-103">Microsoft Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="ebf3b-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="ebf3b-104">管理者としては、カスタム アプリケーションのポリシーと、組織でマイクロソフトのチームに、カスタム アプリケーションをアップロードできるユーザーを制御する設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-104">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="ebf3b-105">管理者がカスタム アプリケーションをアップロードできるユーザーを決定し、管理者とチームの所有者は、組織内の特定のチームがそれらに追加するカスタム アプリケーションを許可するかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-105">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  

## <a name="overview-of-custom-apps"></a><span data-ttu-id="ebf3b-106">カスタム アプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="ebf3b-106">Overview of custom apps</span></span>

<span data-ttu-id="ebf3b-107">ユーザーは、チームに直接、または個人のコンテキストで、アプリケーション パッケージ (.zip ファイル) をアップロードすることで、チームにカスタム アプリケーションを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-107">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="ebf3b-108">これは、チームのアプリケーション ストアからアプリを追加する方法とは異なります。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-108">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="ebf3b-109">呼ばれる sideloading は、アプリケーション パッケージをアップロードすることでカスタム アプリケーションを追加するには、開発中は、広く配布する準備が整う前に、アプリケーションをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-109">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="ebf3b-110">内部使用のみのアプリケーションを作成およびチーム アプリケーション カタログ内のチームのアプリケーション ストアに送信することがなく、チームと共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-110">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![カスタム アプリケーションをアップロードします。](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="ebf3b-112">カスタム アプリケーションのポリシーと設定</span><span class="sxs-lookup"><span data-stu-id="ebf3b-112">Custom app policy and settings</span></span>

<span data-ttu-id="ebf3b-113">3 つのコンポーネントでは、チームにカスタム アプリケーションを追加できるカスタム アプリケーションをチーム細かい制御をすることをユーザーがアップロードできるかどうかを確認しにいるチームがカスタム アプリケーションを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-113">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="ebf3b-114">ユーザーのカスタム アプリケーションのポリシー</span><span class="sxs-lookup"><span data-stu-id="ebf3b-114">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="ebf3b-115">チームのカスタム アプリケーション設定</span><span class="sxs-lookup"><span data-stu-id="ebf3b-115">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="ebf3b-116">組織全体にわたるカスタム アプリケーション設定</span><span class="sxs-lookup"><span data-stu-id="ebf3b-116">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="ebf3b-117">これらの設定は、サード ・ パーティ製のアプリケーションをブロックする機能を影響しません。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-117">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="ebf3b-118">ユーザーのカスタム アプリケーションのポリシー</span><span class="sxs-lookup"><span data-stu-id="ebf3b-118">User custom app policy</span></span>

<span data-ttu-id="ebf3b-119">[アプリケーション設定のポリシー](teams-app-setup-policies.md)の一部として、管理者はチームにユーザーがカスタム アプリケーションをアップロードできるかどうか制御するポリシー設定、**カスタム アプリケーションのアップロードを許可する**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-119">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Allow uploading custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="ebf3b-120">場合はこの設定がオフになっています。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-120">If this setting is turned off:</span></span>

- <span data-ttu-id="ebf3b-121">ユーザーは、組織または個人のコンテキストで任意のチームにカスタム アプリケーションをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-121">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="ebf3b-122">ユーザーは、組織全体にわたるカスタムのアプリケーションの設定によって、カスタム アプリケーションと対話できます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-122">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="ebf3b-123">場合はこの設定がオンになっています。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-123">If this setting is turned on:</span></span>

- <span data-ttu-id="ebf3b-124">できるチームとチームの所有者は、組織全体にわたるカスタムのアプリケーションの設定によって異なりますが、ユーザーはカスタム アプリケーションをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-124">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="ebf3b-125">ユーザーは、個人のコンテキストに、カスタム アプリケーションをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-125">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="ebf3b-126">ユーザーは、組織全体にわたるカスタムのアプリケーションの設定によって、カスタム アプリケーションと対話できます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-126">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="ebf3b-127">ポリシーの設定、グローバル アプリケーション設定を使用するアプリケーションを含めるを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-127">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="ebf3b-128">チーム、組織内のユーザーのグループごとにカスタマイズする場合は、作成し、1 つまたは複数のカスタム アプリケーション設定のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-128">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="ebf3b-129">ユーザー アプリケーションのカスタム ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-129">Set a user custom app policy</span></span>

1. <span data-ttu-id="ebf3b-130">マイクロソフトのチーム管理センターの左側のナビゲーションで**チームのアプリケーション**に移動する > **のポリシーを設定**します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="ebf3b-131">**新しいポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-131">Select **New policy**.</span></span>
3. <span data-ttu-id="ebf3b-132">有効にするまたは**カスタム アプリケーションのアップロードを許可する**をオフにします。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-132">Turn on or turn off **Allow uploading custom apps**.</span></span>
4. <span data-ttu-id="ebf3b-133">ポリシーにするその他の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-133">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="ebf3b-134">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-134">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="ebf3b-135">チームのカスタム アプリケーション設定</span><span class="sxs-lookup"><span data-stu-id="ebf3b-135">Team custom app setting</span></span>

<span data-ttu-id="ebf3b-136">管理者とチームの所有者は、チームがそれに追加するカスタム アプリケーションをできるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-136">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="ebf3b-137">この設定は、**カスタム アプリケーションのアップロードを許可するメンバー**のユーザーのカスタム アプリケーションのポリシーとは、カスタム アプリケーションを特定のチームに追加できるユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-137">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="ebf3b-138">場合はこの設定がオフになっています。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-138">If this setting is turned off:</span></span>

- <span data-ttu-id="ebf3b-139">チームの所有者は、カスタム アプリケーションのポリシーで許可される場合、カスタム アプリケーションを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-139">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="ebf3b-140">チーム所有者のいないチーム メンバーは、チームにカスタム アプリケーションを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-140">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="ebf3b-141">場合はこの設定がオンになっています。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-141">If this setting is turned on:</span></span>

- <span data-ttu-id="ebf3b-142">チームの所有者は、カスタム アプリケーションのポリシーで許可されている場合、カスタム アプリケーションを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-142">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="ebf3b-143">チーム所有者のいないチーム メンバーは、カスタム アプリケーションのポリシーで許可されている場合、カスタム アプリケーションを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-143">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="ebf3b-144">チームのカスタム アプリケーション設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-144">Configure the team custom app setting</span></span>

1. <span data-ttu-id="ebf3b-145">チームで、チームに移動する、**複数のオプションの ˙˙˙**をクリックして > **チームを管理**します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-145">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="ebf3b-146">**の設定**] をクリックし、**メンバーのアクセスを許可**します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-146">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="ebf3b-147">選択、または**カスタム アプリケーションのアップロードを許可するメンバー** ] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-147">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![チームのカスタム アプリケーション設定](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="ebf3b-149">組織全体にわたるカスタム アプリケーション設定</span><span class="sxs-lookup"><span data-stu-id="ebf3b-149">Org-wide custom app setting</span></span>

<span data-ttu-id="ebf3b-150">カスタム アプリケーションを組織全体にわたる設定、**カスタム アプリケーションと相互作用を許可する**では、組織内のすべてのユーザーに適用され、アップロードまたはカスタム アプリケーションと対話できるようにするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-150">The org-wide custom app setting, **Allow interaction with custom apps**, applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="ebf3b-151">この設定は、ユーザーおよびチームのカスタム アプリケーションのポリシー設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-151">This setting overrides the user and team custom app policy and setting.</span></span> <span data-ttu-id="ebf3b-152">セキュリティ イベントの中でスイッチのオン/オフのマスターとして機能するためのものが。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-152">It's intended to serve as a master on/off switch during security events.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="ebf3b-153">組織全体にわたるカスタム アプリケーション設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-153">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="ebf3b-154">マイクロソフトのチーム管理センターの左側のナビゲーションで**チームのアプリケーション**に移動する > **のアクセス許可ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="ebf3b-155">**組織全体にわたるアプリケーションの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-155">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="ebf3b-156">**カスタム アプリケーション**では、[を有効にするまたは**カスタム アプリケーションと相互作用を許可する**をオフにします。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-156">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![組織全体にわたるカスタム アプリケーション設定](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="ebf3b-158">共同作業アプリケーションのカスタム ポリシーおよび設定方法</span><span class="sxs-lookup"><span data-stu-id="ebf3b-158">How custom app policies and settings work together</span></span>

<span data-ttu-id="ebf3b-159">このテーブルは、カスタム アプリケーションのポリシーと設定、間の連携、およびチームにカスタム アプリケーションをアップロードできる、組織内のユーザーを制御する方法の組み合わせの影響をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-159">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="ebf3b-160">たとえば、チームの所有者だけが特定のチームにカスタム アプリケーションをアップロードしたいとも言います。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-160">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="ebf3b-161">以下を設定します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-161">You would set the following:</span></span>
- <span data-ttu-id="ebf3b-162">マイクロソフトのチームの管理センターで**カスタム アプリケーションと相互作用を許可する**設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-162">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="ebf3b-163">**カスタム アプリケーションのアップロードを許可するメンバー**のアクセスを制限するすべてのチームをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-163">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="ebf3b-164">作成し、**ユーザーがカスタム アプリケーションをアップロードできる**設定がオンになって、マイクロソフトのチームの管理センターでカスタム アプリケーション設定のポリシーを割り当てると、チームの所有者に割り当てること。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-164">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **User can upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="ebf3b-165">組織全体にわたるカスタム アプリケーション設定</span><span class="sxs-lookup"><span data-stu-id="ebf3b-165">Org-wide custom app setting</span></span> |<span data-ttu-id="ebf3b-166">チームのカスタム アプリケーション設定</span><span class="sxs-lookup"><span data-stu-id="ebf3b-166">Team custom app setting</span></span> |<span data-ttu-id="ebf3b-167">ユーザーのカスタム アプリケーションのポリシー</span><span class="sxs-lookup"><span data-stu-id="ebf3b-167">User custom app policy</span></span> |<span data-ttu-id="ebf3b-168">効果</span><span class="sxs-lookup"><span data-stu-id="ebf3b-168">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="ebf3b-169">オフ</span><span class="sxs-lookup"><span data-stu-id="ebf3b-169">Off</span></span>    | <span data-ttu-id="ebf3b-170">オフ</span><span class="sxs-lookup"><span data-stu-id="ebf3b-170">Off</span></span>    | <span data-ttu-id="ebf3b-171">オフ</span><span class="sxs-lookup"><span data-stu-id="ebf3b-171">Off</span></span>     |<span data-ttu-id="ebf3b-172">組織のすべてのカスタム アプリケーションとの相互作用がブロックされています。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-172">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="ebf3b-173">カスタム アプリケーションは、すべてのユーザーがアップロードできません。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-173">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="ebf3b-174">PowerShell を使用すると、カスタム アプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-174">You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="ebf3b-175">オフ</span><span class="sxs-lookup"><span data-stu-id="ebf3b-175">Off</span></span>     | <span data-ttu-id="ebf3b-176">オフ</span><span class="sxs-lookup"><span data-stu-id="ebf3b-176">Off</span></span>     | <span data-ttu-id="ebf3b-177">オン</span><span class="sxs-lookup"><span data-stu-id="ebf3b-177">On</span></span>        |<span data-ttu-id="ebf3b-178">組織のすべてのカスタム アプリケーションとの相互作用がブロックされています。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-178">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="ebf3b-179">カスタム アプリケーションは、すべてのユーザーがアップロードできません。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-179">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="ebf3b-180">PowerShell を使用すると、カスタム アプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-180">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="ebf3b-181">オフ</span><span class="sxs-lookup"><span data-stu-id="ebf3b-181">Off</span></span>    | <span data-ttu-id="ebf3b-182">オン</span><span class="sxs-lookup"><span data-stu-id="ebf3b-182">On</span></span>        | <span data-ttu-id="ebf3b-183">オフ</span><span class="sxs-lookup"><span data-stu-id="ebf3b-183">Off</span></span>        |<span data-ttu-id="ebf3b-184">組織のすべてのカスタム アプリケーションとの相互作用がブロックされています。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-184">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="ebf3b-185">カスタム アプリケーションは、すべてのユーザーがアップロードできません。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-185">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="ebf3b-186">カスタム アプリケーションを削除するのには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-186">You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="ebf3b-187">オフ</span><span class="sxs-lookup"><span data-stu-id="ebf3b-187">Off</span></span>    | <span data-ttu-id="ebf3b-188">オン</span><span class="sxs-lookup"><span data-stu-id="ebf3b-188">On</span></span>      | <span data-ttu-id="ebf3b-189">オン</span><span class="sxs-lookup"><span data-stu-id="ebf3b-189">On</span></span>       |<span data-ttu-id="ebf3b-190">組織のすべてのカスタム アプリケーションとの相互作用がブロックされています。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-190">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="ebf3b-191">カスタム アプリケーションは、すべてのユーザーがアップロードできません。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-191">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="ebf3b-192">PowerShell を使用すると、カスタム アプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-192">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="ebf3b-193">オン</span><span class="sxs-lookup"><span data-stu-id="ebf3b-193">On</span></span>    | <span data-ttu-id="ebf3b-194">オフ</span><span class="sxs-lookup"><span data-stu-id="ebf3b-194">Off</span></span>       | <span data-ttu-id="ebf3b-195">オフ</span><span class="sxs-lookup"><span data-stu-id="ebf3b-195">Off</span></span>         |  <span data-ttu-id="ebf3b-196">ユーザーは、カスタム アプリケーションをアップロードできません。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-196">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="ebf3b-197">オン</span><span class="sxs-lookup"><span data-stu-id="ebf3b-197">On</span></span>     | <span data-ttu-id="ebf3b-198">オフ</span><span class="sxs-lookup"><span data-stu-id="ebf3b-198">Off</span></span>       | <span data-ttu-id="ebf3b-199">オン</span><span class="sxs-lookup"><span data-stu-id="ebf3b-199">On</span></span>         | <span data-ttu-id="ebf3b-200">ユーザーがチームのオーナーである場合は、チームにカスタム アプリケーション、アップロードできます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-200">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="ebf3b-201">場合は、ユーザーには、チームの所有者がいない場合は、カスタム アプリケーションをチーム、アップロードできません。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-201">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="ebf3b-202">ユーザーは、個人のコンテキストでカスタム アプリケーションをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-202">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="ebf3b-203">オン</span><span class="sxs-lookup"><span data-stu-id="ebf3b-203">On</span></span>     | <span data-ttu-id="ebf3b-204">オン</span><span class="sxs-lookup"><span data-stu-id="ebf3b-204">On</span></span>     | <span data-ttu-id="ebf3b-205">オフ</span><span class="sxs-lookup"><span data-stu-id="ebf3b-205">Off</span></span>         | <span data-ttu-id="ebf3b-206">ユーザーは、カスタム アプリケーションをアップロードできません。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-206">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="ebf3b-207">オン</span><span class="sxs-lookup"><span data-stu-id="ebf3b-207">On</span></span>    | <span data-ttu-id="ebf3b-208">オン</span><span class="sxs-lookup"><span data-stu-id="ebf3b-208">On</span></span>        | <span data-ttu-id="ebf3b-209">オン</span><span class="sxs-lookup"><span data-stu-id="ebf3b-209">On</span></span>        | <span data-ttu-id="ebf3b-210">ユーザーは、ユーザーがチームのオーナーであるかにかかわらず、チームに、カスタム アプリケーションをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-210">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="ebf3b-211">ユーザーは、個人のコンテキストでカスタム アプリケーションをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="ebf3b-211">The user can upload custom apps in the personal context.</span></span>       |

 ## <a name="related-topics"></a><span data-ttu-id="ebf3b-212">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ebf3b-212">Related topics</span></span>
- [<span data-ttu-id="ebf3b-213">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="ebf3b-213">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="ebf3b-214">Microsoft Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="ebf3b-214">Manage app setup policies in Microsoft Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="ebf3b-215">Microsoft Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="ebf3b-215">Manage app permission policies in Microsoft Teams</span></span>](teams-app-permission-policies.md)
