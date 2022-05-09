---
title: Microsoft Teams の通話品質を監視および改善する
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: サービスの品質 (QoS) 設定を使用し Microsoft Teams で通話分析と通話品質ダッシュボードを使用します。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 86c1982e358f725d8965d8b6b5c4d43a01066584
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60783175"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Microsoft Teams の通話品質を監視および改善する

この記事では、Microsoft Teams の通話品質の監視、トラブルシューティング、管理、および改善に使用できる 3 つの主要なツールについて説明します。 

- **通話品質ダッシュボード (CQD)**: 組織全体の傾向や問題を分析し、パフォーマンスの向上を促進します

- **通話分析**: 個々のユーザーの通話と会議の品質を分析します

- **サービス品質 (QoS)**: 重要なネットワーク トラフィックに優先順位を付けます



## <a name="monitor-and-troubleshoot-call-quality"></a>通話品質のモニターおよぼトラブルシューティング
ユーザーごとの **通話分析** と **通話品質ダッシュボード** を使用して、進行中の操作中に発生する通話品質の問題を見つけてトラブルシューティングします。 これにより、ネットワーク全体でパフォーマンスの向上を促進できます。 これらのツールはどちらも Teams 管理センターにあります。

 - **通話分析** では、Teams の各ユーザーの **_特定の通話と会議_** に関連するデバイス、ネットワーク、接続に関する詳細情報が表示されます。 Teams の管理者とヘルプデスク エージェントは、この情報を使用して、特定の通話での通話品質と接続の問題をトラブルシューティングします。 通話分析と通話品質の詳細については、「[通話分析を設定する](set-up-call-analytics.md)」と、「[低品質の通話をトラブルシューティングする」](use-call-analytics-to-troubleshoot-poor-call-quality.md)をご覧ください。
 
 - **通話品質ダッシュボード (CQD)** を使用すると、組織全体の通話品質の **_ネットワーク全体のビュー_** を得ることができます。 CQD 情報を使用して、問題の特定と解決に役立てましょう。 まず、[CQD](turning-on-and-using-call-quality-dashboard.md) を設定します。 次に、「[Teams で通話と会議の品質を管理する](quality-of-experience-review-guide.md)」をご覧ください。

 通話分析と CQD は並列実行しますが、個別に使用することも、同時に使用することもできます。 たとえば、コミュニケーション サポート スペシャリストが、ユーザーの通話の問題のトラブルシューティングに関してさらに支援が必要であると判断した場合、通話に関する追加情報にアクセスできるコミュニケーション サポート エンジニアに通話をエスカレートします。 これに対して、コミュニケーション サポート エンジニアは、コール分析で気付いたサイト関連の問題についてネットワーク エンジニアに警告します。 ネットワーク エンジニアは、CQD をチェックして、サイト関連の全体的な問題がユーザーの通話問題の原因である可能性があるかどうかを確認します。


## <a name="prioritize-important-network-traffic-using-qos"></a>QoS を使用して重要なネットワーク トラフィックに優先順位を付ける
ユーザーが通話や会議に Teams を使い始めると、発信者の音声が通話や会議の途中で、声が途切れを経験することもあるでしょう。 共有したビデオがフリーズしたり、ピクセル化されたり、完全に失敗したりする可能性があります。 これは、音声トラフィックとビデオ トラフィックを表す IP パケットで、ネットワークの輻輳が発生し、シーケンスどおりに到着しないか、まったく到着しないことが原因です。 これが発生した場合 (または最初に発生しないようにする場合) は、 **サービス品質 (QoS)** を使用します。 

QoS を使用すると、遅延の影響を受けやすいネットワーク トラフィック (音声やビデオ ストリームなど) に優先順位を付け、 (1 秒余分にかかることなど大した問題ではない新しいアプリのダウンロードなど) 遅延の影響を受けにくいトラフィックの前で "順番抜かし" をさせることができます。 QoS は、Windows グループ ポリシー オブジェクトと、音声、ビデオ、および画面が独自の専用ネットワーク帯域幅を共有するようにネットワークに指示するポートベースのアクセスの制御リストと呼ばれるルーティング機能を使用して、リアルタイム ストリーム内のすべてのパケットを識別してマークします。

理想的には、Teams をロールアウトする準備をしながら、内部ネットワークに QoS を実装すればいいのですが、別にいつでも行えます。小規模であれば、QoS は必要ないかもしれません。

準備ができたら、「[Microsoft Teams でサービスの品質 (QoS) を実装する](QoS-in-Teams.md)」を参照してください。

QoS を使用して会議トラフィックを管理するには、「[Teams 会議のリアルタイム メディア トラフィックの処理方法を設定する](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)」を参照してください。


## <a name="related-topics"></a>関連トピック

[通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[CQD をセットアップする](turning-on-and-using-call-quality-dashboard.md)

[Teams で通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
