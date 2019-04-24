---
title: CodecDescription テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription テーブルでは、コーデックの一意の識別子を対応するコーデックにマップします。 伝送およびブロードキャストでは、デジタル信号をエンコードするためにコーデックを使用し、再生するため、それらの信号をデコードします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: efda27afe9312c25add8be0f74364384aed53b3e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212271"
---
# <a name="codecdescription-table"></a>CodecDescription テーブル
 
CodecDescription テーブルでは、コーデックの一意の識別子を対応するコーデックにマップします。 伝送およびブロードキャストでは、デジタル信号をエンコードするためにコーデックを使用し、再生するため、それらの信号をデコードします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |コーデックに割り当てられている一意の識別子です。  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |一意  <br/> |CodecDescriptionKey に対応するコーデックの一意の説明です。  <br/> |
   

