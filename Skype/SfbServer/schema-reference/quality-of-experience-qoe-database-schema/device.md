---
title: Device テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: デバイス テーブルがさまざまなキャプチャの情報を格納するサポート テーブルまたはデバイスを表示します。 テーブル内の各レコードは、1 つのデバイスを表します。
ms.openlocfilehash: 09af6ee11ebc821d123e847fbad812479d9d7bb0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885513"
---
# <a name="device-table"></a>Device テーブル
 
デバイス テーブルがさまざまなキャプチャの情報を格納するサポート テーブルまたはデバイスを表示します。 テーブル内の各レコードは、1 つのデバイスを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |このデバイスを識別する一意の番号です。  <br/> |
|**デバイス名** <br/> |nvarchar(256)  <br/> |デバイス名 + DeviceType が一意では  <br/> |デバイスの名前です。  <br/> |
|**DeviceType** <br/> |bit  <br/> |デバイス名 + DeviceType が一意では  <br/> |デバイスの種類。 キャプチャ デバイスは、1、0 は、レンダリング デバイスです。  <br/> |
   

