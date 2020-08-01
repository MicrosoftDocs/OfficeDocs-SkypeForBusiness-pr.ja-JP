---
title: 学校の大規模なユーザーセットにポリシーを割り当てる
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: グループメンバーシップに基づいて教育機関の多数のユーザーにポリシーを割り当てる方法、またはリモート school (teleschool、tele) 目的で直接バッチの割り当てを行う方法について説明します。
f1keywords: ''
ms.openlocfilehash: 0b4fd804b51fef9537d30230aed400bb0cb7e0aa
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534133"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="6ba92-103">学校の大規模なユーザーセットにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6ba92-103">Assign policies to large sets of users in your school</span></span>

> [!NOTE]
> <span data-ttu-id="6ba92-104">Microsoft Teams でポリシーを割り当てる方法については、「 [Teams でユーザーにポリシーを割り当てる](assign-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="6ba92-105">概要</span><span class="sxs-lookup"><span data-stu-id="6ba92-105">Overview</span></span>

<span data-ttu-id="6ba92-106">学生や教師が Microsoft Teams のさまざまな機能にアクセスできるようにする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="6ba92-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="6ba92-107">ライセンスの種類によって組織内のユーザーをすばやく特定し、適切なポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="6ba92-108">このチュートリアルでは、学校の大規模なユーザーセットに会議ポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="6ba92-109">Microsoft Teams 管理センターと PowerShell を使用してポリシーを割り当てることができます。両方の方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="6ba92-110">ユーザーがメンバーになっているセキュリティグループまたはユーザーが、バッチポリシーの割り当てを使用して、ユーザーが直接ユーザーに所属するセキュリティグループに会議ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="6ba92-111">次の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-111">You'll learn how to:</span></span>

- <span data-ttu-id="6ba92-112">**[ポリシーの割り当てをグループに](#assign-a-policy-to-a-group)使用して、会議ポリシーをセキュリティグループに割り当てる (推奨)**</span><span class="sxs-lookup"><span data-stu-id="6ba92-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="6ba92-113">この方法では、グループメンバーシップに基づいてポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="6ba92-114">セキュリティグループまたは配布リストにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="6ba92-115">メンバーがグループに追加またはグループから削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="6ba92-116">新しいユーザーのポリシーを管理する時間を短縮したり、ユーザーの役割が変更されたりするため、この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6ba92-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="6ba92-117">この方法は、最大5万ユーザーのグループに最適ですが、大規模なグループでも動作します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="6ba92-118">**[バッチポリシーの割り当て](assign-policies.md#assign-a-policy-to-a-batch-of-users)を使用して、ユーザーに対して直接会議ポリシーを割り当てることが**できます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="6ba92-119">一度に最大5000ユーザーのポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="6ba92-120">5000を超えるユーザーがいる場合は、複数のバッチを送信できます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="6ba92-121">この方法では、新しいユーザーがいる場合は、バッチ割り当てを再実行して、これらの新規ユーザーにポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba92-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="6ba92-122">ユーザーは、カスタムポリシーを作成して割り当てることがない限り、チームポリシーの種類に対してグローバル (組織全体の既定の) ポリシーを自動的に取得することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="6ba92-123">学生の人口は、多くの場合、多くの場合、最も制限の厳しいユーザーであるため、次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6ba92-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="6ba92-124">プライベートチャットや会議のスケジュールなどのコア機能を利用できるようにするカスタムポリシーを作成し、そのポリシーをスタッフや教師に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="6ba92-125">ユーザー設定のポリシーをスタッフや教師に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="6ba92-126">グローバル (組織全体の既定) ポリシーを編集して適用し、学生の機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="6ba92-127">グローバルポリシーは、ユーザー設定のポリシーを作成して、それをスタッフや教師に割り当てるまで、学校のすべてのユーザーに適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="6ba92-128">このチュートリアルでは、学生がグローバル会議ポリシーを取得し、EducatorMeetingPolicy という名前のユーザー設定の会議ポリシーをスタッフと教師に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="6ba92-129">このグローバルポリシーを編集して学生の会議の設定を変更し、スタッフや教師の会議の動作を定義する[カスタムポリシーを作成](policy-packages-edu.md)していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="6ba92-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![Teams 管理センターの [会議のポリシー] ページのスクリーンショット](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="6ba92-131">グループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6ba92-131">Assign a policy to a group</span></span>

<span data-ttu-id="6ba92-132">次の手順に従って、スタッフと教師のセキュリティグループを作成し、EducatorMeetingPolicy という名前のカスタム会議ポリシーをそのセキュリティグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="6ba92-133">使用を開始する前に</span><span class="sxs-lookup"><span data-stu-id="6ba92-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ba92-134">ポリシーをグループに割り当てると、ポリシーの割り当ては優先順位の規則に従ってグループのメンバーに伝達されます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="6ba92-135">たとえば、ユーザーに直接ポリシーが割り当てられている場合 (個別またはバッチ割り当て経由)、そのポリシーは、グループから継承されたポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="6ba92-136">これは、ユーザーが直接割り当てた会議ポリシーを持っている場合は、ユーザーがセキュリティグループから会議ポリシーを継承する前に、そのユーザーからその会議ポリシーを削除する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="6ba92-137">作業を始める前に、[優先順位の規則](assign-policies.md#precedence-rules)とグループの[割り当ての順位](assign-policies.md#group-assignment-ranking)を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="6ba92-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="6ba92-138">**[グループへのポリシーの割り当てについて知っておく必要が](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)ある概念を読んで理解している**ことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="6ba92-139">スタッフおよび教師がセキュリティグループから会議ポリシーを継承できるようにするには、次のすべての手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba92-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="6ba92-140">[セキュリティグループを作成](#create-security-groups)します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="6ba92-141">[セキュリティグループにポリシーを割り当て](#assign-a-policy-to-a-security-group)ます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="6ba92-142">[ユーザーに直接割り当てられたポリシーを削除](#remove-a-policy-that-was-directly-assigned-to-users)します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="6ba92-143">セキュリティグループを作成する</span><span class="sxs-lookup"><span data-stu-id="6ba92-143">Create security groups</span></span>

<span data-ttu-id="6ba92-144">最初に、スタッフと教師のセキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="6ba92-145">[School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS) を使用すると、学校で[セキュリティグループの教師と学生を簡単に作成](https://docs.microsoft.com/SchoolDataSync/edu-security-groups)できます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-145">With [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="6ba92-146">SDS を使用して、学校のポリシーを管理するために必要なセキュリティグループを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6ba92-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="6ba92-147">使用している環境に SDS を展開できない場合は、[次の PowerShell スクリプト](scripts/powershell-script-security-groups-edu.md)を使用して、教職員用ライセンスが割り当てられているすべての従業員と、学生用ライセンスが割り当てられているすべての学生用に、2つのセキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="6ba92-148">グループを最新の状態に維持するには、このスクリプトを定期的に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba92-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="6ba92-149">セキュリティグループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6ba92-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6ba92-150">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="6ba92-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="6ba92-151">現時点では、Microsoft Teams 管理センターを使用したグループへのポリシーの割り当ては、Teams の通話ポリシー、Teams の通話パークポリシー、チームポリシー、Teams live イベントポリシー、teams 会議ポリシー、および Teams のメッセージングポリシーでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="6ba92-152">その他のポリシーの種類については、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="6ba92-153">Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="6ba92-154">[**グループポリシーの割り当て**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="6ba92-155">[**グループの追加**] を選択し、[**ポリシーをグループに割り当てる**] ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6ba92-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![会議のポリシーが表示されている [設定の編集] ウィンドウのスクリーンショット](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="6ba92-157">**[グループの選択**] ボックスで、スタッフと教師が含まれているセキュリティグループを検索して追加します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="6ba92-158">**[ランクの選択**] ボックスに「 **1**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="6ba92-159">[**ポリシーの選択**] ボックスで、[ **EducatorMeetingPolicy**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="6ba92-160">[**適用**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-160">Select **Apply**.</span></span>

<span data-ttu-id="6ba92-161">グループポリシーの割り当てを削除するには、[ポリシー] ページの [**グループポリシーの割り当て**] タブで、グループの割り当てを選択し、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="6ba92-162">グループの割り当ての順位を変更するには、最初にグループポリシーの割り当てを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba92-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="6ba92-163">次に、上記の手順に従って、ポリシーをグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="6ba92-164">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="6ba92-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="6ba92-165">現在、PowerShell を使用したグループへのポリシーの割り当ては、すべてのチームポリシーの種類では使用できません。</span><span class="sxs-lookup"><span data-stu-id="6ba92-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="6ba92-166">サポートされているポリシーの種類の一覧については、「[新しい-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-166">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="6ba92-167">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="6ba92-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="6ba92-168">次を実行して[Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールします (まだインストールされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="6ba92-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="6ba92-169">バージョン1.0.5 以降をインストールしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6ba92-170">Teams に接続してセッションを開始するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="6ba92-171">メッセージが表示されたら、管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="6ba92-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="6ba92-172">グループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6ba92-172">Assign a policy to a group</span></span>

<span data-ttu-id="6ba92-173">次を実行して、EducatorMeetingPolicy という名前の会議ポリシーを、スタッフと教師が含まれているセキュリティグループに割り当て、割り当ての順位を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="6ba92-174">オブジェクト Id、セッション開始プロトコル (SIP) アドレス、またはメールアドレスを使用して、セキュリティグループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="6ba92-175">この例では、メールアドレス (staff-faculty@contoso.com) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="6ba92-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="6ba92-176">ユーザーに直接割り当てられたポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="6ba92-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="6ba92-177">ユーザーに直接ポリシーが割り当てられている場合 (個別に、またはバッチ割り当てによって)、ポリシーが優先されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="6ba92-178">つまり、ユーザーに直接割り当てられた会議ポリシーがある場合は、ユーザーがセキュリティグループから会議ポリシーを継承できるようにするには、そのユーザーからその会議ポリシーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba92-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="6ba92-179">詳細については、「[グループに対するポリシーの割り当てについて知っ](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)ておくべきこと」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="6ba92-180">この手順に従って、スタッフと教師に直接割り当てられた会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="6ba92-181">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="6ba92-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="6ba92-182">次を実行して[Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールします (まだインストールされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="6ba92-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="6ba92-183">バージョン1.0.5 以降をインストールしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6ba92-184">Teams に接続してセッションを開始するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="6ba92-185">メッセージが表示されたら、Azure AD への接続に使用したのと同じ管理者資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="6ba92-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="6ba92-186">ユーザーに直接割り当てられたポリシーの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="6ba92-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="6ba92-187">直接ポリシーを割り当てたユーザーから会議ポリシーを削除するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="6ba92-188">ユーザーは、メールアドレスまたはオブジェクト ID で指定できます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="6ba92-189">この例では、ユーザーのメールアドレスで指定されたユーザーから会議ポリシーが削除されています。</span><span class="sxs-lookup"><span data-stu-id="6ba92-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="6ba92-190">この例では、会議のポリシーが、user_ids.txt という名前のテキストファイルのユーザーリストから削除されています。</span><span class="sxs-lookup"><span data-stu-id="6ba92-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span> 

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="6ba92-191">グループのポリシー割り当てを取得する</span><span class="sxs-lookup"><span data-stu-id="6ba92-191">Get policy assignments for a group</span></span>

<span data-ttu-id="6ba92-192">特定のセキュリティグループに割り当てられているポリシーをすべて表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="6ba92-193">グループは、その SIP アドレスまたはメールアドレスがポリシーの割り当てに使用されていた場合でも、常にグループ Id によって一覧表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-193">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="6ba92-194">ユーザーに割り当てられているポリシーを取得する</span><span class="sxs-lookup"><span data-stu-id="6ba92-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="6ba92-195">特定のユーザーに割り当てられているすべてのポリシーを表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="6ba92-196">次の例は、reda@contoso.com に割り当てられているポリシーを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6ba92-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="6ba92-197">ユーザーのバッチにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6ba92-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="6ba92-198">次の手順に従って、EducatorMeetingPolicy という名前のカスタム会議ポリシーを、自分のスタッフと教師に一括して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6ba92-199">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="6ba92-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="6ba92-200">Azure AD PowerShell for Graph モジュールと Teams PowerShell モジュールに接続する</span><span class="sxs-lookup"><span data-stu-id="6ba92-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="6ba92-201">この記事の手順を実行する前に、Graph モジュール用の Azure AD PowerShell (割り当てられているライセンスによってユーザーを識別する) と Microsoft Teams PowerShell モジュール (これらのユーザーにポリシーを割り当てる) をインストールして接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba92-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="6ba92-202">Graph モジュール用 Azure AD PowerShell にインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="6ba92-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="6ba92-203">昇格された Windows PowerShell コマンドプロンプト (管理者として Windows PowerShell を実行) を開き、次のコマンドを実行して、Azure Active Directory PowerShell for Graph モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6ba92-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="6ba92-204">Azure AD に接続するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="6ba92-205">メッセージが表示されたら、管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="6ba92-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="6ba92-206">詳細については、「 [Graph の Azure Active Directory PowerShell で接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="6ba92-207">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="6ba92-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="6ba92-208">次を実行して[Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールします (まだインストールされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="6ba92-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="6ba92-209">バージョン1.0.5 以降をインストールしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6ba92-210">Teams に接続してセッションを開始するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="6ba92-211">メッセージが表示されたら、Azure AD への接続に使用したのと同じ管理者資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="6ba92-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="6ba92-212">ユーザーを特定する</span><span class="sxs-lookup"><span data-stu-id="6ba92-212">Identify your users</span></span>

<span data-ttu-id="6ba92-213">最初に、次を実行して、ライセンスの種類別にスタッフと教師を特定します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="6ba92-214">これは、組織で使用されている Sku を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="6ba92-215">次に、教職員の SKU が割り当てられているスタッフと教師を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="6ba92-216">戻り値:</span><span class="sxs-lookup"><span data-stu-id="6ba92-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="6ba92-217">この例では、教職員ライセンスの SkuId が "e97c048c-37a4-45fb-ab50-922fbf07a370" であることが出力されます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="6ba92-218">教育機関の sku と SKU Id の一覧については、「[教育機関向けリファレンス](sku-reference-edu.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="6ba92-219">次に、このライセンスを所有しているユーザーを特定し、それらをすべてまとめて収集するために、次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="6ba92-220">ポリシーをまとめて割り当てる</span><span class="sxs-lookup"><span data-stu-id="6ba92-220">Assign a policy in bulk</span></span>

<span data-ttu-id="6ba92-221">次に、適切なポリシーをユーザーにまとめて割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="6ba92-222">ポリシーの割り当てまたは更新ができるユーザーの最大数は、一度に5000です。</span><span class="sxs-lookup"><span data-stu-id="6ba92-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="6ba92-223">たとえば、5000のスタッフと教師を超えている場合は、複数のバッチを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba92-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="6ba92-224">次を実行して、EducatorMeetingPolicy という名前のカスタム会議ポリシーを、スタッフと教師に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="6ba92-225">TeamsMessagingPolicy などの別のポリシータイプを一括で割り当てるには、割り当てるポリシーとポリシー名に変更する必要があり ```PolicyType``` ```PolicyName``` ます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="6ba92-226">一括割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="6ba92-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="6ba92-227">各一括割り当てでは、操作 ID が返されます。この ID を使用して、ポリシー割り当ての進捗状況を追跡したり、発生する可能性のあるエラーを特定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="6ba92-228">たとえば、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="6ba92-229">バッチ処理の各ユーザーの割り当て状態を表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="6ba92-230">各ユーザーの詳細がプロパティに表示され ```UserState``` ます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="6ba92-231">5000を超えるユーザーがいる場合にポリシーを一括で割り当てる</span><span class="sxs-lookup"><span data-stu-id="6ba92-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="6ba92-232">まず、次の手順を実行して、所有しているスタッフと教師の数を確認します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="6ba92-233">ユーザー Id のリスト全体を指定する代わりに、次のようにして最初の5000を指定し、その後に次の5000を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="6ba92-234">ユーザー Id の範囲は、すべてのユーザーのリストに到達するまで変更できます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="6ba92-235">たとえば、 ```$faculty[0..4999``` 最初のバッチに対しては enter、2番目のバッチには、3番目のバッチに対してを使用し ```$faculty[5000..9999``` ```$faculty[10000..14999``` ます。</span><span class="sxs-lookup"><span data-stu-id="6ba92-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="6ba92-236">ユーザーに割り当てられているポリシーを取得する</span><span class="sxs-lookup"><span data-stu-id="6ba92-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="6ba92-237">特定のユーザーに割り当てられているすべてのポリシーを表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba92-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="6ba92-238">次の例は、hannah@contoso.com に割り当てられているポリシーを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6ba92-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="6ba92-239">FAQ</span><span class="sxs-lookup"><span data-stu-id="6ba92-239">FAQ</span></span>

<span data-ttu-id="6ba92-240">**私はチームの PowerShell については詳しくありません。詳細情報はどこで入手できますか?**</span><span class="sxs-lookup"><span data-stu-id="6ba92-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="6ba92-241">PowerShell を使用してチームを管理する方法の概要については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="6ba92-242">この記事で使用されているコマンドレットの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba92-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="6ba92-243">新しい CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="6ba92-243">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="6ba92-244">CsGroupPolicyAssignment の取得</span><span class="sxs-lookup"><span data-stu-id="6ba92-244">Get-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="6ba92-245">新規-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="6ba92-245">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="6ba92-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="6ba92-246">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="6ba92-247">CsUserPolicyAssignment を取得する</span><span class="sxs-lookup"><span data-stu-id="6ba92-247">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="6ba92-248">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ba92-248">Related topics</span></span>

- [<span data-ttu-id="6ba92-249">ユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6ba92-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="6ba92-250">教育機関向けのチームポリシーとポリシーパッケージ</span><span class="sxs-lookup"><span data-stu-id="6ba92-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="6ba92-251">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="6ba92-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
