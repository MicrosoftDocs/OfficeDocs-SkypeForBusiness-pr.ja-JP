---
title: エンドポイント テーブル
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
ms.openlocfilehash: 821f24ae2be38a699ce1c21255a66ec4a2fa2f17e448a1cc7b69a5a91d91d714
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302201"
---
# <a name="endpoint-table"></a>エンドポイント テーブル
 
Endpoint テーブルは、データベースに記録されたセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのエンドポイントを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |整数  <br/> |Primary  <br/> |このエンドポイントを識別する一意の番号。  <br/> |
|**名前** <br/> |nvarchar(256)  <br/> |一意  <br/> |エンドポイント名。  <br/> |
|**OS** <br/> |nvarchar(128)  <br/> | <br/> |エンドポイントのオペレーティング システム (OS)。  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||エンドポイントの CPU 名。  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||エンドポイントの CPU コアの数。  <br/> |
|**CPUProcessorSpeed** <br/> |整数  <br/> ||エンドポイントの CPU プロセッサ速度。  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || システムが仮想化環境で実行されているかどうかを示すビット フラグ。 <br/>  0x0000 - なし <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 - 仮想 PC <br/>  0x0008 - Xen PC <br/> |
   

