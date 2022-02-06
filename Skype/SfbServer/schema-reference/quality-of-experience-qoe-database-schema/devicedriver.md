---
title: DeviceDriver テーブル
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: DeviceDriver テーブルは、サポート テーブルです。各レコードは、キャプチャ デバイスまたはレンダー デバイスが使用するドライバーを表します。
---

# <a name="devicedriver-table"></a>DeviceDriver テーブル
 
DeviceDriver テーブルは、サポート テーブルです。各レコードは、キャプチャ デバイスまたはレンダー デバイスが使用するドライバーを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceDriverKey** <br/> |int  <br/> |Primary  <br/> |このデバイス ドライバー レコードを識別する一意の番号。  <br/> |
|**DeviceDriver** <br/> |varchar(256)  <br/> |unique  <br/> |デバイス ドライバー名。  <br/> |
   

