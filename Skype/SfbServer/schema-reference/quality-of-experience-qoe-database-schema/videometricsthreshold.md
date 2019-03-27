---
title: VideoMetricsThreshold テーブル
ms.reviewer: ''
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
ms.openlocfilehash: 560012374ab6a9ef5ea741d2046afb095336d3c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893790"
---
# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold テーブル
 
VideoMetricsThreshold テーブルには、ビデオ通話の品質の指標の最適化と許容可能な値が含まれています。
  

| **列**                                               | **データ型**       | **キー/インデックス**  | **詳細**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primary  <br/> | 配置された呼び出しの種類です。  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimal(5,2)  <br/> |                | 既定値は、0.05 です。  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimal(5,2)  <br/> |                | 既定値は、0.10 です。  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimal(5,2)  <br/> |                | 5.0 を既定値には。  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimal(5,2)  <br/> |                | 既定値は、10.0 です。  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimal(9,4)  <br/> |                | 12.0000 を既定値には。  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimal(9,4)  <br/> |                | 7.0000 を既定値には。  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimal(5,2)  <br/> |                | 5.0 を既定値には。  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | decimal(5,2)  <br/> |                | 既定値は、10.0/  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | 5.0 を既定値には。  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | 既定値は、10.0 です。  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | 既定値は、0.05 です。  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | 既定値は、0.10 です。  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | 既定値は、12 です。  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | 既定値は、7 です。  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | 既定値は、5.00 です。  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | 既定値は 10.00 です。  <br/>   |

