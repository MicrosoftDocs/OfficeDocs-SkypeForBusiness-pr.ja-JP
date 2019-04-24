---
title: ビジネス サーバー 2015 の Skype での ErrorDef テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef テーブルでは、発生するエラーの種類に関する情報を格納します。 各レコードは、1 つの種類のエラーです。
ms.openlocfilehash: cec601dad24dda522477bfcd7b1e80d0efc45799
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213110"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での ErrorDef テーブル
 
ErrorDef テーブルでは、発生するエラーの種類に関する情報を格納します。 各レコードは、1 つの種類のエラーです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primary  <br/> |この種類のエラーを識別する一意の ID 番号です。  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |このエラーに関連付けられている標準の SIP 応答コード。  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |マイクロソフトの診断 id。  <br/> |
|**CallTypeId** <br/> |Int  <br/> |外部  <br/> |呼び出しの種類です。 [ビジネス サーバー 2015 の Skype の CallType テーブル](calltype.md)の詳細についてを参照してください。 <br/> |
|**修飾子の一覧** <br/> |varbinary(33)  <br/> | <br/> |失敗した要求の種類です。  <br/> このデータは、この構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**コンテンツ タイプ** <br/> |varbinary(257)  <br/> | <br/> |失敗した要求のコンテンツ タイプ。  <br/> このデータは、この syntaxt を使用してテキスト形式に変換できます。  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

