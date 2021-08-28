---
title: Teams でポリシーを割り当Teams
author: KarliStites
ms.author: kastites
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
description: グループ内のユーザーとグループにポリシーとポリシー パッケージを割り当てるさまざまな方法についてMicrosoft Teams。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: fb85ae05925a44db75ed63ada899c6fca92cbceb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621989"
---
# <a name="assign-policies-in-teams--getting-started"></a>ポリシーの割り当Teams - 使用を開始する

管理者は、ポリシーを使用して、組織のユーザーが利用できる Teams 機能を制御できます。 たとえば、ほんの一例を挙げると、通話ポリシー、会議ポリシー、メッセージ ポリシーなどがあります。

組織には、固有のニーズを持つユーザーの種類が異なります。 作成して割り当てるカスタム ポリシーを使用すると、それらのニーズに基づいてポリシー設定をさまざまなユーザー セットに合わせて調整できます。

組織のポリシーを簡単に管理するには、Teamsにポリシーを割り当てる方法がいくつか用意されています。 ポリシーをユーザーに直接割り当てる (個別に割り当てるか、バッチ割り当てによって大規模に割り当てるか、ユーザーがメンバーであるグループに割り当てる)。 ポリシー パッケージを使用して、ポリシーの既定のコレクションを、同様の役割を持つ組織内のユーザーに割り当てることもできます。 選択するオプションは、管理しているポリシーの数と、ポリシーを割り当てるユーザーの数によって異なります。 グローバル (組織全体の既定) ポリシーは、組織内の最大ユーザー数に適用されます。 ポリシーは、特殊なポリシーを必要とするユーザーにのみ割り当てる必要があります。

この記事では、ユーザーにポリシーを割り当てるさまざまな方法と、何をいつ使用するかについての推奨シナリオについて説明します。

ユーザーとグループにポリシーを **割り当** てる方法の詳細については、「ユーザーとグループにポリシーを割り当 [てる」を参照してください](assign-policies-users-and-groups.md)。 ポリシー パッケージを割り当てる方法の **詳細については、** ポリシー パッケージの割り当 [てに関するページを参照してください](assign-policy-packages.md)。

## <a name="which-policy-takes-precedence"></a>どのポリシーが優先されますか?

ユーザーには、ポリシーの種類ごとに 1 つの有効なポリシーがあります。 ユーザーにポリシーが直接割り当てられている可能性があります。また、同じ種類のポリシーが割り当てられている 1 つ以上のグループのメンバーである可能性があります。 このようなシナリオでは、どのポリシーが優先されますか? ユーザーの有効なポリシーは、次の優先規則に従って決定されます。

ユーザーに直接ポリシーが割り当てられている場合 （個別に、またはバッチ割り当てによって）、そのポリシーが優先されます。 次の視覚的な例では、ユーザーの有効なポリシーは、ユーザーに直接割り当てられる、Square 会議ポリシーです。

![直接割り当てられたポリシーの優先順位を示す図](media/assign-policies-example-directly-assigned.png)

