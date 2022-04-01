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
description: Shifts コネクタ ウィザードを使用して、Shifts を Blue Yonder Workforce Management Teams統合する方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593665"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Shifts コネクタ ウィザードを使用して Shifts を Blue Yonder Workforce Management に接続する

## <a name="overview"></a>概要

Microsoft 365 管理センター の Shifts コネクタ ウィザードを使用すると、Shifts アプリを Microsoft Teams従業員管理 (WFM) システムと統合できます。 接続を設定すると、フロントライン ワーカーは、シフト内から WFM システム内のスケジュールをシームレスに表示および管理できます。

ウィザードによって Shifts コネクタが構成され、WFM システムへの接続が作成され、選択した同期設定とチーム マッピングが適用されます。 同期設定は、WFM システムとシフトの間で同期されるスケジュール情報を決定します。 チーム マッピングは、WFM サイトとチームの間の同期関係を定義Teams。 既存のチームと新しいチームにマップできます。

同期設定が異なる複数の接続を設定できます。 たとえば、スケジュール要件が異なる複数の場所がある場合は、場所ごとに一意の同期設定を使用して接続を作成します。 WFM サイトは、いつでも 1 つのチームにのみマップできます。 WFM サイトが既にチームにマップされている場合は、別のチームにマップできません。

WFM システムをレコードのシステムとして使用すると、フロントライン ワーカーは、シフトの表示と交換、空き時間の管理、およびデバイス上のシフトでの空き時間の要求を行えます。 フロントライン マネージャーは、引き続き WFM システムを使用してスケジュールを設定できます。

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Shifts と Blue Yonder Workforce Management の統合

現在、ウィザードは Blue [Yonder Microsoft Teams Shifts コネクタをサポートしています](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)。 このコネクタを使用すると、Shifts と Blue Yonder Workforce Management (Blue Yonder WFM) を統合して、スケジュールを管理し、最新の状態に維持することができます。 この記事では、ウィザードを実行して、コネクタを介して Blue Yonder WFM への接続を設定する方法を示します。

> [!NOTE]
> PowerShell を使用して、Shifts と Blue Yonder WFM を統合できます。 詳細については、「 [PowerShell を使用して Shifts を Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md) に接続する」を参照してください。

## <a name="before-you-begin"></a>はじめに

ウィザードを実行するにはMicrosoft 365管理者である必要があります。

