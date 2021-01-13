---
title: Skype for Business Server 2015 の Devices テーブル
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
description: Devices テーブルは、サポート テーブルです。 各レコードには、1 つのデバイス (卓上電話) に関する情報が格納されます。
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831817"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の Devices テーブル
 
Devices テーブルは、サポート テーブルです。 各レコードには、1 つのデバイス (卓上電話) に関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |このハードウェア バージョンを識別する一意の番号。  <br/> |
|**ManufacturerId** <br/> |int  <br/> |外部  <br/> |このデバイスの製造元。 詳細については [、Skype for Business Server 2015 の Manufacturers の表](manufacturers.md) を参照してください。 <br/> |
|**HardwareVersionId** <br/> |int  <br/> |外部  <br/> |このデバイスのハードウェア バージョン。 詳細については [、Skype for Business Server 2015 の HardwareVersions の表](hardwareversions.md) を参照してください。 <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC アドレス  <br/> |
   

