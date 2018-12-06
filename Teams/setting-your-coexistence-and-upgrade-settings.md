---
title: 共存およびアップグレードを設定する
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: bjwhalen
search.appverid: MET150
description: 共存モードを選択し、他の共存の設定を設定するには、この資料が役立ちます。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb2e7ba5f854c392d86006fdb6bd313b3fd87c68
ms.sourcegitcommit: 969a71ef0ac0030c27bd2455c3bf9d536dbcd752
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2018
ms.locfileid: "27182456"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="eca6a-103">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="eca6a-103">Setting your coexistence and upgrade settings</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="eca6a-104">チームを使用するビジネス ユーザー向けに、Skype をアップグレードするとき、ユーザーにシームレスなプロセスにするためのいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="eca6a-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="eca6a-105">共存し、組織内のユーザーのすべての設定をアップグレードするためのオプションがあるか、組織内の 1 つまたは一連のユーザー設定の変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="eca6a-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="eca6a-106">Skype のビジネス クライアント用の以前のバージョンがこれらの設定を無視可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="eca6a-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="eca6a-107">ビジネス クライアントのバージョンの Skype の詳細については[ビジネスの Skype がダウンロードされページの更新](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eca6a-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="eca6a-108">[マイクロソフト チームの理解とビジネスの共存と相互運用性の Skype](teams-and-skypeforbusiness-coexistence-and-interoperability.md)または[Skype のビジネスとの共存](coexistence-chat-calls-presence.md)を参照して使用するモードの種類の理解を深めるを取得できます。</span><span class="sxs-lookup"><span data-stu-id="eca6a-108">You can get a better understanding of the types of modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="eca6a-109">組織内のすべてのユーザーのアップグレード ・ オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="eca6a-110">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="eca6a-110">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams & Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="eca6a-111">左側のナビゲーションでは、**組織全体の設定**に移動 > **のチームをアップグレード**します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-111">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="eca6a-112">**チームのアップグレード**] ページの上部には、次の変更する場合にも使用する場合。</span><span class="sxs-lookup"><span data-stu-id="eca6a-112">At the top of the **Teams upgrade** page, make the following changes if they will work for you.</span></span>
    - <span data-ttu-id="eca6a-113">**共存**モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="eca6a-114">**島**のビジネスとチームの両方の Skype を同時に使用できるようにする場合、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="eca6a-115">**ビジネスのみの Skype**の使用する場合は、ユーザーにのみ、この設定は、ビジネスの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="eca6a-116">**チームのみ**(プレビューでいくつかの組織) のユーザーがチームのみを使用する場合、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-116">**Teams only** (in preview for some organizations) - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="eca6a-117">であっても、この設定でユーザー参加できますビジネス用の Skype でホストされている会議に注意してください。</span><span class="sxs-lookup"><span data-stu-id="eca6a-117">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
    - <span data-ttu-id="eca6a-118">**Skype チームが使用可能にアップグレードするため、ビジネス ユーザー向けに通知**を設定します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-118">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="eca6a-119">これをオンにする場合は分かります、Skype のビジネス ユーザーのことではすぐにアップグレードするチームのアプリケーションにします。</span><span class="sxs-lookup"><span data-stu-id="eca6a-119">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="eca6a-120">**Skype のビジネス ・ ミーティングに参加するユーザーのアプリケーションを優先**に設定します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-120">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="eca6a-121">この設定では、Skype のビジネス ・ ミーティングに参加するためにアプリケーションが使用されるかを決定し、共存モードの値に関係なく受取済です。</span><span class="sxs-lookup"><span data-stu-id="eca6a-121">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="eca6a-122">**Skype 会議アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="eca6a-122">**Skype Meetings app**</span></span>
      - <span data-ttu-id="eca6a-123">**限られた機能とビジネスの Skype**</span><span class="sxs-lookup"><span data-stu-id="eca6a-123">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="eca6a-124">**ビジネス ユーザー向け Skype をバック グラウンドでチームのアプリケーションをダウンロード**するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-124">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="eca6a-125">この設定は、Windows 上でビジネス用の Skype を実行しているユーザーのチームのアプリケーションをサイレント モードでダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="eca6a-125">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="eca6a-126">ビジネス用の Skype での保留中のアップグレードの通知が有効になっている場合またはユーザーの共存モードは、チームのみの場合にのみ受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="eca6a-126">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="eca6a-127">変更を加えた後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eca6a-127">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="eca6a-128">組織内の 1 人のユーザーのアップグレード ・ オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-128">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="eca6a-129">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="eca6a-129">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams & Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="eca6a-130">左側のナビゲーションでは、**ユーザー**に移動し、一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-130">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="eca6a-131">**チームのアップグレード**をするには、[ユーザー**アカウント**] タブで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eca6a-131">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="eca6a-132">**共存モード**を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="eca6a-132">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="eca6a-133">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-133">Choose from the following options:</span></span>
     - <span data-ttu-id="eca6a-134">**使用して組織全体の設定**- ユーザーが**組織全体**の設定の設定を使用する場合、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-134">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="eca6a-135">**島**のビジネスとチームの両方の Skype を使用できるユーザーの場合、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-135">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="eca6a-136">**Skype のみのビジネス**- ビジネスの Skype を使用するユーザーの場合、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-136">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span> 
     - <span data-ttu-id="eca6a-137">だけチームが**チームのみ**のユーザーを使用する場合、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-137">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="eca6a-138">ユーザーは Skype をビジネス ・ ミーティングに参加できます。</span><span class="sxs-lookup"><span data-stu-id="eca6a-138">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="eca6a-139">**使用して組織全体の設定**以外の**共存モード**を選択する場合は、ビジネス アプリケーションをチームへのアップグレードの準備中で Skype のユーザーの通知を有効にするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="eca6a-139">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="eca6a-140">ユーザーの通知を有効にするには、**ビジネス ユーザーの Skype の通知**オプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="eca6a-140">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="eca6a-141">変更を加えた後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eca6a-141">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="eca6a-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="eca6a-142">Related topics</span></span>
[<span data-ttu-id="eca6a-143">旅を計画します。</span><span class="sxs-lookup"><span data-stu-id="eca6a-143">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="eca6a-144">共存を理解し、Skype のビジネスとチームの旅をアップグレード</span><span class="sxs-lookup"><span data-stu-id="eca6a-144">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="eca6a-145">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="eca6a-145">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)
