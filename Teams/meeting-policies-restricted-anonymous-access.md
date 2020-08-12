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
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>RestrictedAnonymousAccess Teams の会議ポリシーをユーザーから削除する

Microsoft Teams の[会議ポリシー](meeting-policies-in-teams.md)は、組織内のユーザーによってスケジュールされている会議の参加者が使用できる機能を制御するために使用されます。 

Teams には、RestrictedAnonymousAccess という名前の組み込みのポリシーが用意されています。これには、匿名ユーザーによる会議の開始を制限する定義済みの設定が含まれています。 (匿名ユーザーとは、認証されていないユーザーのことです。)会議ポリシーで定義された設定は、管理者が編集または変更することはできません。

この記事では、PowerShell を使用して、このポリシーが割り当てられているユーザーから RestrictedAnonymousAccess 会議ポリシーを削除する方法について説明します。 PowerShell を使用してチームを管理する方法の詳細については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。

## <a name="before-you-start"></a>始める前に

[Skype For Business PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=39366)にインストールして接続します。 詳細な手順については、「 [Microsoft Teams PowerShell をインストール](teams-powershell-install.md)する」を参照してください。

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>組織のチーム会議ポリシーの割り当てを取得する

組織のチーム会議ポリシーの割り当てを取得するには、次の操作を実行します。

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

この例では、次の出力が返されます。これは、2人のユーザーに RestrictedAnonymousAccess 会議ポリシーが割り当てられていることを示します。

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>RestrictedAnonymous 会議ポリシーをユーザーから割り当て解除する

ユーザーから RestrictedAnonymous 会議ポリシーを削除するには、少なくとも1人のユーザー (たとえば、100ユーザーより小さい) がある場合は、 [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)コマンドレットを使用できます。 多数のユーザーがいる場合 (たとえば、100ユーザーを超える場合) は、 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)コマンドレットを使用してバッチ操作を送信する方が効率的です。

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Grant-CsTeamsMeeting Policy コマンドレットを使用する

ユーザーから RestrictedAnonymous 会議ポリシーを削除するには、次を実行します。

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>CsBatchPolicyAssignmentOperation コマンドレットを使用する

[バッチポリシーの割り当て](assign-policies.md#assign-a-policy-to-a-batch-of-users)では、ポリシーを削除または更新できるユーザーの最大数は一度に5000です。 たとえば、5000を超えるユーザーがいる場合は、複数のバッチを送信する必要があります。 最善の結果を得るには、一度に複数のバッチを送信しないでください。 さらにバッチを送信する前に、バッチが処理を完了できるようにします。

> [!NOTE]
> [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)コマンドレットは、Teams PowerShell モジュールに含まれています。 次の手順に従う前に、 [Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールして接続します。 詳細な手順については、「 [Microsoft Teams PowerShell をインストール](teams-powershell-install.md)する」を参照してください。

次のコマンドを実行して、ユーザーのバッチから RestrictedAnonymousAccess 会議のポリシーを削除します。

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>バッチ割り当ての状態を取得する

各バッチ割り当ては、操作 ID を返します。この ID を使用して、課題の進捗状況と状態を追跡し、発生する可能性のあるエラーを特定することができます。 たとえば、次のように実行します。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

**ErrorCount**が**0** (ゼロ) で、 **OverallStatus**が**完了**していることを確認します。

## <a name="related-topics"></a>関連項目

- [Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [チームのユーザーにポリシーを割り当てる](assign-policies.md)
