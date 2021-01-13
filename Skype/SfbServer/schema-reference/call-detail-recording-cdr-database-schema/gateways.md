---
title: Skype for Business Server 2015 の Gateways テーブル
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
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Gateways テーブルはサポート テーブルです。 各レコードには、データベース内にレコードがある公衆交換電話網 (PSTN) 通話に関係する 1 つのゲートウェイに関する情報が格納されます。
ms.openlocfilehash: e945e5464093eb0eb58965fa1ef8a734ea0afa75
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821587"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の Gateways テーブル
 
Gateways テーブルはサポート テーブルです。 各レコードには、データベース内にレコードがある公衆交換電話網 (PSTN) 通話に関係する 1 つのゲートウェイに関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |このゲートウェイを識別する一意の番号。  <br/> |
|**ゲートウェイ** <br/> |nvarchar(256)  <br/> | <br/> |ゲートウェイ名。  <br/> |
   

