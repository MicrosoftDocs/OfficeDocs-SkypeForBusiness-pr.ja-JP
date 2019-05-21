---
title: Skype for Business Server 2015 の Devices テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices テーブルは、サポートテーブルです。 各レコードには、1つのデバイス (卓上電話) に関する情報が格納されます。
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296379"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の Devices テーブル
 
Devices テーブルは、サポートテーブルです。 各レコードには、1つのデバイス (卓上電話) に関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |このハードウェアバージョンを識別する一意の番号。  <br/> |
|**Manufacturerid]** <br/> |int  <br/> |外部  <br/> |このデバイスの製造元。 詳細については、「 [Skype For Business Server 2015 の製造元の表](manufacturers.md)」を参照してください。 <br/> |
|**ハードウェアの Versionid** <br/> |int  <br/> |外部  <br/> |このデバイスのハードウェアバージョン。 詳細については、「 [Skype For Business Server 2015 のハードウェアバージョン](hardwareversions.md)」の表を参照してください。 <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC アドレス  <br/> |
   

