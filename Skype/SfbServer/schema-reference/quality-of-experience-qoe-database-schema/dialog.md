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
ms.openlocfilehash: 5796a50a5e9ab121f8c84f81bd00f417843b2c86c5863dafb6d639b1fc0bab55
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305139"
---
# <a name="dialog-table"></a>ダイアログ テーブル
 
Dialog テーブルはサポート テーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |Quality of Excellence (QoE) エージェントが発信者または呼び出し先から最初のレポートを受信する時間。 SessionSeq と組み合わせて使用して、セッションを一意に識別します。  <br/> |
|**SessionSeq** <br/> |整数  <br/> |Primary  <br/> |同じ ConferenceDateTime を持つセッションを区別するシーケンス番号。  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||グローバルに一意のダイアログ ID。  <br/> |
|**DialogIDChecksum** <br/> |整数  <br/> |index  <br/> |ダイアログ ID のチェックサム。  <br/> |
   

