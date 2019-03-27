---
title: Conference テーブル
ms.reviewer: ''
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
ms.openlocfilehash: bae144ff574f19155e11b8a2fbfd3548df356c2a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874040"
---
# <a name="conference-table"></a>Conference テーブル
 
会議の表は、補助テーブルです。 各レコードは、1 つの会議またはピア ツー ピア セッションを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |この会議のレコードを識別する一意の番号です。  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |一意  <br/> |会議 URI は、会議では、DialogID この場合は、ピア ツー ピア セッションです。  <br/> |
|**チェックサム** <br/> |int  <br/> |インデックス  <br/> |会議 URI のチェックサムです。 これは、内部的に使用されます。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||内部でのみ使用します。  <br/> |
   

