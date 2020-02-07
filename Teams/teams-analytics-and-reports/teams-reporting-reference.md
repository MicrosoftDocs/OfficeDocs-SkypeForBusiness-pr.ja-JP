---
title: Microsoft Teams の分析とレポート
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords: ms.teamsadmincenter.analyticsandreports.overview
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターで利用可能な Teams のレポートについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: fc5c3c3c5588abe0c3ee748bdcd8a5ba3a2bf302
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827225"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams の分析とレポート

Microsoft Teams 管理センターで、Microsoft Teams についての新しい分析およびレポートのエクスペリエンスを利用することができます。 異なるレポートを実行して、自分の組織内のユーザーがどのように Teams を使用しているかについての洞察を得ることができます。 たとえば、何人のユーザーがチャネルおよびチャットのメッセージを通して通信を行っているか、および Teams に接続するために使用するデバイスの種類について、確認することができます。 自分の組織において、使用状況のパターンについてより理解を深めたり、ビジネスの意思決定を行う際に役立てたり、トレーニングやコミュニケーションの取り組みへの情報提供を行ったりするために、これらのレポートの情報を使用することができます。

## <a name="how-to-access-the-reports"></a>レポートにアクセスする方法

レポートにアクセスするには、Office 365 の全体管理者、Teams のサービス管理者、または Skype for Business の管理者であることが必要です。Microsoft Teams 管理センターに移動して、左側のナビゲーションにある **[分析およびレポート]** を選択し、**[レポート]** から実行するレポートを選択します。

> [!NOTE]
> Microsoft Teams 管理センターのレポートは、Microsoft 365 管理センターの Office 365 レポートに含まれている Teams のアクティビティレポートとは別のものです。 Microsoft 365 管理センターでのアクティビティレポートの詳細については、「 [microsoft 365 管理センターでのチームアクティビティレポート](../teams-activity-reports.md)」を参照してください。

## <a name="teams-reporting-reference"></a>Teams レポートの参照

ここでは、Microsoft Teams 管理センターで利用できる Teams レポートの一覧と、各レポートで利用できるいくつかの情報の概要を示します。

Microsoft では、Teams のレポート エクスペリエンスの継続的な改善と、機能の追加を行うための取り組みを行っています。 時間の経過とともに、追加の機能をレポートに組み入れるとともに、新しいレポートを Microsoft Teams 管理センターに追加していく予定です。

|レポート  |測定される項目 |
|---------|---------|
|[Teams の使用状況レポート](teams-usage-report.md)  |  アクティブなユーザー<br/>チーム内およびチャネル内のアクティブ ユーザー<br/>アクティブ チャネル<br/>メッセージ<br/>チームのプライバシー設定<br/>チームのゲスト   |
|[Teams ユーザー アクティビティ レポート](user-activity-report.md)  |  ユーザーが参加する 1 対 1 の通話<br/>チーム チャットにユーザーが投稿したメッセージ<br/>プライベート チャットにユーザーが投稿したメッセージ<br/>ユーザーの最後のアクティビティの日付     |
|[Teams のデバイス使用状況レポート](device-usage-report.md)   |  Windows ユーザー:<br/>Mac ユーザー<br/>iOS ユーザー<br/>Android スマートフォン ユーザー     |
|[Teams のライブ イベントの使用状況レポート](teams-live-event-usage-report.md)   |  ビューの合計<br>[開始時刻]<br>イベントの状態<br>[開催者]<br>者<br>者<br>レコーディングの設定<br>生産の種類    |
|[Teams PSTN ブロックユーザーレポート](pstn-blocked-users-report.md)   |  表示名<br>電話番号<br>理由<br>アクションの種類<br>アクションの日付と時刻   |
|[Teams の PSTN 分プールレポート](pstn-minute-pools-report.md) |  国または地域<br>機能 (ライセンス) <br>合計分数<br>使用分数<br>利用可能な通話時間|
|[Teams の PSTN 使用状況レポート-通話プラン](pstn-usage-report.md#calling-plans)|  タイムスタンプ<br>ユーザー名<br>電話番号<br>通話の種類 <br>呼び出し先<br>国または地域へ <br>呼び出し元 <br>国または地域から<br>職責<br>通貨<br>[時間]<br>国内/国際<br>通話 ID<br>数値の種類<br>国または地域<br>会議 ID<br>機能 (ライセンス)|
|[Teams の PSTN 使用状況レポート-直接ルーティング](pstn-usage-report.md#direct-routing)  |  タイムスタンプ<br>表示名<br>SIP アドレス<br>電話番号 <br>通話の種類<br>呼び出し先<br>[開始時刻]<br>[招待時間]<br>故障時間<br>[終了時刻]<br>[時間]<br>数値の種類<br>メディアバイパス<br>SBC FQDN<br>Azure の地域<br>イベントの種類<br>最終 SIP コード<br>最終 Microsoft サブコード<br>最終 SIP 語句<br>関連付け ID  |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]
