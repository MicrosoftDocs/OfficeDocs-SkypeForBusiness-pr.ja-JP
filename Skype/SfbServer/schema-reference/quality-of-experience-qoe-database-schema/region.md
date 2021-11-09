---
title: 地域テーブル
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
description: Region テーブルはサポート テーブルです。各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。
ms.openlocfilehash: 9fe5d69e2f9a7e3e33362bf01d6969420855884f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828500"
---
# <a name="region-table"></a>地域テーブル
 
Region テーブルはサポート テーブルです。各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**RegionKey** <br/> |int  <br/> |Primary  <br/> |国/地域を示す一意の番号です。  <br/> |
|**RegionName** <br/> |nvarchar(128)  <br/> |一意  <br/> |国/地域の名前です。  <br/> |
   

