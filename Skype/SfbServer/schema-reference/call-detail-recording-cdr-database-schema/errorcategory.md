---
title: ErrorCategory テーブル (Skype for Business Server 2015)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory テーブルには、2015 年の診断Skype for Business Serverの名前が含まれている。 既定では、Skype for Business Server 2015 は次の分類を使用します。
ms.openlocfilehash: 19fa265b337f293656473aa24c85bb5fc22008de
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743913"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>ErrorCategory テーブル (Skype for Business Server 2015)
 
ErrorCategory テーブルには、2015 年の診断Skype for Business Serverの名前が含まれている。 既定では、Skype for Business Server 2015 は次の分類を使用します。
  
- 0 -- 成功
    
- 1 -- 予期されるエラー
    
- 2 - 予期しないエラー
    
この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primary  <br/> |分類の一意の識別子。  <br/> |
|**名前** <br/> |nvarchar(256)  <br/> || 分類に割り当てられる値とフレンドリ名。有効な値は次のとおりです。 <br/>  0 -- 成功 <br/>  1 -- 予期されるエラー <br/>  2 - 予期しないエラー <br/> |
   

