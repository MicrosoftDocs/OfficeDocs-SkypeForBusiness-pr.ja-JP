---
title: CodecDescription テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription テーブルでは、一意のコーデック識別子が対応するコーデックにマップされます。 コーデックは、伝送とブロードキャスト用のデジタルシグナルをエンコードし、再生のためにそれらのシグナルをデコードするために使われます。 この表は Microsoft Lync Server 2013 で導入されました
ms.openlocfilehash: 53410b1bdf4875bd66a80c107dc56c5316fc30a3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810365"
---
# <a name="codecdescription-table"></a>CodecDescription テーブル
 
CodecDescription テーブルでは、一意のコーデック識別子が対応するコーデックにマップされます。 コーデックは、伝送とブロードキャスト用のデジタルシグナルをエンコードし、再生のためにそれらのシグナルをデコードするために使われます。 この表は Microsoft Lync Server 2013 で導入されました
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |コーデックに割り当てられている一意の識別子。  <br/> |
|**CodecDescription** <br/> |varchar (256)  <br/> |一意  <br/> |CodecDescriptionKey に対応するコーデックの固有の説明です。  <br/> |
   

