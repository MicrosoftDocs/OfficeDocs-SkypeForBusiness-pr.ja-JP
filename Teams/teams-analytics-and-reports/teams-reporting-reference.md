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
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: この記事では、管理センターでTeamsレポートの詳細Microsoft Teamsします。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 02353f540a3739f46e8e693ab4e83141b0bdfd3b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583551"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams の分析とレポート

Microsoft Teams 管理センターで、Microsoft Teams についての新しい分析およびレポートのエクスペリエンスを利用することができます。 異なるレポートを実行して、自分の組織内のユーザーがどのように Teams を使用しているかについての洞察を得ることができます。 たとえば、何人のユーザーがチャネルおよびチャットのメッセージを通して通信を行っているか、および Teams に接続するために使用するデバイスの種類について、確認することができます。 自分の組織において、使用状況のパターンについてより理解を深めたり、ビジネスの意思決定を行う際に役立てたり、トレーニングやコミュニケーションの取り組みへの情報提供を行ったりするために、これらのレポートの情報を使用することができます。

## <a name="how-to-access-the-reports"></a>レポートにアクセスする方法

レポートにアクセスするには、Microsoft 365 または Office 365 のグローバル管理者、Microsoft 365 または Office 365、Teams サービス管理者、または Skype for Business 管理者である必要があります。管理者ロールの管理Teams、各管理者ロールがアクセスできるレポートの詳細については、「管理者ロールを使用Teamsを使用して管理者ロールを管理する[」](../using-admin-roles.md)をTeams。

Microsoft Teams 管理センターに移動し、左側のナビゲーションで **[Analytics & レポート**] を選択し、[レポート] で実行するレポートを選択します。

> [!NOTE]
> Microsoft Teams 管理センターのレポートは、Teams のレポートの一部である Microsoft 365 のアクティビティ レポートとはMicrosoft 365 管理センター。 アクティビティ レポートの詳細については、Microsoft 365 管理センター のアクティビティ Teams[を参照Microsoft 365 管理センター](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Teams レポートの参照

Microsoft Teams 管理センターで使用できる Teams レポートの一覧と、各レポートで使用できる情報の概要を次に示します。

Microsoft では、Teams のレポート エクスペリエンスの継続的な改善と、機能の追加を行うための取り組みを行っています。 時間の経過とともに、追加の機能をレポートに組み入れるとともに、新しいレポートを Microsoft Teams 管理センターに追加していく予定です。

|レポート  |測定される項目 |
|---------|---------|
|[Teams の使用状況レポート](teams-usage-report.md)  |  アクティブなユーザー<br/>チーム内およびチャネル内のアクティブ ユーザー<br/>アクティブ チャネル<br/>メッセージ<br/>チームのプライバシー設定<br/>チームのゲスト   |
|[Teams ユーザー アクティビティ レポート](user-activity-report.md)  | チーム チャットにユーザーが投稿したメッセージ<br/>プライベート チャットにユーザーが投稿したメッセージ<br/>  ユーザーが参加する 1 対 1 の通話<br/> 開催された会議ユーザーの数 <br/>参加した会議ユーザーの数<br/>会議の音声、ビデオ、画面の共有時間<br/>   ユーザーの最後のアクティビティの日付     |
|[Teams のデバイス使用状況レポート](device-usage-report.md)   |  Windows ユーザー:<br/>Mac ユーザー<br/>iOS ユーザー<br/>Android スマートフォン ユーザー     |
|[Teams のライブ イベントの使用状況レポート](teams-live-event-usage-report.md)   |  合計ビュー数<br>開始時刻<br>イベントの状態<br>開催者<br>発表者<br>プロデューサー<br>録画設定<br>実稼働の種類    |
|[TeamsPSTN ブロックユーザー レポート](pstn-blocked-users-report.md)   |  表示名<br>電話番号<br>理由<br>アクションの種類<br>アクションの日付と時刻   |
|[TeamsPSTN 分プール レポート](pstn-minute-pools-report.md) |  国または地域<br>機能 (ライセンス) <br>合計分数<br>使用時間 (分)<br>利用可能な分数|
|[TeamsPSTN 使用状況レポート - 通話プラン](pstn-usage-report.md#calling-plans)|  タイム スタンプ<br>ユーザー名<br>電話番号<br>通話の種類 <br>の呼び出し<br>国または地域へ <br>から呼び出されます。 <br>国または地域から<br>通話料<br>通貨<br>[時間]<br>国内/国際<br>通話 ID<br>数値の種類<br>国または地域<br>電話会議 ID<br>機能 (ライセンス)|
|[TeamsPSTN 使用状況レポート - 直接ルーティング](pstn-usage-report.md#direct-routing)  |  タイム スタンプ<br>表示名<br>SIP アドレス<br>電話番号 <br>通話の種類<br>の呼び出し<br>開始時刻<br>招待時間<br>失敗時間<br>終了時刻<br>[時間]<br>数値の種類<br>メディアのバイパス<br>SBC FQDN<br>Azure リージョン<br>イベントの種類<br>最終 SIP コード<br>最終 Microsoft サブコード<br>最終的な SIP フレーズ<br>関連付け ID  |
|[Teams情報保護ライセンス レポート](information-protection-license-report.md)  | <br>ユーザーが変更通知を使用してメッセージをプッシュする有効なライセンスを持っているかどうか</br><br>ユーザーによってトリガーされた変更通知イベントの総数</br><br>組織全体の変更通知イベントをリッスンしているアプリ</br>|


[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>ユーザー固有のデータを匿名にする

ユーザー アクティビティとデバイスTeamsレポートTeamsデータを匿名にする場合は、グローバル管理者である必要があります。 これにより、レポートとそのエクスポートの表示名、電子メール、AAD ID などの識別可能な情報が非表示になります。

1. [Microsoft 365 管理センター] の [組織]設定に設定し、[サービス] タブで \> **[** レポート] を選択 **します**。 
    
2. [ **レポート]** を選択し、[匿名識別子 **を表示する] を選択します**。 この設定は、管理センターだけでなく、Microsoft 365 管理センター使用状況レポートTeams適用されます。
  
3. [変更の **保存] を選択します**。

> [!NOTE]
> この設定を有効にすると、ユーザー アクティビティ レポートとデバイスTeams[レポートTeams](user-activity-report.md)[情報が識別されな](device-usage-report.md)されます。 管理センターで使用できる他の使用状況レポートTeams影響を受けられません。
