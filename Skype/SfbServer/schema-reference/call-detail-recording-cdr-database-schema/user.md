---
title: ユーザービュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: ユーザービューには、データベース内のレコードを持つ通話またはセッションに参加しているユーザーに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 2fe0ba4748a776a8f17065a3c5db21d34bd6340d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295742"
---
# <a name="user-view"></a>ユーザービュー
 
ユーザービューには、データベース内のレコードを持つ通話またはセッションに参加しているユーザーに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |このユーザーを識別する一意の番号です。  <br/> |
|UserUri  <br/> |nvarchar (450)  <br/> |ユーザーの Uri。  <br/> |
|TenantKey  <br/> |長さ  <br/> |ユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |ユーザー URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
   

