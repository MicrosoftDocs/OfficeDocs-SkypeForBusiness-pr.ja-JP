---
title: UserSite テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite テーブルはサポート テーブルです。各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。
ms.openlocfilehash: 5e7ae6f304d836fc2413cbbaf696200c3f514bd1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595267"
---
# <a name="usersite-table"></a>UserSite テーブル
 
UserSite テーブルはサポート テーブルです。各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |ユーザー サイトを示す一意の番号です。  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |一意  <br/> |ユーザー サイトの名前。  <br/> |
|**RegionKey** <br/> |int  <br/> |外部  <br/> |Region テーブル [から参照されます](region.md)。  <br/> |
   

