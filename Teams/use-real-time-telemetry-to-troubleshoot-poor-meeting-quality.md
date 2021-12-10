---
title: リアルタイム テレメトリを使用して低品質の会議のトラブルシューティングを行う
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: デバイス、ネットワーク、接続に関する詳細を含むリアルタイム テレメトリを使用して、スケジュールされた会議に関するユーザー Microsoft Teamsトラブルシューティングします。
ms.openlocfilehash: 199eac099e23e8f8f0d96393484c4594763bb47a
ms.sourcegitcommit: 12044ab8b2e79a7b23bf9a0918ae070925d21f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2021
ms.locfileid: "61402001"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>リアルタイム テレメトリを使用して低品質の会議のトラブルシューティングを行う

この記事では、Real-Time Analytics (RTA) を使用して、個々のユーザーの低品質の会議品質Microsoft Teamsトラブルシューティングする方法について説明します。 次のいずれかのロールReal-Time Analytics にアクセスできます。

- Teams 管理者
- Teams 通信サポート スペシャリスト
- Teams 通信サポート エンジニア

管理者ロールの詳細についてはTeams管理者ロールを使用した管理Microsoft Teamsを[参照](/MicrosoftTeams/using-admin-roles)Teams。

Real-Time Analytics を使用すると、IT 管理者は重要なユーザーのスケジュールされた会議を確認し、音声、ビデオ、コンテンツ共有、ネットワーク関連の問題を確認できます。 管理者は、このテレメトリを使用して、会議中にこれらの問題を調査し、リアルタイムでトラブルシューティングを行います。

## <a name="what-is-real-time-analytics"></a>Real-Time Analytics とは

現在、個々の会議のトラブルシューティングは、会議Teams後に通話[分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)を通じて管理者が利用できます。 Real-Time Analytics を使用すると、管理者は進行中のスケジュールされた会議のトラブルシューティングを行います。

Real-Time Analytics には、リアルタイムで更新された Teams アカウント内の各ユーザーのOffice 365に関する詳細情報が表示されます。 これには、デバイス、ネットワーク、接続、オーディオ、ビデオ、コンテンツ共有の問題に関する情報が含まれます。これは、管理者が通話品質のトラブルシューティングを効果的に行うのに役立ちます。

