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
ms.openlocfilehash: f580d8c41fe629a1c705f650a2aef84302128c20
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908616"
---
# <a name="teams-policies-and-policy-packages-for-education"></a><span data-ttu-id="0ed86-103">境域機関向け Teams ポリシーおよびポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="0ed86-103">Teams Policies and Policy Packages for Education</span></span>

> [!NOTE]
> <span data-ttu-id="0ed86-104">Microsoft Teams のポリシーの大規模な事例については、「[Microsoft Teams でユーザーにポリシーを割り当てる](assign-policies.md)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="0ed86-104">For the larger story on policies in Microsoft Teams, please review [Assign policies to your users in Microsoft Teams](assign-policies.md).</span></span>

## <a name="admins-getting-started-with-microsoft-teams-policy-management"></a><span data-ttu-id="0ed86-105">管理者: Microsoft Teams のポリシー管理の概要</span><span class="sxs-lookup"><span data-stu-id="0ed86-105">Admins: Getting started with Microsoft Teams policy management</span></span>

<span data-ttu-id="0ed86-106">Microsoft Teams を使用すると、ユーザーはオンライン会議やライブ イベントへの参加、チャット、通話、アプリの使用などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-106">Microsoft Teams allows users to do things like attend online meetings or live events, chat, make calls, and use apps.</span></span> <span data-ttu-id="0ed86-107">適切な Microsoft Teams 管理ポリシーを設定することは、Teams が学生にとって安全な学習環境であることを保証するための重要なステップです。</span><span class="sxs-lookup"><span data-stu-id="0ed86-107">Setting the right Microsoft Teams admin policies is a critical step in ensuring that Teams is a safe learning environment for students.</span></span> <span data-ttu-id="0ed86-108">管理者は、ポリシーを使用して、教育機関のユーザーが利用できる Teams 機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-108">As an admin, you can use policies to control the Teams features that are available to users in your educational institute.</span></span>  <span data-ttu-id="0ed86-109">ほとんどの場合、環境を安全に保つために、学生と教師の両方のポリシーを調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ed86-109">In most cases, policies must be adjusted for both students and educators to keep the environment safe.</span></span>  

<span data-ttu-id="0ed86-110">Microsoft Teams 内の主なポリシー領域の一覧は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0ed86-110">Here's a list of the main policy areas you will find in Microsoft Teams.</span></span> <span data-ttu-id="0ed86-111">各領域のポリシーとそれらが制御する機能の詳細については、以下のリンクを使用してください:</span><span class="sxs-lookup"><span data-stu-id="0ed86-111">To learn more about the policies in each area and the capabilities they control, use the links below:</span></span>

