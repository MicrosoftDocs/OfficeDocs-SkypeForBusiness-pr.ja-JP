---
title: マイクロソフトのチームで、組織全体にわたるチームを作成します。
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 09/27/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 作成し、チーム、組織全体にわたるチームを管理する方法について説明します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1882e18bdf746acc6b6991e4c574ca28cb3176a6
ms.sourcegitcommit: 8a4ed16adc60497510a528784e139075fbae9e55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "25502327"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a><span data-ttu-id="4b017-103">マイクロソフトのチームで、組織全体にわたるチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b017-103">Create an org-wide team in Microsoft Teams</span></span>

<span data-ttu-id="4b017-104">組織全体にわたるチームの小規模から中規模の組織の 1 つのチームの共同作業の一環として、すべてのユーザーを自動的に手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="4b017-104">Org-wide teams provide an automatic way for everyone in a small to medium-sized organization to be a part of a single team for collaboration.</span></span> 
 
<span data-ttu-id="4b017-105">組織全体にわたるチームでは、グローバル管理者はパブリックのチームでは、組織内のすべてのユーザーと最新のメンバーシップ ユーザーの結合と Active Directory の組織のままにするを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="4b017-105">With org-wide teams, global administrators can easily create a public team that pulls in every user in the organization and keeps the membership up to date with Active Directory as users join and leave the organization.</span></span> <span data-ttu-id="4b017-106">グローバル管理者のみが組織全体にわたるチームを作成でき、現在、組織全体にわたるチームは、1,000 未満のユーザーを持つ組織に限定します。</span><span class="sxs-lookup"><span data-stu-id="4b017-106">Only global admins can create org-wide teams and currently an org-wide team is limited to organizations with no more than 1,000 users.</span></span> <span data-ttu-id="4b017-107">これらの要件を満たしている場合の [**プライバシー** ] でオプションとして、チームを作成するときに管理者に**組織全体**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b017-107">If these requirements are met, admins will see **Org-wide** as an option under **Privacy** when creating a team.</span></span>