### <a name="prerequisites"></a>前提条件
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- マップするチームにスケジュールが設定されている必要があります。 チームに既存のスケジュールがある場合は、 [](#remove-schedules-from-teams-you-want-to-map) Blue Yonder WFM サイトをマップする前にチームからスケジュールを削除します。 それ以外の場合は、重複するシフトが表示されます。

## <a name="remove-schedules-from-teams-you-want-to-map"></a>マップするチームからスケジュールを削除する
<a name="remove_schedules"> </a>

> [!NOTE]
> Blue Yonder WFM サイトをスケジュールがある既存のチームにマッピングする場合は、この手順を完了します。 スケジュールを持たなかったチームにマッピングしている場合、またはマップする新しいチームを作成する場合は、この手順をスキップできます。

PowerShell を使用してチームからスケジュールを削除します。

1. まず、PowerShell モジュールをインストールしてセットアップする必要があります。 手順に従って [環境を設定します](shifts-connector-powershell-manage.md#set-up-your-environment)。
1. 次のコマンドを実行します。

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    パラメーターのシナリオの一覧を取得するには `EntityType` 、 [Get-CsTeamsShiftsConnectionConnector を実行します](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)。 指定した日付と時刻の範囲のスケジュール データが削除されます。

詳細については、「 [Remove-CsTeamsShiftsScheduleRecord」を参照してください](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)。

## <a name="run-the-wizard"></a>ウィザードを実行する

### <a name="get-started"></a>はじめに

1. アプリの左側の [ナビゲーションMicrosoft 365 管理センター、[](https://admin.microsoft.com/)セットアップ] を選択し、[アプリと電子メール **] セクションに移動** します。
1. 従業員 **管理Connectを選択します**。 ここでは、Shifts コネクタと、Shifts を WFM システムに接続する際のフロントライン worker とマネージャーのエクスペリエンスについて詳しくは、こちらを参照してください。
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="[Shifts コネクタ] ウィザードの [詳細] ページのスクリーンショットMicrosoft 365 管理センター。" lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. 準備ができたら、[設定] **概要**。
1. [次 **へ]** を選択して、Blue Yonder WFM 接続を作成します。

### <a name="enter-connection-details"></a>接続の詳細を入力する
<a name="connection_details"> </a>

1. [接続の詳細] ページで、接続に一意の名前を付きます。 128 文字を超えることはできません。また、特殊文字を使用することはできません。
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="接続設定を示すウィザードの [接続の詳細] ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Blue Yonder WFM サービス アカウント名とパスワードとサービス URL を入力します。
1. 完了したら、[次へ] **を選択** して、入力した設定で接続をテストします。

### <a name="choose-sync-settings"></a>同期設定を選択する
<a name="sync"> </a>

[同期設定] ページで、Blue Yonder WFM から Shifts に同期する情報、同期頻度、および Shifts ユーザーがデータを変更できるかどうかを選択します。

1. システム アカウントMicrosoft 365入力します。
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="同期設定を示すウィザードの [同期設定] ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. [ **電子メール通知の受信者] で**、この接続に関する電子メール通知を受け取るユーザーを選択します。 個々のユーザーとグループを追加できます。 電子メール通知には、接続設定の状態に関する情報と、接続の設定後に発生する可能性がある問題やエラーが含まれています。
1. 同期設定を選択します。
    1. [ **スケジュールとシフト] で**、Shifts ユーザーが表示または変更できる Blue Yonder WFM データを選択し、同期頻度を設定します。
    2. [ **リクエスト] で**、Shifts ユーザーが表示して作成できる要求の種類を選択します。

    > [!IMPORTANT]
    > 次のオプションを選択して、シフトを開く、シフト要求を開く、要求を交換する、またはタイムオフ要求を無効にした場合は、Shifts で機能を非表示にするには、別の手順を実行する必要があります。
    >
    > - シフトを開く: **Shifts ユーザーに Blue Yonder WFM データが表示されない**
    > - スワップ要求: **すべてのユーザーに対して機能が無効になっている**
    > - [Time off requests] ( **タイムオフ要求): すべてのユーザーに対して機能が無効になっている**
    >
    > ウィザードを実行したら、この記事の後半の「オープン シフトを[](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests)無効にする、シフト要求、スワップ要求、およびタイムオフ要求を開く」セクションの手順に従ってください。
 
1. 設定の選択が完了したら、[接続の作成] **を選択します**。

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>Blue Yonder Workforce Management サイトをチームにマップする
<a name="sites"> </a>

Shifts に接続する Blue Yonder WFM サイトを選択します。 最大 100 のサイトを選択できます。

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Blue Yonder WFM サイトの一覧を示すウィザードのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a>次に、選択した各 Blue Yonder WFM サイトを、Teams のチームにマップします。 サイトを既存のチームにマップするか、新しいチームを作成できます。
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="[検索チーム] オプションを表示し、新しいチーム オプションを作成するウィンドウのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>サイトを既存のチームにマップするには

1. サイト名を選択します。
2. ウィンドウでチームを検索し、選択します。 この接続でサイトに既にマップされているチームは検索に表示されません。
3. タイム ゾーンと最も近い都市を選択します。
4. [保存 **] を** 選択し、[次へ] を **選択します**。

#### <a name="to-map-a-site-to-a-new-team"></a>サイトを新しいチームにマップするには

1. サイト名を選択します。
2. ウィンドウで、[新しいチームの **作成] を選択します**。 ブラウザーで新しいタブが表示されます。このタブでは、新しいチームを作成Microsoft 365 管理センター。
    1. チームの名前とオプションの説明を入力します。
    1. 1 つ以上のチーム所有者を追加します。 システム アカウントを所有者Microsoft 365追加してください。
    1. チーム メンバーを追加します。
    1. チームのメール アドレスを追加し、プライバシー設定を選択します。
    1. 設定を確認し、[チームの追加 **] を選択します**。 チームが作成したら、[閉じる] を **選択します**。
3. 戻るにアクセスし、作成した新しいチームを検索して選択します。
4. タイム ゾーンと最も近い都市を選択します。
5. [保存 **] を** 選択し、[次へ] を **選択します**。

### <a name="review-and-finish"></a>確認と終了

設定を確認します。 チーム マッピングを変更する必要がある場合は、[編集] **を選択して** 変更します。 準備ができたら、[完了] を **選択します**。

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="ウィザードの [レビュー] ページのスクリーンショット。マッピングが表示されています。" lightbox="../../media/shifts-connector-wizard-review.png":::

操作 ID と共に要求を受信したというメッセージが表示されます。 操作 ID をメモします。 接続のセットアップ状態を確認するために必要になります。

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="確認メッセージと操作 ID を示すウィザード ページのスクリーンショット。" lightbox="../../media/shifts-connector-wizard-operation-id.png":::

ウィザードは、接続を設定するプロセスを開始し、サイトを選択したチームにマップします。 このプロセスが完了するには時間がかかる場合があります。 選択した受信者は、セットアップの状態に関する電子メール通知を受け取る。

[完了 **] を** 選択してウィザードを終了します。

途中ですが、まだ完了していません。 必ずメールを確認してください。 セットアップの状態を確認する方法へのリンクと共に、要求[](shifts-connector-powershell-manage.md#check-connection-setup-status)を受け取ったという確認メッセージが表示されます。

> [!NOTE]
> セットアップ後に接続で問題またはエラーが発生した場合は、電子メールで通知されます。 メールの指示に従って、問題のトラブルシューティングを行います。

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>オープン シフトを無効にする、シフトを開く要求、スワップ要求、およびタイムオフ要求

> [!IMPORTANT]
> 次の手順に従うのは、次のオプションを選択して、開いているシフトを無効にする場合、シフト要求を開く、要求を交換する、またはウィザードで時間を取る要求を無効にする場合のみです。 この手順を完了すると、Shifts の機能が非表示になります。
>
> - シフトを開く: **Shifts ユーザーに Blue Yonder WFM データが表示されない**
> - スワップ要求: **すべてのユーザーに対して機能が無効になっている**
> - [Time off requests] ( **タイムオフ要求): すべてのユーザーに対して機能が無効になっている**
>
> この 2 番目の手順を実行しない場合でも、ユーザーには Shifts の機能が表示され、使用しようとして "サポートされていない操作" エラー メッセージが表示されます。

Shifts で開いているシフト、スワップ要求、およびタイムオフ要求を非表示にする場合は、Graph API [](/graph/api/resources/schedule?view=graph-rest-1.0) ```false``` スケジュール リソースの種類を使用して、Blue Yonder WFM サイトにマップした各チームに対して次のパラメーターを に設定します。

- シフトを開く: ```openShiftsEnabled```
- スワップ要求:  ```swapShiftsRequestsEnabled```
- [Time off requests]を選択します。 ```timeOffRequestsEnabled```

Shifts で開いているシフト要求を非表示にする場合は、Shifts 設定 に移動し、[シフトを開く] 設定 **をオフ** にします。

## <a name="if-you-need-to-make-changes-to-a-connection"></a>接続を変更する必要がある場合
<a name="update_connection"> </a>

接続を設定した後、PowerShell を使用して接続を変更します。 たとえば、同期設定、チーム マッピングを更新し、接続の同期を無効にできます。 詳細なガイダンスについては、「PowerShell を使用して [Blue Yonder Workforce Management へのシフト接続を管理する」を参照してください](shifts-connector-powershell-manage.md)。

## <a name="related-articles"></a>関連記事

- [コネクタをシフトする](shifts-connectors.md)
- [PowerShell を使用して Blue Yonder Workforce Management へのシフト接続を管理する](shifts-connector-powershell-manage.md)
- [Shifts アプリを管理Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
