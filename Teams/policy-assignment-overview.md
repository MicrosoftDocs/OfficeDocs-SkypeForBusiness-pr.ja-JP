---
title: Teams でポリシーを割り当てる
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
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams のユーザーとグループにポリシーとポリシー パッケージを割り当てるさまざまな方法について説明します。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 00f78b3b134c6741a89c0d7b3f43d32a11c182cc
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574356"
---
# <a name="assign-policies-in-teams--getting-started"></a>Teams でポリシーを割り当てる - 使用を開始する

管理者は、ポリシーを使用して、組織のユーザーが利用できる Teams 機能を制御できます。 たとえば、ほんの一例を挙げると、通話ポリシー、会議ポリシー、メッセージ ポリシーなどがあります。

組織には、固有のニーズを持つユーザーの種類が異なります。 作成して割り当てるカスタム ポリシーを使用すると、それらのニーズに基づいて、さまざまなユーザー セットにポリシー設定をカスタマイズできます。

組織内のポリシーを簡単に管理するために、Teams にはユーザーにポリシーを割り当てる方法がいくつか用意されています。 ポリシーをユーザーに直接割り当てる(個別に割り当てるか、バッチ割り当てを通じてスケールで割り当てるか、ユーザーがメンバーであるグループに割り当てる)。 ポリシー パッケージを使用して、ポリシーの既定のコレクションを、同様の役割を持つ組織内のユーザーに割り当てることもできます。 選択するオプションは、管理するポリシーの数と、ポリシーを割り当てるユーザーの数によって異なります。 グローバル (組織全体の既定) ポリシーは、組織内のユーザーの数が最も多い場合に適用されます。 ポリシーを割り当てる必要があるのは、特殊なポリシーが必要なユーザーのみです。

この記事では、ユーザーにポリシーを割り当てるさまざまな方法と、何をいつ使用するかについての推奨シナリオについて説明します。

ユーザーとグループにポリシーを **割り当てる** 方法の詳細については、「ユーザーとグループにポリシーを割り当 [てる」を参照してください](assign-policies-users-and-groups.md)。 ポリシー パッケージを割り当てる方法の **詳細については、「** ポリシー パッケージを割り当 [てる」を参照してください](assign-policy-packages.md)。

## <a name="which-policy-takes-precedence"></a>どのポリシーが優先されますか?

ユーザーには、ポリシーの種類ごとに 1 つの有効なポリシーがあります。 ユーザーに直接ポリシーが割り当て済みで、同じ種類のポリシーが割り当てられている 1 つ以上のグループのメンバーである可能性があります。 このようなシナリオでは、どのポリシーが優先されますか? ユーザーの有効なポリシーは、次の優先規則に従って決定されます。

ユーザーに直接ポリシーが割り当てられている場合 （個別に、またはバッチ割り当てによって）、そのポリシーが優先されます。 次の視覚的な例では、ユーザーの効果的なポリシーは、ユーザーに直接割り当てられる、Square 会議ポリシーです。

![直接割り当てられたポリシーの優先順位を示す図](media/assign-policies-example-directly-assigned.png)

