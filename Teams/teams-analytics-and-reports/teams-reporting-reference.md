---
title: Microsoft Teams の分析とレポート
author: serdarsoysal
ms.author: serdars
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
description: この記事では、Microsoft Teams 管理センターで使用できる Teams レポートについて説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f0891b9267039d8c07d437cb8e67eb2b982a0016
ms.sourcegitcommit: cf2f2d23e6dcda0c03f22a5800a210a1c88e583f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65883550"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams の分析とレポート

Microsoft Teams 管理センターで、Microsoft Teams についての新しい分析およびレポートのエクスペリエンスを利用することができます。 異なるレポートを実行して、自分の組織内のユーザーがどのように Teams を使用しているかについての洞察を得ることができます。 たとえば、何人のユーザーがチャネルおよびチャットのメッセージを通して通信を行っているか、および Teams に接続するために使用するデバイスの種類について、確認することができます。 自分の組織において、使用状況のパターンについてより理解を深めたり、ビジネスの意思決定を行う際に役立てたり、トレーニングやコミュニケーションの取り組みへの情報提供を行ったりするために、これらのレポートの情報を使用することができます。

## <a name="how-to-access-the-reports"></a>レポートにアクセスする方法

レポートにアクセスするには、Microsoft 365 または Office 365 のグローバル管理者、Microsoft 365 または Office 365 のグローバル リーダー、Teams サービス管理者、または Skype for Business 管理者である必要があります。Teams 管理者ロールと、各管理者ロールがアクセスできるレポートの詳細については、「 [Teams 管理者ロールを使用して Teams を管理する」を参照してください](../using-admin-roles.md)。

Microsoft Teams 管理センターに移動し、左側のナビゲーションで **[Analytics & レポート**] を選択し、[ **レポートの表示**] で実行するレポートを選択します。

> [!NOTE]
> Microsoft Teams 管理センターのレポートは、Microsoft 365 管理センターの Microsoft 365 レポートの一部である Teams のアクティビティ レポートとは別です。 Microsoft 365 管理センターのアクティビティ レポートの詳細については、[Microsoft 365 管理センターの Teams アクティビティ レポートを](../teams-activity-reports.md)参照してください。

## <a name="teams-reporting-reference"></a>Teams レポートの参照

Microsoft Teams 管理センターで使用できる Teams レポートの一覧と、各レポートで使用できる情報の概要を次に示します。

Microsoft では、Teams のレポート エクスペリエンスの継続的な改善と、機能の追加を行うための取り組みを行っています。 時間の経過とともに、追加の機能をレポートに組み入れるとともに、新しいレポートを Microsoft Teams 管理センターに追加していく予定です。

