---
title: 会議テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会議テーブルは、サポート テーブルです。 各レコードは、1 つの会議またはピアツーピア セッションを表します。
ms.openlocfilehash: 6dfe60a28e8279f7b4c469c61cddc28912db261eedf4754588de4bd8f5852728
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309156"
---
# <a name="conference-table"></a>会議テーブル
 
会議テーブルは、サポート テーブルです。 各レコードは、1 つの会議またはピアツーピア セッションを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |整数  <br/> |Primary  <br/> |この会議レコードを識別する一意の番号。  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |unique  <br/> |これが会議の場合は会議 URI、ピアツーピア セッションの場合は DialogID です。  <br/> |
|**チェックサム** <br/> |整数  <br/> |index  <br/> |会議 URI のチェックサム。 これは内部的に使用されます。  <br/> |
|**NextUpdateTS** <br/> |日付型  <br/> ||内部使用のみ。  <br/> |
   

