---
title: Conference テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会議の表は、補助テーブルです。 各レコードは、1 つの会議またはピア ツー ピア セッションを表します。
ms.openlocfilehash: 0390f1f9da264ab5269c7bfdcb4a86c08097b835
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="conference-table"></a>Conference テーブル
 
会議の表は、補助テーブルです。 各レコードは、1 つの会議またはピア ツー ピア セッションを表します。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |この会議のレコードを識別する一意の番号です。  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |一意  <br/> |会議 URI は、会議では、DialogID この場合は、ピア ツー ピア セッションです。  <br/> |
|**チェックサム** <br/> |int  <br/> |インデックス  <br/> |会議 URI のチェックサムです。 これは、内部的に使用されます。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||内部でのみ使用します。  <br/> |
   

