---
title: EndpointSubnet テーブル
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
ms.localizationpriority: medium
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet テーブルは、サポート テーブルです。各レコードは、エンドポイントから取得された 1 つのサブネットを表します。
ms.openlocfilehash: 7d42985800af17a1cf73ac81a81990308537e04a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634131"
---
# <a name="endpointsubnet-table"></a>EndpointSubnet テーブル
 
EndpointSubnet テーブルは、サポート テーブルです。各レコードは、エンドポイントから取得された 1 つのサブネットを表します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主/プライマリ、外部  <br/> |サブネットの整数表現。  <br/> |
|**NextUpdateTS** <br/> |日付型  <br/> ||内部使用のみ。  <br/> |
   

