---
title: SessionCorrelation テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: セッション相関関係テーブルは、サポートテーブルです。 各レコードは、複数のセッションを関連付けるために使用される1つの CorrelationID を表します。
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294657"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation テーブル
 
セッション相関関係テーブルは、サポートテーブルです。 各レコードは、複数のセッションを関連付けるために使用される1つの CorrelationID を表します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**サム** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |この A/V 会議サーバーを識別する一意の番号です。  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |一意  <br/> |関連付けられているセッションは、関連付け ID が同じになります。  <br/> |
|**Nextupdatupdat** <br/> |datetime  <br/> | <br/> |内部使用のみ。  <br/> |
   

