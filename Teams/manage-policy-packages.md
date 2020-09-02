---
title: Microsoft Teams でポリシーパッケージを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でポリシーパッケージを使用して管理する方法について説明します。ユーザーグループのポリシーを管理するときの一貫性を向上させるために、さまざまな方法で管理することができます。
ms.openlocfilehash: 01f32f1141ce46aa45073571ccfaabc8646fc215
ms.sourcegitcommit: 19662d4bc4070f6031084d93e8794e0e02decd2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "47327259"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="63e75-103">Microsoft Teams でポリシーパッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="63e75-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="63e75-104">Microsoft Teams のポリシーパッケージは、組織内で同様の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="63e75-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="63e75-105">組織全体のユーザーグループのポリシーを管理する際の一貫性を高めるために、ポリシーパッケージを作成しました。</span><span class="sxs-lookup"><span data-stu-id="63e75-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="63e75-106">ポリシーパッケージをユーザーに割り当てると、パッケージ内のポリシーが作成され、組織のニーズに合わせてパッケージ内のポリシーの設定をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="63e75-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="63e75-107">ポリシーパッケージとは</span><span class="sxs-lookup"><span data-stu-id="63e75-107">What is a policy package</span></span>

<span data-ttu-id="63e75-108">ポリシーパッケージを使用すると、組織内の特定のユーザーのセットに対して許可または制限するチームの機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="63e75-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="63e75-109">Teams の各ポリシーパッケージは、ユーザーロールをベースに設計されており、その役割で一般的なコラボレーションと通信のアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="63e75-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="63e75-110">チームには現在、次のポリシーパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="63e75-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="63e75-111">**パッケージ名**</span><span class="sxs-lookup"><span data-stu-id="63e75-111">**Package name**</span></span>  |<span data-ttu-id="63e75-112">**説明**</span><span class="sxs-lookup"><span data-stu-id="63e75-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="63e75-113">教育機関 (高等教育機関向け生徒)</span><span class="sxs-lookup"><span data-stu-id="63e75-113">Education (Higher education student)</span></span>    |<span data-ttu-id="63e75-114">高等教育機関向けの学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="63e75-114">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="63e75-115">教育機関 (第1学校の学生)</span><span class="sxs-lookup"><span data-stu-id="63e75-115">Education (Primary school student)</span></span>   |<span data-ttu-id="63e75-116">主要な学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="63e75-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="63e75-117">教育機関 (第2学校の学生)</span><span class="sxs-lookup"><span data-stu-id="63e75-117">Education (Secondary school student)</span></span>    |<span data-ttu-id="63e75-118">第2の学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="63e75-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="63e75-119">教育機関 (教師)</span><span class="sxs-lookup"><span data-stu-id="63e75-119">Education (Teacher)</span></span>    |<span data-ttu-id="63e75-120">教師に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="63e75-120">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="63e75-121">学歴 (リモート学習を使用した第1学校教師)</span><span class="sxs-lookup"><span data-stu-id="63e75-121">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="63e75-122">小学校教師に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="63e75-122">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="63e75-123">教育機関 (リモート学習を使った第1学校の学生)</span><span class="sxs-lookup"><span data-stu-id="63e75-123">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="63e75-124">小学生に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="63e75-124">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="63e75-125">Firstline manager</span><span class="sxs-lookup"><span data-stu-id="63e75-125">Firstline manager</span></span> |<span data-ttu-id="63e75-126">一連のポリシーを作成し、組織の Firstline Manager にそれらの設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="63e75-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span> |
|<span data-ttu-id="63e75-127">Firstline worker</span><span class="sxs-lookup"><span data-stu-id="63e75-127">Firstline worker</span></span> |<span data-ttu-id="63e75-128">一連のポリシーを作成し、それらの設定を組織の Firstline Worker に適用します。</span><span class="sxs-lookup"><span data-stu-id="63e75-128">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span> |
|<span data-ttu-id="63e75-129">医療診療員</span><span class="sxs-lookup"><span data-stu-id="63e75-129">Healthcare clinical worker</span></span>  |<span data-ttu-id="63e75-130">登録された看護師、料金の看護師、医師、ソーシャルワーカーなどの、チャット、通話、シフト管理、および会議へのフルアクセスを可能にする、一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="63e75-130">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="63e75-131">医療情報の作業者</span><span class="sxs-lookup"><span data-stu-id="63e75-131">Healthcare information worker</span></span>  |<span data-ttu-id="63e75-132">IT 担当者、informatics 職員、財務担当者、コンプライアンス責任者、チャット、通話、会議へのフルアクセスなどの情報を提供する一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="63e75-132">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="63e75-133">医療の治療室</span><span class="sxs-lookup"><span data-stu-id="63e75-133">Healthcare patient room</span></span>  |<span data-ttu-id="63e75-134">医療機関の患者の会議室に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="63e75-134">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="63e75-135">中小規模企業のユーザー (ビジネス用ボイス)</span><span class="sxs-lookup"><span data-stu-id="63e75-135">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="63e75-136">ビジネス音声エクスペリエンス用のアプリを含むアプリセットアップポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="63e75-136">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="63e75-137">中小規模企業のユーザー (ビジネス用ボイスのない)</span><span class="sxs-lookup"><span data-stu-id="63e75-137">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="63e75-138">中小規模のビジネスチームユーザー (非ビジネス用ボイス) に関連するアプリのセットアップポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="63e75-138">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="63e75-139">公安責任者</span><span class="sxs-lookup"><span data-stu-id="63e75-139">Public safety officer</span></span>   |<span data-ttu-id="63e75-140">組織の公衆安全責任者に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="63e75-140">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="63e75-141">今後のチームのリリースでポリシーパッケージを追加しますので、最新の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="63e75-141">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="63e75-142">個々のポリシーには、ポリシーパッケージの名前が割り当てられているため、ポリシーパッケージにリンクされているポリシーを簡単に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="63e75-142">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="63e75-143">たとえば、学校の教師に教育 (教師) ポリシーパッケージを割り当てると、Education_Teacher という名前のポリシーがパッケージ内の各ポリシーに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="63e75-143">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育機関 (教師) ポリシーパッケージのスクリーンショット](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="63e75-145">ポリシーパッケージの使用方法</span><span class="sxs-lookup"><span data-stu-id="63e75-145">How to use policy packages</span></span>

<span data-ttu-id="63e75-146">組織でポリシーパッケージを使用する方法については、次の表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63e75-146">The following outlines how to use policy packages in your organization.</span></span>

![ポリシーパッケージの使用方法の概要](media/manage-policy-packages-overview.png)

- <span data-ttu-id="63e75-148">**[表示](#view-the-settings-of-a-policy-in-a-policy-package)**: パッケージを割り当てる前に、ポリシーパッケージ内の各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="63e75-148">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="63e75-149">各設定を理解していることを確認して、組織にとって事前に定義された値が適切かどうかを確認します。また、組織のニーズに基づいて、定義済みの値を変更する必要があるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e75-149">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="63e75-150">ポリシーが削除された場合でも、設定は表示できますが、設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="63e75-150">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="63e75-151">ポリシーパッケージを割り当てるときに、削除されたポリシーが定義済みの設定で再作成されます。</span><span class="sxs-lookup"><span data-stu-id="63e75-151">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="63e75-152">**[割り当て](#assign-a-policy-package)**: ポリシーパッケージをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="63e75-152">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="63e75-153">ポリシーパッケージのポリシーは、パッケージを割り当てるまで作成されないことに注意してください。その後、パッケージ内の個々のポリシーの設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="63e75-153">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="63e75-154">**[カスタマイズ](#customize-policies-in-a-policy-package)**: 組織のニーズに合わせてポリシーパッケージのポリシーの設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="63e75-154">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="63e75-155">ポリシー設定に加えた変更は、パッケージを割り当てられたユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="63e75-155">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="63e75-156">Microsoft Teams 管理センターでポリシーパッケージを表示、割り当て、カスタマイズする方法の手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="63e75-156">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="63e75-157">ポリシーパッケージ内のポリシーの設定を表示する</span><span class="sxs-lookup"><span data-stu-id="63e75-157">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="63e75-158">Microsoft Teams 管理センターの左のナビゲーションで、[ **ポリシーパッケージ**] をクリックし、パッケージ名の左側をクリックしてポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="63e75-158">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="63e75-159">表示するポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e75-159">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="63e75-160">ポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="63e75-160">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="63e75-161">1人のユーザーにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="63e75-161">Assign a policy package to one user</span></span>

1. <span data-ttu-id="63e75-162">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e75-162">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="63e75-163">ユーザーのページで、[ **ポリシー**] をクリックし、[ **ポリシーパッケージ**] の横にある [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e75-163">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="63e75-164">[ **ポリシーパッケージの割り当て** ] ウィンドウで、割り当てるパッケージを選択し、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e75-164">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="63e75-165">ポリシーパッケージを複数のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="63e75-165">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="63e75-166">Microsoft Teams 管理センターの左のナビゲーションで、[ **ポリシーパッケージ**] に移動し、パッケージ名の左側をクリックして割り当てるポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="63e75-166">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="63e75-167">[ **ユーザーの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e75-167">Click **Manage users**.</span></span>
3. <span data-ttu-id="63e75-168">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e75-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="63e75-169">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="63e75-169">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="63e75-170">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e75-170">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="63e75-171">ポリシーパッケージを大規模なユーザー (バッチ) に割り当てる</span><span class="sxs-lookup"><span data-stu-id="63e75-171">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="63e75-172">バッチポリシーパッケージの割り当てを使用して、一度に多くのユーザーにポリシーパッケージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="63e75-172">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="63e75-173">[CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation)コマンドレットを使用して、ユーザーのバッチと、割り当てるポリシーパッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="63e75-173">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="63e75-174">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="63e75-174">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="63e75-175">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="63e75-175">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="63e75-176">ユーザーは、オブジェクト Id、UPN、SIP アドレス、またはメールアドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="63e75-176">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="63e75-177">詳細については、「 [ユーザーのバッチにポリシーパッケージを割り当てる](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63e75-177">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="63e75-178">ポリシーパッケージのポリシーをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="63e75-178">Customize policies in a policy package</span></span>

<span data-ttu-id="63e75-179">ポリシーの設定を編集するには、[ **ポリシーパッケージ** ] ページを使用するか、Microsoft Teams 管理センターの [ポリシー] ページに直接移動します。</span><span class="sxs-lookup"><span data-stu-id="63e75-179">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="63e75-180">Microsoft Teams 管理センターの左側のナビゲーションで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="63e75-180">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="63e75-181">[ **ポリシーパッケージ**] をクリックし、パッケージ名の左側をクリックしてポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="63e75-181">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="63e75-182">[ポリシーの種類] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e75-182">Click the policy type.</span></span>  <span data-ttu-id="63e75-183">たとえば、[ **メッセージングポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e75-183">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="63e75-184">編集するポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e75-184">Click the policy you want to edit.</span></span> <span data-ttu-id="63e75-185">ポリシーパッケージにリンクされているポリシーは、ポリシーパッケージと同じ名前になっています。</span><span class="sxs-lookup"><span data-stu-id="63e75-185">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="63e75-186">必要な変更を加えて、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e75-186">Make the changes that you want, and then click **Save**.</span></span>

## <a name="supported-policy-types"></a><span data-ttu-id="63e75-187">サポートされているポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="63e75-187">Supported policy types</span></span>

- <span data-ttu-id="63e75-188">Messaging</span><span class="sxs-lookup"><span data-stu-id="63e75-188">Messaging</span></span>
- <span data-ttu-id="63e75-189">会議</span><span class="sxs-lookup"><span data-stu-id="63e75-189">Meetings</span></span>
- <span data-ttu-id="63e75-190">通話</span><span class="sxs-lookup"><span data-stu-id="63e75-190">Calling</span></span>
- <span data-ttu-id="63e75-191">アプリのセットアップ</span><span class="sxs-lookup"><span data-stu-id="63e75-191">App setup</span></span>
- <span data-ttu-id="63e75-192">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="63e75-192">Live events</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="63e75-193">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="63e75-193">Troubleshooting</span></span>

<span data-ttu-id="63e75-194">**ポリシーパッケージを割り当てるときにエラーが表示される**</span><span class="sxs-lookup"><span data-stu-id="63e75-194">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="63e75-195">この問題は、パッケージ内の1つ以上のポリシーが正常に作成または適用されなかった場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="63e75-195">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="63e75-196">ポリシーパッケージをユーザーに割り当て直します。</span><span class="sxs-lookup"><span data-stu-id="63e75-196">Reassign the policy package to your users.</span></span> <span data-ttu-id="63e75-197">通常、操作を再試行すると、この問題は修正されます。</span><span class="sxs-lookup"><span data-stu-id="63e75-197">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="63e75-198">関連トピック</span><span class="sxs-lookup"><span data-stu-id="63e75-198">Related topics</span></span>

[<span data-ttu-id="63e75-199">EDU 管理者向けの Microsoft Teams ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="63e75-199">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
