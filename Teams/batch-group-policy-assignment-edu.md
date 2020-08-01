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
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>学校の大規模なユーザーセットにポリシーを割り当てる

> [!NOTE]
> Microsoft Teams でポリシーを割り当てる方法については、「 [Teams でユーザーにポリシーを割り当てる](assign-policies.md)」を参照してください。

## <a name="overview"></a>概要

学生や教師が Microsoft Teams のさまざまな機能にアクセスできるようにする必要がありますか? ライセンスの種類によって組織内のユーザーをすばやく特定し、適切なポリシーを割り当てることができます。 このチュートリアルでは、学校の大規模なユーザーセットに会議ポリシーを割り当てる方法について説明します。 Microsoft Teams 管理センターと PowerShell を使用してポリシーを割り当てることができます。両方の方法が表示されます。

ユーザーがメンバーになっているセキュリティグループまたはユーザーが、バッチポリシーの割り当てを使用して、ユーザーが直接ユーザーに所属するセキュリティグループに会議ポリシーを割り当てることができます。 次の方法について説明します。

- **[ポリシーの割り当てをグループに](#assign-a-policy-to-a-group)使用して、会議ポリシーをセキュリティグループに割り当てる (推奨)** この方法では、グループメンバーシップに基づいてポリシーを割り当てることができます。 セキュリティグループまたは配布リストにポリシーを割り当てることができます。 メンバーがグループに追加またはグループから削除されると、それに応じて継承されたポリシーの割り当てが更新されます。 新しいユーザーのポリシーを管理する時間を短縮したり、ユーザーの役割が変更されたりするため、この方法を使用することをお勧めします。 この方法は、最大5万ユーザーのグループに最適ですが、大規模なグループでも動作します。

- **[バッチポリシーの割り当て](assign-policies.md#assign-a-policy-to-a-batch-of-users)を使用して、ユーザーに対して直接会議ポリシーを割り当てることが**できます。 一度に最大5000ユーザーのポリシーを割り当てることができます。 5000を超えるユーザーがいる場合は、複数のバッチを送信できます。 この方法では、新しいユーザーがいる場合は、バッチ割り当てを再実行して、これらの新規ユーザーにポリシーを割り当てる必要があります。

ユーザーは、カスタムポリシーを作成して割り当てることがない限り、チームポリシーの種類に対してグローバル (組織全体の既定の) ポリシーを自動的に取得することに注意してください。 学生の人口は、多くの場合、多くの場合、最も制限の厳しいユーザーであるため、次の手順を実行することをお勧めします。

- プライベートチャットや会議のスケジュールなどのコア機能を利用できるようにするカスタムポリシーを作成し、そのポリシーをスタッフや教師に割り当てます。
- ユーザー設定のポリシーをスタッフや教師に割り当てます。
- グローバル (組織全体の既定) ポリシーを編集して適用し、学生の機能を制限します。

グローバルポリシーは、ユーザー設定のポリシーを作成して、それをスタッフや教師に割り当てるまで、学校のすべてのユーザーに適用されることに注意してください。

このチュートリアルでは、学生がグローバル会議ポリシーを取得し、EducatorMeetingPolicy という名前のユーザー設定の会議ポリシーをスタッフと教師に割り当てます。 このグローバルポリシーを編集して学生の会議の設定を変更し、スタッフや教師の会議の動作を定義する[カスタムポリシーを作成](policy-packages-edu.md)していることを前提としています。

![Teams 管理センターの [会議のポリシー] ページのスクリーンショット](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>グループにポリシーを割り当てる

次の手順に従って、スタッフと教師のセキュリティグループを作成し、EducatorMeetingPolicy という名前のカスタム会議ポリシーをそのセキュリティグループに割り当てます。

### <a name="before-you-get-started"></a>使用を開始する前に

> [!IMPORTANT]
> ポリシーをグループに割り当てると、ポリシーの割り当ては優先順位の規則に従ってグループのメンバーに伝達されます。 たとえば、ユーザーに直接ポリシーが割り当てられている場合 (個別またはバッチ割り当て経由)、そのポリシーは、グループから継承されたポリシーよりも優先されます。 これは、ユーザーが直接割り当てた会議ポリシーを持っている場合は、ユーザーがセキュリティグループから会議ポリシーを継承する前に、そのユーザーからその会議ポリシーを削除する必要があることを意味します。

作業を始める前に、[優先順位の規則](assign-policies.md#precedence-rules)とグループの[割り当ての順位](assign-policies.md#group-assignment-ranking)を理解することが重要です。 **[グループへのポリシーの割り当てについて知っておく必要が](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)ある概念を読んで理解している**ことを確認してください。

スタッフおよび教師がセキュリティグループから会議ポリシーを継承できるようにするには、次のすべての手順を完了する必要があります。

1. [セキュリティグループを作成](#create-security-groups)します。
2. [セキュリティグループにポリシーを割り当て](#assign-a-policy-to-a-security-group)ます。
3. [ユーザーに直接割り当てられたポリシーを削除](#remove-a-policy-that-was-directly-assigned-to-users)します。

### <a name="create-security-groups"></a>セキュリティグループを作成する

最初に、スタッフと教師のセキュリティグループを作成します。

[School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS) を使用すると、学校で[セキュリティグループの教師と学生を簡単に作成](https://docs.microsoft.com/SchoolDataSync/edu-security-groups)できます。 SDS を使用して、学校のポリシーを管理するために必要なセキュリティグループを作成することをお勧めします。

使用している環境に SDS を展開できない場合は、[次の PowerShell スクリプト](scripts/powershell-script-security-groups-edu.md)を使用して、教職員用ライセンスが割り当てられているすべての従業員と、学生用ライセンスが割り当てられているすべての学生用に、2つのセキュリティグループを作成します。 グループを最新の状態に維持するには、このスクリプトを定期的に実行する必要があります。

### <a name="assign-a-policy-to-a-security-group"></a>セキュリティグループにポリシーを割り当てる

#### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

> [!NOTE]
> 現時点では、Microsoft Teams 管理センターを使用したグループへのポリシーの割り当ては、Teams の通話ポリシー、Teams の通話パークポリシー、チームポリシー、Teams live イベントポリシー、teams 会議ポリシー、および Teams のメッセージングポリシーでのみ利用できます。 その他のポリシーの種類については、PowerShell を使用します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。
2. [**グループポリシーの割り当て**] タブを選択します。
3. [**グループの追加**] を選択し、[**ポリシーをグループに割り当てる**] ウィンドウで、次の操作を行います。

    ![会議のポリシーが表示されている [設定の編集] ウィンドウのスクリーンショット](media/batch-group-policy-assignment-edu-group.png)
    1. **[グループの選択**] ボックスで、スタッフと教師が含まれているセキュリティグループを検索して追加します。
    2. **[ランクの選択**] ボックスに「 **1**」と入力します。
    3. [**ポリシーの選択**] ボックスで、[ **EducatorMeetingPolicy**] を選びます。
    4. [**適用**] を選びます。

グループポリシーの割り当てを削除するには、[ポリシー] ページの [**グループポリシーの割り当て**] タブで、グループの割り当てを選択し、[**削除**] を選択します。

グループの割り当ての順位を変更するには、最初にグループポリシーの割り当てを削除する必要があります。 次に、上記の手順に従って、ポリシーをグループに割り当てます。

#### <a name="using-powershell"></a>PowerShell を使用する場合

> [!NOTE]
> 現在、PowerShell を使用したグループへのポリシーの割り当ては、すべてのチームポリシーの種類では使用できません。 サポートされているポリシーの種類の一覧については、「[新しい-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 」を参照してください。

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

次を実行して[Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールします (まだインストールされていない場合)。 バージョン1.0.5 以降をインストールしていることを確認してください。

```powershell
Install-Module -Name MicrosoftTeams
```

Teams に接続してセッションを開始するには、次を実行します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、管理者の資格情報を使用してサインインします。

##### <a name="assign-a-policy-to-a-group"></a>グループにポリシーを割り当てる

次を実行して、EducatorMeetingPolicy という名前の会議ポリシーを、スタッフと教師が含まれているセキュリティグループに割り当て、割り当ての順位を1に設定します。 オブジェクト Id、セッション開始プロトコル (SIP) アドレス、またはメールアドレスを使用して、セキュリティグループを指定できます。 この例では、メールアドレス (staff-faculty@contoso.com) を使用しています。

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>ユーザーに直接割り当てられたポリシーを削除する

ユーザーに直接ポリシーが割り当てられている場合 (個別に、またはバッチ割り当てによって)、ポリシーが優先されることに注意してください。 つまり、ユーザーに直接割り当てられた会議ポリシーがある場合は、ユーザーがセキュリティグループから会議ポリシーを継承できるようにするには、そのユーザーからその会議ポリシーを削除する必要があります。

詳細については、「[グループに対するポリシーの割り当てについて知っ](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)ておくべきこと」を参照してください。

この手順に従って、スタッフと教師に直接割り当てられた会議ポリシーを削除します。

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

次を実行して[Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールします (まだインストールされていない場合)。 バージョン1.0.5 以降をインストールしていることを確認してください。

```powershell
Install-Module -Name MicrosoftTeams
```

Teams に接続してセッションを開始するには、次を実行します。

```powershell
Connect-MicrosoftTeams
```
メッセージが表示されたら、Azure AD への接続に使用したのと同じ管理者資格情報を使用してサインインします。

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>ユーザーに直接割り当てられたポリシーの割り当てを解除する

直接ポリシーを割り当てたユーザーから会議ポリシーを削除するには、次を実行します。 ユーザーは、メールアドレスまたはオブジェクト ID で指定できます。

この例では、ユーザーのメールアドレスで指定されたユーザーから会議ポリシーが削除されています。

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

この例では、会議のポリシーが、user_ids.txt という名前のテキストファイルのユーザーリストから削除されています。 

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>グループのポリシー割り当てを取得する

特定のセキュリティグループに割り当てられているポリシーをすべて表示するには、次を実行します。 グループは、その SIP アドレスまたはメールアドレスがポリシーの割り当てに使用されていた場合でも、常にグループ Id によって一覧表示されることに注意してください。

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>ユーザーに割り当てられているポリシーを取得する

特定のユーザーに割り当てられているすべてのポリシーを表示するには、次を実行します。 次の例は、reda@contoso.com に割り当てられているポリシーを取得する方法を示しています。

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>ユーザーのバッチにポリシーを割り当てる

次の手順に従って、EducatorMeetingPolicy という名前のカスタム会議ポリシーを、自分のスタッフと教師に一括して割り当てます。

### <a name="using-powershell"></a>PowerShell を使用する場合

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Azure AD PowerShell for Graph モジュールと Teams PowerShell モジュールに接続する

この記事の手順を実行する前に、Graph モジュール用の Azure AD PowerShell (割り当てられているライセンスによってユーザーを識別する) と Microsoft Teams PowerShell モジュール (これらのユーザーにポリシーを割り当てる) をインストールして接続する必要があります。

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Graph モジュール用 Azure AD PowerShell にインストールして接続する

昇格された Windows PowerShell コマンドプロンプト (管理者として Windows PowerShell を実行) を開き、次のコマンドを実行して、Azure Active Directory PowerShell for Graph モジュールをインストールします。

```powershell
Install-Module -Name AzureAD
```

Azure AD に接続するには、次を実行します。

```powershell
Connect-AzureAD
```

メッセージが表示されたら、管理者の資格情報を使用してサインインします。

詳細については、「 [Graph の Azure Active Directory PowerShell で接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)する」を参照してください。

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

次を実行して[Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールします (まだインストールされていない場合)。 バージョン1.0.5 以降をインストールしていることを確認してください。

```powershell
Install-Module -Name MicrosoftTeams
```

Teams に接続してセッションを開始するには、次を実行します。

```powershell
Connect-MicrosoftTeams
```
メッセージが表示されたら、Azure AD への接続に使用したのと同じ管理者資格情報を使用してサインインします。

#### <a name="identify-your-users"></a>ユーザーを特定する

最初に、次を実行して、ライセンスの種類別にスタッフと教師を特定します。 これは、組織で使用されている Sku を示します。 次に、教職員の SKU が割り当てられているスタッフと教師を特定することができます。

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

戻り値:

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

この例では、教職員ライセンスの SkuId が "e97c048c-37a4-45fb-ab50-922fbf07a370" であることが出力されます。

> [!NOTE]
> 教育機関の sku と SKU Id の一覧については、「[教育機関向けリファレンス](sku-reference-edu.md)」をご覧ください。

次に、このライセンスを所有しているユーザーを特定し、それらをすべてまとめて収集するために、次の処理を実行します。

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>ポリシーをまとめて割り当てる

次に、適切なポリシーをユーザーにまとめて割り当てます。 ポリシーの割り当てまたは更新ができるユーザーの最大数は、一度に5000です。 たとえば、5000のスタッフと教師を超えている場合は、複数のバッチを送信する必要があります。

次を実行して、EducatorMeetingPolicy という名前のカスタム会議ポリシーを、スタッフと教師に割り当てます。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> TeamsMessagingPolicy などの別のポリシータイプを一括で割り当てるには、割り当てるポリシーとポリシー名に変更する必要があり ```PolicyType``` ```PolicyName``` ます。

#### <a name="get-the-status-of-a-bulk-assignment"></a>一括割り当ての状態を取得する

各一括割り当てでは、操作 ID が返されます。この ID を使用して、ポリシー割り当ての進捗状況を追跡したり、発生する可能性のあるエラーを特定したりすることができます。 たとえば、次のように実行します。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

バッチ処理の各ユーザーの割り当て状態を表示するには、次を実行します。 各ユーザーの詳細がプロパティに表示され ```UserState``` ます。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>5000を超えるユーザーがいる場合にポリシーを一括で割り当てる

まず、次の手順を実行して、所有しているスタッフと教師の数を確認します。

```powershell
$faculty.count
```

ユーザー Id のリスト全体を指定する代わりに、次のようにして最初の5000を指定し、その後に次の5000を実行します。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

ユーザー Id の範囲は、すべてのユーザーのリストに到達するまで変更できます。 たとえば、 ```$faculty[0..4999``` 最初のバッチに対しては enter、2番目のバッチには、3番目のバッチに対してを使用し ```$faculty[5000..9999``` ```$faculty[10000..14999``` ます。

#### <a name="get-the-policies-assigned-to-a-user"></a>ユーザーに割り当てられているポリシーを取得する

特定のユーザーに割り当てられているすべてのポリシーを表示するには、次を実行します。 次の例は、hannah@contoso.com に割り当てられているポリシーを取得する方法を示しています。

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>FAQ

**私はチームの PowerShell については詳しくありません。詳細情報はどこで入手できますか?**

PowerShell を使用してチームを管理する方法の概要については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。 この記事で使用されているコマンドレットの詳細については、以下を参照してください。

- [新しい CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [CsGroupPolicyAssignment の取得](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [新規-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [CsUserPolicyAssignment を取得する](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>関連項目

- [ユーザーにポリシーを割り当てる](assign-policies.md)
- [教育機関向けのチームポリシーとポリシーパッケージ](policy-packages-edu.md)
- [Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)
