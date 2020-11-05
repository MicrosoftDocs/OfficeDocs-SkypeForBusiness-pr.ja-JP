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
ms.openlocfilehash: fb9946f9954dc46d9d97137f707b7ad46c797fb9
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908526"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="3e481-103">Microsoft Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="3e481-104">管理者は、ポリシーを使用して、組織のユーザーが利用できる Teams 機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="3e481-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="3e481-105">たとえば、ほんの一例を挙げると、通話ポリシー、会議ポリシー、メッセージ ポリシーなどがあります。</span><span class="sxs-lookup"><span data-stu-id="3e481-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="3e481-106">組織には、独自のニーズを持つさまざまなタイプのユーザーがあり、カスタム ポリシーを作成して割り当てることで、それらのニーズに応じて、さまざまなユーザーのセットにポリシー設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="3e481-106">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="3e481-107">組織でのポリシーの管理を容易にするために、Teams はユーザーにポリシーを割り当てるいくつかの方法を提供しています。</span><span class="sxs-lookup"><span data-stu-id="3e481-107">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="3e481-108">個別に、一括割り当てで、またはユーザーがメンバーになっているグループを介して、ポリシーをユーザーに直接割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3e481-108">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="3e481-109">ポリシー パッケージを使用して、ポリシーの既定のコレクションを、同様の役割を持つ組織内のユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="3e481-109">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="3e481-110">選択するオプションは、管理しているポリシーの数と、割り当てているユーザーの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3e481-110">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="3e481-111">グローバルな （組織全体の既定の） ポリシーを設定して、それらが組織内の最大数のユーザーに適用されるようにすることで、特殊なポリシーを必要とするユーザーにポリシーを割り当てるだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="3e481-111">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="3e481-112">この記事では、ユーザーにポリシーを割り当てるさまざまな方法と、何をいつ使用するかについての推奨シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3e481-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="3e481-113">どのポリシーが優先されますか?</span><span class="sxs-lookup"><span data-stu-id="3e481-113">Which policy takes precedence?</span></span>

