---
title: Endpoint テーブル
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
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Endpoint テーブルは、データベースに記録されたセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのエンドポイントを表します。
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823067"
---
# <a name="endpoint-table"></a>Endpoint テーブル
 
Endpoint テーブルは、データベースに記録されたセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのエンドポイントを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |このエンドポイントを識別する一意の番号。  <br/> |
|**名前** <br/> |nvarchar(256)  <br/> |一意  <br/> |エンドポイント名。  <br/> |
|**OS** <br/> |nvarchar(128)  <br/> | <br/> |エンドポイントのオペレーティング システム (OS)。  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||エンドポイントの CPU 名。  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||エンドポイントの CPU コアの数。  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||エンドポイントの CPU プロセッサ速度。  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || 仮想化環境でシステムが実行されるかどうかを示すビット フラグ: <br/>  0x0000 - なし <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 - 仮想 PC <br/>  0x0008 - Xen PC <br/> |
   

