---
title: 政府機関向け Teams ポリシー パッケージ
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 政府機関向け Teams ポリシー パッケージを使用して管理する方法について学習します。
ms.openlocfilehash: 2841fbf523f49c5784045cc6cf960e846b45aa9b
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909081"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="3d18e-103">政府機関向け Teams ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="3d18e-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="3d18e-104">現在、ポリシー パッケージは Microsoft 365 Government GCC High または DoD 展開では利用できません。</span><span class="sxs-lookup"><span data-stu-id="3d18e-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="3d18e-105">概要</span><span class="sxs-lookup"><span data-stu-id="3d18e-105">Overview</span></span>

<span data-ttu-id="3d18e-106">Microsoft Teams [の](manage-policy-packages.md) ポリシー パッケージは、組織内で同様の役割を持つユーザーに割り当て可能な定義済みのポリシーとポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="3d18e-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="3d18e-107">ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="3d18e-108">ユーザーのニーズに合わせて、パッケージ内のポリシーの設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="3d18e-109">ポリシー パッケージのポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーに更新された設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="3d18e-110">Microsoft Teams 管理センターまたは PowerShell を使用して、ポリシー パッケージを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="3d18e-111">ポリシー パッケージは、パッケージに応じて、次のポリシーを事前に定義します。</span><span class="sxs-lookup"><span data-stu-id="3d18e-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="3d18e-112">Messaging</span><span class="sxs-lookup"><span data-stu-id="3d18e-112">Messaging</span></span>
- <span data-ttu-id="3d18e-113">会議</span><span class="sxs-lookup"><span data-stu-id="3d18e-113">Meetings</span></span>
- <span data-ttu-id="3d18e-114">通話</span><span class="sxs-lookup"><span data-stu-id="3d18e-114">Calling</span></span>
- <span data-ttu-id="3d18e-115">アプリのセットアップ</span><span class="sxs-lookup"><span data-stu-id="3d18e-115">App setup</span></span>
- <span data-ttu-id="3d18e-116">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="3d18e-116">Live events</span></span>

<span data-ttu-id="3d18e-117">Teams には現在、政府機関向け次のポリシー パッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d18e-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="3d18e-118">Microsoft Teams 管理センターのパッケージ名</span><span class="sxs-lookup"><span data-stu-id="3d18e-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="3d18e-119">以下の目的での使用に最適です</span><span class="sxs-lookup"><span data-stu-id="3d18e-119">Best used for</span></span>|<span data-ttu-id="3d18e-120">説明</span><span class="sxs-lookup"><span data-stu-id="3d18e-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3d18e-121">公安責任者</span><span class="sxs-lookup"><span data-stu-id="3d18e-121">Public safety officer</span></span>  |<span data-ttu-id="3d18e-122">政府機関の公安責任者</span><span class="sxs-lookup"><span data-stu-id="3d18e-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="3d18e-123">組織の公安責任者に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="3d18e-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="3d18e-124">Frontline Manager</span><span class="sxs-lookup"><span data-stu-id="3d18e-124">Frontline manager</span></span>  |<span data-ttu-id="3d18e-125">政府機関のフロントライン マネージャー</span><span class="sxs-lookup"><span data-stu-id="3d18e-125">Frontline Managers in your government organization</span></span> |<span data-ttu-id="3d18e-126">一連のポリシーを作成し、それらの設定を組織内の Frontline Managers に適用します。</span><span class="sxs-lookup"><span data-stu-id="3d18e-126">Creates a set of policies and applies those settings to Frontline Managers in your organization.</span></span>|
|<span data-ttu-id="3d18e-127">最前線の従業員</span><span class="sxs-lookup"><span data-stu-id="3d18e-127">Frontline worker</span></span>  |<span data-ttu-id="3d18e-128">政府機関の最前線の従業員</span><span class="sxs-lookup"><span data-stu-id="3d18e-128">Frontline Workers in your government organization</span></span> |<span data-ttu-id="3d18e-129">一連のポリシーを作成し、それらの設定を組織内の Frontline Worker に適用します。</span><span class="sxs-lookup"><span data-stu-id="3d18e-129">Creates a set of policies and applies those settings to Frontline Workers in your organization.</span></span>|

