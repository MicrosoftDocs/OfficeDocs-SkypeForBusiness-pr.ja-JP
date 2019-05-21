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
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent ビューには、データベース内のレコードを持つセッションに関連しているユーザーエージェントに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294608"
---
# <a name="useragent-view"></a>UserAgent ビュー
 
UserAgent ビューには、データベース内のレコードを持つセッションに関連しているユーザーエージェントに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |このユーザーエージェントを識別する一意の番号です。  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |ユーザーエージェント文字列。  <br/> |
|UAType  <br/> |smallint  <br/> |ユーザーエージェントの種類。 詳細については、 [UserAgent の表](useragent.md)を参照してください。 <br/> |
|UACategory  <br/> |nvarchar (64)  <br/> |ユーザーエージェントが属しているカテゴリ。 たとえば、ユーザーエージェント Conferencing_Attendant_ 1.0 は UACategory CAA をに属しています。  <br/> |
   

