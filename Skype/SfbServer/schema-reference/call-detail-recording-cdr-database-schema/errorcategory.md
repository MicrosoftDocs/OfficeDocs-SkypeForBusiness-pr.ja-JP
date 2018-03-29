---
title: ビジネス サーバー 2015 の Skype での ErrorCategory テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory テーブルには、ビジネス サーバー 2015 診断分類の各 Skype のフレンドリ名が含まれています。 ビジネス サーバー 2015 の Skype は、既定では、次の分類を使用します。
ms.openlocfilehash: 23df7ecb7e10dc104e6274edb762369ad539f8fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での ErrorCategory テーブル
 
ErrorCategory テーブルには、ビジネス サーバー 2015 診断分類の各 Skype のフレンドリ名が含まれています。 ビジネス サーバー 2015 の Skype は、既定では、次の分類を使用します。
  
- 0 - 成功
    
- 1-予想される障害
    
- 2-予期しないエラー
    
このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**[区分コード]** <br/> |tinyint  <br/> |Primary  <br/> |分類の一意の識別子です。  <br/> |
|**名** <br/> |nvarchar(256)  <br/> || 値および分類に割り当てられたフレンドリ名です。 有効な値は次のとおりです。 <br/>  0 - 成功 <br/>  1-予想される障害 <br/>  2-予期しないエラー <br/> |
   