<span data-ttu-id="4b017-108">![組織全体にわたるチームを作成するのには [組織全体] オプションのスクリーン ショット](media/create-org-wide-team.png "組織全体にわたるチームを作成するのには [組織全体] オプションのスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="4b017-108">![Screen shot of the Org-wide option to create an org-wide team](media/create-org-wide-team.png "Screen shot of the Org-wide option to create an org-wide team")</span></span>

> [!NOTE]
> <span data-ttu-id="4b017-109">チームを作成するときに、[**組織全体**] オプションが表示されないし、あなたは、グローバル管理者、機能のロール アウトするも可能性がありますか、組織が 1000 のメンバーの現在のサイズ制限を超える必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b017-109">If you don't see the **Org-wide** option when creating a team and you're a global admin, the feature might still be rolling out or your organization might have more than the current size limit of 1000 members.</span></span> <span data-ttu-id="4b017-110">将来的にこの制限を大きくには求めています。</span><span class="sxs-lookup"><span data-stu-id="4b017-110">We're looking to increase this limit in future.</span></span>

<span data-ttu-id="4b017-111">組織全体にわたるチームを作成してすべてのグローバル管理者は、チームの所有者として追加されますすべてのアクティブなユーザーは、チームのメンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="4b017-111">When an org-wide team is created, all global admins are added as team owners and all active users are added as team members.</span></span> <span data-ttu-id="4b017-112">チーム、ゲスト ユーザー、およびほとんどの部屋を無効にするユーザーは、チームに追加されません。</span><span class="sxs-lookup"><span data-stu-id="4b017-112">Users who are disabled for Teams, guest users, and most rooms aren't added to the team.</span></span> <span data-ttu-id="4b017-113">組織のディレクトリが新しいアクティブなユーザーを含むように更新または変更は自動的に、ユーザーが社内で機能しなく、自分のチームのライセンスが無効になっている場合は、同期とユーザーの追加やチームから削除します。</span><span class="sxs-lookup"><span data-stu-id="4b017-113">As your organization's directory is updated to include new active users or if users no longer work at your company and their Teams license is disabled, changes are automatically synced and the users are added or removed from the team.</span></span> <span data-ttu-id="4b017-114">チーム メンバーには、組織全体にわたるチームをできないままにします。</span><span class="sxs-lookup"><span data-stu-id="4b017-114">Team members can't leave an org-wide team.</span></span> <span data-ttu-id="4b017-115">チームの所有者は、手動で追加または、必要な場合にユーザーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4b017-115">As a team owner, you can manually add or remove users if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="4b017-116">ルームの一覧、機材、およびリソースのアカウントの一部でない会議室を追加または組織全体にわたるチームを同期可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4b017-116">Rooms that aren't a part of a room list, equipment, and resource accounts might be added or synced to the org-wide team.</span></span> <span data-ttu-id="4b017-117">チームの所有者は、チームから、これらのアカウントを簡単に削除できます。</span><span class="sxs-lookup"><span data-stu-id="4b017-117">Team owners can easily remove these accounts from the team.</span></span>

## <a name="best-practices"></a><span data-ttu-id="4b017-118">ベスト ・ プラクティス</span><span class="sxs-lookup"><span data-stu-id="4b017-118">Best practices</span></span>
<span data-ttu-id="4b017-119">組織全体にわたるチームを最大限に活用、チームの所有者は、次の操作をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4b017-119">To get the most out of your org-wide team, we recommend team owners do the following.</span></span>
### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a><span data-ttu-id="4b017-120">チームの所有者のみが一般的なチャネルへの投稿</span><span class="sxs-lookup"><span data-stu-id="4b017-120">Allow only team owners to post to the General channel</span></span>
<span data-ttu-id="4b017-121">チャンネルのノイズを軽減するには、チームの所有者は、一般的なチャネルに投稿だけのこと。</span><span class="sxs-lookup"><span data-stu-id="4b017-121">Reduce channel noise by having only team owners post to the General channel.</span></span> <span data-ttu-id="4b017-122">チームに移動し、**その他のオプション (...)** をクリックします。 > **チームを管理**します。</span><span class="sxs-lookup"><span data-stu-id="4b017-122">Go to the team and click **More options (…)** > **Manage Team**.</span></span> <span data-ttu-id="4b017-123">[**設定**] タブの [**メンバーのアクセス許可**] をクリックします >**所有者だけがメッセージを投稿**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b017-123">On the **Settings** tab, click **Member permissions** > select **Only owners can post messages**.</span></span>
### <a name="turn-off-team-and-team-name-mentions"></a><span data-ttu-id="4b017-124">@Team をオフにし、@ 参照投稿の [チーム名]</span><span class="sxs-lookup"><span data-stu-id="4b017-124">Turn off @team and @[team name] mentions</span></span>
 <span data-ttu-id="4b017-125">組織全体をオーバー ロードしないように、@mentions を削減します。</span><span class="sxs-lookup"><span data-stu-id="4b017-125">Reduce @mentions to keep them from overloading the entire organization.</span></span> <span data-ttu-id="4b017-126">チームに移動し、**その他のオプション (...)** をクリックします。 > **チームを管理**します。</span><span class="sxs-lookup"><span data-stu-id="4b017-126">Go to the team and click **More options (…)** > **Manage Team**.</span></span> <span data-ttu-id="4b017-127">[**設定**] タブの [ **@mentions** ] をクリックします > をオフに**メンバー @team するためのオプションを表示するか、@[チーム名]**。</span><span class="sxs-lookup"><span data-stu-id="4b017-127">On the **Settings** tab, click **@mentions** > turn off **Show members the option to @team or @[team name]**.</span></span> 
### <a name="automatically-favorite-important-channels"></a><span data-ttu-id="4b017-128">自動的にお気に入りの重要なチャネル</span><span class="sxs-lookup"><span data-stu-id="4b017-128">Automatically favorite important channels</span></span>
 <span data-ttu-id="4b017-129">特定の会話を実施しており、組織内のすべてのユーザーを確認するお気に入りの重要なチャンネルです。</span><span class="sxs-lookup"><span data-stu-id="4b017-129">Favorite important channels to ensure everyone in your organization engages in specific conversations.</span></span> <span data-ttu-id="4b017-130">詳細については、[チーム全体の自動-お気に入りのチャンネル](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b017-130">To learn more, see [Auto-favorite channels for the whole team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).</span></span>
