---
title: Skype for Business Server 2015 のダイアログテーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs テーブルは、ピアツーピアセッションの DialogIDs に関する情報を格納するサポートテーブルです。
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296323"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 のダイアログテーブル
 
Dialogs テーブルは、ピアツーピアセッションの DialogIDs に関する情報を格納するサポートテーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |Primary  <br/> |セッション要求の時刻。セッションを一意に識別するために SessionIDSeq と組み合わせて使用されます。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために SessionIDTime と組み合わせて使用されます。  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID のチェックサム。 このフィールドは、データベースの検索速度を上げるために使用されます。  <br/> |
|**ExternalId** <br/> |varbinary (775)  <br/> | <br/> |SIP ダイアログ ID。バイナリとして保存されます。 バイナリの形式は次のとおりです。  <br/> ダイアログ; 開始タグからタグへ  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

