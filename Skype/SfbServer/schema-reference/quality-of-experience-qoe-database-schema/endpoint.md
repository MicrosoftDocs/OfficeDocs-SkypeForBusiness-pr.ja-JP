---
title: Endpoint テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: エンドポイントテーブルは、データベースに記録されているセッションに参加しているエンドポイントに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのエンドポイントを表します。
ms.openlocfilehash: b64b19a3149fa3d490ea8dc957699c0a114f763c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809555"
---
# <a name="endpoint-table"></a>Endpoint テーブル
 
エンドポイントテーブルは、データベースに記録されているセッションに参加しているエンドポイントに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのエンドポイントを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |このエンドポイントを識別する一意の番号です。  <br/> |
|**名前** <br/> |nvarchar(256)  <br/> |一意  <br/> |エンドポイント名。  <br/> |
|**OS** <br/> |nvarchar(128  <br/> | <br/> |エンドポイントのオペレーティングシステム (OS)。  <br/> |
|**CPUName** <br/> |nvarchar(128  <br/> ||エンドポイントの CPU 名。  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||エンドポイントの CPU コアの数。  <br/> |
|**プロセッサーの速度** <br/> |int  <br/> ||エンドポイントの CPU プロセッサの速度。  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || システムが仮想環境で実行されているかどうかを示すビットフラグ。 <br/>  0x0000-なし <br/>  0x0001-HyperV <br/>  0x0002-ヴイエムウェア <br/>  0x0004-仮想 PC <br/>  0x0008-Xen PC <br/> |
   