ユーザーに特定の種類のポリシーが直接割り当てられていない場合は、そのユーザーがメンバーになっているグループに割り当てられているポリシーが優先されます。 ユーザーが複数のグループのメンバーである場合、特定のポリシーの種類に対して最も高い ([グループ](assign-policies-users-and-groups.md#group-assignment-ranking)割り当てランキング ) を持つポリシーが優先されます。

この視覚的な例では、ユーザーの有効なポリシーは Exec Teams ポリシーと HD ポリシーです。このポリシーは、ユーザーがメンバーであり、同じポリシーの種類のポリシーも割り当てられている他のグループに対して最も高い割り当て順位を持っています。  

![グループから継承されたポリシーの優先順位を示す図](media/assign-policies-example-group.png)

ユーザーが直接ポリシーを割り当てられていない場合や、ポリシーが割り当てられているグループのメンバーではない場合、ユーザーはそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーを取得します。 視覚的な例を次に示します。

![グローバル ポリシーの優先順位を示す図](media/assign-policies-example-global.png)

詳細については、 ( 優先順位規則 に[関するページを参照してください](assign-policies-users-and-groups.md#precedence-rules)。

## <a name="ways-to-assign-policies"></a>ポリシーを割り当てる方法

これは、ユーザーにポリシーを割り当てる方法と、それぞれに推奨されるシナリオの概要です。 詳細については、リンクを選択してください。

個々のユーザーまたはグループにポリシーを割り当てる前に、[グローバルな （組織全体の既定の） ポリシーを設定して](#set-the-global-policies)、それらが組織内の最大数のユーザーに適用されるようにします。  グローバル ポリシーが設定された後は、特殊なポリシーを必要とするユーザーにポリシーを割り当てる必要があります。

|操作  |条件...  | 使用する技術...
|---------|---------|----|
|[ポリシーを個々のユーザーに割り当てる](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | Teams を初めて使用する場合、1 つまたはいくつかのポリシーを少数のユーザーに割り当てるだけで済みます。 |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット
|[ポリシーをグループに割り当てる](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |ユーザーのグループ メンバーシップに基づいてポリシーを割り当てる。 たとえば、セキュリティ グループまたは配布リスト内のすべてのユーザーにポリシーを割り当てるとします。| Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシーをユーザーのバッチに割り当てる](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | 多数のユーザーにポリシーを割り当てる。 たとえば、組織内の数百または数千人のユーザーに一度にポリシーを割り当てるとします。 |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシー パッケージをユーザーに割り当てる](assign-policy-packages.md#assign-a-policy-package-to-users)  |同じロールまたは同様のロールを持つ組織内の特定のユーザー セットに複数のポリシーを割り当てます。 たとえば、学校の教師に教育 (教師) ポリシー パッケージを割り当て、チャット、通話、会議へのフル アクセス権を与えます。 Education (中学生) ポリシー パッケージをセカンダリ 学生に割り当て、プライベート通話などの特定の機能を制限します。  |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシー パッケージをグループに割り当てる](assign-policy-packages.md#assign-a-policy-package-to-a-group) (プライベート プレビュー)   |同じロールまたは同様のロールを持つ組織内のユーザーグループに複数のポリシーを割り当てます。 たとえば、セキュリティ グループまたは配布リスト内のすべてのユーザーにポリシー パッケージを割り当てるとします。 |Microsoft Teams 管理センター (近日公開予定) または Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシー パッケージをユーザーのバッチに割り当てる](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|同じロールまたは同様のロールを持つ組織内のユーザーのバッチに複数のポリシーを割り当てます。 たとえば、バッチ割り当てを使用して、学校内のすべての教師に教育 (教師) ポリシー パッケージを割り当て、チャット、通話、会議へのフル アクセス権を与えます。 Education (中学生) ポリシー パッケージをセカンダリ 学生のバッチに割り当て、プライベート通話などの特定の機能を制限します。|Teams PowerShell モジュールの PowerShell コマンドレット|

## <a name="set-the-global-policies"></a>グローバル ポリシーを設定する

次の手順に従って、ポリシーの種類ごとにグローバルな (組織全体の既定の) ポリシーを設定します。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、更新するポリシー タイプのポリシー ページに移動します。 たとえば、**Teams** > **Teams ポリシー**、**会議** > **会議ポリシー**、**メッセージ ポリシー**、または **音声** > **通話ポリシー** です。
2. 現在の設定を表示するには、**グローバルな (組織全体の既定の)** ポリシーを選択します。
3. 必要に応じてポリシーを更新し、**[適用]** を選択します。

![管理センターでグローバル ポリシー Teams更新する](media/assign-globalpolicy.png)

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

Microsoft Teams 管理センターでユーザーにポリシーを割り当てると、それらのポリシー割り当ての状態をアクティビティ ログに表示できます。 アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。 アクティビティ ログには、ポリシー パッケージの割り当て、Microsoft Teams 管理センターを通じて 20 人未満のユーザーのバッチに対するポリシーの割り当て、または PowerShell を使用したポリシーの割り当ては表示されます。

![[アクティビティ ログ] ページのスクリーンショット](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>アクティビティ ログでポリシー割り当てアクティビティを表示する

アクティビティ ログでポリシーの割り当てを表示するには:

1. 管理センターの左側のナビゲーションMicrosoft Teamsダッシュボード] に移動し、[アクティビティログ] で[詳細の表示]**を選択します**。
2. すべてのポリシー割り当てを表示したり、状態で一覧をフィルター処理して、[開始していない]、[進行中]、または [完了] の割り当てのみを **表示することができます**。 各課題に関する次の情報が表示されます。
    - **[** 名前]: ポリシー割り当ての名前。 リンクをクリックすると、詳細が表示されます。 これには、ポリシーが割り当てられたユーザーの数と、完了した割り当て、進行中、開始されていない割り当ての数が含まれます。 バッチ内のユーザーの一覧と、各ユーザーの状態と結果も表示されます。 以下は、実行例です。

        ![のスクリーンショット](media/activity-log-policy-assignment-detail.png)

    - **送信** 済み: ポリシーの割り当てが送信された日付と時刻。
    - **完了時刻**: ポリシーの割り当てが完了した日付と時刻。
    - **影響:** バッチ内のユーザーの数。
    - **全体の状態**: ポリシー割り当ての状態。

> [!NOTE]
> [ユーザー] ページからアクティビティ ログに **アクセス** することもできます。 [適用] **をクリック** して一括ポリシーの割り当てを送信すると、ページの上部にバナーが表示されます。 バナーの **[アクティビティ ログ** ] リンクをクリックします。

## <a name="related-topics"></a>関連トピック

- [ユーザーとグループにポリシーを割り当てる](assign-policies-users-and-groups.md)
- [ユーザーとグループにポリシー パッケージを割り当てる](assign-policy-packages.md)
- [ポリシー Teamsを管理する](manage-teams-with-policies.md)
- [Teams PowerShell の概要](teams-powershell-overview.md)