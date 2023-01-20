---
title: Microsoft Teams の分析とレポート
ms.author: mikeplum
author: MikePlumleyMSFT
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
- m365initiative-meetings
description: この記事では、Microsoft Teams 管理センターで使用できる Teams レポートについて説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1062afeebfde89835330fbc4f367e0fccbe01513
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2023
ms.locfileid: "69845924"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams の分析とレポート

Microsoft Teams 管理センターで、Microsoft Teams についての新しい分析およびレポートのエクスペリエンスを利用することができます。 異なるレポートを実行して、自分の組織内のユーザーがどのように Teams を使用しているかについての洞察を得ることができます。 たとえば、何人のユーザーがチャネルおよびチャットのメッセージを通して通信を行っているか、および Teams に接続するために使用するデバイスの種類について、確認することができます。 自分の組織において、使用状況のパターンについてより理解を深めたり、ビジネスの意思決定を行う際に役立てたり、トレーニングやコミュニケーションの取り組みへの情報提供を行ったりするために、これらのレポートの情報を使用することができます。

## <a name="how-to-access-the-reports"></a>レポートにアクセスする方法

レポートにアクセスするには、次のいずれかのロールを割り当てる必要があります。

- グローバル管理者。
- Teams またはSkype for Business管理者。
- グローバル リーダー (テナント レベルの集計のみ、ユーザーまたはチームごとのデータなし)。

Teams 管理者ロールと、各管理者ロールがアクセスできるレポートの詳細については、「 [Teams 管理者ロールを使用して Teams を管理する](../using-admin-roles.md)」を参照してください。

Microsoft Teams 管理センターに移動し、左側のナビゲーションで [ **Analytics & レポート**] を選択し、[ **レポートの表示**] で実行するレポートを選択します。

> [!NOTE]
> Microsoft Teams 管理センターのレポートは、Microsoft 365 管理センターの Microsoft 365 レポートの一部である Teams のアクティビティ レポートとは別です。 Microsoft 365 管理センターのアクティビティ レポートの詳細については、[管理センターの「Microsoft 365 レポート](/microsoft-365/admin/activity-reports/activity-reports)」を参照してください。

## <a name="teams-reporting-reference"></a>Teams レポートの参照

さまざまな環境で Microsoft Teams 管理センターで利用できる Teams レポートの一覧と、各レポートで使用できる情報の概要を次に示します。

Microsoft では、Teams のレポート エクスペリエンスの継続的な改善と、機能の追加を行うための取り組みを行っています。 時間の経過とともに、追加の機能をレポートに組み入れるとともに、新しいレポートを Microsoft Teams 管理センターに追加していく予定です。

