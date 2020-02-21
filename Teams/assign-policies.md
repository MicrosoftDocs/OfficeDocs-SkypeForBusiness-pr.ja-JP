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
ms.openlocfilehash: cb1c5fd43379388327de5e517409f01f7f52ed1b
ms.sourcegitcommit: d7be89019dd5a3b88b0840bddf1b88fea8598ea7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170763"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="e389f-103">Microsoft Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e389f-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="e389f-104">**この記事で説明されている Microsoft Teams の機能の2つに、[グループへ](#assign-a-policy-to-a-group)の[バッチポリシーの割り当て](#assign-a-policy-to-a-batch-of-users)とポリシーの割り当てが現在プレビュー中です。**</span><span class="sxs-lookup"><span data-stu-id="e389f-104">**Two of the Microsoft Teams features discussed in this article, [batch policy assignment](#assign-a-policy-to-a-batch-of-users) and [policy assignment to groups](#assign-a-policy-to-a-group), are currently in preview.**</span></span>

<span data-ttu-id="e389f-105">管理者は、ポリシーを使って、組織内のユーザーが利用できる Teams 機能を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="e389f-105">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="e389f-106">たとえば、通話ポリシー、会議ポリシー、メッセージポリシーなどは、ほんの少しだけ名前にします。</span><span class="sxs-lookup"><span data-stu-id="e389f-106">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="e389f-107">組織によって、独自のニーズとユーザー設定のポリシーを持つさまざまな種類のユーザーが、それらのニーズに応じてさまざまなユーザーのセットに対してポリシー設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="e389f-107">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="e389f-108">組織内のポリシーを簡単に管理できるように、Teams には、ユーザーにポリシーを割り当てるためのいくつかの方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e389f-108">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="e389f-109">ポリシーは、個別に、またはバッチの割り当てを通じて、またはユーザーがメンバーになっているグループに直接割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e389f-109">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="e389f-110">ポリシーパッケージを使用して、同じようなロールを持つ組織内のユーザーにポリシーの事前設定されたコレクションを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="e389f-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="e389f-111">選択するオプションは、管理しているポリシーの数と、割り当てられているユーザーの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e389f-111">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="e389f-112">この記事では、ユーザーにポリシーを割り当てることができるさまざまな方法について説明します。また、どのような場合に使用するかについての推奨されるシナリオ</span><span class="sxs-lookup"><span data-stu-id="e389f-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="e389f-113">どのポリシーが優先されますか?</span><span class="sxs-lookup"><span data-stu-id="e389f-113">Which policy takes precedence?</span></span>

