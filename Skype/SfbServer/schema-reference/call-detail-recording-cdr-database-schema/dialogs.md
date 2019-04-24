---
title: ビジネス サーバー 2015 の Skype でのダイアログ ボックスのテーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: ダイアログ ボックスのテーブルは、ピア ツー ピア セッションの DialogIDs に関する情報を格納するサポート テーブルです。
ms.openlocfilehash: af7816c202f995e826567391bf32c5c32a2d0d94
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213657"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype でのダイアログ ボックスのテーブル
 
ダイアログ ボックスのテーブルは、ピア ツー ピア セッションの DialogIDs に関する情報を格納するサポート テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |セッションの要求の時間セッションを一意に識別するのには SessionIDSeq と組み合わせてを使用します。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには SessionIDTime と組み合わせてを使用します。  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID のチェックサムです。 このフィールドはデータベース検索の速度を上げるために使用します。  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |SIP ダイアログの ID をバイナリとして格納されています。 バイナリの形式は次のとおりです。  <br/> ダイアログ; タグからタグに  <br/> このデータは、この構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

