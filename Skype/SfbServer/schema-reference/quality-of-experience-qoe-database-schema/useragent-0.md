---
title: UserAgent ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent ビューには、データベース内のレコードを持つセッションに関連しているユーザーエージェントに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805085"
---
# <a name="useragent-view"></a>UserAgent ビュー
 
UserAgent ビューには、データベース内のレコードを持つセッションに関連しているユーザーエージェントに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |このユーザーエージェントを識別する一意の番号です。  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |ユーザーエージェント文字列。  <br/> |
|UAType  <br/> |smallint  <br/> |ユーザーエージェントの種類。 詳細については、 [UserAgent の表](useragent.md)を参照してください。 <br/> |
|UACategory  <br/> |nvarchar (64)  <br/> |ユーザーエージェントが属しているカテゴリ。 たとえば、.0 Conferencing_Attendant_1 .0 は UACategory CAA をに属しています。  <br/> |
   

