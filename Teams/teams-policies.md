---
title: Microsoft Teams でチーム ポリシーを管理する
author: cichur
ms.author: v-cichur
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: ユーザーがチームやチャネルで実行できる操作を制御する組織のチーム ポリシーの使用方法と管理方法について説明します。
ms.openlocfilehash: a05aaf65418e46f7b631bac6f7d88d8bbdf4c806
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802367"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="4948e-103">Microsoft Teams でチーム ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="4948e-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="4948e-104">管理者は、Microsoft Teams でチーム ポリシーを使用して、チームやチャネルで組織のユーザーが実行できる操作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="4948e-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="4948e-105">たとえば、ユーザーにプライベート チャネルの作成を許可するかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4948e-105">For example, you can set whether users are allowed to create private channels.</span></span>

<span data-ttu-id="4948e-106">チーム ポリシーを管理するには、Microsoft Teams 管理センターで **[Teams]** > **[チーム ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4948e-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4948e-107">グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="4948e-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="4948e-108">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4948e-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="4948e-109">グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="4948e-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="4948e-110">グローバル ポリシーを編集するか、ポリシーを割り当てると、変更が有効なまで数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4948e-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="4948e-111">カスタムのチーム ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4948e-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="4948e-112">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4948e-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="4948e-113">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4948e-113">Click **Add**.</span></span>
3. <span data-ttu-id="4948e-114">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="4948e-114">Enter a name and description for the policy.</span></span>

    ![チーム ポリシー設定のスクリーンショット](media/teams-policies.png)
4. <span data-ttu-id="4948e-116">ユーザーにプライベート チャネル<a name="createchannels"></a>の作成を許可するかどうかに応じて、プライベート チャネルの作成をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="4948e-116">Turn on or turn off **Create private channels**, <a name="createchannels"> </a> depending on whether you want to allow users to create private channels.</span></span>

5. <span data-ttu-id="4948e-117">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4948e-117">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="4948e-118">チーム ポリシーの編集</span><span class="sxs-lookup"><span data-stu-id="4948e-118">Edit a teams policy</span></span>

<span data-ttu-id="4948e-119">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="4948e-119">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="4948e-120">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4948e-120">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="4948e-121">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4948e-121">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="4948e-122">希望する設定をオンまたはオフにしてから、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4948e-122">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="4948e-123">ユーザーにカスタムのチーム ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4948e-123">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="4948e-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="4948e-124">Related topics</span></span>

[<span data-ttu-id="4948e-125">Teams のプライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="4948e-125">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="4948e-126"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4948e-126">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="4948e-127">New-CsTeamsChannelsPolicy</span><span class="sxs-lookup"><span data-stu-id="4948e-127">New-CsTeamsChannelsPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)
