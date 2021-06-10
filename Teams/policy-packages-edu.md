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
ms.openlocfilehash: a23c54003f700b3d6dc3e0c45cbbc9ee42a311ed
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796841"
---
# <a name="teams-policies-and-policy-packages-for-education"></a><span data-ttu-id="a2752-103">教育機関向け Teams ポリシーおよびポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="a2752-103">Teams policies and policy packages for Education</span></span>

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> <span data-ttu-id="a2752-104">Microsoft Teams のポリシーの大規模な事例については、「[Microsoft Teams でユーザーにポリシーを割り当てる](assign-policies.md)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="a2752-104">For the larger story on policies in Microsoft Teams, please review [Assign policies to your users in Microsoft Teams](assign-policies.md).</span></span>

## <a name="admins-getting-started-with-microsoft-teams-policy-management"></a><span data-ttu-id="a2752-105">管理者: Microsoft Teams のポリシー管理の概要</span><span class="sxs-lookup"><span data-stu-id="a2752-105">Admins: Getting started with Microsoft Teams policy management</span></span>

<span data-ttu-id="a2752-106">Microsoft Teams を使用すると、ユーザーはオンライン会議やライブ イベントへの参加、チャット、通話、アプリの使用などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a2752-106">Microsoft Teams allows users to do things like attend online meetings or live events, chat, make calls, and use apps.</span></span> <span data-ttu-id="a2752-107">適切な Microsoft Teams 管理ポリシーを設定することは、Teams が学生にとって安全な学習環境であることを保証するための重要なステップです。</span><span class="sxs-lookup"><span data-stu-id="a2752-107">Setting the right Microsoft Teams admin policies is a critical step in ensuring that Teams is a safe learning environment for students.</span></span> <span data-ttu-id="a2752-108">管理者は、ポリシーを使用して、教育機関のユーザーが利用できる Teams 機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="a2752-108">As an admin, you can use policies to control the Teams features that are available to users in your educational institute.</span></span> <span data-ttu-id="a2752-109">ほとんどの場合、環境を安全に保つために、学生と教師の両方のポリシーを調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2752-109">In most cases, policies must be adjusted for both students and educators to keep the environment safe.</span></span>  

<span data-ttu-id="a2752-110">Microsoft Teams 内の主なポリシー領域の一覧は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a2752-110">Here's a list of the main policy areas you will find in Microsoft Teams.</span></span> <span data-ttu-id="a2752-111">各領域のポリシーとそれらが制御する機能の詳細については、以下のリンクを使用してください:</span><span class="sxs-lookup"><span data-stu-id="a2752-111">To learn more about the policies in each area and the capabilities they control, use the links below:</span></span>

