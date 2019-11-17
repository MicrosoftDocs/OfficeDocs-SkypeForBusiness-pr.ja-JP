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
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でポリシーパッケージを使用および管理する方法について説明します。
ms.openlocfilehash: ecfc6ae6fb1bb4d9632b8cd04b35dcee6d63359d
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "38679829"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="725e5-103">Microsoft Teams でポリシーパッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="725e5-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="725e5-104">Microsoft Teams のポリシーパッケージは、組織内で同様の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="725e5-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="725e5-105">組織全体のユーザーグループのポリシーを管理する際の一貫性を高めるために、ポリシーパッケージを作成しました。</span><span class="sxs-lookup"><span data-stu-id="725e5-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="725e5-106">ポリシーパッケージをユーザーに割り当てると、パッケージ内のポリシーが作成され、組織のニーズに合わせてパッケージ内のポリシーの設定をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="725e5-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="725e5-107">ポリシーパッケージとは</span><span class="sxs-lookup"><span data-stu-id="725e5-107">What is a policy package?</span></span>

<span data-ttu-id="725e5-108">ポリシーパッケージを使用すると、組織内の特定のユーザーのセットに対して許可または制限するチームの機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="725e5-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="725e5-109">Teams の各ポリシーパッケージは、ユーザーロールをベースに設計されており、その役割で一般的なコラボレーションと通信のアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="725e5-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="725e5-110">チームには現在、次のポリシーパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="725e5-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="725e5-111">**パッケージ名**</span><span class="sxs-lookup"><span data-stu-id="725e5-111">**Package name**</span></span>  |<span data-ttu-id="725e5-112">**説明**</span><span class="sxs-lookup"><span data-stu-id="725e5-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="725e5-113">Education_Teacher パッケージ</span><span class="sxs-lookup"><span data-stu-id="725e5-113">Education_Teacher package</span></span>     |<span data-ttu-id="725e5-114">教師に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="725e5-114">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="725e5-115">Education_PrimaryStudent パッケージ</span><span class="sxs-lookup"><span data-stu-id="725e5-115">Education_PrimaryStudent package</span></span>    |<span data-ttu-id="725e5-116">主要な学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="725e5-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="725e5-117">Education_SecondaryStudent パッケージ</span><span class="sxs-lookup"><span data-stu-id="725e5-117">Education_SecondaryStudent package</span></span>    |<span data-ttu-id="725e5-118">第2の学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="725e5-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="725e5-119">Education_HigherEducationStudent パッケージ</span><span class="sxs-lookup"><span data-stu-id="725e5-119">Education_HigherEducationStudent package</span></span>    |<span data-ttu-id="725e5-120">高等教育機関向けの学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="725e5-120">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="725e5-121">SmallMediumBusiness_BusinessVoice パッケージ</span><span class="sxs-lookup"><span data-stu-id="725e5-121">SmallMediumBusiness_BusinessVoice package</span></span>    |<span data-ttu-id="725e5-122">ビジネス音声エクスペリエンス用のアプリを含むアプリセットアップポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="725e5-122">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|

