---
title: UserStatistics テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics はテーブルをサポートします。 テーブル内の各レコードは、システムの個々 のユーザーの使用状況に関する情報を格納します。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 45f34a1e8905d19b5ce48d94824591f25ec1ef28
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213040"
---
# <a name="userstatistics-table"></a>UserStatistics テーブル
 
UserStatistics はテーブルをサポートします。 テーブル内の各レコードは、システムの個々 のユーザーの使用状況に関する情報を格納します。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ユーザー Id** <br/> |int  <br/> |Primary  <br/> |このユーザーを識別する一意の番号です。  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||最後にユーザーがログインしています。  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||最後に、ユーザーには、会議が構成されています。  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||最後にユーザーには、呼び出しエラーが発生しました。  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||最後にユーザー会議の開催者として呼び出しエラーが発生しました。  <br/> |
   

