---
title: 学校の多数のユーザーにポリシーを割り当てる
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
description: グループ メンバーシップに基づいて、またはリモート 学校 (テレスクール、テレスクール) のバッチ割り当てを通じて直接、教育機関の多数のユーザーにポリシーを割り当てる方法について説明します。
f1keywords: ''
ms.openlocfilehash: f2d36db6a96f6a9a42590ada6600ef38738b30a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092905"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>学校の多数のユーザーにポリシーを割り当てる

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Microsoft Teams でポリシーを割り当てる方法の詳細については、「Teams でポリシーをユーザーに割り当 [てる」を参照してください](assign-policies.md)。

## <a name="overview"></a>概要

学生や教育者に Microsoft Teams のさまざまな機能へのアクセス権を与える必要がありますか? ライセンスの種類別に組織内のユーザーをすばやく特定し、適切なポリシーを割り当てできます。 このチュートリアルでは、学校の多数のユーザーに会議ポリシーを割り当てる方法について説明します。 Microsoft Teams 管理センターと PowerShell を使用してポリシーを割り当て、両方の方法について説明します。

ユーザーがメンバーであるセキュリティ グループに会議ポリシーを割り当てるか、バッチ ポリシーの割り当てを通じて大規模なユーザーに直接割り当てできます。 次の方法について学習します。

