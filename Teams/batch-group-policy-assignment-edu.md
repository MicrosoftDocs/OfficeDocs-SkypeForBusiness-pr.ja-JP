---
title: 学校内の大規模なユーザー セットにポリシーを割り当てる
author: DaniEASmith
ms.author: danismith
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
ms.localizationpriority: medium
search.appverid: MET150
description: グループ メンバーシップに基づいて教育機関の大規模なユーザー セットにポリシーを割り当てる方法、またはリモート 学校 (teleschool、tele-school) 目的のバッチ割り当てを通じて直接ポリシーを割り当てる方法について説明します。
f1keywords: ''
ms.openlocfilehash: 3cfde2dc523904f571b696e63ea7a5da16afff26
ms.sourcegitcommit: 1129841e68e927fe7cc31de3ad63a3e9247253cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2022
ms.locfileid: "62362993"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>学校内の大規模なユーザー セットにポリシーを割り当てる

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Microsoft Teamsでのポリシーの割り当ての詳細については、「[Teamsのユーザーにポリシーを割り当てる](policy-assignment-overview.md)」を参照してください。

## <a name="overview"></a>概要

学生と教育者に、Microsoft Teamsのさまざまな機能へのアクセス権を付与する必要がありますか? 組織内のユーザーをライセンスの種類で迅速に識別し、適切なポリシーを割り当てることができます。 このチュートリアルでは、学校内の大規模なユーザー セットに会議ポリシーを割り当てる方法について説明します。 Microsoft Teams管理センターと PowerShell を使用してポリシーを割り当てることができます。両方の方法について説明します。

会議ポリシーは、バッチ ポリシーの割り当てを通じて、ユーザーが大規模なユーザーのメンバーであるか、直接ユーザーであるセキュリティ グループに割り当てることができます。 次の方法について説明します。

