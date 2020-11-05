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
ms.openlocfilehash: 986d64b11420877e146abc68f9f65c0503f49ff0
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918655"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="e6f73-103">Microsoft Teams でポリシーパッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="e6f73-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="e6f73-104">この記事で説明されている機能の1つ ( [カスタムポリシーパッケージ](#custom-policy-packages)) は、現在、プライベートプレビューにあります。</span><span class="sxs-lookup"><span data-stu-id="e6f73-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), is currently in private preview.</span></span>

<span data-ttu-id="e6f73-105">Microsoft Teams のポリシーパッケージは、組織内で同様の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="e6f73-105">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="e6f73-106">組織全体のユーザーグループのポリシーを管理する際の一貫性を高めるために、ポリシーパッケージを作成しました。</span><span class="sxs-lookup"><span data-stu-id="e6f73-106">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="e6f73-107">[チームに含まれているポリシーパッケージ](#policy-packages-included-in-teams)を使用するか、[独自のカスタムポリシーパッケージ](#custom-policy-packages)(プライベートプレビュー) を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-107">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理センターの [ポリシーパッケージ] ページのスクリーンショット":::

<span data-ttu-id="e6f73-109">ポリシーパッケージ内のポリシーの設定は、ユーザーのニーズに合わせてカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-109">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="e6f73-110">パッケージ内のポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-110">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="e6f73-111">ポリシーパッケージを管理するには、Microsoft Teams 管理センターまたは PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-111">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="e6f73-112">ポリシーパッケージとは</span><span class="sxs-lookup"><span data-stu-id="e6f73-112">What is a policy package?</span></span>

<span data-ttu-id="e6f73-113">ポリシーパッケージを使用すると、組織内の特定のユーザーのセットに対して許可または制限するチームの機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-113">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="e6f73-114">Teams の各ポリシーパッケージは、ユーザーロールをベースに設計されており、その役割で一般的なコラボレーションと通信のアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e6f73-114">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="e6f73-115">ポリシーパッケージでは、次の Teams ポリシーの種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6f73-115">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="e6f73-116">メッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="e6f73-116">Messaging policy</span></span>
- <span data-ttu-id="e6f73-117">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="e6f73-117">Meeting policy</span></span>
- <span data-ttu-id="e6f73-118">アプリセットアップポリシー</span><span class="sxs-lookup"><span data-stu-id="e6f73-118">App setup policy</span></span>
- <span data-ttu-id="e6f73-119">通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="e6f73-119">Calling policy</span></span>
- <span data-ttu-id="e6f73-120">ライブ イベント ポリシー</span><span class="sxs-lookup"><span data-stu-id="e6f73-120">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="e6f73-121">Teams に含まれるポリシーパッケージ</span><span class="sxs-lookup"><span data-stu-id="e6f73-121">Policy packages included in Teams</span></span>

<span data-ttu-id="e6f73-122">チームには現在、次のポリシーパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e6f73-122">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="e6f73-123">**パッケージ名**</span><span class="sxs-lookup"><span data-stu-id="e6f73-123">**Package name**</span></span>  |<span data-ttu-id="e6f73-124">**説明**</span><span class="sxs-lookup"><span data-stu-id="e6f73-124">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="e6f73-125">教育機関 (高等教育機関向け生徒)</span><span class="sxs-lookup"><span data-stu-id="e6f73-125">Education (Higher education student)</span></span>    |<span data-ttu-id="e6f73-126">高等教育機関向けの学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-126">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="e6f73-127">教育機関 (第1学校の学生)</span><span class="sxs-lookup"><span data-stu-id="e6f73-127">Education (Primary school student)</span></span>   |<span data-ttu-id="e6f73-128">主要な学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-128">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="e6f73-129">教育機関 (第2学校の学生)</span><span class="sxs-lookup"><span data-stu-id="e6f73-129">Education (Secondary school student)</span></span>    |<span data-ttu-id="e6f73-130">第2の学生に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-130">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="e6f73-131">教育機関 (教師)</span><span class="sxs-lookup"><span data-stu-id="e6f73-131">Education (Teacher)</span></span>    |<span data-ttu-id="e6f73-132">教師に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-132">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="e6f73-133">学歴 (リモート学習を使用した第1学校教師)</span><span class="sxs-lookup"><span data-stu-id="e6f73-133">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="e6f73-134">小学校教師に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="e6f73-134">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="e6f73-135">教育機関 (リモート学習を使った第1学校の学生)</span><span class="sxs-lookup"><span data-stu-id="e6f73-135">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="e6f73-136">小学生に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="e6f73-136">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="e6f73-137">Firstline manager</span><span class="sxs-lookup"><span data-stu-id="e6f73-137">Firstline manager</span></span> |<span data-ttu-id="e6f73-138">一連のポリシーを作成し、組織の Firstline Manager にそれらの設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-138">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span> |
|<span data-ttu-id="e6f73-139">Firstline worker</span><span class="sxs-lookup"><span data-stu-id="e6f73-139">Firstline worker</span></span> |<span data-ttu-id="e6f73-140">一連のポリシーを作成し、それらの設定を組織の Firstline Worker に適用します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-140">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span> |
|<span data-ttu-id="e6f73-141">医療診療員</span><span class="sxs-lookup"><span data-stu-id="e6f73-141">Healthcare clinical worker</span></span>  |<span data-ttu-id="e6f73-142">登録された看護師、料金の看護師、医師、ソーシャルワーカーなどの、チャット、通話、シフト管理、および会議へのフルアクセスを可能にする、一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-142">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="e6f73-143">医療情報の作業者</span><span class="sxs-lookup"><span data-stu-id="e6f73-143">Healthcare information worker</span></span>  |<span data-ttu-id="e6f73-144">IT 担当者、informatics 職員、財務担当者、コンプライアンス責任者、チャット、通話、会議へのフルアクセスなどの情報を提供する一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-144">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="e6f73-145">医療の治療室</span><span class="sxs-lookup"><span data-stu-id="e6f73-145">Healthcare patient room</span></span>  |<span data-ttu-id="e6f73-146">医療機関の患者の会議室に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-146">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="e6f73-147">中小規模企業のユーザー (ビジネス用ボイス)</span><span class="sxs-lookup"><span data-stu-id="e6f73-147">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="e6f73-148">ビジネス音声エクスペリエンス用のアプリを含むアプリセットアップポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-148">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="e6f73-149">中小規模企業のユーザー (ビジネス用ボイスのない)</span><span class="sxs-lookup"><span data-stu-id="e6f73-149">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="e6f73-150">中小規模のビジネスチームユーザー (非ビジネス用ボイス) に関連するアプリのセットアップポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-150">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="e6f73-151">公安責任者</span><span class="sxs-lookup"><span data-stu-id="e6f73-151">Public safety officer</span></span>   |<span data-ttu-id="e6f73-152">組織の公衆安全責任者に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-152">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="e6f73-153">今後のチームのリリースでポリシーパッケージを追加しますので、最新の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e6f73-153">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="e6f73-154">個々のポリシーには、ポリシーパッケージの名前が割り当てられているため、ポリシーパッケージにリンクされているポリシーを簡単に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-154">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="e6f73-155">たとえば、学校の教師に教育 (教師) ポリシーパッケージを割り当てると、Education_Teacher という名前のポリシーがパッケージ内の各ポリシーに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-155">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育機関 (教師) ポリシーパッケージのスクリーンショット](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="e6f73-157">カスタムポリシーパッケージ</span><span class="sxs-lookup"><span data-stu-id="e6f73-157">Custom policy packages</span></span>

<span data-ttu-id="e6f73-158">**この機能はプライベートプレビュー**</span><span class="sxs-lookup"><span data-stu-id="e6f73-158">**This feature is in private preview**</span></span>

<span data-ttu-id="e6f73-159">カスタムポリシーパッケージを使用すると、組織内で同様の役割を持つユーザーに独自のポリシーセットをバンドルすることができます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-159">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="e6f73-160">必要なポリシーの種類とポリシーを追加して、独自のポリシーパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-160">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="e6f73-161">新しいカスタムポリシーパッケージを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e6f73-161">To create a new custom policy package:</span></span>

1. <span data-ttu-id="e6f73-162">Microsoft Teams 管理センターの左のナビゲーションで、[ **ポリシーパッケージ** ] を選択し、[ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f73-162">In the left navigation of the Microsoft Teams admin center,  select **Policy packages** , and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="管理センターの [ポリシーパッケージ] ページの [追加] ボタンのスクリーンショット":::
2. <span data-ttu-id="e6f73-164">パッケージの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-164">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新しいカスタムポリシーパッケージの追加のスクリーンショット":::
3. <span data-ttu-id="e6f73-166">パッケージに含めるポリシーの種類とポリシー名を選びます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-166">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="e6f73-167">[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f73-167">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="e6f73-168">ポリシーパッケージの使用方法</span><span class="sxs-lookup"><span data-stu-id="e6f73-168">How to use policy packages</span></span>

<span data-ttu-id="e6f73-169">組織でポリシーパッケージを使用する方法については、次の表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e6f73-169">The following outlines how to use policy packages in your organization.</span></span>

![ポリシーパッケージの使用方法の概要](media/manage-policy-packages-overview.png)

- <span data-ttu-id="e6f73-171">**[表示](#view-the-settings-of-a-policy-in-a-policy-package)** : ポリシーパッケージ内のポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-171">**[View](#view-the-settings-of-a-policy-in-a-policy-package)** : View the policies in a policy package.</span></span> <span data-ttu-id="e6f73-172">次に、パッケージを割り当てる前に、パッケージ内の各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-172">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="e6f73-173">各設定を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e6f73-173">Make sure that you understand each setting.</span></span> <span data-ttu-id="e6f73-174">定義済みの値が組織に適しているかどうかを判断します。または、組織のニーズに基づいて、組織のニーズに応じて、制限を厳しくするか、厳しくする必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-174">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="e6f73-175">ポリシーが削除された場合でも、設定は表示できますが、設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e6f73-175">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="e6f73-176">ポリシーパッケージを割り当てるときに、削除されたポリシーが定義済みの設定で再作成されます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-176">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="e6f73-177">**[カスタマイズ](#customize-policies-in-a-policy-package)** : 組織のニーズに合わせてポリシーパッケージのポリシーの設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="e6f73-177">**[Customize](#customize-policies-in-a-policy-package)** : Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="e6f73-178">**[割り当て](#assign-a-policy-package)** : ポリシーパッケージをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-178">**[Assign](#assign-a-policy-package)** : Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="e6f73-179">また、パッケージの割り当て後に、ポリシーパッケージのポリシーの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-179">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="e6f73-180">ポリシー設定に加えた変更は、パッケージを割り当てられたユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-180">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="e6f73-181">Microsoft Teams 管理センターでポリシーパッケージを表示、割り当て、カスタマイズする方法の手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-181">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="e6f73-182">ポリシーパッケージ内のポリシーの設定を表示する</span><span class="sxs-lookup"><span data-stu-id="e6f73-182">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="e6f73-183">Microsoft Teams 管理センターの左のナビゲーションで、[ **ポリシーパッケージ** ] を選択し、パッケージ名の左側をクリックしてポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-183">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="e6f73-184">表示するポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f73-184">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="e6f73-185">ポリシーパッケージのポリシーをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="e6f73-185">Customize policies in a policy package</span></span>

<span data-ttu-id="e6f73-186">ポリシーの設定を編集するには、[ **ポリシーパッケージ** ] ページを使用するか、Microsoft Teams 管理センターの [ポリシー] ページに直接移動します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-186">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="e6f73-187">Microsoft Teams 管理センターの左側のナビゲーションで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e6f73-187">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="e6f73-188">[ **ポリシーパッケージ** ] をクリックし、パッケージ名の左側をクリックしてポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-188">Click **Policy packages** , and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="e6f73-189">[ポリシーの種類] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f73-189">Click the policy type.</span></span>  <span data-ttu-id="e6f73-190">たとえば、[ **メッセージングポリシー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f73-190">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="e6f73-191">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-191">Select the policy you want to edit.</span></span> <span data-ttu-id="e6f73-192">ポリシーパッケージにリンクされているポリシーは、ポリシーパッケージと同じ名前になっています。</span><span class="sxs-lookup"><span data-stu-id="e6f73-192">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="e6f73-193">必要な変更を加えて、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f73-193">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="e6f73-194">ポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6f73-194">Assign a policy package</span></span> 

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="e6f73-195">1人のユーザーにポリシーパッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6f73-195">Assign a policy package to one user</span></span>

1. <span data-ttu-id="e6f73-196">Microsoft Teams 管理センターの左側のナビゲーションで、 **[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f73-196">In the left navigation of the Microsoft Teams admin center, go to **Users** , and then click the user.</span></span>
2. <span data-ttu-id="e6f73-197">ユーザーのページで、[ **ポリシー** ] をクリックし、[ **ポリシーパッケージ** ] の横にある [ **編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f73-197">On the user's page, click **Policies** , and then next to **Policy package** , click **Edit**.</span></span>
3. <span data-ttu-id="e6f73-198">[ **ポリシーパッケージの割り当て** ] ウィンドウで、割り当てるパッケージを選択し、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f73-198">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="e6f73-199">ポリシーパッケージを複数のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6f73-199">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="e6f73-200">Microsoft Teams 管理センターの左のナビゲーションで、[ **ポリシーパッケージ** ] に移動し、パッケージ名の左側をクリックして割り当てるポリシーパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-200">In the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="e6f73-201">[ **ユーザーの管理** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f73-201">Click **Manage users**.</span></span>
3. <span data-ttu-id="e6f73-202">[ **ユーザーを管理する** ] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f73-202">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="e6f73-203">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-203">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="e6f73-204">ユーザーの追加が完了したら、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f73-204">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="e6f73-205">ポリシーパッケージをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6f73-205">Assign a policy package to a group</span></span>

<span data-ttu-id="e6f73-206">**この機能はプライベートプレビュー**</span><span class="sxs-lookup"><span data-stu-id="e6f73-206">**This feature is in private preview**</span></span>

<span data-ttu-id="e6f73-207">グループにポリシーパッケージを割り当てると、セキュリティグループや配布リストなど、複数のポリシーをユーザーのグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-207">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="e6f73-208">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-208">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="e6f73-209">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-209">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="e6f73-210">この方法は、最大5万ユーザーのグループに推奨されますが、大規模なグループでも動作します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-210">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="e6f73-211">詳細については、「 [ポリシーパッケージをグループに割り当てる](assign-policies.md#assign-a-policy-package-to-a-group)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6f73-211">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="e6f73-212">ポリシーパッケージを大規模なユーザー (バッチ) に割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6f73-212">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="e6f73-213">バッチポリシーパッケージの割り当てを使用して、一度に多くのユーザーにポリシーパッケージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-213">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="e6f73-214">[CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation)コマンドレットを使用して、ユーザーのバッチと、割り当てるポリシーパッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-214">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="e6f73-215">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-215">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="e6f73-216">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-216">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="e6f73-217">ユーザーは、オブジェクト Id、UPN、SIP アドレス、またはメールアドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-217">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="e6f73-218">詳細については、「 [ユーザーのバッチにポリシーパッケージを割り当てる](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6f73-218">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e6f73-219">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e6f73-219">Troubleshooting</span></span>

<span data-ttu-id="e6f73-220">**ポリシーパッケージを割り当てるときにエラーが表示される**</span><span class="sxs-lookup"><span data-stu-id="e6f73-220">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="e6f73-221">この問題は、パッケージ内の1つ以上のポリシーが正常に作成または適用されなかった場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="e6f73-221">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="e6f73-222">ポリシーパッケージをユーザーに割り当て直します。</span><span class="sxs-lookup"><span data-stu-id="e6f73-222">Reassign the policy package to your users.</span></span> <span data-ttu-id="e6f73-223">通常、操作を再試行すると、この問題は修正されます。</span><span class="sxs-lookup"><span data-stu-id="e6f73-223">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e6f73-224">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6f73-224">Related topics</span></span>

[<span data-ttu-id="e6f73-225">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6f73-225">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="e6f73-226">EDU 管理者の Teams ポリシーパッケージ</span><span class="sxs-lookup"><span data-stu-id="e6f73-226">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="e6f73-227">医療用の Teams ポリシーパッケージ</span><span class="sxs-lookup"><span data-stu-id="e6f73-227">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="e6f73-228">Government の Teams ポリシーパッケージ</span><span class="sxs-lookup"><span data-stu-id="e6f73-228">Teams policy packages for government</span></span>](policy-packages-gov.md)
