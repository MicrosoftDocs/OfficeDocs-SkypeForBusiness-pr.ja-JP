---
title: 共存およびアップグレードを設定する
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: この記事では、共存モードを選択し、その他の共存設定を設定する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 674c4c43e1fe99639c6e8bfd9665e1bf0755e1ba
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069378"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="24b08-103">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="24b08-103">Setting your coexistence and upgrade settings</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="24b08-104">Skype for Business ユーザーをアップグレードして Teams を使用する場合、ユーザーのためのシームレスなプロセスを実現するためのいくつかのオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="24b08-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="24b08-105">組織内のすべてのユーザーに対して共存とアップグレードの設定を同時に行うことができます。または、組織内の1人または複数のユーザーの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="24b08-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="24b08-106">以前のバージョンの Skype for Business クライアントでは、これらの設定が認められない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="24b08-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="24b08-107">Skype for Business クライアントのバージョンの詳細については、「 [skype For business のダウンロードと更新プログラム」ページ](https://docs.microsoft.com/skypeforbusiness/software-updates)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24b08-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](https://docs.microsoft.com/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="24b08-108">[Microsoft Teams と skype For business の共存と](teams-and-skypeforbusiness-coexistence-and-interoperability.md)、skype for business との相互運用性や[共存](coexistence-chat-calls-presence.md)について理解しておくと、利用できるモードの種類をより深く理解できます。</span><span class="sxs-lookup"><span data-stu-id="24b08-108">You can get a better understanding of the types of modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="24b08-109">組織内のすべてのユーザーに対してアップグレードオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="24b08-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="24b08-110">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="24b08-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="24b08-111">左側のナビゲーションで、[**組織全体の設定** > ]**チームのアップグレード**に移動します。</span><span class="sxs-lookup"><span data-stu-id="24b08-111">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="24b08-112">**チームのアップグレード**ページの上部で、次のような変更を行う場合は、次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="24b08-112">At the top of the **Teams upgrade** page, make the following changes if they will work for you.</span></span>
    - <span data-ttu-id="24b08-113">**共存**モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="24b08-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="24b08-114">[**諸島**]: ユーザーが Skype for Business と Teams の両方を同時に使用できるようにする場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="24b08-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="24b08-115">**Skype For business のみ**-ユーザーが Skype for business のみを使用できるようにする場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="24b08-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="24b08-116">**チーム**グループ作業での Skype for business-グループコラボレーション (チャネル) で teams を使用することに加えて、ユーザーが Skype for business を使用できるようにする場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="24b08-116">**Skype for Business with Teams collaboration** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
        - <span data-ttu-id="24b08-117">**チームのコラボレーションと会議を使用した skype For business** : グループコラボレーション (チャネル) および teams 会議にチームを使用するだけでなく、ユーザーが Skype for business を使用できるようにする場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="24b08-117">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
        - <span data-ttu-id="24b08-118">**チームのみ**(一部の組織のプレビュー) では、ユーザーが teams のみを使用できるようにする場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="24b08-118">**Teams only** (in preview for some organizations) - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="24b08-119">この設定でも、ユーザーは Skype for Business でホストされている会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="24b08-119">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
    - <span data-ttu-id="24b08-120">**チームがアップグレード可能であることを Skype For business ユーザーに通知するよう**に設定します。</span><span class="sxs-lookup"><span data-stu-id="24b08-120">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="24b08-121">この設定を有効にすると、Skype for Business ユーザーに対して、チームアプリへのアップグレードが間もなく行われることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="24b08-121">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="24b08-122">**ユーザーが Skype For business 会議に参加するための優先アプリを**設定します。</span><span class="sxs-lookup"><span data-stu-id="24b08-122">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="24b08-123">この設定では、Skype for Business 会議に参加するために使用するアプリを決定し、[共存] モードの値に関係なく有効になります。</span><span class="sxs-lookup"><span data-stu-id="24b08-123">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="24b08-124">**Skype 会議アプリ**</span><span class="sxs-lookup"><span data-stu-id="24b08-124">**Skype Meetings app**</span></span>
      - <span data-ttu-id="24b08-125">**機能が限定された Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="24b08-125">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="24b08-126">**Skype For business ユーザーのバックグラウンドで Teams アプリをダウンロード**するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="24b08-126">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="24b08-127">この設定により、Windows で Skype for Business を実行しているユーザーの Teams アプリが自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="24b08-127">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="24b08-128">この機能は、ユーザーの共存モードが Teams のみの場合、または Skype for Business で保留中のアップグレードの通知が有効になっている場合にのみ受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="24b08-128">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="24b08-129">変更を加えた後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24b08-129">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="24b08-130">組織内の1人のユーザーに対してアップグレードオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="24b08-130">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="24b08-131">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="24b08-131">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="24b08-132">左側のナビゲーションで [**ユーザー**] に移動し、リストからユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="24b08-132">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="24b08-133">ユーザーの [**アカウント**] タブで、[**チームのアップグレード**] の下の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24b08-133">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="24b08-134">**共存モード**を設定できます。</span><span class="sxs-lookup"><span data-stu-id="24b08-134">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="24b08-135">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="24b08-135">Choose from the following options:</span></span>
     - <span data-ttu-id="24b08-136">[**組織全体の設定を使用**する]: ユーザーが**組織全体**の設定の設定を使用する場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="24b08-136">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="24b08-137">[**諸島**]: ユーザーが Skype for Business と Teams の両方を使用できるようにする場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="24b08-137">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="24b08-138">**Skype For business のみ**-ユーザーが Skype for business を使用できるようにする場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="24b08-138">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span>
     - <span data-ttu-id="24b08-139">**チーム**グループ作業での Skype for business-グループコラボレーション (チャネル) で teams を使用することに加えて、ユーザーが Skype for business を使用できるようにする場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="24b08-139">**Skype for Business with Teams collaboration** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
      - <span data-ttu-id="24b08-140">**チームでの共同作業と会議**を行った Skype for business-グループコラボレーション (チャネル) および teams 会議にチームを使用するだけでなく、ユーザーが Skype for business を使用できるようにする場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="24b08-140">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
     - <span data-ttu-id="24b08-141">[**チームのみ**]-ユーザーが Teams のみを使用できるようにする場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="24b08-141">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="24b08-142">ユーザーは、引き続き Skype for Business 会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="24b08-142">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="24b08-143">[**組織全体の設定を使用**しない] を選択した場合、ユーザーの Skype for business アプリ**で、Teams**にアップグレードした通知を有効にするオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24b08-143">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="24b08-144">ユーザーに対してこの通知を有効にするには、[ **Skype For business ユーザーに通知**する] オプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="24b08-144">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="24b08-145">変更を加えた後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24b08-145">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="24b08-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="24b08-146">Related topics</span></span>
[<span data-ttu-id="24b08-147">旅を計画する</span><span class="sxs-lookup"><span data-stu-id="24b08-147">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="24b08-148">Skype for Business および Teams の共存とアップグレードの過程を理解する</span><span class="sxs-lookup"><span data-stu-id="24b08-148">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="24b08-149">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="24b08-149">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)
