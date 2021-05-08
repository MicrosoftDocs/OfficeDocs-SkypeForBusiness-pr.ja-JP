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
description: 組織内のユーザーから RestrictedAnonymousAccess Teamsポリシーを削除する方法について説明します。
ms.openlocfilehash: aab4b524ee0c9ab5cab3244a0897730fea0361a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121345"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="c7d60-103">ユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="c7d60-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="c7d60-104">[Microsoft Teamsの](meeting-policies-in-teams.md)会議ポリシーは、組織内のユーザーがスケジュールした会議に対して会議参加者が使用できる機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7d60-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="c7d60-105">Teams RestrictedAnonymousAccess という名前の組み込みポリシーが含まれています。これには、匿名ユーザーによる会議の開始を制限する設定が事前に定義されています。</span><span class="sxs-lookup"><span data-stu-id="c7d60-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="c7d60-106">(匿名ユーザーは、認証されていないユーザーです)。会議ポリシーの定義済みの設定は、管理者が編集または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c7d60-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="c7d60-107">この記事では、PowerShell を使用して、このポリシーが割り当てられているユーザーから RestrictedAnonymousAccess 会議ポリシーを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7d60-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="c7d60-108">PowerShell を使用して管理する方法の詳細Teams PowerShell の概要に関するTeams[を参照してください](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d60-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="c7d60-109">開始する前に</span><span class="sxs-lookup"><span data-stu-id="c7d60-109">Before you start</span></span>

<span data-ttu-id="c7d60-110">PowerShell モジュール をインストール[Skype for Business接続します](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c7d60-110">Install and connect to the [Skype for Business PowerShell module](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span> <span data-ttu-id="c7d60-111">詳細なガイダンスについては、PowerShell のインストールに関[するページMicrosoft Teams参照してください](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d60-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="c7d60-112">組織のTeamsポリシーの割り当てを取得する</span><span class="sxs-lookup"><span data-stu-id="c7d60-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="c7d60-113">次のコマンドを実行して、組織Teamsポリシーの割り当てを取得します。</span><span class="sxs-lookup"><span data-stu-id="c7d60-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="c7d60-114">この例では、次の出力が返されます。これは、2 人のユーザーに RestrictedAnonymousAccess 会議ポリシーが割り当てられている状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="c7d60-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="c7d60-115">ユーザーからの RestrictedAnonymous 会議ポリシーの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="c7d60-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="c7d60-116">ユーザーから RestrictedAnonymous 会議ポリシーを削除するには、ユーザーの数が少ない場合 (ユーザー数が 100 人未満など) は [、Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7d60-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="c7d60-117">多数のユーザー (100 人を超えるユーザーなど) がある場合は  [、New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) コマンドレットを使用してバッチ操作を送信する方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="c7d60-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="c7d60-118">Grant-CsTeamsMeeting Policy コマンドレットを使用する</span><span class="sxs-lookup"><span data-stu-id="c7d60-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="c7d60-119">次のコマンドを実行して、RestrictedAnonymous 会議ポリシーをユーザーから削除します。</span><span class="sxs-lookup"><span data-stu-id="c7d60-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="c7d60-120">次のコマンドレットNew-CsBatchPolicyAssignmentOperationします。</span><span class="sxs-lookup"><span data-stu-id="c7d60-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="c7d60-121">バッチ [ポリシーの割り](assign-policies.md#assign-a-policy-to-a-batch-of-users)当てでは、ポリシーを削除または更新できるユーザーの最大数は、一度に 5,000 人です。</span><span class="sxs-lookup"><span data-stu-id="c7d60-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="c7d60-122">たとえば、ユーザー数が 5,000 を超える場合は、複数のバッチを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7d60-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="c7d60-123">最適な結果を得る場合は、一度に複数のバッチを送信しない。</span><span class="sxs-lookup"><span data-stu-id="c7d60-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="c7d60-124">さらにバッチを送信する前に、バッチが処理を完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c7d60-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="c7d60-125">[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)コマンドレットは、PowerShell モジュールTeamsに含されています。</span><span class="sxs-lookup"><span data-stu-id="c7d60-125">The [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="c7d60-126">これらの手順を実行する前に、PowerShell モジュール をインストール[Teams接続します](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="c7d60-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="c7d60-127">詳細なガイダンスについては、PowerShell のインストールに関[するページMicrosoft Teams参照してください](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d60-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="c7d60-128">次のコマンドを実行して、ユーザーのバッチから RestrictedAnonymousAccess 会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c7d60-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="c7d60-129">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="c7d60-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="c7d60-130">各バッチ割り当ては操作 ID を返します。この ID を使用すると、割り当ての進行状況と状態を追跡し、発生する可能性があるエラーを特定できます。</span><span class="sxs-lookup"><span data-stu-id="c7d60-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="c7d60-131">たとえば、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c7d60-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="c7d60-132">**ErrorCount** が **0** (ゼロ) で **、OverallStatus が Completed** である必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="c7d60-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c7d60-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c7d60-133">Related topics</span></span>

- [<span data-ttu-id="c7d60-134">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="c7d60-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="c7d60-135">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="c7d60-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="c7d60-136"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c7d60-136">Assign policies to your users in Teams</span></span>](assign-policies.md)