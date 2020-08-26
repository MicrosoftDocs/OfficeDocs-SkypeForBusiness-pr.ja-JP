---
title: EDU 管理者向け Microsoft Teams ポリシーおよびポリシーパッケージ
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Priority
search.appverid: MET150
description: 教育機関におけるポリシーや EDU 設定、および Microsoft Teams でポリシー パッケージを使用および管理する方法について説明します。
ms.openlocfilehash: cb5b2620ae014a65abd912b401af1587aceff0e6
ms.sourcegitcommit: 32023931b607542cffadef74383e3ecd47db4ab6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868706"
---
# <a name="teams-policies-and-policy-packages-for-education"></a><span data-ttu-id="09a88-103">境域機関向け Teams ポリシーおよびポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="09a88-103">Teams Policies and Policy Packages for Education</span></span>

> [!NOTE]
> <span data-ttu-id="09a88-104">Microsoft Teams のポリシーの大規模な事例については、「[Microsoft Teams でユーザーにポリシーを割り当てる](assign-policies.md)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="09a88-104">For the larger story on policies in Microsoft Teams, please review [Assign policies to your users in Microsoft Teams](assign-policies.md).</span></span>

<span data-ttu-id="09a88-105">この記事では、Teams 内のユーザーにポリシーを割り当てる複数の方法を説明していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09a88-105">It's important to note this article will cover multiple ways to assign policies to users in Teams.</span></span>

- <span data-ttu-id="09a88-106">個別のユーザーに手動で割り当てる。</span><span class="sxs-lookup"><span data-stu-id="09a88-106">Manual assign to individual users.</span></span>
- <span data-ttu-id="09a88-107">PowerShell を使用して複数のユーザーに一括で割り当てる。</span><span class="sxs-lookup"><span data-stu-id="09a88-107">Bulk assigning via PowerShell to multiple users.</span></span>
- <span data-ttu-id="09a88-108">個別のユーザーまたは複数のユーザーにポリシー パッケージを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="09a88-108">Assigning policy packages to individual or multiple users.</span></span>

<span data-ttu-id="09a88-109">これらのアプローチの長所と短所は、各教育機関の個別のニーズにより異なります。</span><span class="sxs-lookup"><span data-stu-id="09a88-109">The advantages and disadvantages of these approaches come down to the institution's individual needs.</span></span>

## <a name="admins-getting-started-with-microsoft-teams-policy-management"></a><span data-ttu-id="09a88-110">管理者: Microsoft Teams のポリシー管理の概要</span><span class="sxs-lookup"><span data-stu-id="09a88-110">Admins: Getting started with Microsoft Teams policy management</span></span>

<span data-ttu-id="09a88-111">Microsoft Teams の主な機能は、ユーザーが会議やライブイベントに移動したり、チャットしたり、通話を行ったり、アプリを使用したできるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="09a88-111">Microsoft Teams, at its core, is about users being able to do things like go to meetings or live events, chat, make calls, and use apps.</span></span> <span data-ttu-id="09a88-112">また、適切な Microsoft Teams 管理ポリシーを設定することは、Teams 内の学生に対して安全な学習環境を構築するための重要なステップです。</span><span class="sxs-lookup"><span data-stu-id="09a88-112">And setting the right Microsoft Teams admin policies is a critical step in creating a safe learning environment for students within Teams.</span></span> <span data-ttu-id="09a88-113">管理者は、ポリシーを使用して、教育機関のユーザーが利用できる Teams 機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-113">As an admin, you can use policies to control the Teams features that are available to users in your educational institute.</span></span>

<span data-ttu-id="09a88-114">Microsoft Teams 内のポリシー領域の一覧は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="09a88-114">Here's a list of the policy areas you will find in Microsoft Teams:</span></span>

- <span data-ttu-id="09a88-115">会議</span><span class="sxs-lookup"><span data-stu-id="09a88-115">Meetings</span></span>
- <span data-ttu-id="09a88-116">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="09a88-116">Live events</span></span>
- <span data-ttu-id="09a88-117">通話</span><span class="sxs-lookup"><span data-stu-id="09a88-117">Calling</span></span>
- <span data-ttu-id="09a88-118">メッセージング</span><span class="sxs-lookup"><span data-stu-id="09a88-118">Messaging</span></span>
- <span data-ttu-id="09a88-119">Teams</span><span class="sxs-lookup"><span data-stu-id="09a88-119">Teams</span></span>
- <span data-ttu-id="09a88-120">アプリのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="09a88-120">App permissions</span></span>

:::image type="content" source="media/edu-admin-center-users.png" alt-text="ポリシーが適用されているユーザーのスクリーンショット。":::

