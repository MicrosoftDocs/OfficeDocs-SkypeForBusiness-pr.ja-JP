---
title: UserAgent ビュー
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent View には、データベースにレコードがあるセッションに関与したユーザー エージェントに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: a6390689af0da442561ff02fbf54e8843d93fe4f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768295"
---
# <a name="useragent-view"></a>UserAgent ビュー
 
UserAgent View には、データベースにレコードがあるセッションに関与したユーザー エージェントに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |このユーザー エージェントを識別する一意の番号。  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |ユーザー エージェントの文字列。  <br/> |
|UAType  <br/> |smallint  <br/> |ユーザー エージェントの種類。 詳細については [、UserAgent テーブル](useragent.md) を参照してください。 <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |ユーザー エージェントが属するカテゴリ。たとえば、ユーザー エージェント Conferencing_Attendant_1.0 は UACategory CAA に属します。  <br/> |
   

