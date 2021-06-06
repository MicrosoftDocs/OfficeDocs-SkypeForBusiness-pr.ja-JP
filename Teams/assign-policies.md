---
title: Microsoft Teams でユーザーにポリシーを割り当てる
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
description: Microsoft Teams でユーザーにポリシーを割り当てる方法について説明します。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 05ed811c38b3f49e21933d575c82128360ca3390
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739717"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="34f20-103">Microsoft Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="34f20-104">管理者は、ポリシーを使用して、組織のユーザーが利用できる Teams 機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="34f20-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="34f20-105">たとえば、ほんの一例を挙げると、通話ポリシー、会議ポリシー、メッセージ ポリシーなどがあります。</span><span class="sxs-lookup"><span data-stu-id="34f20-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="34f20-106">組織には、固有のニーズを持つユーザーの種類が異なります。</span><span class="sxs-lookup"><span data-stu-id="34f20-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="34f20-107">作成して割り当てるカスタム ポリシーを使用すると、それらのニーズに基づいてポリシー設定をさまざまなユーザー セットに合わせて調整できます。</span><span class="sxs-lookup"><span data-stu-id="34f20-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="34f20-108">組織のポリシーを簡単に管理するには、Teamsにポリシーを割り当てる方法がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="34f20-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="34f20-109">ポリシーをユーザーに直接割り当てる (個別に割り当てるか、バッチ割り当てによって大規模に割り当てるか、ユーザーがメンバーであるグループに割り当てる)。</span><span class="sxs-lookup"><span data-stu-id="34f20-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="34f20-110">ポリシー パッケージを使用して、ポリシーの既定のコレクションを、同様の役割を持つ組織内のユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="34f20-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="34f20-111">選択するオプションは、管理しているポリシーの数と、ポリシーを割り当てるユーザーの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="34f20-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="34f20-112">グローバル (組織全体の既定) ポリシーは、組織内の最大ユーザー数に適用されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="34f20-113">ポリシーは、特殊なポリシーを必要とするユーザーにのみ割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="34f20-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="34f20-114">この記事では、ユーザーにポリシーを割り当てるさまざまな方法と、何をいつ使用するかについての推奨シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34f20-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="34f20-115">どのポリシーが優先されますか?</span><span class="sxs-lookup"><span data-stu-id="34f20-115">Which policy takes precedence?</span></span>

