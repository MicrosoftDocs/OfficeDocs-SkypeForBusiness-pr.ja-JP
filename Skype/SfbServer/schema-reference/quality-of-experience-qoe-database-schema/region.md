---
title: 地域テーブル
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
localization_priority: Normal
ms.assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
description: Region テーブルはサポート テーブルです。各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。
ms.openlocfilehash: 538d574037d7cd3798b63c6d8773f99e1c376d9f5ad115f73bfa725a9aec6b55
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341662"
---
# <a name="region-table"></a>地域テーブル
 
Region テーブルはサポート テーブルです。各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**RegionKey** <br/> |整数  <br/> |Primary  <br/> |国/地域を示す一意の番号です。  <br/> |
|**RegionName** <br/> |nvarchar(128)  <br/> |一意  <br/> |国/地域の名前です。  <br/> |
   

