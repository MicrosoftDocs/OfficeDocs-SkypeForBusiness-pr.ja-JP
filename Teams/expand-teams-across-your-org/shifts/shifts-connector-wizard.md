---
title: Shifts コネクタ ウィザードを使用して Shifts を Blue Yonder Workforce Management に接続する
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Shifts コネクタ ウィザードを使用して、Teamsの Shifts と Blue Yonder Workforce Management を統合する方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593665"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Shifts コネクタ ウィザードを使用して Shifts を Blue Yonder Workforce Management に接続する

## <a name="overview"></a>概要

Microsoft 365 管理センターの Shifts コネクタ ウィザードを使用すると、Microsoft Teamsの Shifts アプリを従業員管理 (WFM) システムと統合できます。 接続を設定すると、フロントライン ワーカーは Shifts 内から WFM システムでスケジュールをシームレスに表示および管理できます。

ウィザードによって Shifts コネクタが構成され、WFM システムへの接続が作成され、選択した同期設定とチーム マッピングが適用されます。 同期設定は、WFM システムと Shifts の間で同期されるスケジュール情報を決定します。 チーム マッピングは、WFM サイトとTeamsのチーム間の同期関係を定義します。 既存のチームと新しいチームにマップできます。

複数の接続を設定できます。それぞれ異なる同期設定を使用します。 たとえば、組織に異なるスケジュール要件を持つ複数の場所がある場合は、場所ごとに一意の同期設定を持つ接続を作成します。 WFM サイトは、特定の時点で 1 つのチームにのみマップできることに注意してください。 WFM サイトが既にチームにマップされている場合、別のチームにマップすることはできません。

WFM システムをレコードのシステムとして使用すると、フロントライン ワーカーは、シフトの表示と交換、可用性の管理、デバイスの Shifts での休暇の要求を行うことができます。 フロントライン マネージャーは引き続き WFM システムを使用してスケジュールを設定できます。

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>シフトを Blue Yonder Workforce Management と統合する

現在、ウィザードは [Blue Yonder の Microsoft Teams Shifts コネクタを](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)サポートしています。 このコネクタを使用すると、Shifts と Blue Yonder Workforce Management (Blue Yonder WFM) を統合してスケジュールを管理し、それらを最新の状態に保つことができます。 この記事では、ウィザードを実行してコネクタを介して Blue Yonder WFM への接続を設定する方法について説明します。

> [!NOTE]
> PowerShell を使用して、Shifts と Blue Yonder WFM を統合することもできます。 詳細については、「 [PowerShell を使用して Shifts を Blue Yonder Workforce Management に接続する」を](shifts-connector-blue-yonder-powershell-setup.md)参照してください。

## <a name="before-you-begin"></a>はじめに

ウィザードを実行するには、Microsoft 365グローバル管理者である必要があります。

