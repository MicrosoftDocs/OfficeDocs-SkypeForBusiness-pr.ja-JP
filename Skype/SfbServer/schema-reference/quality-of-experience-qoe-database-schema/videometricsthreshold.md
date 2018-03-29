---
title: VideoMetricsThreshold テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: VideoMetricsThreshold テーブルには、ビデオ通話の品質の指標の最適化と許容可能な値が含まれています。
ms.openlocfilehash: 7f9901151503889c57a74c6b49e5c9a84e276333
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold テーブル
 
VideoMetricsThreshold テーブルには、ビデオ通話の品質の指標の最適化と許容可能な値が含まれています。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |配置された呼び出しの種類です。  <br/> |
|**VideoPostFECPLROptimal** <br/> |decimal(5,2)  <br/> ||既定値は、0.05 です。  <br/> |
|**VideoPostFECPLRAcceptable** <br/> |decimal(5,2)  <br/> ||既定値は、0.10 です。  <br/> |
|**VideoLocalFrameLostPercentageAverageOptimal** <br/> |decimal(5,2)  <br/> ||5.0 を既定値には。  <br/> |
|**VideoLocalFrameLostPercentageAverageAcceptable** <br/> |decimal(5,2)  <br/> ||既定値は、10.0 です。  <br/> |
|**RecvFrameRateAverageOptimal** <br/> |decimal(9,4)  <br/> ||12.0000 を既定値には。  <br/> |
|**RecvFramerateAverageAcceptable** <br/> |decimal(9,4)  <br/> ||7.0000 を既定値には。  <br/> |
|**LowFrameRateCallPercentOptimal** <br/> |decimal(5,2)  <br/> ||5.0 を既定値には。  <br/> |
|LowFrameRateCallPercentAcceptable。 <br/> |decimal(5,2)  <br/> ||既定値は、10.0/  <br/> |
|**LowResolutionCallPercentOptimal** <br/> |decimal(5,2)  <br/> ||5.0 を既定値には。  <br/> |
|**LowResolutionCallPercentAcceptable** <br/> |decimal(5,2)  <br/> ||既定値は、10.0 です。  <br/> |
|**VideoPacketLossRateOptimal** <br/> |foat  <br/> ||既定値は、0.05 です。  <br/> |
|**VideoPacketLossRateAcceptable** <br/> |float  <br/> ||既定値は、0.10 です。  <br/> |
|**VideoFrameRateAvgOptimal** <br/> |float  <br/> ||既定値は、12 です。  <br/> |
|**VideoFrameRateAvgAcceptable** <br/> |float  <br/> ||既定値は、7 です。  <br/> |
|**DynamicCapabilityPercentOptimal** <br/> |decimal(5,2)  <br/> ||既定値は、5.00 です。  <br/> |
|**DynamicCapabilityPercentAcceptable** <br/> |decimal(5,2)  <br/> ||既定値は 10.00 です。  <br/> |
   

