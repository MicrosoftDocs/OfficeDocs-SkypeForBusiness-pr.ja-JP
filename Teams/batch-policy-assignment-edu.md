---
title: 学校の大規模なユーザーセットにポリシーを割り当てる
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: バッチポリシーの割り当てを使用して、リモート学校 (teleschool、tele) の目的で、教育機関の多数のユーザーにポリシーを割り当てる方法について説明します。
f1keywords: ''
ms.openlocfilehash: e95c6b035298ce583a0ad34a030f2086b7c12ff3
ms.sourcegitcommit: 33bec766519397f898518a999d358657a413924c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583359"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>学校の大規模なユーザーセットにポリシーを割り当てる

学生や教師が Microsoft Teams のさまざまな機能にアクセスできるようにする必要がありますか? ライセンスの種類によって組織内のユーザーをすばやく特定し、適切なポリシーを割り当てることができます。 このチュートリアルでは、[バッチポリシーの割り当て](assign-policies.md#assign-a-policy-to-a-batch-of-users)を使用して、会議ポリシーを一括してユーザーに割り当てる方法について説明します。

ユーザーは、カスタムポリシーを作成して割り当てることがない限り、チームポリシーの種類に対してグローバル (組織全体の既定の) ポリシーを自動的に取得することに注意してください。 学生の人口は、多くの場合、多くの場合、最も制限の厳しいユーザーであるため、次の手順を実行することをお勧めします。

- グローバル (組織全体の既定) ポリシーを編集して適用し、学生の機能を制限します。 
- プライベートチャットや会議のスケジュールなどのコア機能を利用できるようにするカスタムポリシーを作成し、そのポリシーをスタッフや教師に割り当てます。

グローバルポリシーは、ユーザー設定のポリシーを作成して、それをスタッフや教師に割り当てるまで、学校のすべてのユーザーに適用されることに注意してください。

このチュートリアルでは、学生がグローバル会議ポリシーを取得し、PowerShell を使用して、EducatorMeetingPolicy という名前のカスタム会議ポリシーを一括して割り当てます。 このグローバルポリシーを編集して学生の会議の設定を変更し、スタッフや教師の会議の動作を定義するカスタムポリシーを作成していることを前提としています。

![Teams 管理センターの [会議のポリシー] ページのスクリーンショット](media/edu-batch-policy-assignment.png)

次の手順に従って、ユーザー設定の会議ポリシーをまとめて割り当てます。

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Azure AD PowerShell for Graph モジュールと Teams PowerShell モジュールに接続する

この記事の手順を実行する前に、Graph モジュール用の Azure AD PowerShell (割り当てられているライセンスによってユーザーを識別するため) と、プレリリース版の Microsoft Teams PowerShell モジュール (ポリシーを割り当てるため) にインストールして接続する必要があります。ユーザー)。

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Graph モジュール用 Azure AD PowerShell にインストールして接続する

昇格された Windows PowerShell コマンドプロンプト (管理者として Windows PowerShell を実行) を開き、次のコマンドを実行して、Azure Active Directory PowerShell for Graph モジュールをインストールします。

```powershell
Install-Module AzureAD
```

Azure AD に接続するには、次を実行します。

```powershell
Connect-AzureAD
```

メッセージが表示されたら、管理者の資格情報を使用してサインインします。

