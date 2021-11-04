---
title: CodecDescription テーブル
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription テーブルは、対応するコーデックに一意コーデック識別子をマップします。 コーデックは、送受信とブロードキャスト用にデジタル信号をコード化し、再生時にそれらの信号を読み取る目的で使用されます。 この表は、Microsoft Lync Server 2013 で導入されました
ms.openlocfilehash: 0f5601847458f7ce59e0cd691b573ec77605b667
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763245"
---
# <a name="codecdescription-table"></a>CodecDescription テーブル
 
CodecDescription テーブルは、対応するコーデックに一意コーデック識別子をマップします。 コーデックは、送受信とブロードキャスト用にデジタル信号をコード化し、再生時にそれらの信号を読み取る目的で使用されます。 この表は、Microsoft Lync Server 2013 で導入されました
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |新しいコーデックに割り当てる一意識別子です。  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |一意  <br/> |CodecDescriptionKey に対応しているコーデックの一意詳細。  <br/> |
   