<span data-ttu-id="e389f-114">ユーザーには、ポリシーの種類ごとに1つの有効なポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="e389f-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="e389f-115">ユーザーに直接ポリシーが割り当てられている可能性があります。また、同じ種類のポリシーが割り当てられた1つ以上のグループのメンバーでもあります。</span><span class="sxs-lookup"><span data-stu-id="e389f-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="e389f-116">これらの種類のシナリオでは、どのポリシーが優先されますか。</span><span class="sxs-lookup"><span data-stu-id="e389f-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="e389f-117">ユーザーの有効なポリシーは、次のように、優先順位の規則に従って決定されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="e389f-118">ユーザーに直接ポリシーが割り当てられている場合 (個別に、またはバッチ割り当てによって)、ポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="e389f-119">次の例では、ユーザーの有効なポリシーは、ユーザーに直接割り当てられている Lincoln Square 会議ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="e389f-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![直接割り当てられたポリシーの優先順位を示す図](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="e389f-121">ユーザーに特定の種類のポリシーが直接割り当てられていない場合、そのユーザーがメンバーになっているグループに割り当てられているポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="e389f-122">ユーザーが複数のグループのメンバーである場合は、指定したポリシーの種類に対して最も優先順位が高い[グループ割り当て](#group-assignment-ranking)を持つポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="e389f-123">この例では、ユーザーの有効なポリシーは Exec Teams と HD ポリシーで、ユーザーがメンバーになっている他のグループとの相対的な割り当ての順位が高く、同じポリシーの種類のポリシーも割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e389f-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![グループから継承されたポリシーが優先される方法を示す図](media/assign-policies-example-group.png)

<span data-ttu-id="e389f-125">ユーザーが直接ポリシーを割り当てられていない場合や、ポリシーが割り当てられているグループのメンバーでない場合、ユーザーはそのポリシーの種類に対してグローバル (組織全体の既定の) ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="e389f-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="e389f-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e389f-126">Here's an example.</span></span>

![グローバルポリシーの優先順位を示す図](media/assign-policies-example-global.png)

<span data-ttu-id="e389f-128">詳細については、「[優先順位規則](#precedence-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="e389f-129">ポリシーを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="e389f-129">Ways to assign policies</span></span>

<span data-ttu-id="e389f-130">ここでは、ユーザーにポリシーを割り当てる方法の概要と、それぞれの推奨されるシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e389f-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="e389f-131">詳細については、リンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="e389f-131">Click the links to learn more.</span></span>

|<span data-ttu-id="e389f-132">操作</span><span class="sxs-lookup"><span data-stu-id="e389f-132">Do this</span></span>  |<span data-ttu-id="e389f-133">もし。。。</span><span class="sxs-lookup"><span data-stu-id="e389f-133">If...</span></span>  | <span data-ttu-id="e389f-134">使用するのは...</span><span class="sxs-lookup"><span data-stu-id="e389f-134">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="e389f-135">個々のユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e389f-135">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="e389f-136">チームを初めて使い始めたり、少数のユーザーに1つまたはいくつかのポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e389f-136">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="e389f-137">Skype for Business Online PowerShell モジュールの Microsoft Teams 管理センターまたは PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="e389f-137">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="e389f-138">ポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e389f-138">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="e389f-139">同じロールまたは類似のロールを持つ組織内の特定のユーザーのセットに、複数のポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e389f-139">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="e389f-140">たとえば、学校の教師に教育 (教師) ポリシーパッケージを割り当てることで、チャット、通話、会議、および教育 (第2章の学校) ポリシーパッケージへのフルアクセスを許可し、次のような機能を制限することができます。プライベート通話。</span><span class="sxs-lookup"><span data-stu-id="e389f-140">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="e389f-141">Teams PowerShell モジュールの Microsoft Teams 管理センターまたは PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="e389f-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="e389f-142">[ユーザーのバッチにポリシーを割り当てる](#assign-a-policy-to-a-batch-of-users)(プレビュー中)</span><span class="sxs-lookup"><span data-stu-id="e389f-142">[Assign a policy to a batch of users](#assign-a-policy-to-a-batch-of-users) (in preview)</span></span>   | <span data-ttu-id="e389f-143">多数のユーザーにポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e389f-143">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="e389f-144">たとえば、組織内の数百または数千のユーザーに一度にポリシーを割り当てる必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="e389f-144">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="e389f-145">Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="e389f-145">PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="e389f-146">[グループにポリシーを割り当てる](#assign-a-policy-to-a-group)(プレビュー中)</span><span class="sxs-lookup"><span data-stu-id="e389f-146">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="e389f-147">ユーザーのグループメンバーシップに基づいてポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e389f-147">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="e389f-148">たとえば、セキュリティグループまたは組織単位のすべてのユーザーにポリシーを割り当てる必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="e389f-148">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="e389f-149">Teams PowerShell モジュールの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="e389f-149">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="e389f-150">ユーザーのバッチにポリシーパッケージを割り当てる (近日公開)</span><span class="sxs-lookup"><span data-stu-id="e389f-150">Assign a policy package to a batch of users (coming soon)</span></span> |||
| <span data-ttu-id="e389f-151">グループにポリシーパッケージを割り当てる (近日公開)</span><span class="sxs-lookup"><span data-stu-id="e389f-151">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="e389f-152">個々のユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e389f-152">Assign a policy to individual users</span></span>

<span data-ttu-id="e389f-153">個々のユーザーに、または一度に少数のユーザーにポリシーを割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e389f-153">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e389f-154">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="e389f-154">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e389f-155">ユーザーにポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e389f-155">To assign a policy to a user:</span></span>

1. <span data-ttu-id="e389f-156">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e389f-156">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="e389f-157">ユーザー名の左側をクリックしてユーザーを選び、[**設定の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e389f-157">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="e389f-158">割り当てるポリシーを選択し、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e389f-158">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="e389f-159">一度に最大20人のユーザーにポリシーを割り当てるには、「 [Teams のユーザー設定を一括](edit-user-settings-in-bulk.md)して編集する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-159">To assign a policy to up to 20 users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="e389f-160">または、次の操作も行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e389f-160">Or, you can also do the following:</span></span>

1. <span data-ttu-id="e389f-161">Microsoft Teams 管理センターの左側のナビゲーションで、[ポリシー] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e389f-161">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="e389f-162">ポリシー名の左側をクリックして、割り当てるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e389f-162">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="e389f-163">[**ユーザーの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e389f-163">Select **Manage users**.</span></span>
4. <span data-ttu-id="e389f-164">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e389f-164">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="e389f-165">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e389f-165">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="e389f-166">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e389f-166">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e389f-167">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="e389f-167">Using PowerShell</span></span>

<span data-ttu-id="e389f-168">各ポリシーの種類には、それらを管理するための独自のコマンドレットのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="e389f-168">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="e389f-169">指定し```Grant-```たポリシーの種類に対してコマンドレットを使用して、ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e389f-169">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="e389f-170">たとえば、 ```Grant-CsTeamsMeetingPolicy```コマンドレットを使用して、Teams 会議ポリシーをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e389f-170">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="e389f-171">これらのコマンドレットは、Skype for business Online PowerShell モジュールに含まれており、 [skype For business コマンドレットのリファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="e389f-171">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="e389f-172">[Skype For Business Online PowerShell モジュール](https://www.microsoft.com/en-us/download/details.aspx?id=39366)をダウンロードしてインストールし (まだインストールしていない場合)、次を実行して Skype For business online に接続してセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="e389f-172">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="e389f-173">この例では、Student Meeting ポリシーという名前の Teams 会議ポリシーを、Reda という名前のユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="e389f-173">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="e389f-174">詳細については、「PowerShell を使用した[ポリシーの管理](teams-powershell-overview.md#managing-policies-via-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-174">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="e389f-175">ポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e389f-175">Assign a policy package</span></span>

<span data-ttu-id="e389f-176">Teams のポリシーパッケージは、組織内で同じまたは類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="e389f-176">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="e389f-177">各ポリシーパッケージは、ユーザーロールに基づいて設計されています。定義済みのポリシーとポリシー設定が含まれており、その役割の一般的なアクティビティをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e389f-177">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="e389f-178">ポリシーパッケージの例としては、教育機関 (教師) パッケージと医療 (臨床労働者) パッケージがあります。</span><span class="sxs-lookup"><span data-stu-id="e389f-178">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="e389f-179">ポリシーパッケージをユーザーに割り当てると、パッケージ内のポリシーが作成され、ユーザーのニーズに合わせてパッケージ内の各ポリシーの設定をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="e389f-179">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="e389f-180">ポリシーパッケージの詳細については、「[チームで](manage-policy-packages.md)ポリシーパッケージを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-180">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="e389f-181">ユーザーのバッチにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e389f-181">Assign a policy to a batch of users</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]
 
<span data-ttu-id="e389f-182">バッチポリシーが割り当てられている場合は、スクリプトを使わずに、一度に多くのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e389f-182">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="e389f-183">```New-CsBatchPolicyAssignmentOperationd```コマンドレットを使用して、ユーザーと割り当てるポリシーのバッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="e389f-183">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="e389f-184">割り当てはバックグラウンド操作として処理され、各バッチに対して操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-184">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="e389f-185">その後、 ```Get-CsBatchPolicyAssignmentOperation```コマンドレットを使用して、バッチ内の課題の進捗状況と状態を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="e389f-185">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="e389f-186">バッチには最大2万ユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e389f-186">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="e389f-187">ユーザーは、オブジェクト Id、ユーザープリンシパル名 (UPN)、セッション開始プロトコル (SIP) アドレス、またはメールアドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="e389f-187">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span>

> [!NOTE]
> <span data-ttu-id="e389f-188">現時点では、すべてのチームポリシーの種類でバッチポリシーの割り当ては使用できません。</span><span class="sxs-lookup"><span data-stu-id="e389f-188">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="e389f-189">サポートされているポリシーの種類の一覧については、「 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-189">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="e389f-190">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="e389f-190">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="e389f-191">コマンドレットは、Teams PowerShell モジュールのプレリリースバージョンに含まれています。</span><span class="sxs-lookup"><span data-stu-id="e389f-191">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="e389f-192">次の手順に従って、最初に使用できるバージョンの Teams PowerShell モジュールをアンインストールし (インストールされている場合)、PowerShell テストギャラリーから最新のプレリリース版のモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e389f-192">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="e389f-193">まだインストールしていない場合は、次のように実行して、PowerShell テストギャラリーを信頼できるソースとして登録します。</span><span class="sxs-lookup"><span data-stu-id="e389f-193">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="e389f-194">一般的な Teams PowerShell モジュールのバージョンがインストールされている場合は、次のように実行してアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="e389f-194">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="e389f-195">次を実行して、PowerShell テストギャラリーから最新の Microsoft Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e389f-195">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="e389f-196">Teams に接続してセッションを開始するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e389f-196">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="e389f-197">メッセージが表示されたら、管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="e389f-197">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="e389f-198">Graph モジュール用 Azure AD PowerShell をインストールして接続する (オプション)</span><span class="sxs-lookup"><span data-stu-id="e389f-198">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="e389f-199">また、組織内のユーザーのリストを取得できるように[、AZURE Ad PowerShell For Graph モジュール](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)(まだインストールしていない場合) をダウンロードしてインストールし、azure ad に接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="e389f-199">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="e389f-200">Azure AD に接続するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e389f-200">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="e389f-201">メッセージが表示されたら、Teams への接続に使用したのと同じ管理者資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="e389f-201">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="e389f-202">ユーザーのバッチにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e389f-202">Assign a policy to a batch of users</span></span>

<span data-ttu-id="e389f-203">この例では、 ```New-CsBatchPolicyAssignmentOperation```コマンドレットを使用して、HR アプリセットアップポリシーという名前のアプリセットアップポリシーを、Users_ids のテキストファイルに記載されているユーザーのバッチに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e389f-203">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="e389f-204">この例では、Azure AD に接続してユーザーのコレクションを取得し、その Upn を使って指定された一連のユーザーに対して、新しい採用者のメッセージングポリシーという名前のメッセージングポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e389f-204">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="e389f-205">詳細については、「 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-205">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="e389f-206">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="e389f-206">Get the status of a batch assignment</span></span>

<span data-ttu-id="e389f-207">バッチ割り当ての状態を取得するには、次を実行します。 OperationId は、指定された```New-CsBatchPolicyAssignmentOperation```バッチのコマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="e389f-207">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="e389f-208">出力にエラーが発生したことが示された場合は、次を実行して、 ```UserState```プロパティのエラーに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="e389f-208">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="e389f-209">詳細については、「 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-209">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="e389f-210">グループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e389f-210">Assign a policy to a group</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="e389f-211">グループにポリシーを割り当てると、セキュリティグループや組織単位などのユーザーグループにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e389f-211">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="e389f-212">ポリシーの割り当ては、優先順位の規則に従ってグループのメンバーに伝達されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-212">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="e389f-213">メンバーがグループに追加またはグループから削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-213">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="e389f-214">グループにポリシー ```New-CsGroupPolicyAssignment```を割り当てるには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e389f-214">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="e389f-215">オブジェクト Id、SIP アドレス、またはメールアドレスを使用して、グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e389f-215">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="e389f-216">ポリシーを割り当てると、そのポリシーはすぐにグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e389f-216">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="e389f-217">ただし、グループのメンバーへのポリシー割り当ての反映はバックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-217">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="e389f-218">ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除されている場合は、同じことが当てはまります。</span><span class="sxs-lookup"><span data-stu-id="e389f-218">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="e389f-219">現在、グループへのポリシーの割り当ては、すべてのチームポリシーの種類では使用できません。</span><span class="sxs-lookup"><span data-stu-id="e389f-219">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="e389f-220">サポートされているポリシーの種類の一覧については、「[新しい-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-220">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="e389f-221">グループへのポリシーの割り当てについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="e389f-221">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="e389f-222">作業を始める前に、優先順位の規則とグループの割り当ての順位を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e389f-222">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="e389f-223">優先順位ルール</span><span class="sxs-lookup"><span data-stu-id="e389f-223">Precedence rules</span></span>

<span data-ttu-id="e389f-224">特定のポリシーの種類に対して、ユーザーの有効なポリシーは、次のように決定されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-224">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="e389f-225">ユーザーに直接割り当てられているポリシーは、グループに割り当てられているものと同じ種類の他のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-225">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="e389f-226">つまり、ユーザーに特定の種類のポリシーが直接割り当てられている場合、そのユーザーはグループから同じ種類のポリシーを継承しません。</span><span class="sxs-lookup"><span data-stu-id="e389f-226">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="e389f-227">これは、ユーザーが直接割り当てられた特定の種類のポリシーを持っている場合にも、グループから同じ種類のポリシーを継承できるようにするために、そのポリシーをユーザーから削除する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e389f-227">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="e389f-228">ユーザーに直接割り当てられているポリシーがなく、2つ以上のグループのメンバーである場合は、ユーザーは、ランクが最も高いグループの割り当てのポリシーを継承しています。</span><span class="sxs-lookup"><span data-stu-id="e389f-228">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="e389f-229">ユーザーが、ポリシーが割り当てられているグループのメンバーでない場合、そのポリシーの種類に対するグローバル (組織全体の既定) ポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-229">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="e389f-230">ポリシーが割り当てられているグループにユーザーが追加または削除された場合、ポリシーがグループから割り当てられていない場合、またはユーザーに直接割り当てられているポリシーが削除された場合、ユーザーの有効なポリシーは、次の規則に従って更新されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-230">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="e389f-231">グループの割り当てのランク付け</span><span class="sxs-lookup"><span data-stu-id="e389f-231">Group assignment ranking</span></span>
 
<span data-ttu-id="e389f-232">グループにポリシーを割り当てるときは、グループの割り当ての順位を指定します。</span><span class="sxs-lookup"><span data-stu-id="e389f-232">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="e389f-233">ユーザーが2つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合に、ユーザーが有効なポリシーとしてどのポリシーを継承するかを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-233">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="e389f-234">グループの割り当ての順位は、同じ種類の他のグループ割り当てと相対的に異なります。</span><span class="sxs-lookup"><span data-stu-id="e389f-234">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="e389f-235">たとえば、2つのグループに通話ポリシーを割り当てる場合は、1つの割り当ての順位を1に設定して、ランクを1に設定します。</span><span class="sxs-lookup"><span data-stu-id="e389f-235">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="e389f-236">グループの割り当てのランクは、継承に関する他のグループメンバーシップよりも、どのグループメンバーシップが重要であるかを示します。</span><span class="sxs-lookup"><span data-stu-id="e389f-236">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="e389f-237">たとえば、2つのグループがあり、従業員とストアマネージャーが保存されているとします。</span><span class="sxs-lookup"><span data-stu-id="e389f-237">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="e389f-238">どちらのグループにもチームの通話ポリシーが割り当てられ、従業員の通話ポリシーとストアマネージャーの通話ポリシーがそれぞれ保存されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-238">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="e389f-239">両方のグループに参加しているストアマネージャーの場合、管理者としての役割は従業員としての役割よりも関連しているため、ストア管理者グループに割り当てられている通話ポリシーの順位は高くする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e389f-239">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="e389f-240">化</span><span class="sxs-lookup"><span data-stu-id="e389f-240">Group</span></span> |<span data-ttu-id="e389f-241">チーム呼び出しポリシー名</span><span class="sxs-lookup"><span data-stu-id="e389f-241">Teams calling policy name</span></span>  |<span data-ttu-id="e389f-242">[ランク]</span><span class="sxs-lookup"><span data-stu-id="e389f-242">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="e389f-243">ストアマネージャー</span><span class="sxs-lookup"><span data-stu-id="e389f-243">Store Managers</span></span>   |<span data-ttu-id="e389f-244">ストアマネージャーの通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="e389f-244">Store Managers Calling Policy</span></span>         |<span data-ttu-id="e389f-245">1</span><span class="sxs-lookup"><span data-stu-id="e389f-245">1</span></span>|
|<span data-ttu-id="e389f-246">従業員の保存</span><span class="sxs-lookup"><span data-stu-id="e389f-246">Store Employees</span></span>    |<span data-ttu-id="e389f-247">従業員の通話ポリシーの保存</span><span class="sxs-lookup"><span data-stu-id="e389f-247">Store Employees Calling Policy</span></span>      |<span data-ttu-id="e389f-248">両面</span><span class="sxs-lookup"><span data-stu-id="e389f-248">2</span></span>|

<span data-ttu-id="e389f-249">ランクを指定しない場合、ポリシーの割り当てには最も優先順位が設定されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-249">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="e389f-250">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="e389f-250">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="e389f-251">コマンドレットは、Teams PowerShell モジュールのプレリリースバージョンに含まれています。</span><span class="sxs-lookup"><span data-stu-id="e389f-251">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="e389f-252">次の手順に従って、最初に使用できるバージョンの Teams PowerShell モジュールをアンインストールし (インストールされている場合)、PowerShell テストギャラリーから最新のプレリリース版のモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e389f-252">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="e389f-253">まだインストールしていない場合は、次のように実行して、PowerShell テストギャラリーを信頼できるソースとして登録します。</span><span class="sxs-lookup"><span data-stu-id="e389f-253">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="e389f-254">一般的な Teams PowerShell モジュールのバージョンがインストールされている場合は、次のように実行してアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="e389f-254">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="e389f-255">次を実行して、PowerShell テストギャラリーから最新の Microsoft Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e389f-255">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="e389f-256">Teams に接続してセッションを開始するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e389f-256">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="e389f-257">メッセージが表示されたら、管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="e389f-257">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="e389f-258">グループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e389f-258">Assign a policy to a group</span></span>

<span data-ttu-id="e389f-259">この例では、コマンドレット```New-CsGroupPolicyAssignment```を使用して、[小売マネージャー] 会議ポリシーという名前の Teams 会議ポリシーを割り当てランキング1のグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e389f-259">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="e389f-260">詳細については、「[新しい-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-260">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="e389f-261">グループのポリシー割り当てを取得する</span><span class="sxs-lookup"><span data-stu-id="e389f-261">Get policy assignments for a group</span></span>

<span data-ttu-id="e389f-262">グループに```Get-CsGroupPolicyAssignment```割り当てられているすべてのポリシーを取得するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e389f-262">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="e389f-263">グループは、その SIP アドレスまたはメールアドレスがポリシーの割り当てに使用されていた場合でも、常にグループ Id によって一覧表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-263">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="e389f-264">この例では、特定のグループに割り当てられているすべてのポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="e389f-264">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="e389f-265">この例では、Teams 会議ポリシーが割り当てられているすべてのグループを返します。</span><span class="sxs-lookup"><span data-stu-id="e389f-265">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="e389f-266">詳細については、「 [CsGroupPolicyAssignment の取得](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-266">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="e389f-267">グループからポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="e389f-267">Remove a policy from a group</span></span>

<span data-ttu-id="e389f-268">グループから```Remove-CsGroupPolicyAssignment```ポリシーを削除するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e389f-268">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="e389f-269">グループからポリシーを削除すると、そのグループに割り当てられている同じ種類の他のポリシーの優先順位が更新されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-269">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="e389f-270">たとえば、ランクが2のポリシーを削除した場合、ランクが3と4のポリシーは、新しいランク付けを反映して更新されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-270">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="e389f-271">次の2つの表は、この例を示しています。</span><span class="sxs-lookup"><span data-stu-id="e389f-271">The following two tables show this example.</span></span>

<span data-ttu-id="e389f-272">ここでは、Teams 会議ポリシーのポリシー割り当てと優先度の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e389f-272">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="e389f-273">グループ名</span><span class="sxs-lookup"><span data-stu-id="e389f-273">Group name</span></span>  |<span data-ttu-id="e389f-274">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="e389f-274">Policy name</span></span>  |<span data-ttu-id="e389f-275">[ランク]</span><span class="sxs-lookup"><span data-stu-id="e389f-275">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="e389f-276">売上</span><span class="sxs-lookup"><span data-stu-id="e389f-276">Sales</span></span>    |<span data-ttu-id="e389f-277">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="e389f-277">Sales policy</span></span>       | <span data-ttu-id="e389f-278">1</span><span class="sxs-lookup"><span data-stu-id="e389f-278">1</span></span>        |
|<span data-ttu-id="e389f-279">西部地域</span><span class="sxs-lookup"><span data-stu-id="e389f-279">West Region</span></span>     |<span data-ttu-id="e389f-280">西部地域ポリシー</span><span class="sxs-lookup"><span data-stu-id="e389f-280">West Region policy</span></span>         |<span data-ttu-id="e389f-281">両面</span><span class="sxs-lookup"><span data-stu-id="e389f-281">2</span></span>         |
|<span data-ttu-id="e389f-282">課</span><span class="sxs-lookup"><span data-stu-id="e389f-282">Division</span></span>    |<span data-ttu-id="e389f-283">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="e389f-283">Division policy</span></span>         |<span data-ttu-id="e389f-284">3</span><span class="sxs-lookup"><span data-stu-id="e389f-284">3</span></span>         |
|<span data-ttu-id="e389f-285">Microsoft</span><span class="sxs-lookup"><span data-stu-id="e389f-285">Subsidiary</span></span>   |<span data-ttu-id="e389f-286">子会社のポリシー</span><span class="sxs-lookup"><span data-stu-id="e389f-286">Subsidiary policy</span></span>        |<span data-ttu-id="e389f-287">4</span><span class="sxs-lookup"><span data-stu-id="e389f-287">4</span></span>         |

<span data-ttu-id="e389f-288">西部地域グループから西部地域ポリシーを削除すると、ポリシーの割り当てと優先順位が次のように更新されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-288">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="e389f-289">グループ名</span><span class="sxs-lookup"><span data-stu-id="e389f-289">Group name</span></span>  |<span data-ttu-id="e389f-290">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="e389f-290">Policy name</span></span>  |<span data-ttu-id="e389f-291">[ランク]</span><span class="sxs-lookup"><span data-stu-id="e389f-291">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="e389f-292">売上</span><span class="sxs-lookup"><span data-stu-id="e389f-292">Sales</span></span>    |<span data-ttu-id="e389f-293">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="e389f-293">Sales policy</span></span>       | <span data-ttu-id="e389f-294">1</span><span class="sxs-lookup"><span data-stu-id="e389f-294">1</span></span>        |
|<span data-ttu-id="e389f-295">課</span><span class="sxs-lookup"><span data-stu-id="e389f-295">Division</span></span>    |<span data-ttu-id="e389f-296">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="e389f-296">Division policy</span></span>         |<span data-ttu-id="e389f-297">両面</span><span class="sxs-lookup"><span data-stu-id="e389f-297">2</span></span>         |
|<span data-ttu-id="e389f-298">Microsoft</span><span class="sxs-lookup"><span data-stu-id="e389f-298">Subsidiary</span></span>   |<span data-ttu-id="e389f-299">子会社のポリシー</span><span class="sxs-lookup"><span data-stu-id="e389f-299">Subsidiary policy</span></span>        |<span data-ttu-id="e389f-300">3</span><span class="sxs-lookup"><span data-stu-id="e389f-300">3</span></span>        |

<span data-ttu-id="e389f-301">この例では、グループから Teams の会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e389f-301">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="e389f-302">詳細については、「 [CsGroupPolicyAssignment の削除](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-302">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="e389f-303">グループのポリシー割り当てを変更する</span><span class="sxs-lookup"><span data-stu-id="e389f-303">Change a policy assignment for a group</span></span>

<span data-ttu-id="e389f-304">グループにポリシーを割り当てると、 ```Set-CsGroupPolicyAssignmentd```コマンドレットを使用して、グループのポリシー割り当てを次のように変更できます。</span><span class="sxs-lookup"><span data-stu-id="e389f-304">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="e389f-305">順位を変更する</span><span class="sxs-lookup"><span data-stu-id="e389f-305">Change the ranking</span></span>
- <span data-ttu-id="e389f-306">指定したポリシーの種類のポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="e389f-306">Change the policy of a given policy type</span></span>
- <span data-ttu-id="e389f-307">指定したポリシーの種類とランク付けのポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="e389f-307">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="e389f-308">この例では、グループの Teams のコールパークポリシーを、SupportCallPark という名前のポリシーに変更し、割り当てのランク付けを3に変更します。</span><span class="sxs-lookup"><span data-stu-id="e389f-308">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="e389f-309">詳細については、「 [CsGroupPolicyAssignment を設定](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-309">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="e389f-310">ユーザーの有効なポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="e389f-310">Change the effective policy for a user</span></span>

<span data-ttu-id="e389f-311">直接ポリシーを割り当てられているユーザーの有効なポリシーを変更する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e389f-311">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="e389f-312">まず、 ```Get-CsUserPolicyAssignment```コマンドレットを```PolicySource```パラメーターと共に使用して、ユーザーに関連付けられている Teams 会議ブロードキャストポリシーの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="e389f-312">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="e389f-313">詳細については、「 [CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e389f-313">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="e389f-314">出力には、ユーザーが [従業員イベント] という名前の Teams 会議ブロードキャストポリシーが直接割り当てられていることが示されます。これは、ユーザーが所属するグループに割り当てられているベンダーライブイベントという名前のポリシーに優先されます。</span><span class="sxs-lookup"><span data-stu-id="e389f-314">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="e389f-315">次に、ユーザーから従業員のイベントポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e389f-315">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="e389f-316">つまり、ユーザーは、そのユーザーに直接割り当てられた Teams 会議ブロードキャストポリシーを持っておらず、ユーザーが所属するグループに割り当てられているベンダーのライブイベントポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="e389f-316">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="e389f-317">この操作を行うには、Skype for Business PowerShell モジュールの次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e389f-317">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="e389f-318">この操作を行うには、Teams Powershell モジュールの次のコマンドレットを使用します。これには、指定したユーザーの一覧が $users バッチポリシーの割り当てによって行われます。</span><span class="sxs-lookup"><span data-stu-id="e389f-318">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="related-topics"></a><span data-ttu-id="e389f-319">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e389f-319">Related topics</span></span>

- [<span data-ttu-id="e389f-320">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="e389f-320">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)