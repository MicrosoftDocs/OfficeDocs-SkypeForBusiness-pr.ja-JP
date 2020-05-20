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
ms.openlocfilehash: 6927e2efae60370c0622f38570fc961794734f35
ms.sourcegitcommit: e0ed3b6478918c4737648e6c27eb01de0b622b0e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322292"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="370b7-103">Microsoft Teams でポリシーパッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="370b7-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="370b7-104">Microsoft Teams のポリシーパッケージは、組織内で同様の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="370b7-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="370b7-105">組織全体のユーザーグループのポリシーを管理する際の一貫性を高めるために、ポリシーパッケージを作成しました。</span><span class="sxs-lookup"><span data-stu-id="370b7-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="370b7-106">ポリシーパッケージをユーザーに割り当てると、パッケージ内のポリシーが作成され、組織のニーズに合わせてパッケージ内のポリシーの設定をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="370b7-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

<span data-ttu-id="370b7-107">ポリシーパッケージは、米国政府機関向けクラウドコミュニティ (GCC) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="370b7-107">Policy packages aren't available for US Government Cloud Community (GCC) organizations.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="370b7-108">ポリシーパッケージとは</span><span class="sxs-lookup"><span data-stu-id="370b7-108">What is a policy package?</span></span>

<span data-ttu-id="370b7-109">ポリシーパッケージを使用すると、組織内の特定のユーザーのセットに対して許可または制限するチームの機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="370b7-109">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="370b7-110">Teams の各ポリシーパッケージは、ユーザーロールをベースに設計されており、その役割で一般的なコラボレーションと通信のアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="370b7-110">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="370b7-111">チームには現在、次のポリシーパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="370b7-111">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="370b7-112">**パッケージ名**</span><span class="sxs-lookup"><span data-stu-id="370b7-112">**Package name**</span></span>  |<span data-ttu-id="370b7-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="370b7-113">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="370b7-114">教育機関 (高等教育機関向け生徒)</span><span class="sxs-lookup"><span data-stu-id="370b7-114">Education (Higher education student)</span></span>    |<span data-ttu-id="370b7-115">高等教育機関向けの学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="370b7-115">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="370b7-116">教育機関 (第1学校の学生)</span><span class="sxs-lookup"><span data-stu-id="370b7-116">Education (Primary school student)</span></span>   |<span data-ttu-id="370b7-117">主要な学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="370b7-117">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="370b7-118">教育機関 (第2学校の学生)</span><span class="sxs-lookup"><span data-stu-id="370b7-118">Education (Secondary school student)</span></span>    |<span data-ttu-id="370b7-119">第2の学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="370b7-119">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="370b7-120">教育機関 (教師)</span><span class="sxs-lookup"><span data-stu-id="370b7-120">Education (Teacher)</span></span>    |<span data-ttu-id="370b7-121">教師に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="370b7-121">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="370b7-122">学歴 (リモート学習を使用したプライマリ学校教師) (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="370b7-122">Education (Primary school teacher using remote learning) (Preview)</span></span>   |<span data-ttu-id="370b7-123">リモート学習を使用するときに、学生の安全性と共同作業を最大限に活用するために、プライマリ教師に適用する一連のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="370b7-123">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="370b7-124">学歴 (リモート学習を使用した第1の学校学生) (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="370b7-124">Education (Primary school student using remote learning) (Preview)</span></span>    |<span data-ttu-id="370b7-125">リモート学習を使用するときに、学生の安全性と共同作業を最大限に活用するために、主要な学生に適用される一連のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="370b7-125">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="370b7-126">医療診療員</span><span class="sxs-lookup"><span data-stu-id="370b7-126">Healthcare clinical worker</span></span>  |<span data-ttu-id="370b7-127">登録された看護師、料金の看護師、医師、ソーシャルワーカーなどの、チャット、通話、シフト管理、および会議へのフルアクセスを可能にする、一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="370b7-127">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="370b7-128">医療情報の作業者</span><span class="sxs-lookup"><span data-stu-id="370b7-128">Healthcare information worker</span></span>  |<span data-ttu-id="370b7-129">IT 担当者、informatics 職員、財務担当者、コンプライアンス責任者、チャット、通話、会議へのフルアクセスなどの情報を提供する一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="370b7-129">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="370b7-130">医療の治療室</span><span class="sxs-lookup"><span data-stu-id="370b7-130">Healthcare patient room</span></span>  |<span data-ttu-id="370b7-131">医療機関の患者の会議室に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="370b7-131">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="370b7-132">中小規模企業のユーザー (ビジネス用ボイス)</span><span class="sxs-lookup"><span data-stu-id="370b7-132">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="370b7-133">ビジネス音声エクスペリエンス用のアプリを含むアプリセットアップポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="370b7-133">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="370b7-134">中小規模企業のユーザー (ビジネス用ボイスのない)</span><span class="sxs-lookup"><span data-stu-id="370b7-134">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="370b7-135">ビジネス音声機能を使わずに、中小規模のビジネスユーザーに適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="370b7-135">Creates a set of policies and policy settings that apply to small and medium sized business users without any Business Voice features.</span></span>|
|<span data-ttu-id="370b7-136">公安責任者</span><span class="sxs-lookup"><span data-stu-id="370b7-136">Public safety officer</span></span>   |<span data-ttu-id="370b7-137">組織の公衆安全責任者に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="370b7-137">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|



