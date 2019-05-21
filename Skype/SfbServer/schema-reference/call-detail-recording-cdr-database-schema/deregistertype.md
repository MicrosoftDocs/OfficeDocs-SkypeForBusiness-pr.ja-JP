---
title: Skype for Business Server 2015 の DeRegisterType テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType テーブルは、可能なユーザーのレジスタ型 ("クライアントで開始された"、"登録の期限切れ"、または "クライアントが応答を停止しました" など) の一覧を格納する静的テーブルです。
ms.openlocfilehash: 794f8f98ffe20cd69b63fd2084fee38ed055d40f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296351"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の DeRegisterType テーブル
 
DeRegisterType テーブルは、可能なユーザーのレジスタ型 ("クライアントで開始された"、"登録の期限切れ"、または "クライアントが応答を停止しました" など) の一覧を格納する静的テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || 許可される値: <br/>  0--不明 <br/>  1--クライアントが開始した登録解除 <br/>  2--登録が期限切れになりました <br/>  3-クライアントがクラッシュした <br/>  4--ユーザー属性が変更されました <br/>  5-優先レジストラーが変更されました <br/>  6--サバイバルモードでのレガシークライアント <br/> |
   

