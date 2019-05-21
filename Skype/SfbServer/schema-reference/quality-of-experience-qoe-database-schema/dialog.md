---
title: Dialog テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: ダイアログテーブルはサポートテーブルです。各レコードは、1つのセッション開始プロトコル (SIP) ダイアログを表します。
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294958"
---
# <a name="dialog-table"></a>Dialog テーブル
 
ダイアログテーブルはサポートテーブルです。各レコードは、1つのセッション開始プロトコル (SIP) ダイアログを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |卓越した品質 (QoE) エージェントが、呼び出し元または呼び出し元から最初のレポートを受け取る時刻。 セッションを一意に識別するために SessionSeq と組み合わせて使用されます。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |セッションを区別するための順序番号 (同じ ConferenceDateTime がある場合)。  <br/> |
|**この Id** <br/> |varchar (256)  <br/> ||グローバルに一意のダイアログ ID。  <br/> |
|**このチェックサム** <br/> |int  <br/> |位置  <br/> |ダイアログ ID のチェックサム。  <br/> |
   

