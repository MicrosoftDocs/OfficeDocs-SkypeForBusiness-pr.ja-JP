---
title: Skype for Business Server 2015 の Mcus テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus テーブルはサポート テーブルです。 各レコードには、1 つの会議サービスに関する情報が格納されます。 これには、IM 会議サービスとテレフォニー会議サービス (フロントエンド サーバー上のプロセスとして実行される) や、Web 会議サービスと音声ビデオ会議サービスが含まれます。
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821427"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の Mcus テーブル
 
Mcus テーブルはサポート テーブルです。 各レコードには、1 つの会議サービスに関する情報が格納されます。 これには、IM 会議サービスとテレフォニー会議サービス (フロントエンド サーバー上のプロセスとして実行される) や、Web 会議サービスと音声ビデオ会議サービスが含まれます。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |この会議サーバーを識別する一意の番号。  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | 外部 <br/> |会議サーバーの種類 (conf:chat (VM 用) や conf:audio-video など)。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
   

