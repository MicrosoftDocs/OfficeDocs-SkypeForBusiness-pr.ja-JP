---
title: ClientVersions ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: '[ClientVersions] ビューには、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンに関する情報が格納されます。 ビューの各レコードは、1つのクライアントバージョンを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。'
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296540"
---
# <a name="clientversions-view"></a>ClientVersions ビュー
 
[ClientVersions] ビューには、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンに関する情報が格納されます。 ビューの各レコードは、1つのクライアントバージョンを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> 特定の列に対して複数のレコードが存在する場合があります。 
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |このクライアントの種類とバージョンを識別する一意の番号。  <br/> |
|**バージョン** <br/> |nvarchar(256)  <br/> |ユーザーエージェントを表します。  <br/> |
|**ClientType** <br/> |int  <br/> |クライアントの種類。  <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |クライアントが所属するカテゴリ。 たとえば、クライアント Conferencing_Attendant_ 1.0 は、ClientCategory CAA をに属しています。  <br/> |
   

