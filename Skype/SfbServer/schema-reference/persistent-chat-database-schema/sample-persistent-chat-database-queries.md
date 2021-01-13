---
title: 常設チャット データベース クエリのサンプル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: このセクションでは、常設チャット データベースのサンプル クエリを示します。
ms.openlocfilehash: 74cb6c1029cdeaabcd74a34898731b44c71f05a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823107"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="06ee7-103">常設チャット データベース クエリのサンプル</span><span class="sxs-lookup"><span data-stu-id="06ee7-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="06ee7-104">このセクションでは、常設チャット データベースのサンプル クエリを示します。</span><span class="sxs-lookup"><span data-stu-id="06ee7-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="06ee7-105">特定の日付以降に最もアクティブな常設チャット ルームの一覧を取得するには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="06ee7-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="06ee7-106">特定の日付以降に最もアクティブなユーザーのリストを取得するには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="06ee7-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="06ee7-107">"Hello World" という文字列が含まれるメッセージを送信したことがあるユーザー全員のリストを取得するには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="06ee7-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="06ee7-108">特定のプリンシパルのグループ メンバーシップのリストを取得するには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="06ee7-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="06ee7-109">ユーザー Jane Dow が直接メンバーであるすべてのチャット ルームのリストを取得するには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="06ee7-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="06ee7-110">ユーザーが受け取った招待のリストを取得するには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="06ee7-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
