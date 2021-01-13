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
description: 会議テーブルはサポート テーブルです。 各レコードは、1 つの電話会議またはピアツーピア セッションを表します。
ms.openlocfilehash: 3840ad9bb4f9b0ff0aea5068c73d307d5bd0cf5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802787"
---
# <a name="conference-table"></a>会議テーブル
 
会議テーブルはサポート テーブルです。 各レコードは、1 つの電話会議またはピアツーピア セッションを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |この電話会議レコードを識別する一意の番号。  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |unique  <br/> |これが会議の場合は会議 URI、ピアツーピア セッションの場合は DialogID です。  <br/> |
|**チェックサム** <br/> |int  <br/> |index  <br/> |電話会議 URI のチェックサム。 これは内部で使用されます。  <br/> |
|**NextUpdateTS** <br/> |日付型  <br/> ||内部使用のみ。  <br/> |
   

