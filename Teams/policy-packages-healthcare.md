---
title: ヘルスケア向けの Teams ポリシー パッケージ
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
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 医療組織用の Teams ポリシー パッケージを使用および管理する方法について説明します。
ms.openlocfilehash: af6f5923d5c97fc03c77585ba94292264aacc027
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812857"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="b20d3-103">ヘルスケア向けの Teams ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="b20d3-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="b20d3-104">概要</span><span class="sxs-lookup"><span data-stu-id="b20d3-104">Overview</span></span>

<span data-ttu-id="b20d3-105">Microsoft Teams の[ポリシー パッケージ](manage-policy-packages.md)は、組織内で類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="b20d3-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="b20d3-106">ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="b20d3-107">ユーザーのニーズに合わせて、パッケージのポリシーの設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="b20d3-108">ポリシー パッケージ内のポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="b20d3-109">Microsoft Teams 管理センターまたは PowerShell を使用して、ポリシー パッケージを管理できます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="b20d3-110">ポリシー パッケージは、以下に対するポリシーを事前に定義しており、内容はパッケージごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="b20d3-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="b20d3-111">メッセージング</span><span class="sxs-lookup"><span data-stu-id="b20d3-111">Messaging</span></span>
- <span data-ttu-id="b20d3-112">会議</span><span class="sxs-lookup"><span data-stu-id="b20d3-112">Meetings</span></span>
- <span data-ttu-id="b20d3-113">通話</span><span class="sxs-lookup"><span data-stu-id="b20d3-113">Calling</span></span>
- <span data-ttu-id="b20d3-114">アプリのセットアップ</span><span class="sxs-lookup"><span data-stu-id="b20d3-114">App setup</span></span>
- <span data-ttu-id="b20d3-115">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="b20d3-115">Live events</span></span>

<span data-ttu-id="b20d3-116">Microsoft Teams には現在、次のヘルスケア ポリシー パッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b20d3-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="b20d3-117">Microsoft Teams 管理センターのパッケージ名</span><span class="sxs-lookup"><span data-stu-id="b20d3-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="b20d3-118">以下の目的での使用に最適です</span><span class="sxs-lookup"><span data-stu-id="b20d3-118">Best used for</span></span>|<span data-ttu-id="b20d3-119">説明</span><span class="sxs-lookup"><span data-stu-id="b20d3-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b20d3-120">医療施設の職員</span><span class="sxs-lookup"><span data-stu-id="b20d3-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="b20d3-121">貴社の医療組織の医療者</span><span class="sxs-lookup"><span data-stu-id="b20d3-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="b20d3-122">一連のポリシーとポリシー設定を作成して、登録済看護師、担当看護師、医師、およびソーシャル ワーカーに対して、チャット、通話、シフト管理、会議へのフル アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="b20d3-123">医療情報提供者</span><span class="sxs-lookup"><span data-stu-id="b20d3-123">Healthcare information worker</span></span>  |<span data-ttu-id="b20d3-124">医療組織の情報提供者</span><span class="sxs-lookup"><span data-stu-id="b20d3-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="b20d3-125">一連のポリシーとポリシー設定を作成して、IT 担当者、情報スタッフ、財務担当者、法令遵守責任者に対して、チャット、通話、会議へのフル アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="b20d3-126">医療患者室</span><span class="sxs-lookup"><span data-stu-id="b20d3-126">Healthcare patient room</span></span>  |<span data-ttu-id="b20d3-127">患者室のデバイス</span><span class="sxs-lookup"><span data-stu-id="b20d3-127">Patient room devices</span></span>|<span data-ttu-id="b20d3-128">貴社の医療組織の患者室に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![ヘルスケア ポリシー パッケージのスクリーンショット](media/policy-packages-healthcare.png)

