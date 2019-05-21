---
title: Phones テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: 電話の表はサポートテーブルです。 テーブル内の各レコードには、データベース内にレコードがある VoIP 通話に関連する1つの電話番号に関する情報が格納されます。
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295945"
---
# <a name="phones-table"></a>Phones テーブル
 
電話の表はサポートテーブルです。 テーブル内の各レコードには、データベース内にレコードがある VoIP 通話に関連する1つの電話番号に関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |この電話を識別する一意の番号。  <br/> |
|**電話の Uri** <br/> |nvarchar (450)  <br/> | <br/> |電話番号。  <br/> |
|**Nextupdatupdat** <br/> |dateTime  <br/> ||タイムスタンプ (内部使用のみ)。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

