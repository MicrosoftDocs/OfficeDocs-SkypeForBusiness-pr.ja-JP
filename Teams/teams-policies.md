---
title: Microsoft Teams でチーム ポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
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
description: ユーザーがチームやチャネルで実行できる操作を制御する組織のチーム ポリシーの使用方法と管理方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 9ed0bd3aadcde76835bb3d435429785ceaf562a2
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938146"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="8abc7-103">Microsoft Teams でチーム ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="8abc7-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="8abc7-104">管理者は、Microsoft Teams でチーム ポリシーを使用して、チームやチャネルで組織のユーザーが実行できる操作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="8abc7-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="8abc7-105">たとえば、ユーザーが検索結果とチーム ギャラリーでプライベートのチームを検出できるかどうか、およびユーザーがプライベートのチャネルを作成できるかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8abc7-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="8abc7-106">チーム ポリシーを管理するには、Microsoft Teams 管理センターで **[Teams]** > **[チーム ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="8abc7-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="8abc7-107">グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8abc7-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="8abc7-108">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8abc7-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="8abc7-109">グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="8abc7-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="8abc7-110">グローバルポリシーを編集するか、ポリシーを割り当てると、変更が有効になるまでに数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="8abc7-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="8abc7-111">カスタムのチーム ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="8abc7-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="8abc7-112">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="8abc7-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="8abc7-113">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8abc7-113">Click **Add**.</span></span>
3. <span data-ttu-id="8abc7-114">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="8abc7-114">Enter a name and description for the policy.</span></span>

    ![チーム ポリシー設定のスクリーンショット](media/teams-policies.png)
4. <span data-ttu-id="8abc7-116">希望する設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="8abc7-116">Choose the settings that you want:</span></span>

- <span data-ttu-id="8abc7-117">プライベート**チームを見つける**(プライベートプレビュー):<a name="discoverteams"> </a>この設定を有効にすると、ユーザーは検索結果とチームギャラリーでプライベートチームを見つけられるようになります。</span><span class="sxs-lookup"><span data-stu-id="8abc7-117">**Discover private teams** (in private preview):<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="8abc7-118">**プライベート チャネルの作成**: <a name="createchannels"> </a>この設定をオンにすると、ユーザーがプライベート チャネルを作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8abc7-118">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="8abc7-119">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8abc7-119">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="8abc7-120">チーム ポリシーの編集</span><span class="sxs-lookup"><span data-stu-id="8abc7-120">Edit a teams policy</span></span>

<span data-ttu-id="8abc7-121">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="8abc7-121">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="8abc7-122">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="8abc7-122">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="8abc7-123">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8abc7-123">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="8abc7-124">希望する設定をオンまたはオフにしてから、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8abc7-124">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="8abc7-125">ユーザーにカスタムのチーム ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="8abc7-125">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="8abc7-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="8abc7-126">Related topics</span></span>

[<span data-ttu-id="8abc7-127">Teams でプライベート チームの検索を管理する</span><span class="sxs-lookup"><span data-stu-id="8abc7-127">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)

[<span data-ttu-id="8abc7-128">Teams のプライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="8abc7-128">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="8abc7-129">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="8abc7-129">Assign policies to your users in Teams</span></span>](assign-policies.md)
