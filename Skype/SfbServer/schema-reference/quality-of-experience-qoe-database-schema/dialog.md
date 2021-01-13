---
title: ダイアログ テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog テーブルはサポート テーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。
ms.openlocfilehash: 05d9519c9aef20b8c82d904a9d5718a4de8c092c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815847"
---
# <a name="dialog-table"></a>ダイアログ テーブル
 
Dialog テーブルはサポート テーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |Quality of Excellence (QoE) エージェントが発信者または呼び出し先から最初のレポートを受信した時刻。 セッションを一意に識別するために SessionSeq と組み合わせて使用されます。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |ConferenceDateTime が同じ場合にセッションを区別するシーケンス番号。  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||グローバルに一意のダイアログ ID。  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |ダイアログ ID のチェックサム。  <br/> |
   

