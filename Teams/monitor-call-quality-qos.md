---
title: Microsoft Teams の通話品質を監視および改善する
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: サービスの品質 (QoS) 設定を使用し、Microsoft Teams で通話分析と通話品質ダッシュボードを使用します。
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
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Microsoft Teams の通話品質を監視および改善する

この記事では、Microsoft Teams の通話品質を監視、トラブルシューティング、管理、改善するために使用できる 3 つの重要なツールについて説明します。 

- **通話品質ダッシュボード (CQD):** 組織全体の傾向や問題を分析するには、パフォーマンスの向上を後で行います。

- **通話分析**: 個々のユーザーの通話と会議の品質を分析するには

- **サービスの品質 (QoS):** 重要なネットワーク トラフィックを優先順位付けするには



## <a name="monitor-and-troubleshoot-call-quality"></a>通話品質を監視およびトラブルシューティングする
ユーザーごとの通話分析と通話品質ダッシュボードを使用して、進行中の操作中に発生する通話品質の問題を見つけてトラブルシューティングします。 これにより、ネットワーク全体でパフォーマンスの向上を実現できます。 これらのツールは両方とも Teams 管理センターにあります。

 - **通話分析では、Teams** 内の各ユーザーの特定の通話と会議に関連 **** するデバイス、ネットワーク、接続に関する詳細情報が表示されます。 Teams 管理者とヘルプデスク エージェントは、この情報を使用して、特定の通話での通話品質と接続の問題のトラブルシューティングを行います。 詳細については、「通話分析を [設定する](set-up-call-analytics.md) 」と「通話分析を使用して低品質の通話のトラブルシューティングを行う [」を参照してください](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
 
 - **通話品質ダッシュボード (CQD)** では ****、組織全体の通話品質をネットワーク全体で表示できます。 CQD 情報を使用して、問題を特定して解決します。 まず [、CQD をセットアップします](turning-on-and-using-call-quality-dashboard.md)。 次に [、「Teams で通話と会議の品質を管理する」を読む](quality-of-experience-review-guide.md)。

 通話分析と CQD は並列で実行され、個別に、または一緒に使用できます。 たとえば、通信サポートの専門家が、ユーザーの通話の問題のトラブルシューティングにさらに支援が必要と判断した場合、通話に関する追加情報にアクセスできるコミュニケーション サポート エンジニアに通話をエスカレーションします。 さらに、通信サポート エンジニアは、ネットワーク エンジニアに対して、通話分析で気付いたサイト関連の問題の可能性を警告します。 ネットワーク エンジニアは CQD をチェックして、サイト関連の全体的な問題がユーザーの通話の問題の原因になる可能性を確認します。


## <a name="prioritize-important-network-traffic-using-qos"></a>QoS を使用して重要なネットワーク トラフィックを優先順位付けする
ユーザーが通話や会議に Teams を使い始めるに当たって、発信者の音声が通話や会議で切り取りまたは切り取りされる場合があります。 共有ビデオがフリーズしたりピクセル化したり、完全に失敗したりすることがあります。 これは、ネットワークの混雑が発生し、シーケンスから抜け出す、または一切受信しない音声およびビデオ トラフィックを表す IP パケットが原因です。 この問題が発生した場合 (または最初に発生する場合は、サービスの品質 **(QoS) を使用します**。 

QoS を使用すると、遅延に依存するネットワーク トラフィック (音声ストリームやビデオ ストリームなど) に優先順位を付け、機密性の低いトラフィックの前で (新しいアプリをダウンロードする場合など)、(ダウンロードする余分な秒が大した問題ではない) トラフィックの前で "ラインでカット" することを許可します。 QoS は、Windows グループ ポリシー オブジェクトとポートベースのアクセス制御リストと呼ばれるルーティング機能を使用して、すべてのパケットをリアルタイム ストリームで識別してマークします。この機能は、音声、ビデオ、および画面共有に独自の専用ネットワーク帯域幅を提供するようにネットワークに指示します。

理想的には、Teams を展開する準備をしながら内部ネットワークに QoS を実装しますが、いつでも実行できます。 十分に小さい場合は、QoS は必要ない可能性があります。

準備ができたら、「Microsoft Teams でサービス [の品質 (QoS) を実装する」を参照してください](QoS-in-Teams.md)。

QoS を使用して会議トラフィックを管理するには、「Teams 会議のリアルタイム メディア トラフィックを処理する方法を設定する [」を参照してください](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。


## <a name="related-topics"></a>関連トピック

[通話分析を設定する](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[CQD をセットアップする](turning-on-and-using-call-quality-dashboard.md)

[Teams で通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)