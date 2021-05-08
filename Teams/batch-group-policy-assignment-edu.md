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
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>学校の大規模なユーザーにポリシーを割り当てる

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> ポリシーの割り当てに関する詳細については、「Microsoft Teams でポリシーをユーザーに割り当てる[」をTeams。](assign-policies.md)

## <a name="overview"></a>概要

学生と教師に、さまざまな機能へのアクセス権を与える必要Microsoft Teams。 ライセンスの種類によって組織内のユーザーをすばやく特定し、適切なポリシーを割り当てできます。 このチュートリアルでは、学校の大規模なユーザーに会議ポリシーを割り当てる方法について説明します。 管理センターと PowerShell の Microsoft Teamsを使用してポリシーを割り当て、両方の方法について説明します。

会議ポリシーは、ユーザーがメンバーであるセキュリティ グループに割り当てるか、バッチ ポリシーの割り当てによって大規模なユーザーに直接割り当てできます。 次の方法について学習します。

- **グループ [へのポリシーの割り当てを使用](#assign-a-policy-to-a-group) して、セキュリティ グループに会議ポリシーを割り当てる (推奨)**。 この方法では、グループ メンバーシップに基づいてポリシーを割り当てできます。 セキュリティ グループまたは配布リストにポリシーを割り当てできます。 メンバーがグループに追加またはグループから削除されると、そのメンバーの継承されたポリシー割り当てが更新されます。 この方法を使用することをお勧めします。これは、新しいユーザーのポリシーを管理する時間を短縮したり、ユーザーのロールが変更された場合に時間を削減したりするために使用することをお勧めします。 この方法は、最大 50,000 人のユーザーのグループに最適ですが、より大きなグループでも機能します。

- **バッチ [ポリシーの割り当てを使用](assign-policies.md#assign-a-policy-to-a-batch-of-users)して、会議ポリシーをユーザーに直接一括で割り当てる。** 一度に最大 5,000 人のユーザーにポリシーを割り当てできます。 ユーザー数が 5,000 を超える場合は、複数のバッチを送信できます。 この方法では、新しいユーザーが作成された場合、それらの新しいユーザーにポリシーを割り当てるバッチ割り当てを再び実行する必要があります。

Teamsでは、カスタム ポリシーを作成して割り当てない限り、Teams ポリシーの種類に対してグローバル (組織全体の既定) ポリシーが自動的に取得されます。 学生の人口は多くの場合、最大のユーザー セットであり、最も制限の厳しい設定を受け取る場合が多いので、次の手順を実行することをお勧めします。

- プライベート チャットや会議のスケジュール設定などのコア機能を許可し、そのポリシーをスタッフや教師に割り当てるカスタム ポリシーを作成します。
- カスタム ポリシーをスタッフと教師に割り当てる。
- グローバル (組織全体の既定) ポリシーを編集して適用し、学生の機能を制限します。

カスタム ポリシーを作成してスタッフや教師に割り当てるまで、グローバル ポリシーは学校のすべてのユーザーに適用されます。

このチュートリアルでは、学生はグローバル会議ポリシーを取得し、EducatorMeetingPolicy という名前のカスタム会議ポリシーをスタッフと教師に割り当てる必要があります。 グローバル ポリシーを編集して学生の会議設定を調整し、スタッフと教師の[](policy-packages-edu.md)会議エクスペリエンスを定義するカスタム ポリシーを作成したと想定しています。

![管理センターの [会議ポリシー] ページTeamsスクリーンショット](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>ポリシーをグループに割り当てる

次の手順に従って、スタッフと教師のセキュリティ グループを作成し、そのセキュリティ グループに EducatorMeetingPolicy という名前のカスタム会議ポリシーを割り当てる必要があります。

### <a name="before-you-get-started"></a>使用を開始する前に

> [!IMPORTANT]
> グループにポリシーを割り当てると、優先順位ルールに従ってポリシーの割り当てがグループのメンバーに伝達されます。 たとえば、ユーザーに (個別またはバッチ割り当てによって) ポリシーが直接割り当てられている場合、そのポリシーはグループから継承されたポリシーよりも優先されます。 また、ユーザーに直接割り当てられた会議ポリシーがある場合は、セキュリティ グループから会議ポリシーを継承する前に、その会議ポリシーをユーザーから削除する必要があります。

使用を開始する前に、[優先規則](assign-policies.md#precedence-rules)と[グループ割り当てのランク付け](assign-policies.md#group-assignment-ranking)を理解することが重要です。 **グループへのポリシー割り当 [](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)** てについて知る必要がある概念を必ず読んで理解してください。

スタッフと教師がセキュリティ グループから会議ポリシーを継承するには、これらすべての手順を完了する必要があります。

1. [セキュリティ グループ を作成します](#create-security-groups)。
2. [セキュリティ グループにポリシーを割り当てる](#assign-a-policy-to-a-security-group)。
3. [ユーザーに直接割り当てられたポリシーを削除します](#remove-a-policy-that-was-directly-assigned-to-users)。

### <a name="create-security-groups"></a>セキュリティ グループを作成する

まず、スタッフと教師のセキュリティ グループを作成します。

セキュリティ[学校データ同期](/SchoolDataSync/)(SDS) を使用すると、学校でセキュリティ グループ[の教師と学生を簡単に](/SchoolDataSync/edu-security-groups)作成できます。 SDS を使用して、学校のポリシーを管理するために必要なセキュリティ グループを作成することをお勧めします。

環境内で SDS をデプロイできない場合は、この [PowerShell](scripts/powershell-script-security-groups-edu.md) スクリプトを使用して 2 つのセキュリティ グループを作成します。1 つは、教職員のライセンスが割り当てられているすべてのスタッフと教師用、もう 1 つは学生ライセンスが割り当てられているすべての学生用です。 グループを最新の状態に保つには、このスクリプトを定期的に実行する必要があります。

### <a name="assign-a-policy-to-a-security-group"></a>セキュリティ グループにポリシーを割り当てる

#### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

> [!NOTE]
> 現在、Microsoft Teams 管理センターを使用したグループへのポリシー割り当ては、Teams 通話ポリシー、Teams コール パーク ポリシー、Teams ポリシー、Teams ライブ イベント ポリシー、Teams 会議ポリシー、Teams メッセージ ポリシーでのみ使用できます。 他のポリシーの種類については、PowerShell を使用してください。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。
2. **グループ ポリシーの割り当て** タブを選択します。
3. **[グループの追加]** を選択し、**[ポリシーをグループに割り当てる]** ウィンドウで、次の操作を行います:

    ![会議ポリシーが表示されている [設定の編集] ウィンドウのスクリーンショット](media/batch-group-policy-assignment-edu-group.png)
    1. [グループ **の選択] ボックス** で、スタッフと教師を含むセキュリティ グループを検索して追加します。
    2. [ランク **の選択] ボックスに****「1」と入力します**。
    3. [ポリシー **の選択] ボックスで****、[EducatorMeetingPolicy] を選択します**。
    4. **[適用]** を選択します。

グループ ポリシーの割り当てを削除するには、ポリシー ページの **[グループ ポリシーの割り当て]** タブで、グループの割り当てを選び、**[削除]** を選択します。

グループ割り当てのランク付けを変更するには、最初にグループ ポリシーの割り当てを削除する必要があります。 次に、上記の手順に従ってポリシーをグループに割り当てます。

#### <a name="using-powershell"></a>PowerShell の使用

> [!NOTE]
> 現在、PowerShell を使用したグループへのポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。 サポートされているポリシー タイプの一覧については、[New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) を参照してください。

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

PowerShell モジュールをインストールするには[Teamsを実行](https://www.powershellgallery.com/packages/MicrosoftTeams)します (まだインストールされていない場合)。 バージョン 1.0.5 以降をインストールしていることを確認します。

```powershell
Install-Module -Name MicrosoftTeams
```

以下を実行して Teams に接続しセッションを開始します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、管理者の資格情報を使用してサイン インします。

##### <a name="assign-a-policy-to-a-group"></a>ポリシーをグループに割り当てる

次のコマンドを実行して、EducatorMeetingPolicy という名前の会議ポリシーを、スタッフと教師を含むセキュリティ グループに割り当て、割り当てのランク付けを 1 に設定します。 セキュリティ グループは、オブジェクト ID、セッション開始プロトコル (SIP) アドレス、または電子メール アドレスを使用して指定できます。 この例では、メール アドレス (staff-faculty@contoso.com) を使用します。

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>ユーザーに直接割り当てられたポリシーを削除する

ユーザーにポリシーが直接割り当てられた場合 (個別に割り当てたり、バッチ割り当てによって割り当てたりした場合)、そのポリシーが優先されます。 つまり、ユーザーに直接割り当てられた会議ポリシーがある場合は、セキュリティ グループから会議ポリシーを継承する前に、その会議ポリシーをユーザーから削除する必要があります。

詳細については、「グループへのポリシー [の割り当てについて知る必要がある情報」を参照してください](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)。

次の手順に従って、スタッフと教師に直接割り当てられた会議ポリシーを削除します。

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

PowerShell モジュールをインストールするには[Teamsを実行](https://www.powershellgallery.com/packages/MicrosoftTeams)します (まだインストールされていない場合)。 バージョン 1.0.5 以降をインストールしていることを確認します。

```powershell
Install-Module -Name MicrosoftTeams
```

以下を実行して Teams に接続しセッションを開始します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、Azure アカウントへの接続に使用したのと同じ管理者資格情報を使用してAD。

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>ユーザーに直接割り当てられたポリシーの割り当てを解除する

次のコマンドを実行して、そのポリシーを直接割り当てられたユーザーから会議ポリシーを削除します。 メール アドレスまたはオブジェクト ID でユーザーを指定できます。

この例では、会議ポリシーは、メール アドレスで指定されたユーザーから削除されます。

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

次のコマンドを実行して、特定のセキュリティ グループに割り当てられているすべてのポリシーを確認します。 SIP アドレスまたは電子メール アドレスがポリシーの割り当てに使用された場合でも、グループは常にグループ ID で一覧表示されます。

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>ユーザーに割り当てられているポリシーを取得する

次のコマンドを実行して、特定のユーザーに割り当てられているすべてのポリシーを表示します。 次の例は、ポリシーに割り当てられているポリシーを取得する方法を示 reda@contoso.com。

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>ポリシーをユーザーのバッチに割り当てる

次の手順に従って、EducatorMeetingPolicy という名前のカスタム会議ポリシーを、スタッフと教師に直接一括で割り当てる必要があります。

### <a name="using-powershell"></a>PowerShell の使用

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Connect Azure AD PowerShell for Graph PowerShell モジュールTeamsにアクセスする

この記事の手順を実行する前に、Azure AD PowerShell for Graph モジュール (割り当てられたライセンスでユーザーを識別するために) と Microsoft Teams PowerShell モジュール (これらのユーザーにポリシーを割り当てる) をインストールして接続する必要があります。

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Azure AD PowerShell for Graph モジュールをインストールして接続する

管理者特権Windows PowerShell コマンド プロンプト (管理者として Windows PowerShell を実行) を開き、次のコマンドを実行して Azure Active Directory PowerShell for Graph モジュールをインストールします。

```powershell
Install-Module -Name AzureAD
```

以下を実行して、Azure AD に接続します。

```powershell
Connect-AzureAD
```

メッセージが表示されたら、管理者の資格情報を使用してサイン インします。

詳細については[、「powerShell for Connect モジュールを使用Azure Active Directory」をGraphしてください](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

PowerShell モジュールをインストールするには[Teamsを実行](https://www.powershellgallery.com/packages/MicrosoftTeams)します (まだインストールされていない場合)。 バージョン 1.0.5 以降をインストールしていることを確認します。

```powershell
Install-Module -Name MicrosoftTeams
```

以下を実行して Teams に接続しセッションを開始します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、Azure アカウントへの接続に使用したのと同じ管理者資格情報を使用してAD。

#### <a name="identify-your-users"></a>ユーザーを特定する

まず、次のコマンドを実行して、ライセンスの種類別にスタッフと教師を特定します。 これにより、組織で使用されている SKU が示されます。 その後、教職員 SKU が割り当てられているスタッフと教師を識別できます。

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

この例の出力では、Faculty ライセンス SKUId が "e97c048c-37a4-45fb-ab50-922fbf07a370" である必要があります。

> [!NOTE]
> Education SKU と SKU の一覧を表示するには [、「Education SKU リファレンス」を参照してください](sku-reference-edu.md)。

次に、次のコマンドを実行して、このライセンスを持つユーザーを特定し、それらをまとめて収集します。

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>ポリシーを一括で割り当てる

次に、適切なポリシーをユーザーに一括で割り当てます。 ポリシーを割り当てまたは更新できるユーザーの最大数は、一度に 5,000 人です。 たとえば、5,000 人を超えるスタッフと教師がある場合は、複数のバッチを送信する必要があります。

次のコマンドを実行して、EducatorMeetingPolicy という名前のカスタム会議ポリシーをスタッフと教師に割り当てる。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> TeamsMessagingPolicy など、別のポリシーの種類を一括で割り当てるには、割り当てるポリシーとポリシー名に変更する ```PolicyType``` ```PolicyName``` 必要があります。

#### <a name="get-the-status-of-a-bulk-assignment"></a>一括割り当ての状態を取得する

各一括割り当ては操作 ID を返します。この ID を使用して、ポリシー割り当ての進行状況を追跡したり、発生する可能性のあるエラーを特定したりすることができます。 たとえば、次のコマンドを実行します。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

バッチ操作で各ユーザーの割り当て状態を表示するには、次を実行します。 各ユーザーの詳細は プロパティにあります ```UserState``` 。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>ユーザー数が 5,000 人を超える場合は、ポリシーを一括で割り当てる

まず、次のコマンドを実行して、使用しているスタッフと教師の数を確認します。

```powershell
$faculty.count
```

ユーザー ID の一覧全体を指定する代わりに、次のコマンドを実行して最初の 5,000、次の 5,000 などと指定します。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

ユーザー ID の範囲は、ユーザーの完全な一覧に到達するまで変更できます。 たとえば、最初のバッチに「」と入力し、2 番目のバッチにを使用し、3 番目のバッチに「」と ```$faculty[0..4999``` ```$faculty[5000..9999``` ```$faculty[10000..14999``` 入力します。

#### <a name="get-the-policies-assigned-to-a-user"></a>ユーザーに割り当てられているポリシーを取得する

次のコマンドを実行して、特定のユーザーに割り当てられているすべてのポリシーを表示します。 次の例は、ポリシーに割り当てられているポリシーを取得する方法を hannah@contoso.com。

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>よくあるご質問 (FAQ)

**PowerShell の使用に慣Teams。詳細については、どこで学習できますか?**

PowerShell を使用して管理する方法の概要については、「PowerShell Teams」をTeams[を参照してください](teams-powershell-overview.md)。 この記事で使用するコマンドレットの詳細については、以下を参照してください。

- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment)
- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>関連トピック

- [ユーザーにポリシーを割り当てる](assign-policies.md)
- [教育機関向け Teams ポリシーおよびポリシー パッケージ](policy-packages-edu.md)
- [Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)