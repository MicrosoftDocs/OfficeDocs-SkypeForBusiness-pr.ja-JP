---
title: AppSharingMetricsThreshold テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: AppSharingMetricsThreshold テーブルには、アプリケーション共有で使用される QoE (Quality of Experience) 指標の最適な値と許容される値が含まれます。これらのしきい値は、アプリケーション共有のエクスペリエンスを不良として分類する必要があるかどうかを判断するために使用されます。
ms.openlocfilehash: 747497affbf561976bc6dd626bdce060efc1eca8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809697"
---
# <a name="appsharingmetricsthreshold-table"></a>AppSharingMetricsThreshold テーブル
 
AppSharingMetricsThreshold テーブルには、アプリケーション共有で使用される QoE (Quality of Experience) 指標の最適な値と許容される値が含まれます。これらのしきい値は、アプリケーション共有のエクスペリエンスを不良として分類する必要があるかどうかを判断するために使用されます。
  
この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |行われた通話の種類です。  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||アプリケーション共有の最善の帯域幅制限です。既定値は 1000000 です。  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||アプリケーション共有の許容される帯域幅制限です。既定値は 500000 です。  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal(5,2)  <br/> ||アプリケーション共有の品質を分類するための "台無し" タイルの最適な割合。 この値は、ビューアーに到達しなかった共有者からのコンテンツのパーセンテージです。 コンテンツは、共有者がグラフィックス ソースからタイルを破棄すると、または ASMCU タイルが共有者からタイルを破棄すると、破棄される (スポイルされる) 可能性があります。 既定値は 11 パーセントです。  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal(5,2)  <br/> ||アプリケーション共有の品質を分類するための "台無し" タイルの許容パーセンテージ。 この値は、ビューアーに到達しなかった共有者からのコンテンツのパーセンテージです。 コンテンツは、共有者がグラフィックス ソースからタイルを破棄すると、または ASMCU タイルが共有者からタイルを破棄すると、破棄される (スポイルされる) 可能性があります。 既定値は 36 パーセントです。  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||この列は、Microsoft Lync Server 2013 では使用されません。  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||この列は、Microsoft Lync Server 2013 では使用されません。  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |浮動小数点数  <br/> ||この列は、Microsoft Lync Server 2013 では使用されません。  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |浮動小数点数  <br/> ||この列は、Microsoft Lync Server 2013 では使用されません。  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |浮動小数点数  <br/> ||この列は、Microsoft Lync Server 2013 では使用されません。  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |浮動小数点数  <br/> ||この列は、Microsoft Lync Server 2013 では使用されません。  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |浮動小数点数  <br/> ||アプリケーション共有に関係する 2 つのメディア エンドポイント間の相対的な一方向遅延の最善の値です。これは単一ホップ遅延の測定値です。既定値は 1.0 秒です。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |浮動小数点数  <br/> ||アプリケーション共有に関係する 2 つのメディア エンドポイント間の相対的な一方向遅延の許容される値です。これは単一ホップ遅延の測定値です。既定値は 1.75 秒です。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |浮動小数点数  <br/> ||表示セッション中の AS 会議サーバーでの RDP タイル処理の最善の平均遅延です。 待機時間とは、サーバー (シナリオに応じて共有者または MCU) でスタート フレームがエンコードされ、同じ開始フレームがビューアーでデコードされる場合の時間差です。  <br/> 高い平均値は、表示エクスペリエンスでの長い遅延を反映します。高い負荷がかかっている会議サーバーでは、平均遅延が高くなる場合があります。既定値は 200 ミリ秒です。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |浮動小数点数  <br/> ||表示セッション中の AS 会議サーバーでの RDP タイル処理の平均遅延の許容される値です。 待機時間とは、サーバー (シナリオに応じて共有者または MCU) でスタート フレームがエンコードされ、同じ開始フレームがビューアーでデコードされる場合の時間差です。  <br/> 高い平均値は、表示エクスペリエンスでの長い遅延を反映します。高い負荷がかかっている会議サーバーでは、平均遅延が高くなる場合があります。既定値は 200 ミリ秒です。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
   

