---
title: DeviceDriver テーブル
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: DeviceDriver テーブルは、サポート テーブルです。 各レコードは、キャプチャ デバイスまたはレンダー デバイスが使用するドライバーを表します。
ms.openlocfilehash: 1f83bfd014fa5fb49f4d0f900e01aeecfe2b5f46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823077"
---
# <a name="devicedriver-table"></a>DeviceDriver テーブル
 
DeviceDriver テーブルは、サポート テーブルです。各レコードは、キャプチャ デバイスまたはレンダー デバイスが使用するドライバーを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceDriverKey** <br/> |int  <br/> |Primary  <br/> |このデバイス ドライバー レコードを識別する一意の番号。  <br/> |
|**DeviceDriver** <br/> |varchar(256)  <br/> |unique  <br/> |デバイス ドライバー名。  <br/> |
   