|レポート  |公共 |Gcc |GCCH |国防 総省 |測定される項目 |
|---------|---------|---------|---------|---------|---------|
|[Teams の使用状況レポート](teams-usage-report.md)  |Yes|Yes|Yes|Yes|  アクティブなユーザー<br/>チーム内およびチャネル内のアクティブ ユーザー<br/>アクティブ チャネル<br/>メッセージ<br/>チームのプライバシー設定<br/>チーム内のアクティブなゲスト  <br/>アクティブな外部ユーザー (共有チャネル内)<br/>チーム内の共有チャネル固有の詳細 (新規)|
|[Teams ユーザー アクティビティ レポート](user-activity-report.md)  |Yes|Yes|Yes|Yes|アクティブな内部および外部 (共有チャネル内) ユーザー<br/> チーム チャットにユーザーが投稿したメッセージ<br/>プライベート チャットにユーザーが投稿したメッセージ<br/>  ユーザーが参加する 1 対 1 の通話<br/> 組織された会議ユーザーの数 <br/>ユーザーが参加した会議の数<br/>会議のオーディオ、ビデオ、画面の共有時間<br/>   ユーザーの最後のアクティビティの日付  <br>ユーザーの共有チャネル操作 (新規)</br>   |
|[Teams のデバイス使用状況レポート](device-usage-report.md)   |Yes|Yes|Yes|Yes|  Windows ユーザー<br/>Mac ユーザー<br/>iOS ユーザー<br/>Android スマートフォン ユーザー     |
|[Teams アプリ使用状況レポート (新規)](app-usage-report.md)   |Yes|Yes|いいえ|いいえ|  アプリのアクティブなユーザーの合計数<br/>アプリを使用したアクティブなチームの合計数<br/>インストールされているアプリの合計数 (新規)<br/>非アクティブなアプリの合計数 <br/>1P と 3P の合計と LoB アプリの使用量 (新規)     |
|[Teams のライブ イベントの使用状況レポート](teams-live-event-usage-report.md)   |Yes|Yes|いいえ|いいえ|  合計ビュー数<br>開始時刻<br>イベントの状態<br>開催者<br>プレゼンター<br>プロデューサー<br>録画設定<br>運用の種類    |
|[Teams PSTN でブロックされたユーザー レポート](pstn-blocked-users-report.md)   |Yes|Yes|いいえ|いいえ|  表示名<br>電話番号<br>理由<br>アクションの種類<br>アクションの日付と時刻   |
|[Teams PSTN 分プール レポート](pstn-minute-pools-report.md) |Yes|Yes|いいえ|いいえ|  国または地域<br>機能 (ライセンス) <br>合計分数<br>使用時間 (分)<br>利用できる分|
|[Teams PSTN 使用状況レポート - 通話プラン](pstn-usage-report.md#calling-plans)|Yes|Yes|いいえ|いいえ|  タイムスタンプ<br>ユーザー名<br>電話番号<br>通話の種類 <br>呼び出し対象<br>国または地域へ <br>から呼び出される <br>国または地域から<br>通話料<br>通貨<br>[時間]<br>国内/国際<br>通話 ID<br>数値の種類<br>国または地域<br>電話会議 ID<br>機能 (ライセンス)|
|[Teams PSTN 使用状況レポート - ダイレクト ルーティング](pstn-usage-report.md#direct-routing)  |Yes|Yes|いいえ|いいえ|  タイムスタンプ<br>表示名<br>SIP アドレス<br>電話番号 <br>通話の種類<br>呼び出し対象<br>開始時刻<br>招待時間<br>失敗時間<br>終了時刻<br>[時間]<br>数値の種類<br>メディアのバイパス<br>SBC FQDN<br>Azure リージョン<br>イベントの種類<br>最終 SIP コード<br>最終 Microsoft サブコード<br>最終的な SIP フレーズ<br>関連付け ID  |
|[Teams 情報保護ライセンス レポート](information-protection-license-report.md)  |Yes|Yes|いいえ|いいえ| <br>ユーザーが変更通知を介してメッセージをプッシュするための有効なライセンスを持っているかどうか</br><br>ユーザーによってトリガーされた変更通知イベントの合計数<br><br>組織全体の変更通知イベントをリッスンしているアプリ<br>|
|[Teams 仮想予定使用状況レポート](/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)|Yes|Yes|いいえ|いいえ| 仮想予定の数<br>予約予定の数<br>Teams 電子正常性レコード (EHR) 統合予定の数<br>予定の平均期間<br>出席者のロビーの平均待機時間<br>開始時刻<br>会議 ID<br>ロビーの待機時間<br>[時間]<br>ステータス<br>製品の種類<br>出席者<br>部署<br>SMS 送信済み<br>予定が高度な仮想予定機能を使用したかどうか|
|[Teams Advanced 仮想予定 アクティビティ レポート](/microsoft-365/frontline/advanced-virtual-appointments-activity-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |Yes|Yes|いいえ|いいえ|高度な仮想予定機能を使用しているユーザーの数<br>SMS テキスト通知を使用するユーザーの数<br>ロビー チャットを使用するユーザーの数 (近日公開予定)<br>オンデマンドの予定を実行するユーザーの数|
|[Teams EHR コネクタ 仮想予定 レポート](/microsoft-365/frontline/ehr-connector-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |Yes|Yes|いいえ|いいえ| 開始時刻<br>[時間]<br>プライマリ (会議開催者の名前)<br>プライマリのメール (会議の開催者のメール)<br>部署<br>応答<br>ロビーの待機時間<br>予定が割り当て制限内にあるかどうか|
|[Walkie Talkie の使用状況とパフォーマンス レポート](walkie-talkie-usage-report.md) |Yes|Yes|いいえ|いいえ| メトリックには、送受信されたプッシュツートーク (PTT) 送信の数、チャネル アクティビティ、転送期間、デバイスと参加者の詳細が含まれます。|
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>ユーザー固有のデータを匿名にする

使用状況レポートの識別可能な情報を匿名にするには、グローバル管理者である必要があります。 グローバル管理者では、表示名、グループ名、電子メール、AAD ID などの識別可能な情報 (MD5 ハッシュを使用) をレポートとそのエクスポートで非表示にすることができます。

1. Microsoft 365 管理センターで、[**設定** \> **] [組織の設定]** に移動し、[**サービス**] タブで [**レポート**] を選択します。
    
2. [ **レポート]** を選択し、[ **すべてのレポートに隠されたユーザー、グループ、サイト名を表示** する] を選択します。 この設定は、Microsoft 365 管理センターの使用状況レポートと Teams 管理センターの両方に適用されます。
  
3. [ **変更の保存] を選択します**。

> [!NOTE]
> この設定を有効にすると、Teams ユーザー アクティビティ レポート、[Teams デバイス使用状況](device-usage-report.md)[レポート、および Teams](user-activity-report.md) [使用状況](teams-usage-report.md)レポートのユーザー、グループ、およびサイト名の情報が識別されなくなります。 2021 年 9 月 1 日から、この設定は、重要な情報を保護し、企業が地域のプライバシー法をサポートできるようにするための継続的な取り組みの一環として、すべてのユーザーに対して既定で有効になっています。 
>
>この設定は、Microsoft 365 管理センター、Microsoft Graph、Power BI の Microsoft 365 使用状況レポートにも適用されます。
