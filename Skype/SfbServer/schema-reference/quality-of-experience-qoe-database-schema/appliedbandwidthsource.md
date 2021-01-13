---
title: AppliedBandwidthSource テーブル
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource テーブルはサポート テーブルです。 各レコードは 1 つのソースを表します。
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831407"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource テーブル
 
AppliedBandwidthSource テーブルはサポート テーブルです。各レコードは 1 つのソースを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |ソースを示す一意の番号です。  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |一意  <br/> |適用されている帯域幅キャップのソースです。 帯域幅制限の適用先 ("Policy Server"、"TURN Server"、"Modality" など) について説明します。  <br/> |
   

