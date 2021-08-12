---
title: 2015 年Skype for Business Serverデバイス の表
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
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices テーブルは、サポート テーブルです。各レコードには、1 つのデバイス (卓上電話) に関する情報が格納されます。
ms.openlocfilehash: eac31407de3f5a648ebe5f3819b2d7f3556e9bd6c2be930450e8e27700ead178
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295374"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>2015 年Skype for Business Serverデバイス の表
 
Devices テーブルは、サポート テーブルです。各レコードには、1 つのデバイス (卓上電話) に関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |整数  <br/> |Primary  <br/> |このハードウェア バージョンを識別する一意の番号。  <br/> |
|**ManufacturerId** <br/> |整数  <br/> |外部  <br/> |このデバイスの製造元。 詳細については[、2015](manufacturers.md) Skype for Business Serverの製造元の表を参照してください。 <br/> |
|**HardwareVersionId** <br/> |整数  <br/> |外部  <br/> |このデバイスのハードウェア バージョン。 詳細については[、2015 Skype for Business Server HardwareVersions の](hardwareversions.md)表を参照してください。 <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC アドレス  <br/> |
   

