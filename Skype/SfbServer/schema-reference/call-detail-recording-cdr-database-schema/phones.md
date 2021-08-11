---
title: Phones テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones テーブルはサポート テーブルです。 テーブル内の各レコードには、データベースにレコードがある VoIP 呼び出しに関連する 1 つの電話番号に関する情報が格納されます。
ms.openlocfilehash: 938e00267f5f356c646d363033ef9a8917b910261f873637c0f6b3a6b9ff8742
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329461"
---
# <a name="phones-table"></a>Phones テーブル
 
Phones テーブルはサポート テーブルです。 テーブル内の各レコードには、データベースにレコードがある VoIP 呼び出しに関連する 1 つの電話番号に関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |整数  <br/> |Primary  <br/> |この電話を識別する一意の番号。  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |電話番号。  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||タイム スタンプ (内部使用のみ)。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

