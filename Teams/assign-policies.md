---
title: Microsoft Teams でユーザーにポリシーを割り当てる
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: ada58a9abf07e606f91d48b7ac71ba06d4c1496a
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085701"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="c8dba-103">Microsoft Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="c8dba-104">管理者は、ポリシーを使用して、組織のユーザーが利用できる Teams 機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="c8dba-105">たとえば、ほんの一例を挙げると、通話ポリシー、会議ポリシー、メッセージ ポリシーなどがあります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="c8dba-106">組織には、独自のニーズを持つさまざまなタイプのユーザーがあり、カスタム ポリシーを作成して割り当てることで、それらのニーズに応じて、さまざまなユーザーのセットにポリシー設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-106">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="c8dba-107">組織でのポリシーの管理を容易にするために、Teams はユーザーにポリシーを割り当てるいくつかの方法を提供しています。</span><span class="sxs-lookup"><span data-stu-id="c8dba-107">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="c8dba-108">個別に、一括割り当てで、またはユーザーがメンバーになっているグループを介して、ポリシーをユーザーに直接割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-108">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="c8dba-109">ポリシー パッケージを使用して、ポリシーの既定のコレクションを、同様の役割を持つ組織内のユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-109">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="c8dba-110">選択するオプションは、管理しているポリシーの数と、割り当てているユーザーの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-110">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="c8dba-111">グローバルな （組織全体の既定の） ポリシーを設定して、それらが組織内の最大数のユーザーに適用されるようにすることで、特殊なポリシーを必要とするユーザーにポリシーを割り当てるだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-111">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="c8dba-112">この記事では、ユーザーにポリシーを割り当てるさまざまな方法と、何をいつ使用するかについての推奨シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="c8dba-113">どのポリシーが優先されますか?</span><span class="sxs-lookup"><span data-stu-id="c8dba-113">Which policy takes precedence?</span></span>

