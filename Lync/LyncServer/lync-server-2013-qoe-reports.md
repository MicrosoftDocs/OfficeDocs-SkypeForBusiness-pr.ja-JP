---
title: 'Lync Server 2013: QoE レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b08544365cf536b791fdfffa5d1d1521a1cc966
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a>Lync Server 2013 の QoE レポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-01_

<div>

## <a name="qoe-summarytrend-reports"></a>QoE の概要/傾向レポート

QoE のサマリー/傾向レポートは、時間のピーク時の使用時間を見つけて、メディアの品質を調べて、組織のネットワークリソースを十分に確保するのに役立ちます。 組織はレポートで利用可能な多くのフィルターを使用して、特定の場所、クライアントとデバイスの種類、およびサーバーのパフォーマンスの数値を特定することもできます。

QoE の概要/傾向レポートは、次の要素で構成されます。

  - UC から UC へのサマリー/傾向レポート

  - PSTN の概要/傾向レポート

  - 電話会議の概要/傾向レポート

</div>

<div>

## <a name="qoe-performance-reports"></a>QoE パフォーマンスレポート

QoE パフォーマンスレポートには、仲介サーバー、音声ビデオ会議サーバー、およびエンドポイントの場所の QoE パフォーマンスに集中する3つのレポートに関する詳細が記載されています。

</div>

<div>

## <a name="mediation-server-performance-report"></a>仲介サーバーのパフォーマンスレポート

仲介サーバーのパフォーマンスレポートには、指定された期間中に1つ以上の仲介で得られた指標が一覧表示されます。 統合コミュニケーション (UC) ツー仲介サーバーレグの指標と、各呼び出しの仲介サーバー間の区間は別々に報告されます。 このレポートを使用して、組織のさまざまな仲介サーバーのボリュームとパフォーマンスを比較します。

各仲介サーバー (および各通話区間) に対して、レポートには次のように表示されます。

  - 通話の数

  - パケット損失

  - 往復時間

  - ずれ

  - 話し言葉平均意見スコア (MOS)

  - MOS の送信

  - リスニング MOS

  - ネットワーク MOS

  - ネットワーク MOS の低下

  - エコーリターン

  - シグナルレベル

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a>音声ビデオ会議サーバーのパフォーマンスレポート

音声ビデオ会議サーバーのパフォーマンスレポートでは、指定された期間中に1つ以上の音声ビデオ会議サーバーによって得られる指標の一覧が示されます。 このレポートは、組織のさまざまな音声ビデオ会議サーバーのボリュームとパフォーマンスを比較するために使用できます。 また、組織でレポートを分離して、Lync クライアントや PSTN クライアントなど、特定のクライアントの種類に関する実績のみを表示することもできます。

音声ビデオ会議サーバーごとに、レポートに次のメッセージが表示されます。

  - 電話会議の数

  - パケット損失

  - 往復時間

  - ずれ

  - 話し言葉平均意見スコア (MOS)

  - MOS の送信

  - リスニング MOS

  - ネットワーク MOS

  - ネットワーク MOS の低下

  - エコーリターン

  - シグナルレベル

</div>

<div>

## <a name="location-based-performance-report"></a>場所に基づくパフォーマンスレポート

場所に基づくパフォーマンスレポートには、ネットワークの場所の一覧が表示されます。また、各場所には、事前に決められた各品質の範囲内の呼び出しの数が表示されます。 このレポートの目的は、さまざまな場所に対する組織の電話の大部分のメディア品質についての情報を提供することによって、実際には実行されていない場所を特定し、組織内のさまざまな品質のメディア品質を確認できるようにすることです。場所が異なります。

レポートを表示すると、測定基準の異なるテーブルが表示されます。組織がレポートを決定する指標ごとに1つのテーブルが表示されます。 このレポートには、次の指標を選択できます。

  - 話し言葉平均意見スコア (MOS)

  - ネットワーク MOS

  - ネットワーク MOS の低下

  - MOS の送信

  - リスニング MOS

  - パケット損失

  - ずれ

  - 待機時間

</div>

</div>

<span> </span>

</div>

</div>

</div>

