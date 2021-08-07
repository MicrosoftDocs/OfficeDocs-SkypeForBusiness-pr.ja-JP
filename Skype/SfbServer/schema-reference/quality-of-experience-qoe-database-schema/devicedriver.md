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
description: DeviceDriver テーブルは、サポート テーブルです。各レコードは、キャプチャ デバイスまたはレンダー デバイスが使用するドライバーを表します。
ms.openlocfilehash: 49bf941de3c0639552bd01e5066c9b823953ca7d4c01acc1b77a973045d89985
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276572"
---
# <a name="devicedriver-table"></a>DeviceDriver テーブル
 
DeviceDriver テーブルは、サポート テーブルです。各レコードは、キャプチャ デバイスまたはレンダー デバイスが使用するドライバーを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceDriverKey** <br/> |整数  <br/> |Primary  <br/> |このデバイス ドライバー レコードを識別する一意の番号。  <br/> |
|**DeviceDriver** <br/> |varchar(256)  <br/> |unique  <br/> |デバイス ドライバー名。  <br/> |
   

