---
title: EndpointSubnet テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet テーブルは、サポート テーブルです。各レコードは、エンドポイントから取得された 1 つのサブネットを表します。
ms.openlocfilehash: 2d19ef746f67e4f5420d99686bc7f8485ee7dc78
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390849"
---
# <a name="endpointsubnet-table"></a>EndpointSubnet テーブル
 
EndpointSubnet テーブルは、サポート テーブルです。各レコードは、エンドポイントから取得された 1 つのサブネットを表します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主/プライマリ、外部  <br/> |サブネットの整数表現。  <br/> |
|**NextUpdateTS** <br/> |日付型  <br/> ||内部使用のみ。  <br/> |
   

