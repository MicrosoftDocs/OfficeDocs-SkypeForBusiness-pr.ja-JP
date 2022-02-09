---
title: Mcus テーブル (Skype for Business Server 2015)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus テーブルはサポート テーブルです。 各レコードには、1 つの会議サービスに関する情報が格納されます。 これには、IM 会議サービスとテレフォニー会議サービス (フロントエンド サーバー上のプロセスとして実行される)、Web 会議サービスと音声ビデオ会議サービスが含まれます。
ms.openlocfilehash: 3cd0e096a09f1b83d50d4b7cad8428318d7fdb51
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416380"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Mcus テーブル (Skype for Business Server 2015)
 
Mcus テーブルはサポート テーブルです。 各レコードには、1 つの会議サービスに関する情報が格納されます。 これには、IM 会議サービスとテレフォニー会議サービス (フロントエンド サーバー上のプロセスとして実行される)、Web 会議サービスと音声ビデオ会議サービスが含まれます。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |この会議サーバーを識別する一意の番号。  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | 外部 <br/> |会議サーバーの種類 (たとえば、conf:chat (VM の場合) や conf:audio-video など。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
   

