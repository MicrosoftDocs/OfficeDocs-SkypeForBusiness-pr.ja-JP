---
title: Microsoft Teams の通話品質を監視および改善する
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: サービス品質 (QoS) 設定を使用し、次に[サービス品質ダッシュボード] と [通話品質ダッシュボード] Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ed9bab3ad0cde91bc8faa4298956b07f73438e823e3e3c110ce09610fee5e7c0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286266"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Microsoft Teams の通話品質を監視および改善する

この記事では、通話の品質を監視、トラブルシューティング、管理、および改善するために使用できる 3 つの主要なMicrosoft Teams。 

- **通話品質ダッシュボード (CQD)**: 組織全体の傾向や問題を分析するには、パフォーマンスの向上を図ります

- **通話分析**: 個々のユーザーの通話と会議の品質を分析するには

- **サービス品質 (QoS)**: 重要なネットワーク トラフィックに優先順位を付ける



## <a name="monitor-and-troubleshoot-call-quality"></a>通話品質の監視とトラブルシューティング
ユーザーごとの通話分析と通話品質ダッシュボードを使用して、継続的な運用中に発生する通話品質の問題を見つけてトラブルシューティングします。 これにより、ネットワーク全体でパフォーマンスの向上を実現できます。 これらの両方のツールは、管理センター Teamsにあります。

 - **通話分析は**、デバイス、ネットワーク、およびネットワーク内の各ユーザーの特定の通話 **** と会議に関連する接続に関する詳細情報をTeams。 Teamsヘルプデスク エージェントは、この情報を使用して、特定の通話の通話品質と接続の問題をトラブルシューティングします。 詳細については、「通話分析の [セットアップ」](set-up-call-analytics.md) と「通話分析を使用して低品質の通話のトラブルシューティングを行う」 [を参照してください](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
 
 - **通話品質ダッシュボード (CQD) を使用すると**、組織全体の通話品質をネットワーク全体で把握できます。 **** CQD 情報を使用して、問題の特定と修正に役立ちます。 最初に [、CQD を設定します](turning-on-and-using-call-quality-dashboard.md)。 次に、「通話[と会議の品質を管理する」をTeams。](quality-of-experience-review-guide.md)

 呼び出し分析と CQD は並列で実行され、独立して、または一緒に使用できます。 たとえば、通信サポートスペシャリストが、ユーザーの通話問題のトラブルシューティングにさらに役立つ必要があると判断した場合、通話をエスカレートして、通話に関する追加情報にアクセスできるコミュニケーション サポート エンジニアにエスカレートします。 次に、通信サポート エンジニアは、ネットワーク エンジニアに対して、通話分析で気付いたサイト関連の問題の可能性を警告します。 ネットワーク エンジニアは CQD をチェックして、サイト関連の全体的な問題がユーザーの通話問題の原因になる可能性がある場合を確認します。


## <a name="prioritize-important-network-traffic-using-qos"></a>QoS を使用して重要なネットワーク トラフィックの優先順位を設定する
ユーザーが通話や会議に Teamsを使用し始めるに当たって、発信者の音声が通話や会議に割り当てまたは切り取りされる場合があります。 共有ビデオがフリーズしたり、ピクセル化したり、完全に失敗したりすることがあります。 これは、ネットワークの輻輳に遭遇し、順序が切れか、または全く到着しない音声およびビデオ トラフィックを表す IP パケットによる場合です。 この問題が発生した場合 (または、最初に発生するのを防ぐため)、サービス品質 **(QoS) を使用します**。 

QoS を使用すると、遅延に敏感なネットワーク トラフィック (音声やビデオ ストリームなど) に優先順位を付け、機密性の低いトラフィック (新しいアプリをダウンロードする場合など、余分な秒をダウンロードする場合は大したことではない) の前で「ラインでカット」できます。 QoS は、Windows グループ ポリシー オブジェクトとポート ベースのアクセス制御リストと呼ばれるルーティング機能を使用して、リアルタイム ストリーム内のすべてのパケットを識別およびマークします。これは、音声、ビデオ、および画面共有に独自の専用ネットワーク帯域幅を与えるようネットワークに指示します。

理想的には、内部ネットワークに QoS を実装しながら、Teamsを展開する準備をしますが、いつでも実行できます。 十分に小さい場合は、QoS が必要ない場合があります。

準備ができたら、「サービス品質の実装[(QoS)](QoS-in-Teams.md)」を参照Microsoft Teams。

QoS を使用して会議トラフィックを管理するには、「会議のリアルタイム メディア トラフィックを処理する方法を設定する」[をTeamsします](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。


## <a name="related-topics"></a>関連項目

[通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[ CQDをセットアップする](turning-on-and-using-call-quality-dashboard.md)

[通話と会議の品質を管理Teams](quality-of-experience-review-guide.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)