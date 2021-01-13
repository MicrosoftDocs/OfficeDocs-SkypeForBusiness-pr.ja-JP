---
title: Microsoft Teams の分析とレポート
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: この記事では、Microsoft Teams 管理センターで利用できる Teams レポートについて説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 902320f1ea2bc9071bbb9fc2be531117dabc8eef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809277"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams の分析とレポート

Microsoft Teams 管理センターで、Microsoft Teams についての新しい分析およびレポートのエクスペリエンスを利用することができます。 異なるレポートを実行して、自分の組織内のユーザーがどのように Teams を使用しているかについての洞察を得ることができます。 たとえば、何人のユーザーがチャネルおよびチャットのメッセージを通して通信を行っているか、および Teams に接続するために使用するデバイスの種類について、確認することができます。 自分の組織において、使用状況のパターンについてより理解を深めたり、ビジネスの意思決定を行う際に役立てたり、トレーニングやコミュニケーションの取り組みへの情報提供を行ったりするために、これらのレポートの情報を使用することができます。

## <a name="how-to-access-the-reports"></a>レポートにアクセスする方法

レポートにアクセスするには、Microsoft 365 または Office 365、Teams サービス管理者、または Skype for Business 管理者のグローバル管理者である必要があります。Teams の管理者ロールと、各管理者ロールがアクセスできるレポートの詳細については、「Teams 管理者ロールを使用して Teams を管理する」 [を参照してください](../using-admin-roles.md)。

Microsoft Teams 管理センターに移動し、左側のナビゲーションで[分析& レポート] を選択し、[レポート] で実行するレポートを選択します。

> [!NOTE]
> Microsoft Teams 管理センターのレポートは、Microsoft 365 管理センターの Microsoft 365 レポートの一部である Teams のアクティビティ レポートとは別です。 Microsoft 365 管理センターのアクティビティ レポートの詳細については[、Microsoft 365](../teams-activity-reports.md)管理センターの Teams アクティビティ レポートを参照してください。

## <a name="teams-reporting-reference"></a>Teams レポートの参照

Microsoft Teams 管理センターで利用できる Teams レポートの一覧と、各レポートで利用できる一部の情報の概要を示します。

Microsoft では、Teams のレポート エクスペリエンスの継続的な改善と、機能の追加を行うための取り組みを行っています。 時間の経過とともに、追加の機能をレポートに組み入れるとともに、新しいレポートを Microsoft Teams 管理センターに追加していく予定です。

|レポート  |測定される項目 |
|---------|---------|
|[Teams の使用状況レポート](teams-usage-report.md)  |  アクティブなユーザー<br/>チーム内およびチャネル内のアクティブ ユーザー<br/>アクティブ チャネル<br/>メッセージ<br/>チームのプライバシー設定<br/>チームのゲスト   |
|[Teams ユーザー アクティビティ レポート](user-activity-report.md)  |  ユーザーが参加する 1 対 1 の通話<br/>チーム チャットにユーザーが投稿したメッセージ<br/>プライベート チャットにユーザーが投稿したメッセージ<br/>ユーザーの最後のアクティビティの日付     |
|[Teams のデバイス使用状況レポート](device-usage-report.md)   |  Windows ユーザー:<br/>Mac ユーザー<br/>iOS ユーザー<br/>Android スマートフォン ユーザー     |
|[Teams のライブ イベントの使用状況レポート](teams-live-event-usage-report.md)   |  合計ビュー数<br>[開始時刻]<br>イベントの状態<br>開催者<br>発表者<br>プロデューサー<br>録画設定<br>実稼働の種類    |
|[Teams PSTN ブロックユーザー レポート](pstn-blocked-users-report.md)   |  表示名<br>電話番号<br>理由<br>アクションの種類<br>アクションの日付と時刻   |
|[Teams PSTN 分プール レポート](pstn-minute-pools-report.md) |  国または地域<br>機能 (ライセンス) <br>合計分数<br>使用分数<br>利用可能な分数|
|[Teams PSTN 使用状況レポート - 通話プラン](pstn-usage-report.md#calling-plans)|  タイム スタンプ<br>ユーザー名<br>電話番号<br>通話の種類 <br>呼び出し<br>国または地域へ <br>呼び出しの次の名前 <br>国または地域から<br>充電<br>通貨<br>[時間]<br>国内/国際<br>通話 ID<br>数値の種類<br>国または地域<br>会議 ID<br>機能 (ライセンス)|
|[Teams PSTN 使用状況レポート - ダイレクト ルーティング](pstn-usage-report.md#direct-routing)  |  タイム スタンプ<br>表示名<br>SIP アドレス<br>電話番号 <br>通話の種類<br>呼び出し<br>[開始時刻]<br>[招待時間]<br>障害時間<br>[終了時刻]<br>[時間]<br>数値の種類<br>メディア バイパス<br>SBC FQDN<br>Azure 地域<br>イベントの種類<br>最終的な SIP コード<br>最終的な Microsoft サブコード<br>最終的な SIP 語句<br>関連付け ID  |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]
