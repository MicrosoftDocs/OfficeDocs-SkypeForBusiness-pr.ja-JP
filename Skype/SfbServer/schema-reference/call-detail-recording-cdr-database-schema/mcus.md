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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcu テーブルは、サポートテーブルです。 各レコードには、1つの会議サービスに関する情報が格納されます。 これには、IM 会議サービスと、(フロントエンドサーバーでプロセスとして実行される) テレフォニー会議サービス、および Web 会議サービスと A/V 会議サービスを含めることができます。
ms.openlocfilehash: 1e5141ee2a103e540d3ac50e99de0036f31262d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815065"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の mcu テーブル
 
Mcu テーブルは、サポートテーブルです。 各レコードには、1つの会議サービスに関する情報が格納されます。 これには、IM 会議サービスと、(フロントエンドサーバーでプロセスとして実行される) テレフォニー会議サービス、および Web 会議サービスと A/V 会議サービスを含めることができます。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |この会議サーバーを識別する一意の番号です。  <br/> |
|**McuUri** <br/> |nvarchar (450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | 外部 <br/> |会議サーバーの種類 (例: チャット (Im の場合) または conf: オーディオビデオ)。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
   

