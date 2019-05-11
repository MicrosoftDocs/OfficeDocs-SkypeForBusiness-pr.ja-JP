---
title: Phones テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: 電話はテーブルをサポートします。 テーブル内の各レコードは、データベースにレコードがある VoIP 通話に関連する 1 つの電話の番号に関する情報を格納します。
ms.openlocfilehash: ba13a059e043cf2a18c41c28dce1a2a54e694b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930617"
---
# <a name="phones-table"></a>Phones テーブル
 
電話はテーブルをサポートします。 テーブル内の各レコードは、データベースにレコードがある VoIP 通話に関連する 1 つの電話の番号に関する情報を格納します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |この電話を識別する一意の番号です。  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |電話番号です。  <br/> |
|**NextUpdateTS** <br/> |日付時刻  <br/> ||タイム ・ スタンプ (内部使用のみ)。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

