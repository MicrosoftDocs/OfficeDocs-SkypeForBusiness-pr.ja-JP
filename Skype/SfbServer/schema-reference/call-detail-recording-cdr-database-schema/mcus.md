---
title: ビジネス サーバー 2015 の Skype の Mcu のテーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcu はテーブルをサポートします。 各レコードは、1 つの会議サービスに関する情報を格納します。 IM 会議サービス、テレフォニー会議サービス (フロント エンド サーバー上でプロセスとして実行)、および Web 会議サービスおよび A が含まれます/V 会議サービスです。
ms.openlocfilehash: e051af3a77d4f9b8231c122c596a3b6915f6f3e1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212974"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype の Mcu のテーブル
 
Mcu はテーブルをサポートします。 各レコードは、1 つの会議サービスに関する情報を格納します。 IM 会議サービス、テレフォニー会議サービス (フロント エンド サーバー上でプロセスとして実行)、および Web 会議サービスおよび A が含まれます/V 会議サービスです。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |この会議サーバーを識別する一意の番号です。  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | 外部 <br/> |(IMs) の conf:chat や conf:audio などの会議サーバーの種類のビデオです。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
   

