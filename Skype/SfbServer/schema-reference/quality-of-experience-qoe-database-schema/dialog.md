---
title: ダイアログ テーブル
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog テーブルはサポート テーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。
---

# <a name="dialog-table"></a>ダイアログ テーブル
 
Dialog テーブルはサポート テーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |Quality of Excellence (QoE) エージェントが発信者または呼び出し先から最初のレポートを受信する時間。 SessionSeq と組み合わせて使用して、セッションを一意に識別します。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |同じ ConferenceDateTime を持つセッションを区別するシーケンス番号。  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||グローバルに一意のダイアログ ID。  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |ダイアログ ID のチェックサム。  <br/> |
   

