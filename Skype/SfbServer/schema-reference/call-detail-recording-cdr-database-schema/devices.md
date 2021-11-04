---
title: 2015 年Skype for Business Serverデバイス の表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices テーブルは、サポート テーブルです。各レコードには、1 つのデバイス (卓上電話) に関する情報が格納されます。
ms.openlocfilehash: c7662663625937a0ad0c7cc023620798f0398e49
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743973"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>2015 年Skype for Business Serverデバイス の表
 
Devices テーブルは、サポート テーブルです。各レコードには、1 つのデバイス (卓上電話) に関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |このハードウェア バージョンを識別する一意の番号。  <br/> |
|**ManufacturerId** <br/> |int  <br/> |外部  <br/> |このデバイスの製造元。 詳細については[、2015](manufacturers.md) Skype for Business Serverの製造元の表を参照してください。 <br/> |
|**HardwareVersionId** <br/> |int  <br/> |外部  <br/> |このデバイスのハードウェア バージョン。 詳細については[、2015 Skype for Business Server HardwareVersions の](hardwareversions.md)表を参照してください。 <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC アドレス  <br/> |
   

