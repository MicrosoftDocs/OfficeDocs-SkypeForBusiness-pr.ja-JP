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
ms.openlocfilehash: b69ce06d01af624ff73386531d7ef2b77bef3b4e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43914068"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="592b0-103">Microsoft Teams でポリシーパッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="592b0-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="592b0-104">Microsoft Teams のポリシーパッケージは、組織内で同様の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="592b0-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="592b0-105">組織全体のユーザーグループのポリシーを管理する際の一貫性を高めるために、ポリシーパッケージを作成しました。</span><span class="sxs-lookup"><span data-stu-id="592b0-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="592b0-106">ポリシーパッケージをユーザーに割り当てると、パッケージ内のポリシーが作成され、組織のニーズに合わせてパッケージ内のポリシーの設定をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="592b0-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

<span data-ttu-id="592b0-107">ポリシーパッケージは、米国政府機関向けクラウドコミュニティ (GCC) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="592b0-107">Policy packages aren't available for US Government Cloud Community (GCC) organizations.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="592b0-108">ポリシーパッケージとは</span><span class="sxs-lookup"><span data-stu-id="592b0-108">What is a policy package?</span></span>

<span data-ttu-id="592b0-109">ポリシーパッケージを使用すると、組織内の特定のユーザーのセットに対して許可または制限するチームの機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="592b0-109">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="592b0-110">Teams の各ポリシーパッケージは、ユーザーロールをベースに設計されており、その役割で一般的なコラボレーションと通信のアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="592b0-110">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="592b0-111">チームには現在、次のポリシーパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="592b0-111">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="592b0-112">**パッケージ名**</span><span class="sxs-lookup"><span data-stu-id="592b0-112">**Package name**</span></span>  |<span data-ttu-id="592b0-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="592b0-113">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="592b0-114">教育機関 (高等教育機関向け生徒)</span><span class="sxs-lookup"><span data-stu-id="592b0-114">Education (Higher education student)</span></span>    |<span data-ttu-id="592b0-115">高等教育機関向けの学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="592b0-115">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="592b0-116">教育機関 (第1学校の学生)</span><span class="sxs-lookup"><span data-stu-id="592b0-116">Education (Primary school student)</span></span>   |<span data-ttu-id="592b0-117">主要な学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="592b0-117">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="592b0-118">教育機関 (第2学校の学生)</span><span class="sxs-lookup"><span data-stu-id="592b0-118">Education (Secondary school student)</span></span>    |<span data-ttu-id="592b0-119">第2の学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="592b0-119">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="592b0-120">教育機関 (教師)</span><span class="sxs-lookup"><span data-stu-id="592b0-120">Education (Teacher)</span></span>    |<span data-ttu-id="592b0-121">教師に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="592b0-121">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="592b0-122">中小規模企業のユーザー (ビジネス用ボイス)</span><span class="sxs-lookup"><span data-stu-id="592b0-122">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="592b0-123">ビジネス音声エクスペリエンス用のアプリを含むアプリセットアップポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="592b0-123">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="592b0-124">中小規模企業のユーザー (ビジネス用ボイスのない)</span><span class="sxs-lookup"><span data-stu-id="592b0-124">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="592b0-125">このポリシーパッケージは、ビジネスボイス機能を使わずに、一連のポリシーを作成し、その設定を中小規模企業のユーザーに適用するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="592b0-125">This policy package is designed to create a set of policies and apply those settings to small and medium sized business users without any Business Voice features.</span></span>|
|<span data-ttu-id="592b0-126">公安責任者</span><span class="sxs-lookup"><span data-stu-id="592b0-126">Public safety officer</span></span>   |<span data-ttu-id="592b0-127">組織の公衆安全責任者に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="592b0-127">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|
|<span data-ttu-id="592b0-128">医療 (臨床労働者)</span><span class="sxs-lookup"><span data-stu-id="592b0-128">Healthcare (Clinical worker)</span></span>  |<span data-ttu-id="592b0-129">登録された看護師、料金の看護師、医師、ソーシャルワーカーなどの、チャット、通話、シフト管理、および会議へのフルアクセスを可能にする、一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="592b0-129">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="592b0-130">医療 (インフォメーションワーカー)</span><span class="sxs-lookup"><span data-stu-id="592b0-130">Healthcare (Information worker)</span></span>  |<span data-ttu-id="592b0-131">IT 担当者、informatics 職員、財務担当者、コンプライアンス責任者、チャット、通話、会議へのフルアクセスなどの情報を提供する一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="592b0-131">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|


