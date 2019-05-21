---
title: AppSharingMetricsThreshold テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: AppSharingMetricsThreshold の表には、アプリケーションの共有で使用されるエクスペリエンスメトリックの品質と受け入れ可能な値が含まれています。 これらのしきい値は、アプリケーション共有エクスペリエンスが低品質として分類される必要があるかどうかを判断するために使用されます。
ms.openlocfilehash: d3e7bab384c5fffea59e165d5fdf4e6b3d0c09a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295126"
---
# <a name="appsharingmetricsthreshold-table"></a>AppSharingMetricsThreshold テーブル
 
AppSharingMetricsThreshold の表には、アプリケーションの共有で使用されるエクスペリエンスメトリックの品質と受け入れ可能な値が含まれています。 これらのしきい値は、アプリケーション共有エクスペリエンスが低品質として分類される必要があるかどうかを判断するために使用されます。
  
この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |発信した通話の種類。  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||アプリケーション共有に最適な帯域幅の制限。 既定値は100万です。  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||アプリケーション共有に対して許容可能な帯域幅制限。 既定値は50万です。  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |10進数 (5, 2)  <br/> ||アプリケーション共有の品質を分類するための "損失" タイルの最適な比率。 この値は、閲覧者に届かなかった、共有先のコンテンツのパーセンテージです。 グラフィックスソースまたは ASMCU タイルから共有されているタイルがそれぞれ、共有元のタイルを破棄した場合、コンテンツは破棄 (または損失) されることがあります。 既定値は11パーセントです。  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |10進数 (5, 2)  <br/> ||アプリケーション共有の品質を分類するための "損失" タイルの許容率。 この値は、閲覧者に届かなかった、共有先のコンテンツのパーセンテージです。 グラフィックスソースまたは ASMCU タイルから共有されているタイルがそれぞれ、共有元のタイルを破棄した場合、コンテンツは破棄 (または損失) されることがあります。 既定値は36パーセントです。  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||この列は、Microsoft Lync Server 2013 では使用されません。  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||この列は、Microsoft Lync Server 2013 では使用されません。  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||この列は、Microsoft Lync Server 2013 では使用されません。  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||この列は、Microsoft Lync Server 2013 では使用されません。  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||この列は、Microsoft Lync Server 2013 では使用されません。  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||この列は、Microsoft Lync Server 2013 では使用されません。  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||アプリケーション共有に関連する2つのメディアエンドポイント間の相対的な一方向の遅延の最適値。 これは 1 ホップの遅延の測定です。 既定値は1.0 秒です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||アプリケーション共有に関連する2つのメディアエンドポイント間の相対的な一方向の遅延の最適値。 これは 1 ホップの遅延の測定です。 既定値は1.75 秒です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||表示セッションの間の会議サーバーとしての平均 RDP タイル処理の待機時間の最適値。 [待ち時間] は、サーバー (シナリオによっては共有先または MCU) で開始フレームがエンコードされてから、同じ開始フレームが viewer でデコードされるタイミングの差です。  <br/> 平均値が高いと、表示の際の遅延が大きくなります。 過負荷の会議サーバーでは平均遅延が大きくなる場合があります。 既定値は200ms です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||表示セッション中の会議サーバーとしての平均 RDP タイル処理待ち時間の値。 [待ち時間] は、サーバー (シナリオによっては共有先または MCU) で開始フレームがエンコードされてから、同じ開始フレームが viewer でデコードされるタイミングの差です。  <br/> 平均値が高いと、表示の際の遅延が大きくなります。 過負荷の会議サーバーでは平均遅延が大きくなる場合があります。 既定値は200ms です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

