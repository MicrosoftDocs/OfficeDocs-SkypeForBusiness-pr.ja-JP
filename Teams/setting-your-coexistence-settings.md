---
title: 共存の設定
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: こうと、共存モードを選択し、他の共存の設定を設定します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: add6436d66c088d6ffa14867cc03268cb082f0b3
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="setting-your-coexistence-settings"></a><span data-ttu-id="78be6-103">共存の設定</span><span class="sxs-lookup"><span data-stu-id="78be6-103">Setting your coexistence settings</span></span>


> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<Intro text here>

[<span data-ttu-id="78be6-104">共存を理解し、Skype のビジネスとチームのモードをアップグレード</span><span class="sxs-lookup"><span data-stu-id="78be6-104">Understand coexistence and upgrade modes for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

## <a name="setting-your-upgrade-options-for-your-users"></a><span data-ttu-id="78be6-105">ユーザーのアップグレードのオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="78be6-105">Setting your upgrade options for your users</span></span>

<span data-ttu-id="78be6-106">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="78be6-106">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="78be6-107">左側のナビゲーションでは、**組織全体の設定**に移動 > **のチームをアップグレード**します。</span><span class="sxs-lookup"><span data-stu-id="78be6-107">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="78be6-108">**チームは、ページをアップグレード**] ページの上部には、次の変更する場合にも使用する場合。</span><span class="sxs-lookup"><span data-stu-id="78be6-108">At the top of the **Teams upgrade page** page, make the following changes if they will work for you.</span></span>
- <span data-ttu-id="78be6-109">**共存**モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="78be6-109">Set the **Coexistence** mode</span></span>
    - <span data-ttu-id="78be6-110">**島**- Skype のビジネスとチームを使用するいくつかのユーザーの一部のユーザーがある場合、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="78be6-110">**Islands** - use this setting when you have some users on Skype for Business and some users that use Teams.</span></span>
    - <span data-ttu-id="78be6-111">**ビジネスのみの Skype**の Skype をビジネス ユーザーにしかない場合、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="78be6-111">**Skype for Business only** - use this setting if you only have Skype for Business users.</span></span>
    - <span data-ttu-id="78be6-112">**チームのみ**のチームのユーザーのみがある場合、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="78be6-112">**Teams only** - use this setting if you only have Teams users.</span></span>
- <span data-ttu-id="78be6-113">設定**チームをビジネス ユーザー向けに通知 Skype はアップグレードのために使用します**。</span><span class="sxs-lookup"><span data-stu-id="78be6-113">Set **Notify Skype for Business users that Teams is available for upgrade.**</span></span>
    - <span data-ttu-id="78be6-114">これをオンにする場合は、チームのアプリケーションをアップグレードすることがビジネス ユーザー向け Skype が送信されます。</span><span class="sxs-lookup"><span data-stu-id="78be6-114">If you turn this on, it will tell the Skype for Business users that they can upgrade to the Teams app.</span></span>
- <span data-ttu-id="78be6-115">この設定を調べ、どのアプリ Skype のビジネス ・ ミーティングへの参加のために使用は共存モードの値に関係なく受取済**Skype のビジネス ・ ミーティングに参加するユーザーのアプリケーションを優先**に設定します。</span><span class="sxs-lookup"><span data-stu-id="78be6-115">Set the **Preferred app for users to join Skype for Business meetings**  This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
    - <span data-ttu-id="78be6-116">**Skype 会議アプリケーション (既定)**</span><span class="sxs-lookup"><span data-stu-id="78be6-116">**Skype Meetings app (default)**</span></span>
    - <span data-ttu-id="78be6-117">**限られた機能とビジネスの Skype**</span><span class="sxs-lookup"><span data-stu-id="78be6-117">**Skype for Business with limited features**</span></span>
- <span data-ttu-id="78be6-118">**ビジネス ユーザー向け Skype をバック グラウンドでチームのアプリケーションをダウンロード**するのにはこの設定サイレント モードでダウンロード Windows 上でビジネス用の Skype を実行しているユーザーのチームのアプリケーションかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="78be6-118">Set whether to **Download the Teams app in the background for Skype for Business users**  This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="78be6-119">ビジネス用の Skype での保留中のアップグレードの通知が有効になっている場合またはユーザーの共存モードは、チームのみの場合にのみ受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="78be6-119">It is honored only if coexistence mode for the user is Teams Only, or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
1. <span data-ttu-id="78be6-120">変更を加えた後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78be6-120">Click **Save** after you make your changes.</span></span>


### <a name="related-topics"></a><span data-ttu-id="78be6-121">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="78be6-121">Related topics</span></span>
<span data-ttu-id="78be6-122">[旅の計画](upgrade-plan-journey.md)
[の共存を理解しビジネスとチームの Skype のモードのアップグレード](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="78be6-122">[Plan the journey](upgrade-plan-journey.md)
[Understand coexistence and upgrade modes for Skype for Business and Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span></span>