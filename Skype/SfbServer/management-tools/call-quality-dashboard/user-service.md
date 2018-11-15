---
title: 救難用のユーザー ・ サービス
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: '概要: は、ユーザー サービス、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 42268078337e41b2dff595f58963f94656c2fd66
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532113"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="b5d52-104">救難用のユーザー ・ サービス</span><span class="sxs-lookup"><span data-stu-id="b5d52-104">User Service for CQD</span></span>
 
<span data-ttu-id="b5d52-105">**の概要:** ユーザー サービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="b5d52-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b5d52-106">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="b5d52-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b5d52-107">ユーザー サービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="b5d52-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="b5d52-108">ユーザー サービス</span><span class="sxs-lookup"><span data-stu-id="b5d52-108">User Service</span></span>

<span data-ttu-id="b5d52-109">リポジトリ API には、ここでユーザー (新しいユーザー アカウントを作成する) のプロビジョニング、自動と暗黙の型のシンプルなユーザー管理モデルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b5d52-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="b5d52-110">ユーザーは、最初にリポジトリ API に対して要求を行い、リポジトリは、新しいユーザー レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="b5d52-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="b5d52-111">品質のダッシュ ボードが自動的にユーザーを作成する呼び出しは、新しいユーザーのアイテム専用です。</span><span class="sxs-lookup"><span data-stu-id="b5d52-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="b5d52-112">新しいユーザーが専用のアイテムは、システム ユーザーのアイテムの完全なクローンです。</span><span class="sxs-lookup"><span data-stu-id="b5d52-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="b5d52-113">この方法により、ユーザーは、レポートおよびクエリは、すぐに開始することをカスタマイズするが自分のコピーを使用して起動できます。</span><span class="sxs-lookup"><span data-stu-id="b5d52-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b5d52-114">品質のダッシュ ボードの呼び出しを使用すると、ユーザーはリセット専用のアイテムは、いつでも。</span><span class="sxs-lookup"><span data-stu-id="b5d52-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="b5d52-115">**特別なユーザーの Id**</span><span class="sxs-lookup"><span data-stu-id="b5d52-115">**Special User IDs**</span></span>
  
<span data-ttu-id="b5d52-116">リポジトリ API には、特定のユーザーを指定する整数値を受け取る REST API Uri が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b5d52-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="b5d52-117">例: `https://<portal>/QoERepositoryService/repository/user/{userId}`。</span><span class="sxs-lookup"><span data-stu-id="b5d52-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="b5d52-118">{ユーザー Id} を整数値 0 などで置き換える必要がありますここでは、1 などです。</span><span class="sxs-lookup"><span data-stu-id="b5d52-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="b5d52-119">さらに、リポジトリ API は、Uri で {ユーザー Id} の 2 つの特別なユーザー Id を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="b5d52-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="b5d52-120">*既定*では、API を使用して現在操作しているユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="b5d52-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="b5d52-121">これにより、アプリケーションの実際のユーザー ID の値を追跡せずに現在のユーザーのコンテンツにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b5d52-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="b5d52-122">例: ` https://<portal>/QoERepositoryService/repository/user/default`。</span><span class="sxs-lookup"><span data-stu-id="b5d52-122">Example: ` https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="b5d52-123">*システム*では、システムのユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="b5d52-123">*system*  - represents the system user.</span></span> <span data-ttu-id="b5d52-124">これにより、実際のユーザー ID の値を知らなくてもシステムのユーザーのコンテンツにアクセスするアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="b5d52-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="b5d52-125">例: `https://<portal>/QoERepositoryService/repository/user/system`。</span><span class="sxs-lookup"><span data-stu-id="b5d52-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="b5d52-126">特に断らない限りは、Uri で {ユーザー Id} にある特別なユーザ Id が使用できます。</span><span class="sxs-lookup"><span data-stu-id="b5d52-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="b5d52-127">次の表には、他の操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5d52-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="b5d52-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="b5d52-128">**Operation**</span></span>|<span data-ttu-id="b5d52-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="b5d52-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b5d52-130">ユーザーを取得します。</span><span class="sxs-lookup"><span data-stu-id="b5d52-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="b5d52-131">リポジトリ内のユーザーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="b5d52-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="b5d52-132">ユーザーを取得します。</span><span class="sxs-lookup"><span data-stu-id="b5d52-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="b5d52-133">ユーザー レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="b5d52-133">Returns a user record.</span></span>  <br/> |
   

