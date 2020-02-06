---
title: Skype for Business Server 2015 のゲートウェイテーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: ゲートウェイテーブルは、サポートされているテーブルです。 各レコードには、データベース内にレコードがある公衆交換電話網 (PSTN) 通話に関連する1つのゲートウェイに関する情報が格納されます。
ms.openlocfilehash: ce85b36d5ad587a096c99ca3f3f496642d3a3dd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815165"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 のゲートウェイテーブル
 
ゲートウェイテーブルは、サポートされているテーブルです。 各レコードには、データベース内にレコードがある公衆交換電話網 (PSTN) 通話に関連する1つのゲートウェイに関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |このゲートウェイを識別する一意の番号。  <br/> |
|**ゲートウェイ** <br/> |nvarchar(256)  <br/> | <br/> |ゲートウェイ名。  <br/> |
   

