---
title: Device テーブル
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
ms.openlocfilehash: 346ea171b9a0c1b7a874b65a68b582c4167c57fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="device-table"></a>Device テーブル
 
デバイス テーブルがさまざまなキャプチャの情報を格納するサポート テーブルまたはデバイスを表示します。 テーブル内の各レコードは、1 つのデバイスを表します。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |このデバイスを識別する一意の番号です。  <br/> |
|**デバイス名** <br/> |nvarchar(256)  <br/> |デバイス名 + DeviceType が一意では  <br/> |デバイスの名前です。  <br/> |
|**DeviceType** <br/> |bit  <br/> |デバイス名 + DeviceType が一意では  <br/> |デバイスの種類。 キャプチャ デバイスは、1、0 は、レンダリング デバイスです。  <br/> |
   

