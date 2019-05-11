---
title: ビジネス サーバー 2015 の Skype でのダイアログ ボックスのテーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: ダイアログ ボックスのテーブルは、ピア ツー ピア セッションの DialogIDs に関する情報を格納するサポート テーブルです。
ms.openlocfilehash: 379956a2c77c60a53e702913d81b25b41dc2fc23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901130"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype でのダイアログ ボックスのテーブル
 
ダイアログ ボックスのテーブルは、ピア ツー ピア セッションの DialogIDs に関する情報を格納するサポート テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |セッションの要求の時間セッションを一意に識別するのには SessionIDSeq と組み合わせてを使用します。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには SessionIDTime と組み合わせてを使用します。  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID のチェックサムです。 このフィールドはデータベース検索の速度を上げるために使用します。  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |SIP ダイアログの ID をバイナリとして格納されています。 バイナリの形式は次のとおりです。  <br/> ダイアログ; タグからタグに  <br/> このデータは、この構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