ユーザーに特定の種類のポリシーが直接割り当てられていない場合は、そのユーザーがメンバーになっているグループに割り当てられているポリシーが優先されます。 ユーザーが複数のグループのメンバーである場合、指定されたポリシーの種類の中で最も[高い](assign-policies-users-and-groups.md#group-assignment-ranking)(グループ割り当てランキング) を持つポリシーが優先されます。

この視覚的な例では、ユーザーの効果的なポリシーは Exec Teams と HD ポリシーです。このポリシーは、ユーザーがメンバーであり、同じポリシーの種類のポリシーも割り当てられている他のグループに対して、最も高い割り当てランクを持っています。  

![グループから継承されたポリシーの優先順位を示す図](media/assign-policies-example-group.png)

ユーザーが直接ポリシーを割り当てられていない場合や、ポリシーが割り当てられているグループのメンバーではない場合、ユーザーはそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーを取得します。 次に、視覚的な例を示します。

![グローバル ポリシーの優先順位を示す図](media/assign-policies-example-global.png)

詳細については、「(優先順位ルール)」[を参照してください](assign-policies-users-and-groups.md#precedence-rules)。

## <a name="ways-to-assign-policies"></a>ポリシーを割り当てる方法

これは、ユーザーにポリシーを割り当てる方法と、それぞれに推奨されるシナリオの概要です。 詳細については、リンクを選択してください。

個々のユーザーまたはグループにポリシーを割り当てる前に、[グローバルな （組織全体の既定の） ポリシーを設定して](#set-the-global-policies)、それらが組織内の最大数のユーザーに適用されるようにします。  グローバル ポリシーを設定したら、特別なポリシーを必要とするユーザーにのみポリシーを割り当てる必要があります。

|操作  |条件...  | 使用する技術...
|---------|---------|----|
|[ポリシーを個々のユーザーに割り当てる](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | Teams を初めて使用する場合、1 つまたはいくつかのポリシーを少数のユーザーに割り当てるだけで済みます。 |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット
|[ポリシーをグループに割り当てる](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |ユーザーのグループ メンバーシップに基づいてポリシーを割り当てる。 たとえば、セキュリティ グループまたは配布リスト内のすべてのユーザーにポリシーを割り当てるとします。| Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシーをユーザーのバッチに割り当てる](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | 多数のユーザーにポリシーを割り当てる。 たとえば、一度に数百または数千人のユーザーにポリシーを割り当てるとします。 |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシー パッケージをユーザーに割り当てる](assign-policy-packages.md#assign-a-policy-package-to-users)  |同じ役割または同様の役割を持つ組織内の特定のユーザー セットに複数のポリシーを割り当てます。 たとえば、学校の教師に教育 (教師) ポリシー パッケージを割り当て、チャット、通話、会議へのフル アクセス権を与えます。 Education (中等学生) ポリシー パッケージを中学生に割り当て、プライベート通話などの特定の機能を制限します。  |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシー パッケージをグループに割り当てる](assign-policy-packages.md#assign-a-policy-package-to-a-group) (プライベート プレビュー)   |同じ役割または同様の役割を持つ組織内のユーザーのグループに複数のポリシーを割り当てます。 たとえば、セキュリティ グループまたは配布リスト内のすべてのユーザーにポリシー パッケージを割り当てるとします。 |Microsoft Teams 管理センター (近日公開予定) または Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシー パッケージをユーザーのバッチに割り当てる](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|同じ役割または同様の役割を持つ組織内のユーザーのバッチに複数のポリシーを割り当てます。 たとえば、バッチ割り当てを使用して、学校内のすべての教師に教育 (教師) ポリシー パッケージを割り当て、チャット、通話、会議へのフル アクセス権を与えます。 プライベート通話などの特定の機能を制限するために、Education (中等学生) ポリシー パッケージをセカンダリ 学生のバッチに割り当てる。|Teams PowerShell モジュールの PowerShell コマンドレット|

## <a name="set-the-global-policies"></a>グローバル ポリシーを設定する

次の手順に従って、ポリシーの種類ごとにグローバルな (組織全体の既定の) ポリシーを設定します。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、更新するポリシー タイプのポリシー ページに移動します。 たとえば、**Teams** > **Teams ポリシー**、**会議** > **会議ポリシー**、**メッセージ ポリシー**、または **音声** > **通話ポリシー** です。
2. 現在の設定を表示するには、**グローバルな (組織全体の既定の)** ポリシーを選択します。
3. 必要に応じてポリシーを更新し、**[適用]** を選択します。

![Teams 管理センターでグローバル ポリシーを更新する](media/assign-globalpolicy.png)

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

## <a name="view-your-policy-assignments-in-the-activity-log"></a>アクティビティ ログでポリシー割り当てを表示する

Microsoft Teams 管理センターでユーザーにポリシーを割り当てると、アクティビティ ログでそれらのポリシー割り当ての状態を表示できます。 アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。 アクティビティ ログには、ポリシー パッケージの割り当て、Microsoft Teams 管理センターを通じて 20 人未満のユーザーのバッチへのポリシー割り当て、または PowerShell によるポリシー割り当ては表示されます。

![[アクティビティ ログ] ページのスクリーンショット](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>アクティビティ ログでポリシー割り当てアクティビティを表示する

アクティビティ ログにポリシー割り当てを表示するには、次の方法を実行します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ダッシュボード] に移動し、[アクティビティ ログ] の [詳細の表示] を **選択します**。
2. すべてのポリシー割り当てを表示したり、状態でリストをフィルター処理して、[開始していない]、[進行中]、または [完了] の割り当てのみを **表示することができます**。  各課題に関する次の情報が表示されます。
    - **名前**: ポリシー割り当ての名前。 詳細を表示するには、リンクをクリックします。 これには、ポリシーが割り当てられたユーザーの数、完了した割り当て、進行中、開始されていない割り当ての数が含まれます。 バッチ内のユーザーの一覧と、各ユーザーの状態と結果も表示されます。 以下は、実行例です。

        ![[](media/activity-log-policy-assignment-detail.png)

    - **送信** 日時: ポリシー割り当てが送信された日付と時刻。
    - **完了時刻**: ポリシー割り当てが完了した日付と時刻。
    - **影響:** バッチ内のユーザー数。
    - **全体の状態**: ポリシー割り当ての状態。

> [!NOTE]
> [ユーザー] ページからアクティビティ ログに **アクセス** することもできます。 [適用] **をクリック** して一括ポリシーの割り当てを送信すると、ページの上部にバナーが表示されます。 バナーの **[アクティビティ ログ** ] リンクをクリックします。

## <a name="related-topics"></a>関連項目

- [ユーザーとグループにポリシーを割り当てる](assign-policies-users-and-groups.md)
- [ユーザーとグループにポリシー パッケージを割り当てる](assign-policy-packages.md)
- [ポリシーを使用して Teams を管理する](manage-teams-with-policies.md)
- [Teams PowerShell の概要](teams-powershell-overview.md)