<span data-ttu-id="b20d3-130">ポリシー パッケージにリンクされているポリシーを容易に識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="b20d3-131">たとえば、医療職員のポリシー パッケージを組織内の臨床医に割り当てると、パッケージ内のポリシーごとに Healthcare_ClinicalWorker という名称のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![医療職員パッケージのポリシーのスクリーンショット](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="b20d3-133">ポリシー パッケージの概要</span><span class="sxs-lookup"><span data-stu-id="b20d3-133">Get started with policy packages</span></span>

<span data-ttu-id="b20d3-134">医療ポリシー パッケージの使用を開始するには、Microsoft 管理センターのオンボーディング ハブで、[**Healthcare**] を選択し、[**役割によってポリシー設定を割り当てる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare**, and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="b20d3-135">開始する準備ができたら、組織内のユーザーに割り当てるポリシー パッケージを決定します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="b20d3-136">パッケージの特定のポリシーの詳細と各設定を確認するには、[**ポリシーの詳細の表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="b20d3-137">Teams 管理センターでの割り当て後にこれらは、[カスタマイズすることができます](manage-policy-packages.md#customize-policies-in-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="b20d3-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="b20d3-138">割り当てるパッケージを 1 つ以上選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b20d3-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="b20d3-139">役割に最適なポリシー パッケージを検索して、ユーザーをそこに追加できます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="b20d3-140">1 人のユーザーを複数のポリシー パッケージに同時に割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="b20d3-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="b20d3-141">適切なポリシー パッケージにユーザーを追加したら、[**完了**] をクリックして、終了します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="b20d3-142">Microsoft Teams 管理センターで引き続きポリシー パッケージをカスタマイズおよび管理できます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="b20d3-143">ポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="b20d3-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="b20d3-144">表示</span><span class="sxs-lookup"><span data-stu-id="b20d3-144">View</span></span>

<span data-ttu-id="b20d3-145">パッケージを割り当てる前に、ポリシー パッケージ内の各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="b20d3-146">Microsoft Teams 管理センターの左側のナビゲーションで、[**ポリシーパッケージ**] に移動して、パッケージ名を選択して、ポリシー名を選択します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="b20d3-147">事前に定義された値が組織に適しているかどうか、または組織のニーズに基づいてより厳しくあるいは緩めにユーザーをカスタマイズする必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="b20d3-148">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="b20d3-148">Customize</span></span>

<span data-ttu-id="b20d3-149">組織のニーズに合わせてポリシー パッケージのポリシーの設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="b20d3-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="b20d3-150">ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="b20d3-151">ポリシー パッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターの左側のナビゲーションで、[**ポリシー パッケージ**] に移動して、編集するポリシーの名前を選択した後、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="b20d3-152">ポリシー パッケージを割り当てると、パッケージ内のポリシーの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="b20d3-153">詳細については、[「ポリシー パッケージのポリシーをカスタマイズする」](manage-policy-packages.md#customize-policies-in-a-policy-package)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20d3-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="b20d3-154">割り当て</span><span class="sxs-lookup"><span data-stu-id="b20d3-154">Assign</span></span>

<span data-ttu-id="b20d3-155">ユーザーにポリシー パッケージを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="b20d3-155">Assign the policy package to users.</span></span> <span data-ttu-id="b20d3-156">ユーザーにポリシーが割り当てられている場合は、別のポリシーを割り当てると、最新の割り当てが優先されます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-156">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="b20d3-157">1 人または複数のユーザーにポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b20d3-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="b20d3-158">1 人または複数のユーザーにポリシー パッケージを割り当てるには、Microsoft Teams 管理センターの左側のナビゲーションから、[**ポリシー パッケージ**] に移動し、[**ユーザーの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![管理センターでポリシー パッケージを割り当てる方法のスクリーンショット](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="b20d3-160">詳細については、[「ポリシー パッケージを割り当てる」](manage-policy-packages.md#assign-a-policy-package)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20d3-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="b20d3-161">ユーザーにポリシーが割り当てられている場合は、別のポリシーを割り当てると、最新の割り当てが優先されます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="b20d3-162">ポリシー パッケージをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="b20d3-162">Assign a policy package to a group</span></span>

<span data-ttu-id="b20d3-163">**この機能はプライベート プレビューです**</span><span class="sxs-lookup"><span data-stu-id="b20d3-163">**This feature is in private preview**</span></span>

<span data-ttu-id="b20d3-164">グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="b20d3-165">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="b20d3-166">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="b20d3-167">この方法は、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="b20d3-168">詳細については、[「グループにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-group)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20d3-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="b20d3-169">ポリシー パッケージを多数 (一群) のユーザー セットに割り当てる</span><span class="sxs-lookup"><span data-stu-id="b20d3-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="b20d3-170">バッチ ポリシーパッケージの割り当てを使用して、多数のユーザー セットに同時にポリシーパッケージを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="b20d3-171">[New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) コマンドレットを使用して、割り当てたい一群のユーザーおよびポリシー パッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="b20d3-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="b20d3-172">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="b20d3-173">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="b20d3-174">ユーザーをオブジェクト ID、UPN、SIP アドレス、またはメール アドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="b20d3-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="b20d3-175">詳細については、[「一群のユーザーにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20d3-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b20d3-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="b20d3-176">Related topics</span></span>

[<span data-ttu-id="b20d3-177">Teams でポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="b20d3-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="b20d3-178"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b20d3-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
