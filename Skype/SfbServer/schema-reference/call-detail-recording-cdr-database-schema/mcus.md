---
title: Skype for Business Server 2015 の mcu テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcu テーブルは、サポートテーブルです。 各レコードには、1つの会議サービスに関する情報が格納されます。 これには、IM 会議サービスと、(フロントエンドサーバーでプロセスとして実行される) テレフォニー会議サービス、および Web 会議サービスと A/V 会議サービスを含めることができます。
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296043"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の mcu テーブル
 
Mcu テーブルは、サポートテーブルです。 各レコードには、1つの会議サービスに関する情報が格納されます。 これには、IM 会議サービスと、(フロントエンドサーバーでプロセスとして実行される) テレフォニー会議サービス、および Web 会議サービスと A/V 会議サービスを含めることができます。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |この会議サーバーを識別する一意の番号です。  <br/> |
|**McuUri** <br/> |nvarchar (450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | 外部 <br/> |会議サーバーの種類 (例: チャット (Im の場合) または conf: オーディオビデオ)。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
   

