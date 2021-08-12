---
title: デバイス テーブル
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
description: Device テーブルは、さまざまなキャプチャデバイスまたはレンダリング デバイスに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのデバイスを表します。
ms.openlocfilehash: d060ec010cc67ea45fb2f7c58ccc574a7bdbc4ea566342943f7a8f587a9676f5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347732"
---
# <a name="device-table"></a>デバイス テーブル
 
Device テーブルは、さまざまなキャプチャデバイスまたはレンダリング デバイスに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのデバイスを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |整数  <br/> |Primary  <br/> |このデバイスを識別する一意の番号。  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType は一意です  <br/> |デバイス名。  <br/> |
|**DeviceType** <br/> |ビット  <br/> |DeviceName + DeviceType は一意です  <br/> |デバイスの種類。 1 はキャプチャ デバイス、0 はレンダー デバイスです。  <br/> |
   

