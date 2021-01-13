---
title: Device テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device テーブルは、さまざまなキャプチャデバイスまたはレンダー デバイスに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのデバイスを表します。
ms.openlocfilehash: 818458e41c71398f3df11ac9a47eeee0841c6dca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814747"
---
# <a name="device-table"></a>Device テーブル
 
Device テーブルは、さまざまなキャプチャデバイスまたはレンダー デバイスに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのデバイスを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |このデバイスを識別する一意の番号。  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType が一意である  <br/> |デバイス名。  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType が一意である  <br/> |デバイスの種類。 1 はキャプチャ デバイス、0 はレンダー デバイスです。  <br/> |
   

