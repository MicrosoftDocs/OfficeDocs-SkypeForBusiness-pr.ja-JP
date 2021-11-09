---
title: EndpointSubnet テーブル
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 41b6a6500f5b003cffd18afe09790e179cc771f0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839799"
---
# <a name="endpointsubnet-table"></a>EndpointSubnet テーブル
 
EndpointSubnet テーブルは、サポート テーブルです。各レコードは、エンドポイントから取得された 1 つのサブネットを表します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主/プライマリ、外部  <br/> |サブネットの整数表現。  <br/> |
|**NextUpdateTS** <br/> |日付型  <br/> ||内部使用のみ。  <br/> |
   

