---
title: RestrictedAnonymousAccess Teams の会議ポリシーをユーザーから削除する
author: LanaChin
ms.author: v-lanac
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
description: 組織内のユーザーから RestrictedAnonymousAccess Teams の会議ポリシーを削除する方法について説明します。
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640991"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="43803-103">RestrictedAnonymousAccess Teams の会議ポリシーをユーザーから削除する</span><span class="sxs-lookup"><span data-stu-id="43803-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="43803-104">Microsoft Teams の[会議ポリシー](meeting-policies-in-teams.md)は、組織内のユーザーによってスケジュールされている会議の参加者が使用できる機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="43803-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="43803-105">Teams には、RestrictedAnonymousAccess という名前の組み込みのポリシーが用意されています。これには、匿名ユーザーによる会議の開始を制限する定義済みの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="43803-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="43803-106">(匿名ユーザーとは、認証されていないユーザーのことです。)会議ポリシーで定義された設定は、管理者が編集または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="43803-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="43803-107">この記事では、PowerShell を使用して、このポリシーが割り当てられているユーザーから RestrictedAnonymousAccess 会議ポリシーを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43803-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="43803-108">PowerShell を使用してチームを管理する方法の詳細については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43803-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="43803-109">始める前に</span><span class="sxs-lookup"><span data-stu-id="43803-109">Before you start</span></span>

<span data-ttu-id="43803-110">[Skype For Business PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=39366)にインストールして接続します。</span><span class="sxs-lookup"><span data-stu-id="43803-110">Install and connect to the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="43803-111">詳細な手順については、「 [Microsoft Teams PowerShell をインストール](teams-powershell-install.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43803-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="43803-112">組織のチーム会議ポリシーの割り当てを取得する</span><span class="sxs-lookup"><span data-stu-id="43803-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="43803-113">組織のチーム会議ポリシーの割り当てを取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="43803-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="43803-114">この例では、次の出力が返されます。これは、2人のユーザーに RestrictedAnonymousAccess 会議ポリシーが割り当てられていることを示します。</span><span class="sxs-lookup"><span data-stu-id="43803-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="43803-115">RestrictedAnonymous 会議ポリシーをユーザーから割り当て解除する</span><span class="sxs-lookup"><span data-stu-id="43803-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="43803-116">ユーザーから RestrictedAnonymous 会議ポリシーを削除するには、少なくとも1人のユーザー (たとえば、100ユーザーより小さい) がある場合は、 [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="43803-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="43803-117">多数のユーザーがいる場合 (たとえば、100ユーザーを超える場合) は、 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)コマンドレットを使用してバッチ操作を送信する方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="43803-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="43803-118">Grant-CsTeamsMeeting Policy コマンドレットを使用する</span><span class="sxs-lookup"><span data-stu-id="43803-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="43803-119">ユーザーから RestrictedAnonymous 会議ポリシーを削除するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="43803-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="43803-120">CsBatchPolicyAssignmentOperation コマンドレットを使用する</span><span class="sxs-lookup"><span data-stu-id="43803-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="43803-121">[バッチポリシーの割り当て](assign-policies.md#assign-a-policy-to-a-batch-of-users)では、ポリシーを削除または更新できるユーザーの最大数は一度に5000です。</span><span class="sxs-lookup"><span data-stu-id="43803-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="43803-122">たとえば、5000を超えるユーザーがいる場合は、複数のバッチを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43803-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="43803-123">最善の結果を得るには、一度に複数のバッチを送信しないでください。</span><span class="sxs-lookup"><span data-stu-id="43803-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="43803-124">さらにバッチを送信する前に、バッチが処理を完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="43803-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="43803-125">[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)コマンドレットは、Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="43803-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="43803-126">次の手順に従う前に、 [Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールして接続します。</span><span class="sxs-lookup"><span data-stu-id="43803-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="43803-127">詳細な手順については、「 [Microsoft Teams PowerShell をインストール](teams-powershell-install.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43803-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="43803-128">次のコマンドを実行して、ユーザーのバッチから RestrictedAnonymousAccess 会議のポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="43803-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="43803-129">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="43803-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="43803-130">各バッチ割り当ては、操作 ID を返します。この ID を使用して、課題の進捗状況と状態を追跡し、発生する可能性のあるエラーを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="43803-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="43803-131">たとえば、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="43803-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="43803-132">**ErrorCount**が**0** (ゼロ) で、 **OverallStatus**が**完了**していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="43803-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="43803-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="43803-133">Related topics</span></span>

- [<span data-ttu-id="43803-134">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="43803-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="43803-135">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="43803-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="43803-136">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="43803-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