<span data-ttu-id="c8dba-114">ユーザーには、ポリシーの種類ごとに 1 つの有効なポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="c8dba-115">ユーザーに直接ポリシーが割り当てられていてもかまいません。同じ種類のポリシーが割り当てられている 1 つ以上のグループのメンバーでもある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="c8dba-116">このようなシナリオでは、どのポリシーが優先されますか?</span><span class="sxs-lookup"><span data-stu-id="c8dba-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="c8dba-117">ユーザーの有効なポリシーは、次の優先規則に従って決定されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="c8dba-118">ユーザーに直接ポリシーが割り当てられている場合 （個別に、またはバッチ割り当てによって）、そのポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="c8dba-119">次の例では、ユーザーの有効なポリシーは、ユーザーに直接割り当てられている Lincoln Square の会議ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="c8dba-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![直接割り当てられたポリシーの優先順位を示す図](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="c8dba-121">ユーザーに特定の種類のポリシーが直接割り当てられていない場合は、そのユーザーがメンバーになっているグループに割り当てられているポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="c8dba-122">ユーザーが複数のグループのメンバーである場合、特定のポリシーの種類に対して、[グループ割り当てのランク付け](#group-assignment-ranking) が最も高いポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="c8dba-123">この例では、ユーザーの有効なポリシーは、Exec Teams および HD ポリシーです。このポリシーは、ユーザーがメンバーであり、同じポリシー タイプのポリシーが割り当てられている他のグループと比べて、割り当てのランクが最も高くなっています。</span><span class="sxs-lookup"><span data-stu-id="c8dba-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![グループから継承されたポリシーの優先順位を示す図](media/assign-policies-example-group.png)

<span data-ttu-id="c8dba-125">ユーザーが直接ポリシーを割り当てられていない場合や、ポリシーが割り当てられているグループのメンバーではない場合、ユーザーはそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="c8dba-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-126">Here's an example.</span></span>

![グローバル ポリシーの優先順位を示す図](media/assign-policies-example-global.png)

<span data-ttu-id="c8dba-128">詳細については、「[優先規則](#precedence-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="c8dba-129">ポリシーを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="c8dba-129">Ways to assign policies</span></span>

<span data-ttu-id="c8dba-130">これは、ユーザーにポリシーを割り当てる方法と、それぞれに推奨されるシナリオの概要です。</span><span class="sxs-lookup"><span data-stu-id="c8dba-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="c8dba-131">リンクをクリックして詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-131">Click the links to learn more.</span></span>

<span data-ttu-id="c8dba-132">個々のユーザーまたはグループにポリシーを割り当てる前に、[グローバルな （組織全体の既定の） ポリシーを設定して](#set-the-global-policies)、それらが組織内の最大数のユーザーに適用されるようにします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-132">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="c8dba-133">グローバル ポリシーが設定されると、特殊なポリシーを必要とするユーザーにポリシーを割り当てるだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-133">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="c8dba-134">操作</span><span class="sxs-lookup"><span data-stu-id="c8dba-134">Do this</span></span>  |<span data-ttu-id="c8dba-135">条件...</span><span class="sxs-lookup"><span data-stu-id="c8dba-135">If...</span></span>  | <span data-ttu-id="c8dba-136">使用する技術...</span><span class="sxs-lookup"><span data-stu-id="c8dba-136">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="c8dba-137">ポリシーを個々のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-137">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="c8dba-138">Teams を初めて使用する場合、1 つまたはいくつかのポリシーを少数のユーザーに割り当てるだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-138">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="c8dba-139">Microsoft Teams 管理センターまたは Skype for Business Online PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c8dba-139">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="c8dba-140">ポリシーをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-140">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="c8dba-141">ユーザーのグループ メンバーシップに基づいてポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-141">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="c8dba-142">たとえば、セキュリティ グループまたは配布リストのすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-142">For example, you want to assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="c8dba-143">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c8dba-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="c8dba-144">ポリシーをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-144">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="c8dba-145">多数のユーザー セットにポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-145">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="c8dba-146">たとえば、組織内の数百または数千のユーザーに一度にポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-146">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="c8dba-147">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c8dba-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="c8dba-148">ポリシーパッケージをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-148">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  | <span data-ttu-id="c8dba-149">同じまたは類似の役割を持つ組織内の特定のユーザー セットに、複数のポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-149">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="c8dba-150">たとえば、教育機関 (教師) ポリシー パッケージを学校の教師に割り当てて、チャット、通話、および会議へのフル アクセスを許可し、教育機関 (中学生) ポリシー パッケージを中学生に割り当てて、私的な通話などの特定の機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-150">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="c8dba-151">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c8dba-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="c8dba-152">[グループにポリシーパッケージを割り当てる](#assign-a-policy-package-to-a-group) (プライベートプレビュー)</span><span class="sxs-lookup"><span data-stu-id="c8dba-152">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="c8dba-153">同じロールまたは類似のロールを持つ組織内のユーザーグループに複数のポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-153">You need to assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="c8dba-154">たとえば、セキュリティグループまたは配布リスト内のすべてのユーザーにポリシーパッケージを割り当てる必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-154">For example, you want to assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="c8dba-155">Teams PowerShell モジュールの Microsoft Teams 管理センター (近日公開予定) または PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c8dba-155">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="c8dba-156">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-156">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="c8dba-157">同じまたは類似の役割を持つ組織内のユーザーのバッチに、複数のポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-157">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="c8dba-158">たとえば、バッチ割り当てを使用して教育機関 (教師) ポリシー パッケージを学校のすべての教師に割り当てて、チャット、通話、および会議へのフル アクセスを許可し、教育機関 (中学生) ポリシー パッケージを中学生のバッチに割り当てて、私的な通話などの特定の機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-158">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="c8dba-159">Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c8dba-159">PowerShell cmdlets in the Teams PowerShell module</span></span>|


## <a name="set-the-global-policies"></a><span data-ttu-id="c8dba-160">グローバル ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="c8dba-160">Set the global policies</span></span>

<span data-ttu-id="c8dba-161">次の手順に従って、ポリシーの種類ごとにグローバルな (組織全体の既定の) ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c8dba-162">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="c8dba-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c8dba-163">Microsoft Teams 管理センターの左側のナビゲーションで、更新するポリシー タイプのポリシー ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="c8dba-164">たとえば、**Teams** > **Teams ポリシー**、**会議** > **会議ポリシー**、**メッセージ ポリシー**、または **音声** > **通話ポリシー** です。</span><span class="sxs-lookup"><span data-stu-id="c8dba-164">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="c8dba-165">現在の設定を表示するには、**グローバルな (組織全体の既定の)** ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="c8dba-166">必要に応じてポリシーを更新し、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c8dba-167">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="c8dba-167">Using PowerShell</span></span>

<span data-ttu-id="c8dba-168">PowerShell を使用してグローバル ポリシーを設定するには、グローバル識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="c8dba-169">まず、現在のグローバル ポリシーを確認して、変更する設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="c8dba-170">次に、必要に応じてグローバル ポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="c8dba-171">変更する設定の値を指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="c8dba-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="c8dba-172">ポリシーを個々のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-172">Assign a policy to individual users</span></span>

<span data-ttu-id="c8dba-173">個々のユーザーまたは一度に少数のユーザーにポリシーを割り当てるには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c8dba-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c8dba-174">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="c8dba-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c8dba-175">ポリシーをグループに割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="c8dba-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="c8dba-176">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-176">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="c8dba-177">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="c8dba-178">割り当てるポリシーを選択し、**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="c8dba-179">または、次の操作も実行できます:</span><span class="sxs-lookup"><span data-stu-id="c8dba-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="c8dba-180">Microsoft Teams 管理センターの左側のナビゲーションで、ポリシー ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="c8dba-181">ポリシー名の左側をクリックして割り当てるポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="c8dba-182">**[ユーザーを管理する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="c8dba-183">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="c8dba-184">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="c8dba-185">ユーザーの追加が完了したら、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c8dba-186">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="c8dba-186">Using PowerShell</span></span>

<span data-ttu-id="c8dba-187">各ポリシー タイプには、それを管理するための独自のコマンドレットのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="c8dba-188">特定のポリシー タイプに ```Grant-``` コマンドレットを使用して、ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="c8dba-189">たとえば、```Grant-CsTeamsMeetingPolicy``` コマンドレットを使用して、Teams 会議ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="c8dba-190">これらのコマンドレットは、Skype for Business Online PowerShell モジュールに含まれており、[Skype for Business コマンドレットのリファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) に記載されています。</span><span class="sxs-lookup"><span data-stu-id="c8dba-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="c8dba-191">(まだインストールされていない場合は) [Skype for Business Online PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=39366) をダウンロードしてインストールし、次のコマンドを実行して Skype for Business Online に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="c8dba-192">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="c8dba-192">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="c8dba-193">最新の [Teams PowerShell パブリックリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c8dba-193">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="c8dba-194">この例では、Student Meeting Policy という名前の Teams 会議ポリシーを、Reda というユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="c8dba-194">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="c8dba-195">詳細については、「PowerShell を使用した [ポリシーの管理](teams-powershell-managing-teams.md#manage-policies-via-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-195">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="c8dba-196">ポリシーをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-196">Assign a policy to a group</span></span>

<span data-ttu-id="c8dba-197">グループにポリシーを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-197">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="c8dba-198">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-198">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="c8dba-199">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-199">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="c8dba-200">ポリシーをグループに割り当てるのは、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-200">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="c8dba-201">ポリシーを割り当てると、そのポリシーはすぐにグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-201">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="c8dba-202">ただし、グループのメンバーへのポリシーの割り当ての反映は、バックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-202">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="c8dba-203">ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="c8dba-203">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="c8dba-204">グループポリシーの割り当ては、グループのダイレクトメンバーであるユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-204">Group policy assignments are only propagated to users that are direct members of the group.</span></span> <span data-ttu-id="c8dba-205">割り当ては、入れ子になったグループのメンバーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="c8dba-205">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="c8dba-206">グループへのポリシーの割り当てについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="c8dba-206">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="c8dba-207">使用を開始する前に、優先規則とグループ割り当てのランク付けを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c8dba-207">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="c8dba-208">優先規則</span><span class="sxs-lookup"><span data-stu-id="c8dba-208">Precedence rules</span></span>

<span data-ttu-id="c8dba-209">特定のポリシーの種類について、ユーザーの有効なポリシーは、次に従って決定されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-209">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="c8dba-210">ユーザーに直接割り当てられているポリシーは、グループに割り当てられている同じ種類の別のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-210">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="c8dba-211">言い換えると、ユーザーに特定の種類のポリシーが直接割り当てられている場合、そのユーザーはグループから同じ種類のポリシーを継承しません。</span><span class="sxs-lookup"><span data-stu-id="c8dba-211">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="c8dba-212">つまり、ユーザーが特定の種類のポリシーを直接割り当てられている場合は、ユーザーがグループから同じ種類のポリシーを継承する前に、そのポリシーをユーザーから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-212">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="c8dba-213">ユーザーに直接割り当てられたポリシーがなく、2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合、ユーザーは最も高いランク付けを持つグループ割り当てのポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-213">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="c8dba-214">ユーザーがポリシーが割り当てられているグループのメンバーではない場合、ユーザーにそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-214">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="c8dba-215">ポリシーを割り当てられているグループにユーザーを追加または削除したとき、ポリシーがグループに割り当てられていないとき、またはユーザーに直接割り当てられているポリシーが削除されたときに、ユーザーの有効なポリシーはこれらの規則に従って更新されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-215">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="c8dba-216">グループ割り当てのランク付け</span><span class="sxs-lookup"><span data-stu-id="c8dba-216">Group assignment ranking</span></span>
 
<span data-ttu-id="c8dba-217">ポリシーをグループに割り当てるときは、グループ割り当てのランクを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-217">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="c8dba-218">これは、ユーザーが 2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合に、ユーザーが有効なポリシーとして継承する必要があるポリシーを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-218">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="c8dba-219">グループ割り当てのランク付けは、同じ種類の別のグループ割り当てに関連しています。</span><span class="sxs-lookup"><span data-stu-id="c8dba-219">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="c8dba-220">たとえば、通話ポリシーを 2 つのグループに割り当てる場合は、1 つの割り当てのランクを 1 に設定し、もう 1 つの割り当てを 2 に設定します。1 が最高のランクです。</span><span class="sxs-lookup"><span data-stu-id="c8dba-220">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="c8dba-221">グループ割り当てのランク付けは、継承に関して、どのグループ メンバーシップが他のグループ メンバーシップよりも重要または関連性が高いかを示します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-221">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="c8dba-222">たとえば、店舗の従業員と管理者の 2 つのグループがあるとします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-222">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="c8dba-223">両方のグループには、それぞれ Teams 通話ポリシー、店舗従業員通話ポリシー、および店舗管理者通話ポリシーが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c8dba-223">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="c8dba-224">両方のグループに属する店舗管理者の場合、管理者としての役割は従業員としての役割よりも重要であるため、店舗管理者グループに割り当てられている通話ポリシーにより高いランク付けを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-224">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="c8dba-225">グループ</span><span class="sxs-lookup"><span data-stu-id="c8dba-225">Group</span></span> |<span data-ttu-id="c8dba-226">Teams 通話ポリシー名</span><span class="sxs-lookup"><span data-stu-id="c8dba-226">Teams calling policy name</span></span>  |<span data-ttu-id="c8dba-227">ランク</span><span class="sxs-lookup"><span data-stu-id="c8dba-227">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="c8dba-228">店舗管理者</span><span class="sxs-lookup"><span data-stu-id="c8dba-228">Store Managers</span></span>   |<span data-ttu-id="c8dba-229">店舗管理者通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="c8dba-229">Store Managers Calling Policy</span></span>         |<span data-ttu-id="c8dba-230">1</span><span class="sxs-lookup"><span data-stu-id="c8dba-230">1</span></span>|
|<span data-ttu-id="c8dba-231">店舗従業員</span><span class="sxs-lookup"><span data-stu-id="c8dba-231">Store Employees</span></span>    |<span data-ttu-id="c8dba-232">店舗従業員通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="c8dba-232">Store Employees Calling Policy</span></span>      |<span data-ttu-id="c8dba-233">2</span><span class="sxs-lookup"><span data-stu-id="c8dba-233">2</span></span>|

<span data-ttu-id="c8dba-234">ランクを指定しないと、ポリシーの割り当てに最も低いランクが与えられます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-234">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span> 

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c8dba-235">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="c8dba-235">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="c8dba-236">現在、Microsoft Teams 管理センターを使用したグループへのポリシー割り当ては、Teams 通話ポリシー、Teams コール パーク ポリシー、Teams ポリシー、Teams ライブ イベント ポリシー、Teams 会議ポリシー、Teams メッセージ ポリシーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-236">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="c8dba-237">他のポリシーの種類については、PowerShell を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-237">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="c8dba-238">Microsoft Teams 管理センターの左側のナビゲーションで、ポリシーの種類のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-238">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="c8dba-239">たとえば、**会議** > **会議ポリシー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-239">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="c8dba-240">**グループ ポリシーの割り当て** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-240">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="c8dba-241">**[グループの追加]** を選択し、**[ポリシーをグループに割り当てる]** ウィンドウで、次の操作を行います:</span><span class="sxs-lookup"><span data-stu-id="c8dba-241">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="c8dba-242">ポリシーを割り当てるグループを検索し、追加します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-242">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="c8dba-243">グループ割り当てのランク付けを設定します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-243">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="c8dba-244">割り当てるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-244">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="c8dba-245">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-245">Select **Apply**.</span></span>

<span data-ttu-id="c8dba-246">グループ ポリシーの割り当てを削除するには、ポリシー ページの **[グループ ポリシーの割り当て]** タブで、グループの割り当てを選び、**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-246">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="c8dba-247">グループ割り当てのランク付けを変更するには、最初にグループ ポリシーの割り当てを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-247">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="c8dba-248">次に、上記の手順に従ってポリシーをグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-248">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c8dba-249">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="c8dba-249">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="c8dba-250">現在、PowerShell を使用したグループへのポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c8dba-250">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="c8dba-251">サポートされているポリシー タイプの一覧については、[New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-251">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="c8dba-252">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="c8dba-252">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="c8dba-253">段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-253">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="c8dba-254">ユーザーのグループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-254">Assign a policy to a group of users</span></span>

<span data-ttu-id="c8dba-255">グループにポリシーを割り当てるには、 [新しい-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-255">You use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="c8dba-256">オブジェクト ID、SIP アドレス、またはメール アドレスを使用して、グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-256">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="c8dba-257">この例では、"小売課長" という名前の Teams の会議ポリシーを割り当てランキング1のグループに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="c8dba-257">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="c8dba-258">グループのポリシーの割り当てを取得する</span><span class="sxs-lookup"><span data-stu-id="c8dba-258">Get policy assignments for a group</span></span>

<span data-ttu-id="c8dba-259">グループに割り当てられているすべてのポリシーを取得するには、 [CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-259">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="c8dba-260">ポリシーの割り当てに SIP アドレスまたはメール アドレスが使用された場合でも、グループは常にグループ ID 別に一覧表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-260">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="c8dba-261">この例では、特定のグループに割り当てられているすべてのポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-261">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="c8dba-262">この例では、Teams 会議ポリシーが割り当てられているすべてのグループを返します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-262">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="c8dba-263">グループからポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="c8dba-263">Remove a policy from a group</span></span>

<span data-ttu-id="c8dba-264">グループからポリシーを削除するには、 [CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-264">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="c8dba-265">グループからポリシーを削除すると、そのグループに割り当てられた同じ種類でランクが低い他のポリシーの優先順位が更新されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-265">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="c8dba-266">たとえば、ランクが 2 であるポリシーを削除すると、その新しいランク付けを反映して、ランク 3 と 4 のポリシーが更新されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-266">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="c8dba-267">次の 2 つの表にこの例を示します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-267">The following two tables show this example.</span></span>

<span data-ttu-id="c8dba-268">これは、Teams 会議ポリシーのポリシー割り当てと優先順位のリストです。</span><span class="sxs-lookup"><span data-stu-id="c8dba-268">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="c8dba-269">グループ名</span><span class="sxs-lookup"><span data-stu-id="c8dba-269">Group name</span></span>  |<span data-ttu-id="c8dba-270">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="c8dba-270">Policy name</span></span>  |<span data-ttu-id="c8dba-271">ランク</span><span class="sxs-lookup"><span data-stu-id="c8dba-271">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="c8dba-272">営業</span><span class="sxs-lookup"><span data-stu-id="c8dba-272">Sales</span></span>    |<span data-ttu-id="c8dba-273">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="c8dba-273">Sales policy</span></span>       | <span data-ttu-id="c8dba-274">1</span><span class="sxs-lookup"><span data-stu-id="c8dba-274">1</span></span>        |
|<span data-ttu-id="c8dba-275">西部地域</span><span class="sxs-lookup"><span data-stu-id="c8dba-275">West Region</span></span>     |<span data-ttu-id="c8dba-276">西部地域ポリシー</span><span class="sxs-lookup"><span data-stu-id="c8dba-276">West Region policy</span></span>         |<span data-ttu-id="c8dba-277">2</span><span class="sxs-lookup"><span data-stu-id="c8dba-277">2</span></span>         |
|<span data-ttu-id="c8dba-278">部門</span><span class="sxs-lookup"><span data-stu-id="c8dba-278">Division</span></span>    |<span data-ttu-id="c8dba-279">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="c8dba-279">Division policy</span></span>         |<span data-ttu-id="c8dba-280">3</span><span class="sxs-lookup"><span data-stu-id="c8dba-280">3</span></span>         |
|<span data-ttu-id="c8dba-281">部署</span><span class="sxs-lookup"><span data-stu-id="c8dba-281">Subsidiary</span></span>   |<span data-ttu-id="c8dba-282">部署ポリシー</span><span class="sxs-lookup"><span data-stu-id="c8dba-282">Subsidiary policy</span></span>        |<span data-ttu-id="c8dba-283">4</span><span class="sxs-lookup"><span data-stu-id="c8dba-283">4</span></span>         |

<span data-ttu-id="c8dba-284">西部地域グループから西部地域ポリシーを削除すると、ポリシーの割り当てと優先順位は次のように更新されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-284">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="c8dba-285">グループ名</span><span class="sxs-lookup"><span data-stu-id="c8dba-285">Group name</span></span>  |<span data-ttu-id="c8dba-286">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="c8dba-286">Policy name</span></span>  |<span data-ttu-id="c8dba-287">ランク</span><span class="sxs-lookup"><span data-stu-id="c8dba-287">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="c8dba-288">営業</span><span class="sxs-lookup"><span data-stu-id="c8dba-288">Sales</span></span>    |<span data-ttu-id="c8dba-289">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="c8dba-289">Sales policy</span></span>       | <span data-ttu-id="c8dba-290">1</span><span class="sxs-lookup"><span data-stu-id="c8dba-290">1</span></span>        |
|<span data-ttu-id="c8dba-291">部門</span><span class="sxs-lookup"><span data-stu-id="c8dba-291">Division</span></span>    |<span data-ttu-id="c8dba-292">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="c8dba-292">Division policy</span></span>         |<span data-ttu-id="c8dba-293">2</span><span class="sxs-lookup"><span data-stu-id="c8dba-293">2</span></span>         |
|<span data-ttu-id="c8dba-294">部署</span><span class="sxs-lookup"><span data-stu-id="c8dba-294">Subsidiary</span></span>   |<span data-ttu-id="c8dba-295">部署ポリシー</span><span class="sxs-lookup"><span data-stu-id="c8dba-295">Subsidiary policy</span></span>        |<span data-ttu-id="c8dba-296">3</span><span class="sxs-lookup"><span data-stu-id="c8dba-296">3</span></span>        |

<span data-ttu-id="c8dba-297">この例では、グループから Teams 会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-297">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="c8dba-298">グループのポリシーの割り当てを変更する</span><span class="sxs-lookup"><span data-stu-id="c8dba-298">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="c8dba-299">[Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)コマンドレットは間もなく利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-299">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="c8dba-300">それまでの間、グループ ポリシーの割り当てを変更するには、現在のポリシーの割り当てをグループから削除して、新しいポリシーの割り当てを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-300">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="c8dba-301">グループにポリシーを割り当てると、次のように [設定](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) して、そのグループのポリシー割り当てを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-301">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="c8dba-302">ランク付けを変更する</span><span class="sxs-lookup"><span data-stu-id="c8dba-302">Change the ranking</span></span>
- <span data-ttu-id="c8dba-303">特定のポリシーの種類のポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="c8dba-303">Change the policy of a given policy type</span></span>
- <span data-ttu-id="c8dba-304">特定のポリシーの種類のポリシーとランク付けを変更する</span><span class="sxs-lookup"><span data-stu-id="c8dba-304">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="c8dba-305">この例では、グループの Teams コール パーク ポリシーを、SupportCallPark という名前のポリシーに変更し、割り当てのランクを 3 に変更します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-305">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="c8dba-306">ユーザーの有効なポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="c8dba-306">Change the effective policy for a user</span></span>

<span data-ttu-id="c8dba-307">これは、ポリシーを直接割り当てるユーザーの有効なポリシーを変更する方法の例です。</span><span class="sxs-lookup"><span data-stu-id="c8dba-307">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="c8dba-308">まず、 [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) ```PolicySource``` ユーザーに関連付けられている Teams 会議ブロードキャストポリシーの詳細を確認するために、パラメーターと共に、CsUserPolicyAssignment コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-308">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="c8dba-309">出力には、Employee Events という名前の Teams 会議ブロードキャスト ポリシーがユーザーに直接割り当てられていることが示されています。これは、ユーザーが属するグループに割り当てられている Vendor Live Events という名前のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-309">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="c8dba-310">次に、ユーザーから Employee Events policy を削除します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-310">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="c8dba-311">つまり、ユーザーに Teams 会議ブロードキャスト ポリシーが直接割り当てられなくなったことを意味し、ユーザーが属するグループに割り当てられている Vendor Live Events policy を継承します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-311">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="c8dba-312">この操作を行うには、Skype for Business PowerShell モジュールの次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-312">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="c8dba-313">Teams PowerShell モジュールで次のコマンドレットを使用すると、バッチ ポリシーの割り当てを通じて大規模にこれを行うことができます。ここで、$users は指定したユーザーのリストです。</span><span class="sxs-lookup"><span data-stu-id="c8dba-313">You can use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="c8dba-314">ポリシーをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-314">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c8dba-315">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="c8dba-315">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c8dba-316">ポリシーをユーザーに一括で割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="c8dba-316">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="c8dba-317">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-317">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="c8dba-318">ポリシーを割り当てるユーザーを検索するか、ビューをフィルター処理して必要なユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-318">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="c8dba-319">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-319">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="c8dba-320">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-320">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="c8dba-321">[**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-321">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="c8dba-322">ポリシーの割り当ての状態を表示するには、**[適用]** をクリックしてポリシーの割り当てを送信した後に **[ユーザー]** ページの上部に表示されるバナーで、**[アクティビティ ログ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-322">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="c8dba-323">または、Microsoft Teams 管理センターの左側のナビゲーションで、**[ダッシュボード]** に移動し、**[アクティビティ ログ]** で **[詳細の表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-323">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="c8dba-324">アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-324">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="c8dba-325">詳細については、「[アクティビティ ログでポリシーの割り当てを表示する](activity-log.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-325">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c8dba-326">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="c8dba-326">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="c8dba-327">現在、PowerShell を使用したバッチ ポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c8dba-327">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="c8dba-328">サポートされているポリシー タイプの一覧については、[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-328">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="c8dba-329">バッチ ポリシーの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-329">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="c8dba-330">[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)コマンドレットを使用して、ユーザーと割り当てるポリシーのバッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-330">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="c8dba-331">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-331">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="c8dba-332">次に、 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチ内の課題の進捗状況と状態を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-332">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="c8dba-333">ユーザーの指定には、オブジェクト ID またはセッション開始プロトコル (SIP) アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-333">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="c8dba-334">多くの場合、ユーザーの SIP アドレスは、ユーザー プリンシパル名 (UPN) またはメール アドレスと同じ値ですが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="c8dba-334">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="c8dba-335">ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-335">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="c8dba-336">バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-336">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="c8dba-337">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-337">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="c8dba-338">最良の結果を得るには、一度に複数のバッチを送信しないようにします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-338">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="c8dba-339">さらにバッチを送信する前に、バッチが処理を完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-339">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="c8dba-340">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="c8dba-340">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="c8dba-341">以下を実行して、[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-341">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="c8dba-342">バージョン 1.0.5 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-342">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="c8dba-343">以下を実行して Teams に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-343">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="c8dba-344">メッセージが表示されたら、管理者の資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-344">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="c8dba-345">Azure AD PowerShell for Graph モジュールをインストールして接続する (オプション)</span><span class="sxs-lookup"><span data-stu-id="c8dba-345">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="c8dba-346">また、[Azure AD PowerShell for Graph モジュールをダウンロードしてインストールし](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （まだインストールしていない場合）、Azure AD に接続して、組織内のユーザーのリストを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-346">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="c8dba-347">以下を実行して、Azure AD に接続します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-347">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="c8dba-348">メッセージが表示されたら、Teams に接続するために使用したのと同じ管理者資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-348">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="c8dba-349">ポリシーをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-349">Assign a policy to a batch of users</span></span>

<span data-ttu-id="c8dba-350">この例では、 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、HR アプリセットアップポリシーという名前のアプリセットアップポリシーを、Users_ids テキストファイルに記載されているユーザーのバッチに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-350">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="c8dba-351">この例では、Azure AD に接続してユーザーのコレクションを取得し、SIP アドレスを使用して指定されたユーザーのバッチに New Hire Messaging Policy という名前のメッセージ ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-351">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="c8dba-352">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="c8dba-352">Get the status of a batch assignment</span></span>

<span data-ttu-id="c8dba-353">以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの ```New-CsBatchPolicyAssignmentOperation``` コマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="c8dba-353">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="c8dba-354">エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、```UserState``` プロパティにあるエラーに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-354">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="c8dba-355">詳細については、[Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-355">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="c8dba-356">ポリシーパッケージをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-356">Assign a policy package to users</span></span>

<span data-ttu-id="c8dba-357">Teams のポリシー パッケージは、組織内で同じまたは類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="c8dba-357">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="c8dba-358">各ポリシー パッケージは、ユーザーの役割に合わせて設計されており、その役割の一般的なアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c8dba-358">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="c8dba-359">ポリシー パッケージの例としては、教育機関 (教師) パッケージと医療機関 (医療従事者) パッケージがあります。</span><span class="sxs-lookup"><span data-stu-id="c8dba-359">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="c8dba-360">詳細については、「 [Teams でポリシーパッケージを管理](manage-policy-packages.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-360">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="c8dba-361">1人のユーザーにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-361">Assign a policy package to one user</span></span>

1. <span data-ttu-id="c8dba-362">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-362">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="c8dba-363">ユーザーのページで、[ **ポリシー**] をクリックし、[ **ポリシーパッケージ**] の横にある [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-363">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="c8dba-364">[ **ポリシーパッケージの割り当て** ] ウィンドウで、割り当てるパッケージを選択し、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-364">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="c8dba-365">ポリシーパッケージを複数のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-365">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="c8dba-366">Microsoft Teams 管理センターの左のナビゲーションで、[ **ポリシーパッケージ**] に移動し、パッケージ名の左側をクリックして割り当てるポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-366">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="c8dba-367">[ **ユーザーの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-367">Click **Manage users**.</span></span>
3. <span data-ttu-id="c8dba-368">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-368">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="c8dba-369">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-369">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="c8dba-370">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-370">When you're finished adding users, click **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="c8dba-371">ポリシー パッケージをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-371">Assign a policy package to a group</span></span>

<span data-ttu-id="c8dba-372">**この機能はプライベート プレビューです**</span><span class="sxs-lookup"><span data-stu-id="c8dba-372">**This feature is in private preview**</span></span>

<span data-ttu-id="c8dba-373">グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-373">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="c8dba-374">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-374">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="c8dba-375">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-375">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="c8dba-376">グループに割り当てられるポリシーパッケージは、最大5万ユーザーのグループに対して推奨されますが、大規模なグループでも動作します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-376">Policy package assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span> 

<span data-ttu-id="c8dba-377">ポリシーパッケージを割り当てると、そのパッケージはすぐにグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-377">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="c8dba-378">ただし、グループのメンバーへのポリシーの割り当ての反映は、バックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-378">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="c8dba-379">ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="c8dba-379">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8dba-380">作業を始める前に、 [優先順位の規則](#precedence-rules) とグループの [割り当ての順位](#group-assignment-ranking)を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c8dba-380">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="c8dba-381">この記事で前に説明した [グループへのポリシーの割り当てについて知っておく必要がある](#what-you-need-to-know-about-policy-assignment-to-groups) 概念を読んで理解していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-381">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a><span data-ttu-id="c8dba-382">Microsoft Teams 管理センターを使用する (近日公開)</span><span class="sxs-lookup"><span data-stu-id="c8dba-382">Using the Microsoft Teams admin center (coming soon)</span></span>

<span data-ttu-id="c8dba-383">Microsoft Teams 管理センターのグループに対するポリシーパッケージの割り当ては、近日公開予定です。</span><span class="sxs-lookup"><span data-stu-id="c8dba-383">Policy package assignment to groups in the Microsoft Teams admin center is coming soon.</span></span> <span data-ttu-id="c8dba-384">最新の更新プログラムについては、ここを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-384">Check back here for the latest updates.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c8dba-385">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="c8dba-385">Using PowerShell</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="c8dba-386">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="c8dba-386">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="c8dba-387">段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-387">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="c8dba-388">ユーザーのグループにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-388">Assign a policy package to a group of users</span></span>

<span data-ttu-id="c8dba-389">ポリシーパッケージをグループに割り当てるには、 [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-389">You use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="c8dba-390">オブジェクト ID、SIP アドレス、またはメール アドレスを使用して、グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-390">You can specify a group by using the object Id, SIP address, or email address.</span></span> <span data-ttu-id="c8dba-391">ポリシーパッケージを割り当てるときに、ポリシーパッケージのポリシーの種類ごとに、 [グループの割り当ての順位](#group-assignment-ranking) を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-391">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span> 

<span data-ttu-id="c8dba-392">この例では、Education_Teacher ポリシーパッケージをグループに割り当て、TeamsAppSetupPolicy と TeamsMeetingBroadcastPolicy には1、TeamsMeetingPolicy には2のランク付けを行います。</span><span class="sxs-lookup"><span data-stu-id="c8dba-392">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="c8dba-393">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-393">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="c8dba-394">バッチ ポリシー パッケージの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシー パッケージを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-394">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="c8dba-395">[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)コマンドレットを使用して、ユーザーのバッチと、割り当てるポリシーパッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-395">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="c8dba-396">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-396">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="c8dba-397">次に、 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチ内の課題の進捗状況と状態を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-397">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="c8dba-398">ユーザーの指定には、オブジェクト ID またはセッション開始プロトコル (SIP) アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-398">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="c8dba-399">多くの場合、ユーザーの SIP アドレスは、ユーザー プリンシパル名 (UPN) またはメール アドレスと同じ値ですが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="c8dba-399">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="c8dba-400">ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-400">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="c8dba-401">バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-401">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="c8dba-402">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-402">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="c8dba-403">最良の結果を得るには、一度に複数のバッチを送信しないようにします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-403">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="c8dba-404">さらにバッチを送信する前に、バッチが処理を完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-404">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="c8dba-405">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="c8dba-405">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="c8dba-406">以下を実行して、(まだインストールされていない場合は) [Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-406">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="c8dba-407">バージョン 1.0.5 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-407">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="c8dba-408">以下を実行して Teams に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-408">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="c8dba-409">メッセージが表示されたら、管理者の資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="c8dba-409">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="c8dba-410">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8dba-410">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="c8dba-411">この例では、 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、ユーザーのバッチに Education_PrimaryStudent ポリシーパッケージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c8dba-411">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="c8dba-412">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="c8dba-412">Get the status of a batch assignment</span></span>

<span data-ttu-id="c8dba-413">以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの ```New-CsBatchPolicyAssignmentOperation``` コマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="c8dba-413">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="c8dba-414">エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、```UserState``` プロパティにあるエラーに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8dba-414">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="c8dba-415">詳細については、[Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8dba-415">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="c8dba-416">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c8dba-416">Related topics</span></span>

[<span data-ttu-id="c8dba-417">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="c8dba-417">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
