---
title: DeRegisterType テーブル (2015 Skype for Business Server)
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType テーブルは、"クライアントが開始されました"、"登録が期限切れ"、"クライアントが応答を停止しました" など、登録を解除できるユーザーの種類の一覧を格納する静的テーブルです。
ms.openlocfilehash: 606065f0442043d660c917c61b89111b48679145088b4eba9a7a80e668248161
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347792"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>DeRegisterType テーブル (2015 Skype for Business Server)
 
DeRegisterType テーブルは、"クライアントが開始されました"、"登録が期限切れ"、"クライアントが応答を停止しました" など、登録を解除できるユーザーの種類の一覧を格納する静的テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || 有効な値は次のとおりです。 <br/>  0 -- 不明 <br/>  1 -- クライアントが登録解除を開始済み <br/>  2 -- 登録期限切れ <br/>  3 - クライアントがクラッシュしました <br/>  4 -- ユーザー属性変更 <br/>  5 - 優先レジストラーの変更 <br/>  6 -- サバイバル モードのレガシ クライアント <br/> |
   