![医療ポリシー パッケージのスクリーンショット](media/policy-packages-gov.png)

<span data-ttu-id="3d18e-131">ポリシー パッケージにリンクされているポリシーを簡単に識別できるよう、個々のポリシーにはポリシー パッケージの名前が付けされます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="3d18e-132">たとえば、パブリック セーフティ責任者のポリシー パッケージを組織内のユーザーに割り当てると、パッケージ内のポリシーごとに PublicSafety_Officer という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![医療クリニカル ワーカー パッケージのポリシーのスクリーンショット](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="3d18e-134">ポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="3d18e-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="3d18e-135">表示</span><span class="sxs-lookup"><span data-stu-id="3d18e-135">View</span></span>

<span data-ttu-id="3d18e-136">パッケージを割り当てる前に、ポリシー パッケージ内の各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="3d18e-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="3d18e-137">Microsoft Teams 管理センターの左側のナビゲーションで、[**ポリシーパッケージ**] を選択し、パッケージ名を選択して、ポリシー名を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d18e-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="3d18e-138">事前に定義された値が組織に適しているかどうか、または組織のニーズに基づいてより厳しくあるいは緩めにユーザーをカスタマイズする必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="3d18e-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="3d18e-139">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="3d18e-139">Customize</span></span>

<span data-ttu-id="3d18e-140">組織のニーズに合わせてポリシー パッケージのポリシーの設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="3d18e-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="3d18e-141">ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="3d18e-142">ポリシー パッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターでポリシー パッケージを選び、編集するポリシーの名前を選択して、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d18e-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="3d18e-143">ポリシー パッケージを割り当てると、パッケージ内のポリシーの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="3d18e-144">詳細については、[「ポリシー パッケージのポリシーをカスタマイズする」](manage-policy-packages.md#customize-policies-in-a-policy-package)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d18e-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="3d18e-145">割り当て</span><span class="sxs-lookup"><span data-stu-id="3d18e-145">Assign</span></span>

<span data-ttu-id="3d18e-146">ユーザーにポリシー パッケージを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="3d18e-146">Assign the policy package to users.</span></span> <span data-ttu-id="3d18e-147">ユーザーにポリシーが割り当てられている場合は、別のポリシーを割り当てると、最新の割り当てが優先されます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="3d18e-148">1 人または複数のユーザーにポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3d18e-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="3d18e-149">1 人または複数のユーザーにポリシー パッケージを割り当てるには、Microsoft Teams 管理センターの左側のナビゲーションから、[**ポリシー パッケージ**] に移動し、[**ユーザーの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d18e-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![管理センターでポリシー パッケージを割り当てる方法のスクリーンショット](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="3d18e-151">詳細については、[「ポリシー パッケージを割り当てる」](manage-policy-packages.md#assign-a-policy-package)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d18e-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="3d18e-152">ユーザーにポリシーが割り当てられている場合は、別のポリシーを割り当てると、最新の割り当てが優先されます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="3d18e-153">ポリシー パッケージをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3d18e-153">Assign a policy package to a group</span></span>

<span data-ttu-id="3d18e-154">**この機能はプライベート プレビューです**</span><span class="sxs-lookup"><span data-stu-id="3d18e-154">**This feature is in private preview**</span></span>

<span data-ttu-id="3d18e-155">グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="3d18e-156">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="3d18e-157">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="3d18e-158">この方法は、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="3d18e-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="3d18e-159">詳細については、[「グループにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-group)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d18e-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="3d18e-160">ポリシー パッケージを多数 (一群) のユーザー セットに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3d18e-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="3d18e-161">バッチ ポリシーパッケージの割り当てを使用して、多数のユーザー セットに同時にポリシーパッケージを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="3d18e-162">[New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) コマンドレットを使用して、割り当てたい一群のユーザーおよびポリシー パッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3d18e-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="3d18e-163">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="3d18e-164">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="3d18e-165">ユーザーをオブジェクト ID、UPN、SIP アドレス、またはメール アドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="3d18e-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="3d18e-166">詳細については、[「一群のユーザーにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d18e-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3d18e-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d18e-167">Related topics</span></span>

[<span data-ttu-id="3d18e-168">Teams でポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="3d18e-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="3d18e-169"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3d18e-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
