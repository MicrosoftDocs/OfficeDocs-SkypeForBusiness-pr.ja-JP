---
title: Teams でポリシーを割り当てる
author: mkbond007
ms.author: mabond
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
description: Microsoft Teamsのユーザーとグループにポリシーとポリシー パッケージを割り当てるさまざまな方法について説明します。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 3dec8bf23167c5166302942140fcfe49e9ea3720
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156515"
---
# <a name="assign-policies-in-teams--getting-started"></a>Teams でポリシーを割り当てる – 作業の開始

管理者は、ポリシーを使用して、組織のユーザーが利用できる Teams 機能を制御できます。 たとえば、ほんの一例を挙げると、通話ポリシー、会議ポリシー、メッセージ ポリシーなどがあります。

組織には、固有のニーズを持つさまざまな種類のユーザーがいます。 作成して割り当てるカスタム ポリシーを使用すると、それらのニーズに基づいてさまざまなユーザー セットにポリシー設定を調整できます。

組織内のポリシーを簡単に管理するために、Teams では、ユーザーにポリシーを割り当てる方法がいくつか用意されています。 バッチ割り当てによって、またはユーザーがメンバーであるグループに、ポリシーをユーザーに直接割り当てます。個別に、または大規模に割り当てます。 ポリシー パッケージを使用して、ポリシーの既定のコレクションを、同様の役割を持つ組織内のユーザーに割り当てることもできます。 選択するオプションは、管理しているポリシーの数と、ポリシーを割り当てるユーザーの数によって異なります。 グローバル (組織全体の既定) ポリシーは、組織内で最も多くのユーザーに適用されます。 特別なポリシーを必要とするユーザーにのみポリシーを割り当てる必要があります。

この記事では、ユーザーにポリシーを割り当てるさまざまな方法と、何をいつ使用するかについての推奨シナリオについて説明します。

**ユーザーとグループにポリシーを割り当てる** 方法の詳細については、「ユーザーとグループ [へのポリシーの割り当て」を](assign-policies-users-and-groups.md)参照してください。 **ポリシー パッケージを割り当てる** 方法の詳細については、「ポリシー パッケージの [割り当て](assign-policy-packages.md)」を参照してください。

## <a name="which-policy-takes-precedence"></a>どのポリシーが優先されますか?

ユーザーには、ポリシーの種類ごとに 1 つの有効なポリシーがあります。 ユーザーにポリシーが直接割り当てられ、同じ種類のポリシーが割り当てられている 1 つ以上のグループのメンバーである可能性があります。場合によっては、ユーザーにポリシーが直接割り当てられている可能性もあります。 このようなシナリオでは、どのポリシーが優先されますか? ユーザーの有効なポリシーは、次の優先規則に従って決定されます。

ユーザーに直接ポリシーが割り当てられている場合 （個別に、またはバッチ割り当てによって）、そのポリシーが優先されます。 次の視覚的な例では、ユーザーの有効なポリシーは、ユーザーに直接割り当てられるリンカーン 正方形会議ポリシーです。

![直接割り当てられたポリシーの優先順位を示す図。](media/assign-policies-example-directly-assigned.png)

