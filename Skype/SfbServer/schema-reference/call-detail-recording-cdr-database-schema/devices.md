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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices テーブルは、サポートテーブルです。 各レコードには、1つのデバイス (卓上電話) に関する情報が格納されます。
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815285"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の Devices テーブル
 
Devices テーブルは、サポートテーブルです。 各レコードには、1つのデバイス (卓上電話) に関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |このハードウェアバージョンを識別する一意の番号。  <br/> |
|**Manufacturerid]** <br/> |int  <br/> |外部  <br/> |このデバイスの製造元。 詳細については、「 [Skype For Business Server 2015 の製造元の表](manufacturers.md)」を参照してください。 <br/> |
|**ハードウェアの Versionid** <br/> |int  <br/> |外部  <br/> |このデバイスのハードウェアバージョン。 詳細については、「 [Skype For Business Server 2015 のハードウェアバージョン](hardwareversions.md)」の表を参照してください。 <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC アドレス  <br/> |
   

