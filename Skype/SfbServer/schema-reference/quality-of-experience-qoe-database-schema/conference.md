---
title: 会議テーブル
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会議テーブルは、サポート テーブルです。 各レコードは、1 つの会議またはピアツーピア セッションを表します。
ms.openlocfilehash: b5129fec73658d86fdb8d5cd7dd5c387cdadf4f9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763215"
---
# <a name="conference-table"></a>会議テーブル
 
会議テーブルは、サポート テーブルです。 各レコードは、1 つの会議またはピアツーピア セッションを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |この会議レコードを識別する一意の番号。  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |unique  <br/> |これが会議の場合は会議 URI、ピアツーピア セッションの場合は DialogID です。  <br/> |
|**チェックサム** <br/> |int  <br/> |index  <br/> |会議 URI のチェックサム。 これは内部的に使用されます。  <br/> |
|**NextUpdateTS** <br/> |日付型  <br/> ||内部使用のみ。  <br/> |
   

