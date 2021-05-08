---
title: 通話の品質を監視し、改善Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: サービス品質 (QoS) 設定を使用し、次に、Microsoft Teams の [通話分析] と [通話品質ダッシュボード] を使用します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 62e687de154fadffd6ac95bd628fec6f9454cc51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162659"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>通話の品質を監視し、改善Microsoft Teams

この記事では、通話の品質を監視、トラブルシューティング、管理、および改善するために使用できる 3 つの主要なツールについてMicrosoft Teams。 

- **通話品質ダッシュボード (CQD)**: 組織全体の傾向や問題を分析するには、パフォーマンスの向上に役立つ

- **通話分析**: 個々のユーザーの通話と会議の品質を分析するには

- **サービス品質 (QoS)**: 重要なネットワーク トラフィックに優先順位を付ける



## <a name="monitor-and-troubleshoot-call-quality"></a>通話品質の監視とトラブルシューティング
ユーザーごとの通話分析と通話品質ダッシュボードを使用して、進行中の操作中に発生する通話品質の問題を見つけてトラブルシューティングします。 これにより、ネットワーク全体のパフォーマンス向上を実現できます。 これらのツールはどちらも、管理センター Teamsにあります。

 - **通話分析では**、デバイス、ネットワーク、および各ユーザーの特定の通話や会議に **** 関連する接続に関する詳細情報がTeams。 Teamsヘルプデスク エージェントは、この情報を使用して、特定の呼び出しでの通話品質と接続の問題のトラブルシューティングを行います。 詳細については、「通話分析を設定 [する」](set-up-call-analytics.md) と「通話分析を使用して低品質の通話のトラブルシューティング [を行う」を参照してください](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
 
 - **通話品質ダッシュボード (CQD) を使用** すると、 **_組織全体の_** 通話品質をネットワーク全体で確認できます。 CQD 情報を使用して、問題の特定と解決に役立ちます。 最初に [、CQD を設定します](turning-on-and-using-call-quality-dashboard.md)。 次に、「[通話と会議の品質を管理する」をTeams。](quality-of-experience-review-guide.md)

 呼び出し分析と CQD は並列で実行され、個別に、または一緒に使用できます。 たとえば、通信サポートスペシャリストが、ユーザーの通話問題のトラブルシューティングにさらに支援が必要と判断した場合、通話に関する追加情報にアクセスできるコミュニケーション サポート エンジニアに通話をエスカレートします。 さらに、通信サポート エンジニアは、通話分析で気付いたサイト関連の問題の可能性についてネットワーク エンジニアに警告します。 ネットワーク エンジニアは、CQD をチェックして、サイト関連の全体的な問題がユーザーの通話問題の原因になる可能性がある場合を確認します。


## <a name="prioritize-important-network-traffic-using-qos"></a>QoS を使用して重要なネットワーク トラフィックに優先順位を付ける
ユーザーが通話や会議に Teams を使い始めると、発信者の音声が別れ、通話や会議の切り抜きが発生する可能性があります。 共有ビデオがフリーズしたり、ピクセル化したり、完全に失敗したりすることがあります。 これは、ネットワークの輻輳が発生し、順不同で到着する、または一切到着しない音声およびビデオ トラフィックを表す IP パケットが原因です。 これが発生した場合 (または、最初に発生するのを防ぐために) は、サービス品質 **(QoS) を使用します**。 

QoS では、遅延の影響を受けるネットワーク トラフィック (音声やビデオ ストリームなど) に優先順位を付け、機密性の低いトラフィックの前で (新しいアプリをダウンロードする場合など)、追加の 1 秒をダウンロードすることはあまり重要ではありません。 QoS は、Windows グループ ポリシー オブジェクトとポート ベースのアクセス制御リストと呼ばれるルーティング機能を使用して、すべてのパケットをリアルタイム ストリームで識別してマークします。この機能は、音声、ビデオ、画面共有に独自の専用ネットワーク帯域幅を提供するようネットワークに指示します。

理想的には、内部ネットワークに QoS を実装しながら、Teams を展開する準備をしますが、いつでも実行できます。 十分に小さい場合は、QoS は必要ない可能性があります。

準備ができたら、「サービス品質[(QoS)](QoS-in-Teams.md)を実装する」を参照Microsoft Teams。

QoS を使用して会議のトラフィックを管理するには、「会議のリアルタイム メディア トラフィックを処理する方法を設定する[」をTeamsしてください](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。


## <a name="related-topics"></a>関連トピック

[通話分析を設定する](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[CQD を設定する](turning-on-and-using-call-quality-dashboard.md)

[通話と会議の品質を管理Teams](quality-of-experience-review-guide.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)