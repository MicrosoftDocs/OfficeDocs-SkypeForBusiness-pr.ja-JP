---
title: UserStatistics テーブル
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
ms.openlocfilehash: c4a7952eada01033836811555d2e448d13133a27
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="userstatistics-table"></a>UserStatistics テーブル
 
UserStatistics はテーブルをサポートします。 テーブル内の各レコードは、システムの個々 のユーザーの使用状況に関する情報を格納します。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ユーザー Id** <br/> |int  <br/> |Primary  <br/> |このユーザーを識別する一意の番号です。  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||最後にユーザーがログインしています。  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||最後に、ユーザーには、会議が構成されています。  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||最後にユーザーには、呼び出しエラーが発生しました。  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||最後にユーザー会議の開催者として呼び出しエラーが発生しました。  <br/> |
   

