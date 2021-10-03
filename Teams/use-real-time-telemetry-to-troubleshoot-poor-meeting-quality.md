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
ms.openlocfilehash: 2730cb41267e8d02572f72d4d9ed7f154e021d9d
ms.sourcegitcommit: 26ce61afcb743c8b9e06b4fa048ad93ab70c31c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2021
ms.locfileid: "60082957"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>リアルタイム テレメトリを使用して低品質の会議のトラブルシューティングを行う

> [!NOTE]
> この機能は現在、2021 年末までパブリック プレビュー中です。 この時間が過Microsoft Teams、テレメトリをリアルタイムで表示するユーザーごとに、Microsoft Teams 用の Advanced Communications アドオンが必要になります。 詳細については、「[Microsoft Teams 用 Advanced Communications アドオン](/MicrosoftTeams/teams-add-on-licensing/advanced-communications)」を参照してください。

この記事では、Real-Time Analytics (RTA) を使用して、個々のユーザーの低品質の会議品質Microsoft Teamsトラブルシューティングする方法について説明します。 次のいずれかのロールReal-Time Analytics にアクセスできます。

- Teams 管理者
- Teams 通信サポート スペシャリスト
- Teams 通信サポート エンジニア

管理者ロールの詳細についてはTeams管理者ロールを使用して管理Microsoft Teams[を](/MicrosoftTeams/using-admin-roles)参照Teams。

Real-Time Analytics を使用すると、IT 管理者は重要なユーザーのスケジュールされた会議を確認し、音声、ビデオ、コンテンツ共有、ネットワーク関連の問題を確認できます。 管理者は、このテレメトリを使用して、会議中にこれらの問題を調査し、リアルタイムでトラブルシューティングを行います。

## <a name="what-is-real-time-analytics"></a>Real-Time Analytics とは

現在、個々の会議のトラブルシューティングは、会議Teams後に通話[分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)を通じて管理者が利用できます。 Real-Time Analytics を使用すると、管理者は進行中のスケジュールされた会議のトラブルシューティングを行います。

Real-Time Analytics には、リアルタイムで更新された Teams アカウント内の各ユーザーのOffice 365会議に関する詳細情報が表示されます。 これには、デバイス、ネットワーク、接続、オーディオ、ビデオ、コンテンツ共有の問題に関する情報が含まれます。これは、管理者が通話品質のトラブルシューティングを効果的に行うのに役立ちます。

管理者Teams、各ユーザーのすべてのリアルタイム テレメトリ データにフル アクセスできます。 さらに、Azure Active Directory の役割をサポートスタッフに割り当てることができます。 これらのロールの詳細については、「サポートおよびヘルプ デスクスタッフに [アクセス許可を付与する」を参照してください](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>ユーザーごとのリアルタイム トラブルシューティング テレメトリの場所

ユーザーのすべての会議情報とデータを表示するには、管理センターのTeams[移動します](https://admin.teams.microsoft.com)。 [**ユーザー**  >  **管理ユーザー]** でユーザーを選択し、ユーザーのプロファイル ページ& [会議の通話] タブを開きます。 [**最近の会議**] の下に、ユーザーが過去 24 時間以内に出席した会議の一覧が表示されます。この一覧には、進行中の会議も含め、リアルタイムテレメトリが利用できます。 会議が進行中ではない場合、またはリアルタイムのテレメトリ データが存在しない場合は、[過去の会議] に **表示されます**。

![最近の会議テーブルのスクリーンショット。](media/recent-meetings.png)

デバイス、ネットワーク、音声の統計情報など、進行中の会議の参加者に関する追加情報を取得するには、[最近の会議] で会議を見つけ、[参加者] 列の下にあるリンク **を選択** します。

![参加者の詳細テーブルのスクリーンショット。](media/participant-details.png)

デバイス、ネットワーク、音声、ビデオ、コンテンツ共有の詳細に関する情報など、進行中の会議の特定のユーザーのテレメトリを確認するには、[会議 **ID] を選択します**。

![通話分析のユーザー セッション データのスクリーンショット。](media/real-time-telemetry.png)

## <a name="client-platforms-supported-for-real-time-telemetry"></a>リアルタイム テレメトリでサポートされるクライアント プラットフォーム

- Windows
- macOS
- Linux
- Android
- iOS

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Teamsテレメトリをサポートするデバイスを追加する

- (香港) - Surface Hub
- [MTR - Teams Display]
- [アクセス設定] - [コラボレーション] バー
- IP 電話 デバイス

## <a name="limitations"></a>制限事項

- リアルタイム テレメトリは、スケジュールされた会議でのみ使用できます。 [今すぐ会議]、PSTN、1 対 1 の通話、グループ通話のような臨時の会議では、リアルタイム テレメトリは使用できません。
- リアルタイム テレメトリは、スケジュールされたライブ イベントの発表者にのみ使用できます。 現在、ライブ イベントの出席者は利用できません。
- リアルタイム テレメトリ データは、会議が終了した後24 時間、最近の会議の下の会議で使用できます。 24 時間が過ぎた場合、データにアクセスできないので、会議は [過去の会議] **に移動します**。 会議が 3 時間を超える場合、リアルタイム テレメトリは過去 3 時間のみ *使用できます*。
- 以前のバージョンのテレメトリを使用している場合、テレメトリはリアルタイムTeams。 利用できるテレメトリがない場合は、クライアントを更新してみてください。
- 外部参加者または匿名ユーザーが会議に参加した場合、表示名はテナント間のプライバシーを保持できないと表示されます。

## <a name="related-topics"></a>関連項目

[ユーザーごとの呼び出し分析を設定する](set-up-call-analytics.md)

[管理者Microsoft Teamsロールを使用して、 を管理Teams。](/MicrosoftTeams/using-admin-roles)
