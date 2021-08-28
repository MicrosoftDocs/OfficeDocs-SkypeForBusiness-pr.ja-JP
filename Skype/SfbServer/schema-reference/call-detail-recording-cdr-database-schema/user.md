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
ms.localizationpriority: medium
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: ユーザー ビューには、データベース内にレコードのある通話またはセッションに関係するユーザーについての情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 59b7371336ec900d6474016bb366407d4ffb7c14
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616383"
---
# <a name="user-view"></a>ユーザー ビュー
 
ユーザー ビューには、データベース内にレコードのある通話またはセッションに関係するユーザーについての情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |このユーザーを識別する一意の番号。  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |ユーザーの URI。  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |ユーザーのテナント。 詳細については [、「Tenants」テーブル](tenants.md) を参照してください。 <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |ユーザー URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
   

