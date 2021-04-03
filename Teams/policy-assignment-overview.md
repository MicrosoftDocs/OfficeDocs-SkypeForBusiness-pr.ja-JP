---
title: Teams でポリシーを割り当てる
author: KarliStites
ms.author: kastites
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
description: Microsoft Teams のユーザーとグループにポリシーとポリシー パッケージを割り当てるさまざまな方法について説明します。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 00f78b3b134c6741a89c0d7b3f43d32a11c182cc
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574356"
---
# <a name="assign-policies-in-teams--getting-started"></a><span data-ttu-id="6c670-103">Teams でポリシーを割り当てる - 使用を開始する</span><span class="sxs-lookup"><span data-stu-id="6c670-103">Assign policies in Teams – getting started</span></span>

<span data-ttu-id="6c670-104">管理者は、ポリシーを使用して、組織のユーザーが利用できる Teams 機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="6c670-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="6c670-105">たとえば、ほんの一例を挙げると、通話ポリシー、会議ポリシー、メッセージ ポリシーなどがあります。</span><span class="sxs-lookup"><span data-stu-id="6c670-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="6c670-106">組織には、固有のニーズを持つユーザーの種類が異なります。</span><span class="sxs-lookup"><span data-stu-id="6c670-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="6c670-107">作成して割り当てるカスタム ポリシーを使用すると、それらのニーズに基づいて、さまざまなユーザー セットにポリシー設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="6c670-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="6c670-108">組織内のポリシーを簡単に管理するために、Teams にはユーザーにポリシーを割り当てる方法がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="6c670-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="6c670-109">ポリシーをユーザーに直接割り当てる(個別に割り当てるか、バッチ割り当てを通じてスケールで割り当てるか、ユーザーがメンバーであるグループに割り当てる)。</span><span class="sxs-lookup"><span data-stu-id="6c670-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="6c670-110">ポリシー パッケージを使用して、ポリシーの既定のコレクションを、同様の役割を持つ組織内のユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="6c670-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="6c670-111">選択するオプションは、管理するポリシーの数と、ポリシーを割り当てるユーザーの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6c670-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="6c670-112">グローバル (組織全体の既定) ポリシーは、組織内のユーザーの数が最も多い場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6c670-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="6c670-113">ポリシーを割り当てる必要があるのは、特殊なポリシーが必要なユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="6c670-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="6c670-114">この記事では、ユーザーにポリシーを割り当てるさまざまな方法と、何をいつ使用するかについての推奨シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6c670-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

