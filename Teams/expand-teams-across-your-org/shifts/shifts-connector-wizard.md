---
title: Shifts コネクタ ウィザードを使用して Shifts を Blue Yonder Workforce Managementに接続する
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Shifts コネクタ ウィザードを使用して Teams の Shifts と Blue Yonder Workforce Managementを統合する方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: de511df118e1c5e6d62e0bed8cd076a7481b3407
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647810"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Shifts コネクタ ウィザードを使用して Shifts を Blue Yonder Workforce Managementに接続する

## <a name="overview"></a>概要

Microsoft 365 管理センターの Shifts コネクタ ウィザードを使用すると、Microsoft Teams の Shifts アプリを従業員管理 (WFM) システムと統合できます。 接続を設定すると、フロントライン ワーカーは、Shifts 内からWFM システムでスケジュールをシームレスに表示および管理できます。

ウィザードによって Shifts コネクタが構成され、WFM システムへの接続が作成され、選択した同期設定とチーム マッピングが適用されます。 同期設定は、WFM システムと Shifts の間で同期されるスケジュール情報を決定します。 チーム マッピングは、WFM インスタンスと Teams 内のチーム間の同期関係を定義します。 既存のチームと新しいチームにマップできます。

複数の接続を設定できます。それぞれ異なる同期設定を使用します。 たとえば、組織に異なるスケジュール要件を持つ複数の場所がある場合は、場所ごとに一意の同期設定を持つ接続を作成します。 WFM インスタンスは、特定の時点で 1 つのチームにのみマップできることに注意してください。 WFM インスタンスが既にチームにマップされている場合、別のチームにマップすることはできません。

WFM システムをレコードのシステムとして使用すると、フロントライン ワーカーはシフトの表示とスワップ、可用性の管理、デバイスの Shifts での休暇の要求を行うことができます。 フロントライン マネージャーは、引き続きWFM システムを使用してスケジュールを設定できます。

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Shifts と Blue Yonder Workforce Managementを統合する

現在、ウィザードは [Blue Yonder 用の Microsoft Teams Shifts コネクタを](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)サポートしています。 このコネクタを使用すると、Shifts と Blue Yonder Workforce Management (Blue Yonder WFM) を統合してスケジュールを管理し、最新の状態に保つことができます。 この記事では、ウィザードを実行してコネクタ経由で Blue Yonder WFMへの接続を設定する方法について説明します。

> [!NOTE]
> PowerShell を使用して、Shifts と Blue Yonder WFMを統合することもできます。 詳細については、「[PowerShell を使用して Shifts を Blue Yonder Workforce Managementに接続する](shifts-connector-blue-yonder-powershell-setup.md)」を参照してください。

## <a name="before-you-begin"></a>はじめに

ウィザードを実行するには、Microsoft 365 グローバル管理者である必要があります。

