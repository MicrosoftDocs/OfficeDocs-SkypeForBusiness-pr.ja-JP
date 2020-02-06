---
title: UriTypes テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814845"
---
# <a name="uritypes-table"></a>UriTypes テーブル
 
UriTypes テーブルには、Skype for Business Server 2015 で監視されるさまざまな URI (Uniform resource identifier) の種類が含まれています。

CDR DB が作成されると、電話の Uri と UserUri を表す2つのレコードが作成され、その後に作成されたレコードが UriTypeId に動的に割り当てられます。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |URI 型に割り当てられている一意の識別子。  <br/> 指定可能な値-0 ~ 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || 各種の URI の種類について説明します。 次の値が事前に割り当てられています。 <br/>  1-電話の Uri <br/>  0-ユーザー Uri <br/> <br/>  他にも次のような種類があります。 <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf: チャット<br/>    conf:focus<br/>   mras<br/>
