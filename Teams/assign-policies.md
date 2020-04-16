---
title: Microsoft Teams でユーザーにポリシーを割り当てる
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag
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
description: Microsoft Teams でユーザーにポリシーを割り当てるさまざまな方法について説明します。
f1keywords: ''
ms.openlocfilehash: 5c46b74519520950d31f01d4c86ae2a5002ae279
ms.sourcegitcommit: df4dde0fe6ce9e26cb4b3da4e4b878538d31decc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "43521623"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="1bbf4-103">Microsoft Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1bbf4-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="1bbf4-104">**この記事で説明されている Microsoft Teams の機能の1つである [[グループへの割り当て](#assign-a-policy-to-a-group)] は、現在プライベートプレビューでのみ利用できます。この機能の Powershell コマンドレットは、プレリリースチームの PowerShell モジュールに含まれています。**</span><span class="sxs-lookup"><span data-stu-id="1bbf4-104">**One of the Microsoft Teams features discussed in this article, [policy assignment to groups](#assign-a-policy-to-a-group), is currently only available in private preview. The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span> <span data-ttu-id="1bbf4-105">この機能のリリース状況を把握するには、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-105">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="1bbf4-106">管理者は、ポリシーを使って、組織内のユーザーが利用できる Teams 機能を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-106">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="1bbf4-107">たとえば、通話ポリシー、会議ポリシー、メッセージポリシーなどは、ほんの少しだけ名前にします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-107">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="1bbf4-108">組織によって、独自のニーズとユーザー設定のポリシーを持つさまざまな種類のユーザーが、それらのニーズに応じてさまざまなユーザーのセットに対してポリシー設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-108">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="1bbf4-109">組織内のポリシーを簡単に管理できるように、Teams には、ユーザーにポリシーを割り当てるためのいくつかの方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-109">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="1bbf4-110">ポリシーは、個別に、またはバッチの割り当てを通じて、またはユーザーがメンバーになっているグループに直接割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-110">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="1bbf4-111">ポリシーパッケージを使用して、同じようなロールを持つ組織内のユーザーにポリシーの事前設定されたコレクションを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-111">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="1bbf4-112">選択するオプションは、管理しているポリシーの数と、割り当てられているユーザーの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-112">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="1bbf4-113">この記事では、ユーザーにポリシーを割り当てることができるさまざまな方法について説明します。また、どのような場合に使用するかについての推奨されるシナリオ</span><span class="sxs-lookup"><span data-stu-id="1bbf4-113">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="1bbf4-114">どのポリシーが優先されますか?</span><span class="sxs-lookup"><span data-stu-id="1bbf4-114">Which policy takes precedence?</span></span>

<span data-ttu-id="1bbf4-115">ユーザーには、ポリシーの種類ごとに1つの有効なポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-115">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="1bbf4-116">ユーザーに直接ポリシーが割り当てられている可能性があります。また、同じ種類のポリシーが割り当てられた1つ以上のグループのメンバーでもあります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-116">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="1bbf4-117">これらの種類のシナリオでは、どのポリシーが優先されますか。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-117">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="1bbf4-118">ユーザーの有効なポリシーは、次のように、優先順位の規則に従って決定されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-118">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="1bbf4-119">ユーザーに直接ポリシーが割り当てられている場合 (個別に、またはバッチ割り当てによって)、ポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-119">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="1bbf4-120">次の例では、ユーザーの有効なポリシーは、ユーザーに直接割り当てられている Lincoln Square 会議ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-120">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![直接割り当てられたポリシーの優先順位を示す図](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="1bbf4-122">ユーザーに特定の種類のポリシーが直接割り当てられていない場合、そのユーザーがメンバーになっているグループに割り当てられているポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-122">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="1bbf4-123">ユーザーが複数のグループのメンバーである場合は、指定したポリシーの種類に対して最も優先順位が高い[グループ割り当て](#group-assignment-ranking)を持つポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-123">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="1bbf4-124">この例では、ユーザーの有効なポリシーは Exec Teams と HD ポリシーで、ユーザーがメンバーになっている他のグループとの相対的な割り当ての順位が高く、同じポリシーの種類のポリシーも割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-124">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![グループから継承されたポリシーが優先される方法を示す図](media/assign-policies-example-group.png)

<span data-ttu-id="1bbf4-126">ユーザーが直接ポリシーを割り当てられていない場合や、ポリシーが割り当てられているグループのメンバーでない場合、ユーザーはそのポリシーの種類に対してグローバル (組織全体の既定の) ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-126">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="1bbf4-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-127">Here's an example.</span></span>

![グローバルポリシーの優先順位を示す図](media/assign-policies-example-global.png)

<span data-ttu-id="1bbf4-129">詳細については、「[優先順位規則](#precedence-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-129">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="1bbf4-130">ポリシーを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="1bbf4-130">Ways to assign policies</span></span>

<span data-ttu-id="1bbf4-131">ここでは、ユーザーにポリシーを割り当てる方法の概要と、それぞれの推奨されるシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-131">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="1bbf4-132">詳細については、リンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-132">Click the links to learn more.</span></span>

|<span data-ttu-id="1bbf4-133">操作</span><span class="sxs-lookup"><span data-stu-id="1bbf4-133">Do this</span></span>  |<span data-ttu-id="1bbf4-134">もし。。。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-134">If...</span></span>  | <span data-ttu-id="1bbf4-135">使用するのは...</span><span class="sxs-lookup"><span data-stu-id="1bbf4-135">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="1bbf4-136">個々のユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1bbf4-136">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="1bbf4-137">チームを初めて使い始めたり、少数のユーザーに1つまたはいくつかのポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-137">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="1bbf4-138">Skype for Business Online PowerShell モジュールの Microsoft Teams 管理センターまたは PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1bbf4-138">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="1bbf4-139">ポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1bbf4-139">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="1bbf4-140">同じロールまたは類似のロールを持つ組織内の特定のユーザーのセットに、複数のポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-140">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="1bbf4-141">たとえば、学校の教師に教育 (教師) ポリシーパッケージを割り当てることで、チャット、通話、会議、および教育 (第2章) ポリシーパッケージへのフルアクセスを学生に許可し、プライベート通話のような特定の機能を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-141">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="1bbf4-142">Teams PowerShell モジュールの Microsoft Teams 管理センターまたは PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1bbf4-142">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="1bbf4-143">ユーザーのバッチにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1bbf4-143">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="1bbf4-144">多数のユーザーにポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-144">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="1bbf4-145">たとえば、組織内の数百または数千のユーザーに一度にポリシーを割り当てる必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-145">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="1bbf4-146">Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1bbf4-146">PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="1bbf4-147">[グループにポリシーを割り当てる](#assign-a-policy-to-a-group)(プレビュー中)</span><span class="sxs-lookup"><span data-stu-id="1bbf4-147">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="1bbf4-148">ユーザーのグループメンバーシップに基づいてポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-148">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="1bbf4-149">たとえば、セキュリティグループまたは組織単位のすべてのユーザーにポリシーを割り当てる必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-149">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="1bbf4-150">Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1bbf4-150">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="1bbf4-151">ユーザーのバッチにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1bbf4-151">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="1bbf4-152">同じロールまたは類似のロールを持つ組織内のユーザーのバッチに複数のポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-152">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="1bbf4-153">たとえば、バッチの割り当てを使用して学校のすべての教師に教育 (教師) ポリシーパッケージを割り当てることで、チャット、通話、会議へのフルアクセスを許可したり、教育機関 (第1の学生) ポリシーパッケージを第2の学生に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-153">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="1bbf4-154">Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1bbf4-154">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="1bbf4-155">グループにポリシーパッケージを割り当てる (近日公開)</span><span class="sxs-lookup"><span data-stu-id="1bbf4-155">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="1bbf4-156">個々のユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1bbf4-156">Assign a policy to individual users</span></span>

<span data-ttu-id="1bbf4-157">個々のユーザーに、または一度に少数のユーザーにポリシーを割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-157">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1bbf4-158">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="1bbf4-158">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="1bbf4-159">ユーザーにポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-159">To assign a policy to a user:</span></span>

1. <span data-ttu-id="1bbf4-160">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-160">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="1bbf4-161">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-161">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="1bbf4-162">割り当てるポリシーを選択し、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-162">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="1bbf4-163">一度に最大20人のユーザーにポリシーを割り当てるには、「 [Teams のユーザー設定を一括](edit-user-settings-in-bulk.md)して編集する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-163">To assign a policy to up to 20 users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="1bbf4-164">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-164">Or, you can also do the following:</span></span>

1. <span data-ttu-id="1bbf4-165">Microsoft Teams 管理センターの左側のナビゲーションで、[ポリシー] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-165">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="1bbf4-166">ポリシー名の左側をクリックして、割り当てるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-166">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="1bbf4-167">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="1bbf4-168">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="1bbf4-169">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="1bbf4-170">ユーザーの追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-170">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="1bbf4-171">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="1bbf4-171">Using PowerShell</span></span>

<span data-ttu-id="1bbf4-172">各ポリシーの種類には、それらを管理するための独自のコマンドレットのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-172">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="1bbf4-173">指定し```Grant-```たポリシーの種類に対してコマンドレットを使用して、ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-173">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="1bbf4-174">たとえば、 ```Grant-CsTeamsMeetingPolicy```コマンドレットを使用して、Teams 会議ポリシーをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-174">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="1bbf4-175">これらのコマンドレットは、Skype for business Online PowerShell モジュールに含まれており、 [skype For business コマンドレットのリファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-175">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="1bbf4-176">[Skype For Business Online PowerShell モジュール](https://www.microsoft.com/en-us/download/details.aspx?id=39366)をダウンロードしてインストールし (まだインストールしていない場合)、次を実行して Skype For business online に接続してセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-176">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="1bbf4-177">この例では、Student Meeting ポリシーという名前の Teams 会議ポリシーを、Reda という名前のユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-177">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="1bbf4-178">詳細については、「PowerShell を使用した[ポリシーの管理](teams-powershell-overview.md#managing-policies-via-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-178">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="1bbf4-179">ポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1bbf4-179">Assign a policy package</span></span>

<span data-ttu-id="1bbf4-180">Teams のポリシーパッケージは、組織内で同じまたは類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-180">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="1bbf4-181">各ポリシーパッケージは、ユーザーロールに基づいて設計されています。定義済みのポリシーとポリシー設定が含まれており、その役割の一般的なアクティビティをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-181">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="1bbf4-182">ポリシーパッケージの例としては、教育機関 (教師) パッケージと医療 (臨床労働者) パッケージがあります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-182">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="1bbf4-183">ポリシーパッケージをユーザーに割り当てると、パッケージ内のポリシーが作成され、ユーザーのニーズに合わせてパッケージ内の各ポリシーの設定をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-183">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="1bbf4-184">ポリシーパッケージの詳細については、「[チームで](manage-policy-packages.md)ポリシーパッケージを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-184">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="1bbf4-185">ユーザーのバッチにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1bbf4-185">Assign a policy to a batch of users</span></span>
 
<span data-ttu-id="1bbf4-186">バッチポリシーが割り当てられている場合は、スクリプトを使わずに、一度に多くのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-186">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="1bbf4-187">```New-CsBatchPolicyAssignmentOperationd```コマンドレットを使用して、ユーザーと割り当てるポリシーのバッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-187">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="1bbf4-188">割り当てはバックグラウンド操作として処理され、各バッチに対して操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-188">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="1bbf4-189">その後、 ```Get-CsBatchPolicyAssignmentOperation```コマンドレットを使用して、バッチ内の課題の進捗状況と状態を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-189">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="1bbf4-190">バッチには最大2万ユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-190">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="1bbf4-191">ユーザーは、オブジェクト Id、ユーザープリンシパル名 (UPN)、セッション開始プロトコル (SIP) アドレス、またはメールアドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-191">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bbf4-192">現時点では、一度に5000ユーザーのバッチでポリシーを割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-192">We're currently recommending that you assign policies in batches of 5,000 users at a time.</span></span> <span data-ttu-id="1bbf4-193">こうした需要が増加すると、処理時間の遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-193">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="1bbf4-194">これらの増加した処理時間の影響を最小限に抑えるために、最大5000人のユーザーに対して少量のバッチサイズを送信し、前のバッチが完了した後でのみ各バッチを送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-194">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="1bbf4-195">通常の営業時間外にバッチを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-195">Submitting batches outside your regular business hours can also help.</span></span>

> [!NOTE]
> <span data-ttu-id="1bbf4-196">現時点では、すべてのチームポリシーの種類でバッチポリシーの割り当ては使用できません。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-196">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="1bbf4-197">サポートされているポリシーの種類の一覧については、「 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-197">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="1bbf4-198">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="1bbf4-198">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="1bbf4-199">[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-199">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="1bbf4-200">バージョン1.0.5 以降をインストールしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-200">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="1bbf4-201">Teams に接続してセッションを開始するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-201">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="1bbf4-202">メッセージが表示されたら、管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-202">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="1bbf4-203">Graph モジュール用 Azure AD PowerShell をインストールして接続する (オプション)</span><span class="sxs-lookup"><span data-stu-id="1bbf4-203">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="1bbf4-204">また、組織内のユーザーのリストを取得できるように[、AZURE Ad PowerShell For Graph モジュール](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)(まだインストールしていない場合) をダウンロードしてインストールし、azure ad に接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-204">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="1bbf4-205">Azure AD に接続するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-205">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="1bbf4-206">メッセージが表示されたら、Teams への接続に使用したのと同じ管理者資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-206">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="1bbf4-207">ユーザーのバッチにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1bbf4-207">Assign a policy to a batch of users</span></span>

<span data-ttu-id="1bbf4-208">この例では、 ```New-CsBatchPolicyAssignmentOperation```コマンドレットを使用して、HR アプリセットアップポリシーという名前のアプリセットアップポリシーを、Users_ids のテキストファイルに記載されているユーザーのバッチに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-208">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="1bbf4-209">この例では、Azure AD に接続してユーザーのコレクションを取得し、その Upn を使って指定された一連のユーザーに対して、新しい採用者のメッセージングポリシーという名前のメッセージングポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-209">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="1bbf4-210">詳細については、「 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-210">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="1bbf4-211">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="1bbf4-211">Get the status of a batch assignment</span></span>

<span data-ttu-id="1bbf4-212">バッチ割り当ての状態を取得するには、次を実行します。 OperationId は、指定された```New-CsBatchPolicyAssignmentOperation```バッチのコマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-212">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="1bbf4-213">出力にエラーが発生したことが示された場合は、次を実行して、 ```UserState```プロパティのエラーに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-213">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="1bbf4-214">詳細については、「 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-214">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="1bbf4-215">グループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1bbf4-215">Assign a policy to a group</span></span>

<span data-ttu-id="1bbf4-216">**グループへのポリシーの割り当ては、現在プライベートプレビューでのみ利用できます。この機能のコマンドレットは、プレリリースチームの PowerShell モジュールに含まれています。**</span><span class="sxs-lookup"><span data-stu-id="1bbf4-216">**Policy assignment to groups is currently only available in private preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

<span data-ttu-id="1bbf4-217">グループにポリシーを割り当てると、セキュリティグループや組織単位などのユーザーグループにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-217">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="1bbf4-218">ポリシーの割り当ては、優先順位の規則に従ってグループのメンバーに伝達されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-218">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="1bbf4-219">メンバーがグループに追加またはグループから削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-219">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="1bbf4-220">グループにポリシー ```New-CsGroupPolicyAssignment```を割り当てるには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-220">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="1bbf4-221">オブジェクト Id、SIP アドレス、またはメールアドレスを使用して、グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-221">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="1bbf4-222">ポリシーを割り当てると、そのポリシーはすぐにグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-222">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="1bbf4-223">ただし、グループのメンバーへのポリシー割り当ての反映はバックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-223">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="1bbf4-224">ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除されている場合は、同じことが当てはまります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-224">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="1bbf4-225">現在、グループへのポリシーの割り当ては、すべてのチームポリシーの種類では使用できません。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-225">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="1bbf4-226">サポートされているポリシーの種類の一覧については、「[新しい-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-226">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="1bbf4-227">グループへのポリシーの割り当てについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="1bbf4-227">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="1bbf4-228">作業を始める前に、優先順位の規則とグループの割り当ての順位を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-228">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="1bbf4-229">優先順位ルール</span><span class="sxs-lookup"><span data-stu-id="1bbf4-229">Precedence rules</span></span>

<span data-ttu-id="1bbf4-230">特定のポリシーの種類に対して、ユーザーの有効なポリシーは、次のように決定されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-230">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="1bbf4-231">ユーザーに直接割り当てられているポリシーは、グループに割り当てられているものと同じ種類の他のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-231">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="1bbf4-232">つまり、ユーザーに特定の種類のポリシーが直接割り当てられている場合、そのユーザーはグループから同じ種類のポリシーを継承しません。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-232">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="1bbf4-233">これは、ユーザーが直接割り当てられた特定の種類のポリシーを持っている場合にも、グループから同じ種類のポリシーを継承できるようにするために、そのポリシーをユーザーから削除する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-233">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="1bbf4-234">ユーザーに直接割り当てられているポリシーがなく、2つ以上のグループのメンバーである場合は、ユーザーは、ランクが最も高いグループの割り当てのポリシーを継承しています。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-234">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="1bbf4-235">ユーザーが、ポリシーが割り当てられているグループのメンバーでない場合、そのポリシーの種類に対するグローバル (組織全体の既定) ポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-235">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="1bbf4-236">ポリシーが割り当てられているグループにユーザーが追加または削除された場合、ポリシーがグループから割り当てられていない場合、またはユーザーに直接割り当てられているポリシーが削除された場合、ユーザーの有効なポリシーは、次の規則に従って更新されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-236">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="1bbf4-237">グループの割り当てのランク付け</span><span class="sxs-lookup"><span data-stu-id="1bbf4-237">Group assignment ranking</span></span>
 
<span data-ttu-id="1bbf4-238">グループにポリシーを割り当てるときは、グループの割り当ての順位を指定します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-238">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="1bbf4-239">ユーザーが2つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合に、ユーザーが有効なポリシーとしてどのポリシーを継承するかを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-239">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="1bbf4-240">グループの割り当ての順位は、同じ種類の他のグループ割り当てと相対的に異なります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-240">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="1bbf4-241">たとえば、2つのグループに通話ポリシーを割り当てる場合は、1つの割り当ての順位を1に設定して、ランクを1に設定します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-241">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="1bbf4-242">グループの割り当てのランクは、継承に関する他のグループメンバーシップよりも、どのグループメンバーシップが重要であるかを示します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-242">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="1bbf4-243">たとえば、2つのグループがあり、従業員とストアマネージャーが保存されているとします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-243">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="1bbf4-244">どちらのグループにもチームの通話ポリシーが割り当てられ、従業員の通話ポリシーとストアマネージャーの通話ポリシーがそれぞれ保存されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-244">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="1bbf4-245">両方のグループに参加しているストアマネージャーの場合、管理者としての役割は従業員としての役割よりも関連しているため、ストア管理者グループに割り当てられている通話ポリシーの順位は高くする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-245">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="1bbf4-246">化</span><span class="sxs-lookup"><span data-stu-id="1bbf4-246">Group</span></span> |<span data-ttu-id="1bbf4-247">チーム呼び出しポリシー名</span><span class="sxs-lookup"><span data-stu-id="1bbf4-247">Teams calling policy name</span></span>  |<span data-ttu-id="1bbf4-248">[ランク]</span><span class="sxs-lookup"><span data-stu-id="1bbf4-248">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="1bbf4-249">ストアマネージャー</span><span class="sxs-lookup"><span data-stu-id="1bbf4-249">Store Managers</span></span>   |<span data-ttu-id="1bbf4-250">ストアマネージャーの通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="1bbf4-250">Store Managers Calling Policy</span></span>         |<span data-ttu-id="1bbf4-251">1</span><span class="sxs-lookup"><span data-stu-id="1bbf4-251">1</span></span>|
|<span data-ttu-id="1bbf4-252">従業員の保存</span><span class="sxs-lookup"><span data-stu-id="1bbf4-252">Store Employees</span></span>    |<span data-ttu-id="1bbf4-253">従業員の通話ポリシーの保存</span><span class="sxs-lookup"><span data-stu-id="1bbf4-253">Store Employees Calling Policy</span></span>      |<span data-ttu-id="1bbf4-254">両面</span><span class="sxs-lookup"><span data-stu-id="1bbf4-254">2</span></span>|

<span data-ttu-id="1bbf4-255">ランクを指定しない場合、ポリシーの割り当てには最も優先順位が設定されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-255">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="1bbf4-256">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="1bbf4-256">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="1bbf4-257">コマンドレットは、Teams PowerShell モジュールのプレリリースバージョンに含まれています。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-257">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="1bbf4-258">次の手順に従って、最初に使用できるバージョンの Teams PowerShell モジュールをアンインストールし (インストールされている場合)、PowerShell テストギャラリーから最新のプレリリース版のモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-258">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="1bbf4-259">まだインストールしていない場合は、次のように実行して、PowerShell テストギャラリーを信頼できるソースとして登録します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-259">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="1bbf4-260">一般的な Teams PowerShell モジュールのバージョンがインストールされている場合は、次のように実行してアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-260">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="1bbf4-261">次を実行して、PowerShell テストギャラリーから最新の Microsoft Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-261">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="1bbf4-262">Teams に接続してセッションを開始するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-262">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="1bbf4-263">メッセージが表示されたら、管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-263">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="1bbf4-264">グループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1bbf4-264">Assign a policy to a group</span></span>

<span data-ttu-id="1bbf4-265">この例では、コマンドレット```New-CsGroupPolicyAssignment```を使用して、[小売マネージャー] 会議ポリシーという名前の Teams 会議ポリシーを割り当てランキング1のグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-265">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="1bbf4-266">詳細については、「[新しい-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-266">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="1bbf4-267">グループのポリシー割り当てを取得する</span><span class="sxs-lookup"><span data-stu-id="1bbf4-267">Get policy assignments for a group</span></span>

<span data-ttu-id="1bbf4-268">グループに```Get-CsGroupPolicyAssignment```割り当てられているすべてのポリシーを取得するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-268">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="1bbf4-269">グループは、その SIP アドレスまたはメールアドレスがポリシーの割り当てに使用されていた場合でも、常にグループ Id によって一覧表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-269">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="1bbf4-270">この例では、特定のグループに割り当てられているすべてのポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-270">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="1bbf4-271">この例では、Teams 会議ポリシーが割り当てられているすべてのグループを返します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-271">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="1bbf4-272">詳細については、「 [CsGroupPolicyAssignment の取得](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-272">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="1bbf4-273">グループからポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="1bbf4-273">Remove a policy from a group</span></span>

<span data-ttu-id="1bbf4-274">グループから```Remove-CsGroupPolicyAssignment```ポリシーを削除するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-274">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="1bbf4-275">グループからポリシーを削除すると、そのグループに割り当てられている同じ種類の他のポリシーの優先順位が更新されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-275">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="1bbf4-276">たとえば、ランクが2のポリシーを削除した場合、ランクが3と4のポリシーは、新しいランク付けを反映して更新されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-276">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="1bbf4-277">次の2つの表は、この例を示しています。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-277">The following two tables show this example.</span></span>

<span data-ttu-id="1bbf4-278">ここでは、Teams 会議ポリシーのポリシー割り当てと優先度の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-278">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="1bbf4-279">グループ名</span><span class="sxs-lookup"><span data-stu-id="1bbf4-279">Group name</span></span>  |<span data-ttu-id="1bbf4-280">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="1bbf4-280">Policy name</span></span>  |<span data-ttu-id="1bbf4-281">[ランク]</span><span class="sxs-lookup"><span data-stu-id="1bbf4-281">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="1bbf4-282">売上</span><span class="sxs-lookup"><span data-stu-id="1bbf4-282">Sales</span></span>    |<span data-ttu-id="1bbf4-283">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="1bbf4-283">Sales policy</span></span>       | <span data-ttu-id="1bbf4-284">1</span><span class="sxs-lookup"><span data-stu-id="1bbf4-284">1</span></span>        |
|<span data-ttu-id="1bbf4-285">西部地域</span><span class="sxs-lookup"><span data-stu-id="1bbf4-285">West Region</span></span>     |<span data-ttu-id="1bbf4-286">西部地域ポリシー</span><span class="sxs-lookup"><span data-stu-id="1bbf4-286">West Region policy</span></span>         |<span data-ttu-id="1bbf4-287">両面</span><span class="sxs-lookup"><span data-stu-id="1bbf4-287">2</span></span>         |
|<span data-ttu-id="1bbf4-288">課</span><span class="sxs-lookup"><span data-stu-id="1bbf4-288">Division</span></span>    |<span data-ttu-id="1bbf4-289">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="1bbf4-289">Division policy</span></span>         |<span data-ttu-id="1bbf4-290">3</span><span class="sxs-lookup"><span data-stu-id="1bbf4-290">3</span></span>         |
|<span data-ttu-id="1bbf4-291">Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bbf4-291">Subsidiary</span></span>   |<span data-ttu-id="1bbf4-292">子会社のポリシー</span><span class="sxs-lookup"><span data-stu-id="1bbf4-292">Subsidiary policy</span></span>        |<span data-ttu-id="1bbf4-293">4</span><span class="sxs-lookup"><span data-stu-id="1bbf4-293">4</span></span>         |

<span data-ttu-id="1bbf4-294">西部地域グループから西部地域ポリシーを削除すると、ポリシーの割り当てと優先順位が次のように更新されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-294">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="1bbf4-295">グループ名</span><span class="sxs-lookup"><span data-stu-id="1bbf4-295">Group name</span></span>  |<span data-ttu-id="1bbf4-296">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="1bbf4-296">Policy name</span></span>  |<span data-ttu-id="1bbf4-297">[ランク]</span><span class="sxs-lookup"><span data-stu-id="1bbf4-297">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="1bbf4-298">売上</span><span class="sxs-lookup"><span data-stu-id="1bbf4-298">Sales</span></span>    |<span data-ttu-id="1bbf4-299">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="1bbf4-299">Sales policy</span></span>       | <span data-ttu-id="1bbf4-300">1</span><span class="sxs-lookup"><span data-stu-id="1bbf4-300">1</span></span>        |
|<span data-ttu-id="1bbf4-301">課</span><span class="sxs-lookup"><span data-stu-id="1bbf4-301">Division</span></span>    |<span data-ttu-id="1bbf4-302">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="1bbf4-302">Division policy</span></span>         |<span data-ttu-id="1bbf4-303">両面</span><span class="sxs-lookup"><span data-stu-id="1bbf4-303">2</span></span>         |
|<span data-ttu-id="1bbf4-304">Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bbf4-304">Subsidiary</span></span>   |<span data-ttu-id="1bbf4-305">子会社のポリシー</span><span class="sxs-lookup"><span data-stu-id="1bbf4-305">Subsidiary policy</span></span>        |<span data-ttu-id="1bbf4-306">3</span><span class="sxs-lookup"><span data-stu-id="1bbf4-306">3</span></span>        |

<span data-ttu-id="1bbf4-307">この例では、グループから Teams の会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-307">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="1bbf4-308">詳細については、「 [CsGroupPolicyAssignment の削除](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-308">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="1bbf4-309">グループのポリシー割り当てを変更する</span><span class="sxs-lookup"><span data-stu-id="1bbf4-309">Change a policy assignment for a group</span></span>

<span data-ttu-id="1bbf4-310">グループにポリシーを割り当てると、 ```Set-CsGroupPolicyAssignmentd```コマンドレットを使用して、グループのポリシー割り当てを次のように変更できます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-310">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="1bbf4-311">順位を変更する</span><span class="sxs-lookup"><span data-stu-id="1bbf4-311">Change the ranking</span></span>
- <span data-ttu-id="1bbf4-312">指定したポリシーの種類のポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="1bbf4-312">Change the policy of a given policy type</span></span>
- <span data-ttu-id="1bbf4-313">指定したポリシーの種類とランク付けのポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="1bbf4-313">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="1bbf4-314">この例では、グループの Teams のコールパークポリシーを、SupportCallPark という名前のポリシーに変更し、割り当てのランク付けを3に変更します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-314">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="1bbf4-315">詳細については、「 [CsGroupPolicyAssignment を設定](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-315">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="1bbf4-316">ユーザーの有効なポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="1bbf4-316">Change the effective policy for a user</span></span>

<span data-ttu-id="1bbf4-317">直接ポリシーを割り当てられているユーザーの有効なポリシーを変更する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-317">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="1bbf4-318">まず、 ```Get-CsUserPolicyAssignment```コマンドレットを```PolicySource```パラメーターと共に使用して、ユーザーに関連付けられている Teams 会議ブロードキャストポリシーの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-318">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="1bbf4-319">詳細については、「 [CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-319">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="1bbf4-320">出力には、ユーザーが [従業員イベント] という名前の Teams 会議ブロードキャストポリシーが直接割り当てられていることが示されます。これは、ユーザーが所属するグループに割り当てられているベンダーライブイベントという名前のポリシーに優先されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-320">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="1bbf4-321">次に、ユーザーから従業員のイベントポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-321">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="1bbf4-322">つまり、ユーザーは、そのユーザーに直接割り当てられた Teams 会議ブロードキャストポリシーを持っておらず、ユーザーが所属するグループに割り当てられているベンダーのライブイベントポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-322">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="1bbf4-323">この操作を行うには、Skype for Business PowerShell モジュールの次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-323">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="1bbf4-324">この操作を行うには、Teams Powershell モジュールの次のコマンドレットを使用します。これには、指定したユーザーの一覧が $users バッチポリシーの割り当てによって行われます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-324">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="1bbf4-325">ユーザーのバッチにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1bbf4-325">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="1bbf4-326">バッチポリシーパッケージの割り当てでは、スクリプトを使わずに、一度に多くのユーザーにポリシーパッケージを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-326">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="1bbf4-327">```New-CsBatchPolicyPackageAssignmentOperation```コマンドレットを使用して、割り当てるユーザーのバッチと、割り当てるポリシーパッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-327">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="1bbf4-328">割り当てはバックグラウンド操作として処理され、各バッチに対して操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-328">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="1bbf4-329">その後、 ```Get-CsBatchPolicyAssignmentOperation```コマンドレットを使用して、バッチ内の課題の進捗状況と状態を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-329">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="1bbf4-330">バッチには最大2万ユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-330">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="1bbf4-331">ユーザーは、オブジェクト Id、UPN、SIP アドレス、またはメールアドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-331">You can specify users by their object Id, UPN, SIP address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bbf4-332">現時点では、5000ユーザーのバッチでポリシーパッケージを一度に割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-332">We're currently recommending that you assign policy packages in batches of 5,000 users at a time.</span></span> <span data-ttu-id="1bbf4-333">こうした需要が増加すると、処理時間の遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-333">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="1bbf4-334">これらの増加した処理時間の影響を最小限に抑えるために、最大5000人のユーザーに対して少量のバッチサイズを送信し、前のバッチが完了した後でのみ各バッチを送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-334">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="1bbf4-335">通常の営業時間外にバッチを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-335">Submitting batches outside your regular business hours can also help.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="1bbf4-336">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="1bbf4-336">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="1bbf4-337">[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールするには、次を実行します (まだインストールされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-337">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="1bbf4-338">バージョン1.0.5 以降をインストールしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-338">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="1bbf4-339">Teams に接続してセッションを開始するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-339">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="1bbf4-340">メッセージが表示されたら、管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-340">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="1bbf4-341">ユーザーのバッチにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1bbf4-341">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="1bbf4-342">この例では、 ```New-CsBatchPolicyPackageAssignmentOperation```コマンドレットを使用して、Education_PrimaryStudent ポリシーパッケージをユーザーのバッチに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-342">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="1bbf4-343">詳細については、「 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-343">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="1bbf4-344">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="1bbf4-344">Get the status of a batch assignment</span></span>

<span data-ttu-id="1bbf4-345">バッチ割り当ての状態を取得するには、次を実行します。 OperationId は、指定された```New-CsBatchPolicyAssignmentOperation```バッチのコマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-345">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="1bbf4-346">出力にエラーが発生したことが示された場合は、次を実行して、 ```UserState```プロパティのエラーに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-346">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="1bbf4-347">詳細については、「 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbf4-347">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="1bbf4-348">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bbf4-348">Related topics</span></span>

- [<span data-ttu-id="1bbf4-349">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="1bbf4-349">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)