---
title: Shifts for Teams
description: スケジュール管理ツールである Shifts を設定および管理するために必要な管理者ガイダンスをTeams。
ms.topic: conceptual
author: LanaChin
ms.author: v-lanachin
audience: admin
manager: samanro
f1.keywords:
- NOCSH
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 905e846537e40178eba55f1a4ccd9a0d1fd1f993
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279184"
---
# <a name="shifts-for-teams"></a>Shifts for Teams

シフトは、スケジュール管理ツールであり、Teams従業員の接続と同期を維持します。モバイルを最初に構築し、迅速かつ効果的なスケジュール管理と通信を行います。 シフトを使用すると、フロントライン マネージャーと作業員はスケジュールをシームレスに管理し、連絡を取り合います。

マネージャーは、チームのシフト スケジュールを作成、更新、管理できます。 シフトの割り当て、オープン シフトの追加、従業員からのスケジュール要求の承認を行います。 従業員は、自分とチームのスケジュールを表示したり、空き時間を設定したり、シフトを交換または提供したり、休み取りを要求したり、出勤したりすることができます。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

組織で Shifts を設定および管理するには、次のリソースを使用します。

## <a name="set-up-and-manage-shifts"></a>シフトの設定と管理

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">|**[組織内のシフトを管理する](shifts/manage-the-shifts-app-for-your-organization-in-teams.md)** 組織のシフトを管理する方法について学習します。 |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">|**[シフト管理のスケジュール所有者を管理する](shifts/schedule-owner-for-shift-management.md)** この機能を使用すると、従業員をチーム所有者にすることなく、チーム メンバーのアクセス許可をスケジュール所有者に昇格できます。 |

## <a name="shifts-connectors"></a>コネクタをシフトする

スケジュール設定にサード パーティの従業員管理 (WFM) システムを使用している場合は、管理された Shifts コネクタを介して Shifts と直接統合し、オープン ソースの Shifts コネクタを使用して Shifts Graph API と SDK を使用して統合できます。 接続を設定すると、フロントライン ワーカーは、シフト内から WFM システム内のスケジュールをシームレスに表示および管理できます。

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Shifts コネクタの概要](shifts/shifts-connectors.md)** Shifts コネクタの概要と動作について説明します。 使用可能なマネージド コネクタとオープン ソース コネクタと、サポートされている WFM システムについて説明します。   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Managed Shifts コネクタ](shifts/shifts-connectors.md#managed-shifts-connectors)** パートナーと共同で開発されたマネージド Shifts コネクタは、弊社またはパートナーによってホストおよび管理されます。 Rexis WFM システムを使用している場合は、「[Rexis Shifts](shifts/shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams) コネクタ」を参照Microsoft Teams詳細を確認してください。    |
|<img src="/office/media/icons/api.png" alt="Three gears - API.">    | **[オープン ソースの Shifts コネクタ](/microsoftteams/platform/samples/shifts-wfm-connectors)** コミュニティ駆動 [型のオープン](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) ソース コネクタを使用して、Shifts Graph API と SDK を使用して Kronos または JDA WFM システムを統合する方法について説明します。    |

## <a name="shifts-extensions"></a>拡張機能をシフトする

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[Shift Graph Api](/graph/api/resources/shift)** Shifts Graph Api を使用すると、Shifts データを外部の従業員管理 (WFM) システムと統合できます。 ユーザーは、カスタムの Shifts エクスペリエンスをバック エンドで柔軟に構築できる一方で、Teams で豊富なフロントエンド エクスペリエンスをユーザーに提供できます。             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shift + Power Automate を使用すると、Shifts から情報を取得し、他のアプリとカスタム ワークフローを作成し、大規模な操作を実行できます。 コードをほとんどまたは一緒に使用して、主要なプロセスを自動化します。 トリガーとテンプレートは、マネージャーの承認が不要な場合にシフト要求の自動承認を有効にするなど、さまざまなシナリオをサポートします。 |

## <a name="featured-training"></a>おすすめのトレーニング

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [ビデオ: Shifts とは](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [ビデオ: シフト スケジュールを作成する](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [ビデオ: シフト スケジュールを管理する](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
