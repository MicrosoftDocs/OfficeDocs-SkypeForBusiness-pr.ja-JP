---
title: Servers テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1535e676-a647-4606-bc56-e8bfde5ca823
description: Servers テーブルは、さまざまなサーバーに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのサーバーを表します。
ms.openlocfilehash: acbc929c1c47ebf86e1b58f4c008f4351de35496
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809947"
---
# <a name="servers-table"></a>Servers テーブル
 
Servers テーブルは、さまざまなサーバーに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのサーバーを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ServerId** <br/> |int  <br/> |Primary  <br/> |このサーバーを識別する一意の番号。  <br/> |
|**ServerFQDN** <br/> |nvarchar(256)  <br/> | <br/> |サーバーの FQDN。  <br/> |
   