> [!NOTE]
> <span data-ttu-id="725e5-123">今後のチームのリリースでポリシーパッケージを追加しますので、最新の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="725e5-123">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="725e5-124">個々のポリシーには、ポリシーパッケージの名前が割り当てられているため、ポリシーパッケージにリンクされているポリシーを簡単に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="725e5-124">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="725e5-125">たとえば、学校の教師に Education_Teacher ポリシーパッケージを割り当てると、Education_Teacher という名前のポリシーがパッケージ内の各ポリシーに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="725e5-125">For example, when you assign the Education_Teacher policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher ポリシーパッケージのスクリーンショット](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="725e5-127">ポリシーパッケージの使用方法</span><span class="sxs-lookup"><span data-stu-id="725e5-127">How to use policy packages</span></span>

<span data-ttu-id="725e5-128">組織でポリシーパッケージを使用する方法については、次の表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="725e5-128">The following outlines how to use policy packages in your organization.</span></span>

![ポリシーパッケージの使用方法の概要](media/manage-policy-packages-overview.png)

- <span data-ttu-id="725e5-130">**[表示](#view-the-settings-of-a-policy-in-a-policy-package)**: パッケージを割り当てる前に、ポリシーパッケージ内の各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="725e5-130">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="725e5-131">各設定を理解していることを確認して、組織にとって事前に定義された値が適切かどうかを確認します。また、組織のニーズに基づいて、定義済みの値を変更する必要があるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="725e5-131">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="725e5-132">ポリシーが削除された場合でも、設定は表示できますが、設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="725e5-132">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="725e5-133">ポリシーパッケージを割り当てるときに、削除されたポリシーが定義済みの設定で再作成されます。</span><span class="sxs-lookup"><span data-stu-id="725e5-133">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="725e5-134">**[割り当て](#assign-a-policy-package)**: ポリシーパッケージをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="725e5-134">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="725e5-135">ポリシーパッケージのポリシーは、パッケージを割り当てるまで作成されないことに注意してください。その後、パッケージ内の個々のポリシーの設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="725e5-135">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="725e5-136">**[カスタマイズ](#customize-policies-in-a-policy-package)**: 組織のニーズに合わせてポリシーパッケージのポリシーの設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="725e5-136">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="725e5-137">ポリシー設定に加えた変更は、パッケージを割り当てられたユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="725e5-137">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="725e5-138">Microsoft Teams 管理センターでポリシーパッケージを表示、割り当て、カスタマイズする方法の手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="725e5-138">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="725e5-139">ポリシーパッケージ内のポリシーの設定を表示する</span><span class="sxs-lookup"><span data-stu-id="725e5-139">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="725e5-140">Microsoft Teams 管理センターの左のナビゲーションで、[**ポリシーパッケージ**] をクリックし、パッケージ名の左側をクリックしてポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="725e5-140">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="725e5-141">表示するポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="725e5-141">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="725e5-142">ポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="725e5-142">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="725e5-143">1人のユーザーにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="725e5-143">Assign a policy package to one user</span></span>

1. <span data-ttu-id="725e5-144">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="725e5-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="725e5-145">ユーザーのページで、[**ポリシー**] をクリックし、[**ポリシーパッケージ**] の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="725e5-145">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="725e5-146">[**ポリシーパッケージの割り当て**] ウィンドウで、割り当てるパッケージを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="725e5-146">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="725e5-147">ポリシーパッケージを複数のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="725e5-147">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="725e5-148">Microsoft Teams 管理センターの左のナビゲーションで、[**ポリシーパッケージ**] に移動し、パッケージ名の左側をクリックして割り当てるポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="725e5-148">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="725e5-149">[**ユーザーの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="725e5-149">Click **Manage users**.</span></span>
3. <span data-ttu-id="725e5-150">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="725e5-150">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="725e5-151">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="725e5-151">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="725e5-152">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="725e5-152">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="725e5-153">ポリシーパッケージのポリシーをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="725e5-153">Customize policies in a policy package</span></span>

<span data-ttu-id="725e5-154">ポリシーの設定を編集するには、[**ポリシーパッケージ**] ページを使用するか、Microsoft Teams 管理センターの [ポリシー] ページに直接移動します。</span><span class="sxs-lookup"><span data-stu-id="725e5-154">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="725e5-155">Microsoft Teams 管理センターの左側のナビゲーションで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="725e5-155">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="725e5-156">[**ポリシーパッケージ**] をクリックし、パッケージ名の左側をクリックしてポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="725e5-156">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="725e5-157">[ポリシーの種類] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="725e5-157">Click the policy type.</span></span>  <span data-ttu-id="725e5-158">たとえば、[**メッセージングポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="725e5-158">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="725e5-159">編集するポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="725e5-159">Click the policy you want to edit.</span></span> <span data-ttu-id="725e5-160">ポリシーパッケージにリンクされているポリシーは、ポリシーパッケージと同じ名前になっています。</span><span class="sxs-lookup"><span data-stu-id="725e5-160">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="725e5-161">必要な変更を加えて、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="725e5-161">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="725e5-162">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="725e5-162">Troubleshooting</span></span>

<span data-ttu-id="725e5-163">**ポリシーパッケージを割り当てるときにエラーが表示される**</span><span class="sxs-lookup"><span data-stu-id="725e5-163">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="725e5-164">この問題は、パッケージ内の1つ以上のポリシーが正常に作成または適用されなかった場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="725e5-164">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="725e5-165">ポリシーパッケージをユーザーに割り当て直します。</span><span class="sxs-lookup"><span data-stu-id="725e5-165">Reassign the policy package to your users.</span></span> <span data-ttu-id="725e5-166">通常、操作を再試行すると、この問題は修正されます。</span><span class="sxs-lookup"><span data-stu-id="725e5-166">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="725e5-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="725e5-167">Related topics</span></span>

[<span data-ttu-id="725e5-168">EDU の管理者向けの Microsoft Teams ポリシーパッケージ</span><span class="sxs-lookup"><span data-stu-id="725e5-168">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
