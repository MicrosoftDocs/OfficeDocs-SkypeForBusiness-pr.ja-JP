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
description: AppliedBandwidthSource テーブルはサポート テーブルです。各レコードは 1 つのソースを表します。
ms.openlocfilehash: fcb0323b1e6775b20a8ca4d269bcc8eecdc055b73d5a93a490e97f8a1af44b11
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305349"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource テーブル
 
AppliedBandwidthSource テーブルはサポート テーブルです。各レコードは 1 つのソースを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |整数  <br/> |Primary  <br/> |ソースを示す一意の番号です。  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |一意  <br/> |適用されている帯域幅キャップのソースです。 帯域幅の制限がどこから来ているかについて説明します (たとえば、"Policy Server"、"TURN Server"、"Modality"など)。  <br/> |
   

