---
title: Microsoft Teams でタグを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams での組織でのタグの使用方法を管理する方法について説明します。
ms.openlocfilehash: 5fbfa980f1cf6acd8ce32af810bf2527ece3d1fa
ms.sourcegitcommit: 0549714f17f9994cf832a303ec9bc58a537c3a51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951552"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="1e2da-103">Microsoft Teams でタグを管理する</span><span class="sxs-lookup"><span data-stu-id="1e2da-103">Manage tags in Microsoft Teams</span></span>

<span data-ttu-id="1e2da-104">Microsoft Teams のタグを使用すると、ユーザーはチームのメンバーのサブセットと連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-104">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="1e2da-105">タグを1人または複数のチームメンバーに追加して、ユーザーの適切なサブセットに簡単に接続できます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-105">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="1e2da-106">チーム所有者とメンバー (その機能が有効になっている場合) は、1つまたは複数のタグをユーザーに追加できます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-106">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="1e2da-107">その後、タグは、チームの任意のユーザーによってチャネル投稿で @mentions で使用したり、そのタグが割り当てられたユーザーのみとの会話を開始したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-107">The tags can then be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="1e2da-108">プライベートチャネルでは、タグはまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1e2da-108">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="1e2da-109">US Government Community Cloud (GCC)、GCC High、または国防総省 (DoD) の組織では、タグはまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="1e2da-109">Tags are not yet available in US Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) organizations.</span></span> 

## <a name="how-tags-work"></a><span data-ttu-id="1e2da-110">タグのしくみ</span><span class="sxs-lookup"><span data-stu-id="1e2da-110">How tags work</span></span>

<span data-ttu-id="1e2da-111">タグは、特定のチームのメンバーに追加できます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-111">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="1e2da-112">タグを追加すると、チャットまたはチームの標準チャネルで @mentions で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1e2da-112">After a tag is added, it can be used in @mentions in a chat or in any standard channel of the team.</span></span> <span data-ttu-id="1e2da-113">次に、Teams でタグを使用する方法の例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="1e2da-113">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="1e2da-114">ストアマネージャーが、チャネルにお知らせを投稿して、すべてのレジに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e2da-114">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="1e2da-115">グループの製品マネージャーは、チャネル内のすべての製品マネージャーにメッセージを送信したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="1e2da-115">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="1e2da-116">病院の管理者が、チャネル内のすべての radiologists にメッセージを送信したい。</span><span class="sxs-lookup"><span data-stu-id="1e2da-116">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="1e2da-117">マーケティング課長は、すべてのデザイナーとグループチャットを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e2da-117">A marketing manager wants to start a group chat with all designers.</span></span> 

<span data-ttu-id="1e2da-118">詳細については、「 [Teams でタグを使用する」](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1e2da-118">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="1e2da-119">組織のタグを管理する</span><span class="sxs-lookup"><span data-stu-id="1e2da-119">Manage tags for your organization</span></span>

<span data-ttu-id="1e2da-120">管理者は、Microsoft Teams 管理センターにおいて、タグを追加できるユーザーと、タグを組織全体でどのように使用するかを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-120">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Microsoft Teams 管理センターのタグ設定のスクリーンショット](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a><span data-ttu-id="1e2da-122">タグを追加できるユーザーを設定する</span><span class="sxs-lookup"><span data-stu-id="1e2da-122">Set who can add tags</span></span>

<span data-ttu-id="1e2da-123">既定では、チームの所有者はタグを追加できます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-123">By default, team owners can add tags.</span></span> <span data-ttu-id="1e2da-124">この設定を変更して、チーム所有者とチームメンバーがタグを追加できるようにするか、組織のタグをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-124">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="1e2da-125">Microsoft Teams 管理センターの左のナビゲーションで、[**組織全体の設定** > ]**チームの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e2da-125">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="1e2da-126">[**タグ付け**] で、[**タグ付けの対象] の**横にある次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e2da-126">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="1e2da-127">**チームの所有者とメンバー**: チームの所有者とメンバーがタグを追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1e2da-127">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="1e2da-128">**チームの所有者**: チーム所有者がタグを追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1e2da-128">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="1e2da-129">**Disabled**: ノートシールをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1e2da-129">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="1e2da-130">タグ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="1e2da-130">Configure tags settings</span></span>

<span data-ttu-id="1e2da-131">次のタグ設定を構成して、組織全体でのタグの使用方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-131">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="1e2da-132">Microsoft Teams 管理センターの左のナビゲーションで、[**組織全体の設定** > ]**チームの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e2da-132">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="1e2da-133">[**タグ付け**] で、組織のニーズに応じて次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="1e2da-133">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="1e2da-134">**チーム所有者は、タグを適用できるユーザーを上書きでき**ます。この機能がオンになっていると、チームの所有者は、チーム設定でメンバーにタグを追加することを許可または禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-134">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="1e2da-135">**メンバーはタグ**を追加できます。チームメンバーがタグを追加できるようにするには、このオプションをオンにして、設定した既定のタグ以外のタグをチームメンバーが追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1e2da-135">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="1e2da-136">この機能が無効になっている場合、チームメンバーは既定のタグのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-136">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="1e2da-137">**提案**された既定のタグ: これを使用して、一連の既定のタグを追加します。</span><span class="sxs-lookup"><span data-stu-id="1e2da-137">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="1e2da-138">最大25個のタグを追加できます。各タグには最大25文字まで含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-138">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="1e2da-139">チーム所有者とメンバー (機能が有効になっている場合) は、これらの候補を使用したり、それらを追加したり、新しいタグセットを作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-139">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="1e2da-140">チームのタグ設定を管理する</span><span class="sxs-lookup"><span data-stu-id="1e2da-140">Manage tags settings for a team</span></span>

<span data-ttu-id="1e2da-141">チーム所有者が Microsoft Teams 管理センターの [**タグを適用できるユーザーを上書きできる**] 設定をオンにしている場合、チーム所有者は、メンバーがチームレベルでタグを追加できるかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-141">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="1e2da-142">これを行うには、チームの [**設定**] タブで [**タグ**] に移動し、[タグを追加できるユーザー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e2da-142">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![チームレベルの [タグ] 設定のスクリーンショット](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a><span data-ttu-id="1e2da-144">Teams でタグを追加する</span><span class="sxs-lookup"><span data-stu-id="1e2da-144">Add tags in Teams</span></span>

<span data-ttu-id="1e2da-145">Teams では、チームの [チームの管理] ページの [**メンバー** ] タブに [**タグ**] 列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1e2da-145">In Teams, the **Members** tab of the Manage team page for a team includes a **Tags** column.</span></span> <span data-ttu-id="1e2da-146">チームの所有者とメンバー (機能が有効になっている場合) は、メンバーの横にある [**タグの管理**] をクリックすると、そのメンバーの候補タグの一覧が表示され、タグをリストに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="1e2da-146">Team owners and members (if the feature is enabled for them) can click **Manage tags** next to a member to see the list of suggested tags for that member and add tags to the list.</span></span>

![<span data-ttu-id="1e2da-147">Teams クライアントでタグを適用する方法を示すスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="1e2da-147">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png) 
