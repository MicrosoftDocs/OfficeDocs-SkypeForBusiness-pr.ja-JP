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
ms.openlocfilehash: ae1099fc1977596aaef2b2e782140d0eca37e2b2
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262700"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="90c97-103">Microsoft Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="90c97-104">管理者は、ポリシーを使用して、組織のユーザーが利用できる Teams 機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="90c97-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="90c97-105">たとえば、ほんの一例を挙げると、通話ポリシー、会議ポリシー、メッセージ ポリシーなどがあります。</span><span class="sxs-lookup"><span data-stu-id="90c97-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="90c97-106">組織には、固有のニーズを持つユーザーの種類が異なります。</span><span class="sxs-lookup"><span data-stu-id="90c97-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="90c97-107">作成して割り当てるカスタム ポリシーを使用すると、それらのニーズに基づいて、さまざまなユーザー セットにポリシー設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="90c97-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="90c97-108">組織のポリシーを簡単に管理するために、Teams にはユーザーにポリシーを割り当てる方法がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="90c97-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="90c97-109">ポリシーをユーザーに直接割り当てる。個別に割り当てるか、バッチ割り当てを通じて規模を調整するか、ユーザーがメンバーであるグループに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="90c97-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="90c97-110">ポリシー パッケージを使用して、ポリシーの既定のコレクションを、同様の役割を持つ組織内のユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="90c97-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="90c97-111">選択するオプションは、管理するポリシーの数と、ポリシーを割り当てるユーザーの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="90c97-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="90c97-112">グローバル (組織全体の既定) ポリシーは、組織内で最も多くのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="90c97-113">特別なポリシーを必要とするユーザーにのみポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="90c97-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="90c97-114">この記事では、ユーザーにポリシーを割り当てるさまざまな方法と、何をいつ使用するかについての推奨シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="90c97-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="90c97-115">どのポリシーが優先されますか?</span><span class="sxs-lookup"><span data-stu-id="90c97-115">Which policy takes precedence?</span></span>

