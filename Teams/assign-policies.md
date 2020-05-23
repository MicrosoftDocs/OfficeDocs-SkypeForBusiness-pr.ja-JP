---
title: Microsoft Teams でユーザーにライセンスを割り当てる
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
description: Microsoft Teams でユーザーにポリシーを割り当てるさまざまな方法について説明します。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: aa63a0cc7ce24390228cc9d87adf054348c6522d
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350041"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="a9b72-103">Microsoft Teams でユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9b72-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="a9b72-104">**この記事で説明されている Microsoft Teams の機能の1つである [[グループへの割り当て](#assign-a-policy-to-a-group)] は、現在プライベートプレビューでのみ利用できます。この機能の Powershell コマンドレットは、プレリリースチームの PowerShell モジュールに含まれています。**</span><span class="sxs-lookup"><span data-stu-id="a9b72-104">**One of the Microsoft Teams features discussed in this article, [policy assignment to groups](#assign-a-policy-to-a-group), is currently only available in private preview. The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span> <span data-ttu-id="a9b72-105">この機能のリリース状況を把握するには、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-105">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="a9b72-106">管理者は、ポリシーを使って、組織内のユーザーが利用できる Teams 機能を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-106">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="a9b72-107">たとえば、通話ポリシー、会議ポリシー、メッセージポリシーなどは、ほんの少しだけ名前にします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-107">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="a9b72-108">組織によって、独自のニーズとユーザー設定のポリシーを持つさまざまな種類のユーザーが、それらのニーズに応じてさまざまなユーザーのセットに対してポリシー設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-108">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="a9b72-109">組織内のポリシーを簡単に管理できるように、Teams には、ユーザーにポリシーを割り当てるためのいくつかの方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a9b72-109">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="a9b72-110">ポリシーは、個別に、またはバッチの割り当てを通じて、またはユーザーがメンバーになっているグループに直接割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-110">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="a9b72-111">ポリシーパッケージを使用して、同じようなロールを持つ組織内のユーザーにポリシーの事前設定されたコレクションを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-111">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="a9b72-112">選択するオプションは、管理しているポリシーの数と、割り当てられているユーザーの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-112">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="a9b72-113">この記事では、ユーザーにポリシーを割り当てることができるさまざまな方法について説明します。また、どのような場合に使用するかについての推奨されるシナリオ</span><span class="sxs-lookup"><span data-stu-id="a9b72-113">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="a9b72-114">どのポリシーが優先されますか?</span><span class="sxs-lookup"><span data-stu-id="a9b72-114">Which policy takes precedence?</span></span>

