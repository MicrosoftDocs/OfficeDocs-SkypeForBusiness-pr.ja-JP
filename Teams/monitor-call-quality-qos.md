---
title: Microsoft Teams の通話品質を監視および向上させる
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: '[QoS (Quality of Service)] の設定を使用して、Microsoft Teams で分析と通話品質ダッシュボードを呼び出します。'
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085944"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Microsoft Teams の通話品質を監視および向上させる

この記事では、Microsoft Teams の通話品質を監視、トラブルシューティング、管理、向上させるために使用できる3つの主要ツールについて説明します。 

- **通話品質ダッシュボード (CQD)**: 組織全体の傾向や問題を分析して、パフォーマンスを向上させる

- **通話分析**: 個々のユーザーの通話と会議の品質を分析する

- **QoS (Quality Of Service)**: 重要なネットワークトラフィックの優先順位付け



## <a name="monitor-and-troubleshoot-call-quality"></a>通話品質の監視とトラブルシューティング
ユーザーごとの**通話分析**と**通話品質ダッシュボード**を使用して、進行中の操作中に発生する可能性のある通話品質の問題を検出し、トラブルシューティングします。 これにより、ネットワーク全体のパフォーマンスを向上させることができます。 これらのツールはどちらも Teams 管理センターにあります。

 - [**通話分析**] には、チーム内の各ユーザーの特定の***通話と会議***に関連するデバイス、ネットワーク、接続に関する詳細情報が表示されます。 チーム管理者およびヘルプデスク担当者はこの情報を使って、特定の通話での通話品質と接続の問題のトラブルシューティングを行います。 詳細については、「通話[分析を設定](set-up-call-analytics.md)する」および「[通話分析を使用して通話品質の低下を解決する」を](use-call-analytics-to-troubleshoot-poor-call-quality.md)参照してください。
 
 - **通話品質ダッシュボード (CQD)** を使用すると、組織全体の通話品質を***ネットワーク全体で確認***できます。 CQD 情報を使用して、問題の特定と解決に役立ちます。 まず、 [CQD を設定](turning-on-and-using-call-quality-dashboard.md)します。 次に、「 [Teams で通話と会議の品質を管理する」](quality-of-experience-review-guide.md)を参照してください。

 通話分析と CQD は並列で実行され、個別に、または一緒に使うことができます。 たとえば、通信サポート担当者が、ユーザーの通話の問題のトラブルシューティングにさらに詳しいヘルプが必要であると判断した場合は、通話に関する追加情報にアクセスできる通信サポートエンジニアに通話がエスカレートされます。 さらに、通信サポートエンジニアが、通話分析で検出されたサイト関連の問題についてネットワークエンジニアに警告します。 ネットワークエンジニアは、CQD をチェックして、サイトに関連する全体的な問題がユーザーの通話の問題の原因になっている可能性があるかどうかを確認します。


## <a name="prioritize-important-network-traffic-using-qos"></a>QoS を使用して重要なネットワークトラフィックの優先順位を付ける
ユーザーが通話と会議に Teams の使用を開始すると、発信者の声が出たり、通話や会議の途中で切断されたりする場合があります。 共有ビデオは、フリーズまたは pixelate、または完全に失敗することがあります。 これは、ネットワークの輻輳を示す音声とビデオのトラフィックを示す IP パケットによって、順番が正しく表示されない、またはまったく表示されないためです。 この問題が発生した場合は (または最初の場所で行われないようにするために)、 **Quality Of Service (QoS)** を使用します。 

QoS では、遅延が発生する可能性のあるネットワークトラフィック (音声やビデオのストリームなど) の優先順位を付けて、機密性の低いトラフィック (たとえば、新しいアプリをダウンロードして、もう1つ目のダウンロードがあまり重要でない場合) に優先順位を付けることができます。 QoS では、Windows のグループポリシーオブジェクトと、ポートベースのアクセス制御リストと呼ばれるルーティング機能を使用して、リアルタイムストリーム内のすべてのパケットを識別してマークします。これは、ネットワークに対して、独自の専用ネットワーク帯域幅で音声、ビデオ、画面を共有するように指示します。

理想的には、社内ネットワークに QoS を実装して、Teams をロールアウトする準備をしていますが、いつでも行うことができます。 容量が十分でない場合は、QoS を必要としない可能性があります。

準備ができたら、「 [Microsoft Teams でサービスの品質 (QoS) を実装する (QoS)」](QoS-in-Teams.md)を参照してください。

QoS を使って会議トラフィックを管理するには、「 [Teams 会議のリアルタイムメディアトラフィックを処理する方法を設定](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)する」を参照してください。


## <a name="related-topics"></a>関連項目

[通話分析を設定する](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[CQD を設定する](turning-on-and-using-call-quality-dashboard.md)

[Teams で通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[チームのトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

