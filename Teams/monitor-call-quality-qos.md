---
title: Microsoft Teams で QoS を実施し、通話分析を監視する
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jambirk
description: マイクロソフトのチームでは、サービスの品質 (QoS) 設定を呼び出して分析し、品質のダッシュ ボードを呼び出すを使用します。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 505409ac51552a99fabc4eb41801a1f19a737877
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742951"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>マイクロソフトのチームで QoS と通話品質の監視を実装します。

## <a name="get-started"></a>開始します。

ユーザーでは、呼び出しを実行すると、会議を保持しているチームを使用を開始するに気付く場合がありますスピーカー点の ups または会議との間で切るか。 共有ビデオがフリーズまたは pixellate、または完全に失敗します。 IP パケットを音声とビデオのトラフィックがネットワークの輻輳が発生して、順序に関係なく、あるいはまったくの到着を表すためです。 これを防止し、それらが表面化、主にサービスの品質 (QoS) とは、他の問題を特定する方法もあります。

[**サービスの品質 (QoS)**](monitor-call-quality-qos.md)は、パケットの遅延や輻輳、影響を特定し、はるかに少ない輻輳が発生したために優先的な処置を持つパケットを提供する方法です。 こことだけ言っておきますである多くの Mail を使用して文字を送信するように: 送信する、本レートが届いてすぐと取得がはるかに速く、最初のクラスを送信する場合、および優先度のメールを送信する場合に十分であります。、2 日以内に到達します。 ネットワークがコースのメールよりも高速に実行しますが、それはそのまま実行速度が一部のアプリケーションにとって重要で、他のユーザーのために重要ではない場合は true。 このトピックは、本質的に詳細な最初は、理解するのには注意が必要ですが発生するので、ユーザーに大きな違いは、時間とエネルギーをあらかじめへの投資価値があります。

チームは、セットアップ中に内部ネットワークの QoS を実装する理想的ですが、小さい場合は、十分なことができますオプション。 これにより、遅延に依存した音声とビデオのトラフィックを他のトラフィックよりも優先順位を取得します。 ネットワーク内およびスイッチとルーターで、すべてのクライアント デバイスでは、この優先順位付けを行うと。

検索し、実行中の操作で発生する問題のトラブルシューティングを行うには、[**分析機能の呼び出しと呼び出し品質のダッシュ ボード**](difference-between-call-analytics-and-call-quality-dashboard.md)が使用されます。  

分析機能の呼び出しは、デバイス、ネットワーク、および特定のコールとビジネス アカウントに、マイクロソフトのチームまたは Skype では、各ユーザーが会議に関連する接続に関する詳細情報を示しています。 Office 365 管理者の場合、特定の呼び出しで発生した通話品質と接続の問題をトラブルシューティングする分析機能の呼び出しを使用できます。 識別し、問題を解決することができます。

通話品質ダッシュ ボード (救難) は、管理者を支援するように設計されていますおよびネットワーク ・ エンジニアの**ネットワーク**を最適化、分析されず、1 回の呼び出しのトラブルシューティングを行います。 救難は、組織全体の集計情報を確認するのには特定のユーザーからフォーカスを移動します。 これは、こともできますを特定して問題を解決します。

## <a name="related-topics"></a>関連トピック

[ビデオ: 通話品質の概要](https://aka.ms/teams-quality)

[分析機能の呼び出しを設定します](set-up-call-analytics.md)

[通話分析を使用して低い通話品質をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[有効にして、品質のダッシュ ボードの呼び出しを使用します。](turning-on-and-using-call-quality-dashboard.md)

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質ダッシュボードでのストリーム分類](stream-classification-in-call-quality-dashboard.md)