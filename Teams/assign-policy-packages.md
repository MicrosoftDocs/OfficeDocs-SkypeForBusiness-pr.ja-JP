---
title: ユーザーとグループにポリシー パッケージを割り当てる
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
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
description: ポリシー パッケージをユーザーとグループに割り当てるさまざまな方法についてMicrosoft Teams。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 0266cb5c34a13df0dac62be2258134e553a357d8
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574348"
---
# <a name="assign-policy-packages-to-users-and-groups"></a><span data-ttu-id="35585-103">ユーザーとグループにポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="35585-103">Assign policy packages to users and groups</span></span>

<span data-ttu-id="35585-104">この記事では、ユーザーとグループにポリシー パッケージを割り当てるさまざまな方法についてMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="35585-104">This article reviews the different ways to assign policy packages to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="35585-105">この記事を読む前に、「ポリシーの割り当て - [Teams」を参照してください](policy-assignment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="35585-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="35585-106">ポリシー パッケージをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="35585-106">Assign a policy package to users</span></span>

<span data-ttu-id="35585-107">Teams のポリシー パッケージは、組織内で同じまたは類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="35585-107">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="35585-108">各ポリシー パッケージは、ユーザーの役割に合わせて設計されており、その役割の一般的なアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="35585-108">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="35585-109">ポリシー パッケージの例としては、教育機関 (教師) パッケージと医療機関 (医療従事者) パッケージがあります。</span><span class="sxs-lookup"><span data-stu-id="35585-109">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="35585-110">詳細については、「[Teams でポリシー パッケージを管理する](manage-policy-packages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35585-110">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="35585-111">ポリシー パッケージを 1 人のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="35585-111">Assign a policy package to one user</span></span>

1. <span data-ttu-id="35585-112">管理センターの左側のMicrosoft Teams、[ユーザー] に移動し、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="35585-112">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="35585-113">ユーザーのページで 、[ポリシー]を選択し、[ポリシーパッケージ] の横にある [編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="35585-113">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="35585-114">[ポリシー パッケージ **の割り** 当て] ウィンドウで、割り当てるパッケージを選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="35585-114">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

![Teamsへのポリシー パッケージの割り当てに関する管理センターのスクリーンショット](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="35585-116">ポリシー パッケージを複数のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="35585-116">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="35585-117">Microsoft Teams 管理センターの左側のナビゲーションで **[ポリシー パッケージ]** に移動し、パッケージ名の左側をクリックして、割り当てるポリシー パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="35585-117">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="35585-118">**[ユーザーを管理する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35585-118">Select **Manage users**.</span></span>
3. <span data-ttu-id="35585-119">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="35585-119">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="35585-120">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="35585-120">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="35585-121">ユーザーの追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35585-121">When you're finished adding users, select **Save**.</span></span>

![Teamsユーザーへのポリシー パッケージの割り当てに関する管理センターのスクリーンショット](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="35585-123">ポリシー パッケージをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="35585-123">Assign a policy package to a group</span></span>

<span data-ttu-id="35585-124">グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="35585-124">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="35585-125">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="35585-125">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="35585-126">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="35585-126">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="35585-127">グループへのポリシー パッケージの割り当ては、最大 50,000 人のユーザーのグループに対して推奨されますが、大規模なグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="35585-127">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="35585-128">ポリシー パッケージを割り当てると、そのポリシーはすぐにグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="35585-128">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="35585-129">ただし、グループのメンバーへのポリシー割り当ての反映はバックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="35585-129">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="35585-130">ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="35585-130">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35585-131">開始する前に、 (優先順位[ルール)](assign-policies-users-and-groups.md#precedence-rules)と ( グループ割り当てランク付け ) を理解[することが重要です](assign-policies-users-and-groups.md#group-assignment-ranking)。</span><span class="sxs-lookup"><span data-stu-id="35585-131">Before you get started, it's important to understand ([precedence rules](assign-policies-users-and-groups.md#precedence-rules)) and ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)).</span></span> <span data-ttu-id="35585-132">この記事の前の「(グループへのポリシー割り当てについて知る必要があるも[の)」](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)の概念を必ず読んで理解してください。</span><span class="sxs-lookup"><span data-stu-id="35585-132">Make sure you read and understand the concepts in ([What you need to know about policy assignment to groups](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="35585-133">管理センターでユーザーのグループにポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="35585-133">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="35585-134">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="35585-134">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="35585-135">左側のナビゲーションで、ポリシー パッケージ ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="35585-135">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="35585-136">グループ ポリシーの割り当て タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="35585-136">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="35585-137">[ **グループの追加]** を選択し、[グループにポリシー パッケージを割り当てる] ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="35585-137">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="35585-138">a.</span><span class="sxs-lookup"><span data-stu-id="35585-138">a.</span></span> <span data-ttu-id="35585-139">ポリシー パッケージを割り当てるグループを検索して追加します。</span><span class="sxs-lookup"><span data-stu-id="35585-139">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="35585-140">b.</span><span class="sxs-lookup"><span data-stu-id="35585-140">b.</span></span> <span data-ttu-id="35585-141">ポリシー パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="35585-141">Select a policy package.</span></span>

    <span data-ttu-id="35585-142">c.</span><span class="sxs-lookup"><span data-stu-id="35585-142">c.</span></span> <span data-ttu-id="35585-143">ポリシーの種類ごとにランク付けを設定します。</span><span class="sxs-lookup"><span data-stu-id="35585-143">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="35585-144">d.</span><span class="sxs-lookup"><span data-stu-id="35585-144">d.</span></span> <span data-ttu-id="35585-145">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35585-145">Select **Apply**.</span></span>

![グループ ポリシーの割り当てを表示する](media/group-pkg-assignment.png)

5. <span data-ttu-id="35585-147">特定のポリシーの種類のランク付けを管理するには、特定のポリシー ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="35585-147">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="35585-148">ポリシー パッケージをグループに再割り当てするには、最初にグループ ポリシーの割り当てを削除します。</span><span class="sxs-lookup"><span data-stu-id="35585-148">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="35585-149">次に、上記の手順に従って、ポリシー パッケージをグループに割り当てします。</span><span class="sxs-lookup"><span data-stu-id="35585-149">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="35585-150">PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="35585-150">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="35585-151">PowerShell モジュールTeams取得する</span><span class="sxs-lookup"><span data-stu-id="35585-151">Get the Teams PowerShell module</span></span>

<span data-ttu-id="35585-152">段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35585-152">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="35585-153">ポリシー パッケージをユーザーのグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="35585-153">Assign a policy package to a group of users</span></span>

<span data-ttu-id="35585-154">[Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment)コマンドレットを使用して、ポリシー パッケージをグループに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="35585-154">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="35585-155">オブジェクト ID、SIP アドレス、または電子メール アドレスを使用して、グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="35585-155">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="35585-156">ポリシー パッケージを割り当てるときに、ポリシー パッケージのポリシーの種類ごとに[(](assign-policies-users-and-groups.md#group-assignment-ranking)グループ割り当てのランク付け ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="35585-156">When you assign the policy package, specify a ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for each policy type in the policy package.</span></span>

<span data-ttu-id="35585-157">この例では、Education_Teacher ポリシー パッケージをグループに割り当て、TeamsAppSetupPolicy と TeamsMeetingBroadcastPolicy には 1 のランク付け、TeamsMeetingPolicy には 2 のランク付けを行います。</span><span class="sxs-lookup"><span data-stu-id="35585-157">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="35585-158">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="35585-158">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="35585-159">バッチ ポリシー パッケージの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシー パッケージを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="35585-159">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="35585-160">[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、割り当てる一群のユーザーおよびポリシー パッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="35585-160">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="35585-161">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="35585-161">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="35585-162">その後、[Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチの割り当ての進捗状況と状態を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="35585-162">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="35585-163">ユーザーをオブジェクト ID またはセッション開始プロトコル (SIP) アドレスで指定します。</span><span class="sxs-lookup"><span data-stu-id="35585-163">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="35585-164">ユーザーの SIP アドレスの値は、多くの場合、ユーザー プリンシパル名 (UPN) またはメール アドレスと同じですが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="35585-164">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="35585-165">ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="35585-165">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="35585-166">バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="35585-166">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="35585-167">バッチには最大 5,000 人のユーザーが含まれる。</span><span class="sxs-lookup"><span data-stu-id="35585-167">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="35585-168">最適な結果を得る場合は、一度に複数のバッチを送信しない。</span><span class="sxs-lookup"><span data-stu-id="35585-168">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="35585-169">さらにバッチを送信する前に、バッチが処理を完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="35585-169">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="35585-170">PowerShell モジュールTeams使用する</span><span class="sxs-lookup"><span data-stu-id="35585-170">Use the Teams PowerShell module</span></span>

<span data-ttu-id="35585-171">以下を実行して、(まだインストールされていない場合は) [Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="35585-171">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="35585-172">バージョン 1.0.5 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="35585-172">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="35585-173">以下を実行して Teams に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="35585-173">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="35585-174">メッセージが表示されたら、管理者の資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="35585-174">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="35585-175">ポリシー パッケージをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="35585-175">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="35585-176">この例では、[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、ユーザーのバッチに Education_PrimaryStudent ポリシー パッケージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="35585-176">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="35585-177">バッチ割り当ての状態を確認する</span><span class="sxs-lookup"><span data-stu-id="35585-177">See the status of a batch assignment</span></span>

<span data-ttu-id="35585-178">以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの ```New-CsBatchPolicyAssignmentOperation``` コマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="35585-178">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="35585-179">エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、```UserState``` プロパティにあるエラーに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="35585-179">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="35585-180">詳細については、[Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35585-180">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="35585-181">関連トピック</span><span class="sxs-lookup"><span data-stu-id="35585-181">Related topics</span></span>

- [<span data-ttu-id="35585-182">ポリシー Teamsを管理する</span><span class="sxs-lookup"><span data-stu-id="35585-182">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="35585-183">アプリケーションでポリシー パッケージを管理Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35585-183">Manage policy packages in Microsoft Teams</span></span>](manage-policy-packages.md)
- [<span data-ttu-id="35585-184">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="35585-184">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="35585-185">グループでポリシーを割りTeams - 使用を開始する</span><span class="sxs-lookup"><span data-stu-id="35585-185">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)