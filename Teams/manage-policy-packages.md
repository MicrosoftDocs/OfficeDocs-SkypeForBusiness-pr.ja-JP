---
title: Microsoft Teams でポリシー パッケージを管理する
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams でポリシー パッケージを使用して管理し、ユーザー グループのポリシーを管理する際に、一貫性を簡素化、合理化、および提供する方法について説明します。
ms.openlocfilehash: 1173f5a626d6ea559dadd75149a0517f515d821b
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51699342"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="3d08b-103">Microsoft Teams でポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="3d08b-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="3d08b-104">Microsoft Teams のポリシー パッケージは、組織内で類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="3d08b-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="3d08b-105">組織全体のユーザー グループのポリシーを管理する際に、簡素化、合理化、一貫性を確保するために、ポリシー パッケージを構築しました。</span><span class="sxs-lookup"><span data-stu-id="3d08b-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="3d08b-106">Teams に含まれる[ポリシー パッケージを使用するか、独自](#policy-packages-included-in-teams)[のカスタム ポリシー パッケージを作成できます](#custom-policy-packages)。</span><span class="sxs-lookup"><span data-stu-id="3d08b-106">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理センターの [ポリシー パッケージ] ページのスクリーンショット":::

<span data-ttu-id="3d08b-108">ユーザーのニーズに合わせて、ポリシー パッケージ内のポリシーの設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3d08b-108">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="3d08b-109">パッケージ内のポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-109">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="3d08b-110">ポリシー パッケージを管理するには、Microsoft Teams 管理センターまたは PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-110">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="3d08b-111">ポリシー パッケージとは</span><span class="sxs-lookup"><span data-stu-id="3d08b-111">What is a policy package?</span></span>

<span data-ttu-id="3d08b-112">ポリシー パッケージを使用すると、組織全体の特定のユーザー セットに対して許可または制限する Teams の機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="3d08b-112">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="3d08b-113">Teams の各ポリシー パッケージは、ユーザー ロールを中心に設計され、その役割に一般的なコラボレーションおよびコミュニケーション アクティビティをサポートする定義済みのポリシーとポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d08b-113">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="3d08b-114">ポリシー パッケージは、次の Teams ポリシーの種類をサポートします。</span><span class="sxs-lookup"><span data-stu-id="3d08b-114">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="3d08b-115">メッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="3d08b-115">Messaging policy</span></span>
- <span data-ttu-id="3d08b-116">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="3d08b-116">Meeting policy</span></span>
- <span data-ttu-id="3d08b-117">アプリセットアップ ポリシー</span><span class="sxs-lookup"><span data-stu-id="3d08b-117">App setup policy</span></span>
- <span data-ttu-id="3d08b-118">通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="3d08b-118">Calling policy</span></span>
- <span data-ttu-id="3d08b-119">ライブ イベント ポリシー</span><span class="sxs-lookup"><span data-stu-id="3d08b-119">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="3d08b-120">Teams に含まれるポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="3d08b-120">Policy packages included in Teams</span></span>

<span data-ttu-id="3d08b-121">Teams には現在、次のポリシー パッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d08b-121">Teams currently includes the following policy packages.</span></span>

| <span data-ttu-id="3d08b-122">パッケージ名</span><span class="sxs-lookup"><span data-stu-id="3d08b-122">Package name</span></span> | <span data-ttu-id="3d08b-123">説明</span><span class="sxs-lookup"><span data-stu-id="3d08b-123">Description</span></span> |
|---------|---------|
|<span data-ttu-id="3d08b-124">教育 (高等教育学生)</span><span class="sxs-lookup"><span data-stu-id="3d08b-124">Education (Higher education student)</span></span>    |<span data-ttu-id="3d08b-125">高等教育の学生に適用されるポリシーとポリシー設定のセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-125">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="3d08b-126">Education (小学校の学生)</span><span class="sxs-lookup"><span data-stu-id="3d08b-126">Education (Primary school student)</span></span>   |<span data-ttu-id="3d08b-127">プライマリ 学生に適用されるポリシーとポリシー設定のセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-127">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="3d08b-128">Education (中等学生)</span><span class="sxs-lookup"><span data-stu-id="3d08b-128">Education (Secondary school student)</span></span>    |<span data-ttu-id="3d08b-129">第 2 学生に適用されるポリシーとポリシー設定のセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-129">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="3d08b-130">Education (教師)</span><span class="sxs-lookup"><span data-stu-id="3d08b-130">Education (Teacher)</span></span>    |<span data-ttu-id="3d08b-131">教師に適用されるポリシーとポリシー設定のセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-131">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="3d08b-132">Education (リモート学習を使用する小学校教師)</span><span class="sxs-lookup"><span data-stu-id="3d08b-132">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="3d08b-133">小学校教師に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="3d08b-133">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="3d08b-134">Education (リモート学習を使用する主な学生)</span><span class="sxs-lookup"><span data-stu-id="3d08b-134">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="3d08b-135">小学生に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="3d08b-135">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="3d08b-136">Frontline Manager</span><span class="sxs-lookup"><span data-stu-id="3d08b-136">Frontline manager</span></span> |<span data-ttu-id="3d08b-137">一連のポリシーを作成し、それらの設定を組織内の Frontline マネージャーに適用します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-137">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="3d08b-138">最前線の従業員</span><span class="sxs-lookup"><span data-stu-id="3d08b-138">Frontline worker</span></span> |<span data-ttu-id="3d08b-139">一連のポリシーを作成し、それらの設定を組織内の Frontline ワーカーに適用します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-139">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="3d08b-140">医療施設の職員</span><span class="sxs-lookup"><span data-stu-id="3d08b-140">Healthcare clinical worker</span></span>  |<span data-ttu-id="3d08b-141">一連のポリシーとポリシー設定を作成して、登録済看護師、担当看護師、医師、およびソーシャル ワーカーに対して、チャット、通話、シフト管理、会議へのフル アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-141">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="3d08b-142">医療情報提供者</span><span class="sxs-lookup"><span data-stu-id="3d08b-142">Healthcare information worker</span></span>  |<span data-ttu-id="3d08b-143">一連のポリシーとポリシー設定を作成して、IT 担当者、情報スタッフ、財務担当者、法令遵守責任者に対して、チャット、通話、会議へのフル アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-143">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="3d08b-144">医療患者室</span><span class="sxs-lookup"><span data-stu-id="3d08b-144">Healthcare patient room</span></span>  |<span data-ttu-id="3d08b-145">貴社の医療組織の患者室に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-145">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="3d08b-146">中小企業ユーザー (Business Voice)</span><span class="sxs-lookup"><span data-stu-id="3d08b-146">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="3d08b-147">ビジネス ボイス エクスペリエンス用のアプリを含むアプリ セットアップ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-147">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="3d08b-148">中小規模ビジネス ユーザー (Business Voice を使用しない)</span><span class="sxs-lookup"><span data-stu-id="3d08b-148">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="3d08b-149">中小規模のビジネス Teams ユーザーに関連するアプリセットアップ ポリシーを作成します (ビジネスボイス以外のエクスペリエンス)。</span><span class="sxs-lookup"><span data-stu-id="3d08b-149">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="3d08b-150">公安責任者</span><span class="sxs-lookup"><span data-stu-id="3d08b-150">Public safety officer</span></span>   |<span data-ttu-id="3d08b-151">組織の公安責任者に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-151">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="3d08b-152">Teams の今後のリリースでポリシー パッケージを追加する予定なので、最新の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3d08b-152">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="3d08b-153">ポリシー パッケージにリンクされているポリシーを容易に識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。</span><span class="sxs-lookup"><span data-stu-id="3d08b-153">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="3d08b-154">たとえば、教育 (教師) ポリシー パッケージを学校の教師に割り当てると、パッケージ内のポリシーごとに Education_Teacher という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3d08b-154">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Education (教師) ポリシー パッケージのスクリーンショット](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="3d08b-156">カスタム ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="3d08b-156">Custom policy packages</span></span>

<span data-ttu-id="3d08b-157">**カスタム ポリシー パッケージは、Government Community Cloud (GCC) ではまだ利用できません**</span><span class="sxs-lookup"><span data-stu-id="3d08b-157">**Custom policy packages is not yet available for the Government Community Cloud (GCC)**</span></span>

<span data-ttu-id="3d08b-158">カスタム ポリシー パッケージを使用すると、組織内で同様の役割を持つユーザーに独自のポリシー セットをバンドルできます。</span><span class="sxs-lookup"><span data-stu-id="3d08b-158">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="3d08b-159">必要なポリシーの種類とポリシーを追加して、独自のポリシー パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-159">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="3d08b-160">新しいカスタム ポリシー パッケージを作成するには、</span><span class="sxs-lookup"><span data-stu-id="3d08b-160">To create a new custom policy package:</span></span>

1. <span data-ttu-id="3d08b-161">Microsoft Teams 管理センターの左側のナビゲーションで、[ポリシー **パッケージ]** を選択し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="3d08b-161">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>

    :::image type="content" source="media/policy-packages-add.png" alt-text="管理センターの [ポリシー パッケージ] ページの [追加] ボタンのスクリーンショット":::

2. <span data-ttu-id="3d08b-163">パッケージの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-163">Enter a name and description for your package.</span></span>

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新しいカスタム ポリシー パッケージの追加のスクリーンショット":::

3. <span data-ttu-id="3d08b-165">パッケージに含めるポリシーの種類とポリシー名を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-165">Select the policy types and policy names to include in the package.</span></span>

4. <span data-ttu-id="3d08b-166">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d08b-166">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="3d08b-167">ポリシー パッケージの使い方</span><span class="sxs-lookup"><span data-stu-id="3d08b-167">How to use policy packages</span></span>

<span data-ttu-id="3d08b-168">組織でポリシー パッケージを使用する方法の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-168">The following outlines how to use policy packages in your organization.</span></span>

![ポリシー パッケージの使い方の概要](media/manage-policy-packages-overview.png)

- <span data-ttu-id="3d08b-170">**[表示](#view-the-settings-of-a-policy-in-a-policy-package)**: ポリシー パッケージ内のポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-170">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="3d08b-171">次に、パッケージを割り当てる前に、パッケージ内の各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-171">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="3d08b-172">各設定を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d08b-172">Make sure that you understand each setting.</span></span> <span data-ttu-id="3d08b-173">定義済みの値が組織に適しているのか、または組織のニーズに基づいて制限を厳しくするか、適切に変更する必要があるのかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-173">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="3d08b-174">ポリシーが削除された場合でも、設定は表示できますが、設定は変更されません。</span><span class="sxs-lookup"><span data-stu-id="3d08b-174">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="3d08b-175">ポリシー パッケージを割り当てると、定義済みの設定で削除されたポリシーが再び作成されます。</span><span class="sxs-lookup"><span data-stu-id="3d08b-175">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="3d08b-176">**[カスタマイズ](#customize-policies-in-a-policy-package)**: 組織のニーズに合わせてポリシー パッケージ内のポリシーの設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="3d08b-176">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="3d08b-177">**[割り](#assign-a-policy-package)** 当て: ポリシー パッケージをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="3d08b-177">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="3d08b-178">また、パッケージを割り当て後にポリシー パッケージ内のポリシーの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="3d08b-178">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="3d08b-179">ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3d08b-179">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="3d08b-180">Microsoft Teams 管理センターでポリシー パッケージを表示、割り当て、カスタマイズする手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3d08b-180">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="3d08b-181">ポリシー パッケージ内のポリシーの設定を表示する</span><span class="sxs-lookup"><span data-stu-id="3d08b-181">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="3d08b-182">Microsoft Teams 管理センターの左側のナビゲーションで、[ポリシー パッケージ] を選択し、パッケージ名の左側をクリックしてポリシー パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-182">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="3d08b-183">表示するポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d08b-183">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="3d08b-184">ポリシー パッケージ内のポリシーをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="3d08b-184">Customize policies in a policy package</span></span>

<span data-ttu-id="3d08b-185">ポリシーの設定は、[ポリシー パッケージ]ページから、または Microsoft Teams 管理センターのポリシー ページに直接移動して編集できます。</span><span class="sxs-lookup"><span data-stu-id="3d08b-185">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="3d08b-186">Microsoft Teams 管理センターの左側のナビゲーションで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3d08b-186">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="3d08b-187">[ **ポリシー パッケージ]** をクリックし、パッケージ名の左側をクリックしてポリシー パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-187">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="3d08b-188">ポリシーの種類をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d08b-188">Click the policy type.</span></span>  <span data-ttu-id="3d08b-189">たとえば、[メッセージング ポリシー **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3d08b-189">For example, click **Messaging policies**.</span></span>

2. <span data-ttu-id="3d08b-190">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3d08b-190">Select the policy you want to edit.</span></span> <span data-ttu-id="3d08b-191">ポリシー パッケージにリンクされているポリシーは、ポリシー パッケージと同じ名前です。</span><span class="sxs-lookup"><span data-stu-id="3d08b-191">Policies that are linked to a policy package have the same name as the policy package.</span></span>

3. <span data-ttu-id="3d08b-192">必要な変更を行い、[保存] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="3d08b-192">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="3d08b-193">ポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3d08b-193">Assign a policy package</span></span>

<span data-ttu-id="3d08b-194">ポリシー パッケージは、個々のユーザー、グループ、またはユーザーのバッチに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="3d08b-194">You can assign a policy package to an individual user, a group, or a batch of users.</span></span> <span data-ttu-id="3d08b-195">ポリシー パッケージを割り当てる方法の詳細については、「ユーザーとグループにポリシー パッケージを割り当 [てる」を参照してください](assign-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="3d08b-195">For more information on how to assign policy packages, see [Assign policy packages to users and groups](assign-policy-packages.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3d08b-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d08b-196">Related topics</span></span>

- [<span data-ttu-id="3d08b-197">ポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3d08b-197">Assign policy packages</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="3d08b-198">EDU 管理者向け Teams ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="3d08b-198">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="3d08b-199">ヘルスケア向けの Teams ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="3d08b-199">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)
- [<span data-ttu-id="3d08b-200">政府機関向け Teams ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="3d08b-200">Teams policy packages for government</span></span>](policy-packages-gov.md)