- **[グループへのポリシーの割り当てを](#assign-a-policy-to-a-group)使用して、セキュリティ グループに会議ポリシーを割り当てます (推奨)。** このメソッドを使用すると、グループ メンバーシップに基づいてポリシーを割り当てることができます。 セキュリティ グループまたは配布リストにポリシーを割り当てることができます。 メンバーがグループに追加または削除されると、継承されたポリシーの割り当てはそれに応じて更新されます。 新しいユーザーまたはユーザーのロールが変更されたときにポリシーを管理する時間が短縮されるため、この方法を使用することをお勧めします。 この方法は、最大 50,000 人のユーザーのグループに最適ですが、大規模なグループでも機能します。

- **[バッチ ポリシーの割り当てを](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)使用して、会議ポリシーをユーザーに直接一括で割り当てます**。 一度に最大 5,000 人のユーザーにポリシーを割り当てることができます。 ユーザーが 5,000 人を超える場合は、複数のバッチを送信できます。 この方法では、新しいユーザーがいる場合は、バッチ割り当てを再実行して、それらの新しいユーザーにポリシーを割り当てる必要があります。

Teamsでは、カスタム ポリシーを作成して割り当てる場合を除き、ユーザーはTeams ポリシーの種類のグローバル (組織全体の既定) ポリシーを自動的に取得します。 学生の人口は多くの場合、最大のユーザー のセットであり、多くの場合、最も制限の厳しい設定を受け取るため、次の操作を行うことをお勧めします。

- プライベート チャットや会議のスケジュール設定などのコア機能を許可するカスタム ポリシーを作成し、そのポリシーをスタッフと教育者に割り当てます。
- スタッフと教育者にカスタム ポリシーを割り当てます。
- グローバル (組織全体の既定) ポリシーを編集して適用し、学生の機能を制限します。

カスタム ポリシーを作成し、それをスタッフと教育者に割り当てるまで、グローバル ポリシーは学校内のすべてのユーザーに適用されることに注意してください。

このチュートリアルでは、学生がグローバル会議ポリシーを取得し、EducatorMeetingPolicy という名前のカスタム会議ポリシーをスタッフと教育者に割り当てます。 グローバル ポリシーを編集して学生向けの会議設定を調整し、スタッフと教育者の会議エクスペリエンスを定義する [カスタム ポリシーを作成](policy-packages-edu.md) したことを前提としています。

![Teams管理センターの [会議ポリシー] ページのスクリーンショット。](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>ポリシーをグループに割り当てる

次の手順に従って、スタッフと教育者のセキュリティ グループを作成し、そのセキュリティ グループに EducatorMeetingPolicy という名前のカスタム会議ポリシーを割り当てます。

### <a name="before-you-get-started"></a>使用を開始する前に

> [!IMPORTANT]
> グループにポリシーを割り当てると、ポリシーの割り当ては優先順位ルールに従ってグループのメンバーに反映されます。 たとえば、ユーザーに直接ポリシーが割り当てられている場合 (個別またはバッチ割り当て) は、そのポリシーがグループから継承されたポリシーよりも優先されます。 また、ユーザーに直接割り当てられた会議ポリシーがある場合は、セキュリティ グループから会議ポリシーを継承する前に、その会議ポリシーをユーザーから削除する必要があります。

使用を開始する前に、[優先規則](policy-assignment-overview.md#which-policy-takes-precedence)と[グループ割り当てのランク付け](assign-policies-users-and-groups.md#group-assignment-ranking)を理解することが重要です。 **[「グループへのポリシーの割り当てについて知っておくべきこと](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)」の概念を読んで理解していることを確認** します。

スタッフと教育者がセキュリティ グループから会議ポリシーを継承するには、これらのすべての手順を完了する必要があります。

1. [セキュリティ グループを作成します](#create-security-groups)。
2. [セキュリティ グループにポリシーを割り当てます](#assign-a-policy-to-a-security-group)。
3. [ユーザーに直接割り当てられたポリシーを削除します](#remove-a-policy-that-was-directly-assigned-to-users)。

### <a name="create-security-groups"></a>セキュリティ グループを作成する

まず、スタッフと教育者のセキュリティ グループを作成します。

[学校データ同期](/SchoolDataSync/) (SDS) を使用すると、学校で[セキュリティ グループの教育者と学生を簡単に作成](/SchoolDataSync/edu-security-groups)できます。 SDS を使用して、学校のポリシーを管理するために必要なセキュリティ グループを作成することをお勧めします。

環境内で SDS を展開できない場合は、 [この PowerShell スクリプト](scripts/powershell-script-security-groups-edu.md) を使用して 2 つのセキュリティ グループを作成します。1 つは教職員ライセンスが割り当てられているすべてのスタッフと教育者用、もう 1 つは学生ライセンスが割り当てられているすべての学生用です。 グループを最新の状態に保つために、このスクリプトを定期的に実行する必要があります。

### <a name="assign-a-policy-to-a-security-group"></a>セキュリティ グループにポリシーを割り当てる

#### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

> [!NOTE]
> 現在、Microsoft Teams 管理センターを使用したグループへのポリシー割り当ては、Teams 通話ポリシー、Teams コール パーク ポリシー、Teams ポリシー、Teams ライブ イベント ポリシー、Teams 会議ポリシー、Teams メッセージ ポリシーでのみ使用できます。 他のポリシーの種類については、PowerShell を使用してください。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。
2. **グループ ポリシーの割り当て** タブを選択します。
3. **[グループの追加]** を選択し、**[ポリシーをグループに割り当てる]** ウィンドウで、次の操作を行います:

    ![会議ポリシーを示す [設定の編集] ウィンドウのスクリーンショット。](media/batch-group-policy-assignment-edu-group.png)
    1. [ **グループの選択]** ボックスで、スタッフと教育者を含むセキュリティ グループを検索して追加します。
    2. [ **ランクの選択]** ボックスに **「1**」と入力します。
    3. [ **ポリシーの選択] ボックスで** 、[ **EducatorMeetingPolicy**] を選択します。
    4. **[適用]** を選択します。

グループ ポリシーの割り当てを削除するには、ポリシー ページの **[グループ ポリシーの割り当て]** タブで、グループの割り当てを選び、**[削除]** を選択します。

グループ割り当てのランク付けを変更するには、最初にグループ ポリシーの割り当てを削除する必要があります。 次に、上記の手順に従ってポリシーをグループに割り当てます。

#### <a name="using-powershell"></a>PowerShell の使用

> [!NOTE]
> 現在、PowerShell を使用したグループへのポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。 サポートされているポリシー タイプの一覧については、[New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) を参照してください。

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

次のコマンドを実行して[、Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールします (まだインストールされていない場合)。 バージョン 1.0.5 以降をインストールしていることを確認します。

```powershell
Install-Module -Name MicrosoftTeams
```

以下を実行して Teams に接続しセッションを開始します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、管理者の資格情報を使用してサイン インします。

##### <a name="assign-a-policy-to-a-group"></a>ポリシーをグループに割り当てる

次の手順を実行して、スタッフと教師を含むセキュリティ グループに EducatorMeetingPolicy という名前の会議ポリシーを割り当て、割り当てのランク付けを 1 に設定します。 オブジェクト ID、セッション開始プロトコル (SIP) アドレス、または電子メール アドレスを使用して、セキュリティ グループを指定できます。 この例では、電子メール アドレス (staff-faculty@contoso.com) を使用します。

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>ユーザーに直接割り当てられたポリシーを削除する

ユーザーにポリシーが直接割り当てられた場合 (個別に、またはバッチ割り当てによって) そのポリシーが優先されることを忘れないでください。 つまり、ユーザーに直接割り当てられた会議ポリシーがある場合は、セキュリティ グループから会議ポリシーを継承する前に、その会議ポリシーをユーザーから削除する必要があります。

詳細については、「 [グループへのポリシーの割り当てについて知ってお](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)くべきこと」を参照してください。

次の手順に従って、スタッフと教育者に直接割り当てられた会議ポリシーを削除します。

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

次のコマンドを実行して[、Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールします (まだインストールされていない場合)。 バージョン 1.0.5 以降をインストールしていることを確認します。

```powershell
Install-Module -Name MicrosoftTeams
```

以下を実行して Teams に接続しセッションを開始します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、Azure ADへの接続に使用したのと同じ管理者資格情報を使用してサインインします。

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>ユーザーに直接割り当てられたポリシーの割り当てを解除する

次を実行して、そのポリシーを直接割り当てられたユーザーから会議ポリシーを削除します。 ユーザーは、電子メール アドレスまたはオブジェクト ID で指定できます。

この例では、会議ポリシーは自分のメール アドレスで指定されたユーザーから削除されます。

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

この例では、会議ポリシーは、user_ids.txt という名前のテキスト ファイル内のユーザーの一覧から削除されます。

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>グループのポリシーの割り当てを取得する

次を実行して、特定のセキュリティ グループに割り当てられているすべてのポリシーを確認します。 ポリシーの割り当てに SIP アドレスまたは電子メール アドレスが使用された場合でも、グループは常にグループ ID で一覧表示されることに注意してください。

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>ユーザーに割り当てられているポリシーを取得する

次を実行して、特定のユーザーに割り当てられているすべてのポリシーを表示します。 次の例では、reda@contoso.com に割り当てられているポリシーを取得する方法を示します。

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>ポリシーをユーザーのバッチに割り当てる

次の手順に従って、EducatorMeetingPolicy という名前のカスタム会議ポリシーをスタッフと教師に直接一括で割り当てます。

### <a name="using-powershell"></a>PowerShell の使用

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Azure AD PowerShell for Graph モジュールと Teams PowerShell モジュールにConnectする

この記事の手順を実行する前に、Azure AD PowerShell for Graph モジュール (割り当てられたライセンスでユーザーを識別するため) と Microsoft Teams PowerShell モジュール (それらのユーザーにポリシーを割り当てるには) をインストールして接続する必要があります。

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Azure AD PowerShell for Graph モジュールをインストールして接続する

管理者特権でWindows PowerShellコマンド プロンプトを開き (管理者としてWindows PowerShell実行)、次のコマンドを実行して、Azure Active Directory PowerShell for Graph モジュールをインストールします。

```powershell
Install-Module -Name AzureAD
```

以下を実行して、Azure AD に接続します。

```powershell
Connect-AzureAD
```

メッセージが表示されたら、管理者の資格情報を使用してサイン インします。

詳細については、[Azure Active Directory PowerShell for Graph モジュールのConnect](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)を参照してください。

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

次のコマンドを実行して[、Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールします (まだインストールされていない場合)。 バージョン 1.0.5 以降をインストールしていることを確認します。

```powershell
Install-Module -Name MicrosoftTeams
```

以下を実行して Teams に接続しセッションを開始します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、Azure ADへの接続に使用したのと同じ管理者資格情報を使用してサインインします。

#### <a name="identify-your-users"></a>ユーザーを識別する

まず、次のコマンドを実行して、ライセンスの種類別にスタッフと教育者を識別します。 これにより、組織内で使用されている SKU が示されます。 その後、教職員 SKU が割り当てられているスタッフと教育者を特定できます。

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

次の値が返されます。

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

この例では、出力は、教職員ライセンス SkuId が "e97c048c-37a4-45fb-ab50-922fbf07a370" であることを示しています。

> [!NOTE]
> Education SKU と SKU ID の一覧については、「Education SKU リファレンス」を [参照してください](sku-reference-edu.md)。

次に、次の手順を実行して、このライセンスを持つユーザーを特定し、それらをすべてまとめて収集します。

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>ポリシーを一括で割り当てる

次に、適切なポリシーをユーザーに一括で割り当てます。 ポリシーを割り当てまたは更新できるユーザーの最大数は、一度に 5,000 です。 たとえば、5,000 人以上のスタッフと教育者がいる場合は、複数のバッチを送信する必要があります。

次を実行して、EducatorMeetingPolicy という名前のカスタム会議ポリシーをスタッフと教育者に割り当てます。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> TeamsMessagingPolicy など、別のポリシーの種類を一括で割り当てるには、割り当てるポリシーと```PolicyName```ポリシー名に変更```PolicyType```する必要があります。

#### <a name="get-the-status-of-a-bulk-assignment"></a>一括割り当ての状態を取得する

各一括割り当ては、操作 ID を返します。これを使用して、ポリシーの割り当ての進行状況を追跡したり、発生する可能性のあるエラーを特定したりできます。 たとえば、次のように実行します。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

バッチ操作の各ユーザーの割り当て状態を表示するには、次を実行します。 各ユーザーの詳細がプロパティに含 ```UserState``` まれています。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>5,000 人を超えるユーザーがいる場合は、ポリシーを一括で割り当てる

まず、次の手順を実行して、スタッフと教育者の数を確認します。

```powershell
$faculty.count
```

ユーザー ID の一覧全体を指定する代わりに、次を実行して最初の 5,000、次の 5,000 などを指定します。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

ユーザーの完全な一覧に到達するまで、ユーザー ID の範囲を変更できます。 たとえば、最初のバッチを入力 ```$faculty[0..4999``` し、2 番目のバッチに使用 ```$faculty[5000..9999``` し、3 番目のバッチに対して入力 ```$faculty[10000..14999``` します。

#### <a name="get-the-policies-assigned-to-a-user"></a>ユーザーに割り当てられているポリシーを取得する

次を実行して、特定のユーザーに割り当てられているすべてのポリシーを表示します。 次の例では、hannah@contoso.com に割り当てられているポリシーを取得する方法を示します。

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>よくあるご質問 (FAQ)

**powerShell for Teamsについてはよく知りません。詳細はどこで確認できますか?**

PowerShell を使用したTeamsの管理の概要については、[PowerShell の概要Teams](teams-powershell-overview.md)参照してください。 この記事で使用するコマンドレットの詳細については、次を参照してください。

- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment)
- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>関連項目

- [ユーザーにポリシーを割り当てる](policy-assignment-overview.md)
- [教育機関向け Teams ポリシーおよびポリシー パッケージ](policy-packages-edu.md)
- [Teams での会議ポリシーを管理する](meeting-policies-overview.md)