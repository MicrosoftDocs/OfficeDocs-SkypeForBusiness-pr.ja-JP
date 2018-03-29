---
title: UserAgent ビュー
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent ビューは、データベースにレコードが存在するセッションに関係しているユーザー エージェントに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 8df1d45ed1272a886a440aded79a9c4e04c1bae8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-view"></a>UserAgent ビュー
 
UserAgent ビューは、データベースにレコードが存在するセッションに関係しているユーザー エージェントに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |このユーザー エージェントを識別する一意の番号です。  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |ユーザー エージェント文字列です。  <br/> |
|UAType  <br/> |smallint  <br/> |ユーザー エージェントの種類です。 [UserAgent テーブル](useragent.md)の詳細についてはを参照してください。 <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |ユーザー エージェントが属するカテゴリです。 たとえば、ユーザー エージェント Conferencing_Attendant_1.0 は、UACategory CAA に属しています。  <br/> |
   

