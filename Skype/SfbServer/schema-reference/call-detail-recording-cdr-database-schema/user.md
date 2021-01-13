---
title: ユーザー ビュー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: ユーザー ビューには、データベース内にレコードのある通話またはセッションに関係するユーザーについての情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831697"
---
# <a name="user-view"></a>ユーザー ビュー
 
ユーザー ビューには、データベース内にレコードのある通話またはセッションに関係するユーザーについての情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |このユーザーを識別する一意の番号。  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |ユーザーの URI。  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |ユーザーのテナント。 詳細については [、「テナント」の表](tenants.md) を参照してください。 <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |ユーザー URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
   

