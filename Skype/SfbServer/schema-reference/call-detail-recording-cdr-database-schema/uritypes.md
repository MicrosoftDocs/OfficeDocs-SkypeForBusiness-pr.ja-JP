---
title: UriTypes テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes テーブルには、URI (一意リソース識別子)、各種ビジネス サーバー 2015 の Skype の監視が含まれています。
ms.openlocfilehash: 72704715ff5e5fd3a354b75b0aa6baff45ecea54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930270"
---
# <a name="uritypes-table"></a>UriTypes テーブル
 
UriTypes テーブルには、URI (一意リソース識別子)、各種ビジネス サーバー 2015 の Skype の監視が含まれています。

CDR データベースが作成されると、PhoneUri と UserUri を表す 2 つのレコードが作成され、レコードの作成後、UriTypeId を動的に割り当てられています。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |URI の種類に割り当てられている一意の識別子です。  <br/> 使用可能な値の 0 から 255 まで |
|**UriType** <br/> |nvarchar(256)  <br/> || URI の種類の説明です。 次の値は、事前に割り当てられています。 <br/>  1-電話の Uri <br/>  0 - ユーザーの Uri <br/> <br/>  使用可能なその他の型は次のとおりです。 <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
