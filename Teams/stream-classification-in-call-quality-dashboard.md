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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: ストリーム品質がMicrosoft TeamsとSkype for Business Onlineの通話品質ダッシュボードでどのように分類されているかをご覧ください。
ms.openlocfilehash: 6ed59111eea2c14da321cf1467b021980a223ec0
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328333"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>通話品質ダッシュボードでのストリーム分類

Microsoft Teams と Skype for Business Online の通話品質ダッシュボード (CQD) を使用すると、Microsoft Teams と Skype for business のサービスを使って発信した通話の品質を把握することができます。 このトピックでは、メディアストリームの品質分類に関する詳細情報を提供します。 CQD の詳細と有効にする方法については、「[通話品質ダッシュボードをオンにして使用](turning-on-and-using-call-quality-dashboard.md)する」を参照してください。

## <a name="classifier-definitions"></a>分類子の定義

CQD のストリームは、利用可能な主要品質指標の値に基づいて_良好_、_低_品質、または_未分類_として分類されます。 ストリームを分類するために使用されるメトリックと条件は、次の表に示しています。 CQD の "ディメンションに基づく低品質" ディメンションは、_不適切_な分類の対象となるメトリックを理解するために使用できます。 これらの寸法の詳細については、「[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)」を参照してください。

### <a name="audio-classifier"></a>オーディオクラシファイアー

次の条件の1つ以上が満たされている場合、オーディオストリームは_低品質_とマークされます。

