---
title: ビジネス サーバー 2015 の Skype の Mcu のテーブル
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
ms.openlocfilehash: 2a85d46e733d230dc7c8096c8804146b19766bcf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype の Mcu のテーブル
 
Mcu はテーブルをサポートします。 各レコードは、1 つの会議サービスに関する情報を格納します。 IM 会議サービス、テレフォニー会議サービス (フロント エンド サーバー上でプロセスとして実行)、および Web 会議サービスおよび A が含まれます/V 会議サービスです。 
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |この会議サーバーを識別する一意の番号です。  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | 外部 <br/> |(IMs) の conf:chat や conf:audio などの会議サーバーの種類のビデオです。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
   

