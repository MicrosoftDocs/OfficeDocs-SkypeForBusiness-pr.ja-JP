---
title: 常設チャット データベースのクエリのサンプル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: このセクションには、常設チャットデータベースのサンプルクエリが含まれています。
ms.openlocfilehash: f161deb55cb9ecb0e42eb23e71cd842aa8f3d99a
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887716"
---
# <a name="sample-persistent-chat-database-queries"></a>常設チャット データベースのクエリのサンプル
 
このセクションには、常設チャットデータベースのサンプルクエリが含まれています。
  
次の例を使用して、特定の日付以降にアクティブになっている常設チャットルームの一覧を取得します。
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

次の例を使用して、特定の日付以降の最もアクティブなユーザーの一覧を取得します。
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

次の例を使用すると、"Hello World" というメッセージが送信されたすべてのユーザーの一覧を取得できます。
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

特定のプリンシパルのグループメンバーシップの一覧を取得するには、次の例を使用します。
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

次の例を使用して、ユーザーの Jane が直接メンバーであるすべてのチャットルームの一覧を取得します。
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

ユーザーが受信した招待状の一覧を取得するには、次の例を使用します。
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