- [<span data-ttu-id="0ed86-112">会議</span><span class="sxs-lookup"><span data-stu-id="0ed86-112">Meetings</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="0ed86-113">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="0ed86-113">Live events</span></span>](teams-live-events/configure-teams-live-events.md)
- [<span data-ttu-id="0ed86-114">通話</span><span class="sxs-lookup"><span data-stu-id="0ed86-114">Calling</span></span>](teams-calling-policy.md) 
- <span data-ttu-id="0ed86-115">[メッセージング](messaging-policies-in-teams.md) </span><span class="sxs-lookup"><span data-stu-id="0ed86-115">[Messaging](messaging-policies-in-teams.md)</span></span>
- [<span data-ttu-id="0ed86-116">Teams</span><span class="sxs-lookup"><span data-stu-id="0ed86-116">Teams</span></span>](teams-policies.md)
- [<span data-ttu-id="0ed86-117">アプリのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0ed86-117">App permissions</span></span>](teams-app-permission-policies.md)

:::image type="content" source="media/edu-admin-center-users.png" alt-text="ポリシーが適用されているユーザーのスクリーンショット。":::

<span data-ttu-id="0ed86-119">管理者の資格情報でサインインすることにより、[Microsoft Teams 管理センター](https://admin.teams.microsoft.com) で、Teams のすべてのポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-119">You can manage all Teams policies in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) by signing in with your admin credentials.</span></span>

### <a name="where-to-find-microsoft-teams-policies"></a><span data-ttu-id="0ed86-120">Microsoft Teams ポリシーへのアクセス方法</span><span class="sxs-lookup"><span data-stu-id="0ed86-120">Where to find Microsoft Teams policies</span></span>

<span data-ttu-id="0ed86-121">Teams 管理センターにログインすると、Teams 管理センターの左側のナビゲーションにある [ポリシー] オプションをクリックして、管理する必要がある Teams のあらゆる領域のポリシー設定に移動できます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-121">Once you've logged into the Teams admin center, you'll be able to go to the policy settings for any area of Teams you need to manage, by clicking on the policy option in the left hand navigation of the Teams admin center.</span></span> <span data-ttu-id="0ed86-122">メッセージング ポリシーの場所のスクリーンショットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0ed86-122">We've included a screenshot of the location of the messaging policies.</span></span>

:::image type="content" source="media/edu-messaging-policies.png" alt-text="Teams 管理センター内のメッセージング ポリシーの場所。":::

### <a name="how-to-create-and-update-a-policy-definition"></a><span data-ttu-id="0ed86-124">ポリシー定義を作成して更新する方法</span><span class="sxs-lookup"><span data-stu-id="0ed86-124">How to create and update a policy definition</span></span>

<span data-ttu-id="0ed86-125">ユーザーにポリシーを割り当てる前に、Teams を使って、各機能領域のポリシー定義を追加および作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ed86-125">Before you assign policies to your users, you need to first add and create your policy definitions for each capability area with Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="0ed86-126">学生と教師には、異なるポリシー定義を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ed86-126">We recommend that you set different policy definitions for your students and educators.</span></span>

<span data-ttu-id="0ed86-127">既定では、すべての新しいユーザー (学生または教師) に各機能領域に対してグローバル (組織全体の既定) ポリシー定義が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-127">By default, every new user (student or educator) will be assigned the Global (Org-wide default) policy definition for each capability area.</span></span> <span data-ttu-id="0ed86-128">最も厳密なポリシー定義のセットには、グローバル （組織全体の既定） を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ed86-128">We recommend that you use the Global (Org-wide default) for your strictest set of policy definitions.</span></span> <span data-ttu-id="0ed86-129">ほとんどの場合、このより厳密なポリシー セットは学生により適しています。</span><span class="sxs-lookup"><span data-stu-id="0ed86-129">In most cases, this stricter policy set will be more appropriate for students.</span></span> <span data-ttu-id="0ed86-130">このようにグローバル （組織全体の既定） ポリシー定義を使用すると、新しいユーザーがテナントに追加されたときに最も厳しい制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-130">Using your Global (Org-wide default) policy definition in this way will ensure that new users will have the tightest restrictions when they are added to your tenant.</span></span> <span data-ttu-id="0ed86-131">このガイダンスに従うには、次の手順に従うことをお勧めします:</span><span class="sxs-lookup"><span data-stu-id="0ed86-131">To adhere to this guidance, we recommend you follow these steps:</span></span>

1. <span data-ttu-id="0ed86-132">チームの機能領域ごとに、教師のニーズに合ったポリシー値を使用してカスタム ポリシー定義を作成します （これがないと、教師は、グローバル （組織全体の既定） ポリシー定義で定義されているのと同じ制限付きアクセスを学生に与えることになります）。</span><span class="sxs-lookup"><span data-stu-id="0ed86-132">Create a custom policy definition for each Teams capability area with policy values that are fitting for your educators' needs (without this, educators will have the same restricted access as your students as defined within the Global (Org-wide default) policy definition).</span></span>

1. <span data-ttu-id="0ed86-133">これらの新しいカスタム ポリシー定義を教師に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-133">Assign these new custom policy definitions to your educators.</span></span>

1. <span data-ttu-id="0ed86-134">学生に適した値を使用して、各機能領域のグローバル （組織全体の既定） ポリシー定義を編集します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-134">Edit the Global (Org-wide default) policy definitions for each capability area with values that are appropriate for your students.</span></span>

1. <span data-ttu-id="0ed86-135">グローバル （組織全体の既定） ポリシー定義は、他のポリシー定義が割り当てられていない限り、学生に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-135">The Global (Org-wide default) policy definitions will be applied to your students as long as they have no other policy definitions assigned.</span></span>


<span data-ttu-id="0ed86-136">ポリシー定義を作成または編集するには、作業するポリシー機能領域 (メッセージング ポリシーなど) に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-136">To create or edit policy definitions, go to the policy capability area you want to work in (for example, Messaging policies).</span></span> <span data-ttu-id="0ed86-137">**[追加]** を選択して、新しいカスタム ポリシー定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-137">Select **Add** to create a new custom policy definition.</span></span> <span data-ttu-id="0ed86-138">既存のポリシー定義を変更するには、 **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-138">To change an existing policy definition, select **Edit**.</span></span>

:::image type="content" source="media/edu-messaging-policies-add-closeup.png" alt-text="[追加] ボタンを表示した状態での [メッセージング ポリシー] セクションのクローズアップ。":::

<span data-ttu-id="0ed86-140">ポリシー定義を追加するか編集するかを選択したどうかにかかわらず、このポリシー領域に関連付けられているすべてのポリシー オプションが一覧表示されるビューに移動します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-140">Whether you choose to add or edit a policy definition, you're brought to a view that lists all the policy options related to this policy area.</span></span> <span data-ttu-id="0ed86-141">このリストを使用して、ポリシー定義に設定する値を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-141">Use this list to select what values you want set in your policy definition.</span></span>

![選んだポリシー領域に関連付けられているポリシー オプションを含むページ。](media/edu-global-policy-definition.png)

> [!IMPORTANT]
> <span data-ttu-id="0ed86-143">ページから移動する前に、 **[保存]** を必ず選択してください。</span><span class="sxs-lookup"><span data-stu-id="0ed86-143">Don’t forget to select **Save** before you leave the page.</span></span>

### <a name="assigning-policy-definitions"></a><span data-ttu-id="0ed86-144">ポリシー定義の割り当て</span><span class="sxs-lookup"><span data-stu-id="0ed86-144">Assigning policy definitions</span></span> 
<span data-ttu-id="0ed86-145">ポリシー定義をユーザーに割り当てるために使用できる方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="0ed86-145">There are multiple methods you can use to assign policy definitions to your users.</span></span> <span data-ttu-id="0ed86-146">各方法には、独自の利点と欠点があります。これは、お客様の機関のニーズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0ed86-146">Each method has its own advantages and disadvantages, which will differ depending on your institution's unique needs.</span></span>  

<span data-ttu-id="0ed86-147">ほとんどの場合、グループ ポリシーの割り当てを使用して、ユーザーにポリシーを割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ed86-147">In most cases, we recommend that you use group policy assignment to assign policies to your users.</span></span> <span data-ttu-id="0ed86-148">この方法を使用すると、より迅速かつシームレスにポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-148">This method allows for faster and more seamless policy application.</span></span>  <span data-ttu-id="0ed86-149">ポリシー定義が割り当てられているグループにユーザーを追加すると、新しいユーザーはグループのポリシーを自動的に継承します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-149">When a user is added to a group that has a policy definition assigned to it, the new user automatically inherits the policies of the group.</span></span>  <span data-ttu-id="0ed86-150">これにより、たとえば学期の開始時や終了時に、環境に多数のユーザーが追加および削除された場合に、ポリシー管理が容易になります。</span><span class="sxs-lookup"><span data-stu-id="0ed86-150">This allows for easier policy management when large numbers of users are added and removed to the environment, for example at the beginning and ending of a school term.</span></span>  

<span data-ttu-id="0ed86-151">大規模な組織では、多数のユーザーにポリシーを割り当てる必要がある場合に最適なバッチ ポリシーの割り当てもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ed86-151">For large organizations, we also recommend batch policy assignment, which is tailored for cases where you need to assign policies to large sets of users.</span></span> <span data-ttu-id="0ed86-152">これらの適用方法の詳細については、「[学校の多数のユーザーにポリシーを割り当てる](batch-group-policy-assignment-edu.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ed86-152">To learn more about these application methods, refer to [Assign policies to large sets of users in your school](batch-group-policy-assignment-edu.md).</span></span>

<span data-ttu-id="0ed86-153">小規模な機関の場合、または個々の学生または教師のポリシー設定を更新する必要がある場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0ed86-153">If you have a smaller institution or have a need to update an individual student or educator's policy settings, follow the instructions below.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="0ed86-154">個々のユーザー レベルで指定されたポリシーの割り当ては、ユーザーに割り当てられたグループ ポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="0ed86-154">Policy assignments given at the individual user level override any group policies assigned to the user.</span></span> <span data-ttu-id="0ed86-155">グループ ポリシー設定を上書きする場合にのみ、個別のポリシー割り当てを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ed86-155">Ensure that you are only using individual policy assignments when you desire to override group policy settings.</span></span> 

#### <a name="how-to-assign-a-policy-definition-to-a-user"></a><span data-ttu-id="0ed86-156">ユーザーにポリシー定義を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="0ed86-156">How to assign a policy definition to a user</span></span>

> [!NOTE]
> <span data-ttu-id="0ed86-157">ポリシー定義を割り当てると、すべてのユーザーとクライアントに反映されるのにしばらく時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ed86-157">Assigning a policy definition may take a while to propagate out to all the users and clients.</span></span> <span data-ttu-id="0ed86-158">Azure/M365 にユーザー アカウントを初めて作成するとき、教育機関に新しい学生が参加するときに、この操作を行うことが必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ed86-158">You might want to do this when the user accounts are first created in Azure/M365, and whenever a new student joins the educational institute.</span></span>


<span data-ttu-id="0ed86-159">ポリシー定義を作成または更新した後、ポリシー ページの **[ユーザーの管理]** を選択し、希望のユーザーを検索して、ポリシーを割り当てることにより、ユーザーにポリシー定義を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-159">Once your policy definition is created or updated, you can assign it to a user by selecting **Manage users** on the policy page, searching for the desired user, then applying the policy.</span></span>

![[メッセージング ポリシー] ページの上部の右側にあるユーザー パネルを管理します。](media/edu-manage-users-pane.png)

<span data-ttu-id="0ed86-161">また、 **[ユーザー]** に移動し、ポリシーを更新するユーザーを選択し、 **[ポリシー]** を選択してから **[編集]** を選択することにより、ユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-161">You can also assign a policy to a user by navigating to **Users** , selecting the user you wish to update policies for, selecting **Policies** , then **Edit**.</span></span> <span data-ttu-id="0ed86-162">ここから、各機能領域に対してユーザーに割り当てるポリシー定義を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-162">From there, you can select the policy definition you’d like to assign to the user for each capability area.</span></span>

![[割り当てられているポリシー] ページの右側にある [ユーザー ポリシーの編集] ウィンドウ。](media/edu-edit-user-policies-pane.png)

### <a name="policy-packages-in-microsoft-teams"></a><span data-ttu-id="0ed86-164">Microsoft Teams のポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="0ed86-164">Policy packages in Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="0ed86-165">詳細については、「[Microsoft Teams でポリシー パッケージを管理する](manage-policy-packages.md)」をご確認ください。1 人のユーザーにパッケージを割り当てる方法、最大 5000 人のユーザーにパッケージを一括で割り当てる方法、各パッケージに関連付けられたポリシーの管理と更新を行う方法を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="0ed86-165">For more reading, you can check out [Manage policy packages in Microsoft Teams](manage-policy-packages.md) for step by step guidance on assigning single users a package, assigning packages in bulk to up to 5000 users, and managing and updating the policies linked to each package.</span></span>

<span data-ttu-id="0ed86-166">Teams 内のポリシー パッケージは、上記で説明したように事前に定義されたポリシーおよびポリシー設定を収集し、それらを教育機関内の同様の役割を持つユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-166">A policy package in Teams collects predefined policies and policy settings that you learned about outlined above, and assigns them to users with similar roles in your institution.</span></span> <span data-ttu-id="0ed86-167">ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-167">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="0ed86-168">通常の方法では、各ユーザーにポリシーパッケージを割り当て、そのユーザー グループのニーズに合わせて、各パッケージのポリシーを再定義します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-168">In normal practice, you assign each of your users a policy package, and  redefine the policies in each package as needed to suit the needs of that user group.</span></span> <span data-ttu-id="0ed86-169">パッケージの設定を更新すると、そのパッケージに割り当てられているすべてのユーザーが一括更新として変更されます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-169">When you update settings in a package, all users assigned to that package are changed as a bulk update.</span></span>

<span data-ttu-id="0ed86-170">一般に、教育機関には、学生の年齢や成熟度によって異なる固有のニーズを持つ多くのユーザーが存在します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-170">Educational institutions in general have many users with unique needs, depending partly on the age and maturity of the students.</span></span> <span data-ttu-id="0ed86-171">たとえば、教師やスタッフが Microsoft Teams にフルアクセスできるようにする一方で、安全で集中できる学習環境を構築するために、学生に対する Microsoft Teams の機能を制限したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ed86-171">For example, you may want to grant educators and staff full access to Microsoft Teams, but want to limit Microsoft Teams capabilities for students to encourage a safe and focused learning environment.</span></span> <span data-ttu-id="0ed86-172">教育機関コミュニティにおける異なるコーホートのニーズに基づいて、ポリシー パッケージを使用して設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-172">You can use policy packages to tailor settings based on the needs of different cohorts in your educational institute community.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="0ed86-173">最初に、ポリシー パッケージの代わりに、学生に対してグローバル (組織全体の既定) ポリシー定義を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ed86-173">Our primary recommendation is that you use the Global (Org-wide default) policy definition for students instead of a policy package.</span></span> <span data-ttu-id="0ed86-174">これにより、組織内の新しいユーザーは常に、学生に適した最も厳格なポリシーのセットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-174">This ensures that new users in your organizations always have the strictest set of policies appropriate for students.</span></span> <span data-ttu-id="0ed86-175">この勧告が機関のニーズを満たしていない場合は、次のいずれかの学生ポリシー パッケージが適している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ed86-175">If this recommendation does not meet the needs of your institution, one of the student policy packages below may be a good alternative.</span></span> 

<span data-ttu-id="0ed86-176">この記事で前述したポリシー一覧と同様に、ポリシーパッケージでは、次のようなポリシーが事前に定義されています。</span><span class="sxs-lookup"><span data-stu-id="0ed86-176">Just like the policy list earlier in this article, policy packages predefine policies for:</span></span>

- <span data-ttu-id="0ed86-177">会議</span><span class="sxs-lookup"><span data-stu-id="0ed86-177">Meetings</span></span>
- <span data-ttu-id="0ed86-178">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="0ed86-178">Live events</span></span>
- <span data-ttu-id="0ed86-179">通話</span><span class="sxs-lookup"><span data-stu-id="0ed86-179">Calling</span></span>
- <span data-ttu-id="0ed86-180">Messaging</span><span class="sxs-lookup"><span data-stu-id="0ed86-180">Messaging</span></span>
- <span data-ttu-id="0ed86-181">アプリのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0ed86-181">App permissions</span></span>

<span data-ttu-id="0ed86-182">Microsoft Teams には現在、次のポリシー パッケージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-182">Microsoft Teams currently includes the following policy packages:</span></span>

|<span data-ttu-id="0ed86-183">Microsoft Teams 管理センターで一覧表示されるパッケージ名</span><span class="sxs-lookup"><span data-stu-id="0ed86-183">Package name listed in Microsoft Teams Admin center</span></span> |<span data-ttu-id="0ed86-184">以下の目的での使用に最適です</span><span class="sxs-lookup"><span data-stu-id="0ed86-184">Best used for</span></span>  |<span data-ttu-id="0ed86-185">説明</span><span class="sxs-lookup"><span data-stu-id="0ed86-185">Description</span></span> |
|:--- |:--- |:--- |
|<span data-ttu-id="0ed86-186">**Education_Teacher**</span><span class="sxs-lookup"><span data-stu-id="0ed86-186">**Education_Teacher**</span></span>| <span data-ttu-id="0ed86-187">教師およびスタッフ</span><span class="sxs-lookup"><span data-stu-id="0ed86-187">Educators and staff</span></span>| <span data-ttu-id="0ed86-188">この一連のポリシーおよびポリシー設定を使用して、Microsoft Teams を通して、組織内の教師およびスタッフがチャット、通話、会議にフルアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="0ed86-188">Use this set of policies and policy settings to grant educators and staff within your organization full access to chat, calling and meetings through Microsoft Teams.</span></span> |
|<span data-ttu-id="0ed86-189">**Education_PrimaryStudent**</span><span class="sxs-lookup"><span data-stu-id="0ed86-189">**Education_PrimaryStudent**</span></span>| <span data-ttu-id="0ed86-190">小学生</span><span class="sxs-lookup"><span data-stu-id="0ed86-190">Primary school aged students</span></span>  | <span data-ttu-id="0ed86-191">教育機関における小学生の場合、Microsoft Teams 内での更なる制限が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ed86-191">Younger, primary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="0ed86-192">この一連のポリシーおよびポリシー設定を使用して、会議の作成と管理、チャット管理、個人的な通話などの機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-192">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="0ed86-193">**Education_SecondaryStudent**</span><span class="sxs-lookup"><span data-stu-id="0ed86-193">**Education_SecondaryStudent**</span></span>| <span data-ttu-id="0ed86-194">中学生</span><span class="sxs-lookup"><span data-stu-id="0ed86-194">Secondary school aged students</span></span> | <span data-ttu-id="0ed86-195">教育機関における中学生の場合、Microsoft Teams 内での更なる制限が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ed86-195">Secondary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="0ed86-196">この一連のポリシーおよびポリシー設定を使用して、会議の作成と管理、チャット管理、個人的な通話などの機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-196">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="0ed86-197">**Education_HigherEducationStudent**</span><span class="sxs-lookup"><span data-stu-id="0ed86-197">**Education_HigherEducationStudent**</span></span>| <span data-ttu-id="0ed86-198">高校生</span><span class="sxs-lookup"><span data-stu-id="0ed86-198">Higher education students</span></span> | <span data-ttu-id="0ed86-199">教育機関における高校生の場合、小中学生に比べて制限は少なくなりますが、ある程度の制限が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ed86-199">Higher education students within your intuition may need fewer limits than younger students, but some limitations may be recommended.</span></span> <span data-ttu-id="0ed86-200">この一連のポリシーおよびポリシー設定のセットを使用して、組織内でのチャット、通話、会議へのアクセス権を与えることができます。ただし、学生が外部参加者と共に Microsoft Teams を使用する方法を制限します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-200">You can use this set of policies and policy settings to give access to chat, calling, and meetings within your  organization, but limit how your students use Microsoft Teams with external participants.</span></span> |
|<span data-ttu-id="0ed86-201">**Education_PrimaryTeacher_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="0ed86-201">**Education_PrimaryTeacher_RemoteLearning**</span></span>| <span data-ttu-id="0ed86-202">教師およびスタッフ</span><span class="sxs-lookup"><span data-stu-id="0ed86-202">Educators and staff</span></span> | <span data-ttu-id="0ed86-203">小学校教師に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="0ed86-203">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span> |
|<span data-ttu-id="0ed86-204">**Education_PrimaryStudent_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="0ed86-204">**Education_PrimaryStudent_RemoteLearning**</span></span>| <span data-ttu-id="0ed86-205">小学生</span><span class="sxs-lookup"><span data-stu-id="0ed86-205">Primary school aged students</span></span>| <span data-ttu-id="0ed86-206">小学生に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="0ed86-206">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>
|||

:::image type="content" source="media/edu-policy-packages-list.png" alt-text="ポリシー パッケージ ページと選択するポリシーパッケージの一覧。":::

<span data-ttu-id="0ed86-208">ポリシー パッケージにリンクされているポリシーを識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-208">Each individual policy is given the name of the policy package so you can identify policies linked to a policy package.</span></span> <span data-ttu-id="0ed86-209">たとえば、教育機関の教師に Education_Teacher ポリシー パッケージを割り当てると、パッケージ内の各ポリシーに対して Education_Teacher という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-209">For example, when you assign the Education_Teacher policy package to educators in your educational institution, a policy named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher ポリシー パッケージのスクリーンショット](media/policy-packages-education_teacher.png)

> [!NOTE]
> <span data-ttu-id="0ed86-211">教師と管理サポート スタッフが異なるポリシーを必要としていると判断した場合は、既存のパッケージを転用できます。現在使用していないパッケージを特定し、そのグループに合わせて設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-211">If you decide that educators and administrative support staff need different policies, you can repurpose an existing package: identify a package you aren't currently using and change the settings to be appropriate for that group.</span></span> <span data-ttu-id="0ed86-212">どのグループにどのパッケージがあるかを確認することが必要になる場合がありますが、これはパッケージの転用における唯一の障害です。</span><span class="sxs-lookup"><span data-stu-id="0ed86-212">You might have to make a note to yourself which group has which package, but that's the only impediment to repurposing a package.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="0ed86-213">ポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="0ed86-213">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="0ed86-214">表示</span><span class="sxs-lookup"><span data-stu-id="0ed86-214">View</span></span>

<span data-ttu-id="0ed86-215">パッケージを割り当てる前に、ポリシー パッケージ内の各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-215">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="0ed86-216">Microsoft Teams 管理センターの左側のナビゲーションで、[ **ポリシーパッケージ** ] を選択し、パッケージ名を選択して、ポリシー名を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-216">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="0ed86-217">事前に定義された値が組織に適しているかどうか、または組織のニーズに基づいてより厳しくあるいは緩めにユーザーをカスタマイズする必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-217">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="0ed86-218">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="0ed86-218">Customize</span></span>

<span data-ttu-id="0ed86-219">組織のニーズに合わせてポリシー パッケージのポリシーの設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="0ed86-219">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="0ed86-220">ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-220">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="0ed86-221">ポリシー パッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターでポリシー パッケージを選び、編集するポリシーの名前を選択して、[ **編集** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-221">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="0ed86-222">ポリシー パッケージを割り当てると、パッケージ内のポリシーの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-222">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="0ed86-223">詳細については、[「ポリシー パッケージのポリシーをカスタマイズする」](manage-policy-packages.md#customize-policies-in-a-policy-package)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ed86-223">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="0ed86-224">割り当て</span><span class="sxs-lookup"><span data-stu-id="0ed86-224">Assign</span></span>

<span data-ttu-id="0ed86-225">ユーザーにポリシー パッケージを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="0ed86-225">Assign the policy package to users.</span></span> <span data-ttu-id="0ed86-226">ユーザーにポリシーが割り当てられている場合は、別のポリシーを割り当てると、最新の割り当てが優先されます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-226">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="0ed86-227">1 人または複数のユーザーにポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="0ed86-227">Assign a policy package to one or several users</span></span>

<span data-ttu-id="0ed86-228">1 人または複数のユーザーにポリシー パッケージを割り当てるには、Microsoft Teams 管理センターの左側のナビゲーションから、[ **ポリシー パッケージ** ] に移動し、[ **ユーザーの管理** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-228">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![管理センターでポリシー パッケージを割り当てる方法のスクリーンショット](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="0ed86-230">詳細については、[「ポリシー パッケージを割り当てる」](manage-policy-packages.md#assign-a-policy-package)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ed86-230">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="0ed86-231">ユーザーにポリシーが割り当てられている場合は、別のポリシーを割り当てると、最新の割り当てが優先されます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-231">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="0ed86-232">ポリシー パッケージをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="0ed86-232">Assign a policy package to a group</span></span>

<span data-ttu-id="0ed86-233">**この機能はプライベート プレビューです**</span><span class="sxs-lookup"><span data-stu-id="0ed86-233">**This feature is in private preview**</span></span>

<span data-ttu-id="0ed86-234">グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-234">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="0ed86-235">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-235">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="0ed86-236">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-236">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="0ed86-237">この方法は、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-237">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="0ed86-238">詳細については、[「グループにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-group)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ed86-238">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="0ed86-239">ポリシー パッケージを多数 (一群) のユーザー セットに割り当てる</span><span class="sxs-lookup"><span data-stu-id="0ed86-239">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="0ed86-240">バッチ ポリシーパッケージの割り当てを使用して、多数のユーザー セットに同時にポリシーパッケージを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-240">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="0ed86-241">[New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) コマンドレットを使用して、割り当てたい一群のユーザーおよびポリシー パッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="0ed86-241">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="0ed86-242">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-242">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="0ed86-243">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-243">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="0ed86-244">ユーザーをオブジェクト ID、UPN、SIP アドレス、またはメール アドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="0ed86-244">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="0ed86-245">詳細については、[「一群のユーザーにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ed86-245">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="policies-that-should-be-assigned-for-student-safety"></a><span data-ttu-id="0ed86-246">学生の安全を確保するために割り当てるべきポリシー</span><span class="sxs-lookup"><span data-stu-id="0ed86-246">Policies that should be assigned for student safety</span></span>

<span data-ttu-id="0ed86-247">環境内の学生を保護するために必要な手順の詳細については、「[遠隔教育に Teams を使用している間、学生を安全に保つ](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)」を注意深く確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ed86-247">For more information on the steps you need to take to protect students in your environment, carefully review [Keeping students safe while using Teams for distance learning](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8).</span></span>
