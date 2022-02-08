---
title: UriTypes テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes テーブルには、2015 年に監視されるさまざまな URI (統一リソース識別子) Skype for Business Serverがあります。
ms.openlocfilehash: 196207a60bd738b4ef987248d53356b3f20336e8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394879"
---
# <a name="uritypes-table"></a>UriTypes テーブル
 
UriTypes テーブルには、2015 年に監視されるさまざまな URI (統一リソース識別子) Skype for Business Serverがあります。

CDR DB が作成されると、PhoneUri と UserUri を表す 2 つのレコードが作成され、その後に作成されたレコードは UriTypeId に動的に割り当てられます。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |URI の種類に割り当てられている一意の ID です。  <br/> 指定できる値 - 0 ~ 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || URI の種類の説明です。 次の値が事前に割り当てられます。 <br/>  1 - uri 電話 Uri <br/>  0 - ユーザー Uri <br/> <br/>  その他の可能な種類は次のとおりです。 <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
