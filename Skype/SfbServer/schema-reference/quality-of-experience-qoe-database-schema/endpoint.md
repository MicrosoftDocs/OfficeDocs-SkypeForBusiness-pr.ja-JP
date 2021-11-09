---
title: エンドポイント テーブル
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Endpoint テーブルは、データベースに記録されたセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのエンドポイントを表します。
ms.openlocfilehash: 7e892d0e913f8b06fc78f00fbbb348774b9548d3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834003"
---
# <a name="endpoint-table"></a>エンドポイント テーブル
 
Endpoint テーブルは、データベースに記録されたセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのエンドポイントを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |このエンドポイントを識別する一意の番号。  <br/> |
|**名前** <br/> |nvarchar(256)  <br/> |一意  <br/> |エンドポイント名。  <br/> |
|**OS** <br/> |nvarchar(128)  <br/> | <br/> |エンドポイントのオペレーティング システム (OS)。  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||エンドポイントの CPU 名。  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||エンドポイントの CPU コアの数。  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||エンドポイントの CPU プロセッサ速度。  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || システムが仮想化環境で実行されているかどうかを示すビット フラグ。 <br/>  0x0000 - なし <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 - 仮想 PC <br/>  0x0008 - Xen PC <br/> |
   

