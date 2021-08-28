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
ms.localizationpriority: medium
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent View には、データベースにレコードがあるセッションに関与したユーザー エージェントに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: f0e04812928f38d0e9362b08ce160da7e6984df5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580371"
---
# <a name="useragent-view"></a>UserAgent ビュー
 
UserAgent View には、データベースにレコードがあるセッションに関与したユーザー エージェントに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |このユーザー エージェントを識別する一意の番号。  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |ユーザー エージェントの文字列。  <br/> |
|UAType  <br/> |smallint  <br/> |ユーザー エージェントの種類。 詳細については [、UserAgent テーブル](useragent.md) を参照してください。 <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |ユーザー エージェントが属するカテゴリ。たとえば、ユーザー エージェント Conferencing_Attendant_1.0 は UACategory CAA に属します。  <br/> |
   