<span data-ttu-id="09a88-122">管理者の資格情報でサインインすることにより、[Microsoft Teams 管理センター](https://admin.teams.microsoft.com)で、Teams のすべてのポリシーを簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-122">You can easily manage all Teams policies in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) by signing in with your admin credentials.</span></span>

### <a name="where-to-find-microsoft-teams-policies"></a><span data-ttu-id="09a88-123">Microsoft Teams ポリシーへのアクセス方法</span><span class="sxs-lookup"><span data-stu-id="09a88-123">Where to find Microsoft Teams policies</span></span>

<span data-ttu-id="09a88-124">Teams 管理センターにログインすると、Teams 管理センターの左側のナビゲーションにある [ポリシー] オプションをクリックして、管理する必要がある Teams のあらゆる領域のポリシー設定に移動できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-124">Once you've logged into the Teams admin center, you'll be able to go to the policy settings for any area of Teams you need to manage, by clicking on the policy option in the left hand navigation of the Teams admin center.</span></span> <span data-ttu-id="09a88-125">メッセージング ポリシーの場所のスクリーンショットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="09a88-125">We've included a screenshot of the location of the messaging policies.</span></span>

:::image type="content" source="media/edu-messaging-policies.png" alt-text="Teams 管理センター内のメッセージング ポリシーの場所。":::

### <a name="how-to-create-and-update-a-policy-definition"></a><span data-ttu-id="09a88-127">ポリシー定義を作成して更新する方法</span><span class="sxs-lookup"><span data-stu-id="09a88-127">How to create and update a policy definition</span></span>

<span data-ttu-id="09a88-128">ユーザーにポリシーを割り当てる前に、Teams を使って、各機能領域のポリシー定義を追加および作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-128">Before you assign policies to your users, you need to first add and create your policy definitions for each capability area with Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="09a88-129">学生と教師には、異なるポリシー定義を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09a88-129">We recommend that you set different policy definitions for your students and educators.</span></span>

<span data-ttu-id="09a88-130">既定では、すべての新しいユーザー (学生または教師) に各機能領域に対してグローバル (組織全体の既定) ポリシー定義が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="09a88-130">By default, every new user (student or educator) will be assigned the Global (Org-wide default) policy definition for each capability area.</span></span> <span data-ttu-id="09a88-131">次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09a88-131">We recommend you follow these steps:</span></span>

1. <span data-ttu-id="09a88-132">Teams の各機能領域に対してカスタム ポリシー定義を作成し、教師に割り当てます (この手順を実行しないと、教師に独自のポリシーを割り当てるまで、グローバル ポリシーを変更すると、教師を制限することになります)。</span><span class="sxs-lookup"><span data-stu-id="09a88-132">Create a custom policy definition for each Teams capability area that can then be assigned to your educators (without this, any changes you make to the Global policy will restrict educators until they have their own policy).</span></span>

1. <span data-ttu-id="09a88-133">この新しいポリシー定義に教師を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="09a88-133">Assign your educators to this new policy definition.</span></span>

1. <span data-ttu-id="09a88-134">グローバル (組織全体の既定) ポリシー定義を更新し、学生に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="09a88-134">Update the Global (Org-wide default) policy definition, then assign it to your students.</span></span>

<span data-ttu-id="09a88-135">ポリシー定義を作成または編集するには、作業するポリシー機能領域 (メッセージング ポリシーなど) に移動します。</span><span class="sxs-lookup"><span data-stu-id="09a88-135">To create or edit policy definitions, go to the policy capability area you want to work in (for example, Messaging policies).</span></span> <span data-ttu-id="09a88-136">新しいカスタム ポリシーの定義を作成する場合は、**[追加]** を選択します (教師用に作成するカスタム ポリシー定義を対象にします)。</span><span class="sxs-lookup"><span data-stu-id="09a88-136">Select **Add** if you want to create a new custom policy definition (which you'll do for the custom policy definition you create for educators).</span></span> <span data-ttu-id="09a88-137">それ以外の場合、既存のポリシー定義を変更するには、**[編集]** を選択します (学生用のグローバル ポリシーを更新する場合に実行します)。</span><span class="sxs-lookup"><span data-stu-id="09a88-137">Otherwise, to change an existing policy definition, then select **Edit** (which will be what you do if you choose to update the Global policy for students).</span></span>

:::image type="content" source="media/edu-messaging-policies-add-closeup.png" alt-text="[追加] ボタンを表示した状態での [メッセージング ポリシー] セクションのクローズアップ。":::

<span data-ttu-id="09a88-139">ポリシー定義を追加するか編集するかを選択したどうかにかかわらず、このポリシー領域に関連付けられているすべてのポリシー オプションが一覧表示されるビューに移動します。</span><span class="sxs-lookup"><span data-stu-id="09a88-139">Whether you choose to add or edit a policy definition, you're brought to a view that lists all the policy options related to this policy area.</span></span> <span data-ttu-id="09a88-140">このリストを使用して、ポリシー定義に設定する値を選択します。</span><span class="sxs-lookup"><span data-stu-id="09a88-140">Use this list to select what values you want set in your policy definition.</span></span>

![選んだポリシー領域に関連付けられているポリシー オプションを含むページ。](media/edu-global-policy-definition.png)

> [!IMPORTANT]
> <span data-ttu-id="09a88-142">ページから移動する前に、**[保存]** を必ず選択してください。</span><span class="sxs-lookup"><span data-stu-id="09a88-142">Don’t forget to select **Save** before you leave the page.</span></span>

### <a name="how-to-assign-a-policy-definition-to-a-user"></a><span data-ttu-id="09a88-143">ユーザーにポリシー定義を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="09a88-143">How to assign a policy definition to a user</span></span>

> [!NOTE]
> <span data-ttu-id="09a88-144">ポリシー定義を割り当てると、すべてのユーザーとクライアントに反映されるのにしばらく時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-144">Assigning a policy definition may take a while to propagate out to all the users and clients.</span></span> <span data-ttu-id="09a88-145">Azure/M365 にユーザー アカウントを初めて作成するとき、教育機関に新しい学生が参加するときに、この操作を行うことが必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-145">You might want to do this when the user accounts are first created in Azure/M365, and whenever a new student joins the educational institute.</span></span>

<span data-ttu-id="09a88-146">ポリシー定義を作成または更新した後、[ポリシー] ページの **[ユーザーの管理]** を選択し、希望のユーザーを検索して、ポリシーを割り当てることにより、ユーザーにポリシー定義を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="09a88-146">Once your policy definition is created or updated, you can assign it to a user by selecting **Manage users** in policy page, searching for the desired user then applying the policy.</span></span>

![[メッセージング ポリシー] ページの上部の右側にある [ユーザー] パネルを管理します。](media/edu-manage-users-pane.png)

<span data-ttu-id="09a88-148">また、[ユーザー] に移動し、ポリシーを更新するユーザーを選択し、[ポリシー] を選択してから [編集] を選択することにより、ユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="09a88-148">You can also assign a policy to a user by navigating to Users, selecting the user you wish to update policies for, selecting Policies, then Edit.</span></span> <span data-ttu-id="09a88-149">ここから、各機能領域に対してユーザーに割り当てるポリシー定義を選択できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-149">From there, you can select the policy definition you’d like to use assign to the user for each capability area.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="09a88-150">お客様が大規模な教育機関の一員である場合、Microsoft Teams 管理ポータルを使用して各ユーザーのポリシーを設定するのが難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-150">If you're part of a large educational institute, using the Microsoft Teams admin portal experience to set policies for each user may be difficult.</span></span> <span data-ttu-id="09a88-151">このような場合は、PowerShell を使用してポリシーを一括で割り当てる方が適切です。</span><span class="sxs-lookup"><span data-stu-id="09a88-151">It'll be better for you to assign policies in batches via PowerShell.</span></span> <span data-ttu-id="09a88-152">[教育機関の大規模なユーザーにポリシーを割り当てる](batch-group-policy-assignment-edu.md)方法については、EDU に固有の情報があります。この情報を必要とする場合は、ポリシー パッケージの以下のセクションをご確認ください。これは、ユーザーの大規模グループに対してポリシーや設定を管理するための別な優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="09a88-152">We have some EDU-specific information on how to [Assign policies to large sets of users in your educational institute](batch-group-policy-assignment-edu.md) if you need it, and you can also check out the section below on policy packages, which are another great way to manage policies and settings for large groups of users.</span></span>

![[割り当てられているポリシー] ページの右側にある [ユーザー ポリシーの編集] ウィンドウ。](media/edu-edit-user-policies-pane.png)

### <a name="policy-packages-in-microsoft-teams"></a><span data-ttu-id="09a88-154">Microsoft Teams のポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="09a88-154">Policy packages in Microsoft Teams</span></span>

<span data-ttu-id="09a88-155">Teams 内のポリシー パッケージは、上記で説明したように事前に定義されたポリシーおよびポリシー設定を収集し、それらを教育機関内の同様の役割を持つユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="09a88-155">A policy package in Teams collects predefined policies and policy settings that you learned about outlined above, and assigns them to users with similar roles in your institution.</span></span> <span data-ttu-id="09a88-156">ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="09a88-156">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="09a88-157">通常の方法では、各ユーザーにポリシーパッケージを割り当て、そのユーザー グループのニーズに合わせて、各パッケージのポリシーを再定義します。</span><span class="sxs-lookup"><span data-stu-id="09a88-157">In normal practice, you assign each of your users a policy package, and  redefine the policies in each package as needed to suit the needs of that user group.</span></span> <span data-ttu-id="09a88-158">パッケージの設定を更新すると、そのパッケージに割り当てられているすべてのユーザーが一括更新として変更されます。</span><span class="sxs-lookup"><span data-stu-id="09a88-158">When you update settings in a package, all users assigned to that package are changed as a bulk update.</span></span>

<span data-ttu-id="09a88-159">一般に、教育機関には、学生の年齢や成熟度によって異なる固有のニーズを持つ多くのユーザーが存在します。</span><span class="sxs-lookup"><span data-stu-id="09a88-159">Educational institutions in general have many users with unique needs, depending partly on the age and maturity of the students.</span></span> <span data-ttu-id="09a88-160">たとえば、教師やスタッフが Microsoft Teams にフルアクセスできるようにする一方で、安全で集中できる学習環境を構築するために、学生に対する Microsoft Teams の機能を制限したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-160">For example, you may want to grant educators and staff full access to Microsoft Teams, but want to limit Microsoft Teams capabilities for students to encourage a safe and focused learning environment.</span></span> <span data-ttu-id="09a88-161">教育機関コミュニティにおける異なるコーホートのニーズに基づいて、ポリシー パッケージを使用して設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-161">You can use policy packages to tailor settings based on the needs of different cohorts in your educational institute community.</span></span>

> [!NOTE]
> <span data-ttu-id="09a88-162">詳細については、「[Microsoft Teams でポリシー パッケージを管理する](manage-policy-packages.md)」をご確認ください。1 人のユーザーにパッケージを割り当てる方法、最大 5000 人のユーザーにパッケージを一括で割り当てる方法、各パッケージに関連付けられたポリシーの管理と更新を行う方法を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="09a88-162">For more reading, you can check out [Manage policy packages in Microsoft Teams](manage-policy-packages.md) for step by step guidance on assigning single users a package, assigning packages in bulk to up to 5000 users, and managing and updating the policies linked to each package.</span></span>

<span data-ttu-id="09a88-163">この記事で前述したポリシー一覧と同様に、ポリシーパッケージでは、次のようなポリシーが事前に定義されています。</span><span class="sxs-lookup"><span data-stu-id="09a88-163">Just like the policy list earlier in this article, policy packages predefine policies for:</span></span>

- <span data-ttu-id="09a88-164">会議</span><span class="sxs-lookup"><span data-stu-id="09a88-164">Meetings</span></span>
- <span data-ttu-id="09a88-165">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="09a88-165">Live events</span></span>
- <span data-ttu-id="09a88-166">通話</span><span class="sxs-lookup"><span data-stu-id="09a88-166">Calling</span></span>
- <span data-ttu-id="09a88-167">メッセージング</span><span class="sxs-lookup"><span data-stu-id="09a88-167">Messaging</span></span>
- <span data-ttu-id="09a88-168">Teams</span><span class="sxs-lookup"><span data-stu-id="09a88-168">Teams</span></span>
- <span data-ttu-id="09a88-169">アプリのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="09a88-169">App permissions</span></span>

<span data-ttu-id="09a88-170">Microsoft Teams には現在、次のポリシー パッケージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09a88-170">Microsoft Teams currently includes the following policy packages:</span></span>

|<span data-ttu-id="09a88-171">Microsoft Teams 管理センターで一覧表示されるパッケージ名</span><span class="sxs-lookup"><span data-stu-id="09a88-171">Package name listed in Microsoft Teams Admin center</span></span> |<span data-ttu-id="09a88-172">以下の目的での使用に最適です</span><span class="sxs-lookup"><span data-stu-id="09a88-172">Best used for</span></span>  |<span data-ttu-id="09a88-173">説明</span><span class="sxs-lookup"><span data-stu-id="09a88-173">Description</span></span> |
|:--- |:--- |:--- |
|<span data-ttu-id="09a88-174">**Education_Teacher**</span><span class="sxs-lookup"><span data-stu-id="09a88-174">**Education_Teacher**</span></span>| <span data-ttu-id="09a88-175">教師およびスタッフ</span><span class="sxs-lookup"><span data-stu-id="09a88-175">Educators and staff</span></span>| <span data-ttu-id="09a88-176">この一連のポリシーおよびポリシー設定を使用して、Microsoft Teams を通して、組織内の教師およびスタッフがチャット、通話、会議にフルアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="09a88-176">Use this set of policies and policy settings to grant educators and staff within your organization full access to chat, calling and meetings through Microsoft Teams.</span></span> |
|<span data-ttu-id="09a88-177">**Education_PrimaryStudent**</span><span class="sxs-lookup"><span data-stu-id="09a88-177">**Education_PrimaryStudent**</span></span>| <span data-ttu-id="09a88-178">小学生</span><span class="sxs-lookup"><span data-stu-id="09a88-178">Primary school aged students</span></span>  | <span data-ttu-id="09a88-179">教育機関における小学生の場合、Microsoft Teams 内での更なる制限が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-179">Younger, primary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="09a88-180">この一連のポリシーおよびポリシー設定を使用して、会議の作成と管理、チャット管理、個人的な通話などの機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="09a88-180">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="09a88-181">**Education_SecondaryStudent**</span><span class="sxs-lookup"><span data-stu-id="09a88-181">**Education_SecondaryStudent**</span></span>| <span data-ttu-id="09a88-182">中学生</span><span class="sxs-lookup"><span data-stu-id="09a88-182">Secondary school aged students</span></span> | <span data-ttu-id="09a88-183">教育機関における中学生の場合、Microsoft Teams 内での更なる制限が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-183">Secondary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="09a88-184">この一連のポリシーおよびポリシー設定を使用して、会議の作成と管理、チャット管理、個人的な通話などの機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="09a88-184">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="09a88-185">**Education_HigherEducationStudent**</span><span class="sxs-lookup"><span data-stu-id="09a88-185">**Education_HigherEducationStudent**</span></span>| <span data-ttu-id="09a88-186">高校生</span><span class="sxs-lookup"><span data-stu-id="09a88-186">Higher education students</span></span> | <span data-ttu-id="09a88-187">教育機関における高校生の場合、小中学生に比べて制限は少なくなりますが、ある程度の制限が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-187">Higher education students within your intuition may need fewer limits than younger students, but some limitations may be recommended.</span></span> <span data-ttu-id="09a88-188">この一連のポリシーおよびポリシー設定のセットを使用して、組織内でのチャット、通話、会議へのアクセス権を与えることができます。ただし、学生が外部参加者と共に Microsoft Teams を使用する方法を制限します。</span><span class="sxs-lookup"><span data-stu-id="09a88-188">You can use this set of policies and policy settings to give access to chat, calling, and meetings within your  organization, but limit how your students use Microsoft Teams with external participants.</span></span> |
|<span data-ttu-id="09a88-189">**Education_PrimaryTeacher_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="09a88-189">**Education_PrimaryTeacher_RemoteLearning**</span></span>| <span data-ttu-id="09a88-190">教師およびスタッフ</span><span class="sxs-lookup"><span data-stu-id="09a88-190">Educators and staff</span></span> | <span data-ttu-id="09a88-191">小学校教師に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="09a88-191">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span> |
|<span data-ttu-id="09a88-192">**Education_PrimaryStudent_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="09a88-192">**Education_PrimaryStudent_RemoteLearning**</span></span>| <span data-ttu-id="09a88-193">小学生</span><span class="sxs-lookup"><span data-stu-id="09a88-193">Primary school aged students</span></span>| <span data-ttu-id="09a88-194">小学生に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="09a88-194">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>
|||

:::image type="content" source="media/edu-policy-packages-list.png" alt-text="ポリシー パッケージ ページと選択するポリシーパッケージの一覧。":::

<span data-ttu-id="09a88-196">ポリシーパッケージにリンクされているポリシーを容易に識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。</span><span class="sxs-lookup"><span data-stu-id="09a88-196">Each individual policy is given the name of the policy package so you can easily identify policies linked to a policy package.</span></span> <span data-ttu-id="09a88-197">たとえば、教育機関の教師に Education_Teacher ポリシー パッケージを割り当てると、パッケージ内の各ポリシーに対して Education_Teacher という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="09a88-197">For example, when you assign the Education_Teacher policy package to educators in your educational institution, a policy named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher ポリシー パッケージのスクリーンショット](media/policy-packages-education_teacher.png)

> [!NOTE]
> <span data-ttu-id="09a88-199">教師と管理サポート スタッフが異なるポリシーを必要としていると判断した場合は、既存のパッケージを転用できます。現在使用していないパッケージを特定し、そのグループに合わせて設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="09a88-199">If you decide that educators and administrative support staff need different policies, you can repurpose an existing package: identify a package you aren't currently using and change the settings to be appropriate for that group.</span></span> <span data-ttu-id="09a88-200">どのグループにどのパッケージがあるかを確認することが必要になる場合がありますが、これはパッケージの転用における唯一の障害です。</span><span class="sxs-lookup"><span data-stu-id="09a88-200">You might have to make a note to yourself which group has which package, but that's the only impediment to repurposing a package.</span></span>

## <a name="policies-that-should-be-assigned-for-student-safety"></a><span data-ttu-id="09a88-201">学生の安全を確保するために割り当てるべきポリシー</span><span class="sxs-lookup"><span data-stu-id="09a88-201">Policies that should be assigned for student safety</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="09a88-202">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="09a88-202">Meeting policies</span></span>

#### <a name="turn-off-the-ability-to-create-and-start-meetings"></a><span data-ttu-id="09a88-203">会議を作成および開始する機能をオフにする</span><span class="sxs-lookup"><span data-stu-id="09a88-203">Turn off the ability to create and start meetings</span></span>

> [!NOTE]
> <span data-ttu-id="09a88-204">現在、テナントのこの機能に気付かない場合があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-204">You may not notice this functionality in your tenant right now.</span></span> <span data-ttu-id="09a88-205">それは、現在この機能がロールアウトされているためです。すべてのテナントにロールアウトされると、すべてのユーザーが利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="09a88-205">That's because this feature is currently being rolled out, and will be available to all users once it's been rolled out to all tenants.</span></span> <span data-ttu-id="09a88-206">詳細については、「[チーム ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=63355)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09a88-206">Please see the [Teams Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=63355) for more information.</span></span>

<span data-ttu-id="09a88-207">学生が会議を無断でスケジュールすることができないようにするために、会議ポリシーで、次のような全般設定を使用して、会議作成機能を**オフ**に設定します。</span><span class="sxs-lookup"><span data-stu-id="09a88-207">To ensure that students can’t schedule a meeting to communicate unattended, in meeting policies set to **Off** meeting creation capabilities through these General settings:</span></span>

- <span data-ttu-id="09a88-208">**チャネルで今すぐ会議を許可する**: オフ</span><span class="sxs-lookup"><span data-stu-id="09a88-208">**Allow Meet now in channels**: Off</span></span>

- <span data-ttu-id="09a88-209">**Outlook アドインを許可する**: オフ</span><span class="sxs-lookup"><span data-stu-id="09a88-209">**Allow the Outlook add-in**: Off</span></span>

- <span data-ttu-id="09a88-210">**チャネルの会議スケジュールを許可する**: オフ</span><span class="sxs-lookup"><span data-stu-id="09a88-210">**Allow channel meeting scheduling**: Off</span></span>

- <span data-ttu-id="09a88-211">**プライベート会議のスケジュールを許可する**: オフ</span><span class="sxs-lookup"><span data-stu-id="09a88-211">**Allow scheduling private meetings**: Off</span></span>

  ![リモート学習における学生教育を全般セクションと共に表示 (ここではすべてのオプションがオフになっています)。](media/edu-policy-list-a.png)

- <span data-ttu-id="09a88-213">同じページにある [会議の参加者とゲスト] セクションで、次のようにします:</span><span class="sxs-lookup"><span data-stu-id="09a88-213">And on the same page, in the Participants and Guests in meeting section:</span></span>

  - <span data-ttu-id="09a88-214">**プライベート会議で "今すぐ会議" を許可する**: オフ</span><span class="sxs-lookup"><span data-stu-id="09a88-214">**Allow Meet now in private meetings**: Off</span></span>
  - <span data-ttu-id="09a88-215">**会議でチャットを許可する**: 無効</span><span class="sxs-lookup"><span data-stu-id="09a88-215">**Allow chat in meetings**: Disabled</span></span>

  ![参加者とゲストセクション ([プライベート会議で "今すぐ会議" を許可する] オプションが [オフ] に設定されています)。](media/edu-participants-and-guests.png)

<span data-ttu-id="09a88-217">学生に対し、**[チャネルで "今すぐ会議" を許可する]**、**[チャネルミーティングのスケジュールを許可する]**、**[プライベート会議のスケジュールを許可する]**、**[プライベート会議で "今すぐ会議"]** をオフにすることで、学生が主催者として会議をスケジュールしないようにするだけでなく、次のような教育の安全対策も提供しています:</span><span class="sxs-lookup"><span data-stu-id="09a88-217">Turning off **Allow Meet now in channels**, **Allow channel meeting scheduling**, **Allow scheduling private meetings**, and **Meet now in private meetings** for students not only blocks students from scheduling a meeting as the organizer, they also provide the following safety measures for education:</span></span>

- <span data-ttu-id="09a88-218">学生が教師の前に会議に参加しようとすると、Teams アプリの最新バージョンでは会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="09a88-218">If students attempt to join the meeting before the educator, they won't be able to join the meeting in the latest version of the Teams app.</span></span>

- <span data-ttu-id="09a88-219">会議の作成はすべてのユーザーとすべてのライセンスに適用されますが、上記の会議参加ブロックの安全対策は、ユーザーのライセンスの種類に基づいて、Teams 内の教育機関のお客様にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="09a88-219">Although meeting creation applies to any users and any licenses, the safety measures on meeting join block described above apply only to education customers in Teams based on the users’ license type.</span></span>

<span data-ttu-id="09a88-220">ここに、会議の作成に関する各ポリシーのロジックを説明した表を示します。</span><span class="sxs-lookup"><span data-stu-id="09a88-220">Here is a table to describe the logic for each meeting creation policy:</span></span>

| <span data-ttu-id="09a88-221">会議の作成ポリシー</span><span class="sxs-lookup"><span data-stu-id="09a88-221">Meeting creation policy</span></span> | <span data-ttu-id="09a88-222">会議を作成する</span><span class="sxs-lookup"><span data-stu-id="09a88-222">Create a meeting</span></span> | <span data-ttu-id="09a88-223">参加者がいない会議を開始する</span><span class="sxs-lookup"><span data-stu-id="09a88-223">Start a meeting unattended</span></span> | <span data-ttu-id="09a88-224">参加時にロビーをバイパスする</span><span class="sxs-lookup"><span data-stu-id="09a88-224">Bypass lobby when joining</span></span> | <span data-ttu-id="09a88-225">会議を終了する</span><span class="sxs-lookup"><span data-stu-id="09a88-225">End the meeting</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="09a88-226">**オン (例: 教師)**</span><span class="sxs-lookup"><span data-stu-id="09a88-226">**On (e.g. educator)**</span></span> | <span data-ttu-id="09a88-227">はい</span><span class="sxs-lookup"><span data-stu-id="09a88-227">Yes</span></span> | <span data-ttu-id="09a88-228">はい</span><span class="sxs-lookup"><span data-stu-id="09a88-228">Yes</span></span> | <span data-ttu-id="09a88-229">[会議オプション](https://go.microsoft.com/fwlink/?linkid=2093366) によって決定</span><span class="sxs-lookup"><span data-stu-id="09a88-229">Determined by [meeting options](https://go.microsoft.com/fwlink/?linkid=2093366)</span></span> | <span data-ttu-id="09a88-230">はい、開催者として</span><span class="sxs-lookup"><span data-stu-id="09a88-230">Yes, as organizer</span></span>
| <span data-ttu-id="09a88-231">**オフ (例: 学生)**</span><span class="sxs-lookup"><span data-stu-id="09a88-231">**Off (e.g. student)**</span></span> | <span data-ttu-id="09a88-232">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a88-232">No</span></span> | <span data-ttu-id="09a88-233">いいえ\*\*</span><span class="sxs-lookup"><span data-stu-id="09a88-233">No\*\*</span></span> | <span data-ttu-id="09a88-234">[会議オプション](https://go.microsoft.com/fwlink/?linkid=2093366) によって決定</span><span class="sxs-lookup"><span data-stu-id="09a88-234">Determined by [meeting options](https://go.microsoft.com/fwlink/?linkid=2093366)</span></span> | <span data-ttu-id="09a88-235">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a88-235">No</span></span>

> [!NOTE]
> <span data-ttu-id="09a88-236">\*\* これは、EDU ライセンス付与済みのユーザーにのみ適用され、会議、チャネル会議、インスタントの会議、インスタントのチャネル会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="09a88-236">\*\* This applies to EDU licensed users only and applies to meetings, channel meetings, instant meetings, and instant channel meetings.</span></span>

<span data-ttu-id="09a88-237">(チャネルからスケジュールされていない会議、またはチャネルで今すぐ会議において) **[会議でチャットを許可する]** ポリシーを [無効] に変更し、学生がその間会議のスケジュールを設定できないようにし、教師にこのポリシーを有効にすると、学生は教師が会議に参加する前も、会議後も、チャットすることはできません。</span><span class="sxs-lookup"><span data-stu-id="09a88-237">When you change the **Allow chat in meetings** policy to disabled and block students from scheduling meetings from above while and keep this policy on for educators (for the meetings that are not scheduled from a channel or meet now in a channel), students won't be able to chat before the educator joins the meeting, nor after the meeting.</span></span> <span data-ttu-id="09a88-238">会議の前、会議中、会議後もチャットの履歴を表示できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-238">They will still be able to see the chat history before, during, and after the meeting.</span></span> <span data-ttu-id="09a88-239">たとえば、会議が記録された場合は、教師からのメッセージまたは会議の記録リンクを表示できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-239">As an example, they'll be able to see messages from the teacher, or the meeting recording link, if the meeting was recorded.</span></span>

<span data-ttu-id="09a88-240">学生と教師の両方に **[会議でチャットを許可する]** ポリシーを無効にしている場合、会議のチャット ウィンドウでチャットすることはできません。</span><span class="sxs-lookup"><span data-stu-id="09a88-240">If both students and educators have the **Allow chat in meetings** policy turned off, no one will be able to chat in the meeting chat window.</span></span> <span data-ttu-id="09a88-241">上記の、会議のチャット制限の安全対策は、ユーザーのライセンスの種類に基づいて、Teams 内の教育機関のお客様にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="09a88-241">The safety measure on meeting chat restriction described above only applies to education customers in Teams based on users’ license type.</span></span>

<span data-ttu-id="09a88-242">ここに、会議でのチャットの許可について説明した表を示します。</span><span class="sxs-lookup"><span data-stu-id="09a88-242">Here is a table to describe the logic for allow chat in meetings:</span></span>

| <span data-ttu-id="09a88-243">「会議でチャットを許可する」のポリシー</span><span class="sxs-lookup"><span data-stu-id="09a88-243">‘Allow chat in meetings’ policy</span></span> | <span data-ttu-id="09a88-244">チャット履歴をいつでも表示する</span><span class="sxs-lookup"><span data-stu-id="09a88-244">See chat history anytime</span></span> | <span data-ttu-id="09a88-245">会議中にメッセージを投稿する</span><span class="sxs-lookup"><span data-stu-id="09a88-245">Post messages during the meeting</span></span> | <span data-ttu-id="09a88-246">会議の開始前や開始後にメッセージを投稿する</span><span class="sxs-lookup"><span data-stu-id="09a88-246">Post messages before or after the meeting</span></span> |
| --- | --- | --- | --- | 
| <span data-ttu-id="09a88-247">**すべての人に対してオン**</span><span class="sxs-lookup"><span data-stu-id="09a88-247">**On for all**</span></span> | <span data-ttu-id="09a88-248">はい</span><span class="sxs-lookup"><span data-stu-id="09a88-248">Yes</span></span> | <span data-ttu-id="09a88-249">はい</span><span class="sxs-lookup"><span data-stu-id="09a88-249">Yes</span></span> | <span data-ttu-id="09a88-250">はい</span><span class="sxs-lookup"><span data-stu-id="09a88-250">Yes</span></span> |
| <span data-ttu-id="09a88-251">**すべての人に対してオフ**</span><span class="sxs-lookup"><span data-stu-id="09a88-251">**Off for all**</span></span> | <span data-ttu-id="09a88-252">該当なし</span><span class="sxs-lookup"><span data-stu-id="09a88-252">N/A</span></span> | <span data-ttu-id="09a88-253">該当なし</span><span class="sxs-lookup"><span data-stu-id="09a88-253">N/A</span></span> | <span data-ttu-id="09a88-254">該当なし</span><span class="sxs-lookup"><span data-stu-id="09a88-254">N/A</span></span> |
| <span data-ttu-id="09a88-255">**教師に対してオン、学生に対してオフ**</span><span class="sxs-lookup"><span data-stu-id="09a88-255">**On for educators and Off for students**</span></span> | <span data-ttu-id="09a88-256">教師: はい</span><span class="sxs-lookup"><span data-stu-id="09a88-256">Educator: Yes</span></span><br><span data-ttu-id="09a88-257">生徒: はい</span><span class="sxs-lookup"><span data-stu-id="09a88-257">Student Yes</span></span> | <span data-ttu-id="09a88-258">教師: はい</span><span class="sxs-lookup"><span data-stu-id="09a88-258">Educator: Yes</span></span><br><span data-ttu-id="09a88-259">生徒: はい</span><span class="sxs-lookup"><span data-stu-id="09a88-259">Student Yes</span></span> | <span data-ttu-id="09a88-260">教師: はい</span><span class="sxs-lookup"><span data-stu-id="09a88-260">Educator: Yes</span></span><br><span data-ttu-id="09a88-261">生徒: いいえ\*\*</span><span class="sxs-lookup"><span data-stu-id="09a88-261">Student No\*\*</span></span> | 

> [!NOTE]
> <span data-ttu-id="09a88-262">\*\* これは、EDU ライセンス付与済みのユーザーにのみ適用され、会議とインスタントの会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="09a88-262">\*\* This applies to EDU licensed users only and applies to meetings and instant meetings.</span></span> <span data-ttu-id="09a88-263">チャネル会議やインスタントのチャネル会議には適用されません。</span><span class="sxs-lookup"><span data-stu-id="09a88-263">It does not apply to any channel meetings nor instant channel meetings.</span></span>

#### <a name="control-whether-or-not-students-can-share-their-videos-during-calls-and-meetings"></a><span data-ttu-id="09a88-264">学生が通話や会議中にビデオを共有できるかどうかを制御する</span><span class="sxs-lookup"><span data-stu-id="09a88-264">Control whether or not students can share their videos during calls and meetings</span></span>

<span data-ttu-id="09a88-265">[会議ポリシー] セクションで、学生に設定した音声の値や視覚的な値が教育機関のガイドライン、および学生、教師、保護者の要望に沿っていることを確認します (**[クラウド記録を許可する]** を除き、**[オフ]** に設定することをお勧めします)。 </span><span class="sxs-lookup"><span data-stu-id="09a88-265">In the meeting policies section, ensure that the Audio and visual values you set for your students aligns to your educational institution’s guidelines, as well as the desires of students, educators, and parents and guardians (With the exception of **Allow cloud recording**, which we recommend be set to **Off**).</span></span>

<span data-ttu-id="09a88-266">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="09a88-266">The options here:</span></span>

- <span data-ttu-id="09a88-267">**文字起こしを許可する**: オフ/オン</span><span class="sxs-lookup"><span data-stu-id="09a88-267">**Allow transcription**: Off/On</span></span>
- <span data-ttu-id="09a88-268">**クラウド記録を許可する**: **オフ**</span><span class="sxs-lookup"><span data-stu-id="09a88-268">**Allow cloud recording**: **Off**</span></span>
- <span data-ttu-id="09a88-269">**IP ビデオを許可する**: オフ/オン</span><span class="sxs-lookup"><span data-stu-id="09a88-269">**Allow IP Video**: Off/On</span></span>

:::image type="content" source="media/edu-policy-list-b.png" alt-text="リモート学習における学生教育 (ビデオ オプションと共に表示)。":::

### <a name="live-events-policies"></a><span data-ttu-id="09a88-271">ライブ イベント ポリシー</span><span class="sxs-lookup"><span data-stu-id="09a88-271">Live events policies</span></span>

#### <a name="turn-off-the-ability-to-create-and-start-live-events"></a><span data-ttu-id="09a88-272">ライブ イベントを作成および開始する機能をオフにする</span><span class="sxs-lookup"><span data-stu-id="09a88-272">Turn off the ability to create and start live events</span></span>

<span data-ttu-id="09a88-273">学生がライブ イベントを無断でスケジュールできないようにするために、学生に対する **[スケジュールを許可する]** ポリシーを **[オフ]** に設定して無効にします。</span><span class="sxs-lookup"><span data-stu-id="09a88-273">To ensure that students can’t schedule a live events to communicate unattended, disable the **Allow scheduling** policy for students by setting it to **Off**.</span></span>

:::image type="content" source="media/edu-allow-scheduling-off.png" alt-text="リモート学習における学生教育 (スケジュール許可オプションを無効にした状態)。":::

### <a name="calling-policies"></a><span data-ttu-id="09a88-275">通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="09a88-275">Calling policies</span></span>

#### <a name="turn-off-the-ability-to-make-private-calls"></a><span data-ttu-id="09a88-276">プライベート通話を行う機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="09a88-276">Turn off the ability to make private calls</span></span>

<span data-ttu-id="09a88-277">学生が他の学生や教師とプライベート通話を行えないようにするために、学生に対する **[プライベート通話をする]** ポリシーを **[オフ]** に設定して無効にします。</span><span class="sxs-lookup"><span data-stu-id="09a88-277">To ensure that students can’t make private calls with other students or educators, disable the **Make private calls** policy for students by setting it to **Off**.</span></span>

:::image type="content" source="media/edu-private-calls-off.png" alt-text="リモート学習における学生教育 ([プライベート通話をする] をオフに設定した状態)。":::

### <a name="messaging-policies"></a><span data-ttu-id="09a88-279">メッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="09a88-279">Messaging policies</span></span>

#### <a name="turn-off-the-ability-to-delete-or-edit-sent-messages"></a><span data-ttu-id="09a88-280">送信したメッセージを削除または編集する機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="09a88-280">Turn off the ability to delete or edit sent messages</span></span>

- <span data-ttu-id="09a88-281">学生の場合: 学生が送信したメッセージが削除または変更できないようにするために、学生の次の設定を**オフ**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-281">For students: To make sure the messages that students send aren’t deleted or altered, students should have these settings turned **Off**:</span></span>

  - <span data-ttu-id="09a88-282">**送信済みメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="09a88-282">**Delete sent messages**</span></span>
  - <span data-ttu-id="09a88-283">**送信済みメッセージを編集する**</span><span class="sxs-lookup"><span data-stu-id="09a88-283">**Edit sent messages**</span></span>
  
- <span data-ttu-id="09a88-284">教師の場合: 教師が生徒が送信した不適切なメッセージをモデレートしたり、削除したりできるようにするために、教師の次の設定を**オン**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-284">For educators: To make sure that educators can moderate or delete inappropriate messages students sent, educators should have these settings turned **On**:</span></span>

  - <span data-ttu-id="09a88-285">**所有者が送信したメッセージを削除できます** (この設定により、教師は不適切な学生のメッセージを削除できます)</span><span class="sxs-lookup"><span data-stu-id="09a88-285">**Owners can delete sent messages** (This setting allows educators to delete inappropriate student messages)</span></span>
  - <span data-ttu-id="09a88-286">**送信済みメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="09a88-286">**Delete sent messages**</span></span>
  - <span data-ttu-id="09a88-287">**送信済みメッセージを編集する**</span><span class="sxs-lookup"><span data-stu-id="09a88-287">**Edit sent messages**</span></span>

  ![リモート学習における学生教育 (学生および教師に対する送信済みメッセージの設定)。](media/edu-delete-edit-sent.png)

> [!NOTE]
> <span data-ttu-id="09a88-289">このトピックの詳細については、「[クラスチームで学生のコメントをミュートする](https://support.office.com/article/Mute-student-comments-in-a-class-team-a378de16-ffc0-420c-b08d-e17ec08e7c17)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="09a88-289">For more information on this topic, check out [Mute student comments in a class team](https://support.office.com/article/Mute-student-comments-in-a-class-team-a378de16-ffc0-420c-b08d-e17ec08e7c17).</span></span>

#### <a name="control-whether-students-can-chat-privately"></a><span data-ttu-id="09a88-290">学生がプライベート チャットできるかどうかを制御する</span><span class="sxs-lookup"><span data-stu-id="09a88-290">Control whether students can chat privately</span></span>

<span data-ttu-id="09a88-291">学生に対して設定した **[チャットのオン/オフ]** の値が教育機関のガイドラインおよび学生や教師の要望に沿っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="09a88-291">Ensure that the **Chat On/Off** value you set for students aligns to your educational institution’s guidelines as well as the desires of students and educators.</span></span> <span data-ttu-id="09a88-292">このコントロールは、Teams 内でユーザー 1:1 のチャットやグループ チャットを使用してプライベートで会話する機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="09a88-292">This control turns on or off the ability for a user to communicate privately in 1:1 chat or group chat in Teams.</span></span>

![リモート学習における学生教育 (チャット オプションを無効にした状態)。](media/edu-chat-private.png)

#### <a name="control-whether-students-can-personalize-their-messages"></a><span data-ttu-id="09a88-294">学生が自分自身のメッセージをカスタマイズできるかどうかを制御する</span><span class="sxs-lookup"><span data-stu-id="09a88-294">Control whether students can personalize their messages</span></span>

<span data-ttu-id="09a88-295">学生に対して設定した値が、教育機関のガイドラインに加えて、学生、教師、保護者の要望に沿っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="09a88-295">Ensure that the value you set for students aligns to your educational institution’s guidelines as well as the desires of students, educators, parents, and guardians.</span></span> <span data-ttu-id="09a88-296">**[学生に対する Giphy]** を **[オフ]** に設定し、**[ミームとステッカー]** を **[オン]** のままに維持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09a88-296">Our recommendation is to set **Giphy for students** to **Off**, and keep **Memes and Stickers** turned **On**.</span></span>

![リモート学習における学生教育 (Giphy オプションおよびミームとステッカー オプションと共に表示)。](media/edu-personalize-messages.png)

#### <a name="control-whether-students-can-send-voice-messages"></a><span data-ttu-id="09a88-298">学生が音声メッセージを送信できるかどうかを制御する</span><span class="sxs-lookup"><span data-stu-id="09a88-298">Control whether students can send voice messages</span></span>

<span data-ttu-id="09a88-299">学生に対して設定した **[音声メッセージの作成]** の値が教育機関のガイドラインおよび学生や教師の要望に沿っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="09a88-299">Ensure that the value you set for **Create voice messages** for students aligns to your educational institution’s guidelines as well as the desires of students and educators.</span></span>

![リモート学習における学生教育 (音声メッセージの作成 オプションと共に表示)。](media/edu-create-send-voice-mess.png)

#### <a name="turn-off-the-ability-to-remove-users-from-chat-for-students"></a><span data-ttu-id="09a88-301">学生がチャットからユーザーを削除する機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="09a88-301">Turn off the ability to remove users from chat for students</span></span>

<span data-ttu-id="09a88-302">学生には、彼らが参加しているチャットから他のユーザーを削除する機能は付与するべきではありません。</span><span class="sxs-lookup"><span data-stu-id="09a88-302">Students should not have the ability to remove other users from any chats they're included in.</span></span> <span data-ttu-id="09a88-303">**[グループ チャットからユーザーを削除する]** の設定を **[オフ]** に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-303">The setting for **Remove users from group chats** should be set to **Off**.</span></span>

![リモート学習における学生教育 ([グループ チャットからユーザーを削除する] オプションを [オフ] に設定した状態)。](media/edu-remove-users-from-chat-for-students.png)

### <a name="teams-policies"></a><span data-ttu-id="09a88-305">Teams ポリシー</span><span class="sxs-lookup"><span data-stu-id="09a88-305">Teams policies</span></span>

#### <a name="turn-off-the-ability-to-discover-and-create-private-channels"></a><span data-ttu-id="09a88-306">プライベート チャネルを検出して作成する機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="09a88-306">Turn off the ability to discover and create private channels</span></span>

<span data-ttu-id="09a88-307">学生が監視なく会話できるパーソナル スペースとしてプライベート チャネルを作成できないようにするために、学生に対する **[プライベート チャネルを作成する]** ポリシーを **[オフ]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="09a88-307">To ensure that students can’t create a private channel as personal space to communicate without supervision, set the **Create private channels** policy for students to **Off**.</span></span>

![Teams ポリシー ページ (ページの右側に新しい Teams ポリシー パネルが重なった状態、パネルで [プライベート チャネルを作成する] は [オフ] に設定されています)。](media/edu-private-channels.png)

> [!IMPORTANT]
> <span data-ttu-id="09a88-309">また、学生に Microsoft Teams で新しいチームを作成する機能がないことを確認することが必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-309">Likely you will also want to ensure students don't have the ability to create new teams in Microsoft Teams.</span></span> <span data-ttu-id="09a88-310">これは実際には M365 グループの設定です。詳細については、「[Microsoft 365 グループを作成できるユーザーを管理する](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)」をお読みください。</span><span class="sxs-lookup"><span data-stu-id="09a88-310">This is actually an M365 groups setting, and you can read more about it in [Manage who can create Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups).</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="09a88-311">アプリのアクセス許可ポリシー</span><span class="sxs-lookup"><span data-stu-id="09a88-311">App permission policies</span></span>

#### <a name="control-whether-students-can-add-apps-within-teams"></a><span data-ttu-id="09a88-312">学生が Teams 内にアプリを追加できるかどうかを制御する</span><span class="sxs-lookup"><span data-stu-id="09a88-312">Control whether students can add apps within Teams</span></span>

<span data-ttu-id="09a88-313">学生に対して設定した値が教育機関のガイドラインに沿っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="09a88-313">Ensure the values you set for students align to your educational institution’s guidelines.</span></span> <span data-ttu-id="09a88-314">たとえば、学生が承認したアプリを公開できるようにする場合は、次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="09a88-314">For example, if you’d like the students to be exposed to the apps you approve, you can select:</span></span>

- <span data-ttu-id="09a88-315">**Microsoft アプリ**: **すべてのアプリを許可する**</span><span class="sxs-lookup"><span data-stu-id="09a88-315">**Microsoft apps**: **Allow all apps**</span></span>
- <span data-ttu-id="09a88-316">**サードパーティ製のアプリの場合**: **特定のアプリを許可し、他のすべてのアプリを禁止する**</span><span class="sxs-lookup"><span data-stu-id="09a88-316">**For Third-party apps**: **Allow specific apps and block all others**</span></span>
- <span data-ttu-id="09a88-317">**テナント アプリの場合**: **特定のアプリを許可し、他のすべてのアプリを禁止する**</span><span class="sxs-lookup"><span data-stu-id="09a88-317">**For Tenant apps**: **Allow specific apps and block all others**</span></span>

:::image type="content" source="media/edu-policies-apps.png" alt-text="リモート学習における学生教育 (アプリ ポリシー オプションと共に表示)。":::

> [!NOTE]
> <span data-ttu-id="09a88-319">これは例ですが、前述したように、教育機関のガイドラインに従って、これらのポリシーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-319">This is an example, and as stated above, you should set these policies in accordance to your educational institution's guidelines.</span></span>

## <a name="policies-that-should-be-assigned-for-educators"></a><span data-ttu-id="09a88-320">教師向けに割り当てるべきポリシー</span><span class="sxs-lookup"><span data-stu-id="09a88-320">Policies that should be assigned for educators</span></span>

<span data-ttu-id="09a88-321">これらは、管理者が学生に対して安全なクラス環境を実現できるように、教師向けに適用が推奨されるポリシー設定です。</span><span class="sxs-lookup"><span data-stu-id="09a88-321">These are recommended policy settings for admins to apply for educators, so they can have a safe class experience for their students.</span></span>

> [!NOTE]
> <span data-ttu-id="09a88-322">学生向けポリシーの推奨事項には、以下に示す教師向けセクションよりも多くの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09a88-322">The policy recommendations for students contains more information than the educators' sections you'll see below.</span></span> <span data-ttu-id="09a88-323">教育機関独自のポリシーおよび手順に準拠してポリシー設定を行うこともできますが、ここで説明する推奨事項は、学生の安全とセキュリティに関してのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="09a88-323">While you may set policy settings in-line with your educational institute's own policies and procedures, the recommendations provided here are strictly relevant when it comes to the safety and security of students.</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="09a88-324">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="09a88-324">Meeting policies</span></span>

<span data-ttu-id="09a88-325">これらの設定により、教師は会議に対するアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-325">These settings will allow educators to control access to their meetings.</span></span>

- <span data-ttu-id="09a88-326">**匿名ユーザーが会議を開始できるようにする**: **オフ**</span><span class="sxs-lookup"><span data-stu-id="09a88-326">**Let anonymous people start a meeting**: **Off**</span></span>
- <span data-ttu-id="09a88-327">**ユーザーの参加を自動的に許可する**: **組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="09a88-327">**Automatically admit people**: **Everyone in your organization**</span></span>
- <span data-ttu-id="09a88-328">**ダイヤルイン ユーザーによるロビーのバイパスを許可する**: **オフ**</span><span class="sxs-lookup"><span data-stu-id="09a88-328">**Allow dial-in users to bypass the lobby**: **Off**</span></span>
- <span data-ttu-id="09a88-329"><sup>1</sup>**DesignatedPresenterRoleMode**: **OrganizerOnlyUserOverride**</span><span class="sxs-lookup"><span data-stu-id="09a88-329"><sup>1</sup>**DesignatedPresenterRoleMode**: **OrganizerOnlyUserOverride**</span></span>

<span data-ttu-id="09a88-330"><sup>1</sup> この設定は、Microsoft Teams 管理センターにはないので、[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) または [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、**DesignatedPresenterRoleMode** パラメーターを設定するために、PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-330"><sup>1</sup> This setting isn't in the Microsoft Teams admin center, so you'll need to use PowerShell to set the **DesignatedPresenterRoleMode** parameter using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) or [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="09a88-331">これにより、Teams の **[会議]** オプションの **[発表者となるユーザー]** 設定の既定値を **[自分のみ]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="09a88-331">This sets the default value of the **Who can present?** setting in **Meeting options** in Teams to **Only me**.</span></span> <span data-ttu-id="09a88-332">この設定では、会議の開催者のみが発表者となり、他のすべての会議参加者が出席者として指定されます。</span><span class="sxs-lookup"><span data-stu-id="09a88-332">With this setting, only the meeting organizer can be a presenter and all other meeting participants are designated as attendees.</span></span> <span data-ttu-id="09a88-333">詳細については、「[会議ポリシーの設定 - 指定された発表者役割モード](meeting-policies-in-teams.md#meeting-policy-settings---designated-presenter-role-mode)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09a88-333">To learn more, see [Meeting policy settings - Designated presenter role mode](meeting-policies-in-teams.md#meeting-policy-settings---designated-presenter-role-mode).</span></span>

> [!NOTE]
> <span data-ttu-id="09a88-334">教師ではないスタッフの場合、パラメーターを **EveryoneUserOverride** (Teams の **[すべてのユーザー]** 設定に対応) または **EveryoneInCompanyUserOverride** (Teamsの **[自分の組織内のユーザー]** 設定に対応) に設定することが必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-334">For staff who aren't educators, you may want to set the parameter to **EveryoneUserOverride** (which corresponds to the **Everyone** setting in Teams) or **EveryoneInCompanyUserOverride** (which corresponds to the **People in my organization** setting in Teams.)</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="09a88-335">メッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="09a88-335">Messaging policies</span></span>

<span data-ttu-id="09a88-336">**[所有者が送信したメッセージを削除できます]** を **[オン]** に設定することで、教師は、チャット セッションを監視し、チャット メッセージ内の不適切なメッセージを削除できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-336">Setting **Owners can delete sent messages** to **On** will allow educators to monitor chat sessions and remove inappropriate messages in channel meetings.</span></span>

> [!NOTE]
> <span data-ttu-id="09a88-337">これにより、教師は、チャネル内で会議を作成するときにクラス チャットで不適切なメッセージを削除したり、チャネル内のメッセージを削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="09a88-337">This allows educators to remove inappropriate messages in class chats when the meeting is created within the channel, or to remove messages within the channel itself.</span></span>

## <a name="what-educators-can-do-to-protect-students"></a><span data-ttu-id="09a88-338">学生を保護するために教師ができること</span><span class="sxs-lookup"><span data-stu-id="09a88-338">What educators can do to protect students</span></span>

<span data-ttu-id="09a88-339">当然ですが、Teams 設定におけるポリシー設定は、管理者が積極的に学生を保護するのに最適な方法です。また、教師は定期的に学生と交流し、学生の安全を守るために重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="09a88-339">Of course, while setting policies is a great way for Admins to proactively protect students in a Teams setting, educators are the people who are interacting with the students on a regular basis, and they also have a vital role to play to keep students safe.</span></span> <span data-ttu-id="09a88-340">管理者は、次の情報について、協働する教師と話し合うことが必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-340">Admins may want to discuss the following information with the educators they work with.</span></span>

### <a name="set-meeting-roles-through-your-meeting-options"></a><span data-ttu-id="09a88-341">会議のオプションを使用して会議の役割を設定する</span><span class="sxs-lookup"><span data-stu-id="09a88-341">Set meeting roles through your Meeting options</span></span>

<span data-ttu-id="09a88-342">会議オプションにより、会議の参加者が出席者または発表者として会議に参加するかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-342">Meeting options allow you to control if meeting participants join your meetings as attendees or presenters.</span></span> <span data-ttu-id="09a88-343">オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="09a88-343">Your options are:</span></span>

- <span data-ttu-id="09a88-344">**[予定表]** に移動して、更新する会議に移動します。</span><span class="sxs-lookup"><span data-stu-id="09a88-344">Go to your **Calendar**  and navigate to the meeting you'd like to update.</span></span> <span data-ttu-id="09a88-345">[会議参加] リンクの近くにの **[会議オプション]** をクリックまたはタップして、**[会議オプション]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="09a88-345">Click or tap **Meeting options** near the meeting join link to open your **Meeting options**.</span></span>

![Microsoft Teams 会議出席依頼 (会議オプションは、[招待] リンクの下の右端にあります)。](media/edu-join-meeting-options.png)

- <span data-ttu-id="09a88-347">**[ロビーをバイパスできる人]** 選択を使用して、会議に直接参加できるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="09a88-347">Control who can enter the meeting directly with the **Who can bypass the lobby** selection.</span></span> <span data-ttu-id="09a88-348">これを **[自分の組織内のユーザー]** に設定すると、外部ユーザーが会議に参加できるかどうかのオプションを維持することになります。**[常に発信者にロビーをバイパスさせる]** を **[オフ]** にすると、直ちに参加するのではなく、参加者に会議への参加を待機してもらうことになります。</span><span class="sxs-lookup"><span data-stu-id="09a88-348">Set it to **People in my organization** to keep external users from having the option to enter, and turn **Always let callers bypass the lobby** to **Off** to have participants wait to be admitted to the meeting instead of joining immediately.</span></span> <span data-ttu-id="09a88-349">また、**[発信者が会議に参加または会議から退出したときに通知する]** オプションがあります。これを **[オン]** に設定すると、会議に参加しているユーザーを常に把握できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-349">You also have the option to **Announce when callers join or leave**, and this should be set to **On** so you're always aware of who's in the meeting.</span></span>

- <span data-ttu-id="09a88-350">会議に参加するユーザーが発表者または出席者であるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="09a88-350">Control who joins the meeting as a presenter or attendee.</span></span> <span data-ttu-id="09a88-351">他のすべての参加者に出席者を指定するには、**[自分のみ]** 選択します。</span><span class="sxs-lookup"><span data-stu-id="09a88-351">You can select **Only Me** to designate all other participants as attendees.</span></span> <span data-ttu-id="09a88-352">これは、教室設定での会議の最も安全なセットアップです。</span><span class="sxs-lookup"><span data-stu-id="09a88-352">This is the safest set-up for meetings held in a classroom setting.</span></span>

  - <span data-ttu-id="09a88-353">会議に複数の発表者が参加していることが予想される場合は、**[特定のユーザー]** を選択し、発表者として参加する他の参加者を選びます。</span><span class="sxs-lookup"><span data-stu-id="09a88-353">If you expect to have more than one presenter in your meeting, select **Specific people** and pick the other participants who should join as presenters.</span></span> <span data-ttu-id="09a88-354">すべての参加者に発表者として出席を依頼する場合は、**[すべてのユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="09a88-354">Select **Everyone** if you want all participants to join the meeting as a presenter.</span></span>

:::image type="content" source="media/edu-meeting-options.png" alt-text="[ロビーをバイパスできるユーザー] ドロップダウン ([自分の組織内のユーザー] を選択した状態)、および [発表者となるユーザー] ドロップダウン ([自分のみ] を選択した状態)。":::

### <a name="roles-in-an-online-meeting"></a><span data-ttu-id="09a88-356">オンライン会議における役割</span><span class="sxs-lookup"><span data-stu-id="09a88-356">Roles in an online meeting</span></span>

<span data-ttu-id="09a88-357">会議の参加者全員に発表者または出席者としての役割が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="09a88-357">Every participant in a meeting is assigned a role as a presenter or attendee.</span></span> <span data-ttu-id="09a88-358">参加者の役割は、会議でできることを制御します。</span><span class="sxs-lookup"><span data-stu-id="09a88-358">A participant's role controls what they can do in a meeting.</span></span> <span data-ttu-id="09a88-359">以下の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09a88-359">Please see the table below.</span></span>

|<span data-ttu-id="09a88-360">機能</span><span class="sxs-lookup"><span data-stu-id="09a88-360">Capabilities</span></span>  |<span data-ttu-id="09a88-361">主催者/発表者</span><span class="sxs-lookup"><span data-stu-id="09a88-361">Organizer/Presenter</span></span>  |<span data-ttu-id="09a88-362">出席者</span><span class="sxs-lookup"><span data-stu-id="09a88-362">Attendee</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="09a88-363">話す、ビデオを共有する</span><span class="sxs-lookup"><span data-stu-id="09a88-363">Speak and share video</span></span>     |     <span data-ttu-id="09a88-364">Y</span><span class="sxs-lookup"><span data-stu-id="09a88-364">Y</span></span>     |     <span data-ttu-id="09a88-365">Y</span><span class="sxs-lookup"><span data-stu-id="09a88-365">Y</span></span>     |
|<span data-ttu-id="09a88-366">会議のチャットに参加する</span><span class="sxs-lookup"><span data-stu-id="09a88-366">Participate in meeting chat</span></span>     |     <span data-ttu-id="09a88-367">Y</span><span class="sxs-lookup"><span data-stu-id="09a88-367">Y</span></span>     |     <span data-ttu-id="09a88-368">Y</span><span class="sxs-lookup"><span data-stu-id="09a88-368">Y</span></span>     |
|<span data-ttu-id="09a88-369">別のユーザーによって共有されている PowerPoint ファイルをプライベートで表示する</span><span class="sxs-lookup"><span data-stu-id="09a88-369">Privately view a PowerPoint file shared by someone else</span></span>     |     <span data-ttu-id="09a88-370">Y</span><span class="sxs-lookup"><span data-stu-id="09a88-370">Y</span></span>     |     <span data-ttu-id="09a88-371">Y</span><span class="sxs-lookup"><span data-stu-id="09a88-371">Y</span></span>     |
|<span data-ttu-id="09a88-372">コンテンツを共有する</span><span class="sxs-lookup"><span data-stu-id="09a88-372">Share content</span></span>     |     <span data-ttu-id="09a88-373">Y</span><span class="sxs-lookup"><span data-stu-id="09a88-373">Y</span></span>     |     <span data-ttu-id="09a88-374">N</span><span class="sxs-lookup"><span data-stu-id="09a88-374">N</span></span>     |
|<span data-ttu-id="09a88-375">他の参加者をミュートする</span><span class="sxs-lookup"><span data-stu-id="09a88-375">Mute other participants</span></span>|     <span data-ttu-id="09a88-376">Y</span><span class="sxs-lookup"><span data-stu-id="09a88-376">Y</span></span>     |     <span data-ttu-id="09a88-377">N</span><span class="sxs-lookup"><span data-stu-id="09a88-377">N</span></span>     |
|<span data-ttu-id="09a88-378">参加者を削除する</span><span class="sxs-lookup"><span data-stu-id="09a88-378">Remove participants</span></span>      |     <span data-ttu-id="09a88-379">Y</span><span class="sxs-lookup"><span data-stu-id="09a88-379">Y</span></span>     |     <span data-ttu-id="09a88-380">N</span><span class="sxs-lookup"><span data-stu-id="09a88-380">N</span></span>     |
|<span data-ttu-id="09a88-381">ロビーの参加者を許可する</span><span class="sxs-lookup"><span data-stu-id="09a88-381">Admit participants from the lobby</span></span>|     <span data-ttu-id="09a88-382">Y</span><span class="sxs-lookup"><span data-stu-id="09a88-382">Y</span></span>     |     <span data-ttu-id="09a88-383">N</span><span class="sxs-lookup"><span data-stu-id="09a88-383">N</span></span>     |
|<span data-ttu-id="09a88-384">他の参加者の役割を変更する</span><span class="sxs-lookup"><span data-stu-id="09a88-384">Change the roles of other participants</span></span>     |     <span data-ttu-id="09a88-385">Y</span><span class="sxs-lookup"><span data-stu-id="09a88-385">Y</span></span>     |     <span data-ttu-id="09a88-386">N</span><span class="sxs-lookup"><span data-stu-id="09a88-386">N</span></span>     |
|<span data-ttu-id="09a88-387">録画を開始または停止する</span><span class="sxs-lookup"><span data-stu-id="09a88-387">Start or stop recording</span></span>     |     <span data-ttu-id="09a88-388">Y</span><span class="sxs-lookup"><span data-stu-id="09a88-388">Y</span></span>     |     <span data-ttu-id="09a88-389">N</span><span class="sxs-lookup"><span data-stu-id="09a88-389">N</span></span>     |

### <a name="change-roles-during-a-meeting"></a><span data-ttu-id="09a88-390">会議中に役割を変更する</span><span class="sxs-lookup"><span data-stu-id="09a88-390">Change roles during a meeting</span></span>

<span data-ttu-id="09a88-391">会議の参加者全員に発表者または出席者としての役割が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="09a88-391">Every participant in a meeting is assigned a role as presenter or attendee.</span></span> <span data-ttu-id="09a88-392">参加者の役割は、会議中にできることを制御します。</span><span class="sxs-lookup"><span data-stu-id="09a88-392">A participant's role controls what they can do while in a meeting.</span></span>

- <span data-ttu-id="09a88-393">参加者の役割を変更するには、通話コントロールの **[参加者の表示]** をクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="09a88-393">To change a participant's role, click or tap to **Show participants** in your call controls.</span></span> <span data-ttu-id="09a88-394">役割を変更する必要がある参加者を右クリックし、**[出席者にする]** または **[発表者にする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="09a88-394">Right-click on the participant whose role needs to be changed, and then select **Make an attendee** or **Make a presenter**.</span></span>

  ![[ユーザー] バー (メニュー オプションと共に表示。 [出席者] をメニューの 4 番目のオプションにします)。](media/edu-make-attendee-menu.png)

- <span data-ttu-id="09a88-396">会議オプションにすばやくアクセスし、現在の参加者と将来の出席者の両方の会議の役割の設定を変更するには、通話コントロールの **[その他のアクション]** をクリックまたはタップしてから、**[会議の詳細を表示]** をクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="09a88-396">To quickly access your Meeting options and change the meeting role settings for both current participants and anyone joining your meeting in the future, click or tap **More actions** in your call controls, and then **Show meeting details**.</span></span> <span data-ttu-id="09a88-397">[会議参加] リンクの近くに、**[会議オプション]** リンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09a88-397">You can find the link to your **Meeting options** near the join link for the meeting.</span></span>

  :::image type="content" source="media/edu-meeting-details.png" alt-text="会議ウィンドウ (右側の会議詳細ウィンドウと共に表示)。":::

### <a name="mute-student-comments"></a><span data-ttu-id="09a88-399">学生のコメントをミュートする</span><span class="sxs-lookup"><span data-stu-id="09a88-399">Mute student comments</span></span>

<span data-ttu-id="09a88-400">会議の後に、チャネル会議をスケジュールした場合、学生のコメントを禁止できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-400">After the meeting, you can block students from commenting further if you scheduled a channel meeting.</span></span>

#### <a name="for-a-specific-meeting"></a><span data-ttu-id="09a88-401">特定の会議の場合</span><span class="sxs-lookup"><span data-stu-id="09a88-401">For a specific meeting</span></span>

<span data-ttu-id="09a88-402">チャネルで会議をスケジュールすると、会議自体がチャネル投稿になり、会議チャットは投稿のレプリカになります。</span><span class="sxs-lookup"><span data-stu-id="09a88-402">When you schedule a meeting in a channel, the meeting itself is a channel post, and the meeting chats are replicas of the post.</span></span> <span data-ttu-id="09a88-403">チームの所有者である場合は、その投稿の **[その他のオプション]** をクリックまたはタップして、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09a88-403">As the team owner, you can click or tap **More actions** for that post, click **Edit**.</span></span>

:::image type="content" source="media/edu-meeting-edit.png" alt-text="チャネル投稿上で [その他のオプション] を選択し、ポップアップ メニュー上の 2 番目のオプションとして [編集] メニューが表示されています。":::

<span data-ttu-id="09a88-405">[編集] ウィンドウには、ドロップダウン オプションが表示されます。**[自分とモデレーターが返信できる]** ようにこのオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-405">On the edit pane, you have a dropdown option, where you can set that option to be **You and moderators can reply**.</span></span>

![[編集] メニューで、[全員が返信できる] オプションが表示され、 [自分とモデレーターが返信できる] オプションの横のマークにチェックが入れられています。](media/edu-you-and-mods-reply.png)

### <a name="for-all-meetings-and-posts-of-a-team"></a><span data-ttu-id="09a88-407">チームのすべての会議と投稿の場合</span><span class="sxs-lookup"><span data-stu-id="09a88-407">For all meetings and posts of a team</span></span>

<span data-ttu-id="09a88-408">クラス チームや会議チャットで学生が投稿および返信できる日時を制御できます。</span><span class="sxs-lookup"><span data-stu-id="09a88-408">You can control when students can post and reply in the class team and meeting chats.</span></span> <span data-ttu-id="09a88-409">チームの **[その他のアクション]** をタップまたはクリックして、**[チームの管理]** をクリックして、**[メンバー]** に移動して、ミュートする個別のユーザーを選択するか、**[学生全員をミュートにします]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="09a88-409">Click or tap **More actions** of the team, click **Manage Team**, go to **Members**, and either select individuals to mute or **Mute all students**.</span></span>

![学生を個別にミュートするオプション、または一覧上部のすべての学生をミュートするオプションを表示する出席者の会議一覧。](media/edu-student-mute.png)

## <a name="further-reading"></a><span data-ttu-id="09a88-411">参考資料</span><span class="sxs-lookup"><span data-stu-id="09a88-411">Further reading</span></span>

<span data-ttu-id="09a88-412">学生の保護に関する詳細については、「[遠隔教育で Teams 会議を利用している間、学生の安全を確保する](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="09a88-412">For more information on protecting students, review [Keeping students safe while using meetings in Teams for distance learning](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8).</span></span>