<span data-ttu-id="6c670-115">ユーザーとグループにポリシーを **割り当てる** 方法の詳細については、「ユーザーとグループにポリシーを割り当 [てる」を参照してください](assign-policies-users-and-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="6c670-115">For details on how to **assign policies to users and groups**, see [assigning policies to users and groups](assign-policies-users-and-groups.md).</span></span> <span data-ttu-id="6c670-116">ポリシー パッケージを割り当てる方法の **詳細については、「** ポリシー パッケージを割り当 [てる」を参照してください](assign-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="6c670-116">For details on how to **assign policy packages**, see [assign policy packages](assign-policy-packages.md).</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="6c670-117">どのポリシーが優先されますか?</span><span class="sxs-lookup"><span data-stu-id="6c670-117">Which policy takes precedence?</span></span>

<span data-ttu-id="6c670-118">ユーザーには、ポリシーの種類ごとに 1 つの有効なポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="6c670-118">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="6c670-119">ユーザーに直接ポリシーが割り当て済みで、同じ種類のポリシーが割り当てられている 1 つ以上のグループのメンバーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c670-119">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="6c670-120">このようなシナリオでは、どのポリシーが優先されますか?</span><span class="sxs-lookup"><span data-stu-id="6c670-120">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="6c670-121">ユーザーの有効なポリシーは、次の優先規則に従って決定されます。</span><span class="sxs-lookup"><span data-stu-id="6c670-121">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="6c670-122">ユーザーに直接ポリシーが割り当てられている場合 （個別に、またはバッチ割り当てによって）、そのポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="6c670-122">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="6c670-123">次の視覚的な例では、ユーザーの効果的なポリシーは、ユーザーに直接割り当てられる、Square 会議ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="6c670-123">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![直接割り当てられたポリシーの優先順位を示す図](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="6c670-125">ユーザーに特定の種類のポリシーが直接割り当てられていない場合は、そのユーザーがメンバーになっているグループに割り当てられているポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="6c670-125">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="6c670-126">ユーザーが複数のグループのメンバーである場合、指定されたポリシーの種類の中で最も[高い](assign-policies-users-and-groups.md#group-assignment-ranking)(グループ割り当てランキング) を持つポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="6c670-126">If a user is a member of multiple groups, the policy that has the highest ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for the given policy type takes precedence.</span></span>

<span data-ttu-id="6c670-127">この視覚的な例では、ユーザーの効果的なポリシーは Exec Teams と HD ポリシーです。このポリシーは、ユーザーがメンバーであり、同じポリシーの種類のポリシーも割り当てられている他のグループに対して、最も高い割り当てランクを持っています。</span><span class="sxs-lookup"><span data-stu-id="6c670-127">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![グループから継承されたポリシーの優先順位を示す図](media/assign-policies-example-group.png)

<span data-ttu-id="6c670-129">ユーザーが直接ポリシーを割り当てられていない場合や、ポリシーが割り当てられているグループのメンバーではない場合、ユーザーはそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6c670-129">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="6c670-130">次に、視覚的な例を示します。</span><span class="sxs-lookup"><span data-stu-id="6c670-130">Here's a visual example.</span></span>

![グローバル ポリシーの優先順位を示す図](media/assign-policies-example-global.png)

<span data-ttu-id="6c670-132">詳細については、「(優先順位ルール)」[を参照してください](assign-policies-users-and-groups.md#precedence-rules)。</span><span class="sxs-lookup"><span data-stu-id="6c670-132">To learn more, see ([Precedence rules](assign-policies-users-and-groups.md#precedence-rules)).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="6c670-133">ポリシーを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="6c670-133">Ways to assign policies</span></span>

<span data-ttu-id="6c670-134">これは、ユーザーにポリシーを割り当てる方法と、それぞれに推奨されるシナリオの概要です。</span><span class="sxs-lookup"><span data-stu-id="6c670-134">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="6c670-135">詳細については、リンクを選択してください。</span><span class="sxs-lookup"><span data-stu-id="6c670-135">Select the links to learn more.</span></span>

<span data-ttu-id="6c670-136">個々のユーザーまたはグループにポリシーを割り当てる前に、[グローバルな （組織全体の既定の） ポリシーを設定して](#set-the-global-policies)、それらが組織内の最大数のユーザーに適用されるようにします。</span><span class="sxs-lookup"><span data-stu-id="6c670-136">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="6c670-137">グローバル ポリシーを設定したら、特別なポリシーを必要とするユーザーにのみポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c670-137">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="6c670-138">操作</span><span class="sxs-lookup"><span data-stu-id="6c670-138">Do this</span></span>  |<span data-ttu-id="6c670-139">条件...</span><span class="sxs-lookup"><span data-stu-id="6c670-139">If...</span></span>  | <span data-ttu-id="6c670-140">使用する技術...</span><span class="sxs-lookup"><span data-stu-id="6c670-140">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="6c670-141">ポリシーを個々のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="6c670-141">Assign a policy to individual users</span></span>](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | <span data-ttu-id="6c670-142">Teams を初めて使用する場合、1 つまたはいくつかのポリシーを少数のユーザーに割り当てるだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="6c670-142">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="6c670-143">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="6c670-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>
|[<span data-ttu-id="6c670-144">ポリシーをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="6c670-144">Assign a policy to a group</span></span>](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |<span data-ttu-id="6c670-145">ユーザーのグループ メンバーシップに基づいてポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="6c670-145">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="6c670-146">たとえば、セキュリティ グループまたは配布リスト内のすべてのユーザーにポリシーを割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="6c670-146">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="6c670-147">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="6c670-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="6c670-148">ポリシーをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="6c670-148">Assign a policy to a batch of users</span></span>](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="6c670-149">多数のユーザーにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="6c670-149">Assign policies to large sets of users.</span></span> <span data-ttu-id="6c670-150">たとえば、一度に数百または数千人のユーザーにポリシーを割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="6c670-150">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="6c670-151">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="6c670-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="6c670-152">ポリシー パッケージをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="6c670-152">Assign a policy package to users</span></span>](assign-policy-packages.md#assign-a-policy-package-to-users)  |<span data-ttu-id="6c670-153">同じ役割または同様の役割を持つ組織内の特定のユーザー セットに複数のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6c670-153">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="6c670-154">たとえば、学校の教師に教育 (教師) ポリシー パッケージを割り当て、チャット、通話、会議へのフル アクセス権を与えます。</span><span class="sxs-lookup"><span data-stu-id="6c670-154">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="6c670-155">Education (中等学生) ポリシー パッケージを中学生に割り当て、プライベート通話などの特定の機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="6c670-155">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="6c670-156">Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="6c670-156">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="6c670-157">[ポリシー パッケージをグループに割り当てる](assign-policy-packages.md#assign-a-policy-package-to-a-group) (プライベート プレビュー)</span><span class="sxs-lookup"><span data-stu-id="6c670-157">[Assign a policy package to a group](assign-policy-packages.md#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="6c670-158">同じ役割または同様の役割を持つ組織内のユーザーのグループに複数のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6c670-158">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="6c670-159">たとえば、セキュリティ グループまたは配布リスト内のすべてのユーザーにポリシー パッケージを割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="6c670-159">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="6c670-160">Microsoft Teams 管理センター (近日公開予定) または Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="6c670-160">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="6c670-161">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="6c670-161">Assign a policy package to a batch of users</span></span>](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="6c670-162">同じ役割または同様の役割を持つ組織内のユーザーのバッチに複数のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6c670-162">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="6c670-163">たとえば、バッチ割り当てを使用して、学校内のすべての教師に教育 (教師) ポリシー パッケージを割り当て、チャット、通話、会議へのフル アクセス権を与えます。</span><span class="sxs-lookup"><span data-stu-id="6c670-163">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="6c670-164">プライベート通話などの特定の機能を制限するために、Education (中等学生) ポリシー パッケージをセカンダリ 学生のバッチに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="6c670-164">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="6c670-165">Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="6c670-165">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="6c670-166">グローバル ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="6c670-166">Set the global policies</span></span>

<span data-ttu-id="6c670-167">次の手順に従って、ポリシーの種類ごとにグローバルな (組織全体の既定の) ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="6c670-167">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6c670-168">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="6c670-168">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="6c670-169">Microsoft Teams 管理センターの左側のナビゲーションで、更新するポリシー タイプのポリシー ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="6c670-169">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="6c670-170">たとえば、**Teams** > **Teams ポリシー**、**会議** > **会議ポリシー**、**メッセージ ポリシー**、または **音声** > **通話ポリシー** です。</span><span class="sxs-lookup"><span data-stu-id="6c670-170">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="6c670-171">現在の設定を表示するには、**グローバルな (組織全体の既定の)** ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c670-171">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="6c670-172">必要に応じてポリシーを更新し、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c670-172">Update the policy as needed, and then select **Apply**.</span></span>

![Teams 管理センターでグローバル ポリシーを更新する](media/assign-globalpolicy.png)

### <a name="using-powershell"></a><span data-ttu-id="6c670-174">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="6c670-174">Using PowerShell</span></span>

<span data-ttu-id="6c670-175">PowerShell を使用してグローバル ポリシーを設定するには、グローバル識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c670-175">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="6c670-176">まず、現在のグローバル ポリシーを確認して、変更する設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="6c670-176">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="6c670-177">次に、必要に応じてグローバル ポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="6c670-177">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="6c670-178">変更する設定の値を指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="6c670-178">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="6c670-179">アクティビティ ログでポリシー割り当てを表示する</span><span class="sxs-lookup"><span data-stu-id="6c670-179">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="6c670-180">Microsoft Teams 管理センターでユーザーにポリシーを割り当てると、アクティビティ ログでそれらのポリシー割り当ての状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6c670-180">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="6c670-181">アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c670-181">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="6c670-182">アクティビティ ログには、ポリシー パッケージの割り当て、Microsoft Teams 管理センターを通じて 20 人未満のユーザーのバッチへのポリシー割り当て、または PowerShell によるポリシー割り当ては表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c670-182">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![[アクティビティ ログ] ページのスクリーンショット](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="6c670-184">アクティビティ ログでポリシー割り当てアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="6c670-184">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="6c670-185">アクティビティ ログにポリシー割り当てを表示するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="6c670-185">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="6c670-186">Microsoft Teams 管理センターの左側のナビゲーションで、[ダッシュボード] に移動し、[アクティビティ ログ] の [詳細の表示] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6c670-186">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="6c670-187">すべてのポリシー割り当てを表示したり、状態でリストをフィルター処理して、[開始していない]、[進行中]、または [完了] の割り当てのみを **表示することができます**。 </span><span class="sxs-lookup"><span data-stu-id="6c670-187">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="6c670-188">各課題に関する次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c670-188">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="6c670-189">**名前**: ポリシー割り当ての名前。</span><span class="sxs-lookup"><span data-stu-id="6c670-189">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="6c670-190">詳細を表示するには、リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c670-190">Click the link to view more details.</span></span> <span data-ttu-id="6c670-191">これには、ポリシーが割り当てられたユーザーの数、完了した割り当て、進行中、開始されていない割り当ての数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6c670-191">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="6c670-192">バッチ内のユーザーの一覧と、各ユーザーの状態と結果も表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c670-192">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="6c670-193">以下は、実行例です。</span><span class="sxs-lookup"><span data-stu-id="6c670-193">Here's an example:</span></span>

        ![[](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="6c670-195">**送信** 日時: ポリシー割り当てが送信された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="6c670-195">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="6c670-196">**完了時刻**: ポリシー割り当てが完了した日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="6c670-196">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="6c670-197">**影響:** バッチ内のユーザー数。</span><span class="sxs-lookup"><span data-stu-id="6c670-197">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="6c670-198">**全体の状態**: ポリシー割り当ての状態。</span><span class="sxs-lookup"><span data-stu-id="6c670-198">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="6c670-199">[ユーザー] ページからアクティビティ ログに **アクセス** することもできます。</span><span class="sxs-lookup"><span data-stu-id="6c670-199">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="6c670-200">[適用] **をクリック** して一括ポリシーの割り当てを送信すると、ページの上部にバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c670-200">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="6c670-201">バナーの **[アクティビティ ログ** ] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c670-201">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6c670-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c670-202">Related topics</span></span>

- [<span data-ttu-id="6c670-203">ユーザーとグループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6c670-203">Assign policies to users and groups</span></span>](assign-policies-users-and-groups.md)
- [<span data-ttu-id="6c670-204">ユーザーとグループにポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6c670-204">Assign policy packages to users and groups</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="6c670-205">ポリシーを使用して Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="6c670-205">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="6c670-206">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="6c670-206">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)