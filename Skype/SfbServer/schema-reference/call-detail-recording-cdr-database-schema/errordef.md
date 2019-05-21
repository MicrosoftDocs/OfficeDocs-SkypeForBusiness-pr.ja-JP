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
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef テーブルには、発生する可能性がある各エラーの種類に関する情報が格納されます。 各レコードは1種類のエラーです。
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296281"
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
   

