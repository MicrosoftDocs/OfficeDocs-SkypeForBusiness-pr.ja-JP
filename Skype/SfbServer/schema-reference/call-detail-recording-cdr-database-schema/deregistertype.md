---
title: DeRegisterType テーブル (2015 Skype for Business Server)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType テーブルは、"クライアントが開始されました"、"登録が期限切れ"、"クライアントが応答を停止しました" など、登録を解除できるユーザーの種類の一覧を格納する静的テーブルです。
ms.openlocfilehash: 4ce03a677ed275a925c56fe29b729fa2ead3eff3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845070"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>DeRegisterType テーブル (2015 Skype for Business Server)
 
DeRegisterType テーブルは、"クライアントが開始されました"、"登録が期限切れ"、"クライアントが応答を停止しました" など、登録を解除できるユーザーの種類の一覧を格納する静的テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || 有効な値は次のとおりです。 <br/>  0 -- 不明 <br/>  1 -- クライアントが登録解除を開始済み <br/>  2 -- 登録期限切れ <br/>  3 - クライアントがクラッシュしました <br/>  4 -- ユーザー属性変更 <br/>  5 - 優先レジストラーの変更 <br/>  6 -- サバイバル モードのレガシ クライアント <br/> |
   

