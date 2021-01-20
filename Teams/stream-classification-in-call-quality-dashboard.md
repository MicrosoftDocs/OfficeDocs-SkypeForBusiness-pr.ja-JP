---
title: 通話品質ダッシュボード (CQD) でのストリームの分類
ms.author: serdars
author: lolaj
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Microsoft Teams および Skype for Business Online の通話品質ダッシュボード (CQD) で、ストリーム品質がどのように分類されるのかについて説明します。
ms.openlocfilehash: 400dcd953805595b4457b4ca9443c31b66f7425d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909041"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>通話品質ダッシュボード (CQD) でのストリームの分類

Microsoft Teams および Skype for Business Online の通話品質ダッシュボード (CQD) を使用すると、Microsoft Teams および Skype for Business サービスを使用して行われた通話の品質に関する洞察を得ることができます。 このトピックでは、メディアストリームの品質分類に関する詳細情報を提供します。 CQD の詳細と設定方法については、「通話品質ダッシュボードを設定する」 [を参照してください](turning-on-and-using-call-quality-dashboard.md)。

## <a name="classifier-definitions"></a>分類子の定義

CQD のストリームは、利用可能な主要品質指標の値に基づいて、良好、低品質、または未分類として分類されます。  ストリームの分類に使用されるメトリックと条件は、次のテーブルに表示されます。 CQD の "Poor Due To" ディメンションを使用して、低品質の分類の原因であるメトリックを _把握_ できます。 これらのディメンションの詳細については、「通話品質ダッシュボードで利用できるディメンションと [メジャー」を参照してください](dimensions-and-measures-available-in-call-quality-dashboard.md)。

### <a name="audio-classifier"></a>オーディオクラシファイアー

次の条件の 1 つ以上が満たされた場合、オーディオ ストリームは低品質としてマーク _されます_。

