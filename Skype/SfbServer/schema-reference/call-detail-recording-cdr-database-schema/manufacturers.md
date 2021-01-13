---
title: Skype for Business Server 2015 の Manufacturers テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 734608b3-5a3a-4b61-87dc-9a8551401d06
description: Manufacturers テーブルはサポート テーブルです。 各レコードには、1 つのデバイス (電話) 製造元に関する情報が格納されます。
ms.openlocfilehash: f3cdd6e33732eb226cc2d99ff403495ac19f5567
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821487"
---
# <a name="manufacturers-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の Manufacturers テーブル
 
Manufacturers テーブルはサポート テーブルです。 各レコードには、1 つのデバイス (電話) 製造元に関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ManufacturerId** <br/> |int  <br/> |Primary  <br/> |この製造元を識別する一意の番号。  <br/> |
|**製造元** <br/> |nvarchar(256)  <br/> | <br/> |製造元名。  <br/> |
   

