---
title: AppSharingMetricsThreshold テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: AppSharingMetricsThreshold テーブルには、アプリケーション共有で使用される高品質のエクスペリエンスの測定値の最適なと許容可能な値が含まれています。 これらのしきい値を使用すると、経験を共有するアプリケーションを不十分な分類するかかどうかを決定します。
ms.openlocfilehash: 32a3a8e4942ad41fc7c1969c14c915bc95aa9e82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924893"
---
# <a name="appsharingmetricsthreshold-table"></a>AppSharingMetricsThreshold テーブル
 
AppSharingMetricsThreshold テーブルには、アプリケーション共有で使用される高品質のエクスペリエンスの測定値の最適なと許容可能な値が含まれています。 これらのしきい値を使用すると、経験を共有するアプリケーションを不十分な分類するかかどうかを決定します。
  
このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |配置された呼び出しの種類です。  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||アプリケーションを共有するための最適な帯域幅の制限です。 既定値は、1000000 です。  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||アプリケーションを共有するための十分な帯域幅制限。 既定値は、500000 です。  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal(5,2)  <br/> ||「不良」タイルの場合、アプリケーション共有の品質をクラス分けするための最適の割合 (%)。 この値は、視聴者に到達しなかった共有からのコンテンツの割合です。 コンテンツが破棄 (または不良) と共有先は、グラフィックス ソースからタイルを破棄または、ASMCU は、パケットの破棄を並べて表示並べて表示先からそれぞれ。 既定値は、11% です。  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal(5,2)  <br/> ||「不良」タイルの場合、アプリケーション共有の品質をクラス分けするためのレートを許容可能な割合です。 この値は、視聴者に到達しなかった共有からのコンテンツの割合です。 コンテンツが破棄 (または不良) と共有先は、グラフィックス ソースからタイルを破棄または、ASMCU は、パケットの破棄を並べて表示並べて表示先からそれぞれ。 既定値は、36% です。  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Microsoft Lync Server 2013 では、この列は使用されません。  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Microsoft Lync Server 2013 では、この列は使用されません。  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Microsoft Lync Server 2013 では、この列は使用されません。  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Microsoft Lync Server 2013 では、この列は使用されません。  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Microsoft Lync Server 2013 では、この列は使用されません。  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Microsoft Lync Server 2013 では、この列は使用されません。  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||アプリケーションの共有に関連するメディアの 2 つのエンドポイント間での相対的な一方向遅延の最適な値です。 これは 1 ホップの遅延の測定です。 既定値は、1.0 秒です。  <br/> 列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||アプリケーションの共有に関連するメディアの 2 つのエンドポイント間での相対的な一方向遅延の最適な値です。 これは 1 ホップの遅延の測定です。 既定値は、1.75 秒です。  <br/> 列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||閲覧セッションの継続時間中に、会議サーバーの待機時間を処理する平均 RDP タイルの最適な値です。 遅延時間の間の時間差 (共有または状況によって MCU) は、サーバー上の開始フレームをエンコードし、ビューアーで、同一の開始フレームがデコードされると、  <br/> 平均値が高いと、表示の際の遅延が大きくなります。 過負荷の会議サーバーでは平均遅延が大きくなる場合があります。 既定値は、200 ミリ秒です。  <br/> 列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||閲覧セッションの継続時間中に、会議サーバーの待機時間を処理する平均 RDP タイルの有効な値。 遅延時間の間の時間差 (共有または状況によって MCU) は、サーバー上の開始フレームをエンコードし、ビューアーで、同一の開始フレームがデコードされると、  <br/> 平均値が高いと、表示の際の遅延が大きくなります。 過負荷の会議サーバーでは平均遅延が大きくなる場合があります。 既定値は、200 ミリ秒です。  <br/> 列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

