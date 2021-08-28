---
title: ClientVersions ビュー
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
ms.localizationpriority: medium
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions ビューは、データベースに記録されるセッションに参加した、さまざまなクライアントの種類およびバージョンの情報を格納します。 ビュー内の各レコードは、1 つのクライアント バージョンを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: bb17827f018919ba7b6088da884904a959bd6398
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593481"
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
   

