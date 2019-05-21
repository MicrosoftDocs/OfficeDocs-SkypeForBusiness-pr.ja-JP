---
title: VideoMetricsThreshold テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: VideoMetricsThreshold テーブルには、ビデオ通話で使用されるエクスペリエンスメトリックの品質と受け入れ可能な値が含まれています。
ms.openlocfilehash: a923334596ea6b3e6b56c43682be0f0f6a640f15
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294538"
---
# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold テーブル
 
VideoMetricsThreshold テーブルには、ビデオ通話で使用されるエクスペリエンスメトリックの品質と受け入れ可能な値が含まれています。
  

| **列**                                               | **データ型**       | **キー/インデックス**  | **詳細**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primary  <br/> | 発信した通話の種類。  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | 10進数 (5, 2)  <br/> |                | 既定値は0.05 です。  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | 10進数 (5, 2)  <br/> |                | 既定値は0.10 です。  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | 10進数 (5, 2)  <br/> |                | 既定値は5.0 です。  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | 10進数 (5, 2)  <br/> |                | 既定値は10.0 です。  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | 10進数 (9, 4)  <br/> |                | 既定値は12.0000 です。  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | 10進数 (9, 4)  <br/> |                | 既定値は7.0000 です。  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | 10進数 (5, 2)  <br/> |                | 既定値は5.0 です。  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | 10進数 (5, 2)  <br/> |                | 既定値は 10.0/  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | 10進数 (5, 2)  <br/> |                | 既定値は5.0 です。  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | 10進数 (5, 2)  <br/> |                | 既定値は10.0 です。  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | @  <br/>         |                | 既定値は0.05 です。  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | 既定値は0.10 です。  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | 既定値は12です。  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | 既定値は7です。  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | 10進数 (5, 2)  <br/> |                | 既定値は5.00 です。  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | 10進数 (5, 2)  <br/> |                | 既定値は10.00 です。  <br/>   |

