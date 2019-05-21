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
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: このセクションには、常設チャットデータベースのサンプルクエリが含まれています。
ms.openlocfilehash: fef40c2f36547fb0772d2e938bf8259246ec2055
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295609"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="e5c04-103">常設チャット データベースのクエリのサンプル</span><span class="sxs-lookup"><span data-stu-id="e5c04-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="e5c04-104">このセクションには、常設チャットデータベースのサンプルクエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5c04-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="e5c04-105">次の例を使用して、特定の日付以降にアクティブになっている常設チャットルームの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="e5c04-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="e5c04-106">次の例を使用して、特定の日付以降の最もアクティブなユーザーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="e5c04-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="e5c04-107">次の例を使用すると、"Hello World" というメッセージが送信されたすべてのユーザーの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="e5c04-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="e5c04-108">特定のプリンシパルのグループメンバーシップの一覧を取得するには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5c04-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="e5c04-109">次の例を使用して、ユーザーの Jane が直接メンバーであるすべてのチャットルームの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="e5c04-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="e5c04-110">ユーザーが受信した招待状の一覧を取得するには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5c04-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
