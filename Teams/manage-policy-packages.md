---
title: アプリケーションでポリシー パッケージを管理Microsoft Teams
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
description: Microsoft Teams でポリシー パッケージを使用および管理して、ユーザー グループのポリシーを管理する際の一貫性を簡素化、合理化、および提供する方法について説明します。
ms.openlocfilehash: 63900f301a8b3a48a8c17c6278808cd52e2445da
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2021
ms.locfileid: "52810185"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="b1f2e-103">アプリケーションでポリシー パッケージを管理Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1f2e-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="b1f2e-104">Microsoft Teams のポリシー パッケージは、組織内で類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="b1f2e-105">組織全体のユーザー のグループに対するポリシーを管理する際に、一貫性を提供するために、ポリシー パッケージを構築しました。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="b1f2e-106">アプリケーションに含まれている[ポリシー パッケージをTeams](#policy-packages-included-in-teams)独自のカスタム ポリシー[パッケージを作成できます](#custom-policy-packages)。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-106">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理センターの [ポリシー パッケージ] ページのスクリーンショット":::

<span data-ttu-id="b1f2e-108">ユーザーのニーズに合わせて、ポリシー パッケージ内のポリシーの設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-108">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="b1f2e-109">パッケージ内のポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-109">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="b1f2e-110">ポリシー パッケージは、管理センターまたは PowerShell Microsoft Teams使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-110">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="b1f2e-111">カスタム ポリシー パッケージの割り当てを受け取るには、各ユーザーに Advanced Communications アドオンが必要です。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-111">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="b1f2e-112">詳細については、「Advanced [Communications add-on for Microsoft Teams」を参照してください](/microsoftteams/teams-add-on-licensing/advanced-communications)。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-112">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="b1f2e-113">ポリシー パッケージとは</span><span class="sxs-lookup"><span data-stu-id="b1f2e-113">What is a policy package?</span></span>

<span data-ttu-id="b1f2e-114">ポリシー パッケージを使用するとTeams特定のユーザーセットに対して許可または制限する機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-114">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="b1f2e-115">Teams の各ポリシー パッケージは、ユーザー ロールを中心に設計され、そのロールに一般的なコラボレーションおよび通信アクティビティをサポートする定義済みのポリシーとポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-115">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="b1f2e-116">ポリシー パッケージは、次の種類のポリシー Teamsサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-116">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="b1f2e-117">メッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1f2e-117">Messaging policy</span></span>
- <span data-ttu-id="b1f2e-118">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1f2e-118">Meeting policy</span></span>
- <span data-ttu-id="b1f2e-119">アプリセットアップ ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1f2e-119">App setup policy</span></span>
- <span data-ttu-id="b1f2e-120">通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1f2e-120">Calling policy</span></span>
- <span data-ttu-id="b1f2e-121">ライブ イベント ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1f2e-121">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="b1f2e-122">Teams に含まれるポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="b1f2e-122">Policy packages included in Teams</span></span>

<span data-ttu-id="b1f2e-123">Teamsには、現在、次のポリシー パッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-123">Teams currently includes the following policy packages.</span></span>

| <span data-ttu-id="b1f2e-124">パッケージ名</span><span class="sxs-lookup"><span data-stu-id="b1f2e-124">Package name</span></span> | <span data-ttu-id="b1f2e-125">説明</span><span class="sxs-lookup"><span data-stu-id="b1f2e-125">Description</span></span> |
|---------|---------|
|<span data-ttu-id="b1f2e-126">教育 (高等教育学生)</span><span class="sxs-lookup"><span data-stu-id="b1f2e-126">Education (Higher education student)</span></span>    |<span data-ttu-id="b1f2e-127">一連のポリシーとポリシー設定を作成します。この設定は、高学年の学生に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-127">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="b1f2e-128">Education (Primary school student)</span><span class="sxs-lookup"><span data-stu-id="b1f2e-128">Education (Primary school student)</span></span>   |<span data-ttu-id="b1f2e-129">プライマリ 学生に適用されるポリシーとポリシー設定のセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-129">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="b1f2e-130">教育 (中学生)</span><span class="sxs-lookup"><span data-stu-id="b1f2e-130">Education (Secondary school student)</span></span>    |<span data-ttu-id="b1f2e-131">セカンダリ 学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-131">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="b1f2e-132">教育 (教師)</span><span class="sxs-lookup"><span data-stu-id="b1f2e-132">Education (Teacher)</span></span>    |<span data-ttu-id="b1f2e-133">教師に適用されるポリシーとポリシー設定のセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-133">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="b1f2e-134">教育 (リモート学習を使用するプライマリ スクール教師)</span><span class="sxs-lookup"><span data-stu-id="b1f2e-134">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="b1f2e-135">小学校教師に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-135">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="b1f2e-136">教育 (リモート学習を使用するプライマリ スチューデント)</span><span class="sxs-lookup"><span data-stu-id="b1f2e-136">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="b1f2e-137">小学生に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-137">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="b1f2e-138">Frontline Manager</span><span class="sxs-lookup"><span data-stu-id="b1f2e-138">Frontline manager</span></span> |<span data-ttu-id="b1f2e-139">一連のポリシーを作成し、それらの設定を組織内の Frontline マネージャーに適用します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-139">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="b1f2e-140">Frontline worker</span><span class="sxs-lookup"><span data-stu-id="b1f2e-140">Frontline worker</span></span> |<span data-ttu-id="b1f2e-141">一連のポリシーを作成し、組織内の Frontline worker にそれらの設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-141">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="b1f2e-142">医療施設の職員</span><span class="sxs-lookup"><span data-stu-id="b1f2e-142">Healthcare clinical worker</span></span>  |<span data-ttu-id="b1f2e-143">一連のポリシーとポリシー設定を作成して、登録済看護師、担当看護師、医師、およびソーシャル ワーカーに対して、チャット、通話、シフト管理、会議へのフル アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-143">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="b1f2e-144">医療情報提供者</span><span class="sxs-lookup"><span data-stu-id="b1f2e-144">Healthcare information worker</span></span>  |<span data-ttu-id="b1f2e-145">一連のポリシーとポリシー設定を作成して、IT 担当者、情報スタッフ、財務担当者、法令遵守責任者に対して、チャット、通話、会議へのフル アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-145">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="b1f2e-146">医療患者室</span><span class="sxs-lookup"><span data-stu-id="b1f2e-146">Healthcare patient room</span></span>  |<span data-ttu-id="b1f2e-147">貴社の医療組織の患者室に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-147">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="b1f2e-148">中小企業ユーザー (Business Voice)</span><span class="sxs-lookup"><span data-stu-id="b1f2e-148">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="b1f2e-149">ビジネス音声エクスペリエンス用のアプリを含むアプリセットアップ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-149">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="b1f2e-150">中小企業ユーザー (Business Voice なし)</span><span class="sxs-lookup"><span data-stu-id="b1f2e-150">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="b1f2e-151">ユーザー (非 Business Voice エクスペリエンス) に関連するTeamsセットアップ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-151">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="b1f2e-152">公安責任者</span><span class="sxs-lookup"><span data-stu-id="b1f2e-152">Public safety officer</span></span>   |<span data-ttu-id="b1f2e-153">組織内の公安責任者に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-153">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="b1f2e-154">Teams の今後のリリースでポリシー パッケージを追加する予定なので、最新の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-154">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="b1f2e-155">ポリシー パッケージにリンクされているポリシーを容易に識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-155">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="b1f2e-156">たとえば、学校の教師に Education (Teacher) ポリシー パッケージを割り当てると、パッケージ内のポリシーごとに Education_Teacher という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-156">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Education (Teacher) ポリシー パッケージのスクリーンショット](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="b1f2e-158">カスタム ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="b1f2e-158">Custom policy packages</span></span>

<span data-ttu-id="b1f2e-159">**カスタム ポリシー パッケージは、アプリケーションではまだ使用Government Community Cloud (GCC)**</span><span class="sxs-lookup"><span data-stu-id="b1f2e-159">**Custom policy packages is not yet available for the Government Community Cloud (GCC)**</span></span>

<span data-ttu-id="b1f2e-160">カスタム ポリシー パッケージを使用すると、組織内で同様のロールを持つユーザーに対して独自のポリシー セットをバンドルできます。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-160">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="b1f2e-161">必要なポリシーの種類とポリシーを追加して、独自のポリシー パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-161">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="b1f2e-162">新しいカスタム ポリシー パッケージを作成するには:</span><span class="sxs-lookup"><span data-stu-id="b1f2e-162">To create a new custom policy package:</span></span>

1. <span data-ttu-id="b1f2e-163">管理センターの左側のナビゲーションMicrosoft Teams[ポリシー パッケージ] を選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-163">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>

    :::image type="content" source="media/policy-packages-add.png" alt-text="管理センターの [ポリシー パッケージ] ページの [追加] ボタンのスクリーンショット":::

2. <span data-ttu-id="b1f2e-165">パッケージの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-165">Enter a name and description for your package.</span></span>

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新しいカスタム ポリシー パッケージの追加のスクリーンショット":::

3. <span data-ttu-id="b1f2e-167">パッケージに含めるポリシーの種類とポリシー名を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-167">Select the policy types and policy names to include in the package.</span></span>

4. <span data-ttu-id="b1f2e-168">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-168">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="b1f2e-169">ポリシー パッケージの使い方</span><span class="sxs-lookup"><span data-stu-id="b1f2e-169">How to use policy packages</span></span>

<span data-ttu-id="b1f2e-170">次に、組織でポリシー パッケージを使用する方法の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-170">The following outlines how to use policy packages in your organization.</span></span>

![ポリシー パッケージの使用方法の概要](media/manage-policy-packages-overview.png)

- <span data-ttu-id="b1f2e-172">**[表示](#view-the-settings-of-a-policy-in-a-policy-package)**: ポリシー パッケージ内のポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-172">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="b1f2e-173">次に、パッケージを割り当てる前に、パッケージ内の各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-173">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="b1f2e-174">各設定を理解してください。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-174">Make sure that you understand each setting.</span></span> <span data-ttu-id="b1f2e-175">定義済みの値が組織に適しているかどうか、または組織のニーズに基づいて、より制限の厳しい値を変更する必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-175">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="b1f2e-176">ポリシーが削除された場合でも、設定を表示できますが、設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-176">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="b1f2e-177">ポリシー パッケージを割り当てると、定義済みの設定で削除されたポリシーが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-177">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="b1f2e-178">**[カスタマイズ](#customize-policies-in-a-policy-package)**: 組織のニーズに合わせてポリシー パッケージ内のポリシーの設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-178">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="b1f2e-179">**[割り](#assign-a-policy-package)** 当て: ポリシー パッケージをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-179">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="b1f2e-180">パッケージを割り当て後に、ポリシー パッケージ内のポリシーの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-180">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="b1f2e-181">ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-181">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="b1f2e-182">管理センターでポリシー パッケージを表示、割り当て、カスタマイズするMicrosoft Teamsします。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-182">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="b1f2e-183">ポリシー パッケージ内のポリシーの設定を表示する</span><span class="sxs-lookup"><span data-stu-id="b1f2e-183">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="b1f2e-184">Microsoft Teams 管理センターの左側のナビゲーションで、[ポリシー パッケージ] を選択し、パッケージ名の左側をクリックしてポリシー パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-184">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="b1f2e-185">表示するポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-185">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="b1f2e-186">ポリシー パッケージ内のポリシーをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b1f2e-186">Customize policies in a policy package</span></span>

<span data-ttu-id="b1f2e-187">ポリシーの設定は、[ポリシー パッケージ]ページで編集するか、管理センターのポリシー ページに直接移動Microsoft Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-187">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="b1f2e-188">管理センターの左側のMicrosoft Teams、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-188">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="b1f2e-189">[ **ポリシー パッケージ]** をクリックし、パッケージ名の左側をクリックしてポリシー パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-189">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="b1f2e-190">ポリシーの種類をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-190">Click the policy type.</span></span>  <span data-ttu-id="b1f2e-191">たとえば、[メッセージング ポリシー **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-191">For example, click **Messaging policies**.</span></span>

2. <span data-ttu-id="b1f2e-192">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-192">Select the policy you want to edit.</span></span> <span data-ttu-id="b1f2e-193">ポリシー パッケージにリンクされているポリシーは、ポリシー パッケージと同じ名前です。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-193">Policies that are linked to a policy package have the same name as the policy package.</span></span>

3. <span data-ttu-id="b1f2e-194">必要な変更を行い、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-194">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="b1f2e-195">ポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b1f2e-195">Assign a policy package</span></span>

<span data-ttu-id="b1f2e-196">ポリシー パッケージは、個々のユーザー、グループ、またはユーザーのバッチに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-196">You can assign a policy package to an individual user, a group, or a batch of users.</span></span> <span data-ttu-id="b1f2e-197">ポリシー パッケージを割り当てる方法の詳細については、「ユーザーとグループにポリシー パッケージを割り当 [てる」を参照してください](assign-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="b1f2e-197">For more information on how to assign policy packages, see [Assign policy packages to users and groups](assign-policy-packages.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1f2e-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1f2e-198">Related topics</span></span>

- [<span data-ttu-id="b1f2e-199">ポリシー パッケージの割り当て</span><span class="sxs-lookup"><span data-stu-id="b1f2e-199">Assign policy packages</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="b1f2e-200">Teams EDU 管理者向けポリシー パッケージの作成</span><span class="sxs-lookup"><span data-stu-id="b1f2e-200">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="b1f2e-201">ヘルスケア向けの Teams ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="b1f2e-201">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)
- [<span data-ttu-id="b1f2e-202">Teamsのポリシー パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="b1f2e-202">Teams policy packages for government</span></span>](policy-packages-gov.md)
