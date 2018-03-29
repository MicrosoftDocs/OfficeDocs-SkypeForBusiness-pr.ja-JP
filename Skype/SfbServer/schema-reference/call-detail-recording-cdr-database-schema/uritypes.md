---
title: UriTypes テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes テーブルには、URI (一意リソース識別子)、各種ビジネス サーバー 2015 の Skype の監視が含まれています。
ms.openlocfilehash: 00c70c166716ad879257e7b18db80dd760ce4ec4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="uritypes-table"></a>UriTypes テーブル
 
UriTypes テーブルには、URI (一意リソース識別子)、各種ビジネス サーバー 2015 の Skype の監視が含まれています。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |URI の種類に割り当てられている一意の識別子です。  <br/> |
|**UriType** <br/> |nvarchar(256)  <br/> || URI の種類の説明です。 有効な値は次のとおりです。 <br/>  0 - 電話の Uri <br/>  1-ユーザーの Uri <br/> |
   

