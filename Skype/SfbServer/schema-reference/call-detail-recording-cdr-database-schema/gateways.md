---
title: ビジネス サーバー 2015 の Skype でゲートウェイ テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: ゲートウェイはテーブルをサポートします。 各レコードは、データベースにレコードがある公衆交換電話網 (PSTN) の呼び出しが関係している 1 つのゲートウェイに関する情報を格納します。
ms.openlocfilehash: 16860e924fb69f1dfe337e05c13d54fb66a8ed81
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899082"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype でゲートウェイ テーブル
 
ゲートウェイはテーブルをサポートします。 各レコードは、データベースにレコードがある公衆交換電話網 (PSTN) の呼び出しが関係している 1 つのゲートウェイに関する情報を格納します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |このゲートウェイを識別する一意の番号です。  <br/> |
|**ゲートウェイ** <br/> |nvarchar(256)  <br/> | <br/> |ゲートウェイの名前。  <br/> |
   

