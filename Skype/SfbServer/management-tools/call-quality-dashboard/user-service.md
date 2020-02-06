---
title: CQD のユーザーサービス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: '概要: 通話品質ダッシュボードのリポジトリ API の一部であるユーザーサービスについて説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 439df99c1c9d66547e681fdea90b33c6295344db
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816656"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="3fbf0-104">CQD のユーザーサービス</span><span class="sxs-lookup"><span data-stu-id="3fbf0-104">User Service for CQD</span></span>
 
<span data-ttu-id="3fbf0-105">**概要:** 通話品質ダッシュボードのリポジトリ API の一部であるユーザーサービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="3fbf0-106">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="3fbf0-107">ユーザーサービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="3fbf0-108">ユーザー サービス</span><span class="sxs-lookup"><span data-stu-id="3fbf0-108">User Service</span></span>

<span data-ttu-id="3fbf0-109">リポジトリ API は、ユーザープロビジョニング (新規ユーザーアカウントの作成) が自動的かつ暗黙的なものである簡素化されたユーザー管理モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="3fbf0-110">ユーザーが初めてリポジトリ API に対する要求を行うと、リポジトリは新しいユーザーレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="3fbf0-111">通話品質ダッシュボードでは、新規ユーザーのユーザー専用項目も自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="3fbf0-112">新しいユーザー専用項目は、システムユーザーの項目の完全な複製です。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="3fbf0-113">こうすることで、ユーザーはレポートやクエリの独自のコピーから開始し、すぐにカスタマイズを開始できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3fbf0-114">通話品質ダッシュボードを使用すると、ユーザーはいつでも専用のアイテムをリセットできます。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="3fbf0-115">**特殊なユーザー Id**</span><span class="sxs-lookup"><span data-stu-id="3fbf0-115">**Special User IDs**</span></span>
  
<span data-ttu-id="3fbf0-116">リポジトリ API には、特定のユーザーを指定する整数値を受け取る REST API Uri が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="3fbf0-117">例: `https://<portal>/QoERepositoryService/repository/user/{userId}`。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="3fbf0-118">{UserId} は、0、1などの整数値で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="3fbf0-119">さらに、リポジトリ API は、Uri の {userId} で2つの特殊なユーザー Id を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="3fbf0-120">*default* -API を現在操作しているユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="3fbf0-121">これにより、アプリケーションは実際のユーザー ID の値を追跡しなくても、現在のユーザーのコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="3fbf0-122">例: `https://<portal>/QoERepositoryService/repository/user/default`。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="3fbf0-123">*システム*-システムユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-123">*system*  - represents the system user.</span></span> <span data-ttu-id="3fbf0-124">これにより、アプリケーションは実際のユーザー ID 値を知らなくても、システムユーザーのコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="3fbf0-125">例: `https://<portal>/QoERepositoryService/repository/user/system`。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="3fbf0-126">特に注記がない限り、特殊なユーザー Id は、Uri の {userId} で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="3fbf0-127">REST 操作は、次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="3fbf0-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="3fbf0-128">**Operation**</span></span>|<span data-ttu-id="3fbf0-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="3fbf0-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="3fbf0-130">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="3fbf0-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="3fbf0-131">リポジトリ内のユーザーのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="3fbf0-132">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="3fbf0-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="3fbf0-133">ユーザーレコードを返します。</span><span class="sxs-lookup"><span data-stu-id="3fbf0-133">Returns a user record.</span></span>  <br/> |
   

