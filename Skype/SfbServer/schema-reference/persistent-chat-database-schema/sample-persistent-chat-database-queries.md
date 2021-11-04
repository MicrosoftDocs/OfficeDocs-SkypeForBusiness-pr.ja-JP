---
title: 常設チャット データベース クエリのサンプル
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: このセクションには、常設チャット データベースのサンプル クエリが含まれる。
ms.openlocfilehash: 9ae2f99817cae9eb892bf7c43d68900495878abf
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756440"
---
# <a name="sample-persistent-chat-database-queries"></a>常設チャット データベース クエリのサンプル
 
このセクションには、常設チャット データベースのサンプル クエリが含まれる。
  
次の例を使用して、特定の日付以降に最もアクティブな常設チャット ルームの一覧を取得します。
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

特定の日付以降に最もアクティブなユーザーのリストを取得するには、次の例を使用します。
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

"Hello World" という文字列が含まれるメッセージを送信したことがあるユーザー全員のリストを取得するには、次の例を使用します。
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

特定のプリンシパルのグループ メンバーシップのリストを取得するには、次の例を使用します。
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

ユーザー Jane Dow が直接メンバーであるすべてのチャット ルームのリストを取得するには、次の例を使用します。
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

ユーザーが受け取った招待のリストを取得するには、次の例を使用します。
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
