---
title: ビジネス サーバー 2015 の Skype でデバイス ・ テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: デバイス ・ テーブルは、関連テーブルです。 各レコードは、1 つのデバイス (机上電話) に関する情報を格納します。
ms.openlocfilehash: f770f19fb94bf25bdb4c13e74dc41e05f6674788
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213166"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype でデバイス ・ テーブル
 
デバイス ・ テーブルは、関連テーブルです。 各レコードは、1 つのデバイス (机上電話) に関する情報を格納します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |このハードウェアのバージョンを識別する一意の番号です。  <br/> |
|**ManufacturerId** <br/> |int  <br/> |外部  <br/> |このデバイスの製造元です。 詳細については、 [Skype のビジネス サーバー 2015 の製造元テーブル](manufacturers.md)を参照してください。 <br/> |
|**HardwareVersionId** <br/> |int  <br/> |外部  <br/> |このデバイスのハードウェア バージョンです。 詳細については、 [Skype のビジネス サーバー 2015 で HardwareVersions テーブル](hardwareversions.md)を参照してください。 <br/> |
|**MacAddress** <br/> |bigint 型の値  <br/> ||MAC アドレス  <br/> |
   