<span data-ttu-id="90c97-116">ユーザーには、ポリシーの種類ごとに 1 つの有効なポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="90c97-116">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="90c97-117">ユーザーに直接ポリシーが割り当て済みで、同じ種類のポリシーが割り当てられている 1 つ以上のグループのメンバーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90c97-117">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="90c97-118">このようなシナリオでは、どのポリシーが優先されますか?</span><span class="sxs-lookup"><span data-stu-id="90c97-118">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="90c97-119">ユーザーの有効なポリシーは、次の優先規則に従って決定されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-119">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="90c97-120">ユーザーに直接ポリシーが割り当てられている場合 （個別に、またはバッチ割り当てによって）、そのポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-120">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="90c97-121">次の視覚的な例では、ユーザーの効果的なポリシーは、ユーザーに直接割り当てられる、Square 会議ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="90c97-121">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![直接割り当てられたポリシーの優先順位を示す図](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="90c97-123">ユーザーに特定の種類のポリシーが直接割り当てられていない場合は、そのユーザーがメンバーになっているグループに割り当てられているポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-123">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="90c97-124">ユーザーが複数のグループのメンバーである場合、特定のポリシーの種類に対して、[グループ割り当てのランク付け](#group-assignment-ranking) が最も高いポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-124">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="90c97-125">この視覚的な例では、ユーザーの有効なポリシーは Exec Teams と HD ポリシーです。このポリシーは、ユーザーがメンバーであり、同じポリシーの種類のポリシーも割り当てられている他のグループに対して、最も高い割り当てランクを持っています。</span><span class="sxs-lookup"><span data-stu-id="90c97-125">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![グループから継承されたポリシーの優先順位を示す図](media/assign-policies-example-group.png)

<span data-ttu-id="90c97-127">ユーザーが直接ポリシーを割り当てられていない場合や、ポリシーが割り当てられているグループのメンバーではない場合、ユーザーはそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="90c97-127">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="90c97-128">次に、視覚的な例を示します。</span><span class="sxs-lookup"><span data-stu-id="90c97-128">Here's a visual example.</span></span>

![グローバル ポリシーの優先順位を示す図](media/assign-policies-example-global.png)

<span data-ttu-id="90c97-130">詳細については、「[優先規則](#precedence-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c97-130">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="90c97-131">ポリシーを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="90c97-131">Ways to assign policies</span></span>

<span data-ttu-id="90c97-132">これは、ユーザーにポリシーを割り当てる方法と、それぞれに推奨されるシナリオの概要です。</span><span class="sxs-lookup"><span data-stu-id="90c97-132">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="90c97-133">詳細については、リンクを選択してください。</span><span class="sxs-lookup"><span data-stu-id="90c97-133">Select the links to learn more.</span></span>

<span data-ttu-id="90c97-134">個々のユーザーまたはグループにポリシーを割り当てる前に、[グローバルな （組織全体の既定の） ポリシーを設定して](#set-the-global-policies)、それらが組織内の最大数のユーザーに適用されるようにします。</span><span class="sxs-lookup"><span data-stu-id="90c97-134">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="90c97-135">グローバル ポリシーを設定したら、特別なポリシーを必要とするユーザーにのみポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="90c97-135">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="90c97-136">操作</span><span class="sxs-lookup"><span data-stu-id="90c97-136">Do this</span></span>  |<span data-ttu-id="90c97-137">条件...</span><span class="sxs-lookup"><span data-stu-id="90c97-137">If...</span></span>  | <span data-ttu-id="90c97-138">使用する技術...</span><span class="sxs-lookup"><span data-stu-id="90c97-138">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="90c97-139">ポリシーを個々のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-139">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="90c97-140">Teams を初めて使用する場合、1 つまたはいくつかのポリシーを少数のユーザーに割り当てるだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="90c97-140">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="90c97-141">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="90c97-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>
|[<span data-ttu-id="90c97-142">ポリシーをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-142">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="90c97-143">ユーザーのグループ メンバーシップに基づいてポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="90c97-143">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="90c97-144">たとえば、セキュリティ グループまたは配布リストのすべてのユーザーにポリシーを割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="90c97-144">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="90c97-145">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="90c97-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="90c97-146">ポリシーをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-146">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="90c97-147">多数のユーザーにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="90c97-147">Assign policies to large sets of users.</span></span> <span data-ttu-id="90c97-148">たとえば、一度に数百または数千人のユーザーにポリシーを割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="90c97-148">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="90c97-149">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="90c97-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="90c97-150">ポリシー パッケージをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-150">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  |<span data-ttu-id="90c97-151">同じ役割または同様の役割を持つ組織内の特定のユーザー セットに複数のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90c97-151">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="90c97-152">たとえば、学校の教師に教育 (教師) ポリシー パッケージを割り当て、チャット、通話、会議へのフル アクセス権を与えます。</span><span class="sxs-lookup"><span data-stu-id="90c97-152">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="90c97-153">Education (中等学生) ポリシー パッケージを中学生に割り当て、プライベート通話などの特定の機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="90c97-153">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="90c97-154">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="90c97-154">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="90c97-155">[ポリシー パッケージをグループに割り当てる](#assign-a-policy-package-to-a-group) (プライベート プレビュー)</span><span class="sxs-lookup"><span data-stu-id="90c97-155">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="90c97-156">同じ役割または同様の役割を持つ組織内のユーザーのグループに複数のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90c97-156">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="90c97-157">たとえば、セキュリティ グループまたは配布リスト内のすべてのユーザーにポリシー パッケージを割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="90c97-157">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="90c97-158">Microsoft Teams 管理センター (近日公開予定) または Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="90c97-158">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="90c97-159">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-159">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="90c97-160">同じ役割または同様の役割を持つ組織内のユーザーのバッチに複数のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90c97-160">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="90c97-161">たとえば、バッチ割り当てを使用して、学校内のすべての教師に教育 (教師) ポリシー パッケージを割り当て、チャット、通話、会議へのフル アクセス権を与えます。</span><span class="sxs-lookup"><span data-stu-id="90c97-161">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="90c97-162">プライベート通話などの特定の機能を制限するために、Education (中等学生) ポリシー パッケージをセカンダリ 学生のバッチに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="90c97-162">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="90c97-163">Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="90c97-163">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="90c97-164">グローバル ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="90c97-164">Set the global policies</span></span>

<span data-ttu-id="90c97-165">次の手順に従って、ポリシーの種類ごとにグローバルな (組織全体の既定の) ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="90c97-165">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="90c97-166">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="90c97-166">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="90c97-167">Microsoft Teams 管理センターの左側のナビゲーションで、更新するポリシー タイプのポリシー ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="90c97-167">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="90c97-168">たとえば、**Teams** > **Teams ポリシー**、**会議** > **会議ポリシー**、**メッセージ ポリシー**、または **音声** > **通話ポリシー** です。</span><span class="sxs-lookup"><span data-stu-id="90c97-168">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="90c97-169">現在の設定を表示するには、**グローバルな (組織全体の既定の)** ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-169">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="90c97-170">必要に応じてポリシーを更新し、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-170">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="90c97-171">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="90c97-171">Using PowerShell</span></span>

<span data-ttu-id="90c97-172">PowerShell を使用してグローバル ポリシーを設定するには、グローバル識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="90c97-172">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="90c97-173">まず、現在のグローバル ポリシーを確認して、変更する設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="90c97-173">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="90c97-174">次に、必要に応じてグローバル ポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="90c97-174">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="90c97-175">変更する設定の値を指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="90c97-175">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="90c97-176">ポリシーを個々のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-176">Assign a policy to individual users</span></span>

<span data-ttu-id="90c97-177">個々のユーザーまたは一度に少数のユーザーにポリシーを割り当てるには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="90c97-177">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="90c97-178">Microsoft Teams 管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="90c97-178">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="90c97-179">ポリシーをグループに割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="90c97-179">To assign a policy to a user:</span></span>

1. <span data-ttu-id="90c97-180">Microsoft Teams 管理センターの左側のナビゲーションで、[ユーザー ] に移動し、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-180">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="90c97-181">ユーザー名の左側をクリックしてユーザーを選択し、[設定の編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90c97-181">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="90c97-182">割り当てるポリシーを選択し、[適用] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="90c97-182">Select the policy you want to assign, and then select **Apply**.</span></span>

<span data-ttu-id="90c97-183">または、次の操作も実行できます:</span><span class="sxs-lookup"><span data-stu-id="90c97-183">Or, you can also do the following:</span></span>

1. <span data-ttu-id="90c97-184">Microsoft Teams 管理センターの左側のナビゲーションで、ポリシー ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="90c97-184">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="90c97-185">ポリシー名の左側をクリックして割り当てるポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="90c97-185">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="90c97-186">**[ユーザーを管理する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-186">Select **Manage users**.</span></span>
4. <span data-ttu-id="90c97-187">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="90c97-187">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="90c97-188">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="90c97-188">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="90c97-189">ユーザーの追加が完了したら、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-189">When you're finished adding users, select **Apply**.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="90c97-190">PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="90c97-190">Use PowerShell</span></span>

<span data-ttu-id="90c97-191">各ポリシー タイプには、それを管理するための独自のコマンドレットのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="90c97-191">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="90c97-192">特定のポリシー タイプに ```Grant-``` コマンドレットを使用して、ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90c97-192">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="90c97-193">たとえば、```Grant-CsTeamsMeetingPolicy``` コマンドレットを使用して、Teams 会議ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90c97-193">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="90c97-194">これらのコマンドレットは Teams PowerShell モジュールに含まれており、Skype for Business コマンドレット リファレンス [に記載されています](/powershell/skype/intro?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="90c97-194">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="90c97-195">[Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック リリース (まだインストールしていない場合) をダウンロードしてインストールし、次のコマンドを実行して接続します。</span><span class="sxs-lookup"><span data-stu-id="90c97-195">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="90c97-196">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="90c97-196">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="90c97-197">最新の [Teams PowerShell パブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)をご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="90c97-197">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="90c97-198">この例では、Student Meeting Policy という名前の Teams 会議ポリシーを、Reda というユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="90c97-198">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="90c97-199">詳細については、「[PowerShell によるポリシーの管理](teams-powershell-managing-teams.md#manage-policies-via-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c97-199">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="90c97-200">ポリシーをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-200">Assign a policy to a group</span></span>

<span data-ttu-id="90c97-201">グループにポリシーを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="90c97-201">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="90c97-202">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-202">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="90c97-203">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-203">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="90c97-204">ポリシーをグループに割り当てるのは、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="90c97-204">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="90c97-205">ポリシーを割り当てると、そのポリシーはすぐにグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="90c97-205">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="90c97-206">ただし、グループのメンバーへのポリシー割り当ての反映はバックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="90c97-206">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="90c97-207">ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="90c97-207">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="90c97-208">グループ ポリシーの割り当ては、グループの直接メンバーであるユーザーにのみ伝達されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-208">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="90c97-209">割り当ては、入れ子になったグループのメンバーには伝達されません。</span><span class="sxs-lookup"><span data-stu-id="90c97-209">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="90c97-210">グループへのポリシーの割り当てについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="90c97-210">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="90c97-211">使用を開始する前に、優先規則とグループ割り当てのランク付けを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="90c97-211">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="90c97-212">優先規則</span><span class="sxs-lookup"><span data-stu-id="90c97-212">Precedence rules</span></span>

<span data-ttu-id="90c97-213">特定のポリシーの種類について、ユーザーの有効なポリシーは、次に従って決定されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-213">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="90c97-214">ユーザーに直接割り当てられているポリシーは、グループに割り当てられている同じ種類の別のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-214">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="90c97-215">言い換えると、ユーザーに特定の種類のポリシーが直接割り当てられている場合、そのユーザーはグループから同じ種類のポリシーを継承しません。</span><span class="sxs-lookup"><span data-stu-id="90c97-215">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="90c97-216">つまり、ユーザーが特定の種類のポリシーを直接割り当てられている場合は、ユーザーがグループから同じ種類のポリシーを継承する前に、そのポリシーをユーザーから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90c97-216">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="90c97-217">ユーザーに直接割り当てられたポリシーがなく、2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合、ユーザーは最も高いランク付けを持つグループ割り当てのポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="90c97-217">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="90c97-218">ユーザーがポリシーが割り当てられているグループのメンバーではない場合、ユーザーにそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="90c97-218">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="90c97-219">ユーザーの有効なポリシーは、次のルールに従って更新されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-219">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="90c97-220">ポリシーが割り当てられているグループにユーザーが追加または削除された場合。</span><span class="sxs-lookup"><span data-stu-id="90c97-220">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="90c97-221">ポリシーはグループから割り当て解除されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-221">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="90c97-222">ユーザーに直接割り当てられているポリシーは削除されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-222">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="90c97-223">グループ割り当てのランク付け</span><span class="sxs-lookup"><span data-stu-id="90c97-223">Group assignment ranking</span></span>

<span data-ttu-id="90c97-224">ポリシーをグループに割り当てるときは、グループ割り当てのランクを指定します。</span><span class="sxs-lookup"><span data-stu-id="90c97-224">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="90c97-225">これは、ユーザーが 2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合に、ユーザーが有効なポリシーとして継承する必要があるポリシーを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-225">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="90c97-226">グループ割り当てのランク付けは、同じ種類の別のグループ割り当てに関連しています。</span><span class="sxs-lookup"><span data-stu-id="90c97-226">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="90c97-227">たとえば、通話ポリシーを 2 つのグループに割り当てる場合は、1 つの割り当てのランクを 1 に設定し、もう 1 つの割り当てを 2 に設定します。1 が最高のランクです。</span><span class="sxs-lookup"><span data-stu-id="90c97-227">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="90c97-228">グループ割り当てのランク付けは、継承に関する他のグループ メンバーシップよりも重要または関連性の高いグループ メンバーシップを示します。</span><span class="sxs-lookup"><span data-stu-id="90c97-228">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships regarding inheritance.</span></span>

<span data-ttu-id="90c97-229">たとえば、店舗の従業員と管理者の 2 つのグループがあるとします。</span><span class="sxs-lookup"><span data-stu-id="90c97-229">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="90c97-230">両方のグループには、それぞれ Teams 通話ポリシー、店舗従業員通話ポリシー、および店舗管理者通話ポリシーが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="90c97-230">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="90c97-231">両方のグループに属する店舗管理者の場合、管理者としての役割は従業員としての役割よりも重要であるため、店舗管理者グループに割り当てられている通話ポリシーにより高いランク付けを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="90c97-231">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="90c97-232">グループ</span><span class="sxs-lookup"><span data-stu-id="90c97-232">Group</span></span> |<span data-ttu-id="90c97-233">Teams 通話ポリシー名</span><span class="sxs-lookup"><span data-stu-id="90c97-233">Teams calling policy name</span></span>  |<span data-ttu-id="90c97-234">ランク</span><span class="sxs-lookup"><span data-stu-id="90c97-234">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="90c97-235">店舗管理者</span><span class="sxs-lookup"><span data-stu-id="90c97-235">Store Managers</span></span>   |<span data-ttu-id="90c97-236">店舗管理者通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="90c97-236">Store Managers Calling Policy</span></span>         |<span data-ttu-id="90c97-237">1</span><span class="sxs-lookup"><span data-stu-id="90c97-237">1</span></span>|
|<span data-ttu-id="90c97-238">店舗従業員</span><span class="sxs-lookup"><span data-stu-id="90c97-238">Store Employees</span></span>    |<span data-ttu-id="90c97-239">店舗従業員通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="90c97-239">Store Employees Calling Policy</span></span>      |<span data-ttu-id="90c97-240">2</span><span class="sxs-lookup"><span data-stu-id="90c97-240">2</span></span>|

<span data-ttu-id="90c97-241">ランクを指定しないと、ポリシーの割り当てに最も低いランクが与えられます。</span><span class="sxs-lookup"><span data-stu-id="90c97-241">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="90c97-242">Teams 管理センターの場合</span><span class="sxs-lookup"><span data-stu-id="90c97-242">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="90c97-243">現在、Microsoft Teams 管理センターを使用したグループへのポリシー割り当ては、Teams 通話ポリシー、Teams コール パーク ポリシー、Teams ポリシー、Teams ライブ イベント ポリシー、Teams 会議ポリシー、Teams メッセージ ポリシーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="90c97-243">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="90c97-244">他のポリシーの種類については、PowerShell を使用してください。</span><span class="sxs-lookup"><span data-stu-id="90c97-244">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="90c97-245">Microsoft Teams 管理センターの左側のナビゲーションで、ポリシーの種類のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="90c97-245">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="90c97-246">たとえば、**会議** > **会議ポリシー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="90c97-246">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="90c97-247">**グループ ポリシーの割り当て** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-247">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="90c97-248">**[グループの追加]** を選択し、**[ポリシーをグループに割り当てる]** ウィンドウで、次の操作を行います:</span><span class="sxs-lookup"><span data-stu-id="90c97-248">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="90c97-249">ポリシーを割り当てるグループを検索し、追加します。</span><span class="sxs-lookup"><span data-stu-id="90c97-249">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="90c97-250">グループ割り当てのランク付けを設定します。</span><span class="sxs-lookup"><span data-stu-id="90c97-250">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="90c97-251">割り当てるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-251">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="90c97-252">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-252">Select **Apply**.</span></span>

<span data-ttu-id="90c97-253">グループ ポリシーの割り当てを削除するには、ポリシー ページの **[グループ ポリシーの割り当て]** タブで、グループの割り当てを選び、**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-253">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="90c97-254">グループ割り当てのランク付けを変更するには、最初にグループ ポリシーの割り当てを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90c97-254">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="90c97-255">次に、上記の手順に従ってポリシーをグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90c97-255">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="90c97-256">PowerShell オプションを使用する</span><span class="sxs-lookup"><span data-stu-id="90c97-256">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="90c97-257">現在、PowerShell を使用したグループへのポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="90c97-257">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="90c97-258">サポートされているポリシー タイプの一覧については、[New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c97-258">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="90c97-259">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="90c97-259">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="90c97-260">段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c97-260">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="90c97-261">ポリシーをユーザーのグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-261">Assign a policy to a group of users</span></span>

<span data-ttu-id="90c97-262">[New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)コマンドレットを使用して、グループにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="90c97-262">Use the [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="90c97-263">オブジェクト ID、SIP アドレス、またはメール アドレスを使用してグループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="90c97-263">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="90c97-264">この例では、Retail Managers Meeting Policy という名前の Teams 会議ポリシーを、割り当てのランクが 1 のグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90c97-264">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="90c97-265">グループのポリシーの割り当てを取得する</span><span class="sxs-lookup"><span data-stu-id="90c97-265">Get policy assignments for a group</span></span>

<span data-ttu-id="90c97-266">[Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) コマンドレットを使用して、グループに割り当てられているすべてのポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="90c97-266">Use the [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="90c97-267">グループは、SIP アドレスまたはメール アドレスがポリシーの割り当てに使用された場合でも、常にグループ ID で一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-267">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="90c97-268">この例では、特定のグループに割り当てられているすべてのポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="90c97-268">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="90c97-269">この例では、Teams 会議ポリシーが割り当てられているすべてのグループを返します。</span><span class="sxs-lookup"><span data-stu-id="90c97-269">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="90c97-270">グループからポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="90c97-270">Remove a policy from a group</span></span>

<span data-ttu-id="90c97-271">[Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) コマンドレットを使用して、グループからポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="90c97-271">Use the [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="90c97-272">グループからポリシーを削除すると、そのグループに割り当てられている、ランクが低い同じ種類の他のポリシーの優先度が更新されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-272">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="90c97-273">たとえば、ランクが 2 であるポリシーを削除すると、その新しいランク付けを反映して、ランク 3 と 4 のポリシーが更新されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-273">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="90c97-274">次の 2 つの表にこの例を示します。</span><span class="sxs-lookup"><span data-stu-id="90c97-274">The following two tables show this example.</span></span>

<span data-ttu-id="90c97-275">これは、Teams 会議ポリシーのポリシー割り当てと優先順位のリストです。</span><span class="sxs-lookup"><span data-stu-id="90c97-275">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="90c97-276">グループ名</span><span class="sxs-lookup"><span data-stu-id="90c97-276">Group name</span></span>  |<span data-ttu-id="90c97-277">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="90c97-277">Policy name</span></span>  |<span data-ttu-id="90c97-278">ランク</span><span class="sxs-lookup"><span data-stu-id="90c97-278">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="90c97-279">営業</span><span class="sxs-lookup"><span data-stu-id="90c97-279">Sales</span></span>    |<span data-ttu-id="90c97-280">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="90c97-280">Sales policy</span></span>       | <span data-ttu-id="90c97-281">1</span><span class="sxs-lookup"><span data-stu-id="90c97-281">1</span></span>        |
|<span data-ttu-id="90c97-282">西部地域</span><span class="sxs-lookup"><span data-stu-id="90c97-282">West Region</span></span>     |<span data-ttu-id="90c97-283">西部地域ポリシー</span><span class="sxs-lookup"><span data-stu-id="90c97-283">West Region policy</span></span>         |<span data-ttu-id="90c97-284">2</span><span class="sxs-lookup"><span data-stu-id="90c97-284">2</span></span>         |
|<span data-ttu-id="90c97-285">部門</span><span class="sxs-lookup"><span data-stu-id="90c97-285">Division</span></span>    |<span data-ttu-id="90c97-286">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="90c97-286">Division policy</span></span>         |<span data-ttu-id="90c97-287">3</span><span class="sxs-lookup"><span data-stu-id="90c97-287">3</span></span>         |
|<span data-ttu-id="90c97-288">部署</span><span class="sxs-lookup"><span data-stu-id="90c97-288">Subsidiary</span></span>   |<span data-ttu-id="90c97-289">部署ポリシー</span><span class="sxs-lookup"><span data-stu-id="90c97-289">Subsidiary policy</span></span>        |<span data-ttu-id="90c97-290">4</span><span class="sxs-lookup"><span data-stu-id="90c97-290">4</span></span>         |

<span data-ttu-id="90c97-291">西部地域グループから西部地域ポリシーを削除すると、ポリシーの割り当てと優先順位は次のように更新されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-291">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="90c97-292">グループ名</span><span class="sxs-lookup"><span data-stu-id="90c97-292">Group name</span></span>  |<span data-ttu-id="90c97-293">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="90c97-293">Policy name</span></span>  |<span data-ttu-id="90c97-294">ランク</span><span class="sxs-lookup"><span data-stu-id="90c97-294">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="90c97-295">営業</span><span class="sxs-lookup"><span data-stu-id="90c97-295">Sales</span></span>    |<span data-ttu-id="90c97-296">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="90c97-296">Sales policy</span></span>       | <span data-ttu-id="90c97-297">1</span><span class="sxs-lookup"><span data-stu-id="90c97-297">1</span></span>        |
|<span data-ttu-id="90c97-298">部門</span><span class="sxs-lookup"><span data-stu-id="90c97-298">Division</span></span>    |<span data-ttu-id="90c97-299">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="90c97-299">Division policy</span></span>         |<span data-ttu-id="90c97-300">2</span><span class="sxs-lookup"><span data-stu-id="90c97-300">2</span></span>         |
|<span data-ttu-id="90c97-301">部署</span><span class="sxs-lookup"><span data-stu-id="90c97-301">Subsidiary</span></span>   |<span data-ttu-id="90c97-302">部署ポリシー</span><span class="sxs-lookup"><span data-stu-id="90c97-302">Subsidiary policy</span></span>        |<span data-ttu-id="90c97-303">3</span><span class="sxs-lookup"><span data-stu-id="90c97-303">3</span></span>        |

<span data-ttu-id="90c97-304">この例では、グループから Teams 会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="90c97-304">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="90c97-305">グループのポリシーの割り当てを変更する</span><span class="sxs-lookup"><span data-stu-id="90c97-305">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="90c97-306">[Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) コマンドレットは間もなく使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="90c97-306">The [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="90c97-307">それまでの間、グループ ポリシーの割り当てを変更するには、現在のポリシーの割り当てをグループから削除して、新しいポリシーの割り当てを追加します。</span><span class="sxs-lookup"><span data-stu-id="90c97-307">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="90c97-308">ポリシーをグループに割り当てたら、[Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) コマンドレットを使用して、グループのポリシーの割り当てを次のように変更できます:</span><span class="sxs-lookup"><span data-stu-id="90c97-308">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="90c97-309">ランク付けを変更する</span><span class="sxs-lookup"><span data-stu-id="90c97-309">Change the ranking</span></span>
- <span data-ttu-id="90c97-310">特定のポリシーの種類のポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="90c97-310">Change the policy of a given policy type</span></span>
- <span data-ttu-id="90c97-311">特定のポリシーの種類のポリシーとランク付けを変更する</span><span class="sxs-lookup"><span data-stu-id="90c97-311">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="90c97-312">この例では、グループの Teams コール パーク ポリシーを、SupportCallPark という名前のポリシーに変更し、割り当てのランクを 3 に変更します。</span><span class="sxs-lookup"><span data-stu-id="90c97-312">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="90c97-313">ユーザーの有効なポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="90c97-313">Change the effective policy for a user</span></span>

<span data-ttu-id="90c97-314">これは、ポリシーを直接割り当てるユーザーの有効なポリシーを変更する方法の例です。</span><span class="sxs-lookup"><span data-stu-id="90c97-314">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="90c97-315">最初に、[Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) コマンドレットを ```PolicySource``` パラメーターと共に使用して、ユーザーに関連付けられた Teams 会議ブロードキャスト ポリシーの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="90c97-315">First, we use the [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="90c97-316">出力には、Employee Events という名前の Teams 会議ブロードキャスト ポリシーがユーザーに直接割り当てられていることが示されています。これは、ユーザーが属するグループに割り当てられている Vendor Live Events という名前のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-316">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="90c97-317">次に、ユーザーから Employee Events policy を削除します。</span><span class="sxs-lookup"><span data-stu-id="90c97-317">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="90c97-318">つまり、ユーザーに Teams 会議ブロードキャスト ポリシーが直接割り当てられなくなったことを意味し、ユーザーが属するグループに割り当てられている Vendor Live Events policy を継承します。</span><span class="sxs-lookup"><span data-stu-id="90c97-318">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="90c97-319">この操作を行うには、Skype for Business PowerShell モジュールの次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="90c97-319">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="90c97-320">Teams PowerShell モジュールで次のコマンドレットを使用して、バッチ ポリシーの割り当て (指定したユーザーの一覧$users)、この操作を大規模に行います。</span><span class="sxs-lookup"><span data-stu-id="90c97-320">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="90c97-321">ポリシーをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-321">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="90c97-322">管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="90c97-322">Use the admin center</span></span>

<span data-ttu-id="90c97-323">ポリシーをユーザーに一括で割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="90c97-323">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="90c97-324">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-324">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="90c97-325">ポリシーを割り当てるユーザーを検索するか、ビューをフィルター処理して必要なユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="90c97-325">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="90c97-326">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-326">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="90c97-327">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90c97-327">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="90c97-328">[ **設定の編集]** を選択し、必要な変更を行い、[適用] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="90c97-328">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="90c97-329">ポリシー割り当ての状態を表示するには、[適用] を選択してポリシー割り当てを送信した後、[ユーザー] ページの上部に表示されるバナーで、[アクティビティ ログ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="90c97-329">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="90c97-330">または、Microsoft Teams 管理センターの左側のナビゲーションで [ダッシュボード] に移動し、[アクティビティ ログ] で [詳細の表示]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90c97-330">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="90c97-331">アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-331">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="90c97-332">詳細については、「[アクティビティ ログでポリシーの割り当てを表示する](activity-log.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c97-332">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="90c97-333">PowerShell メソッドを使用する</span><span class="sxs-lookup"><span data-stu-id="90c97-333">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="90c97-334">現在、PowerShell を使用したバッチ ポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="90c97-334">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="90c97-335">サポートされているポリシー タイプの一覧については、[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c97-335">See [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="90c97-336">バッチ ポリシーの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="90c97-336">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="90c97-337">[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、割り当てる一群のユーザーおよびポリシーを送信します。</span><span class="sxs-lookup"><span data-stu-id="90c97-337">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="90c97-338">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="90c97-339">その後、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチの割り当ての進捗状況と状態を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="90c97-339">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="90c97-340">ユーザーをオブジェクト ID またはセッション開始プロトコル (SIP) アドレスで指定します。</span><span class="sxs-lookup"><span data-stu-id="90c97-340">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="90c97-341">多くの場合、ユーザーの SIP アドレスの値はユーザー プリンシパル名 (UPN) またはメール アドレスと同じですが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="90c97-341">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="90c97-342">ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="90c97-342">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="90c97-343">バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-343">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="90c97-344">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="90c97-344">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="90c97-345">最良の結果を得る場合は、一度に複数のバッチを送信しない。</span><span class="sxs-lookup"><span data-stu-id="90c97-345">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="90c97-346">さらにバッチを送信する前に、バッチが処理を完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="90c97-346">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="90c97-347">Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="90c97-347">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="90c97-348">以下を実行して、[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="90c97-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="90c97-349">バージョン 1.0.5 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="90c97-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="90c97-350">以下を実行して Teams に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="90c97-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="90c97-351">メッセージが表示されたら、管理者の資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="90c97-351">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="90c97-352">Azure AD PowerShell for Graph モジュールをインストールして接続する (オプション)</span><span class="sxs-lookup"><span data-stu-id="90c97-352">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="90c97-353">[Azure AD PowerShell for Graph](/powershell/azure/active-directory/install-adv2)モジュール (まだインストールしていない場合) をダウンロードしてインストールし、Azure AD に接続して、組織内のユーザーのリストを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="90c97-353">You might also want to [download and install the Azure AD PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="90c97-354">以下を実行して、Azure AD に接続します。</span><span class="sxs-lookup"><span data-stu-id="90c97-354">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="90c97-355">メッセージが表示されたら、Teams に接続するために使用したのと同じ管理者資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="90c97-355">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="90c97-356">ユーザーのバッチにセットアップ ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-356">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="90c97-357">この例では、[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、HR App Setup Policy という名前のアプリ セットアップ ポリシーを Users_ids.text ファイルに記載されているユーザーのバッチに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90c97-357">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="90c97-358">この例では、Azure AD に接続してユーザーのコレクションを取得し、SIP アドレスを使用して指定されたユーザーのバッチに New Hire Messaging Policy という名前のメッセージ ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90c97-358">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="90c97-359">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="90c97-359">Get the status of a batch assignment</span></span>

<span data-ttu-id="90c97-360">以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの ```New-CsBatchPolicyAssignmentOperation``` コマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="90c97-360">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="90c97-361">エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、```UserState``` プロパティにあるエラーに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="90c97-361">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="90c97-362">詳細については、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c97-362">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="90c97-363">ポリシー パッケージをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-363">Assign a policy package to users</span></span>

<span data-ttu-id="90c97-364">Teams のポリシー パッケージは、組織内で同じまたは類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="90c97-364">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="90c97-365">各ポリシー パッケージは、ユーザーの役割に合わせて設計されており、その役割の一般的なアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="90c97-365">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="90c97-366">ポリシー パッケージの例としては、教育機関 (教師) パッケージと医療機関 (医療従事者) パッケージがあります。</span><span class="sxs-lookup"><span data-stu-id="90c97-366">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="90c97-367">詳細については、「[Teams でポリシー パッケージを管理する](manage-policy-packages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c97-367">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="90c97-368">ポリシー パッケージを 1 人のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-368">Assign a policy package to one user</span></span>

1. <span data-ttu-id="90c97-369">Microsoft Teams 管理センターの左側のナビゲーションで、[ユーザー ] に移動し、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-369">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="90c97-370">ユーザーのページで、[ポリシー]を選択し、[ポリシー パッケージ] の横にある **[編集**] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="90c97-370">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="90c97-371">[ポリシー パッケージ **の割り当** て] ウィンドウで、割り当てるパッケージを選択し、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="90c97-371">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="90c97-372">ポリシー パッケージを複数のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-372">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="90c97-373">Microsoft Teams 管理センターの左側のナビゲーションで **[ポリシー パッケージ]** に移動し、パッケージ名の左側をクリックして、割り当てるポリシー パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-373">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="90c97-374">**[ユーザーを管理する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-374">Select **Manage users**.</span></span>
3. <span data-ttu-id="90c97-375">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="90c97-375">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="90c97-376">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="90c97-376">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="90c97-377">ユーザーの追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-377">When you're finished adding users, select **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="90c97-378">ポリシー パッケージをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-378">Assign a policy package to a group</span></span>

<span data-ttu-id="90c97-379">グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="90c97-379">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="90c97-380">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-380">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="90c97-381">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-381">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="90c97-382">最大 50,000 人のユーザーのグループには、グループへのポリシー パッケージの割り当てが推奨されますが、大規模なグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="90c97-382">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="90c97-383">ポリシー パッケージを割り当てると、そのポリシーはすぐにグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="90c97-383">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="90c97-384">ただし、グループのメンバーへのポリシー割り当ての反映はバックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="90c97-384">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="90c97-385">ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="90c97-385">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90c97-386">使用を開始する前に、[優先規則](#precedence-rules)と[グループ割り当てのランク付け](#group-assignment-ranking)を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="90c97-386">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="90c97-387">この記事の前半の「[グループへのポリシーの割り当てについて知っておくべきこと](#what-you-need-to-know-about-policy-assignment-to-groups)」の概念を必ず読み、理解してください。</span><span class="sxs-lookup"><span data-stu-id="90c97-387">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="90c97-388">管理センターでユーザーのグループにポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-388">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="90c97-389">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="90c97-389">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="90c97-390">左側のナビゲーションで、ポリシー パッケージ ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="90c97-390">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="90c97-391">グループ ポリシーの割り当て タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-391">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="90c97-392">[ **グループの追加]** を選び、[ポリシー パッケージをグループに割り当てる] ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="90c97-392">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="90c97-393">a.</span><span class="sxs-lookup"><span data-stu-id="90c97-393">a.</span></span> <span data-ttu-id="90c97-394">ポリシー パッケージを割り当てるグループを検索して追加します。</span><span class="sxs-lookup"><span data-stu-id="90c97-394">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="90c97-395">b.</span><span class="sxs-lookup"><span data-stu-id="90c97-395">b.</span></span> <span data-ttu-id="90c97-396">ポリシー パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-396">Select a policy package.</span></span>

    <span data-ttu-id="90c97-397">c.</span><span class="sxs-lookup"><span data-stu-id="90c97-397">c.</span></span> <span data-ttu-id="90c97-398">ポリシーの種類ごとにランク付けを設定します。</span><span class="sxs-lookup"><span data-stu-id="90c97-398">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="90c97-399">d.</span><span class="sxs-lookup"><span data-stu-id="90c97-399">d.</span></span> <span data-ttu-id="90c97-400">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c97-400">Select **Apply**.</span></span>

    ![グループ ポリシーの割り当てを表示する](media/group-pkg-assignment.png)

5. <span data-ttu-id="90c97-402">特定のポリシーの種類のランク付けを管理するには、特定のポリシー ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="90c97-402">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="90c97-403">ポリシー パッケージをグループに再割り当てするには、まずグループ ポリシーの割り当てを削除します。</span><span class="sxs-lookup"><span data-stu-id="90c97-403">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="90c97-404">次に、上記の手順に従って、ポリシー パッケージをグループに割り当てします。</span><span class="sxs-lookup"><span data-stu-id="90c97-404">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="90c97-405">PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="90c97-405">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="90c97-406">Teams PowerShell モジュールを取得する</span><span class="sxs-lookup"><span data-stu-id="90c97-406">Get the Teams PowerShell module</span></span>

<span data-ttu-id="90c97-407">段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c97-407">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="90c97-408">ポリシー パッケージをユーザーのグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-408">Assign a policy package to a group of users</span></span>

<span data-ttu-id="90c97-409">[Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment)コマンドレットを使用して、ポリシー パッケージをグループに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="90c97-409">Use the [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="90c97-410">オブジェクト ID、SIP アドレス、またはメール アドレスを使用してグループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="90c97-410">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="90c97-411">ポリシー パッケージを割り当てる場合は、ポリシー パッケージの各ポリシーの種類に対して[グループ割り当てのランク付け](#group-assignment-ranking)を指定します。</span><span class="sxs-lookup"><span data-stu-id="90c97-411">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span>

<span data-ttu-id="90c97-412">この例では、Education_Teacher ポリシー パッケージをグループに割り当て、TeamsAppSetupPolicy と TeamsMeetingBroadcastPolicy には 1 のランク付け、TeamsMeetingPolicy には 2 のランク付けを行います。</span><span class="sxs-lookup"><span data-stu-id="90c97-412">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="90c97-413">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-413">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="90c97-414">バッチ ポリシー パッケージの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシー パッケージを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="90c97-414">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="90c97-415">[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、割り当てる一群のユーザーおよびポリシー パッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="90c97-415">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="90c97-416">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-416">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="90c97-417">その後、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチの割り当ての進捗状況と状態を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="90c97-417">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="90c97-418">ユーザーをオブジェクト ID またはセッション開始プロトコル (SIP) アドレスで指定します。</span><span class="sxs-lookup"><span data-stu-id="90c97-418">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="90c97-419">多くの場合、ユーザーの SIP アドレスの値はユーザー プリンシパル名 (UPN) またはメール アドレスと同じですが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="90c97-419">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="90c97-420">ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="90c97-420">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="90c97-421">バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="90c97-421">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="90c97-422">バッチには最大 5,000 人のユーザーが含まれる。</span><span class="sxs-lookup"><span data-stu-id="90c97-422">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="90c97-423">最良の結果を得る場合は、一度に複数のバッチを送信しない。</span><span class="sxs-lookup"><span data-stu-id="90c97-423">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="90c97-424">さらにバッチを送信する前に、バッチが処理を完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="90c97-424">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="90c97-425">Teams PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="90c97-425">Use the Teams PowerShell module</span></span>

<span data-ttu-id="90c97-426">以下を実行して、(まだインストールされていない場合は) [Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="90c97-426">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="90c97-427">バージョン 1.0.5 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="90c97-427">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="90c97-428">以下を実行して Teams に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="90c97-428">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="90c97-429">メッセージが表示されたら、管理者の資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="90c97-429">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="90c97-430">複数のユーザーにポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="90c97-430">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="90c97-431">この例では、[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、ユーザーのバッチに Education_PrimaryStudent ポリシー パッケージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90c97-431">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="90c97-432">バッチ割り当ての状態を確認する</span><span class="sxs-lookup"><span data-stu-id="90c97-432">See the status of a batch assignment</span></span>

<span data-ttu-id="90c97-433">以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの ```New-CsBatchPolicyAssignmentOperation``` コマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="90c97-433">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="90c97-434">エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、```UserState``` プロパティにあるエラーに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="90c97-434">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="90c97-435">詳細については、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c97-435">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="90c97-436">関連トピック</span><span class="sxs-lookup"><span data-stu-id="90c97-436">Related topics</span></span>

[<span data-ttu-id="90c97-437">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="90c97-437">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