詳細については、「 [Graph の Azure Active Directory PowerShell で接続](https://docs.microsoft.com/eoffice365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)する」を参照してください。

### <a name="install-and-connect-to-the-pre-release-version-of-the-teams-powershell-module"></a>Teams PowerShell モジュールのプレリリース版をインストールして接続する

必要なコマンドレットは、Teams PowerShell モジュールのプレリリースバージョンに含まれています。 「 [Microsoft Teams powershell モジュールをインストールして接続](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module)する」の手順に従って、最初に使用可能なバージョンの teams powershell モジュール (インストールされている場合) をアンインストールしてから、PowerShell テストギャラリーから最新のプレリリース版のモジュールをインストールします。

Teams に接続してセッションを開始するには、次を実行します。

```powershell
Connect-MicrosoftTeams
```
メッセージが表示されたら、Azure AD への接続に使用したのと同じ管理者資格情報を使用してサインインします。

## <a name="identify-your-users"></a>ユーザーを特定する

最初に、次を実行して、ライセンスの種類別にスタッフと教師を特定します。 これは、組織で使用されている Sku を示します。 次に、教職員の SKU が割り当てられているスタッフと教師を特定することができます。

```powershell
Get-AzureADSubscribedSku
```

```powershell
$skus = Get-AzureADSubscribedSku
```

戻り値:

```
ObjectId                                                                  SkuPartNumber      SkuId
--------                                                                  -------------      -----
ee1a846c-79e9-4bc3-9189-011ca89be890_e97c048c-37a4-45fb-ab50-022fbf07a370 M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
ee1a846c-79e9-4bc3-9189-011ca89be890_46c119d4-0379-4a9d-85e4-97c66d3f909e M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

この例では、教職員ライセンスの SkuId が "e97c048c-37a4-45fb-ab50-922fbf07a370" であることが出力されます。

> [!NOTE]
> 教育機関の sku と SKU Id の一覧については、「[教育機関向けリファレンス](sku-reference-edu.md)」をご覧ください。

次に、このライセンスを所有しているユーザーを特定し、それらをすべてまとめて収集するために、次の処理を実行します。

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object (($_.assignedLicenses).SkuId -contains “e97c048c-37a4-45fb-ab50-922fbf07a370”)
```

## <a name="assign-a-policy-in-bulk"></a>ポリシーをまとめて割り当てる

次に、適切なポリシーをユーザーにまとめて割り当てます。 ポリシーの割り当てまたは更新ができるユーザーの最大数は、一度に2万です。 たとえば、2万のスタッフと教師を超えている場合は、複数のバッチを送信する必要があります。

次を実行して、EducatorMeetingPolicy という名前の会議ポリシーを、スタッフと教師に割り当てます。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> TeamsMessagingPolicy などの別のポリシータイプを一括で割り当てるには、割り当てるポリシーと```PolicyType``` ```PolicyName```ポリシー名に変更する必要があります。

## <a name="get-the-status-of-a-bulk-assignment"></a>一括割り当ての状態を取得する

各一括割り当てでは、操作 ID が返されます。この ID を使用して、ポリシー割り当ての進捗状況を追跡したり、発生する可能性のあるエラーを特定したりすることができます。 たとえば、次のように実行します。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

バッチ処理の各ユーザーの割り当て状態を表示するには、次を実行します。 各ユーザーの詳細が```UserState```プロパティに表示されます。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a>2万を超えるユーザーがいる場合にポリシーを一括で割り当てる

まず、次の手順を実行して、所有しているスタッフと教師の数を確認します。

```powershell
$faculty.count
```

ユーザー Id のリスト全体を指定する代わりに、次のようにして最初の2万を指定し、その後に次の2万を実行します。

```powershell
Assign-CsPolicy -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identities $faculty[0..19999].ObjectId
```

ユーザー Id の範囲は、すべてのユーザーのリストに到達するまで変更できます。 たとえば、最初の```$faculty[0..19999```バッチに対しては enter ```$faculty[20000..39999``` 、2番目```$faculty[40000..59999```のバッチには、3番目のバッチに対してを使用します。

## <a name="get-the-policies-assigned-to-a-user"></a>ユーザーに割り当てられているポリシーを取得する

特定のユーザーに割り当てられているすべてのポリシーを表示するには、次を実行します。 次の例は、hannah@contoso.com に割り当てられているポリシーを取得する方法を示しています。

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>FAQ

**学生、スタッフ、および教師であるすべてのユーザーが、自動的に割り当てられるライセンスを取得するようにします。どうすればよいですか?**

Teams 製品チームは、セキュリティグループへのポリシーの割り当てをサポートする作業を行っています。 この時点で、学生と教師のグループを作成し、そのグループに適切なポリシーを作成することができます。 明示的なユーザーの割り当て (このチュートリアルで割り当てたポリシーなど) により、グループから継承されたポリシーが上書きされることに注意してください。 この機能がサポートされている場合は、ポリシーの割り当てをグループに使用する方法と、継承したグループポリシーを確実に取得できるようにユーザーを更新する方法について説明します。

**私はチームの PowerShell については詳しくありません。詳細情報はどこで入手できますか?**

「 [Teams Powershell の概要](teams-powershell-overview.md)」をご覧ください。

## <a name="related-topics"></a>関連項目

- [ユーザーにポリシーを割り当てる](assign-policies.md)
- [新規-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [CsUserPolicyAssignment を取得する](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)