> [!NOTE]
> <span data-ttu-id="370b7-138">今後のチームのリリースでポリシーパッケージを追加しますので、最新の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="370b7-138">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="370b7-139">個々のポリシーには、ポリシーパッケージの名前が割り当てられているため、ポリシーパッケージにリンクされているポリシーを簡単に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="370b7-139">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="370b7-140">たとえば、学校の教師に教育 (教師) ポリシーパッケージを割り当てると、Education_Teacher という名前のポリシーがパッケージ内の各ポリシーに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="370b7-140">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育機関 (教師) ポリシーパッケージのスクリーンショット](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="370b7-142">ポリシーパッケージの使用方法</span><span class="sxs-lookup"><span data-stu-id="370b7-142">How to use policy packages</span></span>

<span data-ttu-id="370b7-143">組織でポリシーパッケージを使用する方法については、次の表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="370b7-143">The following outlines how to use policy packages in your organization.</span></span>

![ポリシーパッケージの使用方法の概要](media/manage-policy-packages-overview.png)

- <span data-ttu-id="370b7-145">**[表示](#view-the-settings-of-a-policy-in-a-policy-package)**: パッケージを割り当てる前に、ポリシーパッケージ内の各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="370b7-145">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="370b7-146">各設定を理解していることを確認して、組織にとって事前に定義された値が適切かどうかを確認します。また、組織のニーズに基づいて、定義済みの値を変更する必要があるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="370b7-146">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="370b7-147">ポリシーが削除された場合でも、設定は表示できますが、設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="370b7-147">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="370b7-148">ポリシーパッケージを割り当てるときに、削除されたポリシーが定義済みの設定で再作成されます。</span><span class="sxs-lookup"><span data-stu-id="370b7-148">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="370b7-149">**[割り当て](#assign-a-policy-package)**: ポリシーパッケージをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="370b7-149">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="370b7-150">ポリシーパッケージのポリシーは、パッケージを割り当てるまで作成されないことに注意してください。その後、パッケージ内の個々のポリシーの設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="370b7-150">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="370b7-151">**[カスタマイズ](#customize-policies-in-a-policy-package)**: 組織のニーズに合わせてポリシーパッケージのポリシーの設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="370b7-151">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="370b7-152">ポリシー設定に加えた変更は、パッケージを割り当てられたユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="370b7-152">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="370b7-153">Microsoft Teams 管理センターでポリシーパッケージを表示、割り当て、カスタマイズする方法の手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="370b7-153">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="370b7-154">ポリシーパッケージ内のポリシーの設定を表示する</span><span class="sxs-lookup"><span data-stu-id="370b7-154">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="370b7-155">Microsoft Teams 管理センターの左のナビゲーションで、[**ポリシーパッケージ**] をクリックし、パッケージ名の左側をクリックしてポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="370b7-155">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="370b7-156">表示するポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="370b7-156">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="370b7-157">ポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="370b7-157">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="370b7-158">1人のユーザーにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="370b7-158">Assign a policy package to one user</span></span>

1. <span data-ttu-id="370b7-159">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="370b7-159">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="370b7-160">ユーザーのページで、[**ポリシー**] をクリックし、[**ポリシーパッケージ**] の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370b7-160">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="370b7-161">[**ポリシーパッケージの割り当て**] ウィンドウで、割り当てるパッケージを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370b7-161">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="370b7-162">ポリシーパッケージを複数のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="370b7-162">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="370b7-163">Microsoft Teams 管理センターの左のナビゲーションで、[**ポリシーパッケージ**] に移動し、パッケージ名の左側をクリックして割り当てるポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="370b7-163">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="370b7-164">[**ユーザーの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370b7-164">Click **Manage users**.</span></span>
3. <span data-ttu-id="370b7-165">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370b7-165">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="370b7-166">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="370b7-166">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="370b7-167">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370b7-167">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="370b7-168">ポリシーパッケージを大規模なユーザー (バッチ) に割り当てる</span><span class="sxs-lookup"><span data-stu-id="370b7-168">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="370b7-169">バッチポリシーパッケージの割り当てを使用して、一度に多くのユーザーにポリシーパッケージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="370b7-169">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="370b7-170">[CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation)コマンドレットを使用して、ユーザーのバッチと、割り当てるポリシーパッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="370b7-170">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="370b7-171">割り当てはバックグラウンド操作として処理され、各バッチに対して操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="370b7-171">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="370b7-172">バッチには最大2万ユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="370b7-172">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="370b7-173">ユーザーは、オブジェクト Id、UPN、SIP アドレス、またはメールアドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="370b7-173">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="370b7-174">詳細については、「[ユーザーのバッチにポリシーパッケージを割り当てる](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="370b7-174">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="370b7-175">現時点では、一度に5000ユーザーのバッチでポリシーを割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="370b7-175">We're currently recommending that you assign policies in batches of 5,000 users at a time.</span></span> <span data-ttu-id="370b7-176">こうした需要が増加すると、処理時間の遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="370b7-176">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="370b7-177">これらの増加した処理時間の影響を最小限に抑えるために、最大5000人のユーザーに対して少量のバッチサイズを送信し、前のバッチが完了した後でのみ各バッチを送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="370b7-177">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="370b7-178">通常の営業時間外にバッチを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="370b7-178">Submitting batches outside your regular business hours can also help.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="370b7-179">ポリシーパッケージのポリシーをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="370b7-179">Customize policies in a policy package</span></span>

<span data-ttu-id="370b7-180">ポリシーの設定を編集するには、[**ポリシーパッケージ**] ページを使用するか、Microsoft Teams 管理センターの [ポリシー] ページに直接移動します。</span><span class="sxs-lookup"><span data-stu-id="370b7-180">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="370b7-181">Microsoft Teams 管理センターの左側のナビゲーションで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="370b7-181">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="370b7-182">[**ポリシーパッケージ**] をクリックし、パッケージ名の左側をクリックしてポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="370b7-182">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="370b7-183">[ポリシーの種類] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370b7-183">Click the policy type.</span></span>  <span data-ttu-id="370b7-184">たとえば、[**メッセージングポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370b7-184">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="370b7-185">編集するポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="370b7-185">Click the policy you want to edit.</span></span> <span data-ttu-id="370b7-186">ポリシーパッケージにリンクされているポリシーは、ポリシーパッケージと同じ名前になっています。</span><span class="sxs-lookup"><span data-stu-id="370b7-186">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="370b7-187">必要な変更を加えて、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370b7-187">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="370b7-188">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="370b7-188">Troubleshooting</span></span>

<span data-ttu-id="370b7-189">**ポリシーパッケージを割り当てるときにエラーが表示される**</span><span class="sxs-lookup"><span data-stu-id="370b7-189">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="370b7-190">この問題は、パッケージ内の1つ以上のポリシーが正常に作成または適用されなかった場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="370b7-190">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="370b7-191">ポリシーパッケージをユーザーに割り当て直します。</span><span class="sxs-lookup"><span data-stu-id="370b7-191">Reassign the policy package to your users.</span></span> <span data-ttu-id="370b7-192">通常、操作を再試行すると、この問題は修正されます。</span><span class="sxs-lookup"><span data-stu-id="370b7-192">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="370b7-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="370b7-193">Related topics</span></span>

[<span data-ttu-id="370b7-194">EDU 管理者向けの Microsoft Teams ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="370b7-194">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