|指標|状態|解説|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1.0|ネットワーク平均オピニオン値によるストリームの平均低下値。 受信した音声の品質に影響を与えるネットワーク損失とジッタの量。|
|Round Trip|500 ミリ秒より長い|平均ラウンドトリップネットワーク伝播時間 (ミリ秒単位)。 [RFC3550](https://tools.ietf.org/html/rfc3550)で利用可能な詳細情報。|
|Packet Loss Rate|> 0.1|ストリームの平均のパケット損失率。|
|ジッター|> 30|ミリ秒単位のストリームの平均ジッター。|
|Ratio Concealed Samples Avg|> 0.07|パケット損失の回復によって生成された、オーディオフレームの合計数に対する、非表示のサンプルを含むオーディオフレームの平均比率。|
||||

### <a name="video-classifier"></a>ビデオ クラシファイアー

ビデオストリームは、最初に利用可能なメトリックの値に基づいて、次の順序で_正常_または_低品質_としてマークされます。

|手順 #|指標|状態 |条件が真である場合の分類 |条件が偽の場合の分類 |メトリックが利用できない場合の分類 |解説 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|手順 2 に進んでください|ユーザーに対する表示でのビデオ フレームの損失の平均割合。 平均には、ネットワークの損失から回復したフレームが含まれます。|
|2|Video Frame Rate Avg|<7|_Poor_|_Good_|手順 3 に進んでください|セッションのデュレーションにわたり算出された、ビデオ ストリームで受信した秒あたりの平均フレーム数。|
|3|Video Post FECPLR|> 0.15|_Poor_|_Good_|_Unclassified_|FEC がすべてのビデオストリームとコーデックで集計された後のパケット損失率。|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS 分類子

VBSS ストリームは、最初に利用可能なメトリックの値に基づいて、次の順序で_有効または__不適切_としてマークされます。

|手順 # |指標 |状態 |条件が真である場合の分類 |条件が偽の場合の分類 |メトリックが利用できない場合の分類 |解説 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|手順 2 に進んでください|ユーザーに対する表示でのビデオ フレームの損失の平均割合。 平均には、ネットワークの損失から回復したフレームが含まれます。|
|2|Video Frame Rate Avg|<2|_Poor_|_Good_|手順 3 に進んでください|セッションのデュレーションにわたり算出された、ビデオ ストリームで受信した秒あたりの平均フレーム数。|
|3|Video Post FECPLR|> 0.15|_Poor_|_Good_|_Unclassified_|FEC がすべてのビデオストリームとコーデックで集計された後のパケット損失率。|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>アプリケーション共有分類子

アプリケーション共有ストリームは、次の条件の1つ以上が満たされている場合は、_低品質_としてマークされます。

| 指標     | 状態 | 解説 |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | リモートピアに送信されるのではなく、破棄されたタイルのパーセンテージ (MCU からビューアーへなど)。 クライアントとサーバーの間の帯域幅の制限が原因で、破棄された (または損失) タイルが表示される場合があります。 |
| AppSharing RDP Tile Processing Latency Average | > 400 | 電話会議サーバーでの RDP スタック上のタイル処理の平均遅延 (ミリ秒単位)。 |
| AppSharing Relative OneWay Average | > 1.75 | アプリケーション共有ストリームのエンドポイント間の1方向の平均相対的な遅延 (秒単位)。 |
| | | |

## <a name="unclassified-streams"></a>未分類ストリーム

CQD では、対話型接続の確立 (ICE) 接続に失敗した場合、またはストリームの分類の計算に必要なすべてのメトリックが報告されない場合、ストリームは_未分類_とマークされます。

ICE接続障害をチェックするには、 "FAILED"値の "First Connectivity Ice"と "Second Connectivity Ice"のディメンションを調べます。 いずれかの値がエラーを示している場合、ストリームは_未分類_としてマークされます。

_未分類_のストリームの ICE 接続に成功した場合、キーストリームのメトリックが報告されなかったため、ストリームは_未分類_と見なされる可能性が高くなります。 これらの指標が報告されない理由はいくつかあります。

- **Qoe レポートは受信されませんでした**。分類に使用されるメトリックは、通話の終了時に送信される qoe レポートで報告されます。 このレポートが生成されない場合 (たとえば、一部のサードパーティ製エンドポイントが QoE を送信しなかった可能性があります)、または送信できなかった場合 (たとえば、ネットワークの停止のため)、CQD はストリームを分類することができません。

> [!TIP]
> 「QoE Record Available」ディメンションを使用して、QoEレポートがストリームに対して受信されたかどうかを判断できます。 いずれかのエンドポイントからQoEレポートを受信した場合、このディメンションの値は「True」になります。 最も正確な測定基準の報告には、両方のエンドポイントからのQoEレポートが必要です。

- **短い通話**-短い通話には、キーストリームの測定値を計算するための十分なメディアアクティビティがない場合があります。 これらのメトリックがなければ、CQDはストリームを分類できません。

> [!TIP]
> 「期間（秒）」、「期間（分）」、「期間5秒以下」、および「期間60秒以上」のディメンションは、ストリームの期間を決定するために使用できます。 測定値「平均通話時間」を使用して、一連のストリームの平均所要時間を計算することもできます。

- **低パケット使用率**(「短い通話」のシナリオなど) には、キーストリームメトリックの計算に十分なパケット使用量が必要です。 これらのメトリックがなければ、CQDはストリームを分類できません。
  - 一般的な低パケット使用率のシナリオは、出席者が会議に参加して発表者を聞き、話すことができない場合に発生します (ほとんどの通話では、マイクがミュートになっています)。 ここでは、クライアントに対して受信するオーディオストリームの使用率が高く、クライアントから送信されるオーディオストリームのパケット使用率が低い場合。 ストリームの継続時間は1時間以上であっても、クライアントからサーバーへのストリームのパケット使用率は、マイクがミュートになっているために、_未分類_のストリームの結果となっています。

> [!TIP]
> 「パケット使用率」ディメンションおよび「平均パケット使用率」測定値を使用して、ストリームのパケットアクティビティを判断できます。

## <a name="related-topics"></a>関連項目

[通話品質ダッシュボード (CQD) をオンにして使用する](turning-on-and-using-call-quality-dashboard.md)

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)
