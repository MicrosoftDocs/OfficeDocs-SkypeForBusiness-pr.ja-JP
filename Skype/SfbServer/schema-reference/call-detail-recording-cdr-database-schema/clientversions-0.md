---
title: ClientVersions ビュー
ms.reviewer: null
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions ビューは、データベースに記録されるセッションに参加した、さまざまなクライアントの種類およびバージョンの情報を格納します。 ビュー内の各レコードは、1 つのクライアント バージョンを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。
---

# <a name="clientversions-view"></a>ClientVersions ビュー
 
ClientVersions ビューは、データベースに記録されるセッションに参加した、さまざまなクライアントの種類およびバージョンの情報を格納します。 ビュー内の各レコードは、1 つのクライアント バージョンを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> 一部の列には複数のレコードが存在する場合があります。 
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |このクライアントの種類とバージョンを識別する一意の番号。  <br/> |
|**バージョン** <br/> |nvarchar(256)  <br/> |ユーザー エージェントを表す。  <br/> |
|**ClientType** <br/> |int  <br/> |クライアントの種類。  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |クライアントが属するカテゴリ。たとえば、Conferencing_Attendant_1.0 というクライアントは CAA という ClientCategory に属します。  <br/> |
   

