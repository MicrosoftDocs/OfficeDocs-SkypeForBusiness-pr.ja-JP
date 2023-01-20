---
title: Walkie Talkie の使用状況とパフォーマンス レポート
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: admin
ms.topic: article
ms.service: microsoft-365-frontline
ms.reviewer: prastogi
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
- tier2
description: Microsoft Teams 管理センターの Walkie Talkie 使用状況とパフォーマンス レポートを使用して、組織内の Walkie Talkie 使用状況アクティビティの概要を取得する方法について説明します。
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 85f92e715efe2b9608691151a08d006816658095
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2023
ms.locfileid: "69846052"
---
# <a name="walkie-talkie-usage-and-performance-report"></a>Walkie Talkie の使用状況とパフォーマンス レポート

Microsoft Teams 管理センターの Walkie Talkie の使用状況とパフォーマンス レポートには、組織内の [Walkie Talkie](../walkie-talkie.md) アクティビティの概要が表示されます。 レポートには、送信および受信したプッシュツートーク (PTT) 送信の数、チャネル アクティビティ、送信期間、デバイスと参加者の詳細などの情報が表示されます。

このレポートを使用して、組織内の Walkie Talkie の使用状況の傾向とパフォーマンスに関する分析情報を得ることができます。 レポートにアクセスするには、グローバル管理者、Teams 管理者、グローバル リーダー、またはレポート リーダーである必要があります。

## <a name="download-and-view-the-report"></a>レポートをダウンロードして表示する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[分析] **& [レポート****] [使用状況レポート** > ] を選択します。 [ **レポートの表示** ] タブの [ **レポート**] で、[ **トランシーバーの使用状況**] を選択します。
1. [ **日付範囲]** で、7 日または 30 日の日付範囲を選択します。 次に、[ **レポートの実行**] を選択します。
1. [ **レポートの生成] を選択します**。
1. [ **ダウンロード** ] タブの [ **状態] で**、[ **ダウンロード** ] を選択して CSV 形式でレポートをダウンロードします。

## <a name="interpret-the-report"></a>レポートを解釈する

レポートには、選択した日付範囲で行われた各転送の内訳が表示されます。 レポートに含まれている情報を次に示します。

|列名 |説明 |
|---------|---------|
|TenantId|テナント ID。|
|Userid|ユーザー ID。|
|DeviceId|デバイス ID。|
|ChannelId|コミュニケーションが行われるトランシーバー チャネル。|
|clientCallStatus | デバイスが問題なく転送を受信できたかどうかを示します。|
|ConversationId|各 PTT 転送の ID。|
|TeamId|ユーザーが接続する Walkie Talkie チャネルに対応するチームの ID。|
|UnreachableParticipantsCount|過去 5 つの転送のいずれかを受信できなかったため、到達不能としてフラグが設定され、名簿から非表示にされた参加者の数。|
|TransmissionDuration|サービスが転送の最後のパッケージを配信するときに、1 人の参加者が転送を開始しようとしているという通知をサービスが受信するまでの時間 (ミリ秒)。|
|TotalParticipantsCount|トランシーバー チャネルに接続されている参加者の合計数。|
|PacketCount|オーディオ転送の送信に使用されるパケットの数。|
|NotifiedParticipants|転送の開始時にプッシュ通知が送信される参加者。 デバイスとサービスの間の接続が失われるシナリオでは、転送が行われるため、できるだけ早く接続を確立し直す通知がデバイスに送信されます。|
|AudioDurationMilliseconds|ミリ秒単位の転送の期間。|
|ConnectionId|デバイスによって確立された Walkie Talkie チャネルへの各接続の ID。|
|TransmissionStartTime |サービスが最初のオーディオ パケットを受信した日時。
|TransmissionEndTime|サービスが最後のオーディオ パケットを受信した日時。|
|ParticipantList|伝送の送信時にチャネルに接続されているデバイスの ID のセミコロン区切りリスト。|
|CallTimedOut|転送が期間制限を超えたかどうか。 これはブール値です。|
|プラットフォーム|デバイス オペレーティング システム。|
|ParticipantType|参加者がトランスミッションの送信機か受信機か。|
|WebSocketState|転送の開始時に、デバイスとサービスの間の接続の状態が既に確立されているかどうか。|
|AppVersion|デバイスにインストールされている Teams アプリのバージョン。|

## <a name="related-articles"></a>関連記事

- [Teams のトランシーバー アプリ](../walkie-talkie.md)
- [トランシーバーの概要](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)