管理者Teams、各ユーザーのすべてのリアルタイム テレメトリ データにフル アクセスできます。 さらに、Azure Active Directory の役割をサポートスタッフに割り当てることができます。 これらのロールの詳細については、「サポートおよびヘルプ デスク スタッフに [アクセス許可を付与する」を参照してください](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>ユーザーごとのリアルタイム トラブルシューティング テレメトリの場所

ユーザーのすべての会議情報とデータを表示するには、管理センターの Teams[移動します](https://admin.teams.microsoft.com)。 [**ユーザー**  >  **管理ユーザー] で** ユーザーを選択し、ユーザーのプロファイル **ページ**& [通話] タブを開きます。 [**最近の会議**] の下に、ユーザーが過去 24 時間以内に出席した会議の一覧が表示されます。この一覧には、進行中の会議も含め、リアルタイムテレメトリが利用できます。 会議が進行中ではない場合、またはリアルタイムのテレメトリ データが存在しない場合は、[過去の会議] に **表示されます**。

:::image type="content" alt-text="最近の会議テーブルのスクリーンショット。" source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

デバイス、ネットワーク、音声の統計情報など、進行中の会議の参加者に関する追加情報を取得するには、[最近の会議] で会議を見つけ、[参加者] 列の下にあるリンク **を選択** します。

:::image type="content" alt-text="参加者の詳細テーブルのスクリーンショット。" source="media/participant-details.png" lightbox="media/participant-details.png":::

デバイス、ネットワーク、音声、ビデオ、コンテンツ共有の詳細に関する情報など、進行中の会議の特定のユーザーのテレメトリを確認するには、[会議 **ID] を選択します**。

:::image type="content" alt-text="通話分析のユーザー セッション データのスクリーンショット。" source="media/real-time-telemetry.png" lightbox="media/real-time-telemetry.png":::

## <a name="measures-available-in-real-time-analytics"></a>Real-Time Analytics で使用可能なメジャー

|メジャーの名前 |単位 |良好なしきい値 |説明 |
|:---|:---|:---|:---|
|ジッター |ミリ秒 |30 ミリ秒未満 |ジッターは、データ ストリームのパケット遅延の変動の尺度です。 これが高すぎると、オーディオが途切れになる可能性があります。 | 
|パケット損失 |パーセンテージ |5% 未満 |パケット損失は、データ パケットが宛先に到達できなかった場合に発生します。 失われたパケットの割合は、送信されたパケットの総数に基づいて行われます。 |
|ラウンド トリップ時間 |ミリ秒 |500 ミリ秒未満 |ラウンド トリップ時間は、1 つのパケットがクライアントからリモート エンドポイントに移動し、クライアントに戻る時間です。 ラウンド トリップ時間が長い場合、ストリームの再生に遅延が発生する可能性があります。 たとえば、会議に参加している 2 人のユーザーが、遅延のために意図せずに互いに話し合っている場合です。 |
|ビットレート (オーディオ) |キロビット/秒 (Kbps) |24 Kbps を超える |キロビット/秒で表されるオーディオ ストリームのスループット。 |
|ビットレート (ビデオ & アプリの共有) |メガビット/秒 (Mbps) | 情報のみ |メガビット/秒で表されるビデオ ストリームのスループット。 |
|フレーム レート (ビデオ) |秒あたりのフレーム数 |360p 以上: 25 ~ 30 FPS <br/> 270p 以下: 7 ~ 15 FPS |送信ビデオ ストリームの場合、フレーム レート (FPS) は、クライアントが送信しているビデオの 1 秒あたりのフレーム数です。 ここで想定される値より小さい場合は、システム リソースの制約、ネットワーク帯域幅の不足、またはビデオ キャプチャ デバイスの動作の誤りを示している可能性があります。 解像度が異なると、許容できる FPS 範囲が異なります。 |
|フレーム レート (アプリ共有) |1 秒あたりのフレーム数 (FPS) |情報のみ |アプリ共有の場合、フレーム レートはコンテンツに対応し、必要な数のフレームが送信され、フレームが不要な場合は送信を回避しながら、適切なエクスペリエンスを確保します。 たとえば、スクリーンでテキスト ドキュメントを共有する場合、優れたエクスペリエンスを実現するには 1 秒あたり 1 フレームしか必要ないのに対し、より多くのアクティビティを使用してビデオやコンテンツを共有すると、1 秒あたりのフレーム数が最大 30 FPS に増加し、よりスムーズなエクスペリエンスが実現します。 |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>リアルタイム テレメトリでサポートされるクライアント プラットフォーム

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> Teams Web クライアント (VDI を含む) では、テレメトリのリアルタイム配信はサポートされていません。

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Teamsテレメトリをサポートするデバイスを選択する

- (香港) - Surface Hub
- [MTR - Teams Display]
- [アクセス設定] - [コラボレーション] バー
- IP 電話 デバイス

> [!NOTE]
> Cloud Video Interop (CVI) ソリューションを使用して会議に参加したデバイスは、Real-Time Analytics ではサポートされていません。


## <a name="limitations"></a>制限事項

- リアルタイム テレメトリは、スケジュールされた会議でのみ使用できます。 [今すぐ会議]、PSTN、1 対 1 の通話、グループ通話のような臨時の会議では、リアルタイム テレメトリは使用できません。
- リアルタイム テレメトリは、スケジュールされたライブ イベントの発表者にのみ使用できます。 現在、ライブ イベントの出席者は利用できません。
- リアルタイム テレメトリ データは、会議が終了した後24 時間、最近の会議の下の会議で使用できます。 24 時間が過ぎた場合、データにアクセスできないので、会議は [過去の会議] **に移動します**。 会議が 3 時間を超える場合、リアルタイム テレメトリは過去 3 時間のみ *使用できます*。
- 以前のバージョンのテレメトリを使用している場合、テレメトリはリアルタイムTeams。 利用できるテレメトリがない場合は、クライアントを更新してみてください。
- 外部参加者または匿名ユーザーが会議に参加した場合、表示名はテナント間のプライバシーを保持できないと表示されます。

## <a name="related-topics"></a>関連トピック

[ユーザーごとの通話分析を設定する](set-up-call-analytics.md)

[管理者Microsoft Teamsロールを使用して、 を管理Teams。](/MicrosoftTeams/using-admin-roles)
