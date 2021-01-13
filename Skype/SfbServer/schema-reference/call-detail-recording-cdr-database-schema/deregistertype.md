---
title: Skype for Business Server 2015 の DeRegisterType テーブル
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
description: DeRegisterType テーブルは、"client initiated"、"registration expired"、"client stopped responding" など、考えられるユーザー登録解除タイプのリストを格納する静的テーブルです。
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816077"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の DeRegisterType テーブル
 
DeRegisterType テーブルは、"client initiated"、"registration expired"、"client stopped responding" など、考えられるユーザー登録解除タイプのリストを格納する静的テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || 有効な値は次のとおりです。 <br/>  0 -- 不明 <br/>  1 -- クライアントが登録解除を開始済み <br/>  2 -- 登録期限切れ <br/>  3 - クライアントがクラッシュしました <br/>  4 -- ユーザー属性変更 <br/>  5 - 優先レジストラーの変更 <br/>  6 -- サバイバル モードのレガシ クライアント <br/> |
   

