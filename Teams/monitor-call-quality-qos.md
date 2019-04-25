---
title: Microsoft Teams で QoS を実施し、通話分析を監視する
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jambirk
description: マイクロソフトのチームでは、サービスの品質 (QoS) 設定を呼び出して分析し、品質のダッシュ ボードを呼び出すを使用します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77730db17e900951f0fe1a60b7c0ae2ccdbfbc5b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32228424"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>マイクロソフトのチームで QoS と通話品質の監視を実装します。

## <a name="get-started"></a>開始します。

ユーザーでは、呼び出しを実行すると、会議を保持しているチームを使用を開始するように分割することまたは呼び出しとの間で切る、または会議の呼び出し元の音声が発生した可能性があります。 共有ビデオがフリーズまたはモザイク、全体が失敗するか。 IP パケットを音声とビデオのトラフィックがネットワークの輻輳が発生して、順序に関係なく、あるいはまったくの到着を表すためです。 表面化し、リターンでは、主にサービスの品質 (QoS) を防ぐためにこれらの問題を識別する方法もあります。

カット ラインでは、(場所をダウンロードするのには追加の 2 番目に、新しいアプリケーションをダウンロードするなど重要度の低いトラフィックの前にするにはネットワークの遅延に敏感である (音声またはビデオのストリーム) のようなリアルタイムのネットワーク トラフィックを許可する方法は、**サービスの品質 (QoS)** 大きな問題はありません)。 ポート ベースのアクセス制御リスト、音声、ビデオ、および画面共有を提供するネットワークを利用すると呼ばれるルーティング機能の独自の専用部分のストリームと QoS を識別し、Windows グループ ポリシー オブジェクトを使用してリアルタイムのストリーム内のすべてのパケットをマークネットワークの帯域幅です。

 こことだけ言っておきますである多くの mail を使用して文字を送信するように: 送信する、本レートが届いてすぐと取得がはるかに速く、最初のクラスを送信する場合、および優先度のメールを送信する場合に十分であります。、2 日以内に到達します。 ネットワークがコースのメールよりも高速に実行しますが、それはそのまま実行速度が一部のアプリケーションにとって重要で、他のユーザーのために重要ではない場合は true。 このトピックは、本質的に詳細な最初は、理解するのには注意が必要ですが発生するので、ユーザーに大きな違いは、時間とエネルギーをあらかじめへの投資価値があります。 については詳細な[実装のサービス品質 (QoS) では、マイクロソフトのチーム](QoS-in-Teams.md)を参照してください。

チームは、セットアップ中に内部ネットワークの QoS を実装する理想的ですが、小さい場合は、十分なことができますオプション。 これにより、遅延に依存した音声とビデオのトラフィックを他のトラフィックよりも優先順位を取得します。 ネットワークですべての[クライアント デバイス](QoS-in-Teams-clients.md)スイッチとルーターだけでなく、[マイクロソフトのチーム管理センター](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)ではこの優先順位付けの操作とします。

検索し、実行中の操作で発生する問題のトラブルシューティングを行うには、[**分析機能の呼び出しと呼び出し品質のダッシュ ボード**](difference-between-call-analytics-and-call-quality-dashboard.md)が使用されます。  

**分析機能を呼び出す**には、デバイス、ネットワーク、およびに関連する***特定の通話や会議***ユーザーごとに、マイクロソフトのチームまたは Skype ビジネス アカウントの接続に関する詳細情報が表示されます。 Office 365 管理者の場合、特定の呼び出しで発生した通話品質と接続の問題をトラブルシューティングする分析機能の呼び出しを使用できます。 識別し、問題を解決することができます。

**呼び出し品質ダッシュ ボード (救難)** は、管理者を支援するように設計されていて、ネットワーク エンジニア、***ネットワーク***を最適化、解析されず、1 回の呼び出しのトラブルシューティングを行います。 救難は、組織全体の集計情報を確認するのには特定のユーザーからフォーカスを移動します。 これは、こともできますを特定して問題を解決します。

## <a name="related-topics"></a>関連項目

[マイクロソフトのチームでのサービス品質 (QoS) を実装します。](QoS-in-Teams.md)

[ビデオ: 通話品質の概要](https://aka.ms/teams-quality)

[通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話品質ダッシュボードをオンにして使用する](turning-on-and-using-call-quality-dashboard.md)

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質ダッシュボードでのストリームの分類](stream-classification-in-call-quality-dashboard.md)