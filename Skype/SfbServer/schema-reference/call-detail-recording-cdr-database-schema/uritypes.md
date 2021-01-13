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
description: UriTypes テーブルには、Skype for Business Server 2015 で監視されるさまざまな URI (Uniform resource identifier) の種類が含まれています。
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831687"
---
# <a name="uritypes-table"></a>UriTypes テーブル
 
UriTypes テーブルには、Skype for Business Server 2015 で監視されるさまざまな URI (Uniform resource identifier) の種類が含まれています。

CDR DB が作成されると、PhoneUri と UserUri を表す 2 つのレコードが作成され、その後に作成されたレコードには UriTypeId が動的に割り当てられます。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |URI の種類に割り当てられている一意の ID です。  <br/> 指定可能な値 - 0 ~ 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || URI の種類の説明です。 次の値が事前に割り当てられます。 <br/>  1 - 電話 URI <br/>  0 - ユーザー URI <br/> <br/>  その他の種類には、次のものがあります。 <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
