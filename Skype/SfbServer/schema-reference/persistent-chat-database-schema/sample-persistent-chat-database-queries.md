---
title: 常設チャット データベースのクエリのサンプル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: このセクションには、永続的なチャットのデータベースのサンプル クエリが含まれています。
ms.openlocfilehash: 9dace51aa882402cd7f4f6c58c9444c21263333c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212685"
---
# <a name="sample-persistent-chat-database-queries"></a>常設チャット データベースのクエリのサンプル
 
このセクションには、永続的なチャットのデータベースのサンプル クエリが含まれています。
  
特定の日付以降後、最もアクティブな永続的なチャット ルームの一覧を取得するのにには、次の例を使用します。
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

特定の日付以降後、最もアクティブなユーザーの一覧を取得するのにには、次の例を使用します。
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

"Hello World"のメッセージを送信した人全員のリストを取得するのにには、次の例を使用します。
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

次の例を使用して、特定のプリンシパルのグループ メンバーシップのリストを取得します。
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

Jane Dow では、ユーザーが直接のメンバーであるすべてのチャット ルームの一覧を取得するのにには、次の例を使用します。
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

ユーザーが受信した招待状のリストを取得するのにには、次の例を使用します。
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
