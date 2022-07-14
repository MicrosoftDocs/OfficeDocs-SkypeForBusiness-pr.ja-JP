---
title: 通話品質ダッシュボード (CQD) のストリーム分類
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Microsoft Teams および Skype for Business Online の通話品質ダッシュボード (CQD) でストリーム品質を分類する方法について説明します。
ms.openlocfilehash: 9b17cf115759e96edbccdb85369ac42fd5861ff7
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794295"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>通話品質ダッシュボード (CQD) のストリーム分類

Microsoft Teams と Skype for Business Online の通話品質ダッシュボード (CQD) を使用すると、Microsoft Teams とSkype for Business サービスを使用して行われた通話の品質に関する分析情報を得ることができます。 このトピックでは、メディアストリームの品質分類に関する詳細情報を提供します。 CQD とその設定方法の詳細については、「 [通話品質ダッシュボードの設定」を](turning-on-and-using-call-quality-dashboard.md)参照してください。

## <a name="classifier-definitions"></a>分類子の定義

CQD のストリームは、使用可能なキー品質メトリックの値に基づいて、 _Good_、 _Poor_、または _Unclassified_ として分類されます。 ストリームの分類に使用されるメトリックと条件は、次の表に示されています。 CQD の "不適切な原因" ディメンションを使用すると、分類の _不十分_ なメトリックを把握できます。 これらのディメンションの詳細については、「 [通話品質ダッシュボードで使用できるディメンションとメジャー」を](dimensions-and-measures-available-in-call-quality-dashboard.md)参照してください。

### <a name="audio-classifier"></a>オーディオクラシファイアー

次の条件のうち 1 つ以上が満たされ、パケット使用率が 500 パケット>場合、オーディオ ストリームは _[不良_] とマークされます。

