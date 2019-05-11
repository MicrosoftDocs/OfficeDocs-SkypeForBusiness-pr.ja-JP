---
title: Dialog テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: ダイアログはサポートのテーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。
ms.openlocfilehash: 36ab76d147673ca85371ca4cdfb151fa953e29b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920090"
---
# <a name="dialog-table"></a>Dialog テーブル
 
ダイアログはサポートのテーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |「優れた品質 (QoE) エージェントが呼び出し元または呼び出し先のいずれかから最初のレポートを受信するときの時間です。 セッションを一意に識別するのには SessionSeq と組み合わせてを使用します。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |セッションが同じ ConferenceDateTime がある場合を区別するためにシーケンス番号。  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||グローバルに一意な ID をダイアログです。  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |インデックス  <br/> |ダイアログ ID のチェックサム  <br/> |
   