- **グループ [へのポリシー割り当てを使用して](#assign-a-policy-to-a-group)、セキュリティ グループに会議ポリシーを割り当てる (推奨)** この方法では、グループ メンバーシップに基づいてポリシーを割り当てできます。 セキュリティ グループまたは配布リストにポリシーを割り当てできます。 メンバーがグループに追加またはグループから削除されると、そのメンバーの継承されたポリシー割り当てが更新されます。 この方法は、新しいユーザーのポリシーを管理する時間を短縮したり、ユーザーの役割が変更された場合に使用することをお勧めします。 この方法は、最大 50,000 人のユーザーのグループに最適ですが、大規模なグループでも使用できます。

- **バッチ [ポリシーの割り当てを使用](assign-policies.md#assign-a-policy-to-a-batch-of-users) して、会議ポリシーをユーザーに一括で直接割り当てる**。 一度に最大 5,000 人のユーザーにポリシーを割り当てできます。 ユーザー数が 5,000 を超える場合は、複数のバッチを送信できます。 この方法では、新しいユーザーを作成するときに、バッチ割り当てを再び実行して、それらの新しいユーザーにポリシーを割り当てる必要があります。

Teams では、カスタム ポリシーを作成して割り当てない限り、ユーザーは Teams ポリシータイプのグローバル (組織全体の既定) ポリシーを自動的に取得します。 学生の人口は多くの場合、最大のユーザー セットであり、最も制限の厳しい設定を受け取る場合が多いので、次の操作を行う必要があります。

- プライベート チャットや会議のスケジュール設定などの主要な機能を許可するカスタム ポリシーを作成し、スタッフや教師にポリシーを割り当てる。
- スタッフと教師にカスタム ポリシーを割り当てる。
- グローバル (組織全体の既定) ポリシーを編集して適用し、学生の機能を制限します。

グローバル ポリシーは、カスタム ポリシーを作成し、それをスタッフや教師に割り当てるまで、学校のすべてのユーザーに適用されます。

このチュートリアルでは、学生はグローバル会議ポリシーを取得し、EducatorMeetingPolicy という名前のカスタム会議ポリシーをスタッフと教師に割り当てる方法について説明します。 グローバル ポリシーを編集して学生の会議設定を調整し、スタッフと教師の[](policy-packages-edu.md)会議エクスペリエンスを定義するカスタム ポリシーを作成したとします。

![Teams 管理センターの [会議ポリシー] ページのスクリーンショット](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>ポリシーをグループに割り当てる

次の手順に従って、スタッフと教育者用のセキュリティ グループを作成し、EducatorMeetingPolicy という名前のカスタム会議ポリシーをそのセキュリティ グループに割り当てします。

### <a name="before-you-get-started"></a>使用を開始する前に

> [!IMPORTANT]
> ポリシーをグループに割り当てると、ポリシー割り当ては優先順位ルールに従ってグループのメンバーに伝達されます。 たとえば、ユーザーにポリシーが (個別に、またはバッチ割り当てによって) 直接割り当てられる場合、そのポリシーはグループから継承されたポリシーよりも優先されます。 つまり、ユーザーに直接割り当てられた会議ポリシーがある場合は、セキュリティ グループから会議ポリシーを継承する前に、ユーザーからその会議ポリシーを削除する必要があります。

使用を開始する前に、[優先規則](assign-policies.md#precedence-rules)と[グループ割り当てのランク付け](assign-policies.md#group-assignment-ranking)を理解することが重要です。 **グループへのポリシー割り当 [](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)** てについて理解する必要がある概念を読んで理解してください。

スタッフと教育者がセキュリティ グループから会議ポリシーを継承するには、これらすべての手順を完了する必要があります。

1. [セキュリティ グループを作成します](#create-security-groups)。
2. [セキュリティ グループにポリシーを割り当てる](#assign-a-policy-to-a-security-group)。
3. [ユーザーに直接割り当てられたポリシーを削除します](#remove-a-policy-that-was-directly-assigned-to-users)。

### <a name="create-security-groups"></a>セキュリティ グループを作成する

最初に、スタッフと教育者用のセキュリティ グループを作成します。

School [Data Sync](/SchoolDataSync/) (SDS) を使用すると、学校の教育者と学生のセキュリティ グループ [を簡単に](/SchoolDataSync/edu-security-groups) 作成できます。 SDS を使用して、学校のポリシーを管理するために必要なセキュリティ グループを作成することをお勧めします。

環境内で SDS を展開できない場合は、この [PowerShell](scripts/powershell-script-security-groups-edu.md) スクリプトを使用して 2 つのセキュリティ グループを作成します。1 つは、Faculty ライセンスが割り当てられているすべてのスタッフと教育者用と、Student ライセンスが割り当てられているすべての学生用です。 グループを最新の状態に保つには、このスクリプトを日常的に実行する必要があります。

### <a name="assign-a-policy-to-a-security-group"></a>セキュリティ グループにポリシーを割り当てる

#### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

> [!NOTE]
> 現在、Microsoft Teams 管理センターを使用したグループへのポリシー割り当ては、Teams 通話ポリシー、Teams コール パーク ポリシー、Teams ポリシー、Teams ライブ イベント ポリシー、Teams 会議ポリシー、Teams メッセージ ポリシーでのみ使用できます。 他のポリシーの種類については、PowerShell を使用してください。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。
2. **グループ ポリシーの割り当て** タブを選択します。
3. **[グループの追加]** を選択し、**[ポリシーをグループに割り当てる]** ウィンドウで、次の操作を行います:

    ![会議ポリシーが表示されている [設定の編集] ウィンドウのスクリーンショット](media/batch-group-policy-assignment-edu-group.png)
    1. [グループ **の選択] ボックス** で、スタッフと教師を含むセキュリティ グループを検索して追加します。
    2. [ランクの **選択] ボックスに****「1」と入力します**。
    3. [ポリシー **の選択] ボックスで****、[EducatorMeetingPolicy] を選択します**。
    4. **[適用]** を選択します。

グループ ポリシーの割り当てを削除するには、ポリシー ページの **[グループ ポリシーの割り当て]** タブで、グループの割り当てを選び、**[削除]** を選択します。

グループ割り当てのランク付けを変更するには、最初にグループ ポリシーの割り当てを削除する必要があります。 次に、上記の手順に従ってポリシーをグループに割り当てます。

#### <a name="using-powershell"></a>PowerShell の使用

> [!NOTE]
> 現在、PowerShell を使用したグループへのポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。 サポートされているポリシー タイプの一覧については、[New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) を参照してください。

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

[Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)モジュール (まだインストールされていない場合) をインストールするには、次を実行します。 バージョン 1.0.5 以降をインストールしていることを確認します。

```powershell
Install-Module -Name MicrosoftTeams
```

以下を実行して Teams に接続しセッションを開始します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、管理者の資格情報を使用してサイン インします。

##### <a name="assign-a-policy-to-a-group"></a>ポリシーをグループに割り当てる

次の手順を実行して、EducatorMeetingPolicy という名前の会議ポリシーを、スタッフと教師を含むセキュリティ グループに割り当て、割り当てのランク付けを 1 に設定します。 セキュリティ グループを指定するには、オブジェクト ID、セッション開始プロトコル (SIP) アドレス、またはメール アドレスを使用します。 この例では、メール アドレス (staff-faculty@contoso.com)。

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>ユーザーに直接割り当てられたポリシーを削除する

ユーザーに (個別に、またはバッチ割り当てによって) ポリシーが直接割り当てられた場合は、そのポリシーが優先されます。 つまり、ユーザーに直接割り当てられた会議ポリシーがある場合は、セキュリティ グループから会議ポリシーを継承する前に、ユーザーからその会議ポリシーを削除する必要があります。

詳細については、「グループへのポリシー [割り当てについて知る必要がある情報」を参照してください](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)。

次の手順に従って、スタッフと教師に直接割り当てられた会議ポリシーを削除します。

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

[Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)モジュール (まだインストールされていない場合) をインストールするには、次を実行します。 バージョン 1.0.5 以降をインストールしていることを確認します。

```powershell
Install-Module -Name MicrosoftTeams
```

以下を実行して Teams に接続しセッションを開始します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、Azure AD への接続に使用したのと同じ管理者資格情報を使用してサインインします。

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>ユーザーに直接割り当てられたポリシーの割り当てを解除する

次の手順を実行して、そのポリシーが直接割り当てられたユーザーから会議ポリシーを削除します。 メール アドレスまたはオブジェクト ID でユーザーを指定できます。

この例では、会議ポリシーは、メール アドレスで指定されたユーザーから削除されます。

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

この例では、会議ポリシーは、"会議" という名前のテキスト ファイル内のユーザーのリストuser_ids.txt。

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>グループのポリシーの割り当てを取得する

特定のセキュリティ グループに割り当てられているすべてのポリシーを表示するには、次を実行します。 グループは、SIP アドレスまたはメール アドレスがポリシーの割り当てに使用された場合でも、常にグループ ID で一覧表示されます。

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>ユーザーに割り当てられているポリシーを取得する

特定のユーザーに割り当てられているすべてのポリシーを表示するには、次を実行します。 次の例では、ポリシーに割り当てられているポリシーを取得 reda@contoso.com。

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>ポリシーをユーザーのバッチに割り当てる

EducatorMeetingPolicy という名前のカスタム会議ポリシーを、スタッフと教師に一括で直接割り当てるには、次の手順に従います。

### <a name="using-powershell"></a>PowerShell の使用

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Azure AD PowerShell for Graph モジュールと Teams PowerShell モジュールに接続する

この記事の手順を実行する前に、(割り当てられたライセンスでユーザーを識別するために) Azure AD PowerShell for Graph モジュールと Microsoft Teams PowerShell モジュール (それらのユーザーにポリシーを割り当てる) をインストールして接続する必要があります。

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Azure AD PowerShell for Graph モジュールをインストールして接続する

管理者特権Windows PowerShellコマンド プロンプト (管理者として Windows PowerShell を実行) を開き、次の手順を実行して Azure Active Directory PowerShell for Graph モジュールをインストールします。

```powershell
Install-Module -Name AzureAD
```

以下を実行して、Azure AD に接続します。

```powershell
Connect-AzureAD
```

メッセージが表示されたら、管理者の資格情報を使用してサイン インします。

詳細については、「Azure Active Directory PowerShell for Graph モジュールで接続する [」を参照してください](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

[Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)モジュール (まだインストールされていない場合) をインストールするには、次を実行します。 バージョン 1.0.5 以降をインストールしていることを確認します。

```powershell
Install-Module -Name MicrosoftTeams
```

以下を実行して Teams に接続しセッションを開始します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、Azure AD への接続に使用したのと同じ管理者資格情報を使用してサインインします。

#### <a name="identify-your-users"></a>ユーザーを特定する

まず、次の手順を実行して、ライセンスの種類別にスタッフと教師を特定します。 これにより、組織で使用されている SKU が示されます。 その後、Faculty SKU が割り当てられている教職員と教師を特定できます。

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

この例では、出力は、Faculty ライセンス SKUId が "e97c048c-37a4-45fb-ab50-922fbf07a370" です。

> [!NOTE]
> Education SKU と SKU の一覧については [、「Education SKU リファレンス」を参照してください](sku-reference-edu.md)。

次に、次の手順を実行して、このライセンスを持つユーザーを特定し、それらをまとめて収集します。

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>ポリシーを一括で割り当てる

これで、適切なポリシーをユーザーに一括で割り当てます。 ポリシーを割り当てまたは更新できるユーザーの最大数は、一度に 5,000 人です。 たとえば、5,000 を超えるスタッフと教師がある場合は、複数のバッチを提出する必要があります。

次の手順を実行して、EducatorMeetingPolicy という名前のカスタム会議ポリシーをスタッフと教師に割り当てる。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> TeamsMessagingPolicy など、別のポリシーの種類を一括で割り当てるには、割り当てるポリシーとポリシー名に変更する ```PolicyType``` ```PolicyName``` 必要があります。

#### <a name="get-the-status-of-a-bulk-assignment"></a>一括割り当ての状態を取得する

一括割り当てごとに操作 ID が返されます。この ID を使用すると、ポリシー割り当ての進捗状況を追跡したり、発生する可能性のあるエラーを特定できます。 たとえば、次のコマンドを実行します。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

バッチ操作で各ユーザーの割り当ての状態を表示するには、次を実行します。 各ユーザーの詳細は、このプロパティ ```UserState``` にあります。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>ユーザー数が 5,000 を超える場合は、ポリシーを一括で割り当てる

まず、次の手順を実行して、スタッフと教師の数を確認します。

```powershell
$faculty.count
```

ユーザー ID の一覧全体を指定する代わりに、次の手順を実行して最初の 5,000、次の 5,000 を指定します。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

ユーザー ID の範囲は、ユーザーの完全なリストに到達するまで変更できます。 たとえば、最初のバッチに対して入力し、2 番目のバッチに使用し、3 番目のバッチに対して入力 ```$faculty[0..4999``` ```$faculty[5000..9999``` ```$faculty[10000..14999``` します。

#### <a name="get-the-policies-assigned-to-a-user"></a>ユーザーに割り当てられているポリシーを取得する

特定のユーザーに割り当てられているすべてのポリシーを表示するには、次を実行します。 次の例では、ポリシーに割り当てられているポリシーを取得 hannah@contoso.com。

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>よくあるご質問 (FAQ)

**PowerShell for Teams に詳しくない。詳しくは、どこで参照できますか?**

PowerShell を使用して Teams を管理する概要については [、「Teams PowerShell の概要」を参照してください](teams-powershell-overview.md)。 この記事で使用されるコマンドレットの詳細については、次を参照してください。

- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment)
- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>関連項目

- [ユーザーにポリシーを割り当てる](assign-policies.md)
- [Teams のポリシーと Education のポリシー パッケージ](policy-packages-edu.md)
- [Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)