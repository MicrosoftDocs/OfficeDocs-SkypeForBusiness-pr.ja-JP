---
title: 品目サービスの通話品質のダッシュ ボード (救難)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: '概要: は、項目のサービス品質のダッシュ ボードを呼び出すためのリポジトリ API の一部について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: cbebdcfcac62eae375c13785b8d9866d055c2b50
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897500"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="5094f-104">品目サービスの通話品質のダッシュ ボード (救難)</span><span class="sxs-lookup"><span data-stu-id="5094f-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="5094f-105">**の概要:** 項目のサービス品質のダッシュ ボードを呼び出すためのリポジトリ API の一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="5094f-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="5094f-106">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="5094f-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="5094f-107">項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="5094f-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="5094f-108">アイテムのサービス</span><span class="sxs-lookup"><span data-stu-id="5094f-108">Item Service</span></span>

<span data-ttu-id="5094f-109">リポジトリ API は、ユーザーに対して、アプリケーション定義の内容を格納するために使用できる項目のサービスと呼ばれる、単純なコンテンツ管理サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5094f-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="5094f-110">システムの内容はシステムのユーザーが所有しているし、読み取り専用アクセス権を持つすべてのユーザーで共有します。</span><span class="sxs-lookup"><span data-stu-id="5094f-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="5094f-111">専用のユーザーのコンテンツが、正規のユーザーが所有していると所有者のみが変更または削除が、すべてのユーザーは読み取り専用にすることもあります。</span><span class="sxs-lookup"><span data-stu-id="5094f-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5094f-112">この API のドキュメントでは、リポジトリ API の読み取り専用の操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="5094f-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="5094f-113">通話品質のダッシュ ボードはレポートおよびクエリをリポジトリ データベース内の項目として保存します。</span><span class="sxs-lookup"><span data-stu-id="5094f-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="5094f-114">アイテムは、オプションのサブ項目を持つことができ、品質のダッシュ ボードを呼び出すのサブ項目の機能を使用して、階層構造のレポートおよびクエリを整理します。</span><span class="sxs-lookup"><span data-stu-id="5094f-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="5094f-115">項目のサービスには、次の概念が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5094f-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="5094f-116">**アイテム**のリポジトリの基本的な要素です。</span><span class="sxs-lookup"><span data-stu-id="5094f-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="5094f-117">各項目は、1 つのユーザーが所有します。</span><span class="sxs-lookup"><span data-stu-id="5094f-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="5094f-118">**サブ項目**をリポジトリの基本的な組織の仕組みです。</span><span class="sxs-lookup"><span data-stu-id="5094f-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="5094f-119">項目 0 を持つことができます、1 つ、または複数の下位のアイテムです。</span><span class="sxs-lookup"><span data-stu-id="5094f-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="5094f-120">**アイテムの先祖**の項目が特定のアイテムに、ユーザーの既定値は、最上位の項目から始まり、項目の一覧です。</span><span class="sxs-lookup"><span data-stu-id="5094f-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="5094f-121">**項目の内容**の項目に格納されているアプリケーション固有のコンテンツです。</span><span class="sxs-lookup"><span data-stu-id="5094f-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="5094f-122">通話品質のダッシュ ボードでは、内容のレポートおよびクエリの JSON 形式を保存します。</span><span class="sxs-lookup"><span data-stu-id="5094f-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="5094f-123">次の表には、他の操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5094f-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="5094f-124">**操作**</span><span class="sxs-lookup"><span data-stu-id="5094f-124">**Operation**</span></span>|<span data-ttu-id="5094f-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="5094f-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="5094f-126">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="5094f-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="5094f-127">リポジトリ内のアイテムを返します。 すべてのアイテムを取得します。</span><span class="sxs-lookup"><span data-stu-id="5094f-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="5094f-128">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="5094f-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="5094f-129">返品品目の特定の項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="5094f-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="5094f-130">サブアイテムの取得</span><span class="sxs-lookup"><span data-stu-id="5094f-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="5094f-131">サブ項目を返します。 特定の項目のサブ項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="5094f-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="5094f-132">アイテムの親の取得</span><span class="sxs-lookup"><span data-stu-id="5094f-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="5094f-133">Get アイテムの先祖は、特定のアイテムの親を返します。</span><span class="sxs-lookup"><span data-stu-id="5094f-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="5094f-134">アイテムの更新</span><span class="sxs-lookup"><span data-stu-id="5094f-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="5094f-135">リポジトリ内の特定のアイテムを更新します。</span><span class="sxs-lookup"><span data-stu-id="5094f-135">Update a specific item in the repository.</span></span>  <br/> |
   

