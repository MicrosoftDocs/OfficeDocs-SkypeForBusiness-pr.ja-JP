---
title: Dialog テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: ダイアログはサポートのテーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。
ms.openlocfilehash: 0380f9c7c48ff7d3b26b9ea5442fb5ac2155f785
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="dialog-table"></a>Dialog テーブル
 
ダイアログはサポートのテーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |「優れた品質 (QoE) エージェントが呼び出し元または呼び出し先のいずれかから最初のレポートを受信するときの時間です。 セッションを一意に識別するのには SessionSeq と組み合わせてを使用します。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |セッションが同じ ConferenceDateTime がある場合を区別するためにシーケンス番号。  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||グローバルに一意な ID をダイアログです。  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |インデックス  <br/> |ダイアログ ID のチェックサム  <br/> |
   

