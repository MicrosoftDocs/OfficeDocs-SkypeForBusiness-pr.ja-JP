---
title: VideoMetricsThreshold テーブル
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
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: VideoMetricsThreshold テーブルには、ビデオ通話で使用される QoE 指標の最適な値および許容可能な値が含まれています。
ms.openlocfilehash: 15bf482412973fe4b3a0178be6ecdcc593c762e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821377"
---
# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold テーブル
 
VideoMetricsThreshold テーブルには、ビデオ通話で使用される QoE 指標の最適な値および許容可能な値が含まれています。
  

| **列**                                               | **データ型**       | **キー/インデックス**  | **詳細**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primary  <br/> | 発信された通話の種類  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimal(5,2)  <br/> |                | 既定値は 0.05 です。  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimal(5,2)  <br/> |                | 既定値は 0.10 です。  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimal(5,2)  <br/> |                | 既定値は 5.0 です。  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimal(5,2)  <br/> |                | 既定値は 10.0 です。  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimal(9,4)  <br/> |                | 既定値は 12.0000 です。  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimal(9,4)  <br/> |                | 既定値は 7.0000 です。  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimal(5,2)  <br/> |                | 既定値は 5.0 です。  <br/>     |
| \****LowFrameRateCallPercentAcceptable** _\_ <br/>        | decimal(5,2)  <br/> |                | 既定値は 10.0 です。  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | 既定値は 5.0 です。  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | 既定値は 10.0 です。  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | 既定値は 0.05 です。  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | 浮動小数点数  <br/>        |                | 既定値は 0.10 です。  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | 浮動小数点数  <br/>        |                | 既定値は 12 です。  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | 浮動小数点数  <br/>        |                | 既定値は 7 です。  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | 既定値は 5.00 です。  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | 既定値は 10.00 です。  <br/>   |

