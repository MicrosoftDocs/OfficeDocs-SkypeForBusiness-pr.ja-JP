---
title: 共存およびアップグレードの設定
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 組織内のすべてのユーザー、または組織内の 1 人または一連のユーザーの共存とアップグレードの設定を一度に設定する方法について学習します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e7559b5376f6b386132e7814b88b6fcce3f5b378
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282724"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="8e17b-103">共存およびアップグレードの設定</span><span class="sxs-lookup"><span data-stu-id="8e17b-103">Set your coexistence and upgrade settings</span></span>


<span data-ttu-id="8e17b-104">Teams を使用するように Skype for Business ユーザーをアップグレードする場合、ユーザーにとってシームレスなプロセスにするためのオプションがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="8e17b-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="8e17b-105">組織内のすべてのユーザーの共存とアップグレードの設定を一度に行うオプションがあります。また、組織内の 1 人または複数のユーザーの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e17b-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="8e17b-106">以前のバージョンの Skype for Business クライアントでは、これらの設定が優先されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="8e17b-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="8e17b-107">Skype for Business クライアント バージョンの詳細については、「[Skype for Business のダウンロードと更新プログラム](/skypeforbusiness/software-updates)」ページ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e17b-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="8e17b-108">「Understanding Microsoft Teams and [Skype for Business coexistence](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and interoperability or Coexistence with Skype for Business 」を参照して、使用できるモードについて理解[を深Skype for Business。](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="8e17b-108">You can get a better understanding of the modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="8e17b-109">組織内のすべてのユーザーに対するアップグレード オプションの設定</span><span class="sxs-lookup"><span data-stu-id="8e17b-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="8e17b-110">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="8e17b-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="8e17b-111">[Microsoft Teams [管理センター]](https://admin.teams.microsoft.com/)の左側のナビゲーションで、[アップグレード] の [**組織** 全体の設定  >  **] にTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="8e17b-111">In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), in the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="8e17b-112">[アップグレード] ページの **Teams、** 必要に応じて次のオプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-112">At the top of the **Teams upgrade** page, modify the following options as desired.</span></span>
    - <span data-ttu-id="8e17b-113">[**共存**] モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="8e17b-114">**アイランド** - ユーザーが Skype for Business と Teams の両方を同時に使用できるようにする場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="8e17b-115">**Skype for Business のみ** - ユーザーが Skype for Business のみを使用する場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="8e17b-116">**Skype for Business と Teams のコラボレーション** - グループ コラボレーション (チャネル) に Teams を使用するだけでなく、Skype for Business も使用する場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-116">**Skype for Business with Teams collaboration** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
        - <span data-ttu-id="8e17b-117">**Skype for Business と Teams のコラボレーションと会議** - グループ コラボレーション (チャネル) と会議に Teams を使用するだけでなく、Skype for Business も使用する場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-117">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
        - <span data-ttu-id="8e17b-118">**Teamsのみ**- この設定は、ユーザーが他のユーザーのみを使用する場合Teams。</span><span class="sxs-lookup"><span data-stu-id="8e17b-118">**Teams only** - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="8e17b-119">この設定を使用しても、Skype for Business でホストされている会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="8e17b-119">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
        
    - <span data-ttu-id="8e17b-120">[**Skype for Business ユーザーに Teams へのアップグレードが利用できることを通知します**] を設定します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-120">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="8e17b-121">このオプションをオンにすると、Skype for Business ユーザーに間もなく Teams アプリにアップグレードされることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="8e17b-121">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="8e17b-122">[**Skype for Business 会議に参加するユーザー向けの優先アプリ**] を設定します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-122">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="8e17b-123">この設定では、Skype for Business 会議に参加するために使用されるアプリが決定され、共存モードの値に関係なく、適用されます。</span><span class="sxs-lookup"><span data-stu-id="8e17b-123">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="8e17b-124">**Skype 会議アプリ**</span><span class="sxs-lookup"><span data-stu-id="8e17b-124">**Skype Meetings app**</span></span>
      - <span data-ttu-id="8e17b-125">**機能が制限されている Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="8e17b-125">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="8e17b-126">[**Skype for Business 向けにバックグラウンドで Teams アプリをダウンロードする**] かどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-126">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="8e17b-127">この設定は、Windows 上で Skype for Business を実行しているユーザー向けに、自動的に Teams アプリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8e17b-127">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="8e17b-128">これは、ユーザーの共存モードが Teams のみになっているか、保留中のアップグレードの通知が Skype for Business アプリで有効になっている場合、適用されます。</span><span class="sxs-lookup"><span data-stu-id="8e17b-128">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="8e17b-129">変更を完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e17b-129">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="8e17b-130">組織内の 1 人のユーザーに対するアップグレード オプションの設定</span><span class="sxs-lookup"><span data-stu-id="8e17b-130">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="8e17b-131">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="8e17b-131">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="8e17b-132">左側のナビゲーションで、[**ユーザー**] に移動し、リストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-132">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="8e17b-133">ユーザーの [**アカウント**] タブで、[**Teams アップグレード**] にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e17b-133">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="8e17b-134">[**共存**] モードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8e17b-134">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="8e17b-135">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-135">Choose from the following options:</span></span>
     - <span data-ttu-id="8e17b-136">**組織全体の設定を使用する** - ユーザーが **組織全体** の設定の設定を使用する場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-136">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="8e17b-137">**アイランド** - ユーザーが Skype for Business と Teams の両方を使用できるようにする場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-137">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="8e17b-138">**Skype for Business のみ** - ユーザーが Skype for Business を使用する場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-138">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span>
     - <span data-ttu-id="8e17b-139">**Skype for Business と Teams のコラボレーション** - グループ コラボレーション (チャネル) に Teams を使用するだけでなく、Skype for Business も使用する場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-139">**Skype for Business with Teams collaboration** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
      - <span data-ttu-id="8e17b-140">**Skype for Business と Teams のコラボレーションと会議** - グループ コラボレーション (チャネル) と会議に Teams を使用するだけでなく、Skype for Business も使用する場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-140">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
     - <span data-ttu-id="8e17b-141">**Teams のみ** - ユーザーが Teams のみを使用する場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e17b-141">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="8e17b-142">ユーザーは引き続き Skype for Business 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="8e17b-142">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="8e17b-143">[**組織全体の設定を使用する**] 以外の [**共存モード**] を選択した場合、ユーザーの Skype for Business アプリで Teams へのアップグレードが間もなく開始されるという通知を有効にするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8e17b-143">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="8e17b-144">ユーザーに対してこの通知を有効にするには、[**Skype for Business ユーザーに通知する**] オプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8e17b-144">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="8e17b-145">変更を完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e17b-145">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="8e17b-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e17b-146">Related topics</span></span>
[<span data-ttu-id="8e17b-147">行程を計画する</span><span class="sxs-lookup"><span data-stu-id="8e17b-147">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="8e17b-148">Skype for Business と Teams の共存とアップグレードの行程について理解する</span><span class="sxs-lookup"><span data-stu-id="8e17b-148">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="8e17b-149">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="8e17b-149">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)