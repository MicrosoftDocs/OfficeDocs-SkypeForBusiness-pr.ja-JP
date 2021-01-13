---
title: 通話品質ダッシュボード (CQD) のアイテム サービス
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
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: '概要: 通話品質ダッシュボードのリポジトリ API の一部であるアイテム サービスについて説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827707"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="729ec-104">通話品質ダッシュボード (CQD) のアイテム サービス</span><span class="sxs-lookup"><span data-stu-id="729ec-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="729ec-105">**概要:** 通話品質ダッシュボードのリポジトリ API の一部であるアイテム サービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="729ec-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="729ec-106">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="729ec-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="729ec-107">アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="729ec-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="729ec-108">アイテムのサービス</span><span class="sxs-lookup"><span data-stu-id="729ec-108">Item Service</span></span>

<span data-ttu-id="729ec-109">リポジトリ API は、アイテム サービスと呼ばれる単純なコンテンツ管理サービスを提供し、ユーザーに対してアプリケーション定義のコンテンツを格納するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="729ec-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="729ec-110">システム コンテンツはシステム ユーザーによって所有され、読み取り専用アクセス権を持つすべてのユーザーによって共有されます。</span><span class="sxs-lookup"><span data-stu-id="729ec-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="729ec-111">専用のユーザー コンテンツは通常のユーザーによって所有され、所有者だけが変更または削除できますが、すべてのユーザーは引き続き読み取り専用アクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="729ec-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="729ec-112">この API ドキュメントでは、リポジトリ API の読み取り専用操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="729ec-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="729ec-113">通話品質ダッシュボードは、レポートとクエリをアイテムとしてリポジトリ データベースに保存します。</span><span class="sxs-lookup"><span data-stu-id="729ec-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="729ec-114">アイテムにはオプションのサブアイテムを含め、通話品質ダッシュボードはサブアイテム機能を使用してレポートとクエリを階層構造で整理します。</span><span class="sxs-lookup"><span data-stu-id="729ec-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="729ec-115">アイテム サービスには、次の概念が含まれます。</span><span class="sxs-lookup"><span data-stu-id="729ec-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="729ec-116">**アイテム** : リポジトリの基本要素です。</span><span class="sxs-lookup"><span data-stu-id="729ec-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="729ec-117">各アイテムは、1 人のユーザーによって所有されます。</span><span class="sxs-lookup"><span data-stu-id="729ec-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="729ec-118">**サブ項目** : リポジトリの基本的な組織構造を指定します。</span><span class="sxs-lookup"><span data-stu-id="729ec-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="729ec-119">アイテムは、0、1、または複数の下位アイテムを持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="729ec-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="729ec-120">**アイテムの先祖** : ユーザーの既定のアイテムである、最も上位のアイテムから始まり、特定のアイテムに至るアイテムのリスト。</span><span class="sxs-lookup"><span data-stu-id="729ec-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="729ec-121">**アイテム コンテンツ** : アイテムに格納されているアプリケーション固有のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="729ec-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="729ec-122">通話品質ダッシュボードは、レポートとクエリの JSON 表記をコンテンツに保存します。</span><span class="sxs-lookup"><span data-stu-id="729ec-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="729ec-123">REST 操作を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="729ec-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="729ec-124">**操作**</span><span class="sxs-lookup"><span data-stu-id="729ec-124">**Operation**</span></span>|<span data-ttu-id="729ec-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="729ec-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="729ec-126">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="729ec-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="729ec-127">アイテムを取得すると、リポジトリ内のすべてのアイテムが返されます。</span><span class="sxs-lookup"><span data-stu-id="729ec-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="729ec-128">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="729ec-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="729ec-129">アイテムを取得すると、特定の Item が返されます。</span><span class="sxs-lookup"><span data-stu-id="729ec-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="729ec-130">サブアイテムの取得</span><span class="sxs-lookup"><span data-stu-id="729ec-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="729ec-131">取得Sub-Itemsアイテムのサブアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="729ec-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="729ec-132">アイテムの親の取得</span><span class="sxs-lookup"><span data-stu-id="729ec-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="729ec-133">アイテムの先祖を取得すると、特定のアイテムの先祖が返されます。</span><span class="sxs-lookup"><span data-stu-id="729ec-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="729ec-134">アイテムの更新</span><span class="sxs-lookup"><span data-stu-id="729ec-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="729ec-135">リポジトリ内の特定のアイテムを更新します。</span><span class="sxs-lookup"><span data-stu-id="729ec-135">Update a specific item in the repository.</span></span>  <br/> |
   

