---
title: UserStatistics テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics はテーブルをサポートします。 テーブル内の各レコードは、システムの個々 のユーザーの使用状況に関する情報を格納します。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: c2e0acffa7b75b3c54781e3e4e9a8b033be5e440
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929981"
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
   

