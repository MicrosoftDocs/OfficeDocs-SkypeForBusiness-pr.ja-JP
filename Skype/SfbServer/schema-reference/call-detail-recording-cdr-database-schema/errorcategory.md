---
title: Skype for Business Server 2015 の ErrorCategory テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory テーブルには、各 Skype for Business Server 2015 診断分類の表示名が含まれる。 既定では、Skype for Business Server 2015 は次の分類を使用します。
ms.openlocfilehash: ca3719f6d284cf715be1a87b1c7a5dc04ae84b04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813147"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ErrorCategory テーブル
 
ErrorCategory テーブルには、各 Skype for Business Server 2015 診断分類の表示名が含まれる。 既定では、Skype for Business Server 2015 は次の分類を使用します。
  
- 0 -- 成功
    
- 1 -- 予期されるエラー
    
- 2 - 予期しないエラー
    
この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primary  <br/> |分類の一意の識別子。  <br/> |
|**名前** <br/> |nvarchar(256)  <br/> || 分類に割り当てられる値とフレンドリ名。有効な値は次のとおりです。 <br/>  0 -- 成功 <br/>  1 -- 予期されるエラー <br/>  2 - 予期しないエラー <br/> |
   

