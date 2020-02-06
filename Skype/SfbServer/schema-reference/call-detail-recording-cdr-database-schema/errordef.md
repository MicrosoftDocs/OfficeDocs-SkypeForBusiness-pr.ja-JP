---
title: Skype for Business Server 2015 の ErrorDef テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef テーブルには、発生する可能性がある各エラーの種類に関する情報が格納されます。 各レコードは1種類のエラーです。
ms.openlocfilehash: f686692bee334c0927b6e8342cfb7152b3e54f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815235"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ErrorDef テーブル
 
ErrorDef テーブルには、発生する可能性がある各エラーの種類に関する情報が格納されます。 各レコードは1種類のエラーです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primary  <br/> |この種類のエラーを識別する固有の ID 番号。  <br/> |
|**返信** <br/> |int  <br/> | <br/> |このエラーに関連付けられた標準 SIP 応答コード。  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft 診断 ID。  <br/> |
|**発信者の Typeid** <br/> |Int  <br/> |外部  <br/> |通話の種類。 詳細については、「 [Skype For Business Server 2015 の CallType テーブル](calltype.md)」を参照してください。 <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |失敗した要求の種類。  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary (257)  <br/> | <br/> |失敗した要求のコンテンツタイプ。  <br/> このデータは、次の syntaxt を使用してテキスト形式に変換できます。  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

