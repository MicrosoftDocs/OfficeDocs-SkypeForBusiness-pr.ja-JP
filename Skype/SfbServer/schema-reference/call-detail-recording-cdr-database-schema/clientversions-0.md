---
title: ClientVersions ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions ビューでは、さまざまな種類のクライアントとデータベースに記録されているセッションに参加したバージョンに関する情報を格納します。 ビュー内の各レコードは、1 つのクライアント バージョンを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: abf1436a2c3309e95bec8371b586c017e11b816d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213397"
---
# <a name="clientversions-view"></a>ClientVersions ビュー
 
ClientVersions ビューでは、さまざまな種類のクライアントとデータベースに記録されているセッションに参加したバージョンに関する情報を格納します。 ビュー内の各レコードは、1 つのクライアント バージョンを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> 可能性があります複数のレコードの特定の列。 
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**バージョン Id** <br/> |int  <br/> |このクライアントの種類とバージョンを識別する一意の番号です。  <br/> |
|**バージョン** <br/> |nvarchar(256)  <br/> |ユーザー エージェントを表します。  <br/> |
|**顧客タイプ** <br/> |int  <br/> |クライアントの種類です。  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |クライアントが属しているカテゴリです。 たとえば、クライアントの Conferencing_Attendant_1.0 は、ClientCategory CAA に属しています。  <br/> |
   