- [<span data-ttu-id="a2752-112">会議</span><span class="sxs-lookup"><span data-stu-id="a2752-112">Meetings</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="a2752-113">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="a2752-113">Live events</span></span>](teams-live-events/configure-teams-live-events.md)
- [<span data-ttu-id="a2752-114">通話</span><span class="sxs-lookup"><span data-stu-id="a2752-114">Calling</span></span>](teams-calling-policy.md) 
- <span data-ttu-id="a2752-115">[メッセージング](messaging-policies-in-teams.md) </span><span class="sxs-lookup"><span data-stu-id="a2752-115">[Messaging](messaging-policies-in-teams.md)</span></span>
- [<span data-ttu-id="a2752-116">Teams</span><span class="sxs-lookup"><span data-stu-id="a2752-116">Teams</span></span>](teams-policies.md)
- [<span data-ttu-id="a2752-117">アプリのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a2752-117">App permissions</span></span>](teams-app-permission-policies.md)

:::image type="content" source="media/edu-admin-center-users.png" alt-text="ポリシーが適用されているユーザーのスクリーンショット。":::

<span data-ttu-id="a2752-119">管理者の資格情報でサインインすることにより、[Microsoft Teams 管理センター](https://admin.teams.microsoft.com) で、Teams のすべてのポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a2752-119">You can manage all Teams policies in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) by signing in with your admin credentials.</span></span>

### <a name="where-to-find-microsoft-teams-policies"></a><span data-ttu-id="a2752-120">Microsoft Teams ポリシーへのアクセス方法</span><span class="sxs-lookup"><span data-stu-id="a2752-120">Where to find Microsoft Teams policies</span></span>

<span data-ttu-id="a2752-p103">Teams 管理センターにログインすると、Teams 管理センターの左側のナビゲーションにある [ポリシー] オプションをクリックして、管理する必要がある Teams のあらゆる領域のポリシー設定に移動できます。メッセージング ポリシーの場所のスクリーンショットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a2752-p103">Once you've logged into the Teams admin center, you'll be able to go to the policy settings for any area of Teams you need to manage, by clicking on the policy option in the left hand navigation of the Teams admin center. We've included a screenshot of the location of the messaging policies.</span></span>

:::image type="content" source="media/edu-messaging-policies.png" alt-text="Teams 管理センター内のメッセージング ポリシーの場所。":::

### <a name="how-to-create-and-update-a-policy-definition"></a><span data-ttu-id="a2752-124">ポリシー定義を作成して更新する方法</span><span class="sxs-lookup"><span data-stu-id="a2752-124">How to create and update a policy definition</span></span>

<span data-ttu-id="a2752-125">ユーザーにポリシーを割り当てる前に、Teams を使って、各機能領域のポリシー定義を追加および作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2752-125">Before you assign policies to your users, you need to first add and create your policy definitions for each capability area with Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="a2752-126">学生と教師には、異なるポリシー定義を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2752-126">We recommend that you set different policy definitions for your students and educators.</span></span>

<span data-ttu-id="a2752-127">既定では、すべての新しいユーザー (学生または教師) に各機能領域に対してグローバル (組織全体の既定) ポリシー定義が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a2752-127">By default, every new user (student or educator) will be assigned the Global (Org-wide default) policy definition for each capability area.</span></span> <span data-ttu-id="a2752-128">最も厳密なポリシー定義のセットには、グローバル （組織全体の既定） を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2752-128">We recommend that you use the Global (Org-wide default) for your strictest set of policy definitions.</span></span> <span data-ttu-id="a2752-129">ほとんどの場合、このより厳密なポリシー セットは学生により適しています。</span><span class="sxs-lookup"><span data-stu-id="a2752-129">In most cases, this stricter policy set will be more appropriate for students.</span></span> <span data-ttu-id="a2752-130">このようにグローバル （組織全体の既定） ポリシー定義を使用すると、新しいユーザーがテナントに追加されたときに最も厳しい制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a2752-130">Using your Global (Org-wide default) policy definition in this way will ensure that new users will have the tightest restrictions when they are added to your tenant.</span></span> <span data-ttu-id="a2752-131">このガイダンスに従うには、次の手順に従うことをお勧めします:</span><span class="sxs-lookup"><span data-stu-id="a2752-131">To adhere to this guidance, we recommend you follow these steps:</span></span>

1. <span data-ttu-id="a2752-132">チームの機能領域ごとに、教師のニーズに合ったポリシー値を使用してカスタム ポリシー定義を作成します （これがないと、教師は、グローバル （組織全体の既定） ポリシー定義で定義されているのと同じ制限付きアクセスを学生に与えることになります）。</span><span class="sxs-lookup"><span data-stu-id="a2752-132">Create a custom policy definition for each Teams capability area with policy values that are fitting for your educators' needs (without this, educators will have the same restricted access as your students as defined within the Global (Org-wide default) policy definition).</span></span>

1. <span data-ttu-id="a2752-133">これらの新しいカスタム ポリシー定義を教師に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a2752-133">Assign these new custom policy definitions to your educators.</span></span>

1. <span data-ttu-id="a2752-134">学生に適した値を使用して、各機能領域のグローバル （組織全体の既定） ポリシー定義を編集します。</span><span class="sxs-lookup"><span data-stu-id="a2752-134">Edit the Global (Org-wide default) policy definitions for each capability area with values that are appropriate for your students.</span></span>

1. <span data-ttu-id="a2752-135">グローバル （組織全体の既定） ポリシー定義は、他のポリシー定義が割り当てられていない限り、学生に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a2752-135">The Global (Org-wide default) policy definitions will be applied to your students as long as they have no other policy definitions assigned.</span></span>


<span data-ttu-id="a2752-136">ポリシー定義を作成または編集するには、作業するポリシー機能領域 (メッセージング ポリシーなど) に移動します。</span><span class="sxs-lookup"><span data-stu-id="a2752-136">To create or edit policy definitions, go to the policy capability area you want to work in (for example, Messaging policies).</span></span> <span data-ttu-id="a2752-137">**[追加]** を選択して、新しいカスタム ポリシー定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="a2752-137">Select **Add** to create a new custom policy definition.</span></span> <span data-ttu-id="a2752-138">既存のポリシー定義を変更するには、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2752-138">To change an existing policy definition, select **Edit**.</span></span>

:::image type="content" source="media/edu-messaging-policies-add-closeup.png" alt-text="[追加] ボタンを表示した状態での [メッセージング ポリシー] セクションのクローズアップ。":::

<span data-ttu-id="a2752-140">ポリシー定義を追加するか編集するかを選択したどうかにかかわらず、このポリシー領域に関連付けられているすべてのポリシー オプションが一覧表示されるビューに移動します。</span><span class="sxs-lookup"><span data-stu-id="a2752-140">Whether you choose to add or edit a policy definition, you're brought to a view that lists all the policy options related to this policy area.</span></span> <span data-ttu-id="a2752-141">このリストを使用して、ポリシー定義に設定する値を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2752-141">Use this list to select what values you want set in your policy definition.</span></span>

![選んだポリシー領域に関連付けられているポリシー オプションを含むページ。](media/edu-global-policy-definition.png)

> [!IMPORTANT]
> <span data-ttu-id="a2752-143">ページから移動する前に、**[保存]** を必ず選択してください。</span><span class="sxs-lookup"><span data-stu-id="a2752-143">Don’t forget to select **Save** before you leave the page.</span></span>

### <a name="assigning-policy-definitions"></a><span data-ttu-id="a2752-144">ポリシー定義の割り当て</span><span class="sxs-lookup"><span data-stu-id="a2752-144">Assigning policy definitions</span></span> 
<span data-ttu-id="a2752-145">ポリシー定義をユーザーに割り当てるために使用できる方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="a2752-145">There are multiple methods you can use to assign policy definitions to your users.</span></span> <span data-ttu-id="a2752-146">各方法には、独自の利点と欠点があります。これは、お客様の機関のニーズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="a2752-146">Each method has its own advantages and disadvantages, which will differ depending on your institution's unique needs.</span></span>  

<span data-ttu-id="a2752-147">ほとんどの場合、グループ ポリシーの割り当てを使用して、ユーザーにポリシーを割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2752-147">In most cases, we recommend that you use group policy assignment to assign policies to your users.</span></span> <span data-ttu-id="a2752-148">この方法を使用すると、より迅速かつシームレスにポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="a2752-148">This method allows for faster and more seamless policy application.</span></span>  <span data-ttu-id="a2752-149">ポリシー定義が割り当てられているグループにユーザーを追加すると、新しいユーザーはグループのポリシーを自動的に継承します。</span><span class="sxs-lookup"><span data-stu-id="a2752-149">When a user is added to a group that has a policy definition assigned to it, the new user automatically inherits the policies of the group.</span></span>  <span data-ttu-id="a2752-150">これにより、たとえば学期の開始時や終了時に、環境に多数のユーザーが追加および削除された場合に、ポリシー管理が容易になります。</span><span class="sxs-lookup"><span data-stu-id="a2752-150">This allows for easier policy management when large numbers of users are added and removed to the environment, for example at the beginning and ending of a school term.</span></span>  

<span data-ttu-id="a2752-151">大規模な組織では、多数のユーザーにポリシーを割り当てる必要がある場合に最適なバッチ ポリシーの割り当てもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2752-151">For large organizations, we also recommend batch policy assignment, which is tailored for cases where you need to assign policies to large sets of users.</span></span> <span data-ttu-id="a2752-152">これらの適用方法の詳細については、「[学校の多数のユーザーにポリシーを割り当てる](batch-group-policy-assignment-edu.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2752-152">To learn more about these application methods, refer to [Assign policies to large sets of users in your school](batch-group-policy-assignment-edu.md).</span></span>

<span data-ttu-id="a2752-153">小規模な機関の場合、または個々の学生または教師のポリシー設定を更新する必要がある場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a2752-153">If you have a smaller institution or have a need to update an individual student or educator's policy settings, follow the instructions below.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="a2752-154">個々のユーザー レベルで指定されたポリシーの割り当ては、ユーザーに割り当てられたグループ ポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="a2752-154">Policy assignments given at the individual user level override any group policies assigned to the user.</span></span> <span data-ttu-id="a2752-155">グループ ポリシー設定を上書きする場合にのみ、個別のポリシー割り当てを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a2752-155">Ensure that you are only using individual policy assignments when you desire to override group policy settings.</span></span> 

#### <a name="how-to-assign-a-policy-definition-to-a-user"></a><span data-ttu-id="a2752-156">ユーザーにポリシー定義を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="a2752-156">How to assign a policy definition to a user</span></span>

> [!NOTE]
> <span data-ttu-id="a2752-157">ポリシー定義を割り当てると、すべてのユーザーとクライアントに反映されるのにしばらく時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2752-157">Assigning a policy definition may take a while to propagate out to all the users and clients.</span></span> <span data-ttu-id="a2752-158">Azure/M365 にユーザー アカウントを初めて作成するとき、教育機関に新しい学生が参加するときに、この操作を行うことが必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2752-158">You might want to do this when the user accounts are first created in Azure/M365, and whenever a new student joins the educational institute.</span></span>


<span data-ttu-id="a2752-159">ポリシー定義を作成または更新した後、ポリシー ページの **[ユーザーの管理]** を選択し、希望のユーザーを検索して、ポリシーを割り当てることにより、ユーザーにポリシー定義を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a2752-159">Once your policy definition is created or updated, you can assign it to a user by selecting **Manage users** on the policy page, searching for the desired user, then applying the policy.</span></span>

![[メッセージング ポリシー] ページの上部の右側にあるユーザー パネルを管理します。](media/edu-manage-users-pane.png)

<span data-ttu-id="a2752-161">また、**[ユーザー]** に移動し、ポリシーを更新するユーザーを選択し、**[ポリシー]** を選択してから **[編集]** を選択することにより、ユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a2752-161">You can also assign a policy to a user by navigating to **Users**, selecting the user you wish to update policies for, selecting **Policies**, then **Edit**.</span></span> <span data-ttu-id="a2752-162">ここから、各機能領域に対してユーザーに割り当てるポリシー定義を選択できます。</span><span class="sxs-lookup"><span data-stu-id="a2752-162">From there, you can select the policy definition you’d like to assign to the user for each capability area.</span></span>

![[割り当てられているポリシー] ページの右側にある [ユーザー ポリシーの編集] ウィンドウ。](media/edu-edit-user-policies-pane.png)

### <a name="policy-packages-in-microsoft-teams"></a><span data-ttu-id="a2752-164">Microsoft Teams のポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="a2752-164">Policy packages in Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="a2752-165">詳細については、「[Microsoft Teams でポリシー パッケージを管理する](manage-policy-packages.md)」をご確認ください。1 人のユーザーにパッケージを割り当てる方法、最大 5000 人のユーザーにパッケージを一括で割り当てる方法、各パッケージに関連付けられたポリシーの管理と更新を行う方法を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="a2752-165">For more reading, you can check out [Manage policy packages in Microsoft Teams](manage-policy-packages.md) for step by step guidance on assigning single users a package, assigning packages in bulk to up to 5000 users, and managing and updating the policies linked to each package.</span></span>

<span data-ttu-id="a2752-166">Teams 内のポリシー パッケージは、上記で説明したように事前に定義されたポリシーおよびポリシー設定を収集し、それらを教育機関内の同様の役割を持つユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a2752-166">A policy package in Teams collects predefined policies and policy settings that you learned about outlined above, and assigns them to users with similar roles in your institution.</span></span> <span data-ttu-id="a2752-167">ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="a2752-167">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="a2752-168">通常の方法では、各ユーザーにポリシーパッケージを割り当て、そのユーザー グループのニーズに合わせて、各パッケージのポリシーを再定義します。</span><span class="sxs-lookup"><span data-stu-id="a2752-168">In normal practice, you assign each of your users a policy package, and  redefine the policies in each package as needed to suit the needs of that user group.</span></span> <span data-ttu-id="a2752-169">パッケージの設定を更新すると、そのパッケージに割り当てられているすべてのユーザーが一括更新として変更されます。</span><span class="sxs-lookup"><span data-stu-id="a2752-169">When you update settings in a package, all users assigned to that package are changed as a bulk update.</span></span>

<span data-ttu-id="a2752-170">一般に、教育機関には、学生の年齢や成熟度によって異なる固有のニーズを持つ多くのユーザーが存在します。</span><span class="sxs-lookup"><span data-stu-id="a2752-170">Educational institutions in general have many users with unique needs, depending partly on the age and maturity of the students.</span></span> <span data-ttu-id="a2752-171">たとえば、教師やスタッフが Microsoft Teams にフルアクセスできるようにする一方で、安全で集中できる学習環境を構築するために、学生に対する Microsoft Teams の機能を制限したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2752-171">For example, you may want to grant educators and staff full access to Microsoft Teams, but want to limit Microsoft Teams capabilities for students to encourage a safe and focused learning environment.</span></span> <span data-ttu-id="a2752-172">教育機関コミュニティにおける異なるコーホートのニーズに基づいて、ポリシー パッケージを使用して設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="a2752-172">You can use policy packages to tailor settings based on the needs of different cohorts in your educational institute community.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="a2752-173">最初に、ポリシー パッケージの代わりに、学生に対してグローバル (組織全体の既定) ポリシー定義を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2752-173">Our primary recommendation is that you use the Global (Org-wide default) policy definition for students instead of a policy package.</span></span> <span data-ttu-id="a2752-174">これにより、組織内の新しいユーザーは常に、学生に適した最も厳格なポリシーのセットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2752-174">This ensures that new users in your organizations always have the strictest set of policies appropriate for students.</span></span> <span data-ttu-id="a2752-175">この勧告が機関のニーズを満たしていない場合は、次のいずれかの学生ポリシー パッケージが適している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2752-175">If this recommendation does not meet the needs of your institution, one of the student policy packages below may be a good alternative.</span></span> 

<span data-ttu-id="a2752-176">この記事で前述したポリシー一覧と同様に、ポリシーパッケージでは、次のようなポリシーが事前に定義されています。</span><span class="sxs-lookup"><span data-stu-id="a2752-176">Just like the policy list earlier in this article, policy packages predefine policies for:</span></span>

- <span data-ttu-id="a2752-177">会議</span><span class="sxs-lookup"><span data-stu-id="a2752-177">Meetings</span></span>
- <span data-ttu-id="a2752-178">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="a2752-178">Live events</span></span>
- <span data-ttu-id="a2752-179">通話</span><span class="sxs-lookup"><span data-stu-id="a2752-179">Calling</span></span>
- <span data-ttu-id="a2752-180">Messaging</span><span class="sxs-lookup"><span data-stu-id="a2752-180">Messaging</span></span>
- <span data-ttu-id="a2752-181">アプリのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a2752-181">App permissions</span></span>

<span data-ttu-id="a2752-182">Microsoft Teams には現在、次のポリシー パッケージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2752-182">Microsoft Teams currently includes the following policy packages:</span></span>

|<span data-ttu-id="a2752-183">Microsoft Teams 管理センターで一覧表示されるパッケージ名</span><span class="sxs-lookup"><span data-stu-id="a2752-183">Package name listed in Microsoft Teams Admin center</span></span> |<span data-ttu-id="a2752-184">以下の目的での使用に最適です</span><span class="sxs-lookup"><span data-stu-id="a2752-184">Best used for</span></span>  |<span data-ttu-id="a2752-185">説明</span><span class="sxs-lookup"><span data-stu-id="a2752-185">Description</span></span> |
|:--- |:--- |:--- |
|<span data-ttu-id="a2752-186">**Education_Teacher**</span><span class="sxs-lookup"><span data-stu-id="a2752-186">**Education_Teacher**</span></span>| <span data-ttu-id="a2752-187">教師およびスタッフ</span><span class="sxs-lookup"><span data-stu-id="a2752-187">Educators and staff</span></span>| <span data-ttu-id="a2752-188">この一連のポリシーおよびポリシー設定を使用して、Microsoft Teams を通して、組織内の教師およびスタッフがチャット、通話、会議にフルアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="a2752-188">Use this set of policies and policy settings to grant educators and staff within your organization full access to chat, calling and meetings through Microsoft Teams.</span></span> |
|<span data-ttu-id="a2752-189">**Education_PrimaryStudent**</span><span class="sxs-lookup"><span data-stu-id="a2752-189">**Education_PrimaryStudent**</span></span>| <span data-ttu-id="a2752-190">小学生</span><span class="sxs-lookup"><span data-stu-id="a2752-190">Primary school aged students</span></span>  | <span data-ttu-id="a2752-191">教育機関における小学生の場合、Microsoft Teams 内での更なる制限が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2752-191">Younger, primary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="a2752-192">この一連のポリシーおよびポリシー設定を使用して、会議の作成と管理、チャット管理、個人的な通話などの機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="a2752-192">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="a2752-193">**Education_SecondaryStudent**</span><span class="sxs-lookup"><span data-stu-id="a2752-193">**Education_SecondaryStudent**</span></span>| <span data-ttu-id="a2752-194">中学生</span><span class="sxs-lookup"><span data-stu-id="a2752-194">Secondary school aged students</span></span> | <span data-ttu-id="a2752-195">教育機関における中学生の場合、Microsoft Teams 内での更なる制限が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2752-195">Secondary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="a2752-196">この一連のポリシーおよびポリシー設定を使用して、会議の作成と管理、チャット管理、個人的な通話などの機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="a2752-196">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="a2752-197">**Education_HigherEducationStudent**</span><span class="sxs-lookup"><span data-stu-id="a2752-197">**Education_HigherEducationStudent**</span></span>| <span data-ttu-id="a2752-198">高校生</span><span class="sxs-lookup"><span data-stu-id="a2752-198">Higher education students</span></span> | <span data-ttu-id="a2752-199">教育機関における高校生の場合、小中学生に比べて制限は少なくなりますが、ある程度の制限が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2752-199">Higher education students within your intuition may need fewer limits than younger students, but some limitations may be recommended.</span></span> <span data-ttu-id="a2752-200">この一連のポリシーおよびポリシー設定のセットを使用して、組織内でのチャット、通話、会議へのアクセス権を与えることができます。ただし、学生が外部参加者と共に Microsoft Teams を使用する方法を制限します。</span><span class="sxs-lookup"><span data-stu-id="a2752-200">You can use this set of policies and policy settings to give access to chat, calling, and meetings within your  organization, but limit how your students use Microsoft Teams with external participants.</span></span> |
|<span data-ttu-id="a2752-201">**Education_PrimaryTeacher_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="a2752-201">**Education_PrimaryTeacher_RemoteLearning**</span></span>| <span data-ttu-id="a2752-202">教師およびスタッフ</span><span class="sxs-lookup"><span data-stu-id="a2752-202">Educators and staff</span></span> | <span data-ttu-id="a2752-203">小学校教師に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="a2752-203">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span> |
|<span data-ttu-id="a2752-204">**Education_PrimaryStudent_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="a2752-204">**Education_PrimaryStudent_RemoteLearning**</span></span>| <span data-ttu-id="a2752-205">小学生</span><span class="sxs-lookup"><span data-stu-id="a2752-205">Primary school aged students</span></span>| <span data-ttu-id="a2752-206">小学生に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。</span><span class="sxs-lookup"><span data-stu-id="a2752-206">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>
|||

:::image type="content" source="media/edu-policy-packages-list.png" alt-text="ポリシー パッケージ ページと選択するポリシーパッケージの一覧。":::

<span data-ttu-id="a2752-208">ポリシー パッケージにリンクされているポリシーを識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。</span><span class="sxs-lookup"><span data-stu-id="a2752-208">Each individual policy is given the name of the policy package so you can identify policies linked to a policy package.</span></span> <span data-ttu-id="a2752-209">たとえば、教育機関の教師に Education_Teacher ポリシー パッケージを割り当てると、パッケージ内の各ポリシーに対して Education_Teacher という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a2752-209">For example, when you assign the Education_Teacher policy package to educators in your educational institution, a policy named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher ポリシー パッケージのスクリーンショット](media/policy-packages-education_teacher.png)

> [!NOTE]
> <span data-ttu-id="a2752-211">教師と管理サポート スタッフが異なるポリシーを必要としていると判断した場合は、既存のパッケージを転用できます。現在使用していないパッケージを特定し、そのグループに合わせて設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="a2752-211">If you decide that educators and administrative support staff need different policies, you can repurpose an existing package: identify a package you aren't currently using and change the settings to be appropriate for that group.</span></span> <span data-ttu-id="a2752-212">どのグループにどのパッケージがあるかを確認することが必要になる場合がありますが、これはパッケージの転用における唯一の障害です。</span><span class="sxs-lookup"><span data-stu-id="a2752-212">You might have to make a note to yourself which group has which package, but that's the only impediment to repurposing a package.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="a2752-213">ポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="a2752-213">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="a2752-214">表示</span><span class="sxs-lookup"><span data-stu-id="a2752-214">View</span></span>

<span data-ttu-id="a2752-215">パッケージを割り当てる前に、ポリシー パッケージ内の各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2752-215">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="a2752-216">Microsoft Teams 管理センターの左側のナビゲーションで、[**ポリシーパッケージ**] を選択し、パッケージ名を選択して、ポリシー名を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2752-216">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="a2752-217">事前に定義された値が組織に適しているかどうか、または組織のニーズに基づいてより厳しくあるいは緩めにユーザーをカスタマイズする必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="a2752-217">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="a2752-218">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="a2752-218">Customize</span></span>

<span data-ttu-id="a2752-219">組織のニーズに合わせてポリシー パッケージのポリシーの設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="a2752-219">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="a2752-220">ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a2752-220">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="a2752-221">ポリシー パッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターでポリシー パッケージを選び、編集するポリシーの名前を選択して、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2752-221">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="a2752-222">ポリシー パッケージを割り当てると、パッケージ内のポリシーの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2752-222">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="a2752-223">詳細については、[「ポリシー パッケージのポリシーをカスタマイズする」](manage-policy-packages.md#customize-policies-in-a-policy-package)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2752-223">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="a2752-224">割り当て</span><span class="sxs-lookup"><span data-stu-id="a2752-224">Assign</span></span>

<span data-ttu-id="a2752-p124">ポリシー パッケージをユーザーに割り当てます。ユーザーにポリシーが割り当てられている場合は、別のポリシーを割り当てると、最新の割り当てが優先されます。</span><span class="sxs-lookup"><span data-stu-id="a2752-p124">Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

> [!NOTE]
> <span data-ttu-id="a2752-227">カスタム ポリシー パッケージの割り当てを受け取るには、各ユーザーに Advanced Communications アドオンが必要です。</span><span class="sxs-lookup"><span data-stu-id="a2752-227">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="a2752-228">詳細については、「[Microsoft Teams 用 Advanced Communications アドオン](/microsoftteams/teams-add-on-licensing/advanced-communications)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2752-228">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="a2752-229">1 人または複数のユーザーにポリシー パッケージを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a2752-229">Assign a policy package to one or several users</span></span>

<span data-ttu-id="a2752-230">1 人または複数のユーザーにポリシー パッケージを割り当てるには、Microsoft Teams 管理センターの左側のナビゲーションから、[**ポリシー パッケージ**] に移動し、[**ユーザーの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2752-230">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![管理センターでポリシー パッケージを割り当てる方法のスクリーンショット](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="a2752-232">詳細については、[「ポリシー パッケージを割り当てる」](manage-policy-packages.md#assign-a-policy-package)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2752-232">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="a2752-233">ユーザーにポリシーが割り当てられている場合は、別のポリシーを割り当てると、最新の割り当てが優先されます。</span><span class="sxs-lookup"><span data-stu-id="a2752-233">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="a2752-234">ポリシー パッケージをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="a2752-234">Assign a policy package to a group</span></span>

<span data-ttu-id="a2752-235">**この機能はプライベート プレビューです**</span><span class="sxs-lookup"><span data-stu-id="a2752-235">**This feature is in private preview**</span></span>

<span data-ttu-id="a2752-236">グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a2752-236">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="a2752-237">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="a2752-237">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="a2752-238">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="a2752-238">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="a2752-239">この方法は、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="a2752-239">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="a2752-240">詳細については、[「グループにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-group)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2752-240">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="a2752-241">ポリシー パッケージを多数 (一群) のユーザー セットに割り当てる</span><span class="sxs-lookup"><span data-stu-id="a2752-241">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="a2752-242">バッチ ポリシーパッケージの割り当てを使用して、多数のユーザー セットに同時にポリシーパッケージを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a2752-242">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="a2752-243">[New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) コマンドレットを使用して、割り当てたい一群のユーザーおよびポリシー パッケージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a2752-243">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="a2752-244">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a2752-244">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="a2752-245">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a2752-245">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="a2752-246">ユーザーをオブジェクト ID、UPN、SIP アドレス、またはメール アドレスで指定できます。</span><span class="sxs-lookup"><span data-stu-id="a2752-246">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="a2752-247">詳細については、[「一群のユーザーにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2752-247">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="policies-that-should-be-assigned-for-student-safety"></a><span data-ttu-id="a2752-248">学生の安全を確保するために割り当てるべきポリシー</span><span class="sxs-lookup"><span data-stu-id="a2752-248">Policies that should be assigned for student safety</span></span>

<span data-ttu-id="a2752-249">環境内の学生を保護するために必要な手順の詳細については、「[遠隔教育に Teams を使用している間、学生を安全に保つ](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)」を注意深く確認してください。</span><span class="sxs-lookup"><span data-stu-id="a2752-249">For more information on the steps you need to take to protect students in your environment, carefully review [Keeping students safe while using Teams for distance learning](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8).</span></span>
