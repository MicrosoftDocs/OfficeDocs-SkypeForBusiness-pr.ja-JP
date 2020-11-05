---
title: 医療用の Teams ポリシーパッケージ
author: lanachin
ms.author: v-lanac
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
description: 医療組織の Teams ポリシーパッケージを使用および管理する方法について説明します。
ms.openlocfilehash: b8317a7f860d0ab8510a6170b69a50f7a3387ebd
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908516"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="3674b-103">医療用の Teams ポリシーパッケージ</span><span class="sxs-lookup"><span data-stu-id="3674b-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="3674b-104">概要</span><span class="sxs-lookup"><span data-stu-id="3674b-104">Overview</span></span>

<span data-ttu-id="3674b-105">Microsoft Teams の [ポリシーパッケージ](manage-policy-packages.md) は、組織内で同様の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="3674b-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="3674b-106">ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="3674b-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="3674b-107">パッケージ内のポリシーの設定をカスタマイズして、ユーザーのニーズに合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="3674b-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="3674b-108">ポリシーパッケージのポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="3674b-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="3674b-109">ポリシーパッケージを管理するには、Microsoft Teams 管理センターまたは PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="3674b-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="3674b-110">ポリシーパッケージでは、パッケージに応じて、次のポリシーが事前に定義されています。</span><span class="sxs-lookup"><span data-stu-id="3674b-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="3674b-111">Messaging</span><span class="sxs-lookup"><span data-stu-id="3674b-111">Messaging</span></span>
- <span data-ttu-id="3674b-112">会議</span><span class="sxs-lookup"><span data-stu-id="3674b-112">Meetings</span></span>
- <span data-ttu-id="3674b-113">通話</span><span class="sxs-lookup"><span data-stu-id="3674b-113">Calling</span></span>
- <span data-ttu-id="3674b-114">アプリのセットアップ</span><span class="sxs-lookup"><span data-stu-id="3674b-114">App setup</span></span>
- <span data-ttu-id="3674b-115">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="3674b-115">Live events</span></span>

<span data-ttu-id="3674b-116">Teams には現在、以下の医療ポリシーパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3674b-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="3674b-117">Microsoft Teams 管理センターのパッケージ名</span><span class="sxs-lookup"><span data-stu-id="3674b-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="3674b-118">以下の目的での使用に最適です</span><span class="sxs-lookup"><span data-stu-id="3674b-118">Best used for</span></span>|<span data-ttu-id="3674b-119">説明</span><span class="sxs-lookup"><span data-stu-id="3674b-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3674b-120">医療診療員</span><span class="sxs-lookup"><span data-stu-id="3674b-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="3674b-121">医療機関向けの臨床従業員</span><span class="sxs-lookup"><span data-stu-id="3674b-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="3674b-122">登録された看護師、料金の看護師、医師、ソーシャルワーカーなどの、チャット、通話、シフト管理、および会議へのフルアクセスを可能にする、一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="3674b-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="3674b-123">医療情報の作業者</span><span class="sxs-lookup"><span data-stu-id="3674b-123">Healthcare information worker</span></span>  |<span data-ttu-id="3674b-124">医療機関のインフォメーションワーカー</span><span class="sxs-lookup"><span data-stu-id="3674b-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="3674b-125">IT 担当者、informatics 職員、財務担当者、コンプライアンス責任者、チャット、通話、会議へのフルアクセスなどの情報を提供する一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="3674b-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="3674b-126">医療の治療室</span><span class="sxs-lookup"><span data-stu-id="3674b-126">Healthcare patient room</span></span>  |<span data-ttu-id="3674b-127">患者室のデバイス</span><span class="sxs-lookup"><span data-stu-id="3674b-127">Patient room devices</span></span>|<span data-ttu-id="3674b-128">医療機関の患者の会議室に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="3674b-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![ヘルスケアポリシーパッケージのスクリーンショット](media/policy-packages-healthcare.png)

<span data-ttu-id="3674b-130">個々のポリシーには、ポリシーパッケージの名前が割り当てられているため、ポリシーパッケージにリンクされているポリシーを簡単に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="3674b-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="3674b-131">たとえば、医療臨床 worker ポリシーパッケージを組織内の clinicians に割り当てると、パッケージ内のポリシーごとに Healthcare_ClinicalWorker という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3674b-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![医療用臨床 worker パッケージのポリシーのスクリーンショット](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="3674b-133">ポリシーパッケージの概要</span><span class="sxs-lookup"><span data-stu-id="3674b-133">Get started with policy packages</span></span>

