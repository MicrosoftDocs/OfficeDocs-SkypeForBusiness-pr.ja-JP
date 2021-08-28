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
ms.localizationpriority: medium
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource テーブルはサポート テーブルです。各レコードは 1 つのソースを表します。
ms.openlocfilehash: 2daa4d35d11c000503fa83c79963df14886f50cd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633471"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource テーブル
 
AppliedBandwidthSource テーブルはサポート テーブルです。各レコードは 1 つのソースを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |ソースを示す一意の番号です。  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |一意  <br/> |適用されている帯域幅キャップのソースです。 帯域幅の制限がどこから来ているかについて説明します (たとえば、"Policy Server"、"TURN Server"、"Modality"など)。  <br/> |
   

