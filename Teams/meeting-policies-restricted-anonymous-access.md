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
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>ユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する

[Microsoft Teamsの](meeting-policies-in-teams.md)会議ポリシーは、組織内のユーザーがスケジュールした会議に対して会議参加者が使用できる機能を制御するために使用されます。 

Teams RestrictedAnonymousAccess という名前の組み込みポリシーが含まれています。これには、匿名ユーザーによる会議の開始を制限する設定が事前に定義されています。 (匿名ユーザーは、認証されていないユーザーです)。会議ポリシーの定義済みの設定は、管理者が編集または変更することはできません。

この記事では、PowerShell を使用して、このポリシーが割り当てられているユーザーから RestrictedAnonymousAccess 会議ポリシーを削除する方法について説明します。 PowerShell を使用して管理する方法の詳細Teams PowerShell の概要に関するTeams[を参照してください](teams-powershell-overview.md)。

## <a name="before-you-start"></a>開始する前に

PowerShell モジュール をインストール[Skype for Business接続します](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。 詳細なガイダンスについては、PowerShell のインストールに関[するページMicrosoft Teams参照してください](teams-powershell-install.md)。

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>組織のTeamsポリシーの割り当てを取得する

次のコマンドを実行して、組織Teamsポリシーの割り当てを取得します。

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

この例では、次の出力が返されます。これは、2 人のユーザーに RestrictedAnonymousAccess 会議ポリシーが割り当てられている状態を示しています。

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>ユーザーからの RestrictedAnonymous 会議ポリシーの割り当てを解除する

ユーザーから RestrictedAnonymous 会議ポリシーを削除するには、ユーザーの数が少ない場合 (ユーザー数が 100 人未満など) は [、Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) コマンドレットを使用できます。 多数のユーザー (100 人を超えるユーザーなど) がある場合は  [、New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) コマンドレットを使用してバッチ操作を送信する方が効率的です。

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Grant-CsTeamsMeeting Policy コマンドレットを使用する

次のコマンドを実行して、RestrictedAnonymous 会議ポリシーをユーザーから削除します。

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>次のコマンドレットNew-CsBatchPolicyAssignmentOperationします。

バッチ [ポリシーの割り](assign-policies.md#assign-a-policy-to-a-batch-of-users)当てでは、ポリシーを削除または更新できるユーザーの最大数は、一度に 5,000 人です。 たとえば、ユーザー数が 5,000 を超える場合は、複数のバッチを送信する必要があります。 最適な結果を得る場合は、一度に複数のバッチを送信しない。 さらにバッチを送信する前に、バッチが処理を完了できるようにします。

> [!NOTE]
> [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)コマンドレットは、PowerShell モジュールTeamsに含されています。 これらの手順を実行する前に、PowerShell モジュール をインストール[Teams接続します](https://www.powershellgallery.com/packages/MicrosoftTeams)。 詳細なガイダンスについては、PowerShell のインストールに関[するページMicrosoft Teams参照してください](teams-powershell-install.md)。

次のコマンドを実行して、ユーザーのバッチから RestrictedAnonymousAccess 会議ポリシーを削除します。

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>バッチ割り当ての状態を取得する

各バッチ割り当ては操作 ID を返します。この ID を使用すると、割り当ての進行状況と状態を追跡し、発生する可能性があるエラーを特定できます。 たとえば、次のコマンドを実行します。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

**ErrorCount** が **0** (ゼロ) で **、OverallStatus が Completed** である必要 **があります**。

## <a name="related-topics"></a>関連トピック

- [Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [ Teams でユーザーにポリシーを割り当てる](assign-policies.md)