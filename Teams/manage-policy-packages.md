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
description: Microsoft Teams でポリシー パッケージを使用して管理し、ユーザー のグループのポリシーを管理する際に一貫性を提供するために、簡素化、合理化、および一貫性を提供する方法について説明します。
ms.openlocfilehash: 5713274270a7784379eb47c6dd1fa875b41e20b1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162677"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="84f79-103">Microsoft Teams でポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="84f79-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="84f79-104">この記事で説明するカスタム ポリシー パッケージの機能の 1 [つは、](#custom-policy-packages)現在、プライベート プレビューに含まれています。</span><span class="sxs-lookup"><span data-stu-id="84f79-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), is currently in private preview.</span></span>

<span data-ttu-id="84f79-105">Microsoft Teams のポリシー パッケージは、組織内で類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="84f79-105">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="84f79-106">組織全体のユーザー グループのポリシーを管理する際に、簡素化、合理化、一貫性を確保するために、ポリシー パッケージを構築しました。</span><span class="sxs-lookup"><span data-stu-id="84f79-106">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="84f79-107">Teams に含まれる [ポリシー パッケージを使用するか](#policy-packages-included-in-teams) 、(プライベート プレビューで) 独自 [のカスタム](#custom-policy-packages) ポリシー パッケージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="84f79-107">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理センターの [ポリシー パッケージ] ページのスクリーンショット":::

<span data-ttu-id="84f79-109">ユーザーのニーズに合わせて、ポリシー パッケージ内のポリシーの設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="84f79-109">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="84f79-110">パッケージ内のポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="84f79-110">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="84f79-111">ポリシー パッケージを管理するには、Microsoft Teams 管理センターまたは PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="84f79-111">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="84f79-112">ポリシー パッケージとは</span><span class="sxs-lookup"><span data-stu-id="84f79-112">What is a policy package?</span></span>

<span data-ttu-id="84f79-113">ポリシー パッケージを使用すると、組織全体の特定のユーザー セットに対して許可または制限する Teams の機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="84f79-113">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="84f79-114">Teams の各ポリシー パッケージは、ユーザー ロールを中心に設計され、その役割に一般的なコラボレーションおよびコミュニケーション アクティビティをサポートする定義済みのポリシーとポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="84f79-114">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="84f79-115">ポリシー パッケージは、次の Teams ポリシーの種類をサポートします。</span><span class="sxs-lookup"><span data-stu-id="84f79-115">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="84f79-116">メッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="84f79-116">Messaging policy</span></span>
- <span data-ttu-id="84f79-117">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="84f79-117">Meeting policy</span></span>
- <span data-ttu-id="84f79-118">アプリセットアップ ポリシー</span><span class="sxs-lookup"><span data-stu-id="84f79-118">App setup policy</span></span>
- <span data-ttu-id="84f79-119">通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="84f79-119">Calling policy</span></span>
- <span data-ttu-id="84f79-120">ライブ イベント ポリシー</span><span class="sxs-lookup"><span data-stu-id="84f79-120">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="84f79-121">Teams に含まれるポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="84f79-121">Policy packages included in Teams</span></span>

<span data-ttu-id="84f79-122">Teams には現在、次のポリシー パッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="84f79-122">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="84f79-123">**パッケージ名**</span><span class="sxs-lookup"><span data-stu-id="84f79-123">**Package name**</span></span>  |<span data-ttu-id="84f79-124">**説明**</span><span class="sxs-lookup"><span data-stu-id="84f79-124">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="84f79-125">教育 (高等教育学生)</span><span class="sxs-lookup"><span data-stu-id="84f79-125">Education (Higher education student)</span></span>    |<span data-ttu-id="84f79-126">高等教育の学生に適用されるポリシーとポリシー設定のセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="84f79-126">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="84f79-127">Education (小学校の学生)</span><span class="sxs-lookup"><span data-stu-id="84f79-127">Education (Primary school student)</span></span>   |<span data-ttu-id="84f79-128">プライマリ 学生に適用されるポリシーとポリシー設定のセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="84f79-128">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="84f79-129">Education (中等学生)</span><span class="sxs-lookup"><span data-stu-id="84f79-129">Education (Secondary school student)</span></span>    |<span data-ttu-id="84f79-130">第 2 学生に適用されるポリシーとポリシー設定のセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="84f79-130">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="84f79-131">Education (教師)</span><span class="sxs-lookup"><span data-stu-id="84f79-131">Education (Teacher)</span></span>    |<span data-ttu-id="84f79-132">教師に適用されるポリシーとポリシー設定のセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="84f79-132">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="84f79-133">Education (リモート学習を使用する小学校教師)</span><span class="sxs-lookup"><span data-stu-id="84f79-133">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="84f79-134">小学校教師に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="84f79-134">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="84f79-135">Education (リモート学習を使用する主な学生)</span><span class="sxs-lookup"><span data-stu-id="84f79-135">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="84f79-136">小学生に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="84f79-136">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="84f79-137">Frontline Manager</span><span class="sxs-lookup"><span data-stu-id="84f79-137">Frontline manager</span></span> |<span data-ttu-id="84f79-138">一連のポリシーを作成し、それらの設定を組織内の Frontline マネージャーに適用します。</span><span class="sxs-lookup"><span data-stu-id="84f79-138">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="84f79-139">最前線の従業員</span><span class="sxs-lookup"><span data-stu-id="84f79-139">Frontline worker</span></span> |<span data-ttu-id="84f79-140">一連のポリシーを作成し、それらの設定を組織内の Frontline ワーカーに適用します。</span><span class="sxs-lookup"><span data-stu-id="84f79-140">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="84f79-141">医療施設の職員</span><span class="sxs-lookup"><span data-stu-id="84f79-141">Healthcare clinical worker</span></span>  |<span data-ttu-id="84f79-142">一連のポリシーとポリシー設定を作成して、登録済看護師、担当看護師、医師、およびソーシャル ワーカーに対して、チャット、通話、シフト管理、会議へのフル アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="84f79-142">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="84f79-143">医療情報提供者</span><span class="sxs-lookup"><span data-stu-id="84f79-143">Healthcare information worker</span></span>  |<span data-ttu-id="84f79-144">一連のポリシーとポリシー設定を作成して、IT 担当者、情報スタッフ、財務担当者、法令遵守責任者に対して、チャット、通話、会議へのフル アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="84f79-144">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="84f79-145">医療患者室</span><span class="sxs-lookup"><span data-stu-id="84f79-145">Healthcare patient room</span></span>  |<span data-ttu-id="84f79-146">貴社の医療組織の患者室に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="84f79-146">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="84f79-147">中小企業ユーザー (Business Voice)</span><span class="sxs-lookup"><span data-stu-id="84f79-147">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="84f79-148">ビジネス ボイス エクスペリエンス用のアプリを含むアプリ セットアップ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="84f79-148">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="84f79-149">中小規模ビジネス ユーザー (Business Voice を使用しない)</span><span class="sxs-lookup"><span data-stu-id="84f79-149">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="84f79-150">中小規模のビジネス Teams ユーザーに関連するアプリセットアップ ポリシーを作成します (ビジネスボイス以外のエクスペリエンス)。</span><span class="sxs-lookup"><span data-stu-id="84f79-150">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="84f79-151">公安責任者</span><span class="sxs-lookup"><span data-stu-id="84f79-151">Public safety officer</span></span>   |<span data-ttu-id="84f79-152">組織の公安責任者に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="84f79-152">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="84f79-153">Teams の今後のリリースでポリシー パッケージを追加する予定なので、最新の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="84f79-153">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="84f79-154">ポリシー パッケージにリンクされているポリシーを容易に識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。</span><span class="sxs-lookup"><span data-stu-id="84f79-154">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="84f79-155">たとえば、学校の教師に教育 (教師) ポリシー パッケージを割り当てると、パッケージ内のポリシーごとに Education_Teacher という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="84f79-155">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Education (教師) ポリシー パッケージのスクリーンショット](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="84f79-157">カスタム ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="84f79-157">Custom policy packages</span></span>

<span data-ttu-id="84f79-158">**この機能はプライベート プレビューです**</span><span class="sxs-lookup"><span data-stu-id="84f79-158">**This feature is in private preview**</span></span>

<span data-ttu-id="84f79-159">カスタム ポリシー パッケージを使用すると、組織内で同様の役割を持つユーザーに独自のポリシー セットをバンドルできます。</span><span class="sxs-lookup"><span data-stu-id="84f79-159">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="84f79-160">必要なポリシーの種類とポリシーを追加して、独自のポリシー パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="84f79-160">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="84f79-161">新しいカスタム ポリシー パッケージを作成するには、</span><span class="sxs-lookup"><span data-stu-id="84f79-161">To create a new custom policy package:</span></span>

1. <span data-ttu-id="84f79-162">Microsoft Teams 管理センターの左側のナビゲーションで、[ポリシー **パッケージ]** を選択し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="84f79-162">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="管理センターの [ポリシー パッケージ] ページの [追加] ボタンのスクリーンショット":::
2. <span data-ttu-id="84f79-164">パッケージの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="84f79-164">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新しいカスタム ポリシー パッケージの追加のスクリーンショット":::
3. <span data-ttu-id="84f79-166">パッケージに含めるポリシーの種類とポリシー名を選択します。</span><span class="sxs-lookup"><span data-stu-id="84f79-166">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="84f79-167">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84f79-167">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="84f79-168">ポリシー パッケージの使い方</span><span class="sxs-lookup"><span data-stu-id="84f79-168">How to use policy packages</span></span>

<span data-ttu-id="84f79-169">組織でポリシー パッケージを使用する方法の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="84f79-169">The following outlines how to use policy packages in your organization.</span></span>

![ポリシー パッケージの使い方の概要](media/manage-policy-packages-overview.png)

- <span data-ttu-id="84f79-171">**[表示](#view-the-settings-of-a-policy-in-a-policy-package)**: ポリシー パッケージ内のポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="84f79-171">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="84f79-172">次に、パッケージを割り当てる前に、パッケージ内の各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="84f79-172">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="84f79-173">各設定を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="84f79-173">Make sure that you understand each setting.</span></span> <span data-ttu-id="84f79-174">定義済みの値が組織に適しているのか、または組織のニーズに基づいて制限を厳しくするか、適切に変更する必要があるのかを決定します。</span><span class="sxs-lookup"><span data-stu-id="84f79-174">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="84f79-175">ポリシーが削除された場合でも、設定は表示できますが、設定は変更されません。</span><span class="sxs-lookup"><span data-stu-id="84f79-175">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="84f79-176">ポリシー パッケージを割り当てると、定義済みの設定で削除されたポリシーが再び作成されます。</span><span class="sxs-lookup"><span data-stu-id="84f79-176">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="84f79-177">**[カスタマイズ](#customize-policies-in-a-policy-package)**: 組織のニーズに合わせてポリシー パッケージ内のポリシーの設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="84f79-177">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="84f79-178">**[割り](#assign-a-policy-package)** 当て: ポリシー パッケージをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="84f79-178">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="84f79-179">また、パッケージを割り当て後にポリシー パッケージ内のポリシーの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="84f79-179">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="84f79-180">ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="84f79-180">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="84f79-181">Microsoft Teams 管理センターでポリシー パッケージを表示、割り当て、カスタマイズする手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="84f79-181">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="84f79-182">ポリシー パッケージ内のポリシーの設定を表示する</span><span class="sxs-lookup"><span data-stu-id="84f79-182">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="84f79-183">Microsoft Teams 管理センターの左側のナビゲーションで、[ポリシー パッケージ] を選択し、パッケージ名の左側をクリックしてポリシー パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="84f79-183">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="84f79-184">表示するポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="84f79-184">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="84f79-185">ポリシー パッケージ内のポリシーをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="84f79-185">Customize policies in a policy package</span></span>

<span data-ttu-id="84f79-186">ポリシーの設定は、[ポリシー パッケージ]ページから、または Microsoft Teams 管理センターのポリシー ページに直接移動して編集できます。</span><span class="sxs-lookup"><span data-stu-id="84f79-186">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="84f79-187">Microsoft Teams 管理センターの左側のナビゲーションで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="84f79-187">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="84f79-188">[ **ポリシー パッケージ]** をクリックし、パッケージ名の左側をクリックしてポリシー パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="84f79-188">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="84f79-189">ポリシーの種類をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84f79-189">Click the policy type.</span></span>  <span data-ttu-id="84f79-190">たとえば、[メッセージング ポリシー **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="84f79-190">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="84f79-191">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="84f79-191">Select the policy you want to edit.</span></span> <span data-ttu-id="84f79-192">ポリシー パッケージにリンクされているポリシーは、ポリシー パッケージと同じ名前です。</span><span class="sxs-lookup"><span data-stu-id="84f79-192">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="84f79-193">必要な変更を行い、[保存] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="84f79-193">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="84f79-194">ポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="84f79-194">Assign a policy package</span></span> 

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="84f79-195">ポリシー パッケージを 1 人のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="84f79-195">Assign a policy package to one user</span></span>

1. <span data-ttu-id="84f79-196">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="84f79-196">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="84f79-197">ユーザーのページで、**[ポリシー]** をクリックし、**[ポリシー パッケージ]** の横の **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84f79-197">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="84f79-198">**[ポリシー パッケージの割り当て]** ウィンドウで、割り当てるパッケージを選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84f79-198">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="84f79-199">ポリシー パッケージを複数のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="84f79-199">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="84f79-200">Microsoft Teams 管理センターの左側のナビゲーションで **[ポリシー パッケージ]** に移動し、パッケージ名の左側をクリックして、割り当てるポリシー パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="84f79-200">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="84f79-201">**[ユーザーの管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84f79-201">Click **Manage users**.</span></span>
3. <span data-ttu-id="84f79-202">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84f79-202">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="84f79-203">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="84f79-203">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="84f79-204">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84f79-204">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="84f79-205">ポリシー パッケージをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="84f79-205">Assign a policy package to a group</span></span>

<span data-ttu-id="84f79-206">グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="84f79-206">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="84f79-207">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="84f79-207">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="84f79-208">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="84f79-208">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="84f79-209">この方法は、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="84f79-209">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="84f79-210">詳細については、[「グループにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-group)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84f79-210">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="84f79-211">ポリシー パッケージを多数 (一群) のユーザー セットに割り当てる</span><span class="sxs-lookup"><span data-stu-id="84f79-211">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="84f79-212">バッチ ポリシーパッケージの割り当てを使用して、多数のユーザー セットに同時にポリシーパッケージを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="84f79-212">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="84f79-213">[New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) コマンドレットを使用して、割り当てたい一群のユーザーおよびポリシー パッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="84f79-213">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="84f79-214">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="84f79-214">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="84f79-215">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="84f79-215">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="84f79-216">ユーザーをオブジェクト ID、UPN、SIP アドレス、またはメール アドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="84f79-216">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="84f79-217">詳細については、[「一群のユーザーにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84f79-217">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="84f79-218">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="84f79-218">Troubleshooting</span></span>

<span data-ttu-id="84f79-219">**ポリシー パッケージを割り当てるとエラーが表示される**</span><span class="sxs-lookup"><span data-stu-id="84f79-219">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="84f79-220">これは、パッケージ内の 1 つ以上のポリシーが正常に作成または適用されなかった場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="84f79-220">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="84f79-221">ポリシー パッケージをユーザーに再割り当てします。</span><span class="sxs-lookup"><span data-stu-id="84f79-221">Reassign the policy package to your users.</span></span> <span data-ttu-id="84f79-222">通常、操作を再試行すると、この問題が修正されます。</span><span class="sxs-lookup"><span data-stu-id="84f79-222">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="84f79-223">関連項目</span><span class="sxs-lookup"><span data-stu-id="84f79-223">Related topics</span></span>

[<span data-ttu-id="84f79-224">Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="84f79-224">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="84f79-225">EDU 管理者向け Teams ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="84f79-225">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="84f79-226">ヘルスケア向けの Teams ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="84f79-226">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="84f79-227">政府機関向け Teams ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="84f79-227">Teams policy packages for government</span></span>](policy-packages-gov.md)