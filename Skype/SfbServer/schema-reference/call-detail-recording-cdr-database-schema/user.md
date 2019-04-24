---
title: ユーザーの表示
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: ユーザー ビューでは、呼び出しまたはデータベースのレコードが存在するセッションに関連するユーザーに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 9e631c101660e8f14bca25f019f5d991a0d9aadd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213180"
---
# <a name="user-view"></a>ユーザーの表示
 
ユーザー ビューでは、呼び出しまたはデータベースのレコードが存在するセッションに関連するユーザーに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|ユーザー Id  <br/> |int  <br/> |このユーザーを識別する一意の番号です。  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |ユーザーの Uri。  <br/> |
|TenantKey  <br/> |一意識別子  <br/> |ユーザーのテナントです。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |ユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
   