ユーザーに特定の種類のポリシーが直接割り当てられていない場合は、そのユーザーがメンバーになっているグループに割り当てられているポリシーが優先されます。 ユーザーが複数のグループのメンバーである場合、特定のポリシーの種類に対して最も高い ([グループ割り当て順位付け](assign-policies-users-and-groups.md#group-assignment-ranking)) ポリシーが優先されます。

この視覚的な例では、ユーザーの有効なポリシーは Exec Teams と HD ポリシーで、ユーザーがメンバーであり、同じポリシーの種類のポリシーも割り当てられている他のグループに対する割り当て順位が最も高くなります。  

![グループから継承されたポリシーが優先される方法を示す図。](media/assign-policies-example-group.png)

ユーザーが直接ポリシーを割り当てられていない場合や、ポリシーが割り当てられているグループのメンバーではない場合、ユーザーはそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーを取得します。 視覚的な例を次に示します。

![グローバル ポリシーの優先順位を示す図。](media/assign-policies-example-global.png)

詳細については、「([優先順位規則](assign-policies-users-and-groups.md#precedence-rules))」を参照してください。

## <a name="ways-to-assign-policies"></a>ポリシーを割り当てる方法

これは、ユーザーにポリシーを割り当てる方法と、それぞれに推奨されるシナリオの概要です。 リンクを選択して詳細を確認します。

個々のユーザーまたはグループにポリシーを割り当てる前に、[グローバルな （組織全体の既定の） ポリシーを設定して](#set-the-global-policies)、それらが組織内の最大数のユーザーに適用されるようにします。  グローバル ポリシーが設定されたら、特別なポリシーを必要とするユーザーにのみポリシーを割り当てる必要があります。

|操作  |条件...  | 使用する技術...
|---------|---------|----|
|[ポリシーを個々のユーザーに割り当てる](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | Teams を初めて使用する場合、1 つまたはいくつかのポリシーを少数のユーザーに割り当てるだけで済みます。 |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット
|[ポリシーをグループに割り当てる](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |ユーザーのグループ メンバーシップに基づいてポリシーを割り当てます。 たとえば、セキュリティ グループまたは配布リスト内のすべてのユーザーにポリシーを割り当てます。| Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシーをユーザーのバッチに割り当てる](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | 大規模なユーザー セットにポリシーを割り当てます。 たとえば、一度に組織内の数百または数千人のユーザーにポリシーを割り当てます。 |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシー パッケージをユーザーに割り当てる](assign-policy-packages.md#assign-a-policy-package-to-users)  |同じまたは類似のロールを持つ組織内の特定のユーザー セットに複数のポリシーを割り当てます。 たとえば、教育機関 (教師) ポリシー パッケージを学校の教師に割り当てて、チャット、通話、会議にフル アクセスできるようにします。 教育機関 (中等生) ポリシー パッケージを中等生に割り当てて、プライベート通話などの特定の機能を制限します。  |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシー パッケージをグループに割り当てる](assign-policy-packages.md#assign-a-policy-package-to-a-group)  |同じまたは類似のロールを持つ組織内のユーザーのグループに複数のポリシーを割り当てます。 たとえば、セキュリティ グループまたは配布リスト内のすべてのユーザーにポリシー パッケージを割り当てます。 |Microsoft Teams 管理センター (近日公開予定) または Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシー パッケージをユーザーのバッチに割り当てる](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|同じまたは類似のロールを持つ組織内のユーザーのバッチに複数のポリシーを割り当てます。 たとえば、バッチ割り当てを使用して学校内のすべての教師に教育 (教師) ポリシー パッケージを割り当てて、チャット、通話、会議にフル アクセスできるようにします。 教育機関 (中等生) ポリシー パッケージを中等生のバッチに割り当てて、プライベート通話などの特定の機能を制限します。|Teams PowerShell モジュールの PowerShell コマンドレット|

> [!NOTE]
> ポリシーの割り当てを解除するには、ポリシーに直接割り当てられているすべてのユーザーの割り当てを一括で削除できます。 詳細については、「ポリシーの [割り当てを一括で割り当て解除する」](assign-policies-users-and-groups.md#unassign-policies-in-bulk)を参照してください。

## <a name="set-the-global-policies"></a>グローバル ポリシーを設定する

次の手順に従って、ポリシーの種類ごとにグローバルな (組織全体の既定の) ポリシーを設定します。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、更新するポリシー タイプのポリシー ページに移動します。 たとえば、**Teams** > **Teams ポリシー**、**会議** > **会議ポリシー**、**メッセージ ポリシー**、または **音声** > **通話ポリシー** です。
2. 現在の設定を表示するには、**グローバルな (組織全体の既定の)** ポリシーを選択します。
3. 必要に応じてポリシーを更新し、**[適用]** を選択します。

![Teams 管理センターでグローバル ポリシーを更新します。](media/assign-globalpolicy.png)

### <a name="using-powershell"></a>PowerShell の使用

PowerShell を使用してグローバル ポリシーを設定するには、グローバル識別子を使用します。  まず、現在のグローバル ポリシーを確認して、変更する設定を決定します。

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

次に、必要に応じてグローバル ポリシーを更新します。  変更する設定の値を指定するだけです。

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a>アクティビティ ログでポリシーの割り当てを表示する

Microsoft Teams管理センターのユーザーにポリシーを割り当てると、それらのポリシー割り当ての状態を [アクティビティ ログ](https://admin.teams.microsoft.com/activitylog)に表示できます。 アクティビティ ログには、ネットワーク レコードのアップロード情報、Teams 管理センターと PowerShell からのグループ ポリシー操作、および Teams 管理センターからの過去 30 日間のバッチ ポリシー操作 (20 人以上のユーザー) が表示されます。

![[アクティビティ ログ] ページのスクリーンショット。](media/Activity_Log.png)

アクティビティ ログでポリシー操作を表示するには:

1. Microsoft Teams管理センターの左側のナビゲーションで、[ **ダッシュボード**] に移動し、[ **アクティビティ ログ**] で [ **詳細の表示**] を選択します。
2. 各ポリシー操作に関する次の情報が表示されます。
    - **アクティビティ**: ポリシー操作の名前。 たとえば、 **グループ ポリシーの割り当て**
    - **グループ名**: ポリシー操作が完了したグループの名前。
    - **ポリシーの種類**: ポリシーの種類。
    - **ポリシー名**: ポリシー操作の名前。 バッチ ポリシーの割り当てでは、リンクを選択して詳細を表示できます。 これには、ポリシーが割り当てられたユーザーの数と、完了、進行中、未開始の割り当ての数が含まれます。 バッチ内のユーザーの一覧と、各ユーザーの状態と結果も表示されます。
    - **送信元**: ポリシー操作を送信したユーザーの名前。
    - **送信日**: ポリシー操作が送信された日時。
    - **完了日**: ポリシー操作が完了した日時。
    - **影響を受けた**: バッチまたはグループ内のユーザーの数。
    - **全体的な状態**: ポリシー操作の状態。 ポリシーには、次のいずれかの状態を設定できます。
        - **未開始**: ポリシー操作は管理者によって送信されました。
        - **進行中**: ポリシー操作が処理を開始しました。
        - **ユーザーへのロールアウト**: システムは、ポリシー更新プログラムをユーザーに適用し始めました。
        - **完了:** ポリシー更新プログラムはすべてのユーザーに適用されました。
        - **'x' エラーで完了:** ポリシー操作は完了しましたが、エラーがあります。

> [!NOTE]
> [ **ユーザー]** ページからアクティビティ ログにアクセスすることもできます。 [ **適用]** を選択して一括ポリシーの割り当てを送信すると、ページの上部にバナーが表示されます。 バナーで **[アクティビティ ログ** ] リンクを選択します。

## <a name="related-topics"></a>関連項目

- [ユーザーとグループにポリシーを割り当てる](assign-policies-users-and-groups.md)
- [ユーザーとグループにポリシー パッケージを割り当てる](assign-policy-packages.md)
- [ポリシーを使用して Teams を管理する](manage-teams-with-policies.md)
- [Teams PowerShell の概要](teams-powershell-overview.md)
