---
title: Region テーブル
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
ms.assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
description: Region テーブルはサポート テーブルです。 各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。
ms.openlocfilehash: fe38d71c433e540a381e87d7952a8eb6d57ecb5b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834407"
---
# <a name="region-table"></a>Region テーブル
 
Region テーブルはサポート テーブルです。各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**RegionKey** <br/> |int  <br/> |Primary  <br/> |国/地域を示す一意の番号です。  <br/> |
|**RegionName** <br/> |nvarchar(128)  <br/> |一意  <br/> |国/地域の名前です。  <br/> |
   

