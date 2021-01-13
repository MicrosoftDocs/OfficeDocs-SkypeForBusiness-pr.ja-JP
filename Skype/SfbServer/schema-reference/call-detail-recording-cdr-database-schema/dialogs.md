---
title: Skype for Business Server 2015 の Dialogs テーブル
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
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816047"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の Dialogs テーブル
 
Dialogs テーブルは、ピアツーピア セッションの DialogID に関する情報を格納するサポート テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |Primary  <br/> |セッション要求の時刻。セッションを一意に識別するために SessionIDSeq と組み合わせて使用されます。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために SessionIDTime と組み合わせて使用します。  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID のチェックサム。 このフィールドは、データベース検索の速度を向上するために使用されます。  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |バイナリとして格納される SIP ダイアログ ID。 バイナリの形式は次の形式です。  <br/> dialog;from-tag;to-tag  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

