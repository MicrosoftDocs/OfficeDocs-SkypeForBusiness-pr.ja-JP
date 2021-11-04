---
title: ConferenceMessageCount テーブル (Skype for Business Server 2015)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: この表の各レコードは、1 つの IM 会議で 1 人のユーザーを表し、そのユーザーが送信したメッセージの数を含む。 各会議は、このテーブル内の複数のレコードで表されます。ユーザーごとに 1 つのレコードを指定します。
ms.openlocfilehash: 3504a7cb9affbd4c9e26518dbf9d7e404ad9d90e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754410"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>ConferenceMessageCount テーブル (Skype for Business Server 2015)
 
この表の各レコードは、1 つの IM 会議で 1 人のユーザーを表し、そのユーザーが送信したメッセージの数を含む。 各会議は、このテーブル内の複数のレコードで表されます。ユーザーごとに 1 つのレコードを指定します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |会議インスタンスの時間。 **SessionIdSeq と組み合わせて使用して**、会議インスタンスを一意に識別します。 詳細については[、Skype for Business Server 2015 の](conferences.md)電話会議の表を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |会議インスタンスを識別する ID 番号。 **SessionIdTime と組み合わせて使用して**、会議インスタンスを一意に識別します。 詳細については[、Skype for Business Server 2015 の](conferences.md)電話会議の表を参照してください。 <br/> |
|**UserId** <br/> |int  <br/> |外部  <br/> |User テーブルから参照される、このユーザーを識別する [一意の番号](users.md)です。  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |この会議中にこのユーザーが送信したメッセージの数。  <br/> |
   