<span data-ttu-id="a9b72-115">ユーザーには、ポリシーの種類ごとに1つの有効なポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-115">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="a9b72-116">ユーザーに直接ポリシーが割り当てられている可能性があります。また、同じ種類のポリシーが割り当てられた1つ以上のグループのメンバーでもあります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-116">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="a9b72-117">これらの種類のシナリオでは、どのポリシーが優先されますか。</span><span class="sxs-lookup"><span data-stu-id="a9b72-117">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="a9b72-118">ユーザーの有効なポリシーは、次のように、優先順位の規則に従って決定されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-118">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="a9b72-119">ユーザーに直接ポリシーが割り当てられている場合 (個別に、またはバッチ割り当てによって)、ポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-119">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="a9b72-120">次の例では、ユーザーの有効なポリシーは、ユーザーに直接割り当てられている Lincoln Square 会議ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="a9b72-120">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![直接割り当てられたポリシーの優先順位を示す図](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="a9b72-122">ユーザーに特定の種類のポリシーが直接割り当てられていない場合、そのユーザーがメンバーになっているグループに割り当てられているポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-122">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="a9b72-123">ユーザーが複数のグループのメンバーである場合は、指定したポリシーの種類に対して最も優先順位が高い[グループ割り当て](#group-assignment-ranking)を持つポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-123">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="a9b72-124">この例では、ユーザーの有効なポリシーは Exec Teams と HD ポリシーで、ユーザーがメンバーになっている他のグループとの相対的な割り当ての順位が高く、同じポリシーの種類のポリシーも割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-124">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![グループから継承されたポリシーが優先される方法を示す図](media/assign-policies-example-group.png)

<span data-ttu-id="a9b72-126">ユーザーが直接ポリシーを割り当てられていない場合や、ポリシーが割り当てられているグループのメンバーでない場合、ユーザーはそのポリシーの種類に対してグローバル (組織全体の既定の) ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-126">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="a9b72-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-127">Here's an example.</span></span>

![グローバルポリシーの優先順位を示す図](media/assign-policies-example-global.png)

<span data-ttu-id="a9b72-129">詳細については、「[優先順位規則](#precedence-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-129">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="a9b72-130">ポリシーを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="a9b72-130">Ways to assign policies</span></span>

<span data-ttu-id="a9b72-131">ここでは、ユーザーにポリシーを割り当てる方法の概要と、それぞれの推奨されるシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-131">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="a9b72-132">詳細については、リンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-132">Click the links to learn more.</span></span>

|<span data-ttu-id="a9b72-133">操作</span><span class="sxs-lookup"><span data-stu-id="a9b72-133">Do this</span></span>  |<span data-ttu-id="a9b72-134">もし。。。</span><span class="sxs-lookup"><span data-stu-id="a9b72-134">If...</span></span>  | <span data-ttu-id="a9b72-135">使用するのは...</span><span class="sxs-lookup"><span data-stu-id="a9b72-135">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="a9b72-136">個々のユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9b72-136">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="a9b72-137">チームを初めて使い始めたり、少数のユーザーに1つまたはいくつかのポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-137">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="a9b72-138">Skype for Business Online PowerShell モジュールの Microsoft Teams 管理センターまたは PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a9b72-138">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="a9b72-139">ポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9b72-139">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="a9b72-140">同じロールまたは類似のロールを持つ組織内の特定のユーザーのセットに、複数のポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-140">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="a9b72-141">たとえば、学校の教師に教育 (教師) ポリシーパッケージを割り当てることで、チャット、通話、会議、および教育 (第2章) ポリシーパッケージへのフルアクセスを学生に許可し、プライベート通話のような特定の機能を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-141">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="a9b72-142">Teams PowerShell モジュールの Microsoft Teams 管理センターまたは PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a9b72-142">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="a9b72-143">ユーザーのバッチにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9b72-143">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="a9b72-144">多数のユーザーにポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-144">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="a9b72-145">たとえば、組織内の数百または数千のユーザーに一度にポリシーを割り当てる必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-145">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="a9b72-146">Teams PowerShell モジュールの Microsoft Teams 管理センターまたは PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a9b72-146">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="a9b72-147">[グループにポリシーを割り当てる](#assign-a-policy-to-a-group)(プレビュー中)</span><span class="sxs-lookup"><span data-stu-id="a9b72-147">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="a9b72-148">ユーザーのグループメンバーシップに基づいてポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-148">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="a9b72-149">たとえば、セキュリティグループまたは組織単位のすべてのユーザーにポリシーを割り当てる必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-149">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="a9b72-150">Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a9b72-150">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="a9b72-151">ユーザーのバッチにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9b72-151">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="a9b72-152">同じロールまたは類似のロールを持つ組織内のユーザーのバッチに複数のポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-152">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="a9b72-153">たとえば、バッチの割り当てを使用して学校のすべての教師に教育 (教師) ポリシーパッケージを割り当てることで、チャット、通話、会議へのフルアクセスを許可したり、教育機関 (第1の学生) ポリシーパッケージを第2の学生に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-153">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="a9b72-154">Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a9b72-154">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="a9b72-155">グループにポリシーパッケージを割り当てる (近日公開)</span><span class="sxs-lookup"><span data-stu-id="a9b72-155">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="a9b72-156">個々のユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9b72-156">Assign a policy to individual users</span></span>

<span data-ttu-id="a9b72-157">個々のユーザーに、または一度に少数のユーザーにポリシーを割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-157">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a9b72-158">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="a9b72-158">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="a9b72-159">ユーザーにポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a9b72-159">To assign a policy to a user:</span></span>

1. <span data-ttu-id="a9b72-160">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-160">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="a9b72-161">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-161">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="a9b72-162">割り当てるポリシーを選択し、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-162">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="a9b72-163">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-163">Or, you can also do the following:</span></span>

1. <span data-ttu-id="a9b72-164">Microsoft Teams 管理センターの左側のナビゲーションで、[ポリシー] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-164">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="a9b72-165">ポリシー名の左側をクリックして、割り当てるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-165">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="a9b72-166">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-166">Select **Manage users**.</span></span>
4. <span data-ttu-id="a9b72-167">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-167">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="a9b72-168">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-168">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="a9b72-169">ユーザーの追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-169">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a9b72-170">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="a9b72-170">Using PowerShell</span></span>

<span data-ttu-id="a9b72-171">各ポリシーの種類には、それらを管理するための独自のコマンドレットのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-171">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="a9b72-172">指定した ```Grant-``` ポリシーの種類に対してコマンドレットを使用して、ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-172">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="a9b72-173">たとえば、コマンドレットを使用して、 ```Grant-CsTeamsMeetingPolicy``` Teams 会議ポリシーをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-173">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="a9b72-174">これらのコマンドレットは、Skype for business Online PowerShell モジュールに含まれており、 [skype For business コマンドレットのリファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="a9b72-174">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="a9b72-175">[Skype For Business Online PowerShell モジュール](https://www.microsoft.com/en-us/download/details.aspx?id=39366)をダウンロードしてインストールし (まだインストールしていない場合)、次を実行して Skype For business online に接続してセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-175">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="a9b72-176">この例では、Student Meeting ポリシーという名前の Teams 会議ポリシーを、Reda という名前のユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="a9b72-176">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="a9b72-177">詳細については、「PowerShell を使用した[ポリシーの管理](teams-powershell-overview.md#managing-policies-via-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-177">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="a9b72-178">ポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9b72-178">Assign a policy package</span></span>

<span data-ttu-id="a9b72-179">Teams のポリシーパッケージは、組織内で同じまたは類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="a9b72-179">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="a9b72-180">各ポリシーパッケージは、ユーザーロールに基づいて設計されています。定義済みのポリシーとポリシー設定が含まれており、その役割の一般的なアクティビティをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-180">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="a9b72-181">ポリシーパッケージの例としては、教育機関 (教師) パッケージと医療 (臨床労働者) パッケージがあります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-181">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="a9b72-182">ポリシーパッケージをユーザーに割り当てると、パッケージ内のポリシーが作成され、ユーザーのニーズに合わせてパッケージ内の各ポリシーの設定をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-182">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="a9b72-183">ポリシーパッケージの詳細については、「[チームで](manage-policy-packages.md)ポリシーパッケージを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-183">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="a9b72-184">ユーザーのバッチにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9b72-184">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a9b72-185">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="a9b72-185">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="a9b72-186">ユーザーに一括してポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a9b72-186">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="a9b72-187">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-187">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="a9b72-188">ポリシーを割り当てるユーザーを検索するか、ビューをフィルター処理して、目的のユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-188">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="a9b72-189">[ **&#x2713;** (チェックマーク)] 列で、ユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-189">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="a9b72-190">すべてのユーザーを選択するには、テーブルの上部にある &#x2713; (チェックマーク) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-190">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="a9b72-191">[**設定の編集**] をクリックし、必要な変更を加えて、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-191">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="a9b72-192">ポリシーの割り当ての状態を表示するには、[**適用**] をクリックしてポリシーの割り当てを提出した後、[**ユーザー** ] ページの上部に表示されるバナーで、[**アクティビティログ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-192">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="a9b72-193">または、Microsoft Teams 管理センターの左のナビゲーションで [**ダッシュボード**] に移動し、[**アクティビティログ**] の下の [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-193">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="a9b72-194">アクティビティログには、過去30日間の Microsoft Teams 管理センターを通じて、20人を超えるユーザーのバッチに対するポリシーの割り当てが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-194">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="a9b72-195">詳細については、「[アクティビティログでポリシーの割り当てを表示](activity-log.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-195">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a9b72-196">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="a9b72-196">Using PowerShell</span></span>
 
<span data-ttu-id="a9b72-197">バッチポリシーが割り当てられている場合は、スクリプトを使わずに、一度に多くのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-197">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="a9b72-198">コマンドレットを使用して、 ```New-CsBatchPolicyAssignmentOperationd``` ユーザーと割り当てるポリシーのバッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-198">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="a9b72-199">割り当てはバックグラウンド操作として処理され、各バッチに対して操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-199">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="a9b72-200">その後、コマンドレットを使用して、 ```Get-CsBatchPolicyAssignmentOperation``` バッチ内の課題の進捗状況と状態を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-200">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="a9b72-201">バッチには最大2万ユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-201">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="a9b72-202">ユーザーは、オブジェクト Id、ユーザープリンシパル名 (UPN)、セッション開始プロトコル (SIP) アドレス、またはメールアドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-202">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9b72-203">現時点では、一度に5000ユーザーのバッチでポリシーを割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-203">We're currently recommending that you assign policies in batches of 5,000 users at a time.</span></span> <span data-ttu-id="a9b72-204">こうした需要が増加すると、処理時間の遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-204">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="a9b72-205">これらの増加した処理時間の影響を最小限に抑えるために、最大5000人のユーザーに対して少量のバッチサイズを送信し、前のバッチが完了した後でのみ各バッチを送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-205">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="a9b72-206">通常の営業時間外にバッチを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-206">Submitting batches outside your regular business hours can also help.</span></span>

> [!NOTE]
> <span data-ttu-id="a9b72-207">現時点では、すべてのチームポリシーの種類でバッチポリシーの割り当ては使用できません。</span><span class="sxs-lookup"><span data-stu-id="a9b72-207">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="a9b72-208">サポートされているポリシーの種類の一覧については、「 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-208">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="a9b72-209">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="a9b72-209">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="a9b72-210">[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-210">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="a9b72-211">バージョン1.0.5 以降をインストールしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-211">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="a9b72-212">Teams に接続してセッションを開始するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-212">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="a9b72-213">メッセージが表示されたら、管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-213">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="a9b72-214">Graph モジュール用 Azure AD PowerShell をインストールして接続する (オプション)</span><span class="sxs-lookup"><span data-stu-id="a9b72-214">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="a9b72-215">また、組織内のユーザーのリストを取得できるように[、AZURE Ad PowerShell For Graph モジュール](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)(まだインストールしていない場合) をダウンロードしてインストールし、azure ad に接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-215">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="a9b72-216">Azure AD に接続するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-216">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="a9b72-217">メッセージが表示されたら、Teams への接続に使用したのと同じ管理者資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-217">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="a9b72-218">ユーザーのバッチにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9b72-218">Assign a policy to a batch of users</span></span>

<span data-ttu-id="a9b72-219">この例では、コマンドレットを使用して、 ```New-CsBatchPolicyAssignmentOperation``` HR アプリセットアップポリシーという名前のアプリセットアップポリシーを、Users_ids のテキストファイルに記載されているユーザーのバッチに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-219">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="a9b72-220">この例では、Azure AD に接続してユーザーのコレクションを取得し、その Upn を使って指定された一連のユーザーに対して、新しい採用者のメッセージングポリシーという名前のメッセージングポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-220">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="a9b72-221">詳細については、「 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-221">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="a9b72-222">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="a9b72-222">Get the status of a batch assignment</span></span>

<span data-ttu-id="a9b72-223">バッチ割り当ての状態を取得するには、次を実行します。 OperationId は、指定された ```New-CsBatchPolicyAssignmentOperation``` バッチのコマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="a9b72-223">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="a9b72-224">出力にエラーが発生したことが示された場合は、次を実行して、プロパティのエラーに関する詳細情報を取得し ```UserState``` ます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-224">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="a9b72-225">詳細については、「 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-225">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="a9b72-226">グループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9b72-226">Assign a policy to a group</span></span>

<span data-ttu-id="a9b72-227">**グループへのポリシーの割り当ては、現在プライベートプレビューでのみ利用できます。この機能のコマンドレットは、プレリリースチームの PowerShell モジュールに含まれています。**</span><span class="sxs-lookup"><span data-stu-id="a9b72-227">**Policy assignment to groups is currently only available in private preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

<span data-ttu-id="a9b72-228">グループにポリシーを割り当てると、セキュリティグループや組織単位などのユーザーグループにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-228">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="a9b72-229">ポリシーの割り当ては、優先順位の規則に従ってグループのメンバーに伝達されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-229">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="a9b72-230">メンバーがグループに追加またはグループから削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-230">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="a9b72-231">```New-CsGroupPolicyAssignment```グループにポリシーを割り当てるには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-231">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="a9b72-232">オブジェクト Id、SIP アドレス、またはメールアドレスを使用して、グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-232">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="a9b72-233">ポリシーを割り当てると、そのポリシーはすぐにグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-233">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="a9b72-234">ただし、グループのメンバーへのポリシー割り当ての反映はバックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-234">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="a9b72-235">ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除されている場合は、同じことが当てはまります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-235">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="a9b72-236">現在、グループへのポリシーの割り当ては、すべてのチームポリシーの種類では使用できません。</span><span class="sxs-lookup"><span data-stu-id="a9b72-236">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="a9b72-237">サポートされているポリシーの種類の一覧については、「[新しい-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-237">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="a9b72-238">グループへのポリシーの割り当てについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="a9b72-238">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="a9b72-239">作業を始める前に、優先順位の規則とグループの割り当ての順位を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a9b72-239">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="a9b72-240">優先順位ルール</span><span class="sxs-lookup"><span data-stu-id="a9b72-240">Precedence rules</span></span>

<span data-ttu-id="a9b72-241">特定のポリシーの種類に対して、ユーザーの有効なポリシーは、次のように決定されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-241">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="a9b72-242">ユーザーに直接割り当てられているポリシーは、グループに割り当てられているものと同じ種類の他のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-242">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="a9b72-243">つまり、ユーザーに特定の種類のポリシーが直接割り当てられている場合、そのユーザーはグループから同じ種類のポリシーを継承しません。</span><span class="sxs-lookup"><span data-stu-id="a9b72-243">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="a9b72-244">これは、ユーザーが直接割り当てられた特定の種類のポリシーを持っている場合にも、グループから同じ種類のポリシーを継承できるようにするために、そのポリシーをユーザーから削除する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-244">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="a9b72-245">ユーザーに直接割り当てられているポリシーがなく、2つ以上のグループのメンバーである場合は、ユーザーは、ランクが最も高いグループの割り当てのポリシーを継承しています。</span><span class="sxs-lookup"><span data-stu-id="a9b72-245">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="a9b72-246">ユーザーが、ポリシーが割り当てられているグループのメンバーでない場合、そのポリシーの種類に対するグローバル (組織全体の既定) ポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-246">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="a9b72-247">ポリシーが割り当てられているグループにユーザーが追加または削除された場合、ポリシーがグループから割り当てられていない場合、またはユーザーに直接割り当てられているポリシーが削除された場合、ユーザーの有効なポリシーは、次の規則に従って更新されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-247">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="a9b72-248">グループの割り当てのランク付け</span><span class="sxs-lookup"><span data-stu-id="a9b72-248">Group assignment ranking</span></span>
 
<span data-ttu-id="a9b72-249">グループにポリシーを割り当てるときは、グループの割り当ての順位を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-249">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="a9b72-250">ユーザーが2つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合に、ユーザーが有効なポリシーとしてどのポリシーを継承するかを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-250">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="a9b72-251">グループの割り当ての順位は、同じ種類の他のグループ割り当てと相対的に異なります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-251">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="a9b72-252">たとえば、2つのグループに通話ポリシーを割り当てる場合は、1つの割り当ての順位を1に設定して、ランクを1に設定します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-252">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="a9b72-253">グループの割り当てのランクは、継承に関する他のグループメンバーシップよりも、どのグループメンバーシップが重要であるかを示します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-253">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="a9b72-254">たとえば、2つのグループがあり、従業員とストアマネージャーが保存されているとします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-254">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="a9b72-255">どちらのグループにもチームの通話ポリシーが割り当てられ、従業員の通話ポリシーとストアマネージャーの通話ポリシーがそれぞれ保存されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-255">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="a9b72-256">両方のグループに参加しているストアマネージャーの場合、管理者としての役割は従業員としての役割よりも関連しているため、ストア管理者グループに割り当てられている通話ポリシーの順位は高くする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-256">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="a9b72-257">化</span><span class="sxs-lookup"><span data-stu-id="a9b72-257">Group</span></span> |<span data-ttu-id="a9b72-258">チーム呼び出しポリシー名</span><span class="sxs-lookup"><span data-stu-id="a9b72-258">Teams calling policy name</span></span>  |<span data-ttu-id="a9b72-259">[ランク]</span><span class="sxs-lookup"><span data-stu-id="a9b72-259">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="a9b72-260">ストアマネージャー</span><span class="sxs-lookup"><span data-stu-id="a9b72-260">Store Managers</span></span>   |<span data-ttu-id="a9b72-261">ストアマネージャーの通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="a9b72-261">Store Managers Calling Policy</span></span>         |<span data-ttu-id="a9b72-262">1</span><span class="sxs-lookup"><span data-stu-id="a9b72-262">1</span></span>|
|<span data-ttu-id="a9b72-263">従業員の保存</span><span class="sxs-lookup"><span data-stu-id="a9b72-263">Store Employees</span></span>    |<span data-ttu-id="a9b72-264">従業員の通話ポリシーの保存</span><span class="sxs-lookup"><span data-stu-id="a9b72-264">Store Employees Calling Policy</span></span>      |<span data-ttu-id="a9b72-265">2</span><span class="sxs-lookup"><span data-stu-id="a9b72-265">2</span></span>|

<span data-ttu-id="a9b72-266">ランクを指定しない場合、ポリシーの割り当てには最も優先順位が設定されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-266">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="a9b72-267">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="a9b72-267">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="a9b72-268">コマンドレットは、Teams PowerShell モジュールのプレリリースバージョンに含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9b72-268">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="a9b72-269">次の手順に従って、最初に使用できるバージョンの Teams PowerShell モジュールをアンインストールし (インストールされている場合)、PowerShell テストギャラリーから最新のプレリリース版のモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-269">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="a9b72-270">まだインストールしていない場合は、次のように実行して、PowerShell テストギャラリーを信頼できるソースとして登録します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-270">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="a9b72-271">一般的な Teams PowerShell モジュールのバージョンがインストールされている場合は、次のように実行してアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-271">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="a9b72-272">次を実行して、PowerShell テストギャラリーから最新の Microsoft Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-272">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="a9b72-273">Teams に接続してセッションを開始するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-273">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="a9b72-274">メッセージが表示されたら、管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-274">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="a9b72-275">グループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9b72-275">Assign a policy to a group</span></span>

<span data-ttu-id="a9b72-276">この例では、 ```New-CsGroupPolicyAssignment``` コマンドレットを使用して、[小売マネージャー] 会議ポリシーという名前の Teams 会議ポリシーを割り当てランキング1のグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-276">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="a9b72-277">詳細については、「[新しい-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-277">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="a9b72-278">グループのポリシー割り当てを取得する</span><span class="sxs-lookup"><span data-stu-id="a9b72-278">Get policy assignments for a group</span></span>

<span data-ttu-id="a9b72-279">```Get-CsGroupPolicyAssignment```グループに割り当てられているすべてのポリシーを取得するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-279">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="a9b72-280">グループは、その SIP アドレスまたはメールアドレスがポリシーの割り当てに使用されていた場合でも、常にグループ Id によって一覧表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-280">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="a9b72-281">この例では、特定のグループに割り当てられているすべてのポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-281">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="a9b72-282">この例では、Teams 会議ポリシーが割り当てられているすべてのグループを返します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-282">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="a9b72-283">詳細については、「 [CsGroupPolicyAssignment の取得](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-283">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="a9b72-284">グループからポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="a9b72-284">Remove a policy from a group</span></span>

<span data-ttu-id="a9b72-285">```Remove-CsGroupPolicyAssignment```グループからポリシーを削除するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-285">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="a9b72-286">グループからポリシーを削除すると、そのグループに割り当てられている同じ種類の他のポリシーの優先順位が更新されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-286">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="a9b72-287">たとえば、ランクが2のポリシーを削除した場合、ランクが3と4のポリシーは、新しいランク付けを反映して更新されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-287">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="a9b72-288">次の2つの表は、この例を示しています。</span><span class="sxs-lookup"><span data-stu-id="a9b72-288">The following two tables show this example.</span></span>

<span data-ttu-id="a9b72-289">ここでは、Teams 会議ポリシーのポリシー割り当てと優先度の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-289">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="a9b72-290">グループ名</span><span class="sxs-lookup"><span data-stu-id="a9b72-290">Group name</span></span>  |<span data-ttu-id="a9b72-291">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="a9b72-291">Policy name</span></span>  |<span data-ttu-id="a9b72-292">[ランク]</span><span class="sxs-lookup"><span data-stu-id="a9b72-292">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="a9b72-293">売上</span><span class="sxs-lookup"><span data-stu-id="a9b72-293">Sales</span></span>    |<span data-ttu-id="a9b72-294">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="a9b72-294">Sales policy</span></span>       | <span data-ttu-id="a9b72-295">1</span><span class="sxs-lookup"><span data-stu-id="a9b72-295">1</span></span>        |
|<span data-ttu-id="a9b72-296">西部地域</span><span class="sxs-lookup"><span data-stu-id="a9b72-296">West Region</span></span>     |<span data-ttu-id="a9b72-297">西部地域ポリシー</span><span class="sxs-lookup"><span data-stu-id="a9b72-297">West Region policy</span></span>         |<span data-ttu-id="a9b72-298">2</span><span class="sxs-lookup"><span data-stu-id="a9b72-298">2</span></span>         |
|<span data-ttu-id="a9b72-299">課</span><span class="sxs-lookup"><span data-stu-id="a9b72-299">Division</span></span>    |<span data-ttu-id="a9b72-300">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="a9b72-300">Division policy</span></span>         |<span data-ttu-id="a9b72-301">3</span><span class="sxs-lookup"><span data-stu-id="a9b72-301">3</span></span>         |
|<span data-ttu-id="a9b72-302">Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9b72-302">Subsidiary</span></span>   |<span data-ttu-id="a9b72-303">子会社のポリシー</span><span class="sxs-lookup"><span data-stu-id="a9b72-303">Subsidiary policy</span></span>        |<span data-ttu-id="a9b72-304">4</span><span class="sxs-lookup"><span data-stu-id="a9b72-304">4</span></span>         |

<span data-ttu-id="a9b72-305">西部地域グループから西部地域ポリシーを削除すると、ポリシーの割り当てと優先順位が次のように更新されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-305">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="a9b72-306">グループ名</span><span class="sxs-lookup"><span data-stu-id="a9b72-306">Group name</span></span>  |<span data-ttu-id="a9b72-307">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="a9b72-307">Policy name</span></span>  |<span data-ttu-id="a9b72-308">[ランク]</span><span class="sxs-lookup"><span data-stu-id="a9b72-308">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="a9b72-309">売上</span><span class="sxs-lookup"><span data-stu-id="a9b72-309">Sales</span></span>    |<span data-ttu-id="a9b72-310">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="a9b72-310">Sales policy</span></span>       | <span data-ttu-id="a9b72-311">1</span><span class="sxs-lookup"><span data-stu-id="a9b72-311">1</span></span>        |
|<span data-ttu-id="a9b72-312">課</span><span class="sxs-lookup"><span data-stu-id="a9b72-312">Division</span></span>    |<span data-ttu-id="a9b72-313">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="a9b72-313">Division policy</span></span>         |<span data-ttu-id="a9b72-314">2</span><span class="sxs-lookup"><span data-stu-id="a9b72-314">2</span></span>         |
|<span data-ttu-id="a9b72-315">Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9b72-315">Subsidiary</span></span>   |<span data-ttu-id="a9b72-316">子会社のポリシー</span><span class="sxs-lookup"><span data-stu-id="a9b72-316">Subsidiary policy</span></span>        |<span data-ttu-id="a9b72-317">3</span><span class="sxs-lookup"><span data-stu-id="a9b72-317">3</span></span>        |

<span data-ttu-id="a9b72-318">この例では、グループから Teams の会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-318">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="a9b72-319">詳細については、「 [CsGroupPolicyAssignment の削除](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-319">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="a9b72-320">グループのポリシー割り当てを変更する</span><span class="sxs-lookup"><span data-stu-id="a9b72-320">Change a policy assignment for a group</span></span>

<span data-ttu-id="a9b72-321">グループにポリシーを割り当てると、コマンドレットを使用し ```Set-CsGroupPolicyAssignmentd``` て、グループのポリシー割り当てを次のように変更できます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-321">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="a9b72-322">順位を変更する</span><span class="sxs-lookup"><span data-stu-id="a9b72-322">Change the ranking</span></span>
- <span data-ttu-id="a9b72-323">指定したポリシーの種類のポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="a9b72-323">Change the policy of a given policy type</span></span>
- <span data-ttu-id="a9b72-324">指定したポリシーの種類とランク付けのポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="a9b72-324">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="a9b72-325">この例では、グループの Teams のコールパークポリシーを、SupportCallPark という名前のポリシーに変更し、割り当てのランク付けを3に変更します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-325">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="a9b72-326">詳細については、「 [CsGroupPolicyAssignment を設定](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-326">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="a9b72-327">ユーザーの有効なポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="a9b72-327">Change the effective policy for a user</span></span>

<span data-ttu-id="a9b72-328">直接ポリシーを割り当てられているユーザーの有効なポリシーを変更する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-328">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="a9b72-329">まず、コマンドレットをパラメーターと共に使用して、 ```Get-CsUserPolicyAssignment``` ```PolicySource``` ユーザーに関連付けられている Teams 会議ブロードキャストポリシーの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-329">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="a9b72-330">詳細については、「 [CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-330">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="a9b72-331">出力には、ユーザーが [従業員イベント] という名前の Teams 会議ブロードキャストポリシーが直接割り当てられていることが示されます。これは、ユーザーが所属するグループに割り当てられているベンダーライブイベントという名前のポリシーに優先されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-331">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="a9b72-332">次に、ユーザーから従業員のイベントポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-332">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="a9b72-333">つまり、ユーザーは、そのユーザーに直接割り当てられた Teams 会議ブロードキャストポリシーを持っておらず、ユーザーが所属するグループに割り当てられているベンダーのライブイベントポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-333">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="a9b72-334">この操作を行うには、Skype for Business PowerShell モジュールの次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-334">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="a9b72-335">この操作を行うには、Teams Powershell モジュールの次のコマンドレットを使用します。これには、指定したユーザーの一覧が $users バッチポリシーの割り当てによって行われます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-335">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="a9b72-336">ユーザーのバッチにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9b72-336">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="a9b72-337">バッチポリシーパッケージの割り当てでは、スクリプトを使わずに、一度に多くのユーザーにポリシーパッケージを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-337">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="a9b72-338">コマンドレットを使用して、 ```New-CsBatchPolicyPackageAssignmentOperation``` 割り当てるユーザーのバッチと、割り当てるポリシーパッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-338">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="a9b72-339">割り当てはバックグラウンド操作として処理され、各バッチに対して操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-339">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="a9b72-340">その後、コマンドレットを使用して、 ```Get-CsBatchPolicyAssignmentOperation``` バッチ内の課題の進捗状況と状態を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-340">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="a9b72-341">バッチには最大2万ユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-341">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="a9b72-342">ユーザーは、オブジェクト Id、UPN、SIP アドレス、またはメールアドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-342">You can specify users by their object Id, UPN, SIP address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9b72-343">現時点では、5000ユーザーのバッチでポリシーパッケージを一度に割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-343">We're currently recommending that you assign policy packages in batches of 5,000 users at a time.</span></span> <span data-ttu-id="a9b72-344">こうした需要が増加すると、処理時間の遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9b72-344">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="a9b72-345">これらの増加した処理時間の影響を最小限に抑えるために、最大5000人のユーザーに対して少量のバッチサイズを送信し、前のバッチが完了した後でのみ各バッチを送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-345">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="a9b72-346">通常の営業時間外にバッチを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-346">Submitting batches outside your regular business hours can also help.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="a9b72-347">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="a9b72-347">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="a9b72-348">[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールするには、次を実行します (まだインストールされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="a9b72-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="a9b72-349">バージョン1.0.5 以降をインストールしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="a9b72-350">Teams に接続してセッションを開始するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9b72-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="a9b72-351">メッセージが表示されたら、管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="a9b72-351">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="a9b72-352">ユーザーのバッチにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9b72-352">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="a9b72-353">この例では、 ```New-CsBatchPolicyPackageAssignmentOperation``` コマンドレットを使用して、Education_PrimaryStudent ポリシーパッケージをユーザーのバッチに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-353">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="a9b72-354">詳細については、「 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-354">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="a9b72-355">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="a9b72-355">Get the status of a batch assignment</span></span>

<span data-ttu-id="a9b72-356">バッチ割り当ての状態を取得するには、次を実行します。 OperationId は、指定された ```New-CsBatchPolicyAssignmentOperation``` バッチのコマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="a9b72-356">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="a9b72-357">出力にエラーが発生したことが示された場合は、次を実行して、プロパティのエラーに関する詳細情報を取得し ```UserState``` ます。</span><span class="sxs-lookup"><span data-stu-id="a9b72-357">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="a9b72-358">詳細については、「 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b72-358">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="a9b72-359">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a9b72-359">Related topics</span></span>

- [<span data-ttu-id="a9b72-360">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="a9b72-360">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)