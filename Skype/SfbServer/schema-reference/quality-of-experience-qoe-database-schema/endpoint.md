---
title: Endpoint テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: エンドポイントはデータベースに記録されているセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのエンドポイントを表します。
ms.openlocfilehash: f9c304408006ef9caf5521b8f0bbe28c2d917abe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212243"
---
# <a name="endpoint-table"></a>Endpoint テーブル
 
エンドポイントはデータベースに記録されているセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのエンドポイントを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |このエンドポイントを識別する一意の番号です。  <br/> |
|**名前** <br/> |nvarchar(256)  <br/> |一意  <br/> |エンドポイントの名前です。  <br/> |
|**OS** <br/> |nvarchar (128)  <br/> | <br/> |エンドポイントのオペレーティング システム (OS)。  <br/> |
|**CPUName** <br/> |nvarchar (128)  <br/> ||エンドポイントの CPU の名前です。  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||エンドポイントの CPU コアの数です。  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||エンドポイントの CPU のプロセッサ速度です。  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || システムが仮想化環境で実行されているかどうかであることを示すビット フラグ。 <br/>  0x0000 - なし <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 - 仮想 PC <br/>  0x0008 - Xen PC <br/> |
   

