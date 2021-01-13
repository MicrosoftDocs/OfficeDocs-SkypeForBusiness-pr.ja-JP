---
title: Skype for Business Server 2015 の ErrorDef テーブル
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef テーブルには、発生する可能性がある各種類のエラーに関する情報が格納されます。 各レコードは 1 種類のエラーです。
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821727"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ErrorDef テーブル
 
ErrorDef テーブルには、発生する可能性がある各種類のエラーに関する情報が格納されます。 各レコードは 1 種類のエラーです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primary  <br/> |この種類のエラーを識別する一意の ID 番号。  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |このエラーに関連付けられている標準的な SIP 応答コード。  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft 診断 ID。  <br/> |
|**CallTypeId** <br/> |Int  <br/> |外部  <br/> |通話の種類。 詳細については [、Skype for Business Server 2015](calltype.md) の CallType テーブルを参照してください。 <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |失敗した要求の種類。  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |失敗した要求のコンテンツ タイプ。  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

