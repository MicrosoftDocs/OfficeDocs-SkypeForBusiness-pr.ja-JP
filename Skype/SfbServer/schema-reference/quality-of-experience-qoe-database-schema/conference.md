---
title: Conference テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会議の表は、補助テーブルです。 各レコードは、1 つの会議またはピア ツー ピア セッションを表します。
ms.openlocfilehash: 0914e98aed4aea16e5301ccae454e925663454a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920167"
---
# <a name="conference-table"></a>Conference テーブル
 
会議の表は、補助テーブルです。 各レコードは、1 つの会議またはピア ツー ピア セッションを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |この会議のレコードを識別する一意の番号です。  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |一意  <br/> |会議 URI は、会議では、DialogID この場合は、ピア ツー ピア セッションです。  <br/> |
|**チェックサム** <br/> |int  <br/> |インデックス  <br/> |会議 URI のチェックサムです。 これは、内部的に使用されます。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||内部でのみ使用します。  <br/> |
   