> [!NOTE]
> <span data-ttu-id="592b0-132">今後のチームのリリースでポリシーパッケージを追加しますので、最新の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="592b0-132">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="592b0-133">個々のポリシーには、ポリシーパッケージの名前が割り当てられているため、ポリシーパッケージにリンクされているポリシーを簡単に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="592b0-133">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="592b0-134">たとえば、学校の教師に教育 (教師) ポリシーパッケージを割り当てると、Education_Teacher という名前のポリシーがパッケージ内の各ポリシーに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="592b0-134">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育機関 (教師) ポリシーパッケージのスクリーンショット](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="592b0-136">ポリシーパッケージの使用方法</span><span class="sxs-lookup"><span data-stu-id="592b0-136">How to use policy packages</span></span>

<span data-ttu-id="592b0-137">組織でポリシーパッケージを使用する方法については、次の表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="592b0-137">The following outlines how to use policy packages in your organization.</span></span>

![ポリシーパッケージの使用方法の概要](media/manage-policy-packages-overview.png)

- <span data-ttu-id="592b0-139">**[表示](#view-the-settings-of-a-policy-in-a-policy-package)**: パッケージを割り当てる前に、ポリシーパッケージ内の各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="592b0-139">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="592b0-140">各設定を理解していることを確認して、組織にとって事前に定義された値が適切かどうかを確認します。また、組織のニーズに基づいて、定義済みの値を変更する必要があるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="592b0-140">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="592b0-141">ポリシーが削除された場合でも、設定は表示できますが、設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="592b0-141">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="592b0-142">ポリシーパッケージを割り当てるときに、削除されたポリシーが定義済みの設定で再作成されます。</span><span class="sxs-lookup"><span data-stu-id="592b0-142">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="592b0-143">**[割り当て](#assign-a-policy-package)**: ポリシーパッケージをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="592b0-143">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="592b0-144">ポリシーパッケージのポリシーは、パッケージを割り当てるまで作成されないことに注意してください。その後、パッケージ内の個々のポリシーの設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="592b0-144">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="592b0-145">**[カスタマイズ](#customize-policies-in-a-policy-package)**: 組織のニーズに合わせてポリシーパッケージのポリシーの設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="592b0-145">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="592b0-146">ポリシー設定に加えた変更は、パッケージを割り当てられたユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="592b0-146">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="592b0-147">Microsoft Teams 管理センターでポリシーパッケージを表示、割り当て、カスタマイズする方法の手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="592b0-147">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="592b0-148">ポリシーパッケージ内のポリシーの設定を表示する</span><span class="sxs-lookup"><span data-stu-id="592b0-148">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="592b0-149">Microsoft Teams 管理センターの左のナビゲーションで、[**ポリシーパッケージ**] をクリックし、パッケージ名の左側をクリックしてポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="592b0-149">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="592b0-150">表示するポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="592b0-150">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="592b0-151">ポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="592b0-151">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="592b0-152">1人のユーザーにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="592b0-152">Assign a policy package to one user</span></span>

1. <span data-ttu-id="592b0-153">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="592b0-153">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="592b0-154">ユーザーのページで、[**ポリシー**] をクリックし、[**ポリシーパッケージ**] の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="592b0-154">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="592b0-155">[**ポリシーパッケージの割り当て**] ウィンドウで、割り当てるパッケージを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="592b0-155">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="592b0-156">ポリシーパッケージを複数のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="592b0-156">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="592b0-157">Microsoft Teams 管理センターの左のナビゲーションで、[**ポリシーパッケージ**] に移動し、パッケージ名の左側をクリックして割り当てるポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="592b0-157">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="592b0-158">[**ユーザーの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="592b0-158">Click **Manage users**.</span></span>
3. <span data-ttu-id="592b0-159">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="592b0-159">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="592b0-160">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="592b0-160">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="592b0-161">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="592b0-161">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="592b0-162">ポリシーパッケージのポリシーをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="592b0-162">Customize policies in a policy package</span></span>

<span data-ttu-id="592b0-163">ポリシーの設定を編集するには、[**ポリシーパッケージ**] ページを使用するか、Microsoft Teams 管理センターの [ポリシー] ページに直接移動します。</span><span class="sxs-lookup"><span data-stu-id="592b0-163">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="592b0-164">Microsoft Teams 管理センターの左側のナビゲーションで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="592b0-164">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="592b0-165">[**ポリシーパッケージ**] をクリックし、パッケージ名の左側をクリックしてポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="592b0-165">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="592b0-166">[ポリシーの種類] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="592b0-166">Click the policy type.</span></span>  <span data-ttu-id="592b0-167">たとえば、[**メッセージングポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="592b0-167">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="592b0-168">編集するポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="592b0-168">Click the policy you want to edit.</span></span> <span data-ttu-id="592b0-169">ポリシーパッケージにリンクされているポリシーは、ポリシーパッケージと同じ名前になっています。</span><span class="sxs-lookup"><span data-stu-id="592b0-169">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="592b0-170">必要な変更を加えて、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="592b0-170">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="592b0-171">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="592b0-171">Troubleshooting</span></span>

<span data-ttu-id="592b0-172">**ポリシーパッケージを割り当てるときにエラーが表示される**</span><span class="sxs-lookup"><span data-stu-id="592b0-172">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="592b0-173">この問題は、パッケージ内の1つ以上のポリシーが正常に作成または適用されなかった場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="592b0-173">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="592b0-174">ポリシーパッケージをユーザーに割り当て直します。</span><span class="sxs-lookup"><span data-stu-id="592b0-174">Reassign the policy package to your users.</span></span> <span data-ttu-id="592b0-175">通常、操作を再試行すると、この問題は修正されます。</span><span class="sxs-lookup"><span data-stu-id="592b0-175">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="592b0-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="592b0-176">Related topics</span></span>

[<span data-ttu-id="592b0-177">EDU 管理者向けの Microsoft Teams ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="592b0-177">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