|測定基準|シナリオ|状態|説明|
|:-----|:-----|:-----|:-----|
|Audio Degradation Avg|ペイロードの説明は、DESCRIPTION ではありません|> 1.0|ネットワーク平均オピニオン値によるストリームの平均低下値。 受信音声の品質に影響を与えたネットワーク損失とジッターの量。|
|Round Trip|すべての|500 ミリ秒より長い|ミリ秒単位で計算された、平均ラウンドトリップ ネットワーク伝達時間。 [RFC3550 で利用可能な詳細](https://tools.ietf.org/html/rfc3550)。|
|Packet Loss Rate|すべての|> 0.1|ストリームの平均のパケット損失率。|
|ジッター|すべての|> 30|ミリ秒単位のストリームの平均ジッター。|
|Ratio Concealed Samples Avg|ペイロードの説明は、|> 0.07|オーディオ フレームの総数に対するパケット損失によって生成された隠しサンプルを含むオーディオ フレーム数の平均比率。|
||||

### <a name="video-classifier-due-to-freeze"></a>固定が原因のビデオ分類子

ビデオ ストリームは、_エンド_ ユーザーが固定ビデオを体験したと推定するために生成された分類子スコアの値に基づいて、良好または低品質とマークされます。 この分類子は、Microsoft Teams 製品でのみ使用できます。

|手順 #|測定基準|シナリオ|状態 |条件が真である場合の分類 |条件が偽の場合の分類 |メトリックが利用できない場合の分類 |説明 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Server|>0.246|_Poor_|_Good_|_Unclassified_|ユーザー エクスペリエンスの組み合わせに基づいて生成される 0 から 1 のスコア、期間の統計情報の固定、全体的な通話エクスペリエンス |
|2|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Client|>0.524|_Poor_|_Good_|_Unclassified_|ユーザー エクスペリエンスの組み合わせ、期間統計情報の固定、全体的な通話エクスペリエンスに基づいて生成される 0 から 1 のスコア |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>ビデオ クラシファイアー
ビデオ ストリームは、次の順序で最初に利用可能なメトリックの値に基づいて、良好または低品質としてマークされます。

|手順 #|測定基準|状態 |条件が真である場合の分類 |条件が偽の場合の分類 |メトリックが利用できない場合の分類 |説明 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|手順 2 に進んでください|ユーザーに対する表示でのビデオ フレームの損失の平均割合。 平均には、ネットワーク損失から回復したフレームが含まれます。|
|2|Video Frame Rate Avg|<7|_Poor_|_Good_|手順 3 に進んでください|セッションのデュレーションにわたり算出された、ビデオ ストリームで受信した秒あたりの平均フレーム数。|
|3|Video Post FECPLR|> 0.15|_Poor_|_Good_|_Unclassified_|FEC が適用された後のパケット損失率は、すべてのビデオ ストリームとコーデックで集約されます。|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS 分類子

VBSS ストリームは、次の順序で最初に利用可能なメトリックの値に基づいて、良好または低品質としてマークされます。

|手順 # |測定基準 |状態 |条件が真である場合の分類 |条件が偽の場合の分類 |メトリックが利用できない場合の分類 |説明 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|手順 2 に進んでください|ユーザーに対する表示でのビデオ フレームの損失の平均割合。 平均には、ネットワーク損失から回復したフレームが含まれます。|
|2|Video Frame Rate Avg|<2|_Poor_|_Good_|手順 3 に進んでください|セッションのデュレーションにわたり算出された、ビデオ ストリームで受信した秒あたりの平均フレーム数。|
|3|Video Post FECPLR|> 0.15|_Poor_|_Good_|_Unclassified_|FEC が適用された後のパケット損失率は、すべてのビデオ ストリームとコーデックで集約されます。|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>アプリケーション共有分類子

次の条件の 1 _つ以上が_ 満たされた場合、アプリケーション共有ストリームは低品質としてマークされます。

| 測定基準     | 状態 | 説明 |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | (MCU からビューアーへなど) リモート ピアに送信される代わりに破棄されるタイルのパーセンテージ。 破棄 (または破損) タイルは、クライアントとサーバー間の帯域幅制限が原因である可能性があります。 |
| AppSharing RDP Tile Processing Latency Average | > 400 | 電話会議サーバーでの RDP スタック上のタイル処理の平均遅延 (ミリ秒単位)。 |
| AppSharing Relative OneWay Average | > 1.75 | アプリケーション共有ストリームのエンドポイント間の相対的な一方的な遅延の平均 (秒)。 |
| | | |

## <a name="unclassified-streams"></a>未分類ストリーム

CQD では、対話型接続確立(ICE) 接続が失敗したとき、またはストリームの分類を計算するために必要なすべてのメトリックが報告されない場合、ストリームは [未分類] とマークされます。

ICE接続障害をチェックするには、 "FAILED"値の "First Connectivity Ice"と "Second Connectivity Ice"のディメンションを調べます。 いずれかの値が失敗を示す場合、ストリームは [未分類] _としてマークされます_。

未分類ストリームで ICE 接続が成功した場合、主要なストリームメトリックが報告されていないので、ストリームは未分類と見なされる可能性があります。 これらの指標が報告されない理由はいくつかあります。

- **QoE レポートは受信されません。** 分類に使用されるメトリックは、通話の最後に送信される QoE レポートで報告されます。 このレポートが生成されない場合 (たとえば、一部のサード パーティのエンドポイントは QoE を送信できない可能性がある)、または送信できなかった場合 (ネットワークの停止など)、CQD はストリームを分類できません。

  > [!TIP]
  > 「QoE Record Available」ディメンションを使用して、QoEレポートがストリームに対して受信されたかどうかを判断できます。 いずれかのエンドポイントからQoEレポートを受信した場合、このディメンションの値は「True」になります。 最も正確な測定基準の報告には、両方のエンドポイントからのQoEレポートが必要です。

- **短い通話** : 短い通話では、キー ストリームのメトリックを計算するのに十分なメディア アクティビティが不足している可能性があります。 これらのメトリックがなければ、CQDはストリームを分類できません。

  > [!TIP]
  > 「期間（秒）」、「期間（分）」、「期間5秒以下」、および「期間60秒以上」のディメンションは、ストリームの期間を決定するために使用できます。 測定値「平均通話時間」を使用して、一連のストリームの平均所要時間を計算することもできます。

- **パケット使用率が低** い —"短い通話" シナリオと同様に、主要なストリーム メトリックの計算には十分なパケット使用率が必要です。 これらのメトリックがなければ、CQDはストリームを分類できません。
  - 一般的な低パケット使用率のシナリオは、出席者が発表者の話を聞くために会議に参加し、話さない場合に発生します (ほとんどの通話ではマイクがミュートされています)。 ここで、クライアントに受信するオーディオ ストリームのパケット使用率は高く、クライアントから送信されるオーディオ ストリームのパケット使用率はほとんどまたは全く発生します。 ストリームのデュレーションは 1 時間以上になる場合がありますが、マイクがミュートされ、ストリームの結果が未分類になった場合、クライアントからサーバーへのストリームのパケット使用率は低くなります。

  > [!TIP]
  > 「パケット使用率」ディメンションおよび「平均パケット使用率」測定値を使用して、ストリームのパケットアクティビティを判断できます。

## <a name="related-topics"></a>関連項目
[Teams の通話品質の向上と監視](monitor-call-quality-qos.md)

[CQD とは](CQD-what-is-call-quality-dashboard.md)

[通話品質ダッシュボード (CQD) を設定する](turning-on-and-using-call-quality-dashboard.md)

[テナントと建物のデータをアップロードする](CQD-upload-tenant-building-data.md)

[CQD データとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で使用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)
