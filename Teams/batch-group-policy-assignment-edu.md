---
title: 学校の大規模なユーザーにポリシーを割り当てる
author: cichur
ms.author: v-cichur
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
description: グループ メンバーシップに基づいて、またはリモート 学校 (teleschool、tele-school) の目的でバッチ割り当てによって、教育機関の大規模なユーザーにポリシーを割り当てる方法について説明します。
f1keywords: ''
ms.openlocfilehash: f2d36db6a96f6a9a42590ada6600ef38738b30a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092905"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="e6763-103">学校の大規模なユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6763-103">Assign policies to large sets of users in your school</span></span>

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> <span data-ttu-id="e6763-104">ポリシーの割り当てに関する詳細については、「Microsoft Teams でポリシーをユーザーに割り当てる[」をTeams。](assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e6763-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="e6763-105">概要</span><span class="sxs-lookup"><span data-stu-id="e6763-105">Overview</span></span>

<span data-ttu-id="e6763-106">学生と教師に、さまざまな機能へのアクセス権を与える必要Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="e6763-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="e6763-107">ライセンスの種類によって組織内のユーザーをすばやく特定し、適切なポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="e6763-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="e6763-108">このチュートリアルでは、学校の大規模なユーザーに会議ポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6763-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="e6763-109">管理センターと PowerShell の Microsoft Teamsを使用してポリシーを割り当て、両方の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6763-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="e6763-110">会議ポリシーは、ユーザーがメンバーであるセキュリティ グループに割り当てるか、バッチ ポリシーの割り当てによって大規模なユーザーに直接割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="e6763-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="e6763-111">次の方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="e6763-111">You'll learn how to:</span></span>

- <span data-ttu-id="e6763-112">**グループ [へのポリシーの割り当てを使用](#assign-a-policy-to-a-group) して、セキュリティ グループに会議ポリシーを割り当てる (推奨)**。</span><span class="sxs-lookup"><span data-stu-id="e6763-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="e6763-113">この方法では、グループ メンバーシップに基づいてポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="e6763-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="e6763-114">セキュリティ グループまたは配布リストにポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="e6763-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="e6763-115">メンバーがグループに追加またはグループから削除されると、そのメンバーの継承されたポリシー割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="e6763-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="e6763-116">この方法を使用することをお勧めします。これは、新しいユーザーのポリシーを管理する時間を短縮したり、ユーザーのロールが変更された場合に時間を削減したりするために使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e6763-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="e6763-117">この方法は、最大 50,000 人のユーザーのグループに最適ですが、より大きなグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="e6763-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="e6763-118">**バッチ [ポリシーの割り当てを使用](assign-policies.md#assign-a-policy-to-a-batch-of-users)して、会議ポリシーをユーザーに直接一括で割り当てる。**</span><span class="sxs-lookup"><span data-stu-id="e6763-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="e6763-119">一度に最大 5,000 人のユーザーにポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="e6763-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="e6763-120">ユーザー数が 5,000 を超える場合は、複数のバッチを送信できます。</span><span class="sxs-lookup"><span data-stu-id="e6763-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="e6763-121">この方法では、新しいユーザーが作成された場合、それらの新しいユーザーにポリシーを割り当てるバッチ割り当てを再び実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6763-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="e6763-122">Teamsでは、カスタム ポリシーを作成して割り当てない限り、Teams ポリシーの種類に対してグローバル (組織全体の既定) ポリシーが自動的に取得されます。</span><span class="sxs-lookup"><span data-stu-id="e6763-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="e6763-123">学生の人口は多くの場合、最大のユーザー セットであり、最も制限の厳しい設定を受け取る場合が多いので、次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e6763-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="e6763-124">プライベート チャットや会議のスケジュール設定などのコア機能を許可し、そのポリシーをスタッフや教師に割り当てるカスタム ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e6763-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="e6763-125">カスタム ポリシーをスタッフと教師に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e6763-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="e6763-126">グローバル (組織全体の既定) ポリシーを編集して適用し、学生の機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="e6763-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="e6763-127">カスタム ポリシーを作成してスタッフや教師に割り当てるまで、グローバル ポリシーは学校のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e6763-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="e6763-128">このチュートリアルでは、学生はグローバル会議ポリシーを取得し、EducatorMeetingPolicy という名前のカスタム会議ポリシーをスタッフと教師に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6763-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="e6763-129">グローバル ポリシーを編集して学生の会議設定を調整し、スタッフと教師の[](policy-packages-edu.md)会議エクスペリエンスを定義するカスタム ポリシーを作成したと想定しています。</span><span class="sxs-lookup"><span data-stu-id="e6763-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![管理センターの [会議ポリシー] ページTeamsスクリーンショット](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="e6763-131">ポリシーをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6763-131">Assign a policy to a group</span></span>

<span data-ttu-id="e6763-132">次の手順に従って、スタッフと教師のセキュリティ グループを作成し、そのセキュリティ グループに EducatorMeetingPolicy という名前のカスタム会議ポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6763-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="e6763-133">使用を開始する前に</span><span class="sxs-lookup"><span data-stu-id="e6763-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6763-134">グループにポリシーを割り当てると、優先順位ルールに従ってポリシーの割り当てがグループのメンバーに伝達されます。</span><span class="sxs-lookup"><span data-stu-id="e6763-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="e6763-135">たとえば、ユーザーに (個別またはバッチ割り当てによって) ポリシーが直接割り当てられている場合、そのポリシーはグループから継承されたポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e6763-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="e6763-136">また、ユーザーに直接割り当てられた会議ポリシーがある場合は、セキュリティ グループから会議ポリシーを継承する前に、その会議ポリシーをユーザーから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6763-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="e6763-137">使用を開始する前に、[優先規則](assign-policies.md#precedence-rules)と[グループ割り当てのランク付け](assign-policies.md#group-assignment-ranking)を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e6763-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="e6763-138">**グループへのポリシー割り当 [](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)** てについて知る必要がある概念を必ず読んで理解してください。</span><span class="sxs-lookup"><span data-stu-id="e6763-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="e6763-139">スタッフと教師がセキュリティ グループから会議ポリシーを継承するには、これらすべての手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6763-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="e6763-140">[セキュリティ グループ を作成します](#create-security-groups)。</span><span class="sxs-lookup"><span data-stu-id="e6763-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="e6763-141">[セキュリティ グループにポリシーを割り当てる](#assign-a-policy-to-a-security-group)。</span><span class="sxs-lookup"><span data-stu-id="e6763-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="e6763-142">[ユーザーに直接割り当てられたポリシーを削除します](#remove-a-policy-that-was-directly-assigned-to-users)。</span><span class="sxs-lookup"><span data-stu-id="e6763-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="e6763-143">セキュリティ グループを作成する</span><span class="sxs-lookup"><span data-stu-id="e6763-143">Create security groups</span></span>

<span data-ttu-id="e6763-144">まず、スタッフと教師のセキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="e6763-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="e6763-145">セキュリティ[学校データ同期](/SchoolDataSync/)(SDS) を使用すると、学校でセキュリティ グループ[の教師と学生を簡単に](/SchoolDataSync/edu-security-groups)作成できます。</span><span class="sxs-lookup"><span data-stu-id="e6763-145">With [School Data Sync](/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="e6763-146">SDS を使用して、学校のポリシーを管理するために必要なセキュリティ グループを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e6763-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="e6763-147">環境内で SDS をデプロイできない場合は、この [PowerShell](scripts/powershell-script-security-groups-edu.md) スクリプトを使用して 2 つのセキュリティ グループを作成します。1 つは、教職員のライセンスが割り当てられているすべてのスタッフと教師用、もう 1 つは学生ライセンスが割り当てられているすべての学生用です。</span><span class="sxs-lookup"><span data-stu-id="e6763-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="e6763-148">グループを最新の状態に保つには、このスクリプトを定期的に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6763-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="e6763-149">セキュリティ グループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6763-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e6763-150">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="e6763-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="e6763-151">現在、Microsoft Teams 管理センターを使用したグループへのポリシー割り当ては、Teams 通話ポリシー、Teams コール パーク ポリシー、Teams ポリシー、Teams ライブ イベント ポリシー、Teams 会議ポリシー、Teams メッセージ ポリシーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6763-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="e6763-152">他のポリシーの種類については、PowerShell を使用してください。</span><span class="sxs-lookup"><span data-stu-id="e6763-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="e6763-153">Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e6763-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="e6763-154">**グループ ポリシーの割り当て** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6763-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="e6763-155">**[グループの追加]** を選択し、**[ポリシーをグループに割り当てる]** ウィンドウで、次の操作を行います:</span><span class="sxs-lookup"><span data-stu-id="e6763-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![会議ポリシーが表示されている [設定の編集] ウィンドウのスクリーンショット](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="e6763-157">[グループ **の選択] ボックス** で、スタッフと教師を含むセキュリティ グループを検索して追加します。</span><span class="sxs-lookup"><span data-stu-id="e6763-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="e6763-158">[ランク **の選択] ボックスに\*\*\*\*「1」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="e6763-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="e6763-159">[ポリシー **の選択] ボックスで\*\*\*\*、[EducatorMeetingPolicy] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e6763-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="e6763-160">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6763-160">Select **Apply**.</span></span>

<span data-ttu-id="e6763-161">グループ ポリシーの割り当てを削除するには、ポリシー ページの **[グループ ポリシーの割り当て]** タブで、グループの割り当てを選び、**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6763-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="e6763-162">グループ割り当てのランク付けを変更するには、最初にグループ ポリシーの割り当てを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6763-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="e6763-163">次に、上記の手順に従ってポリシーをグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e6763-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="e6763-164">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="e6763-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="e6763-165">現在、PowerShell を使用したグループへのポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="e6763-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="e6763-166">サポートされているポリシー タイプの一覧については、[New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6763-166">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="e6763-167">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="e6763-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="e6763-168">PowerShell モジュールをインストールするには[Teamsを実行](https://www.powershellgallery.com/packages/MicrosoftTeams)します (まだインストールされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="e6763-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="e6763-169">バージョン 1.0.5 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6763-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="e6763-170">以下を実行して Teams に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="e6763-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="e6763-171">メッセージが表示されたら、管理者の資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="e6763-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="e6763-172">ポリシーをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6763-172">Assign a policy to a group</span></span>

<span data-ttu-id="e6763-173">次のコマンドを実行して、EducatorMeetingPolicy という名前の会議ポリシーを、スタッフと教師を含むセキュリティ グループに割り当て、割り当てのランク付けを 1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="e6763-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="e6763-174">セキュリティ グループは、オブジェクト ID、セッション開始プロトコル (SIP) アドレス、または電子メール アドレスを使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="e6763-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="e6763-175">この例では、メール アドレス (staff-faculty@contoso.com) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e6763-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="e6763-176">ユーザーに直接割り当てられたポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="e6763-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="e6763-177">ユーザーにポリシーが直接割り当てられた場合 (個別に割り当てたり、バッチ割り当てによって割り当てたりした場合)、そのポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="e6763-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="e6763-178">つまり、ユーザーに直接割り当てられた会議ポリシーがある場合は、セキュリティ グループから会議ポリシーを継承する前に、その会議ポリシーをユーザーから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6763-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="e6763-179">詳細については、「グループへのポリシー [の割り当てについて知る必要がある情報」を参照してください](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)。</span><span class="sxs-lookup"><span data-stu-id="e6763-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="e6763-180">次の手順に従って、スタッフと教師に直接割り当てられた会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e6763-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="e6763-181">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="e6763-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="e6763-182">PowerShell モジュールをインストールするには[Teamsを実行](https://www.powershellgallery.com/packages/MicrosoftTeams)します (まだインストールされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="e6763-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="e6763-183">バージョン 1.0.5 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6763-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="e6763-184">以下を実行して Teams に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="e6763-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="e6763-185">メッセージが表示されたら、Azure アカウントへの接続に使用したのと同じ管理者資格情報を使用してAD。</span><span class="sxs-lookup"><span data-stu-id="e6763-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="e6763-186">ユーザーに直接割り当てられたポリシーの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="e6763-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="e6763-187">次のコマンドを実行して、そのポリシーを直接割り当てられたユーザーから会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e6763-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="e6763-188">メール アドレスまたはオブジェクト ID でユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e6763-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="e6763-189">この例では、会議ポリシーは、メール アドレスで指定されたユーザーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e6763-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="e6763-190">この例では、会議ポリシーは、user_ids.txt という名前のテキスト ファイル内のユーザーの一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="e6763-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="e6763-191">グループのポリシーの割り当てを取得する</span><span class="sxs-lookup"><span data-stu-id="e6763-191">Get policy assignments for a group</span></span>

<span data-ttu-id="e6763-192">次のコマンドを実行して、特定のセキュリティ グループに割り当てられているすべてのポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6763-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="e6763-193">SIP アドレスまたは電子メール アドレスがポリシーの割り当てに使用された場合でも、グループは常にグループ ID で一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6763-193">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="e6763-194">ユーザーに割り当てられているポリシーを取得する</span><span class="sxs-lookup"><span data-stu-id="e6763-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="e6763-195">次のコマンドを実行して、特定のユーザーに割り当てられているすべてのポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="e6763-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="e6763-196">次の例は、ポリシーに割り当てられているポリシーを取得する方法を示 reda@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e6763-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="e6763-197">ポリシーをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6763-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="e6763-198">次の手順に従って、EducatorMeetingPolicy という名前のカスタム会議ポリシーを、スタッフと教師に直接一括で割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6763-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e6763-199">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="e6763-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="e6763-200">Connect Azure AD PowerShell for Graph PowerShell モジュールTeamsにアクセスする</span><span class="sxs-lookup"><span data-stu-id="e6763-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="e6763-201">この記事の手順を実行する前に、Azure AD PowerShell for Graph モジュール (割り当てられたライセンスでユーザーを識別するために) と Microsoft Teams PowerShell モジュール (これらのユーザーにポリシーを割り当てる) をインストールして接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6763-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="e6763-202">Azure AD PowerShell for Graph モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="e6763-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="e6763-203">管理者特権Windows PowerShell コマンド プロンプト (管理者として Windows PowerShell を実行) を開き、次のコマンドを実行して Azure Active Directory PowerShell for Graph モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e6763-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="e6763-204">以下を実行して、Azure AD に接続します。</span><span class="sxs-lookup"><span data-stu-id="e6763-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="e6763-205">メッセージが表示されたら、管理者の資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="e6763-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="e6763-206">詳細については[、「powerShell for Connect モジュールを使用Azure Active Directory」をGraphしてください](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="e6763-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="e6763-207">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="e6763-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="e6763-208">PowerShell モジュールをインストールするには[Teamsを実行](https://www.powershellgallery.com/packages/MicrosoftTeams)します (まだインストールされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="e6763-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="e6763-209">バージョン 1.0.5 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6763-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="e6763-210">以下を実行して Teams に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="e6763-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="e6763-211">メッセージが表示されたら、Azure アカウントへの接続に使用したのと同じ管理者資格情報を使用してAD。</span><span class="sxs-lookup"><span data-stu-id="e6763-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="e6763-212">ユーザーを特定する</span><span class="sxs-lookup"><span data-stu-id="e6763-212">Identify your users</span></span>

<span data-ttu-id="e6763-213">まず、次のコマンドを実行して、ライセンスの種類別にスタッフと教師を特定します。</span><span class="sxs-lookup"><span data-stu-id="e6763-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="e6763-214">これにより、組織で使用されている SKU が示されます。</span><span class="sxs-lookup"><span data-stu-id="e6763-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="e6763-215">その後、教職員 SKU が割り当てられているスタッフと教師を識別できます。</span><span class="sxs-lookup"><span data-stu-id="e6763-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="e6763-216">次の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="e6763-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="e6763-217">この例の出力では、Faculty ライセンス SKUId が "e97c048c-37a4-45fb-ab50-922fbf07a370" である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6763-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="e6763-218">Education SKU と SKU の一覧を表示するには [、「Education SKU リファレンス」を参照してください](sku-reference-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="e6763-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="e6763-219">次に、次のコマンドを実行して、このライセンスを持つユーザーを特定し、それらをまとめて収集します。</span><span class="sxs-lookup"><span data-stu-id="e6763-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="e6763-220">ポリシーを一括で割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6763-220">Assign a policy in bulk</span></span>

<span data-ttu-id="e6763-221">次に、適切なポリシーをユーザーに一括で割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e6763-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="e6763-222">ポリシーを割り当てまたは更新できるユーザーの最大数は、一度に 5,000 人です。</span><span class="sxs-lookup"><span data-stu-id="e6763-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="e6763-223">たとえば、5,000 人を超えるスタッフと教師がある場合は、複数のバッチを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6763-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="e6763-224">次のコマンドを実行して、EducatorMeetingPolicy という名前のカスタム会議ポリシーをスタッフと教師に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e6763-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="e6763-225">TeamsMessagingPolicy など、別のポリシーの種類を一括で割り当てるには、割り当てるポリシーとポリシー名に変更する ```PolicyType``` ```PolicyName``` 必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6763-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="e6763-226">一括割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="e6763-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="e6763-227">各一括割り当ては操作 ID を返します。この ID を使用して、ポリシー割り当ての進行状況を追跡したり、発生する可能性のあるエラーを特定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e6763-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="e6763-228">たとえば、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6763-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="e6763-229">バッチ操作で各ユーザーの割り当て状態を表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e6763-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="e6763-230">各ユーザーの詳細は プロパティにあります ```UserState``` 。</span><span class="sxs-lookup"><span data-stu-id="e6763-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="e6763-231">ユーザー数が 5,000 人を超える場合は、ポリシーを一括で割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6763-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="e6763-232">まず、次のコマンドを実行して、使用しているスタッフと教師の数を確認します。</span><span class="sxs-lookup"><span data-stu-id="e6763-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="e6763-233">ユーザー ID の一覧全体を指定する代わりに、次のコマンドを実行して最初の 5,000、次の 5,000 などと指定します。</span><span class="sxs-lookup"><span data-stu-id="e6763-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="e6763-234">ユーザー ID の範囲は、ユーザーの完全な一覧に到達するまで変更できます。</span><span class="sxs-lookup"><span data-stu-id="e6763-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="e6763-235">たとえば、最初のバッチに「」と入力し、2 番目のバッチにを使用し、3 番目のバッチに「」と ```$faculty[0..4999``` ```$faculty[5000..9999``` ```$faculty[10000..14999``` 入力します。</span><span class="sxs-lookup"><span data-stu-id="e6763-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="e6763-236">ユーザーに割り当てられているポリシーを取得する</span><span class="sxs-lookup"><span data-stu-id="e6763-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="e6763-237">次のコマンドを実行して、特定のユーザーに割り当てられているすべてのポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="e6763-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="e6763-238">次の例は、ポリシーに割り当てられているポリシーを取得する方法を hannah@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e6763-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="e6763-239">よくあるご質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="e6763-239">FAQ</span></span>

<span data-ttu-id="e6763-240">**PowerShell の使用に慣Teams。詳細については、どこで学習できますか?**</span><span class="sxs-lookup"><span data-stu-id="e6763-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="e6763-241">PowerShell を使用して管理する方法の概要については、「PowerShell Teams」をTeams[を参照してください](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e6763-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="e6763-242">この記事で使用するコマンドレットの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6763-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="e6763-243">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="e6763-243">New-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="e6763-244">Get-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="e6763-244">Get-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="e6763-245">New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="e6763-245">New-CsBatchPolicyAssignmentOperation</span></span>](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="e6763-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="e6763-246">Get-CsBatchPolicyAssignmentOperation</span></span>](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="e6763-247">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="e6763-247">Get-CsUserPolicyAssignment</span></span>](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="e6763-248">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e6763-248">Related topics</span></span>

- [<span data-ttu-id="e6763-249">ユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6763-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="e6763-250">教育機関向け Teams ポリシーおよびポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="e6763-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="e6763-251">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="e6763-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)