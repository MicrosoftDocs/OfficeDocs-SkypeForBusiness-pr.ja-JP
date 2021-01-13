---
title: CQD のユーザー サービス
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: '概要: 通話品質ダッシュボードのリポジトリ API の一部であるユーザー サービスについて説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803077"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="d4741-104">CQD のユーザー サービス</span><span class="sxs-lookup"><span data-stu-id="d4741-104">User Service for CQD</span></span>
 
<span data-ttu-id="d4741-105">**概要:** 通話品質ダッシュボードのリポジトリ API の一部であるユーザー サービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d4741-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d4741-106">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="d4741-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d4741-107">ユーザー サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="d4741-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="d4741-108">ユーザー サービス</span><span class="sxs-lookup"><span data-stu-id="d4741-108">User Service</span></span>

<span data-ttu-id="d4741-109">リポジトリ API は、ユーザー プロビジョニング (新しいユーザー アカウントの作成) が自動的で暗黙的である、簡略化されたユーザー管理モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="d4741-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="d4741-110">ユーザーがリポジトリ API に対して初めて要求を行う場合、リポジトリは新しいユーザー レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4741-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="d4741-111">通話品質ダッシュボードでは、新しいユーザー専用のアイテムも自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4741-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="d4741-112">新しいユーザー専用アイテムは、システム ユーザーのアイテムの完全な複製です。</span><span class="sxs-lookup"><span data-stu-id="d4741-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="d4741-113">これにより、ユーザーはレポートとクエリの独自のコピーを使用して開始し、すぐにカスタマイズを開始できます。</span><span class="sxs-lookup"><span data-stu-id="d4741-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d4741-114">通話品質ダッシュボードを使用すると、ユーザーは専用アイテムをいつでもリセットできます。</span><span class="sxs-lookup"><span data-stu-id="d4741-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="d4741-115">**特別なユーザー ID**</span><span class="sxs-lookup"><span data-stu-id="d4741-115">**Special User IDs**</span></span>
  
<span data-ttu-id="d4741-116">リポジトリ API には、特定のユーザーを指定する整数値を期待する REST API URI が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4741-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="d4741-117">例: `https://<portal>/QoERepositoryService/repository/user/{userId}`</span><span class="sxs-lookup"><span data-stu-id="d4741-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="d4741-118">ここでは、{userId} を 0、1 などの整数値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4741-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="d4741-119">さらに、リポジトリ API は URI の {userId} で 2 つの特別なユーザー ID を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4741-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="d4741-120">*default*  - 現在 API を操作しているユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="d4741-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="d4741-121">これにより、アプリケーションは、実際のユーザー ID 値を追跡することなく、現在のユーザーのコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d4741-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="d4741-122">例: `https://<portal>/QoERepositoryService/repository/user/default`。</span><span class="sxs-lookup"><span data-stu-id="d4741-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="d4741-123">*system*  - システム ユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="d4741-123">*system*  - represents the system user.</span></span> <span data-ttu-id="d4741-124">これにより、アプリケーションは、実際のユーザー ID 値を知らなくてもシステム ユーザーのコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d4741-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="d4741-125">例: `https://<portal>/QoERepositoryService/repository/user/system`。</span><span class="sxs-lookup"><span data-stu-id="d4741-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="d4741-126">特に指定がない限り、特別なユーザー ID は URI の {userId} で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4741-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="d4741-127">REST 操作を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d4741-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="d4741-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="d4741-128">**Operation**</span></span>|<span data-ttu-id="d4741-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4741-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d4741-130">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="d4741-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="d4741-131">リポジトリ内のユーザーのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="d4741-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="d4741-132">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="d4741-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="d4741-133">ユーザー レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="d4741-133">Returns a user record.</span></span>  <br/> |
   

