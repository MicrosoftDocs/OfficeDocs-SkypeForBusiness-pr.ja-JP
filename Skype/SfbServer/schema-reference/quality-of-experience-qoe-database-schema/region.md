---
title: Region テーブル
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
ms.assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
description: Region テーブルはサポートテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つの国/地域を表します。
ms.openlocfilehash: 8e3a0bbe37b1197bae1f35b8fc2ac05f54c5846d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806225"
---
# <a name="region-table"></a>Region テーブル
 
Region テーブルはサポートテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つの国/地域を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**RegionKey** <br/> |int  <br/> |Primary  <br/> |国または地域を識別する一意の番号。  <br/> |
|**RegionName** <br/> |nvarchar(128  <br/> |一意  <br/> |国または地域の名前。  <br/> |
   

