---
title: ErrorDef テーブル (Skype for Business Server 2015)
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef テーブルには、発生する可能性がある各種類のエラーに関する情報が格納されます。 各レコードは 1 種類のエラーです。
ms.openlocfilehash: c4480df63b081fc264334ffeb7031c54de887875
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743883"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>ErrorDef テーブル (Skype for Business Server 2015)
 
ErrorDef テーブルには、発生する可能性がある各種類のエラーに関する情報が格納されます。 各レコードは 1 種類のエラーです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primary  <br/> |この種類のエラーを識別する一意の ID 番号。  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |このエラーに関連付けられている標準の SIP 応答コード。  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft 診断 ID。  <br/> |
|**CallTypeId** <br/> |Int  <br/> |外部  <br/> |呼び出しの種類。 詳細については[、2015 Skype for Business Serverの CallType](calltype.md)テーブルを参照してください。 <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |失敗した要求の種類。  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |失敗した要求のコンテンツ タイプ。  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

