---
title: Shifts for Teams
description: スケジュール管理ツールである Shifts をTeamsで設定および管理するために必要な管理者ガイダンスを取得します。
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
- microsoftcloud-retail
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: f8980116dab90abd3c9c96ac17b577e6abf64f90
ms.sourcegitcommit: 3b86e55787c34da76428d6915964ac4f3c6239fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2022
ms.locfileid: "65598310"
---
# <a name="shifts-for-teams"></a>Shifts for Teams

シフトは、Teamsのスケジュール管理ツールであり、現場の従業員の接続と同期を維持します。高速で効果的なスケジュール管理と通信を実現するために、モバイルファーストが構築されています。 Shifts を使用すると、フロントライン マネージャーとワーカーはスケジュールをシームレスに管理し、連絡を取り合うことができます。

マネージャーは、チームのシフト スケジュールを作成、更新、管理できます。 シフトの割り当て、オープン シフトの追加、従業員からのスケジュール要求の承認を行うことができます。 従業員は、自分とチームのスケジュールを表示したり、可用性を設定したり、シフトを交換または提供したりするように要求したり、休暇を要求したり、出勤したりすることができます。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

次のリソースを使用して、組織内の Shifts を設定および管理します。

## <a name="set-up-and-manage-shifts"></a>Shifts の設定と管理

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">   |**[シフトを管理する](shifts/manage-the-shifts-app-for-your-organization-in-teams.md)** 組織のシフトを管理する方法について説明します。         |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">   |**[シフト管理のスケジュール所有者を管理する](shifts/schedule-owner-for-shift-management.md)** この機能を使用すると、従業員をチーム所有者にすることなく、チーム メンバーのアクセス許可をスケジュール所有者に昇格できます。         |
|<img src="/office/media/icons/help.png" alt="Help symbol.">     | **[Shifts データに関する FAQ](shifts/shifts-data-faq.md)** Shifts データの保存場所と、保持、取得、暗号化など、Shifts データに関連するその他のトピックについて説明します。        |

## <a name="shifts-connectors"></a>コネクタをシフトする

スケジュール設定にサード パーティの従業員管理 (WFM) システムを使用している場合は、マネージド Shifts コネクタを介して Shifts と直接統合できます。 接続を設定すると、フロントライン ワーカーは Shifts 内から WFM システムでスケジュールをシームレスに表示および管理できます。

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Shifts コネクタの概要](shifts/shifts-connectors.md)** Shifts コネクタとその動作の概要について説明します。 使用可能なマネージド コネクタとサポートされている WFM システムについて説明します。   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[マネージド シフト コネクタ](shifts/shifts-connectors.md#managed-shifts-connectors)** パートナーと共同で開発されたマネージド シフト コネクタは、Microsoft またはパートナーによってホストおよび管理されます。 詳細については、「[Microsoft Teams用の Blue Yonder および Reflectionis Shifts コネクタの Shifts コネクタ](shifts/shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)[Microsoft Teams](shifts/shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams)参照してください。    |
|   | **[Shifts コネクタ ウィザードを使用して Shifts を Blue Yonder Workforce Management に接続する](shifts/shifts-connector-wizard.md)** Microsoft 365 管理センターの Shifts コネクタ ウィザードを使用すると、WFM システムへの接続をすばやく設定できます。 現在、ウィザードは Blue Yonder 用の Teams Shifts コネクタをサポートし、Shifts と Blue Yonder Workforce Management を統合しています。
|  | **[PowerShell を使用してシフトを Blue Yonder Workforce Management に接続する](shifts/shifts-connector-blue-yonder-powershell-setup.md)** PowerShell を使用して、Blue Yonder の Teams Shifts コネクタを使用して Blue Yonder Workforce Management への接続を設定する方法について説明します。         |
|   | **[PowerShell を使用して、Blue Yonder Workforce Management への Shifts 接続を管理する](shifts/shifts-connector-powershell-manage.md)** Shifts コネクタ ウィザードまたは PowerShell を使用してセットアップした後、PowerShell を使用して Blue Yonder Workforce Management への Shifts 接続を管理する方法に関するガイダンスを取得します。

## <a name="shifts-extensions"></a>拡張機能をシフトする

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[Shift Graph API](/graph/api/resources/shift)** Shifts Graph API を使用すると、Shifts データと外部従業員管理 (WFM) システムを統合できます。 バックエンドでカスタム Shifts エクスペリエンスを構築し、ユーザーにTeamsで豊富なフロントエンド エクスペリエンスを提供する柔軟性があります。             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate を使用すると、Shift から情報を取得し、他のアプリでカスタム ワークフローを作成し、大規模な操作を実行できます。 コードをほとんどまたはまったく使用せずに、キー プロセスを自動化します。 トリガーとテンプレートは、マネージャーの承認が必要ない場合にシフト要求の自動承認を有効にするなど、さまざまなシナリオをサポートします。 |

## <a name="featured-training"></a>おすすめのトレーニング

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [ビデオ: Shifts とは何ですか?](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [ビデオ: シフト スケジュールを作成する](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [ビデオ: シフト スケジュールを管理する](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
