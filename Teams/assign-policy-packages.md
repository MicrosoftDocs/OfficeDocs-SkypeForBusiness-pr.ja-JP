---
title: ユーザーとグループにポリシー パッケージを割り当てる
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teamsのユーザーとグループにポリシー パッケージを割り当てるさまざまな方法について説明します。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 553e30fa694403b2ad5e2edfd86b53fe8231eed3
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015071"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>ユーザーとグループにポリシー パッケージを割り当てる

この記事では、Microsoft Teamsのユーザーとグループにポリシー パッケージを割り当てるさまざまな方法について説明します。 読む前に、「[Teamsのポリシーの割り当て - 作業の開始](policy-assignment-overview.md)」を参照してください。

> [!NOTE]
> カスタム ポリシー パッケージの割り当てを受け取るには、各ユーザーに Advanced Communications アドオンが必要です。 詳細については、「[Microsoft Teams 用 Advanced Communications アドオン](/microsoftteams/teams-add-on-licensing/advanced-communications)」を参照してください。

## <a name="assign-a-policy-package-to-users"></a>ポリシー パッケージをユーザーに割り当てる

Teams のポリシー パッケージは、組織内で同じまたは類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 各ポリシー パッケージは、ユーザーの役割に合わせて設計されており、その役割の一般的なアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。 ポリシー パッケージの例としては、教育機関 (教師) パッケージと医療機関 (医療従事者) パッケージがあります。 詳細については、「[Teams でポリシー パッケージを管理する](manage-policy-packages.md)」を参照してください。

### <a name="assign-a-policy-package-to-one-user"></a>ポリシー パッケージを 1 人のユーザーに割り当てる

1. Microsoft Teams管理センターの左側のナビゲーションで、[**ユーザー]** に移動し、ユーザーを選択します。

2. ユーザーのページで [ **ポリシー**] を選択し、[ **ポリシー パッケージ**] の横にある **[編集**] を選択します。

3. [ **ポリシー パッケージの割り当て** ] ウィンドウで、割り当てるパッケージを選択し、[保存] を選択 **します**。

![ユーザーへのポリシー パッケージの割り当ての管理センターのスクリーンショットをTeamsします。](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a>ポリシー パッケージを複数のユーザーに割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで **[ポリシー パッケージ]** に移動し、パッケージ名の左側をクリックして、割り当てるポリシー パッケージを選択します。

2. [**ユーザーを管理する**] を選択します。

3. [**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。 追加するユーザーごとに、この手順を繰り返します。

4. ユーザーの追加が完了したら、**[保存]** を選択します。


![複数のユーザーにポリシー パッケージを割り当てるための管理センターのスクリーンショットをTeamsします。](media/assign-policypackages-multipleusers.png)


## <a name="assign-a-policy-package-to-a-group"></a>ポリシー パッケージをグループに割り当てる

グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。 ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。 グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。

グループへのポリシー パッケージの割り当ては、最大 50,000 人のユーザーのグループに推奨されますが、大規模なグループでも機能します。

ポリシー パッケージを割り当てると、そのポリシーはすぐにグループに割り当てられます。 ただし、グループのメンバーへのポリシー割り当ての伝達はバックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があります。 ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。

> [!IMPORTANT]
> 作業を開始する前に、([優先順位ルール](assign-policies-users-and-groups.md#precedence-rules)) と ([グループ割り当ての順位付け](assign-policies-users-and-groups.md#group-assignment-ranking)) を理解しておくことが重要です。 この記事の前半の「([グループへのポリシーの割り当てについて知ってお](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)くべきこと)」の概念を読んで理解していることを確認してください。

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>管理センターのユーザーのグループにポリシー パッケージを割り当てる

1. Teams 管理センターにサインインします。

2. 左側のナビゲーションで、ポリシー パッケージ ページに移動します。

3. グループ ポリシーの割り当て タブを選択します。

4. [ **グループの追加]** を選択し、[グループにポリシー パッケージを割り当てる] ウィンドウで、次の操作を行います。

    1. ポリシー パッケージを割り当てるグループを検索して追加します。

    1. ポリシー パッケージを選択します。

    1. ポリシーの種類ごとにランク付けを設定します。

    1. **[適用]** を選択します。


       ![グループ ポリシーの割り当てを示します。](media/group-pkg-assignment.png)

5. 特定のポリシーの種類のランク付けを管理するには、特定のポリシー ページに移動します。

6. ポリシー パッケージをグループに再割り当てするには、まずグループ ポリシーの割り当てを削除します。 次に、上記の手順に従ってポリシー パッケージをグループに割り当てます。

### <a name="work-with-powershell"></a>PowerShell を使用する

#### <a name="get-the-teams-powershell-module"></a>Teams PowerShell モジュールを取得する

段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>ポリシー パッケージをユーザーのグループに割り当てる

[Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) コマンドレットを使用して、ポリシー パッケージをグループに割り当てます。 オブジェクト ID、SIP アドレス、または電子メール アドレスを使用してグループを指定できます。 ポリシー パッケージを割り当てるときに、ポリシー パッケージ内のポリシーの種類ごとに ([グループ割り当て順位付け](assign-policies-users-and-groups.md#group-assignment-ranking)) を指定します。

この例では、Education_Teacher ポリシー パッケージをグループに割り当て、TeamsAppSetupPolicy と TeamsMeetingBroadcastPolicy には 1 のランク付け、TeamsMeetingPolicy には 2 のランク付けを行います。

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>ポリシー パッケージをユーザーのバッチに割り当てる

バッチ ポリシー パッケージの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシー パッケージを割り当てることができます。 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、割り当てる一群のユーザーおよびポリシー パッケージを送信します。 割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。 その後、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチの割り当ての進捗状況と状態を追跡できます。

オブジェクト ID またはセッション開始プロトコル (SIP) アドレスでユーザーを指定します。 ユーザーの SIP アドレスは、多くの場合、ユーザー プリンシパル名 (UPN) または電子メール アドレスと同じ値を持っていますが、これは必須ではありません。 ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。 バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。

バッチには、最大 5,000 人のユーザーが含まれます。 最適な結果を得るには、一度に複数のバッチを送信しないでください。 さらにバッチを送信する前に、バッチが処理を完了できるようにします。

### <a name="use-the-teams-powershell-module"></a>Teams PowerShell モジュールを使用する

以下を実行して、(まだインストールされていない場合は) [Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。 バージョン 1.0.5 以降をインストールしていることを確認します。

```powershell
Install-Module -Name MicrosoftTeams
```

以下を実行して Teams に接続しセッションを開始します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、管理者の資格情報を使用してサイン インします。

### <a name="assign-policy-packages-to-a-batch-of-users"></a>ユーザーのバッチにポリシー パッケージを割り当てる

この例では、[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、ユーザーのバッチに Education_PrimaryStudent ポリシー パッケージを割り当てます。

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>バッチ割り当ての状態を確認する

以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの `New-CsBatchPolicyAssignmentOperation` コマンドレットによって返される操作 ID です。

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、`UserState` プロパティにあるエラーに関する詳細情報を取得します。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

詳細については、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。

## <a name="related-topics"></a>関連トピック

- [ポリシーを使用してTeamsを管理する](manage-teams-with-policies.md)
- [Microsoft Teamsでポリシー パッケージを管理する](manage-policy-packages.md)
- [Teams PowerShell の概要](teams-powershell-overview.md)
- [Teamsでポリシーを割り当てる - 作業の開始](policy-assignment-overview.md)
