---
title: ビジネス サーバー 2015 の Skype でゲートウェイ テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: ゲートウェイはテーブルをサポートします。 各レコードは、データベースにレコードがある公衆交換電話網 (PSTN) の呼び出しが関係している 1 つのゲートウェイに関する情報を格納します。
ms.openlocfilehash: 2a3429b45a63c0c7765f4e9da0ea2baf3f0d11b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901039"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype でゲートウェイ テーブル
 
ゲートウェイはテーブルをサポートします。 各レコードは、データベースにレコードがある公衆交換電話網 (PSTN) の呼び出しが関係している 1 つのゲートウェイに関する情報を格納します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |このゲートウェイを識別する一意の番号です。  <br/> |
|**ゲートウェイ** <br/> |nvarchar(256)  <br/> | <br/> |ゲートウェイの名前。  <br/> |
   

