---
title: Microsoft Teams で QoS を実施し、通話分析を監視する
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: jambirk
description: '[QoS (Quality of Service)] の設定を使用して、Microsoft Teams で分析と通話品質ダッシュボードを呼び出します。'
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 70e862adf2aad795a9ef1ab34eaa2de21240a388
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239255"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Microsoft Teams で QoS を実装して通話品質を監視する

## <a name="get-started"></a>はじめに

ユーザーが Teams を使って電話をかけたり会議を開催したりするときに、発信者の声が出たり、通話または会議を chopping したりする場合があります。 共有ビデオは、フリーズまたは pixelate、または完全に失敗することがあります。 これは、ネットワークの輻輳を示す音声とビデオのトラフィックを示す IP パケットによって、順番が正しく表示されない、またはまったく表示されないためです。 このような問題を特定するには、主にサービス品質 (QoS) の利益を防ぐための方法があります。

**QoS (Quality Of Service** ) は、ネットワークの遅延に敏感なトラフィック (音声やビデオストリームなど) を使用して、機密性の低いトラフィック (新しいアプリをダウンロードするなど) を使用して、重要度の低いネットワークトラフィック (音声やビデオなど) を許可する方法です。たいしたことはありません)。 QoS は、Windows グループポリシーオブジェクトと、ポートベースのアクセス制御リストと呼ばれるルーティング機能を使用して、リアルタイムストリーム内のすべてのパケットを識別してマークします。これにより、ネットワークでは、音声、ビデオ、画面の共有に対して、ネットワーク帯域幅。

 ここでは、メールを使用して手紙を送信する場合と同じように、郵送料金を送信した場合は、すぐにご利用いただけます。また、初めて送信した場合は、さらに多くのことが可能になります。2日以内に取得されます。 もちろん、ネットワークはメールよりも高速で実行されますが、一部のアプリケーションでは速度が重要であり、他のユーザーにとって重要ではないこともあります。 この主題は、最初は理解しにくいものですが、ユーザーエクスペリエンスに大きな違いがあるため、時間と労力を事前に費やす価値があります。 詳細については、「 [Microsoft Teams でサービスの品質 (QoS) を実装する」](QoS-in-Teams.md)を参照してください。

理想的には、内部ネットワークで Teams をセットアップするときに、QoS を実装することをお勧めしますが、小さなサイズの場合はオプションでもかまいません。 これにより、遅延に敏感な音声とビデオのトラフィックが、他のトラフィックの優先順位を取得できます。 この優先順位付けは、 [Microsoft Teams 管理センター](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)のすべての[クライアントデバイス](QoS-in-Teams-clients.md)、およびネットワーク内のスイッチとルーターに対して行います。

[**通話分析と通話品質ダッシュボード**](difference-between-call-analytics-and-call-quality-dashboard.md)を使用して、進行中の操作中に発生する問題の検出とトラブルシューティングを行うことができます。  

[**通話分析**] には、Microsoft Teams または Skype for business アカウントの各ユーザーの***特定の通話と会議***に関連するデバイス、ネットワーク、接続に関する詳細情報が表示されます。 Office 365 管理者の場合は、通話分析を使用して、特定の通話で発生した通話品質や接続の問題のトラブルシューティングを行うことができます。 これは、問題を特定して解決するのに役立ちます。

**通話品質ダッシュボード (CQD)** は、管理者とネットワークエンジニアが1回の通話の分析とトラブルシューティングを行わずに、***ネットワーク***を最適化するために設計されています。 CQD は、特定のユーザーからフォーカスを移動して、組織全体の集計情報を確認します。 これは、問題を特定して解決するのにも役立ちます。

## <a name="related-topics"></a>関連項目

[Microsoft Teams でサービスの品質 (QoS) を実装する](QoS-in-Teams.md)

[ビデオ: 通話品質の概要](https://aka.ms/teams-quality)

[通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話品質ダッシュボードをオンにして使用する](turning-on-and-using-call-quality-dashboard.md)

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質ダッシュボードでのストリームの分類](stream-classification-in-call-quality-dashboard.md)