<span data-ttu-id="34f20-116">ユーザーには、ポリシーの種類ごとに 1 つの有効なポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="34f20-116">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="34f20-117">ユーザーにポリシーが直接割り当てられている可能性があります。また、同じ種類のポリシーが割り当てられている 1 つ以上のグループのメンバーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34f20-117">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="34f20-118">このようなシナリオでは、どのポリシーが優先されますか?</span><span class="sxs-lookup"><span data-stu-id="34f20-118">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="34f20-119">ユーザーの有効なポリシーは、次の優先規則に従って決定されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-119">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="34f20-120">ユーザーに直接ポリシーが割り当てられている場合 （個別に、またはバッチ割り当てによって）、そのポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-120">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="34f20-121">次の視覚的な例では、ユーザーの有効なポリシーは、ユーザーに直接割り当てられる、Square 会議ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="34f20-121">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![直接割り当てられたポリシーの優先順位を示す図](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="34f20-123">ユーザーに特定の種類のポリシーが直接割り当てられていない場合は、そのユーザーがメンバーになっているグループに割り当てられているポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-123">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="34f20-124">ユーザーが複数のグループのメンバーである場合、特定のポリシーの種類に対して、[グループ割り当てのランク付け](#group-assignment-ranking) が最も高いポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-124">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="34f20-125">この視覚的な例では、ユーザーの有効なポリシーは Exec Teams ポリシーと HD ポリシーです。これは、ユーザーがメンバーであり、同じポリシーの種類のポリシーも割り当てられている他のグループに対して最も高い割り当て順位を持っています。</span><span class="sxs-lookup"><span data-stu-id="34f20-125">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![グループから継承されたポリシーの優先順位を示す図](media/assign-policies-example-group.png)

<span data-ttu-id="34f20-127">ユーザーが直接ポリシーを割り当てられていない場合や、ポリシーが割り当てられているグループのメンバーではない場合、ユーザーはそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="34f20-127">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="34f20-128">視覚的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="34f20-128">Here's a visual example.</span></span>

![グローバル ポリシーの優先順位を示す図](media/assign-policies-example-global.png)

<span data-ttu-id="34f20-130">詳細については、「[優先規則](#precedence-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34f20-130">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="34f20-131">ポリシーを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="34f20-131">Ways to assign policies</span></span>

<span data-ttu-id="34f20-132">これは、ユーザーにポリシーを割り当てる方法と、それぞれに推奨されるシナリオの概要です。</span><span class="sxs-lookup"><span data-stu-id="34f20-132">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="34f20-133">詳細については、リンクを選択してください。</span><span class="sxs-lookup"><span data-stu-id="34f20-133">Select the links to learn more.</span></span>

<span data-ttu-id="34f20-134">個々のユーザーまたはグループにポリシーを割り当てる前に、[グローバルな （組織全体の既定の） ポリシーを設定して](#set-the-global-policies)、それらが組織内の最大数のユーザーに適用されるようにします。</span><span class="sxs-lookup"><span data-stu-id="34f20-134">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="34f20-135">グローバル ポリシーを設定した後は、特殊なポリシーを必要とするユーザーにポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="34f20-135">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="34f20-136">操作</span><span class="sxs-lookup"><span data-stu-id="34f20-136">Do this</span></span>  |<span data-ttu-id="34f20-137">条件...</span><span class="sxs-lookup"><span data-stu-id="34f20-137">If...</span></span>  | <span data-ttu-id="34f20-138">使用する技術...</span><span class="sxs-lookup"><span data-stu-id="34f20-138">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="34f20-139">ポリシーを個々のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-139">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="34f20-140">Teams を初めて使用する場合、1 つまたはいくつかのポリシーを少数のユーザーに割り当てるだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="34f20-140">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="34f20-141">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="34f20-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>
|[<span data-ttu-id="34f20-142">ポリシーをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-142">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="34f20-143">ユーザーのグループ メンバーシップに基づいてポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="34f20-143">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="34f20-144">たとえば、セキュリティ グループまたは配布リスト内のすべてのユーザーにポリシーを割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="34f20-144">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="34f20-145">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="34f20-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="34f20-146">ポリシーをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-146">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="34f20-147">多数のユーザーにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="34f20-147">Assign policies to large sets of users.</span></span> <span data-ttu-id="34f20-148">たとえば、組織内の数百または数千人のユーザーに一度にポリシーを割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="34f20-148">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="34f20-149">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="34f20-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="34f20-150">ポリシー パッケージをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-150">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  |<span data-ttu-id="34f20-151">同じロールまたは同様のロールを持つ組織内の特定のユーザー セットに複数のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="34f20-151">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="34f20-152">たとえば、学校の教師に教育 (教師) ポリシー パッケージを割り当て、チャット、通話、会議へのフル アクセス権を与えます。</span><span class="sxs-lookup"><span data-stu-id="34f20-152">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="34f20-153">Education (中学生) ポリシー パッケージをセカンダリ 学生に割り当て、プライベート通話などの特定の機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="34f20-153">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="34f20-154">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="34f20-154">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="34f20-155">[ポリシー パッケージをグループに割り当てる](#assign-a-policy-package-to-a-group) (プライベート プレビュー)</span><span class="sxs-lookup"><span data-stu-id="34f20-155">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="34f20-156">同じロールまたは同様のロールを持つ組織内のユーザーグループに複数のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="34f20-156">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="34f20-157">たとえば、セキュリティ グループまたは配布リスト内のすべてのユーザーにポリシー パッケージを割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="34f20-157">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="34f20-158">Microsoft Teams 管理センター (近日公開予定) または Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="34f20-158">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="34f20-159">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-159">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="34f20-160">同じロールまたは同様のロールを持つ組織内のユーザーのバッチに複数のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="34f20-160">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="34f20-161">たとえば、バッチ割り当てを使用して、学校内のすべての教師に教育 (教師) ポリシー パッケージを割り当て、チャット、通話、会議へのフル アクセス権を与えます。</span><span class="sxs-lookup"><span data-stu-id="34f20-161">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="34f20-162">Education (中学生) ポリシー パッケージをセカンダリ 学生のバッチに割り当て、プライベート通話などの特定の機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="34f20-162">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="34f20-163">Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="34f20-163">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="34f20-164">グローバル ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="34f20-164">Set the global policies</span></span>

<span data-ttu-id="34f20-165">次の手順に従って、ポリシーの種類ごとにグローバルな (組織全体の既定の) ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="34f20-165">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="34f20-166">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="34f20-166">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="34f20-167">Microsoft Teams 管理センターの左側のナビゲーションで、更新するポリシー タイプのポリシー ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="34f20-167">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="34f20-168">たとえば、**Teams** > **Teams ポリシー**、**会議** > **会議ポリシー**、**メッセージ ポリシー**、または **音声** > **通話ポリシー** です。</span><span class="sxs-lookup"><span data-stu-id="34f20-168">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="34f20-169">現在の設定を表示するには、**グローバルな (組織全体の既定の)** ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-169">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="34f20-170">必要に応じてポリシーを更新し、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-170">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="34f20-171">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="34f20-171">Using PowerShell</span></span>

<span data-ttu-id="34f20-172">PowerShell を使用してグローバル ポリシーを設定するには、グローバル識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="34f20-172">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="34f20-173">まず、現在のグローバル ポリシーを確認して、変更する設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="34f20-173">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

<span data-ttu-id="34f20-174">次に、必要に応じてグローバル ポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="34f20-174">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="34f20-175">変更する設定の値を指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="34f20-175">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="34f20-176">ポリシーを個々のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-176">Assign a policy to individual users</span></span>

<span data-ttu-id="34f20-177">個々のユーザーまたは一度に少数のユーザーにポリシーを割り当てるには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="34f20-177">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="34f20-178">管理センター Microsoft Teams使用する</span><span class="sxs-lookup"><span data-stu-id="34f20-178">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="34f20-179">ポリシーをグループに割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="34f20-179">To assign a policy to a user:</span></span>

1. <span data-ttu-id="34f20-180">管理センターの左側のMicrosoft Teams、[ユーザー] に移動し、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-180">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="34f20-181">ユーザー名の左側をクリックしてユーザーを選択し、[設定の編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="34f20-181">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="34f20-182">割り当てるポリシーを選択し、[適用] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="34f20-182">Select the policy you want to assign, and then select **Apply**.</span></span>

<span data-ttu-id="34f20-183">または、次の操作も実行できます:</span><span class="sxs-lookup"><span data-stu-id="34f20-183">Or, you can also do the following:</span></span>

1. <span data-ttu-id="34f20-184">Microsoft Teams 管理センターの左側のナビゲーションで、ポリシー ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="34f20-184">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="34f20-185">ポリシー名の左側をクリックして割り当てるポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="34f20-185">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="34f20-186">**[ユーザーを管理する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-186">Select **Manage users**.</span></span>
4. <span data-ttu-id="34f20-187">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="34f20-187">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="34f20-188">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="34f20-188">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="34f20-189">ユーザーの追加が完了したら、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-189">When you're finished adding users, select **Apply**.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="34f20-190">PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="34f20-190">Use PowerShell</span></span>

<span data-ttu-id="34f20-191">各ポリシー タイプには、それを管理するための独自のコマンドレットのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="34f20-191">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="34f20-192">特定のポリシー タイプに ```Grant-``` コマンドレットを使用して、ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="34f20-192">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="34f20-193">たとえば、```Grant-CsTeamsMeetingPolicy``` コマンドレットを使用して、Teams 会議ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="34f20-193">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="34f20-194">これらのコマンドレットは PowerShell モジュールの Teamsに含まれており、このコマンドレット リファレンス[Skype for Businessに記載されています](/powershell/skype/intro?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="34f20-194">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](/powershell/skype/intro?view=skype-ps).</span></span>

<span data-ttu-id="34f20-195">PowerShell のパブリック[Teamsを](https://www.powershellgallery.com/packages/MicrosoftTeams/)ダウンロードしてインストールし (まだインストールしていない場合)、次のコマンドを実行して接続します。</span><span class="sxs-lookup"><span data-stu-id="34f20-195">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="34f20-196">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="34f20-196">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="34f20-197">最新の [Teams PowerShell パブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)をご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="34f20-197">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="34f20-198">この例では、Student Meeting Policy という名前の Teams 会議ポリシーを、Reda というユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="34f20-198">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="34f20-199">詳細については、「[PowerShell によるポリシーの管理](teams-powershell-managing-teams.md#manage-policies-via-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34f20-199">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="34f20-200">ポリシーをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-200">Assign a policy to a group</span></span>

<span data-ttu-id="34f20-201">グループにポリシーを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="34f20-201">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="34f20-202">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-202">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="34f20-203">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-203">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="34f20-204">ポリシーをグループに割り当てるのは、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="34f20-204">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="34f20-205">ポリシーを割り当てると、そのポリシーはすぐにグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="34f20-205">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="34f20-206">ただし、グループのメンバーへのポリシー割り当ての反映はバックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="34f20-206">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="34f20-207">ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="34f20-207">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="34f20-208">グループ ポリシーの割り当ては、グループの直接メンバーであるユーザーにのみ伝達されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-208">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="34f20-209">割り当ては、入れ子になったグループのメンバーには伝達されません。</span><span class="sxs-lookup"><span data-stu-id="34f20-209">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="34f20-210">グループへのポリシーの割り当てについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="34f20-210">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="34f20-211">使用を開始する前に、優先規則とグループ割り当てのランク付けを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="34f20-211">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="34f20-212">優先規則</span><span class="sxs-lookup"><span data-stu-id="34f20-212">Precedence rules</span></span>

<span data-ttu-id="34f20-213">特定のポリシーの種類について、ユーザーの有効なポリシーは、次に従って決定されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-213">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="34f20-214">ユーザーに直接割り当てられているポリシーは、グループに割り当てられている同じ種類の別のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-214">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="34f20-215">言い換えると、ユーザーに特定の種類のポリシーが直接割り当てられている場合、そのユーザーはグループから同じ種類のポリシーを継承しません。</span><span class="sxs-lookup"><span data-stu-id="34f20-215">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="34f20-216">つまり、ユーザーが特定の種類のポリシーを直接割り当てられている場合は、ユーザーがグループから同じ種類のポリシーを継承する前に、そのポリシーをユーザーから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34f20-216">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>

- <span data-ttu-id="34f20-217">ユーザーに直接割り当てられたポリシーがなく、2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合、ユーザーは最も高いランク付けを持つグループ割り当てのポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="34f20-217">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>

- <span data-ttu-id="34f20-218">ユーザーがポリシーが割り当てられているグループのメンバーではない場合、ユーザーにそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="34f20-218">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="34f20-219">ユーザーの有効なポリシーは、次の規則に従って更新されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-219">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="34f20-220">ポリシーが割り当てられているグループにユーザーが追加または削除された場合。</span><span class="sxs-lookup"><span data-stu-id="34f20-220">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="34f20-221">ポリシーはグループから割り当て解除されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-221">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="34f20-222">ユーザーに直接割り当てられているポリシーは削除されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-222">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="34f20-223">グループ割り当てのランク付け</span><span class="sxs-lookup"><span data-stu-id="34f20-223">Group assignment ranking</span></span>

<span data-ttu-id="34f20-224">ポリシーをグループに割り当てるときは、グループ割り当てのランクを指定します。</span><span class="sxs-lookup"><span data-stu-id="34f20-224">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="34f20-225">これは、ユーザーが 2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合に、ユーザーが有効なポリシーとして継承する必要があるポリシーを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-225">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="34f20-226">グループ割り当てのランク付けは、同じ種類の別のグループ割り当てに関連しています。</span><span class="sxs-lookup"><span data-stu-id="34f20-226">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="34f20-227">たとえば、通話ポリシーを 2 つのグループに割り当てる場合は、1 つの割り当てのランクを 1 に設定し、もう 1 つの割り当てを 2 に設定します。1 が最高のランクです。</span><span class="sxs-lookup"><span data-stu-id="34f20-227">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="34f20-228">グループ割り当てランキングは、継承に関する他のグループ メンバーシップよりも重要または関連性の高いグループ メンバーシップを示します。</span><span class="sxs-lookup"><span data-stu-id="34f20-228">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships regarding inheritance.</span></span>

<span data-ttu-id="34f20-229">たとえば、店舗の従業員と管理者の 2 つのグループがあるとします。</span><span class="sxs-lookup"><span data-stu-id="34f20-229">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="34f20-230">両方のグループには、それぞれ Teams 通話ポリシー、店舗従業員通話ポリシー、および店舗管理者通話ポリシーが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="34f20-230">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="34f20-231">両方のグループに属する店舗管理者の場合、管理者としての役割は従業員としての役割よりも重要であるため、店舗管理者グループに割り当てられている通話ポリシーにより高いランク付けを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="34f20-231">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="34f20-232">グループ</span><span class="sxs-lookup"><span data-stu-id="34f20-232">Group</span></span> |<span data-ttu-id="34f20-233">Teams 通話ポリシー名</span><span class="sxs-lookup"><span data-stu-id="34f20-233">Teams calling policy name</span></span>  |<span data-ttu-id="34f20-234">ランク</span><span class="sxs-lookup"><span data-stu-id="34f20-234">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="34f20-235">店舗管理者</span><span class="sxs-lookup"><span data-stu-id="34f20-235">Store Managers</span></span>   |<span data-ttu-id="34f20-236">店舗管理者通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="34f20-236">Store Managers Calling Policy</span></span>         |<span data-ttu-id="34f20-237">1</span><span class="sxs-lookup"><span data-stu-id="34f20-237">1</span></span>|
|<span data-ttu-id="34f20-238">店舗従業員</span><span class="sxs-lookup"><span data-stu-id="34f20-238">Store Employees</span></span>    |<span data-ttu-id="34f20-239">店舗従業員通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="34f20-239">Store Employees Calling Policy</span></span>      |<span data-ttu-id="34f20-240">2</span><span class="sxs-lookup"><span data-stu-id="34f20-240">2</span></span>|

<span data-ttu-id="34f20-241">ランクを指定しないと、ポリシーの割り当てに最も低いランクが与えられます。</span><span class="sxs-lookup"><span data-stu-id="34f20-241">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="34f20-242">管理センター Teamsで</span><span class="sxs-lookup"><span data-stu-id="34f20-242">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="34f20-243">現在、Microsoft Teams 管理センターを使用したグループへのポリシー割り当ては、Teams 通話ポリシー、Teams コール パーク ポリシー、Teams ポリシー、Teams ライブ イベント ポリシー、Teams 会議ポリシー、Teams メッセージ ポリシーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="34f20-243">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="34f20-244">他のポリシーの種類については、PowerShell を使用してください。</span><span class="sxs-lookup"><span data-stu-id="34f20-244">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="34f20-245">Microsoft Teams 管理センターの左側のナビゲーションで、ポリシーの種類のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="34f20-245">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="34f20-246">たとえば、**会議** > **会議ポリシー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="34f20-246">For example, go to **Meetings** > **Meeting policies**.</span></span>

2. <span data-ttu-id="34f20-247">**グループ ポリシーの割り当て** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-247">Select the **Group policy assignment** tab.</span></span>

3. <span data-ttu-id="34f20-248">**[グループの追加]** を選択し、**[ポリシーをグループに割り当てる]** ウィンドウで、次の操作を行います:</span><span class="sxs-lookup"><span data-stu-id="34f20-248">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="34f20-249">ポリシーを割り当てるグループを検索し、追加します。</span><span class="sxs-lookup"><span data-stu-id="34f20-249">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="34f20-250">グループ割り当てのランク付けを設定します。</span><span class="sxs-lookup"><span data-stu-id="34f20-250">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="34f20-251">割り当てるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-251">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="34f20-252">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-252">Select **Apply**.</span></span>

<span data-ttu-id="34f20-253">グループ ポリシーの割り当てを削除するには、ポリシー ページの **[グループ ポリシーの割り当て]** タブで、グループの割り当てを選び、**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-253">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="34f20-254">グループ割り当てのランク付けを変更するには、最初にグループ ポリシーの割り当てを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34f20-254">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="34f20-255">次に、上記の手順に従ってポリシーをグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="34f20-255">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="34f20-256">PowerShell オプションを使用する</span><span class="sxs-lookup"><span data-stu-id="34f20-256">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="34f20-257">現在、PowerShell を使用したグループへのポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="34f20-257">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="34f20-258">サポートされているポリシー タイプの一覧については、[New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34f20-258">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="34f20-259">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="34f20-259">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="34f20-260">段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34f20-260">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="34f20-261">ポリシーをユーザーのグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-261">Assign a policy to a group of users</span></span>

<span data-ttu-id="34f20-262">[New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)コマンドレットを使用して、グループにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="34f20-262">Use the [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="34f20-263">オブジェクト ID、SIP アドレス、または電子メール アドレスを使用して、グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="34f20-263">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="34f20-264">この例では、Retail Managers Meeting Policy という名前の Teams 会議ポリシーを、割り当てのランクが 1 のグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="34f20-264">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="34f20-265">グループのポリシーの割り当てを取得する</span><span class="sxs-lookup"><span data-stu-id="34f20-265">Get policy assignments for a group</span></span>

<span data-ttu-id="34f20-266">[Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) コマンドレットを使用して、グループに割り当てられているすべてのポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="34f20-266">Use the [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="34f20-267">SIP アドレスまたは電子メール アドレスがポリシーの割り当てに使用された場合でも、グループは常にグループ ID で一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-267">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="34f20-268">この例では、特定のグループに割り当てられているすべてのポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="34f20-268">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="34f20-269">この例では、Teams 会議ポリシーが割り当てられているすべてのグループを返します。</span><span class="sxs-lookup"><span data-stu-id="34f20-269">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="34f20-270">グループからポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="34f20-270">Remove a policy from a group</span></span>

<span data-ttu-id="34f20-271">[Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) コマンドレットを使用して、グループからポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="34f20-271">Use the [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="34f20-272">グループからポリシーを削除すると、そのグループに割り当てられている、ランクが低い同じ種類の他のポリシーの優先順位が更新されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-272">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="34f20-273">たとえば、ランクが 2 であるポリシーを削除すると、その新しいランク付けを反映して、ランク 3 と 4 のポリシーが更新されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-273">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="34f20-274">次の 2 つの表にこの例を示します。</span><span class="sxs-lookup"><span data-stu-id="34f20-274">The following two tables show this example.</span></span>

<span data-ttu-id="34f20-275">これは、Teams 会議ポリシーのポリシー割り当てと優先順位のリストです。</span><span class="sxs-lookup"><span data-stu-id="34f20-275">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="34f20-276">グループ名</span><span class="sxs-lookup"><span data-stu-id="34f20-276">Group name</span></span>  |<span data-ttu-id="34f20-277">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="34f20-277">Policy name</span></span>  |<span data-ttu-id="34f20-278">ランク</span><span class="sxs-lookup"><span data-stu-id="34f20-278">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="34f20-279">営業</span><span class="sxs-lookup"><span data-stu-id="34f20-279">Sales</span></span>    |<span data-ttu-id="34f20-280">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="34f20-280">Sales policy</span></span>       | <span data-ttu-id="34f20-281">1</span><span class="sxs-lookup"><span data-stu-id="34f20-281">1</span></span>        |
|<span data-ttu-id="34f20-282">西部地域</span><span class="sxs-lookup"><span data-stu-id="34f20-282">West Region</span></span>     |<span data-ttu-id="34f20-283">西部地域ポリシー</span><span class="sxs-lookup"><span data-stu-id="34f20-283">West Region policy</span></span>         |<span data-ttu-id="34f20-284">2</span><span class="sxs-lookup"><span data-stu-id="34f20-284">2</span></span>         |
|<span data-ttu-id="34f20-285">部門</span><span class="sxs-lookup"><span data-stu-id="34f20-285">Division</span></span>    |<span data-ttu-id="34f20-286">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="34f20-286">Division policy</span></span>         |<span data-ttu-id="34f20-287">3</span><span class="sxs-lookup"><span data-stu-id="34f20-287">3</span></span>         |
|<span data-ttu-id="34f20-288">部署</span><span class="sxs-lookup"><span data-stu-id="34f20-288">Subsidiary</span></span>   |<span data-ttu-id="34f20-289">部署ポリシー</span><span class="sxs-lookup"><span data-stu-id="34f20-289">Subsidiary policy</span></span>        |<span data-ttu-id="34f20-290">4</span><span class="sxs-lookup"><span data-stu-id="34f20-290">4</span></span>         |

<span data-ttu-id="34f20-291">西部地域グループから西部地域ポリシーを削除すると、ポリシーの割り当てと優先順位は次のように更新されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-291">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="34f20-292">グループ名</span><span class="sxs-lookup"><span data-stu-id="34f20-292">Group name</span></span>  |<span data-ttu-id="34f20-293">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="34f20-293">Policy name</span></span>  |<span data-ttu-id="34f20-294">ランク</span><span class="sxs-lookup"><span data-stu-id="34f20-294">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="34f20-295">営業</span><span class="sxs-lookup"><span data-stu-id="34f20-295">Sales</span></span>    |<span data-ttu-id="34f20-296">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="34f20-296">Sales policy</span></span>       | <span data-ttu-id="34f20-297">1</span><span class="sxs-lookup"><span data-stu-id="34f20-297">1</span></span>        |
|<span data-ttu-id="34f20-298">部門</span><span class="sxs-lookup"><span data-stu-id="34f20-298">Division</span></span>    |<span data-ttu-id="34f20-299">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="34f20-299">Division policy</span></span>         |<span data-ttu-id="34f20-300">2</span><span class="sxs-lookup"><span data-stu-id="34f20-300">2</span></span>         |
|<span data-ttu-id="34f20-301">部署</span><span class="sxs-lookup"><span data-stu-id="34f20-301">Subsidiary</span></span>   |<span data-ttu-id="34f20-302">部署ポリシー</span><span class="sxs-lookup"><span data-stu-id="34f20-302">Subsidiary policy</span></span>        |<span data-ttu-id="34f20-303">3</span><span class="sxs-lookup"><span data-stu-id="34f20-303">3</span></span>        |

<span data-ttu-id="34f20-304">この例では、グループから Teams 会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="34f20-304">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="34f20-305">グループのポリシーの割り当てを変更する</span><span class="sxs-lookup"><span data-stu-id="34f20-305">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="34f20-306">[Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) コマンドレットは間もなく使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="34f20-306">The [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="34f20-307">それまでの間、グループ ポリシーの割り当てを変更するには、現在のポリシーの割り当てをグループから削除して、新しいポリシーの割り当てを追加します。</span><span class="sxs-lookup"><span data-stu-id="34f20-307">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="34f20-308">ポリシーをグループに割り当てたら、[Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) コマンドレットを使用して、グループのポリシーの割り当てを次のように変更できます:</span><span class="sxs-lookup"><span data-stu-id="34f20-308">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="34f20-309">ランク付けを変更する</span><span class="sxs-lookup"><span data-stu-id="34f20-309">Change the ranking</span></span>
- <span data-ttu-id="34f20-310">特定のポリシーの種類のポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="34f20-310">Change the policy of a given policy type</span></span>
- <span data-ttu-id="34f20-311">特定のポリシーの種類のポリシーとランク付けを変更する</span><span class="sxs-lookup"><span data-stu-id="34f20-311">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="34f20-312">この例では、グループの Teams コール パーク ポリシーを、SupportCallPark という名前のポリシーに変更し、割り当てのランクを 3 に変更します。</span><span class="sxs-lookup"><span data-stu-id="34f20-312">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="34f20-313">ユーザーの有効なポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="34f20-313">Change the effective policy for a user</span></span>

<span data-ttu-id="34f20-314">これは、ポリシーを直接割り当てるユーザーの有効なポリシーを変更する方法の例です。</span><span class="sxs-lookup"><span data-stu-id="34f20-314">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="34f20-315">最初に、[Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) コマンドレットを `PolicySource` パラメーターと共に使用して、ユーザーに関連付けられた Teams 会議ブロードキャスト ポリシーの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="34f20-315">First, we use the [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the `PolicySource` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="34f20-316">出力には、Employee Events という名前の Teams 会議ブロードキャスト ポリシーがユーザーに直接割り当てられていることが示されています。これは、ユーザーが属するグループに割り当てられている Vendor Live Events という名前のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-316">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="34f20-317">次に、ユーザーから Employee Events policy を削除します。</span><span class="sxs-lookup"><span data-stu-id="34f20-317">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="34f20-318">つまり、ユーザーに Teams 会議ブロードキャスト ポリシーが直接割り当てられなくなったことを意味し、ユーザーが属するグループに割り当てられている Vendor Live Events policy を継承します。</span><span class="sxs-lookup"><span data-stu-id="34f20-318">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="34f20-319">この操作を行うには、Skype for Business PowerShell モジュールの次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="34f20-319">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="34f20-320">Teams PowerShell モジュールで次のコマンドレットを使用して、バッチ ポリシーの割り当て ($users は指定したユーザーの一覧) を使用して大規模にこれを行います。</span><span class="sxs-lookup"><span data-stu-id="34f20-320">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="34f20-321">ポリシーをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-321">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="34f20-322">管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="34f20-322">Use the admin center</span></span>

<span data-ttu-id="34f20-323">ポリシーをユーザーに一括で割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="34f20-323">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="34f20-324">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-324">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>

2. <span data-ttu-id="34f20-325">ポリシーを割り当てるユーザーを検索するか、ビューをフィルター処理して必要なユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="34f20-325">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>

3. <span data-ttu-id="34f20-326">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-326">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="34f20-327">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34f20-327">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>

4. <span data-ttu-id="34f20-328">[設定 **の編集]** を選択し、必要な変更を行い、[適用] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="34f20-328">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="34f20-329">ポリシー割り当ての状態を表示するには、[適用] を選択した後に [ユーザー] ページの上部に表示されるバナーで、[アクティビティ ログ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="34f20-329">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="34f20-330">または、管理センターの左側のナビゲーションMicrosoft Teamsダッシュボード] に移動し、[アクティビティログ] で[詳細の表示]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="34f20-330">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="34f20-331">アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-331">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="34f20-332">詳細については、「[アクティビティ ログでポリシーの割り当てを表示する](activity-log.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34f20-332">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="34f20-333">PowerShell メソッドを使用する</span><span class="sxs-lookup"><span data-stu-id="34f20-333">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="34f20-334">現在、PowerShell を使用したバッチ ポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="34f20-334">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="34f20-335">サポートされているポリシー タイプの一覧については、[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34f20-335">See [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="34f20-336">バッチ ポリシーの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="34f20-336">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="34f20-337">[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、割り当てる一群のユーザーおよびポリシーを送信します。</span><span class="sxs-lookup"><span data-stu-id="34f20-337">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="34f20-338">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="34f20-339">その後、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチの割り当ての進捗状況と状態を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="34f20-339">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="34f20-340">ユーザーをオブジェクト ID またはセッション開始プロトコル (SIP) アドレスで指定します。</span><span class="sxs-lookup"><span data-stu-id="34f20-340">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="34f20-341">多くの場合、ユーザーの SIP アドレスの値はユーザー プリンシパル名 (UPN) またはメール アドレスと同じですが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="34f20-341">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="34f20-342">ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="34f20-342">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="34f20-343">バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-343">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="34f20-344">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="34f20-344">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="34f20-345">最適な結果を得る場合は、一度に複数のバッチを送信しない。</span><span class="sxs-lookup"><span data-stu-id="34f20-345">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="34f20-346">さらにバッチを送信する前に、バッチが処理を完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="34f20-346">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="34f20-347">PowerShell モジュールをインストールTeams接続する</span><span class="sxs-lookup"><span data-stu-id="34f20-347">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="34f20-348">以下を実行して、[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="34f20-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="34f20-349">バージョン 1.0.5 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34f20-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="34f20-350">以下を実行して Teams に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="34f20-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="34f20-351">メッセージが表示されたら、管理者の資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="34f20-351">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="34f20-352">Azure AD PowerShell for Graph モジュールをインストールして接続する (オプション)</span><span class="sxs-lookup"><span data-stu-id="34f20-352">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="34f20-353">[Azure AD PowerShell for Graph](/powershell/azure/active-directory/install-adv2)モジュール (まだインストールしていない場合) をダウンロードしてインストールし、Azure AD に接続して、組織内のユーザーの一覧を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="34f20-353">You might also want to [download and install the Azure AD PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="34f20-354">以下を実行して、Azure AD に接続します。</span><span class="sxs-lookup"><span data-stu-id="34f20-354">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="34f20-355">メッセージが表示されたら、Teams に接続するために使用したのと同じ管理者資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="34f20-355">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="34f20-356">ユーザーのバッチにセットアップ ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-356">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="34f20-357">この例では [、New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、HR App Setup Policy という名前のアプリ セットアップ ポリシーを Users_ids.txt ファイルに一覧表示されているユーザーのバッチに割り当てします。</span><span class="sxs-lookup"><span data-stu-id="34f20-357">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.txt file.</span></span>

```powershell
$users_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="34f20-358">この例では、Azure AD に接続してユーザーのコレクションを取得し、SIP アドレスを使用して指定されたユーザーのバッチに New Hire Messaging Policy という名前のメッセージ ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="34f20-358">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="34f20-359">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="34f20-359">Get the status of a batch assignment</span></span>

<span data-ttu-id="34f20-360">以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの `New-CsBatchPolicyAssignmentOperation` コマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="34f20-360">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the `New-CsBatchPolicyAssignmentOperation` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="34f20-361">エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、`UserState` プロパティにあるエラーに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="34f20-361">If the output shows that an error occurred, run the following to get more information about errors, which are in the `UserState` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="34f20-362">詳細については、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34f20-362">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="34f20-363">ポリシー パッケージをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-363">Assign a policy package to users</span></span>

<span data-ttu-id="34f20-364">Teams のポリシー パッケージは、組織内で同じまたは類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="34f20-364">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="34f20-365">各ポリシー パッケージは、ユーザーの役割に合わせて設計されており、その役割の一般的なアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="34f20-365">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="34f20-366">ポリシー パッケージの例としては、教育機関 (教師) パッケージと医療機関 (医療従事者) パッケージがあります。</span><span class="sxs-lookup"><span data-stu-id="34f20-366">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="34f20-367">詳細については、「[Teams でポリシー パッケージを管理する](manage-policy-packages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34f20-367">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="34f20-368">ポリシー パッケージを 1 人のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-368">Assign a policy package to one user</span></span>

1. <span data-ttu-id="34f20-369">管理センターの左側のMicrosoft Teams、[ユーザー] に移動し、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-369">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>

2. <span data-ttu-id="34f20-370">ユーザーのページで 、[ポリシー]を選択し、[ポリシーパッケージ] の横にある [編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="34f20-370">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>

3. <span data-ttu-id="34f20-371">[ポリシー パッケージ **の割り** 当て] ウィンドウで、割り当てるパッケージを選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="34f20-371">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="34f20-372">ポリシー パッケージを複数のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-372">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="34f20-373">Microsoft Teams 管理センターの左側のナビゲーションで **[ポリシー パッケージ]** に移動し、パッケージ名の左側をクリックして、割り当てるポリシー パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-373">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="34f20-374">**[ユーザーを管理する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-374">Select **Manage users**.</span></span>

3. <span data-ttu-id="34f20-375">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="34f20-375">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="34f20-376">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="34f20-376">Repeat this step for each user that you want to add.</span></span>

4. <span data-ttu-id="34f20-377">ユーザーの追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-377">When you're finished adding users, select **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="34f20-378">ポリシー パッケージをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-378">Assign a policy package to a group</span></span>

<span data-ttu-id="34f20-379">グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="34f20-379">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="34f20-380">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-380">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="34f20-381">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-381">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="34f20-382">グループへのポリシー パッケージの割り当ては、最大 50,000 人のユーザーのグループに対して推奨されますが、大規模なグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="34f20-382">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="34f20-383">ポリシー パッケージを割り当てると、そのポリシーはすぐにグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="34f20-383">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="34f20-384">ただし、グループのメンバーへのポリシー割り当ての反映はバックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="34f20-384">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="34f20-385">ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="34f20-385">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f20-386">使用を開始する前に、[優先規則](#precedence-rules)と[グループ割り当てのランク付け](#group-assignment-ranking)を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="34f20-386">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="34f20-387">この記事の前半の「[グループへのポリシーの割り当てについて知っておくべきこと](#what-you-need-to-know-about-policy-assignment-to-groups)」の概念を必ず読み、理解してください。</span><span class="sxs-lookup"><span data-stu-id="34f20-387">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="34f20-388">管理センターでユーザーのグループにポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-388">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="34f20-389">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="34f20-389">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="34f20-390">左側のナビゲーションで、ポリシー パッケージ ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="34f20-390">In the left navigation, go to the policy package page.</span></span>

3. <span data-ttu-id="34f20-391">グループ ポリシーの割り当て タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-391">Select the Group policy assignment tab.</span></span>

4. <span data-ttu-id="34f20-392">[ **グループの追加]** を選択し、[グループにポリシー パッケージを割り当てる] ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="34f20-392">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    1. <span data-ttu-id="34f20-393">ポリシー パッケージを割り当てるグループを検索して追加します。</span><span class="sxs-lookup"><span data-stu-id="34f20-393">Search for and add the group you want to assign the policy package to.</span></span>
    
    1. <span data-ttu-id="34f20-394">ポリシー パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-394">Select a policy package.</span></span>
    
    1. <span data-ttu-id="34f20-395">ポリシーの種類ごとにランク付けを設定します。</span><span class="sxs-lookup"><span data-stu-id="34f20-395">Set the ranking for each policy type.</span></span>
    
    1. <span data-ttu-id="34f20-396">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="34f20-396">Select **Apply**.</span></span>
    
    ![グループ ポリシーの割り当てを表示する](media/group-pkg-assignment.png)

5. <span data-ttu-id="34f20-398">特定のポリシーの種類のランク付けを管理するには、特定のポリシー ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="34f20-398">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>

6. <span data-ttu-id="34f20-399">ポリシー パッケージをグループに再割り当てするには、最初にグループ ポリシーの割り当てを削除します。</span><span class="sxs-lookup"><span data-stu-id="34f20-399">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="34f20-400">次に、上記の手順に従って、ポリシー パッケージをグループに割り当てします。</span><span class="sxs-lookup"><span data-stu-id="34f20-400">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="34f20-401">PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="34f20-401">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="34f20-402">PowerShell モジュールTeams取得する</span><span class="sxs-lookup"><span data-stu-id="34f20-402">Get the Teams PowerShell module</span></span>

<span data-ttu-id="34f20-403">段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34f20-403">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="34f20-404">ポリシー パッケージをユーザーのグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-404">Assign a policy package to a group of users</span></span>

<span data-ttu-id="34f20-405">[Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment)コマンドレットを使用して、ポリシー パッケージをグループに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="34f20-405">Use the [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="34f20-406">オブジェクト ID、SIP アドレス、または電子メール アドレスを使用して、グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="34f20-406">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="34f20-407">ポリシー パッケージを割り当てる場合は、ポリシー パッケージの各ポリシーの種類に対して[グループ割り当てのランク付け](#group-assignment-ranking)を指定します。</span><span class="sxs-lookup"><span data-stu-id="34f20-407">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span>

<span data-ttu-id="34f20-408">この例では、Education_Teacher ポリシー パッケージをグループに割り当て、TeamsAppSetupPolicy と TeamsMeetingBroadcastPolicy には 1 のランク付け、TeamsMeetingPolicy には 2 のランク付けを行います。</span><span class="sxs-lookup"><span data-stu-id="34f20-408">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="34f20-409">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-409">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="34f20-410">バッチ ポリシー パッケージの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシー パッケージを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="34f20-410">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="34f20-411">[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、割り当てる一群のユーザーおよびポリシー パッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="34f20-411">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="34f20-412">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-412">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="34f20-413">その後、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチの割り当ての進捗状況と状態を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="34f20-413">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="34f20-414">ユーザーをオブジェクト ID またはセッション開始プロトコル (SIP) アドレスで指定します。</span><span class="sxs-lookup"><span data-stu-id="34f20-414">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="34f20-415">ユーザーの SIP アドレスの値は、多くの場合、ユーザー プリンシパル名 (UPN) またはメール アドレスと同じですが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="34f20-415">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="34f20-416">ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="34f20-416">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="34f20-417">バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="34f20-417">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="34f20-418">バッチには最大 5,000 人のユーザーが含まれる。</span><span class="sxs-lookup"><span data-stu-id="34f20-418">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="34f20-419">最適な結果を得る場合は、一度に複数のバッチを送信しない。</span><span class="sxs-lookup"><span data-stu-id="34f20-419">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="34f20-420">さらにバッチを送信する前に、バッチが処理を完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="34f20-420">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="34f20-421">PowerShell モジュールTeams使用する</span><span class="sxs-lookup"><span data-stu-id="34f20-421">Use the Teams PowerShell module</span></span>

<span data-ttu-id="34f20-422">以下を実行して、(まだインストールされていない場合は) [Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="34f20-422">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="34f20-423">バージョン 1.0.5 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34f20-423">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="34f20-424">以下を実行して Teams に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="34f20-424">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="34f20-425">メッセージが表示されたら、管理者の資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="34f20-425">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="34f20-426">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="34f20-426">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="34f20-427">この例では、[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、ユーザーのバッチに Education_PrimaryStudent ポリシー パッケージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="34f20-427">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="34f20-428">バッチ割り当ての状態を確認する</span><span class="sxs-lookup"><span data-stu-id="34f20-428">See the status of a batch assignment</span></span>

<span data-ttu-id="34f20-429">以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの `New-CsBatchPolicyAssignmentOperation` コマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="34f20-429">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the `New-CsBatchPolicyAssignmentOperation` cmdlet for a given batch.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="34f20-430">エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、`UserState` プロパティにあるエラーに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="34f20-430">If the output shows that an error occurred, run the following to get more information about errors, which are in the `UserState` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="34f20-431">詳細については、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34f20-431">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="34f20-432">関連トピック</span><span class="sxs-lookup"><span data-stu-id="34f20-432">Related topics</span></span>

[<span data-ttu-id="34f20-433">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="34f20-433">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
