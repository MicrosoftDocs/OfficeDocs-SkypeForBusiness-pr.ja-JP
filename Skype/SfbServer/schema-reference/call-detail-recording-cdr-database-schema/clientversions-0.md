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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: '[ClientVersions] ビューには、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンに関する情報が格納されます。 ビューの各レコードは、1つのクライアントバージョンを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。'
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815415"
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
|**ClientCategory** <br/> |nvarchar (64)  <br/> |クライアントが所属するカテゴリ。 たとえば、.0 というクライアント Conferencing_Attendant_1 は ClientCategory CAA をに属しています。  <br/> |
   

