---
title: Device テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: デバイス テーブルがさまざまなキャプチャの情報を格納するサポート テーブルまたはデバイスを表示します。 テーブル内の各レコードは、1 つのデバイスを表します。
ms.openlocfilehash: 0b3c27708cd8e9d1b02914e6f2cba414e353609c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920027"
---
# <a name="device-table"></a>Device テーブル
 
デバイス テーブルがさまざまなキャプチャの情報を格納するサポート テーブルまたはデバイスを表示します。 テーブル内の各レコードは、1 つのデバイスを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |このデバイスを識別する一意の番号です。  <br/> |
|**デバイス名** <br/> |nvarchar(256)  <br/> |デバイス名 + DeviceType が一意では  <br/> |デバイスの名前です。  <br/> |
|**DeviceType** <br/> |bit  <br/> |デバイス名 + DeviceType が一意では  <br/> |デバイスの種類。 キャプチャ デバイスは、1、0 は、レンダリング デバイスです。  <br/> |
   

