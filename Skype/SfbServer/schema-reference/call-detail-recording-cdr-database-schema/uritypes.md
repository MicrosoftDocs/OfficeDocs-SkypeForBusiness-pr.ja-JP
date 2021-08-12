---
title: UriTypes テーブル
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
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes テーブルには、2015 年に監視されるさまざまな URI (統一リソース識別子) Skype for Business Serverがあります。
ms.openlocfilehash: 1e98bc879e7ddb6e2ca92d4f226284e604d22d312f9e2db8c0ff80cad89c33e5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295364"
---
# <a name="uritypes-table"></a>UriTypes テーブル
 
UriTypes テーブルには、2015 年に監視されるさまざまな URI (統一リソース識別子) Skype for Business Serverがあります。

CDR DB が作成されると、PhoneUri と UserUri を表す 2 つのレコードが作成され、その後に作成されたレコードは UriTypeId に動的に割り当てられます。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |URI の種類に割り当てられている一意の ID です。  <br/> 指定できる値 - 0 ~ 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || URI の種類の説明です。 次の値が事前に割り当てられます。 <br/>  1 - uri 電話 Uri <br/>  0 - ユーザー Uri <br/> <br/>  その他の可能な種類は次のとおりです。 <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
