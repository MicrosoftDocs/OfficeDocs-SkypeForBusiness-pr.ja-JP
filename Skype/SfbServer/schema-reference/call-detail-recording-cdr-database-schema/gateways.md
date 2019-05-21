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
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: ゲートウェイテーブルは、サポートされているテーブルです。 各レコードには、データベース内にレコードがある公衆交換電話網 (PSTN) 通話に関連する1つのゲートウェイに関する情報が格納されます。
ms.openlocfilehash: 6c827b6661e6dadd0550506f1e593462ec9d8c7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296183"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 のゲートウェイテーブル
 
ゲートウェイテーブルは、サポートされているテーブルです。 各レコードには、データベース内にレコードがある公衆交換電話網 (PSTN) 通話に関連する1つのゲートウェイに関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |このゲートウェイを識別する一意の番号。  <br/> |
|**ゲートウェイ** <br/> |nvarchar(256)  <br/> | <br/> |ゲートウェイ名。  <br/> |
   

