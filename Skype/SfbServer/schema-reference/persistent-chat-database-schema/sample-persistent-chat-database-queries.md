---
title: 常設チャット データベースのクエリのサンプル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: このセクションには、永続的なチャットのデータベースのサンプル クエリが含まれています。
ms.openlocfilehash: 1e2d457a31061dcfb3c332a067069cbd4a8a9ebd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="feeb4-103">常設チャット データベースのクエリのサンプル</span><span class="sxs-lookup"><span data-stu-id="feeb4-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="feeb4-104">このセクションには、永続的なチャットのデータベースのサンプル クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="feeb4-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="feeb4-105">特定の日付以降後、最もアクティブな永続的なチャット ルームの一覧を取得するのにには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="feeb4-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC

```

<span data-ttu-id="feeb4-106">特定の日付以降後、最もアクティブなユーザーの一覧を取得するのにには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="feeb4-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC

```

<span data-ttu-id="feeb4-107">"Hello World"のメッセージを送信した人全員のリストを取得するのにには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="feeb4-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="feeb4-108">次の例を使用して、特定のプリンシパルのグループ メンバーシップのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="feeb4-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="feeb4-109">Jane Dow では、ユーザーが直接のメンバーであるすべてのチャット ルームの一覧を取得するのにには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="feeb4-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="feeb4-110">ユーザーが受信した招待状のリストを取得するのにには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="feeb4-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```


