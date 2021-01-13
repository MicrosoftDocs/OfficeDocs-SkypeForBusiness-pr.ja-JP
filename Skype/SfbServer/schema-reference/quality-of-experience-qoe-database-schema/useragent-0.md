---
title: UserAgent ビュー
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent View は、データベース内のレコードを持つセッションに関与したユーザー エージェントに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 90db61df5bd947b101823172602103e47d4182a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800017"
---
# <a name="useragent-view"></a>UserAgent ビュー
 
UserAgent View は、データベース内のレコードを持つセッションに関与したユーザー エージェントに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |このユーザー エージェントを識別する一意の番号。  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |ユーザー エージェント文字列。  <br/> |
|UAType  <br/> |smallint  <br/> |ユーザー エージェントの種類。 詳細については [、UserAgent の表](useragent.md) を参照してください。 <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |ユーザー エージェントが属するカテゴリ。たとえば、ユーザー エージェント Conferencing_Attendant_1.0 は UACategory CAA に属します。  <br/> |
   