|レポート  |測定される項目 |
|---------|---------|
|[Teams の使用状況レポート](teams-usage-report.md)  |  アクティブなユーザー<br/>チーム内およびチャネル内のアクティブ ユーザー<br/>アクティブ チャネル<br/>メッセージ<br/>チームのプライバシー設定<br/>チームのゲスト   |
|[Teams ユーザー アクティビティ レポート](user-activity-report.md)  | チーム チャットにユーザーが投稿したメッセージ<br/>プライベート チャットにユーザーが投稿したメッセージ<br/>  ユーザーが参加する 1 対 1 の通話<br/> ユーザーが組織した会議の数 <br/>ユーザーが参加した会議の数<br/>会議のオーディオ、ビデオ、画面の共有時間<br/>   ユーザーの最後のアクティビティの日付     |
|[Teams のデバイス使用状況レポート](device-usage-report.md)   |  Windows ユーザー:<br/>Mac ユーザー<br/>iOS ユーザー<br/>Android スマートフォン ユーザー     |
|[Teams のライブ イベントの使用状況レポート](teams-live-event-usage-report.md)   |  ビューの合計<br>開始時刻<br>イベントの状態<br>開催者<br>プレゼンター<br>プロデューサー<br>録画設定<br>運用の種類    |
|[Teams PSTN でブロックされたユーザー レポート](pstn-blocked-users-report.md)   |  表示名<br>電話番号<br>理由<br>アクションの種類<br>アクションの日付と時刻   |
|[Teams PSTN 分プール レポート](pstn-minute-pools-report.md) |  国または地域<br>機能 (ライセンス) <br>合計分数<br>使用時間 (分)<br>利用可能な分数|
|[Teams PSTN 使用状況レポート - 通話プラン](pstn-usage-report.md#calling-plans)|  タイムスタンプ<br>ユーザー名<br>電話番号<br>通話の種類 <br>呼び出し対象<br>国または地域へ <br>呼び出し元 <br>国または地域から<br>通話料<br>通貨<br>[時間]<br>国内/国際<br>通話 ID<br>数値の種類<br>国または地域<br>電話会議 ID<br>機能 (ライセンス)|
|[Teams PSTN 使用状況レポート - ダイレクト ルーティング](pstn-usage-report.md#direct-routing)  |  タイムスタンプ<br>表示名<br>SIP アドレス<br>電話番号 <br>通話の種類<br>呼び出し対象<br>開始時刻<br>招待時間<br>失敗時間<br>終了時刻<br>[時間]<br>数値の種類<br>メディアのバイパス<br>SBC FQDN<br>Azure リージョン<br>イベントの種類<br>最終 SIP コード<br>最終 Microsoft サブコード<br>最終的な SIP フレーズ<br>関連付け ID  |
|[Teams の情報保護ライセンス レポート](information-protection-license-report.md)  | <br>ユーザーが変更通知を介してメッセージをプッシュする有効なライセンスを持っているかどうか</br><br>ユーザーによってトリガーされた変更通知イベントの合計数<br><br>組織全体の変更通知イベントをリッスンしているアプリ<br>|
|[Teams Virtual Visits の使用状況レポート](virtual-visits-usage-report.md)  | 仮想予定の数<br>Bookings の予定の数<br>Teams 電子正常性レコード (EHR) の統合予定の数<br>予定の平均期間<br>出席者のロビーの平均待機時間<br>開始時刻<br>会議 ID<br>ロビーの待機時間<br>[時間]<br>ステータス<br>製品の種類<br>出席者<br>SMS 送信済み
|[Teams EHR コネクタの仮想予定レポート](../expand-teams-across-your-org/healthcare/ehr-admin-reports.md) | 開始時刻<br>[時間]<br>プライマリ (会議の開催者の名前)<br>プライマリのメール (会議の開催者のメール)<br>部署<br>応答<br>ロビーの待機時間<br>予定が割り当て制限内にあるかどうか
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>ユーザー固有のデータを匿名にする

Teams ユーザー アクティビティと Teams デバイス使用状況レポートのデータを匿名にするには、グローバル管理者である必要があります。 これにより、レポートとそのエクスポートの表示名、電子メール、Microsoft Azure Active Directory ID などの識別可能な情報が非表示になります。

1. Microsoft 365 管理センターで、[設定 **組織の設定]** \> に移動し、[**サービス**] タブで [**レポート**] を選択します。
    
2. [ **レポート]** を選択し、 **非表示にされたユーザー名、グループ名、サイト名をすべてのレポートに表示** することを選択します。 この設定は、Microsoft 365 管理センターと Teams 管理センターの使用状況レポートの両方に適用されます。
  
3. [ **変更の保存] を選択します**。

> [!NOTE]
> この設定を有効にすると、 [Teams ユーザー アクティビティ レポート](user-activity-report.md) と [Teams デバイス使用状況レポート](device-usage-report.md) レポートの情報が識別されなくなります。 Teams 管理センターで使用できるその他の使用状況レポートには影響しません。
> この設定は、Microsoft 365 管理センター、Microsoft Graph、および Power BI の Microsoft 365 使用状況レポートにも適用されます。
