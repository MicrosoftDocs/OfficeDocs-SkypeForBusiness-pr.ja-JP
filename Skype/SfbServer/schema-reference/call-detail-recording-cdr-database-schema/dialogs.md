---
title: ビジネス サーバー 2015 の Skype でのダイアログ ボックスのテーブル
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
ms.openlocfilehash: b2953ff2bec35575221bc0d43785eb6c0d90e2d1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype でのダイアログ ボックスのテーブル
 
ダイアログ ボックスのテーブルは、ピア ツー ピア セッションの DialogIDs に関する情報を格納するサポート テーブルです。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |セッションの要求の時間セッションを一意に識別するのには SessionIDSeq と組み合わせてを使用します。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには SessionIDTime と組み合わせてを使用します。  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID のチェックサムです。 このフィールドはデータベース検索の速度を上げるために使用します。  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |SIP ダイアログの ID をバイナリとして格納されています。 バイナリの形式は次のとおりです。  <br/> ダイアログ; タグからタグに  <br/> このデータは、この構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

