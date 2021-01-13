---
title: ユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: 組織内のユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する方法について説明します。
ms.openlocfilehash: 55385cdd47f6b6c9882f8d4e8dcadc848f13755d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806257"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="5c8ee-103">ユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="5c8ee-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="5c8ee-104">Microsoft Teams[の](meeting-policies-in-teams.md)会議ポリシーは、組織内のユーザーがスケジュールした会議の会議参加者が使用できる機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="5c8ee-105">Teams には RestrictedAnonymousAccess という名前の組み込みポリシーが含まれています。これには、匿名ユーザーによる会議の開始を制限する設定が事前に含まれています。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="5c8ee-106">(匿名ユーザーは、認証されていないユーザーです)。会議ポリシーの定義済みの設定は、管理者が編集または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="5c8ee-107">この記事では、PowerShell を使用して、このポリシーが割り当てられているユーザーから RestrictedAnonymousAccess 会議ポリシーを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="5c8ee-108">PowerShell を使用して Teams を管理する方法の詳細については [、Teams PowerShell の概要を参照してください](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="5c8ee-109">始める前に</span><span class="sxs-lookup"><span data-stu-id="5c8ee-109">Before you start</span></span>

<span data-ttu-id="5c8ee-110">[Skype for Business PowerShell モジュールをインストールして接続します](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-110">Install and connect to the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="5c8ee-111">詳しい手順については [、「Microsoft Teams PowerShell をインストールする」を参照してください](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="5c8ee-112">組織の Teams 会議ポリシーの割り当てを取得する</span><span class="sxs-lookup"><span data-stu-id="5c8ee-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="5c8ee-113">次を実行して、組織の Teams 会議ポリシーの割り当てを取得します。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="5c8ee-114">この例では、2 人のユーザーに RestrictedAnonymousAccess 会議ポリシーが割り当てられているという次の出力が返されます。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="5c8ee-115">RestrictedAnonymous 会議ポリシーのユーザーからの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="5c8ee-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="5c8ee-116">ユーザーから RestrictedAnonymous 会議ポリシーを削除するには、ユーザー数が少ない場合 (ユーザー数が 100 未満など) 場合は [、Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="5c8ee-117">多数のユーザー (100 を超えるユーザーなど) がある場合は  [、New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) コマンドレットを使用してバッチ操作を送信する方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="5c8ee-118">ポリシーコマンドレットGrant-CsTeamsMeeting使用する</span><span class="sxs-lookup"><span data-stu-id="5c8ee-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="5c8ee-119">次を実行して、RestrictedAnonymous 会議ポリシーをユーザーから削除します。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="5c8ee-120">次のコマンドレットをNew-CsBatchPolicyAssignmentOperationする</span><span class="sxs-lookup"><span data-stu-id="5c8ee-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="5c8ee-121">バッチ [ポリシーの割](assign-policies.md#assign-a-policy-to-a-batch-of-users)り当てでは、ポリシーを削除または更新できるユーザーの最大数は、一度に 5,000 人です。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="5c8ee-122">たとえば、ユーザー数が 5,000 を超える場合は、複数のバッチを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="5c8ee-123">最良の結果を得る場合は、一度に複数のバッチを送信しない。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="5c8ee-124">さらにバッチを送信する前に、バッチが処理を完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="5c8ee-125">[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)コマンドレットは、Teams PowerShell モジュール内に入っています。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="5c8ee-126">これらの手順を実行する前に [、Teams PowerShell モジュールをインストールして接続します](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="5c8ee-127">詳しい手順については [、「Microsoft Teams PowerShell をインストールする」を参照してください](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="5c8ee-128">次のコマンドを実行して、ユーザーのバッチから RestrictedAnonymousAccess 会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="5c8ee-129">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="5c8ee-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="5c8ee-130">各バッチ割り当ては、割り当ての進捗状況と状態を追跡し、発生する可能性があるエラーを特定するために使用できる操作 ID を返します。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="5c8ee-131">たとえば、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="5c8ee-132">**ErrorCount** が **0** (ゼロ) で **、OverallStatus が** 完了した状態を **確認します**。</span><span class="sxs-lookup"><span data-stu-id="5c8ee-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5c8ee-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c8ee-133">Related topics</span></span>

- [<span data-ttu-id="5c8ee-134">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="5c8ee-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="5c8ee-135">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="5c8ee-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="5c8ee-136"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5c8ee-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
