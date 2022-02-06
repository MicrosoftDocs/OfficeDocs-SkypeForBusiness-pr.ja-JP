---
title: デバイス テーブル
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device テーブルは、さまざまなキャプチャデバイスまたはレンダリング デバイスに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのデバイスを表します。
---

# <a name="device-table"></a>デバイス テーブル
 
Device テーブルは、さまざまなキャプチャデバイスまたはレンダリング デバイスに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのデバイスを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |このデバイスを識別する一意の番号。  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType は一意です  <br/> |デバイス名。  <br/> |
|**DeviceType** <br/> |ビット  <br/> |DeviceName + DeviceType は一意です  <br/> |デバイスの種類。 1 はキャプチャ デバイス、0 はレンダー デバイスです。  <br/> |
   