### <a name="prerequisites"></a>前提条件
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- マップするチームにはスケジュールがありません。 チームに既存のスケジュールがある場合は、Blue Yonder WFM インスタンスをチームにマップする前に[、チームからスケジュールを削除](#remove-schedules-from-teams-you-want-to-map)します。 それ以外の場合は、重複するシフトが表示されます。

## <a name="remove-schedules-from-teams-you-want-to-map"></a>マップするチームからスケジュールを削除する
<a name="remove_schedules"> </a>

> [!NOTE]
> Blue Yonder WFM インスタンスをスケジュールがある既存のチームにマッピングする場合は、この手順を完了します。 スケジュールがないチームにマッピングする場合、またはマップ先の新しいチームを作成する場合は、この手順をスキップできます。

PowerShell を使用して、チームからスケジュールを削除します。

1. まず、PowerShell モジュールをインストールし、セットアップする必要があります。 手順に従って [環境を設定します](shifts-connector-powershell-manage.md#set-up-your-environment)。
1. 次のコマンドを実行します。

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    パラメーターのシナリオ `EntityType` の一覧を取得するには、 [Get-CsTeamsShiftsConnectionConnectionConnector を](/powershell/module/teams/get-csteamsshiftsconnectionconnector)実行します。 指定した日付と時刻の範囲のスケジュール データが削除されます。

詳細については、「 [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)」を参照してください。

## <a name="run-the-wizard"></a>ウィザードを実行する

### <a name="get-started"></a>はじめに

1. [Microsoft 365 管理センター](https://admin.microsoft.com/)の左側のナビゲーションで、[**セットアップ**] を選択し、[**アプリと電子メール**] セクションに移動します。
1. [ **従業員管理システムの接続] を選択します**。 ここでは、Shifts コネクタと、Shifts をWFM システムに接続するときの現場のワーカーとマネージャーのエクスペリエンスについて詳しく説明します。
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Microsoft 365 管理センターの Shifts コネクタ ウィザードの詳細ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. 準備ができたら、[ **作業の開始**] を選択します。
1. **[次へ**] を選択して Blue Yonder WFM接続を作成します。

### <a name="enter-connection-details"></a>接続の詳細を入力する
<a name="connection_details"> </a>

1. [接続の詳細] ページで、接続に一意の名前を付けます。 128 文字を超えたり、特殊文字を含めたりすることはできません。
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="接続設定を示すウィザードの [接続の詳細] ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Blue Yonder WFMサービス アカウント名とパスワードとサービス URL を入力します。
1. 完了したら、[ **次へ** ] を選択して、入力した設定で接続をテストします。

### <a name="choose-sync-settings"></a>同期設定を選択する
<a name="sync"> </a>

[同期設定] ページで、Blue Yonder WFMから Shifts に同期する情報、同期頻度、および Shifts ユーザーがデータを変更できるかどうかを選択します。

1. Microsoft 365 システム アカウントを入力します。
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="同期設定を示すウィザードの [同期設定] ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. [ **電子メール通知の受信者**] で、この接続に関する電子メール通知を受け取るユーザーを選択します。 個々のユーザーとグループを追加できます。 電子メール通知には、接続のセットアップ状態と、接続のセットアップ後に発生する可能性がある問題やエラーに関する情報が含まれています。
1. 同期設定を選択します。
    1. **[スケジュールとシフト**] で、Shifts ユーザーが表示または変更できる Blue Yonder WFM データを選択し、同期頻度を設定します。
    2. [ **要求]** で、Shifts ユーザーが表示および作成できる要求の種類を選択します。

    > [!IMPORTANT]
    > オープン シフト、オープン シフト要求、スワップ要求、または休暇要求を無効にする次のいずれかのオプションを選択した場合は、Shifts で機能を非表示にするには、別の手順を実行する必要があります。
    >
    > - シフトを開く: **Shifts ユーザーに Blue Yonder WFMデータが表示されない**
    > - スワップ要求: **すべてのユーザーに対して機能が無効になっている**
    > - 休暇要求: **すべてのユーザーに対して機能が無効になっている**
    >
    > ウィザードを実行した後は、この記事の後半の「 [オープン シフトを無効にする、シフト要求を開く、要求をスワップする、および休暇要求を無効にする](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) 」セクションの手順に従っていることを確認します。
 
1. 設定の選択が完了したら、[ **接続の作成**] を選択します。

### <a name="map-blue-yonder-workforce-management-instances-to-teams"></a>Blue Yonder Workforce Management インスタンスをチームにマップする
<a name="sites"> </a>

Shifts に接続する Blue Yonder WFM インスタンスを選択し、Teams のチームに各インスタンスをマップします。 最大 100 個のインスタンスをマップできます。 これを行うには、次の 2 つの方法があります。

- [インスタンスをチームに手動でマップする](#manually-map-instances-to-teams)
- [マッピングを定義する CSV ファイルを準備してアップロードする](#use-a-csv-file-to-map-instances-to-teams)

#### <a name="manually-map-instances-to-teams"></a>インスタンスをチームに手動でマップする

マップするインスタンスを選択します。

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Blue Yonder WFM インスタンスの一覧を示すウィザードのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> 次に、各インスタンスを Teams のチームにマップします。 インスタンスを既存のチームにマップすることも、新しいチームを作成することもできます。
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="検索チーム オプションと新しいチーム オプションの作成を示すウィンドウのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-search-team.png":::

##### <a name="to-map-an-instance-to-an-existing-team"></a>インスタンスを既存のチームにマップするには

1. インスタンス名を選択します。
2. ウィンドウでチームを検索し、それを選択します。 この接続内のインスタンスに既にマップされているチームは、検索に表示されないことに注意してください。
3. タイム ゾーンと最も近い都市を選択します。
4. **[保存] を** 選択し、[**次へ**] を選択します。

##### <a name="to-map-an-instance-to-a-new-team"></a>インスタンスを新しいチームにマップするには

1. インスタンス名を選択します。
2. ウィンドウで、[ **新しいチームの作成**] を選択します。 ブラウザーの新しいタブに移動し、Microsoft 365 管理センターで新しいチームを作成できます。
    1. チームの名前とオプションの説明を入力します。
    1. 1 つ以上のチーム所有者を追加します。 Microsoft 365 システム アカウントを所有者として追加してください。
    1. チーム メンバーを追加します。
    1. チームのメール アドレスを追加し、プライバシー設定を選択します。
    1. 設定を確認し、[チームの **追加]** を選択します。 チームが作成されたら、[ **閉じる**] を選択します。
3. ウィザードに戻るし、作成した新しいチームを検索して選択します。
4. タイム ゾーンと最も近い都市を選択します。
5. **[保存] を** 選択し、[**次へ**] を選択します。

#### <a name="use-a-csv-file-to-map-instances-to-teams"></a>CSV ファイルを使用してインスタンスをチームにマップする

1. **[一括モードに切り替える] を選択します**。
1. **テンプレート ファイルをダウンロード** して、マッピングの定義に使用できるマッピング テンプレートをダウンロードします。

    :::image type="content" source="../../media/shifts-connector-wizard-mapping-file.png" alt-text="ウィザードの [マッピング ファイルのアップロード] ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-mapping-file.png":::

1. テンプレートを使用してマッピング ファイルを作成します。 最初の列から始まる次の順序で、これらの列が含まれます。 アスタリスク (*) は、必要な列を示します。

    |列名  |説明  |
    |---------|---------|
    |**Blue Yonder インスタンス ID*** |Blue Yonder WFMインスタンス ID。|
    |**Blue Yonder インスタンス名**|Blue Yonder WFMインスタンス名。|
    |**チーム ID*** |チーム ID。|
    |**チーム名**|チーム名。|
    |**タイム ゾーン*** |tz データベース形式のタイム ゾーン。 たとえば、ヨーロッパ/ロンドンなどです。|

    > [!NOTE]
    > 必要な列 (Blue Yonder インスタンス ID、チーム ID、タイム ゾーン) に入力するだけで、インスタンスをチームにマップできます。

    マッピング ファイルの例を次に示します。

    |Blue Yonder インスタンス ID|Blue Yonder インスタンス名|チーム ID|チーム名|タイム ゾーン|
    |---------|---------|---------|---------|---------|
    |2111|Contoso 米国チーム|3a4d78a-2261|米国チーム|アメリカ/Los_Angeles|
    |3212|Contoso UK チーム|2d1f6c2e-5272|UK チーム|ヨーロッパ/ロンドン|
    |4865||bfa6o89e-1328||アメリカ/トロント|

1. マッピング ファイルを作成したら、[ **参照** ] を選択してアップロードします。 ウィザードによってファイルが検証されます。 エラーが見つかると、エラーの一覧と、エラーの修正を要求するメッセージが表示されます。 それ以外の場合は、次の手順に進むメッセージが表示されます。  
1. [**次へ**] を選択します。

### <a name="review-and-finish"></a>確認と完了

設定を確認します。 チーム マッピングに変更を加える必要がある場合は、[ **編集]** を選択して変更します。 準備ができたら、[完了] を選択 **します**。

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="マッピングを示すウィザードの [確認] ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-review.png":::

要求を受信したことを確認するメッセージと操作 ID が表示されます。 操作 ID をメモしておきます。 接続のセットアップ状態を確認する必要があります。

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="確認メッセージと操作 ID を示すウィザード ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-operation-id.png":::

ウィザードによってプロセスが開始され、接続が設定され、選択したチームにインスタンスがマップされます。 このプロセスの完了には時間がかかる場合があります。 選択した受信者には、セットアップの状態に関する電子メール通知が送信されます。

**[完了] を** 選択してウィザードを終了します。

あなたは途中ですが、まだ完了していません。 メールを必ず確認してください。 要求を受け取ったという確認と、セットアップの状態を確認する方法への [リンク](shifts-connector-powershell-manage.md#check-connection-setup-status) が表示されます。

> [!NOTE]
> セットアップ後に接続で問題またはエラーが発生した場合は、電子メールで通知を受け取ります。 電子メールの指示に従って、問題のトラブルシューティングを行います。

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>オープン シフト、オープン シフト要求、スワップ要求、および休暇要求を無効にする

> [!IMPORTANT]
> 次のいずれかのオプションを選択して、開いているシフト、シフト要求を開く、要求をスワップする、またはウィザードで休暇要求を無効にする場合にのみ、次の手順に従います。 この手順を完了すると、Shifts で機能が非表示になります。
>
> - シフトを開く: **Shifts ユーザーに Blue Yonder WFMデータが表示されない**
> - スワップ要求: **すべてのユーザーに対して機能が無効になっている**
> - 休暇要求: **すべてのユーザーに対して機能が無効になっている**
>
> この 2 番目の手順を実行しないと、Shifts で機能が表示され、使用しようとすると"サポートされていない操作" というエラー メッセージが表示されます。

Shifts でオープン シフト、スワップ要求、および休暇要求を非表示にするには、リソース[の種類をスケジュール](/graph/api/resources/schedule)Graph API使用して、Blue Yonder WFM インスタンスにマップした各チームに対して```false```次のパラメーターを設定します。

- 開いているシフト: ```openShiftsEnabled```
- スワップ要求:  ```swapShiftsRequestsEnabled```
- 休暇要求: ```timeOffRequestsEnabled```

Shifts で開いているシフト要求を非表示にするには、Shifts の **[設定]** に移動し、[シフトを **開く** ] 設定をオフにします。

## <a name="if-you-need-to-make-changes-to-a-connection"></a>接続に変更を加える必要がある場合
<a name="update_connection"> </a>

接続が設定されたら、PowerShell を使用して変更を加えます。 たとえば、同期設定、チーム マッピングを更新し、接続の同期を無効にすることができます。 詳細なガイダンスについては、「[PowerShell を使用して Blue Yonder Workforce Managementへの Shifts 接続を管理する](shifts-connector-powershell-manage.md)」を参照してください。

## <a name="related-articles"></a>関連記事

- [コネクタをシフトする](shifts-connectors.md)
- [PowerShell を使用して Blue Yonder Workforce Managementへの Shifts 接続を管理する](shifts-connector-powershell-manage.md)
- [Teams でシフト アプリを使用する](manage-the-shifts-app-for-your-organization-in-teams.md)