### <a name="prerequisites"></a>前提条件
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- マップするチームにはスケジュールがありません。 チームに既存のスケジュールがある場合は、Blue Yonder WFM サイトをチームにマップする前に [、チームからスケジュールを削除](#remove-schedules-from-teams-you-want-to-map) します。 それ以外の場合は、重複するシフトが表示されます。

## <a name="remove-schedules-from-teams-you-want-to-map"></a>マップするチームからスケジュールを削除する
<a name="remove_schedules"> </a>

> [!NOTE]
> Blue Yonder WFM サイトをスケジュールがある既存のチームにマッピングする場合は、この手順を完了します。 スケジュールがないチームにマッピングする場合、またはマップ先の新しいチームを作成する場合は、この手順をスキップできます。

PowerShell を使用して、チームからスケジュールを削除します。

1. まず、PowerShell モジュールをインストールし、セットアップする必要があります。 手順に従って [環境を設定します](shifts-connector-powershell-manage.md#set-up-your-environment)。
1. 次のコマンドを実行します。

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    パラメーターのシナリオ `EntityType` の一覧を取得するには、 [Get-CsTeamsShiftsConnectionConnectionConnector を](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)実行します。 指定した日付と時刻の範囲のスケジュール データが削除されます。

詳細については、「 [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)」を参照してください。

## <a name="run-the-wizard"></a>ウィザードを実行する

### <a name="get-started"></a>はじめに

1. [Microsoft 365 管理センター](https://admin.microsoft.com/)の左側のナビゲーションで、[**セットアップ**] を選択し、[**アプリと電子メール**] セクションに移動します。
1. **従業員管理システムConnect選択します**。 ここでは、Shifts コネクタと、Shifts を WFM システムに接続するときの現場のワーカーとマネージャーのエクスペリエンスについて詳しく説明します。
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Microsoft 365 管理センターの Shifts コネクタ ウィザードの詳細ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. 準備ができたら、**概要** を選択します。
1. **[次へ**] を選択して Blue Yonder WFM 接続を作成します。

### <a name="enter-connection-details"></a>接続の詳細を入力する
<a name="connection_details"> </a>

1. [接続の詳細] ページで、接続に一意の名前を付けます。 128 文字を超えたり、特殊文字を含めたりすることはできません。
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="接続設定を示すウィザードの [接続の詳細] ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Blue Yonder WFM サービス アカウント名とパスワードとサービス URL を入力します。
1. 完了したら、[ **次へ** ] を選択して、入力した設定で接続をテストします。

### <a name="choose-sync-settings"></a>同期設定を選択する
<a name="sync"> </a>

[同期設定] ページで、Blue Yonder WFM から Shifts に同期する情報、同期頻度、および Shifts ユーザーがデータに変更を加えることができるかどうかを選択します。

1. Microsoft 365システム アカウントを入力します。
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="同期設定を示すウィザードの [同期設定] ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. [ **電子メール通知の受信者**] で、この接続に関する電子メール通知を受け取るユーザーを選択します。 個々のユーザーとグループを追加できます。 電子メール通知には、接続のセットアップ状態と、接続のセットアップ後に発生する可能性がある問題やエラーに関する情報が含まれています。
1. 同期設定を選択します。
    1. [ **スケジュールとシフト**] で、Shifts ユーザーが表示または変更できる Blue Yonder WFM データを選択し、同期頻度を設定します。
    2. [ **要求]** で、Shifts ユーザーが表示および作成できる要求の種類を選択します。

    > [!IMPORTANT]
    > オープン シフト、オープン シフト要求、スワップ要求、または休暇要求を無効にする次のいずれかのオプションを選択した場合は、Shifts で機能を非表示にするには、別の手順を実行する必要があります。
    >
    > - オープン シフト: **Shifts ユーザーに Blue Yonder WFM データが表示されない**
    > - スワップ要求: **すべてのユーザーに対して機能が無効になっている**
    > - 休暇要求: **すべてのユーザーに対して機能が無効になっている**
    >
    > ウィザードを実行した後は、この記事の後半の「 [オープン シフトを無効にする、シフト要求を開く、要求をスワップする、および休暇要求を無効にする](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) 」セクションの手順に従っていることを確認します。
 
1. 設定の選択が完了したら、[ **接続の作成**] を選択します。

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>Blue Yonder Workforce Management サイトをチームにマップする
<a name="sites"> </a>

Shifts に接続する Blue Yonder WFM サイトを選択します。 最大 100 個のサイトを選択できます。

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Blue Yonder WFM サイトの一覧を示すウィザードのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a>次に、選択した各 Blue Yonder WFM サイトをTeamsのチームにマップします。 サイトを既存のチームにマップすることも、新しいチームを作成することもできます。
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="検索チーム オプションと新しいチーム オプションの作成を示すウィンドウのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>サイトを既存のチームにマップするには

1. サイト名を選択します。
2. ウィンドウでチームを検索し、それを選択します。 この接続内のサイトに既にマップされているチームは、検索に表示されないことに注意してください。
3. タイム ゾーンと最も近い都市を選択します。
4. **[保存] を** 選択し、[**次へ**] を選択します。

#### <a name="to-map-a-site-to-a-new-team"></a>サイトを新しいチームにマップするには

1. サイト名を選択します。
2. ウィンドウで、[ **新しいチームの作成**] を選択します。 ブラウザーの新しいタブに移動し、Microsoft 365 管理センターで新しいチームを作成できます。
    1. チームの名前とオプションの説明を入力します。
    1. 1 つ以上のチーム所有者を追加します。 Microsoft 365システム アカウントを所有者として追加してください。
    1. チーム メンバーを追加します。
    1. チームのメール アドレスを追加し、プライバシー設定を選択します。
    1. 設定を確認し、[チームの **追加]** を選択します。 チームが作成されたら、[ **閉じる**] を選択します。
3. ウィザードに戻るし、作成した新しいチームを検索して選択します。
4. タイム ゾーンと最も近い都市を選択します。
5. **[保存] を** 選択し、[**次へ**] を選択します。

### <a name="review-and-finish"></a>確認と完了

設定を確認します。 チーム マッピングに変更を加える必要がある場合は、[ **編集]** を選択して変更します。 準備ができたら、[完了] を選択 **します**。

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="マッピングを示すウィザードの [確認] ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-review.png":::

要求を受信したことを確認するメッセージと操作 ID が表示されます。 操作 ID をメモしておきます。 接続のセットアップ状態を確認する必要があります。

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="確認メッセージと操作 ID を示すウィザード ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-operation-id.png":::

ウィザードによって、接続を設定し、選択したチームにサイトをマップするプロセスが開始されます。 このプロセスの完了には時間がかかる場合があります。 選択した受信者には、セットアップの状態に関する電子メール通知が送信されます。

**[完了] を** 選択してウィザードを終了します。

あなたは途中ですが、まだ完了していません。 メールを必ず確認してください。 要求を受け取ったという確認と、セットアップの状態を確認する方法への [リンク](shifts-connector-powershell-manage.md#check-connection-setup-status) が表示されます。

> [!NOTE]
> セットアップ後に接続で問題またはエラーが発生した場合は、電子メールで通知を受け取ります。 電子メールの指示に従って、問題のトラブルシューティングを行います。

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>オープン シフト、オープン シフト要求、スワップ要求、および休暇要求を無効にする

> [!IMPORTANT]
> 次のいずれかのオプションを選択して、開いているシフト、シフト要求を開く、要求をスワップする、またはウィザードで休暇要求を無効にする場合にのみ、次の手順に従います。 この手順を完了すると、Shifts で機能が非表示になります。
>
> - オープン シフト: **Shifts ユーザーに Blue Yonder WFM データが表示されない**
> - スワップ要求: **すべてのユーザーに対して機能が無効になっている**
> - 休暇要求: **すべてのユーザーに対して機能が無効になっている**
>
> この 2 番目の手順を実行しないと、Shifts で機能が表示され、使用しようとすると"サポートされていない操作" というエラー メッセージが表示されます。

Shifts でオープン シフト、スワップ要求、および休暇要求を非表示にするには、リソース[の種類をスケジュール](/graph/api/resources/schedule?view=graph-rest-1.0)Graph API使用して、Blue Yonder WFM サイトにマップした各チームに対して```false```次のパラメーターを設定します。

- 開いているシフト: ```openShiftsEnabled```
- スワップ要求:  ```swapShiftsRequestsEnabled```
- 休暇要求: ```timeOffRequestsEnabled```

Shifts で開いているシフト要求を非表示にするには、Shifts **の [設定**] に移動し、[**シフトを開く**] 設定をオフにします。

## <a name="if-you-need-to-make-changes-to-a-connection"></a>接続に変更を加える必要がある場合
<a name="update_connection"> </a>

接続が設定されたら、PowerShell を使用して変更を加えます。 たとえば、同期設定、チーム マッピングを更新し、接続の同期を無効にすることができます。 詳細なガイダンスについては、「 [PowerShell を使用して Blue Yonder Workforce Management への Shifts 接続を管理する」を参照してください](shifts-connector-powershell-manage.md)。

## <a name="related-articles"></a>関連記事

- [コネクタをシフトする](shifts-connectors.md)
- [PowerShell を使用して、Blue Yonder Workforce Management への Shifts 接続を管理する](shifts-connector-powershell-manage.md)
- [Teams でシフト アプリを使用する](manage-the-shifts-app-for-your-organization-in-teams.md)
