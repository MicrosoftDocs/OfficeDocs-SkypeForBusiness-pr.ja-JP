---
title: Conference テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会議の表は、サポートされているテーブルです。 各レコードは、1つの会議またはピアツーピアセッションを表します。
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810305"
---
# <a name="conference-table"></a>Conference テーブル
 
会議の表は、サポートされているテーブルです。 各レコードは、1つの会議またはピアツーピアセッションを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |この会議レコードを識別する一意の番号です。  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |一意  <br/> |会議の URI (会議の場合) または [この Id がピアツーピアセッションの場合] です。  <br/> |
|**サム** <br/> |int  <br/> |位置  <br/> |会議 URI のチェックサム。 これは内部的に使用されます。  <br/> |
|**Nextupdatupdat** <br/> |datetime  <br/> ||内部使用のみ。  <br/> |
   

