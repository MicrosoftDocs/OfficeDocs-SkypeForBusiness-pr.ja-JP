---
title: DeviceDriver テーブル
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 31b847ce089ca042282ad04aa4af77fc0e6681c6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740273"
---
# <a name="devicedriver-table"></a>DeviceDriver テーブル
 
DeviceDriver テーブルは、サポート テーブルです。各レコードは、キャプチャ デバイスまたはレンダー デバイスが使用するドライバーを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeviceDriverKey** <br/> |int  <br/> |Primary  <br/> |このデバイス ドライバー レコードを識別する一意の番号。  <br/> |
|**DeviceDriver** <br/> |varchar(256)  <br/> |unique  <br/> |デバイス ドライバー名。  <br/> |
   

