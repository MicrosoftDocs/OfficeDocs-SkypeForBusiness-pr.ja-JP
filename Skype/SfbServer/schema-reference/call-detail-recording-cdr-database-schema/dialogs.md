---
title: ダイアログ 2015 Skype for Business Server
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs テーブルは、ピアツーピア セッションの DialogID に関する情報を格納するサポート テーブルです。
ms.openlocfilehash: 368abb6131367434edbdf1fe142a376fe9a155277eec8b369482545146dbdc3b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302281"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>ダイアログ 2015 Skype for Business Server
 
Dialogs テーブルは、ピアツーピア セッションの DialogID に関する情報を格納するサポート テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |Primary  <br/> |セッション要求の時刻。セッションを一意に識別するために SessionIDSeq と組み合わせて使用されます。  <br/> |
|**SessionIdSeq** <br/> |整数  <br/> |Primary  <br/> |セッションを識別するための ID 番号。 SessionIDTime と組み合わせて使用して、セッションを一意に識別します。  <br/> |
|**ExternalChecksum** <br/> |整数  <br/> | <br/> |ExternalID のチェックサム。 このフィールドは、データベース検索の速度を向上するために使用されます。  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |バイナリとして格納された SIP ダイアログ ID。 バイナリの形式は次の形式です。  <br/> dialog;from-tag;to-tag  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

