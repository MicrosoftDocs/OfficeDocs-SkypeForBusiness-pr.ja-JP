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
ms.openlocfilehash: ce472ca1c5307dd8a5573ca076c58e32e2d41df9
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "37571526"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="7f902-103">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="7f902-103">Setting your coexistence and upgrade settings</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="7f902-104">Skype for Business ユーザーをアップグレードして Teams を使用する場合、ユーザーのためのシームレスなプロセスを実現するためのいくつかのオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7f902-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="7f902-105">組織内のすべてのユーザーに対して共存とアップグレードの設定を同時に行うことができます。または、組織内の1人または複数のユーザーの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f902-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="7f902-106">以前のバージョンの Skype for Business クライアントでは、これらの設定が認められない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7f902-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="7f902-107">Skype for Business クライアントのバージョンの詳細については、「 [skype For business のダウンロードと更新プログラム」ページ](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f902-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="7f902-108">[Microsoft Teams と skype For business の共存と](teams-and-skypeforbusiness-coexistence-and-interoperability.md)、skype for business との相互運用性や[共存](coexistence-chat-calls-presence.md)について理解しておくと、利用できるモードの種類をより深く理解できます。</span><span class="sxs-lookup"><span data-stu-id="7f902-108">You can get a better understanding of the types of modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="7f902-109">組織内のすべてのユーザーに対してアップグレードオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="7f902-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="7f902-110">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="7f902-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7f902-111">左側のナビゲーションで、[**組織全体の設定** > ]**チームのアップグレード**に移動します。</span><span class="sxs-lookup"><span data-stu-id="7f902-111">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="7f902-112">**チームのアップグレード**ページの上部で、次のような変更を行う場合は、次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="7f902-112">At the top of the **Teams upgrade** page, make the following changes if they will work for you.</span></span>
    - <span data-ttu-id="7f902-113">**共存**モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="7f902-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="7f902-114">[**諸島**]: ユーザーが Skype for Business と Teams の両方を同時に使用できるようにする場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="7f902-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="7f902-115">**Skype For business のみ**-ユーザーが Skype for business のみを使用できるようにする場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="7f902-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="7f902-116">**チームのみ**(一部の組織のプレビュー) では、ユーザーが teams のみを使用できるようにする場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="7f902-116">**Teams only** (in preview for some organizations) - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="7f902-117">この設定でも、ユーザーは Skype for Business でホストされている会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="7f902-117">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
    - <span data-ttu-id="7f902-118">**チームがアップグレード可能であることを Skype For business ユーザーに通知するよう**に設定します。</span><span class="sxs-lookup"><span data-stu-id="7f902-118">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="7f902-119">この設定を有効にすると、Skype for Business ユーザーに対して、チームアプリへのアップグレードが間もなく行われることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="7f902-119">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="7f902-120">**ユーザーが Skype For business 会議に参加するための優先アプリを**設定します。</span><span class="sxs-lookup"><span data-stu-id="7f902-120">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="7f902-121">この設定では、Skype for Business 会議に参加するために使用するアプリを決定し、[共存] モードの値に関係なく有効になります。</span><span class="sxs-lookup"><span data-stu-id="7f902-121">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="7f902-122">**Skype 会議アプリ**</span><span class="sxs-lookup"><span data-stu-id="7f902-122">**Skype Meetings app**</span></span>
      - <span data-ttu-id="7f902-123">**機能が限定された Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="7f902-123">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="7f902-124">**Skype For business ユーザーのバックグラウンドで Teams アプリをダウンロード**するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="7f902-124">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="7f902-125">この設定により、Windows で Skype for Business を実行しているユーザーの Teams アプリが自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="7f902-125">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="7f902-126">この機能は、ユーザーの共存モードが Teams のみの場合、または Skype for Business で保留中のアップグレードの通知が有効になっている場合にのみ受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="7f902-126">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="7f902-127">変更を加えた後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f902-127">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="7f902-128">組織内の1人のユーザーに対してアップグレードオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="7f902-128">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="7f902-129">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="7f902-129">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7f902-130">左側のナビゲーションで [**ユーザー**] に移動し、リストからユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="7f902-130">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="7f902-131">ユーザーの [**アカウント**] タブで、[**チームのアップグレード**] の下の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f902-131">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="7f902-132">**共存モード**を設定できます。</span><span class="sxs-lookup"><span data-stu-id="7f902-132">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="7f902-133">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="7f902-133">Choose from the following options:</span></span>
     - <span data-ttu-id="7f902-134">[**組織全体の設定を使用**する]: ユーザーが**組織全体**の設定の設定を使用する場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="7f902-134">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="7f902-135">[**諸島**]: ユーザーが Skype for Business と Teams の両方を使用できるようにする場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="7f902-135">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="7f902-136">**Skype For business のみ**-ユーザーが Skype for business を使用できるようにする場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="7f902-136">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span> 
     - <span data-ttu-id="7f902-137">[**チームのみ**]-ユーザーが Teams のみを使用できるようにする場合は、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="7f902-137">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="7f902-138">ユーザーは、引き続き Skype for Business 会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="7f902-138">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="7f902-139">[**組織全体の設定を使用**しない] を選択した場合、ユーザーの Skype for business アプリ**で、Teams**にアップグレードした通知を有効にするオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f902-139">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="7f902-140">ユーザーに対してこの通知を有効にするには、[ **Skype For business ユーザーに通知**する] オプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7f902-140">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="7f902-141">変更を加えた後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f902-141">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="7f902-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7f902-142">Related topics</span></span>
[<span data-ttu-id="7f902-143">旅を計画する</span><span class="sxs-lookup"><span data-stu-id="7f902-143">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="7f902-144">Skype for Business および Teams の共存とアップグレードの過程を理解する</span><span class="sxs-lookup"><span data-stu-id="7f902-144">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="7f902-145">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="7f902-145">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)
