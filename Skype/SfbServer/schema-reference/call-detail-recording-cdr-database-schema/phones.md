---
title: Phones テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones テーブルはサポート テーブルです。 テーブル内の各レコードには、データベースにレコードがある VoIP 呼び出しに関連する 1 つの電話番号に関する情報が格納されます。
ms.openlocfilehash: 0dbe5065b4a0849b4538e77c05a846ed06f72da5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389809"
---
# <a name="phones-table"></a>Phones テーブル
 
Phones テーブルはサポート テーブルです。 テーブル内の各レコードには、データベースにレコードがある VoIP 呼び出しに関連する 1 つの電話番号に関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |この電話を識別する一意の番号。  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |電話番号。  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||タイム スタンプ (内部使用のみ)。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

