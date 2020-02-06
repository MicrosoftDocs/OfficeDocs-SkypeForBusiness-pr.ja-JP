---
title: Skype for Business Server 2015 の EdgeServers テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers テーブルは、サポートテーブルです。 各レコードには、データベース内のレコードが含まれる通話に関連する1つの Edge サーバーに関する情報が格納されます。
ms.openlocfilehash: 7a1621e3416b6cff48c430e7bc2e45057ecb3e14
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815265"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の EdgeServers テーブル
 
EdgeServers テーブルは、サポートテーブルです。 各レコードには、データベース内のレコードが含まれる通話に関連する1つの Edge サーバーに関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |int  <br/> |Primary  <br/> |このエッジサーバーを識別する一意の番号。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> | <br/> |エッジサーバー名。  <br/> |
   