<span data-ttu-id="3674b-134">医療ポリシーパッケージの概要については、Microsoft 管理センターのオンボードハブで、[ **医療** ] を選んでから、[ **役割別にポリシー設定を割り当てる** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3674b-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare** , and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="3674b-135">作業を開始する準備ができたら、組織内の個人を割り当てるポリシーパッケージを決定します。</span><span class="sxs-lookup"><span data-stu-id="3674b-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="3674b-136">[ **ポリシーの詳細の表示** ] を選択して、パッケージ内の特定のポリシーとその設定を詳しく確認します。</span><span class="sxs-lookup"><span data-stu-id="3674b-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="3674b-137">これらは、Teams 管理センターで割り当て後に [カスタマイズすることができ](manage-policy-packages.md#customize-policies-in-a-policy-package) ます。</span><span class="sxs-lookup"><span data-stu-id="3674b-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="3674b-138">割り当てるパッケージを1つまたは複数選択して、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3674b-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="3674b-139">ポリシーパッケージにユーザーを検索して追加することで、その役割に最適です。</span><span class="sxs-lookup"><span data-stu-id="3674b-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="3674b-140">1人のユーザーを一度に複数のポリシーパッケージに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="3674b-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="3674b-141">適切なポリシーパッケージにユーザーを追加したら、 **[完了** ] で選択内容が終了します。</span><span class="sxs-lookup"><span data-stu-id="3674b-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="3674b-142">引き続き、Microsoft Teams 管理センターでポリシーパッケージのカスタマイズと管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3674b-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="3674b-143">ポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="3674b-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="3674b-144">表示</span><span class="sxs-lookup"><span data-stu-id="3674b-144">View</span></span>

<span data-ttu-id="3674b-145">パッケージを割り当てる前に、ポリシーパッケージの各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="3674b-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="3674b-146">Microsoft Teams 管理センターの左のナビゲーションで、[ **ポリシーパッケージ** ] に移動し、パッケージ名を選択して、ポリシー名を選びます。</span><span class="sxs-lookup"><span data-stu-id="3674b-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="3674b-147">定義済みの値が組織に適しているかどうかを判断します。または、組織のニーズに基づいて、ユーザー設定の値をカスタマイズする必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3674b-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="3674b-148">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="3674b-148">Customize</span></span>

<span data-ttu-id="3674b-149">組織のニーズに合わせて、ポリシーパッケージのポリシーの設定を必要に応じてカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="3674b-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="3674b-150">ポリシー設定に加えた変更は、パッケージを割り当てられたユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3674b-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="3674b-151">ポリシーパッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターの左側のナビゲーションで [ **ポリシー** パッケージ] に移動し、ポリシーパッケージを選び、編集するポリシーの名前を選んで、[ **編集** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3674b-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="3674b-152">ポリシーパッケージを割り当てると、パッケージのポリシーの設定を変更できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3674b-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="3674b-153">詳細については、「 [ポリシーパッケージの](manage-policy-packages.md#customize-policies-in-a-policy-package)ポリシーをカスタマイズする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3674b-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="3674b-154">割り当てる</span><span class="sxs-lookup"><span data-stu-id="3674b-154">Assign</span></span>

<span data-ttu-id="3674b-155">ポリシーパッケージをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3674b-155">Assign the policy package to users.</span></span> <span data-ttu-id="3674b-156">ユーザーにポリシーが割り当てられていて、後で別のポリシーを割り当てると、最新の割り当てが優先されます。</span><span class="sxs-lookup"><span data-stu-id="3674b-156">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="3674b-157">1人または複数のユーザーにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3674b-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="3674b-158">ポリシーパッケージを1人または複数のユーザーに割り当てるには、Microsoft Teams 管理センターの左側のナビゲーションで [ **ポリシーパッケージ** ] に移動し、[ **ユーザーの管理** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3674b-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![管理センターでポリシーパッケージを割り当てる方法のスクリーンショット](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="3674b-160">詳細については、「 [ポリシーパッケージを割り当てる](manage-policy-packages.md#assign-a-policy-package)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3674b-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="3674b-161">ユーザーにポリシーが割り当てられていて、後で別のポリシーを割り当てると、最新の割り当てが優先されます。</span><span class="sxs-lookup"><span data-stu-id="3674b-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="3674b-162">ポリシーパッケージをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3674b-162">Assign a policy package to a group</span></span>

<span data-ttu-id="3674b-163">**この機能はプライベートプレビュー**</span><span class="sxs-lookup"><span data-stu-id="3674b-163">**This feature is in private preview**</span></span>

<span data-ttu-id="3674b-164">グループにポリシーパッケージを割り当てると、セキュリティグループや配布リストなど、複数のポリシーをユーザーのグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3674b-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="3674b-165">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="3674b-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="3674b-166">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="3674b-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="3674b-167">この方法は、最大5万ユーザーのグループに推奨されますが、大規模なグループでも動作します。</span><span class="sxs-lookup"><span data-stu-id="3674b-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="3674b-168">詳細については、「 [ポリシーパッケージをグループに割り当てる](assign-policies.md#assign-a-policy-package-to-a-group)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3674b-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="3674b-169">ポリシーパッケージを大規模なユーザー (バッチ) に割り当てる</span><span class="sxs-lookup"><span data-stu-id="3674b-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="3674b-170">バッチポリシーパッケージの割り当てを使用して、一度に多くのユーザーにポリシーパッケージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3674b-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="3674b-171">[CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation)コマンドレットを使用して、ユーザーのバッチと、割り当てるポリシーパッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3674b-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="3674b-172">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3674b-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="3674b-173">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3674b-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="3674b-174">ユーザーは、オブジェクト Id、UPN、SIP アドレス、またはメールアドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="3674b-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="3674b-175">詳細については、「 [ユーザーのバッチにポリシーパッケージを割り当てる](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3674b-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3674b-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="3674b-176">Related topics</span></span>

[<span data-ttu-id="3674b-177">Teams でポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="3674b-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="3674b-178">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3674b-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