|測定基準|シナリオ|状態|説明|
|:-----|:-----|:-----|:-----|
|Round Trip|すべての|500 ミリ秒より長い|平均ラウンドトリップ ネットワーク伝達時間 (ミリ秒単位)。 [RFC3550](https://tools.ietf.org/html/rfc3550) で入手できる詳細。|
|Packet Loss Rate|すべての|> 0.1|ストリームの平均のパケット損失率。|
|ジッター|すべての|> 30|ミリ秒単位のストリームの平均ジッター。|
||||

### <a name="video-classifier-due-to-freeze"></a>フリーズによるビデオ分類子

ビデオ ストリームは、エンド ユーザーが Frozen Video を体験したと推定するために生成された分類子スコアの値に基づいて  _、Good_ または _Poor_ とマークされます。 この分類子は、Microsoft Teams 製品でのみ使用できます。

|手順 #|測定基準|シナリオ|状態 |条件が真である場合の分類 |条件が偽の場合の分類 |メトリックが利用できない場合の分類 |説明 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|フリーズ分類子が原因でビデオが不十分 |サーバー ペアはクライアントです: サーバー|>0.246|_Poor_|_Good_|_Unclassified_|ユーザー エクスペリエンス、凍結期間の統計情報、および全体的な通話エクスペリエンスの組み合わせに基づいて生成される 0 ~ 1 のスコア |
|2|フリーズ分類子が原因でビデオが不十分 |サーバー ペアはクライアントです: クライアント|>0.524|_Poor_|_Good_|_Unclassified_|ユーザー エクスペリエンス、凍結期間の統計情報、および全体的な通話エクスペリエンスの組み合わせに基づいて生成される 0 ~ 1 のスコア |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>ビデオ クラシファイアー
ビデオ ストリームは、次の順序で使用可能な最初のメトリックの値に基づいて _、良好_ または _低_ いとしてマークされます。

|手順 #|測定基準|状態 |条件が真である場合の分類 |条件が偽の場合の分類 |メトリックが利用できない場合の分類 |説明 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|手順 2 に進んでください|ユーザーに対する表示でのビデオ フレームの損失の平均割合。 平均には、ネットワーク損失から回復されたフレームが含まれます。|
|2|Video Frame Rate Avg|<7|_Poor_|_Good_|手順 3 に進んでください|セッションのデュレーションにわたり算出された、ビデオ ストリームで受信した秒あたりの平均フレーム数。|
|3|Video Post FECPLR|> 0.15|_Poor_|_Good_|_Unclassified_|すべてのビデオ ストリームとコーデックに対して、FEC が適用された後のパケット損失率。|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS 分類子

VBSS ストリームは、使用可能な最初のメトリックの値に基づいて、次の順序で _Good_ または _Poor_ としてマークされます。

|手順 # |測定基準 |状態 |条件が真である場合の分類 |条件が偽の場合の分類 |メトリックが利用できない場合の分類 |説明 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|コーデックが H264S ではない</br>そして</br>StreamDirection は受信です</br></br>FrameLoss > 50% の場合|_Poor_|_Good_|_Unclassified_|ユーザーに対する表示でのビデオ フレームの損失の平均割合。 平均には、ネットワーク損失から回復されたフレームが含まれます。 FrameLoss は、受信 H264S 以外のストリームの分類にのみ使用されます。|
|2|Video Frame Rate Avg|< 1|_Poor_|_Good_|_Unclassified_|セッションのデュレーションにわたり算出された、ビデオ ストリームで受信した秒あたりの平均フレーム数。 すべての送信ストリームと、H264S の StreamDirection のいずれかに適用されます。|
| |  | | | |  ||


### <a name="application-sharing-classifier"></a>アプリケーション共有分類子

アプリケーション共有ストリームは、次の条件の 1 つ以上が満たされている場合は _、低品質_ としてマークされます。

| 測定基準     | 状態 | 説明 |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | リモート ピアに送信される代わりに破棄されるタイルの割合 (MCU からビューアーなど)。 破棄された (または台無しにされた) タイルは、クライアントとサーバー間の帯域幅制限が原因である可能性があります。 |
| AppSharing RDP Tile Processing Latency Average | > 400 | 電話会議サーバーでの RDP スタック上のタイル処理の平均遅延 (ミリ秒単位)。 |
| AppSharing Relative OneWay Average | > 1.75 | アプリケーション共有ストリームのエンドポイント間の平均相対一方向遅延 (秒単位)。 |
| | | |

## <a name="unclassified-streams"></a>未分類ストリーム

CQD では、対話型接続確立 (ICE) 接続が失敗したとき、またはストリーム分類の計算に必要なすべてのメトリックが報告されない場合、ストリームは _未分類_ としてマークされます。

ICE接続障害をチェックするには、 "FAILED"値の "First Connectivity Ice"と "Second Connectivity Ice"のディメンションを調べます。 どちらかの値がエラーを示す場合、ストリームは _未分類_ としてマークされます。

_未分類_ ストリームに対して ICE 接続が成功した場合、キー ストリーム メトリックが報告されなかったため、ストリームは _未分類_ と見なされる可能性があります。 これらの指標が報告されない理由はいくつかあります。

- **QoE レポートが受信されませんでした** 。 分類に使用されるメトリックは、呼び出しの終了時に送信された QoE レポートで報告されます。 このレポートが生成されない場合 (たとえば、一部のサード パーティのエンドポイントが QoE を送信しない可能性があるため)、送信できなかった場合 (ネットワーク障害など)、CQD はストリームを分類できません。

  > [!TIP]
  > 「QoE Record Available」ディメンションを使用して、QoEレポートがストリームに対して受信されたかどうかを判断できます。 いずれかのエンドポイントからQoEレポートを受信した場合、このディメンションの値は「True」になります。 最も正確な測定基準の報告には、両方のエンドポイントからのQoEレポートが必要です。

- **短い呼び出し** — 短い呼び出しでは、キー ストリーム メトリックを計算するのに十分なメディア アクティビティがない場合があります。 これらのメトリックがなければ、CQDはストリームを分類できません。

  > [!TIP]
  > 「期間（秒）」、「期間（分）」、「期間5秒以下」、および「期間60秒以上」のディメンションは、ストリームの期間を決定するために使用できます。 測定値「平均通話時間」を使用して、一連のストリームの平均所要時間を計算することもできます。

- **パケット使用率が低い** — "短い呼び出し" シナリオと同様に、キー ストリーム メトリックの計算には十分なパケット使用率が必要です。 これらのメトリックがなければ、CQDはストリームを分類できません。
  - 一般的なパケット使用率の低いシナリオは、出席者が発表者の話を聞くために会議に参加しても話さない場合に発生します (ほとんどの通話ではマイクがミュートされます)。 ここでは、クライアントに受信するオーディオ ストリームのパケット使用率が高く、クライアントから送信されるオーディオ ストリームのパケット使用率はほとんど、まったくありません。 ストリームの継続時間は 1 時間以上ですが、マイクがミュートされたため、クライアントからサーバーへのストリームのパケット使用率が低くなり、 _分類されていない_ ストリームが生成されます。

  > [!TIP]
  > 「パケット使用率」ディメンションおよび「平均パケット使用率」測定値を使用して、ストリームのパケットアクティビティを判断できます。

## <a name="related-topics"></a>関連トピック
[Teams の通話品質の向上と監視](monitor-call-quality-qos.md)

[CQD とは](CQD-what-is-call-quality-dashboard.md)

[通話品質ダッシュボード (CQD) をセットアップする](turning-on-and-using-call-quality-dashboard.md)

[テナントと建物のデータをアップロードする](CQD-upload-tenant-building-data.md)

[CQD のデータとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)
