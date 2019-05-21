---
title: Skype for Business Server 2015 の ErrorCategory テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory テーブルには、各 Skype for Business Server 2015 診断分類のフレンドリ名が含まれています。 既定では、Skype for Business Server 2015 には次のような分類が使用されます。
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296288"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ErrorCategory テーブル
 
ErrorCategory テーブルには、各 Skype for Business Server 2015 診断分類のフレンドリ名が含まれています。 既定では、Skype for Business Server 2015 には次のような分類が使用されます。
  
- 0--成功
    
- 1--予期しないエラー
    
- 2-予期しないエラーが発生した
    
この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**区分** <br/> |tinyint  <br/> |Primary  <br/> |分類の一意の識別子。  <br/> |
|**名前** <br/> |nvarchar(256)  <br/> || 分類に割り当てられている値とフレンドリ名。 有効な値は次のとおりです。 <br/>  0--成功 <br/>  1--予期しないエラー <br/>  2-予期しないエラーが発生した <br/> |
   

