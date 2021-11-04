---
title: ダイアログ 2015 Skype for Business Server
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs テーブルは、ピアツーピア セッションの DialogID に関する情報を格納するサポート テーブルです。
ms.openlocfilehash: 9aaf2691e3869830e2ccc605475d856517d1fe8b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743963"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>ダイアログ 2015 Skype for Business Server
 
Dialogs テーブルは、ピアツーピア セッションの DialogID に関する情報を格納するサポート テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |Primary  <br/> |セッション要求の時刻。セッションを一意に識別するために SessionIDSeq と組み合わせて使用されます。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別するための ID 番号。 SessionIDTime と組み合わせて使用して、セッションを一意に識別します。  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID のチェックサム。 このフィールドは、データベース検索の速度を向上するために使用されます。  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |バイナリとして格納された SIP ダイアログ ID。 バイナリの形式は次の形式です。  <br/> dialog;from-tag;to-tag  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

