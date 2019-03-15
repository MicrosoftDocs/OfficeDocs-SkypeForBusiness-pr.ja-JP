---
title: 通話品質ダッシュボードでのストリーム分類
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: ストリーム品質がMicrosoft TeamsとSkype for Business Onlineの通話品質ダッシュボードでどのように分類されているかをご覧ください。
ms.openlocfilehash: b3b63ff8ac89ed0ad1d88893913fa89af769e078
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641035"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>通話品質ダッシュボードでのストリーム分類

The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to enable it, see [Turning on and using Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>分類子の定義

Streams in CQD are classified as good, poor, or unclassified based on the values of the available key quality metrics. The metrics and conditions used to classify stream are shown in the tables below. CQD's "Poor Due To" dimensions can be used to understand which metric is responsible for a poor classification. See [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for more information on these dimensions.

### <a name="audio-classifier"></a>オーディオクラシファイアー

次の条件の1つ以上が満たされている場合、オーディオストリームは不良とマークされます。

|**指標**|**状態**|**解説**|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1.0|Average Network Mean Opinion Score degradation for stream. Represents how much the network loss and jitter has impacted the quality of received audio.|
|Round Trip|500 ミリ秒より長い|RFC3550 での規定に従って計算されたミリ秒単位の平均ネットワーク伝達ラウンド トリップ時間。|
|Packet Loss Rate|> 0.1|ストリームの平均のパケット損失率。|
|ジッター|> 30|ミリ秒単位のストリームの平均ジッター。|
|Ratio Concealed Samples Avg|> 0.07|パケット損失のオーディオ フレームの合計数を治療によって生成される非表示の文字列のサンプルでのオーディオ フレームの数の平均の比率です。|

### <a name="video-classifier"></a>ビデオ クラシファイアー

ビデオストリームは、使用可能な最初のメトリックの値に基づいて、次の順序で良好または不良としてマークされます。

|**手順 #**|**指標**|**状態**|**条件が真である場合の分類**|**条件が偽の場合の分類**|**メトリックが利用できない場合の分類**|**解説**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|_gt 50% |Poor|Good|手順 2 に進んでください|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|<7|Poor|Good|手順 3 に進んでください|セッションのデュレーションにわたり算出された、ビデオ ストリームで受信した秒あたりの平均フレーム数。|
|3|Video Post FECPLR|> 0.15|Poor|Good|Unclassified|FEC を適用した後のパケット損失の割合は、すべてのビデオ ストリームとコーデックの間で集計。|

### <a name="vbss-classifier"></a>VBSS 分類子

VBSS ストリームは、使用可能な最初のメトリックの値に基づいて、次の順序で良好または不良としてマークされます。

|**手順 #**|**指標**|**状態**|**条件が真である場合の分類**|**条件が偽の場合の分類**|**メトリックが利用できない場合の分類**|**解説**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|_gt 50% |Poor|Good|手順 2 に進んでください|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|<2|Poor|Good|手順 3 に進んでください|セッションのデュレーションにわたり算出された、ビデオ ストリームで受信した秒あたりの平均フレーム数。|
|3|Video Post FECPLR|> 0.15|Poor|Good|Unclassified|FEC を適用した後のパケット損失の割合は、すべてのビデオ ストリームとコーデックの間で集計。|

### <a name="application-sharing-classifier"></a>アプリケーション共有分類子

次の条件の1つ以上が満たされている場合、オーディオストリームは不良とマークされます。


| **指標**                                     | **状態** | **解説**                                                                                                                                                                                                        |
|:-----------------------------------------------|:--------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Spoiled Tile Percent Total                     | > 36          | Percentage of tiles that are discarded instead of being sent to a remote peer (for example, from the MCU to a viewer). Discarded (or spoiled) tiles may be caused by bandwidth restrictions between client and server. |
| AppSharing RDP Tile Processing Latency Average | _gt 400         | 電話会議サーバーでの RDP スタック上のタイル処理の平均遅延 (ミリ秒単位)。                                                                                                                          |
| AppSharing Relative OneWay Average             | > 1.75        | 平均相対的な一方向の遅延 (秒) のストリームを共有するアプリケーションのエンドポイントとの間です。                                                                                                                       |

## <a name="unclassified-streams"></a>未分類ストリーム

CQDでは、ICE接続が失敗した場合、またはストリーム分類を計算するために必要なすべてのメトリックが報告されていない場合、ストリームは分類されていないとマークされます。

To check for ICE connectivity failures, examine the dimensions "First Connectivity Ice" and "Second Connectivity Ice" for a "FAILED" value. If either value indicates a failure, the stream will be marked as unclassified.

If ICE connectivity succeeded for an unclassified stream, the stream is likely considered unclassified because key stream metrics were not reported. There are a few reasons these metrics may not be reported:

- **QoE reports were not received** - The metrics used for classification are reported in a QoE report sent at the end of a call. If this report is not produced (e.g., because some third-party endpoints may not send QoE) or was not able to be sent (e.g., because of a network outage), CQD is unable to classify the stream.

> [!TIP]
> The "QoE Record Available" dimension can be used to determine whether a QoE report was received for a stream. Note that this dimension will have a value of "True" if a QoE report was received from either endpoint. A QoE report from both endpoints is required for the most accurate reporting of metrics.

- **Short calls** - Short calls may not have enough media activity to compute key stream metrics. Without these metrics, CQD is unable to classify the stream.

> [!TIP]
> The dimensions "Duration (Seconds)", "Duration (Minutes)", "Duration 5 seconds or less", and "Duration 60 seconds or more" can be used to determine the duration of a stream. The measurement "Avg Call Duration" can also be used to compute the average duration for a set of streams.

- **Low packet utilization** - Like the "short call" scenario, sufficient packet utilization is required for computation of key stream metrics. Without these metrics, CQD is unable to classify the stream.
    - A common low packet utilization scenario occurs when a user joins a meeting to listen to the presenter but never speaks (likely muting the microphone for most of the call). In such a scenario, one audio stream will have high packet utilization (inbound to the client) while the other will have little to no packet utilization (outbound from the client). In this scenario, the duration of the stream may be an hour or longer but the packet utilization on the stream from the client to the server will be extremely low due to the microphone being muted, resulting in an unclassified stream.

> [!TIP]
> 「パケット使用率」ディメンションおよび「平均パケット使用率」測定値を使用して、ストリームのパケットアクティビティを判断できます。


## <a name="related-topics"></a>関連トピック
[有効にして、呼び出し品質ダッシュ ボード (救難) を使用します。](turning-on-and-using-call-quality-dashboard.md)

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)