<span data-ttu-id="3e481-114">ユーザーには、ポリシーの種類ごとに 1 つの有効なポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="3e481-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="3e481-115">ユーザーに直接ポリシーが割り当てられていてもかまいません。同じ種類のポリシーが割り当てられている 1 つ以上のグループのメンバーでもある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3e481-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="3e481-116">このようなシナリオでは、どのポリシーが優先されますか?</span><span class="sxs-lookup"><span data-stu-id="3e481-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="3e481-117">ユーザーの有効なポリシーは、次の優先規則に従って決定されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="3e481-118">ユーザーに直接ポリシーが割り当てられている場合 （個別に、またはバッチ割り当てによって）、そのポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="3e481-119">次の例では、ユーザーの有効なポリシーは、ユーザーに直接割り当てられている Lincoln Square の会議ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3e481-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![直接割り当てられたポリシーの優先順位を示す図](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="3e481-121">ユーザーに特定の種類のポリシーが直接割り当てられていない場合は、そのユーザーがメンバーになっているグループに割り当てられているポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="3e481-122">ユーザーが複数のグループのメンバーである場合、特定のポリシーの種類に対して、[グループ割り当てのランク付け](#group-assignment-ranking) が最も高いポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="3e481-123">この例では、ユーザーの有効なポリシーは、Exec Teams および HD ポリシーです。このポリシーは、ユーザーがメンバーであり、同じポリシー タイプのポリシーが割り当てられている他のグループと比べて、割り当てのランクが最も高くなっています。</span><span class="sxs-lookup"><span data-stu-id="3e481-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![グループから継承されたポリシーの優先順位を示す図](media/assign-policies-example-group.png)

<span data-ttu-id="3e481-125">ユーザーが直接ポリシーを割り当てられていない場合や、ポリシーが割り当てられているグループのメンバーではない場合、ユーザーはそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="3e481-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="3e481-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3e481-126">Here's an example.</span></span>

![グローバル ポリシーの優先順位を示す図](media/assign-policies-example-global.png)

<span data-ttu-id="3e481-128">詳細については、「[優先規則](#precedence-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="3e481-129">ポリシーを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="3e481-129">Ways to assign policies</span></span>

<span data-ttu-id="3e481-130">これは、ユーザーにポリシーを割り当てる方法と、それぞれに推奨されるシナリオの概要です。</span><span class="sxs-lookup"><span data-stu-id="3e481-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="3e481-131">リンクをクリックして詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-131">Click the links to learn more.</span></span>

<span data-ttu-id="3e481-132">個々のユーザーまたはグループにポリシーを割り当てる前に、[グローバルな （組織全体の既定の） ポリシーを設定して](#set-the-global-policies)、それらが組織内の最大数のユーザーに適用されるようにします。</span><span class="sxs-lookup"><span data-stu-id="3e481-132">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="3e481-133">グローバル ポリシーが設定されると、特殊なポリシーを必要とするユーザーにポリシーを割り当てるだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="3e481-133">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="3e481-134">操作</span><span class="sxs-lookup"><span data-stu-id="3e481-134">Do this</span></span>  |<span data-ttu-id="3e481-135">条件...</span><span class="sxs-lookup"><span data-stu-id="3e481-135">If...</span></span>  | <span data-ttu-id="3e481-136">使用する技術...</span><span class="sxs-lookup"><span data-stu-id="3e481-136">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="3e481-137">ポリシーを個々のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-137">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="3e481-138">Teams を初めて使用する場合、1 つまたはいくつかのポリシーを少数のユーザーに割り当てるだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="3e481-138">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="3e481-139">Microsoft Teams 管理センターまたは Skype for Business Online PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="3e481-139">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="3e481-140">ポリシーをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-140">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="3e481-141">ユーザーのグループ メンバーシップに基づいてポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e481-141">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="3e481-142">たとえば、セキュリティ グループまたは配布リストのすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3e481-142">For example, you want to assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="3e481-143">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="3e481-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="3e481-144">ポリシーをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-144">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="3e481-145">多数のユーザー セットにポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e481-145">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="3e481-146">たとえば、組織内の数百または数千のユーザーに一度にポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3e481-146">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="3e481-147">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="3e481-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="3e481-148">ポリシーパッケージをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-148">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  | <span data-ttu-id="3e481-149">同じまたは類似の役割を持つ組織内の特定のユーザー セットに、複数のポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e481-149">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="3e481-150">たとえば、教育機関 (教師) ポリシー パッケージを学校の教師に割り当てて、チャット、通話、および会議へのフル アクセスを許可し、教育機関 (中学生) ポリシー パッケージを中学生に割り当てて、私的な通話などの特定の機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="3e481-150">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="3e481-151">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="3e481-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="3e481-152">[グループにポリシーパッケージを割り当てる](#assign-a-policy-package-to-a-group) (プライベートプレビュー)</span><span class="sxs-lookup"><span data-stu-id="3e481-152">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="3e481-153">同じロールまたは類似のロールを持つ組織内のユーザーグループに複数のポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e481-153">You need to assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="3e481-154">たとえば、セキュリティグループまたは配布リスト内のすべてのユーザーにポリシーパッケージを割り当てる必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="3e481-154">For example, you want to assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="3e481-155">Teams PowerShell モジュールの Microsoft Teams 管理センター (近日公開予定) または PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="3e481-155">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="3e481-156">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-156">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="3e481-157">同じまたは類似の役割を持つ組織内のユーザーのバッチに、複数のポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e481-157">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="3e481-158">たとえば、バッチ割り当てを使用して教育機関 (教師) ポリシー パッケージを学校のすべての教師に割り当てて、チャット、通話、および会議へのフル アクセスを許可し、教育機関 (中学生) ポリシー パッケージを中学生のバッチに割り当てて、私的な通話などの特定の機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="3e481-158">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="3e481-159">Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="3e481-159">PowerShell cmdlets in the Teams PowerShell module</span></span>|


## <a name="set-the-global-policies"></a><span data-ttu-id="3e481-160">グローバル ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="3e481-160">Set the global policies</span></span>

<span data-ttu-id="3e481-161">次の手順に従って、ポリシーの種類ごとにグローバルな (組織全体の既定の) ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="3e481-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3e481-162">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="3e481-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3e481-163">Microsoft Teams 管理センターの左側のナビゲーションで、更新するポリシー タイプのポリシー ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3e481-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="3e481-164">たとえば、 **Teams** > **Teams ポリシー** 、 **会議** > **会議ポリシー** 、 **メッセージ ポリシー** 、または **音声** > **通話ポリシー** です。</span><span class="sxs-lookup"><span data-stu-id="3e481-164">For example, **Teams** > **Teams policies** , **Meetings** > **Meetings policies** , **Messaging policies** , or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="3e481-165">現在の設定を表示するには、 **グローバルな (組織全体の既定の)** ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e481-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="3e481-166">必要に応じてポリシーを更新し、 **[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e481-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3e481-167">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="3e481-167">Using PowerShell</span></span>

<span data-ttu-id="3e481-168">PowerShell を使用してグローバル ポリシーを設定するには、グローバル識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="3e481-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="3e481-169">まず、現在のグローバル ポリシーを確認して、変更する設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="3e481-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="3e481-170">次に、必要に応じてグローバル ポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="3e481-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="3e481-171">変更する設定の値を指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="3e481-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="3e481-172">ポリシーを個々のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-172">Assign a policy to individual users</span></span>

<span data-ttu-id="3e481-173">個々のユーザーまたは一度に少数のユーザーにポリシーを割り当てるには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3e481-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3e481-174">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="3e481-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="3e481-175">ポリシーをグループに割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="3e481-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="3e481-176">Microsoft Teams 管理センターの左側のナビゲーションで、 **[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e481-176">In the left navigation of the Microsoft Teams admin center, go to **Users** , and then click the user.</span></span>
2. <span data-ttu-id="3e481-177">ユーザー名の左側をクリックしてユーザーを選択し、[ **編集を設定する** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e481-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="3e481-178">割り当てるポリシーを選択し、 **[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e481-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="3e481-179">または、次の操作も実行できます:</span><span class="sxs-lookup"><span data-stu-id="3e481-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="3e481-180">Microsoft Teams 管理センターの左側のナビゲーションで、ポリシー ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3e481-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="3e481-181">ポリシー名の左側をクリックして割り当てるポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="3e481-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="3e481-182">**[ユーザーを管理する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e481-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="3e481-183">[ **ユーザーを管理** ] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [ **追加** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3e481-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="3e481-184">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3e481-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="3e481-185">ユーザーの追加が完了したら、 **[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e481-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3e481-186">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="3e481-186">Using PowerShell</span></span>

<span data-ttu-id="3e481-187">各ポリシー タイプには、それを管理するための独自のコマンドレットのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="3e481-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="3e481-188">特定のポリシー タイプに ```Grant-``` コマンドレットを使用して、ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3e481-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="3e481-189">たとえば、```Grant-CsTeamsMeetingPolicy``` コマンドレットを使用して、Teams 会議ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3e481-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="3e481-190">これらのコマンドレットは、Skype for Business Online PowerShell モジュールに含まれており、[Skype for Business コマンドレットのリファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) に記載されています。</span><span class="sxs-lookup"><span data-stu-id="3e481-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="3e481-191">(まだインストールされていない場合は) [Skype for Business Online PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=39366) をダウンロードしてインストールし、次のコマンドを実行して Skype for Business Online に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="3e481-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="3e481-192">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e481-192">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="3e481-193">最新の [Teams PowerShell パブリックリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3e481-193">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="3e481-194">この例では、Student Meeting Policy という名前の Teams 会議ポリシーを、Reda というユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="3e481-194">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="3e481-195">詳細については、「PowerShell を使用した [ポリシーの管理](teams-powershell-managing-teams.md#manage-policies-via-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-195">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="3e481-196">ポリシーをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-196">Assign a policy to a group</span></span>

<span data-ttu-id="3e481-197">グループにポリシーを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3e481-197">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="3e481-198">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-198">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="3e481-199">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-199">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="3e481-200">ポリシーをグループに割り当てるのは、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="3e481-200">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="3e481-201">ポリシーを割り当てると、そのポリシーはすぐにグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3e481-201">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="3e481-202">ただし、グループのメンバーへのポリシーの割り当ての反映は、バックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-202">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="3e481-203">ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="3e481-203">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="3e481-204">グループへのポリシーの割り当てについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="3e481-204">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="3e481-205">使用を開始する前に、優先規則とグループ割り当てのランク付けを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3e481-205">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="3e481-206">優先規則</span><span class="sxs-lookup"><span data-stu-id="3e481-206">Precedence rules</span></span>

<span data-ttu-id="3e481-207">特定のポリシーの種類について、ユーザーの有効なポリシーは、次に従って決定されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-207">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="3e481-208">ユーザーに直接割り当てられているポリシーは、グループに割り当てられている同じ種類の別のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-208">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="3e481-209">言い換えると、ユーザーに特定の種類のポリシーが直接割り当てられている場合、そのユーザーはグループから同じ種類のポリシーを継承しません。</span><span class="sxs-lookup"><span data-stu-id="3e481-209">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="3e481-210">つまり、ユーザーが特定の種類のポリシーを直接割り当てられている場合は、ユーザーがグループから同じ種類のポリシーを継承する前に、そのポリシーをユーザーから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e481-210">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="3e481-211">ユーザーに直接割り当てられたポリシーがなく、2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合、ユーザーは最も高いランク付けを持つグループ割り当てのポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="3e481-211">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="3e481-212">ユーザーがポリシーが割り当てられているグループのメンバーではない場合、ユーザーにそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3e481-212">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="3e481-213">ポリシーを割り当てられているグループにユーザーを追加または削除したとき、ポリシーがグループに割り当てられていないとき、またはユーザーに直接割り当てられているポリシーが削除されたときに、ユーザーの有効なポリシーはこれらの規則に従って更新されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-213">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="3e481-214">グループ割り当てのランク付け</span><span class="sxs-lookup"><span data-stu-id="3e481-214">Group assignment ranking</span></span>
 
<span data-ttu-id="3e481-215">ポリシーをグループに割り当てるときは、グループ割り当てのランクを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e481-215">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="3e481-216">これは、ユーザーが 2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合に、ユーザーが有効なポリシーとして継承する必要があるポリシーを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-216">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="3e481-217">グループ割り当てのランク付けは、同じ種類の別のグループ割り当てに関連しています。</span><span class="sxs-lookup"><span data-stu-id="3e481-217">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="3e481-218">たとえば、通話ポリシーを 2 つのグループに割り当てる場合は、1 つの割り当てのランクを 1 に設定し、もう 1 つの割り当てを 2 に設定します。1 が最高のランクです。</span><span class="sxs-lookup"><span data-stu-id="3e481-218">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="3e481-219">グループ割り当てのランク付けは、継承に関して、どのグループ メンバーシップが他のグループ メンバーシップよりも重要または関連性が高いかを示します。</span><span class="sxs-lookup"><span data-stu-id="3e481-219">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="3e481-220">たとえば、店舗の従業員と管理者の 2 つのグループがあるとします。</span><span class="sxs-lookup"><span data-stu-id="3e481-220">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="3e481-221">両方のグループには、それぞれ Teams 通話ポリシー、店舗従業員通話ポリシー、および店舗管理者通話ポリシーが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="3e481-221">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="3e481-222">両方のグループに属する店舗管理者の場合、管理者としての役割は従業員としての役割よりも重要であるため、店舗管理者グループに割り当てられている通話ポリシーにより高いランク付けを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e481-222">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="3e481-223">グループ</span><span class="sxs-lookup"><span data-stu-id="3e481-223">Group</span></span> |<span data-ttu-id="3e481-224">Teams 通話ポリシー名</span><span class="sxs-lookup"><span data-stu-id="3e481-224">Teams calling policy name</span></span>  |<span data-ttu-id="3e481-225">ランク</span><span class="sxs-lookup"><span data-stu-id="3e481-225">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="3e481-226">店舗管理者</span><span class="sxs-lookup"><span data-stu-id="3e481-226">Store Managers</span></span>   |<span data-ttu-id="3e481-227">店舗管理者通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="3e481-227">Store Managers Calling Policy</span></span>         |<span data-ttu-id="3e481-228">1</span><span class="sxs-lookup"><span data-stu-id="3e481-228">1</span></span>|
|<span data-ttu-id="3e481-229">店舗従業員</span><span class="sxs-lookup"><span data-stu-id="3e481-229">Store Employees</span></span>    |<span data-ttu-id="3e481-230">店舗従業員通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="3e481-230">Store Employees Calling Policy</span></span>      |<span data-ttu-id="3e481-231">2</span><span class="sxs-lookup"><span data-stu-id="3e481-231">2</span></span>|

<span data-ttu-id="3e481-232">ランクを指定しないと、ポリシーの割り当てに最も低いランクが与えられます。</span><span class="sxs-lookup"><span data-stu-id="3e481-232">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span> 

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3e481-233">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="3e481-233">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="3e481-234">現在、Microsoft Teams 管理センターを使用したグループへのポリシー割り当ては、Teams 通話ポリシー、Teams コール パーク ポリシー、Teams ポリシー、Teams ライブ イベント ポリシー、Teams 会議ポリシー、Teams メッセージ ポリシーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e481-234">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="3e481-235">他のポリシーの種類については、PowerShell を使用してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-235">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="3e481-236">Microsoft Teams 管理センターの左側のナビゲーションで、ポリシーの種類のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3e481-236">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="3e481-237">たとえば、 **会議** > **会議ポリシー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e481-237">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="3e481-238">**グループ ポリシーの割り当て** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e481-238">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="3e481-239">**[グループの追加]** を選択し、 **[ポリシーをグループに割り当てる]** ウィンドウで、次の操作を行います:</span><span class="sxs-lookup"><span data-stu-id="3e481-239">Select **Add group** , and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="3e481-240">ポリシーを割り当てるグループを検索し、追加します。</span><span class="sxs-lookup"><span data-stu-id="3e481-240">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="3e481-241">グループ割り当てのランク付けを設定します。</span><span class="sxs-lookup"><span data-stu-id="3e481-241">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="3e481-242">割り当てるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e481-242">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="3e481-243">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e481-243">Select **Apply**.</span></span>

<span data-ttu-id="3e481-244">グループ ポリシーの割り当てを削除するには、ポリシー ページの **[グループ ポリシーの割り当て]** タブで、グループの割り当てを選び、 **[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e481-244">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="3e481-245">グループ割り当てのランク付けを変更するには、最初にグループ ポリシーの割り当てを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e481-245">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="3e481-246">次に、上記の手順に従ってポリシーをグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3e481-246">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3e481-247">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="3e481-247">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="3e481-248">現在、PowerShell を使用したグループへのポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="3e481-248">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="3e481-249">サポートされているポリシー タイプの一覧については、[New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-249">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="3e481-250">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="3e481-250">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="3e481-251">段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-251">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="3e481-252">ユーザーのグループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-252">Assign a policy to a group of users</span></span>

<span data-ttu-id="3e481-253">グループにポリシーを割り当てるには、 [新しい-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e481-253">You use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="3e481-254">オブジェクト ID、SIP アドレス、またはメール アドレスを使用して、グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3e481-254">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="3e481-255">この例では、"小売課長" という名前の Teams の会議ポリシーを割り当てランキング1のグループに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="3e481-255">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="3e481-256">グループのポリシーの割り当てを取得する</span><span class="sxs-lookup"><span data-stu-id="3e481-256">Get policy assignments for a group</span></span>

<span data-ttu-id="3e481-257">グループに割り当てられているすべてのポリシーを取得するには、 [CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e481-257">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="3e481-258">ポリシーの割り当てに SIP アドレスまたはメール アドレスが使用された場合でも、グループは常にグループ ID 別に一覧表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-258">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="3e481-259">この例では、特定のグループに割り当てられているすべてのポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="3e481-259">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="3e481-260">この例では、Teams 会議ポリシーが割り当てられているすべてのグループを返します。</span><span class="sxs-lookup"><span data-stu-id="3e481-260">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="3e481-261">グループからポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="3e481-261">Remove a policy from a group</span></span>

<span data-ttu-id="3e481-262">グループからポリシーを削除するには、 [CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e481-262">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="3e481-263">グループからポリシーを削除すると、そのグループに割り当てられた同じ種類でランクが低い他のポリシーの優先順位が更新されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-263">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="3e481-264">たとえば、ランクが 2 であるポリシーを削除すると、その新しいランク付けを反映して、ランク 3 と 4 のポリシーが更新されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-264">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="3e481-265">次の 2 つの表にこの例を示します。</span><span class="sxs-lookup"><span data-stu-id="3e481-265">The following two tables show this example.</span></span>

<span data-ttu-id="3e481-266">これは、Teams 会議ポリシーのポリシー割り当てと優先順位のリストです。</span><span class="sxs-lookup"><span data-stu-id="3e481-266">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="3e481-267">グループ名</span><span class="sxs-lookup"><span data-stu-id="3e481-267">Group name</span></span>  |<span data-ttu-id="3e481-268">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="3e481-268">Policy name</span></span>  |<span data-ttu-id="3e481-269">ランク</span><span class="sxs-lookup"><span data-stu-id="3e481-269">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="3e481-270">営業</span><span class="sxs-lookup"><span data-stu-id="3e481-270">Sales</span></span>    |<span data-ttu-id="3e481-271">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="3e481-271">Sales policy</span></span>       | <span data-ttu-id="3e481-272">1</span><span class="sxs-lookup"><span data-stu-id="3e481-272">1</span></span>        |
|<span data-ttu-id="3e481-273">西部地域</span><span class="sxs-lookup"><span data-stu-id="3e481-273">West Region</span></span>     |<span data-ttu-id="3e481-274">西部地域ポリシー</span><span class="sxs-lookup"><span data-stu-id="3e481-274">West Region policy</span></span>         |<span data-ttu-id="3e481-275">2</span><span class="sxs-lookup"><span data-stu-id="3e481-275">2</span></span>         |
|<span data-ttu-id="3e481-276">部門</span><span class="sxs-lookup"><span data-stu-id="3e481-276">Division</span></span>    |<span data-ttu-id="3e481-277">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="3e481-277">Division policy</span></span>         |<span data-ttu-id="3e481-278">3</span><span class="sxs-lookup"><span data-stu-id="3e481-278">3</span></span>         |
|<span data-ttu-id="3e481-279">部署</span><span class="sxs-lookup"><span data-stu-id="3e481-279">Subsidiary</span></span>   |<span data-ttu-id="3e481-280">部署ポリシー</span><span class="sxs-lookup"><span data-stu-id="3e481-280">Subsidiary policy</span></span>        |<span data-ttu-id="3e481-281">4</span><span class="sxs-lookup"><span data-stu-id="3e481-281">4</span></span>         |

<span data-ttu-id="3e481-282">西部地域グループから西部地域ポリシーを削除すると、ポリシーの割り当てと優先順位は次のように更新されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-282">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="3e481-283">グループ名</span><span class="sxs-lookup"><span data-stu-id="3e481-283">Group name</span></span>  |<span data-ttu-id="3e481-284">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="3e481-284">Policy name</span></span>  |<span data-ttu-id="3e481-285">ランク</span><span class="sxs-lookup"><span data-stu-id="3e481-285">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="3e481-286">営業</span><span class="sxs-lookup"><span data-stu-id="3e481-286">Sales</span></span>    |<span data-ttu-id="3e481-287">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="3e481-287">Sales policy</span></span>       | <span data-ttu-id="3e481-288">1</span><span class="sxs-lookup"><span data-stu-id="3e481-288">1</span></span>        |
|<span data-ttu-id="3e481-289">部門</span><span class="sxs-lookup"><span data-stu-id="3e481-289">Division</span></span>    |<span data-ttu-id="3e481-290">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="3e481-290">Division policy</span></span>         |<span data-ttu-id="3e481-291">2</span><span class="sxs-lookup"><span data-stu-id="3e481-291">2</span></span>         |
|<span data-ttu-id="3e481-292">部署</span><span class="sxs-lookup"><span data-stu-id="3e481-292">Subsidiary</span></span>   |<span data-ttu-id="3e481-293">部署ポリシー</span><span class="sxs-lookup"><span data-stu-id="3e481-293">Subsidiary policy</span></span>        |<span data-ttu-id="3e481-294">3</span><span class="sxs-lookup"><span data-stu-id="3e481-294">3</span></span>        |

<span data-ttu-id="3e481-295">この例では、グループから Teams 会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="3e481-295">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="3e481-296">グループのポリシーの割り当てを変更する</span><span class="sxs-lookup"><span data-stu-id="3e481-296">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="3e481-297">[Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)コマンドレットは間もなく利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="3e481-297">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="3e481-298">それまでの間、グループ ポリシーの割り当てを変更するには、現在のポリシーの割り当てをグループから削除して、新しいポリシーの割り当てを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e481-298">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="3e481-299">グループにポリシーを割り当てると、次のように [設定](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) して、そのグループのポリシー割り当てを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="3e481-299">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="3e481-300">ランク付けを変更する</span><span class="sxs-lookup"><span data-stu-id="3e481-300">Change the ranking</span></span>
- <span data-ttu-id="3e481-301">特定のポリシーの種類のポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="3e481-301">Change the policy of a given policy type</span></span>
- <span data-ttu-id="3e481-302">特定のポリシーの種類のポリシーとランク付けを変更する</span><span class="sxs-lookup"><span data-stu-id="3e481-302">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="3e481-303">この例では、グループの Teams コール パーク ポリシーを、SupportCallPark という名前のポリシーに変更し、割り当てのランクを 3 に変更します。</span><span class="sxs-lookup"><span data-stu-id="3e481-303">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="3e481-304">ユーザーの有効なポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="3e481-304">Change the effective policy for a user</span></span>

<span data-ttu-id="3e481-305">これは、ポリシーを直接割り当てるユーザーの有効なポリシーを変更する方法の例です。</span><span class="sxs-lookup"><span data-stu-id="3e481-305">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="3e481-306">まず、 [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) ```PolicySource``` ユーザーに関連付けられている Teams 会議ブロードキャストポリシーの詳細を確認するために、パラメーターと共に、CsUserPolicyAssignment コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e481-306">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="3e481-307">出力には、Employee Events という名前の Teams 会議ブロードキャスト ポリシーがユーザーに直接割り当てられていることが示されています。これは、ユーザーが属するグループに割り当てられている Vendor Live Events という名前のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-307">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="3e481-308">次に、ユーザーから Employee Events policy を削除します。</span><span class="sxs-lookup"><span data-stu-id="3e481-308">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="3e481-309">つまり、ユーザーに Teams 会議ブロードキャスト ポリシーが直接割り当てられなくなったことを意味し、ユーザーが属するグループに割り当てられている Vendor Live Events policy を継承します。</span><span class="sxs-lookup"><span data-stu-id="3e481-309">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="3e481-310">この操作を行うには、Skype for Business PowerShell モジュールの次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e481-310">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="3e481-311">Teams PowerShell モジュールで次のコマンドレットを使用すると、バッチ ポリシーの割り当てを通じて大規模にこれを行うことができます。ここで、$users は指定したユーザーのリストです。</span><span class="sxs-lookup"><span data-stu-id="3e481-311">You can use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="3e481-312">ポリシーをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-312">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3e481-313">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="3e481-313">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="3e481-314">ポリシーをユーザーに一括で割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="3e481-314">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="3e481-315">Microsoft Teams 管理センターの左側のナビゲーションで、 **[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e481-315">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="3e481-316">ポリシーを割り当てるユーザーを検索するか、ビューをフィルター処理して必要なユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="3e481-316">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="3e481-317">[ **&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e481-317">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="3e481-318">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e481-318">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="3e481-319">[ **設定の編集** ] をクリックし、必要な変更を行い、[ **適用** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e481-319">Click **Edit settings** , make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="3e481-320">ポリシーの割り当ての状態を表示するには、 **[適用]** をクリックしてポリシーの割り当てを送信した後に **[ユーザー]** ページの上部に表示されるバナーで、 **[アクティビティ ログ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e481-320">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="3e481-321">または、Microsoft Teams 管理センターの左側のナビゲーションで、 **[ダッシュボード]** に移動し、 **[アクティビティ ログ]** で **[詳細の表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e481-321">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard** , and then under **Activity log** , click **View details**.</span></span> <span data-ttu-id="3e481-322">アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-322">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="3e481-323">詳細については、「[アクティビティ ログでポリシーの割り当てを表示する](activity-log.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-323">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3e481-324">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="3e481-324">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="3e481-325">現在、PowerShell を使用したバッチ ポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="3e481-325">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="3e481-326">サポートされているポリシー タイプの一覧については、[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-326">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="3e481-327">バッチ ポリシーの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3e481-327">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="3e481-328">[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)コマンドレットを使用して、ユーザーと割り当てるポリシーのバッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="3e481-328">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="3e481-329">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-329">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="3e481-330">次に、 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチ内の課題の進捗状況と状態を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="3e481-330">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="3e481-331">ユーザーの指定には、オブジェクト ID またはセッション開始プロトコル (SIP) アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e481-331">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="3e481-332">多くの場合、ユーザーの SIP アドレスは、ユーザー プリンシパル名 (UPN) またはメール アドレスと同じ値ですが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="3e481-332">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="3e481-333">ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="3e481-333">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="3e481-334">バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-334">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="3e481-335">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3e481-335">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="3e481-336">最良の結果を得るには、一度に複数のバッチを送信しないようにします。</span><span class="sxs-lookup"><span data-stu-id="3e481-336">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="3e481-337">さらにバッチを送信する前に、バッチが処理を完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3e481-337">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="3e481-338">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="3e481-338">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="3e481-339">以下を実行して、[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3e481-339">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="3e481-340">バージョン 1.0.5 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e481-340">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="3e481-341">以下を実行して Teams に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="3e481-341">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="3e481-342">メッセージが表示されたら、管理者の資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="3e481-342">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="3e481-343">Azure AD PowerShell for Graph モジュールをインストールして接続する (オプション)</span><span class="sxs-lookup"><span data-stu-id="3e481-343">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="3e481-344">また、[Azure AD PowerShell for Graph モジュールをダウンロードしてインストールし](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （まだインストールしていない場合）、Azure AD に接続して、組織内のユーザーのリストを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e481-344">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="3e481-345">以下を実行して、Azure AD に接続します。</span><span class="sxs-lookup"><span data-stu-id="3e481-345">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="3e481-346">メッセージが表示されたら、Teams に接続するために使用したのと同じ管理者資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="3e481-346">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="3e481-347">ポリシーをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-347">Assign a policy to a batch of users</span></span>

<span data-ttu-id="3e481-348">この例では、 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、HR アプリセットアップポリシーという名前のアプリセットアップポリシーを、Users_ids テキストファイルに記載されているユーザーのバッチに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3e481-348">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="3e481-349">この例では、Azure AD に接続してユーザーのコレクションを取得し、SIP アドレスを使用して指定されたユーザーのバッチに New Hire Messaging Policy という名前のメッセージ ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3e481-349">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="3e481-350">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="3e481-350">Get the status of a batch assignment</span></span>

<span data-ttu-id="3e481-351">以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの ```New-CsBatchPolicyAssignmentOperation``` コマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="3e481-351">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="3e481-352">エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、```UserState``` プロパティにあるエラーに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="3e481-352">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="3e481-353">詳細については、[Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-353">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="3e481-354">ポリシーパッケージをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-354">Assign a policy package to users</span></span>

<span data-ttu-id="3e481-355">Teams のポリシー パッケージは、組織内で同じまたは類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="3e481-355">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="3e481-356">各ポリシー パッケージは、ユーザーの役割に合わせて設計されており、その役割の一般的なアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e481-356">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="3e481-357">ポリシー パッケージの例としては、教育機関 (教師) パッケージと医療機関 (医療従事者) パッケージがあります。</span><span class="sxs-lookup"><span data-stu-id="3e481-357">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="3e481-358">詳細については、「 [Teams でポリシーパッケージを管理](manage-policy-packages.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-358">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="3e481-359">1人のユーザーにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-359">Assign a policy package to one user</span></span>

1. <span data-ttu-id="3e481-360">Microsoft Teams 管理センターの左側のナビゲーションで、 **[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e481-360">In the left navigation of the Microsoft Teams admin center, go to **Users** , and then click the user.</span></span>
2. <span data-ttu-id="3e481-361">ユーザーのページで、[ **ポリシー** ] をクリックし、[ **ポリシーパッケージ** ] の横にある [ **編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e481-361">On the user's page, click **Policies** , and then next to **Policy package** , click **Edit**.</span></span>
3. <span data-ttu-id="3e481-362">[ **ポリシーパッケージの割り当て** ] ウィンドウで、割り当てるパッケージを選択し、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e481-362">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="3e481-363">ポリシーパッケージを複数のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-363">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="3e481-364">Microsoft Teams 管理センターの左のナビゲーションで、[ **ポリシーパッケージ** ] に移動し、パッケージ名の左側をクリックして割り当てるポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e481-364">In the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="3e481-365">[ **ユーザーの管理** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e481-365">Click **Manage users**.</span></span>
3. <span data-ttu-id="3e481-366">[ **ユーザーを管理する** ] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e481-366">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="3e481-367">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3e481-367">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="3e481-368">ユーザーの追加が完了したら、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e481-368">When you're finished adding users, click **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="3e481-369">ポリシーパッケージをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-369">Assign a policy package to a group</span></span>

<span data-ttu-id="3e481-370">**この機能はプライベートプレビュー**</span><span class="sxs-lookup"><span data-stu-id="3e481-370">**This feature is in private preview**</span></span>

<span data-ttu-id="3e481-371">グループにポリシーパッケージを割り当てると、セキュリティグループや配布リストなど、複数のポリシーをユーザーのグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3e481-371">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="3e481-372">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-372">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="3e481-373">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-373">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="3e481-374">グループに割り当てられるポリシーパッケージは、最大5万ユーザーのグループに対して推奨されますが、大規模なグループでも動作します。</span><span class="sxs-lookup"><span data-stu-id="3e481-374">Policy package assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span> 

<span data-ttu-id="3e481-375">ポリシーパッケージを割り当てると、そのパッケージはすぐにグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3e481-375">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="3e481-376">ただし、グループのメンバーへのポリシーの割り当ての反映は、バックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-376">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="3e481-377">ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="3e481-377">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e481-378">作業を始める前に、 [優先順位の規則](#precedence-rules) とグループの [割り当ての順位](#group-assignment-ranking)を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3e481-378">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="3e481-379">この記事で前に説明した [グループへのポリシーの割り当てについて知っておく必要がある](#what-you-need-to-know-about-policy-assignment-to-groups) 概念を読んで理解していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e481-379">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a><span data-ttu-id="3e481-380">Microsoft Teams 管理センターを使用する (近日公開)</span><span class="sxs-lookup"><span data-stu-id="3e481-380">Using the Microsoft Teams admin center (coming soon)</span></span>

<span data-ttu-id="3e481-381">Microsoft Teams 管理センターのグループに対するポリシーパッケージの割り当ては、近日公開予定です。</span><span class="sxs-lookup"><span data-stu-id="3e481-381">Policy package assignment to groups in the Microsoft Teams admin center is coming soon.</span></span> <span data-ttu-id="3e481-382">最新の更新プログラムについては、ここを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-382">Check back here for the latest updates.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3e481-383">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="3e481-383">Using PowerShell</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="3e481-384">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="3e481-384">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="3e481-385">段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-385">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="3e481-386">ユーザーのグループにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-386">Assign a policy package to a group of users</span></span>

<span data-ttu-id="3e481-387">ポリシーパッケージをグループに割り当てるには、 [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e481-387">You use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="3e481-388">オブジェクト ID、SIP アドレス、またはメール アドレスを使用して、グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3e481-388">You can specify a group by using the object Id, SIP address, or email address.</span></span> <span data-ttu-id="3e481-389">ポリシーパッケージを割り当てるときに、ポリシーパッケージのポリシーの種類ごとに、 [グループの割り当ての順位](#group-assignment-ranking) を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e481-389">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span> 

<span data-ttu-id="3e481-390">この例では、Education_Teacher ポリシーパッケージをグループに割り当て、TeamsAppSetupPolicy と TeamsMeetingBroadcastPolicy には1、TeamsMeetingPolicy には2のランク付けを行います。</span><span class="sxs-lookup"><span data-stu-id="3e481-390">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="3e481-391">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-391">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="3e481-392">バッチ ポリシー パッケージの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシー パッケージを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3e481-392">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="3e481-393">[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)コマンドレットを使用して、ユーザーのバッチと、割り当てるポリシーパッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3e481-393">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="3e481-394">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-394">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="3e481-395">次に、 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチ内の課題の進捗状況と状態を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="3e481-395">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="3e481-396">ユーザーの指定には、オブジェクト ID またはセッション開始プロトコル (SIP) アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e481-396">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="3e481-397">多くの場合、ユーザーの SIP アドレスは、ユーザー プリンシパル名 (UPN) またはメール アドレスと同じ値ですが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="3e481-397">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="3e481-398">ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="3e481-398">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="3e481-399">バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3e481-399">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="3e481-400">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3e481-400">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="3e481-401">最良の結果を得るには、一度に複数のバッチを送信しないようにします。</span><span class="sxs-lookup"><span data-stu-id="3e481-401">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="3e481-402">さらにバッチを送信する前に、バッチが処理を完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3e481-402">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="3e481-403">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="3e481-403">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="3e481-404">以下を実行して、(まだインストールされていない場合は) [Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3e481-404">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="3e481-405">バージョン 1.0.5 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e481-405">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="3e481-406">以下を実行して Teams に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="3e481-406">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="3e481-407">メッセージが表示されたら、管理者の資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="3e481-407">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="3e481-408">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3e481-408">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="3e481-409">この例では、 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、ユーザーのバッチに Education_PrimaryStudent ポリシーパッケージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3e481-409">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="3e481-410">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="3e481-410">Get the status of a batch assignment</span></span>

<span data-ttu-id="3e481-411">以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの ```New-CsBatchPolicyAssignmentOperation``` コマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="3e481-411">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="3e481-412">エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、```UserState``` プロパティにあるエラーに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="3e481-412">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="3e481-413">詳細については、[Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e481-413">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="3e481-414">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3e481-414">Related topics</span></span>

[<span data-ttu-id="3e481-415">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="3e481-415">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
