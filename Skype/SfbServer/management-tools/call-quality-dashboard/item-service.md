---
title: 通話品質ダッシュボード (CQD) の項目サービス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: '概要: 通話品質ダッシュボードのリポジトリ API の一部であるアイテムサービスについて説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 585ba97d9dedbfcbbd572069a792a121e6156afe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274612"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="53bd1-104">通話品質ダッシュボード (CQD) の項目サービス</span><span class="sxs-lookup"><span data-stu-id="53bd1-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="53bd1-105">**概要:** 通話品質ダッシュボードのリポジトリ API の一部である、アイテムサービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="53bd1-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="53bd1-106">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="53bd1-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="53bd1-107">項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="53bd1-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="53bd1-108">アイテムのサービス</span><span class="sxs-lookup"><span data-stu-id="53bd1-108">Item Service</span></span>

<span data-ttu-id="53bd1-109">リポジトリ API は、項目サービスと呼ばれるシンプルなコンテンツ管理サービスを提供します。これを使うと、ユーザーに対してアプリケーションで定義されたコンテンツを保存することができます。</span><span class="sxs-lookup"><span data-stu-id="53bd1-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="53bd1-110">システムのコンテンツは、システムユーザーによって所有され、読み取り専用のアクセス権を持つすべてのユーザーが共有します。</span><span class="sxs-lookup"><span data-stu-id="53bd1-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="53bd1-111">専用ユーザーのコンテンツは、通常のユーザーによって所有され、所有者だけが変更または削除できますが、すべてのユーザーが引き続き読み取り専用アクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="53bd1-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="53bd1-112">この API ドキュメントでは、リポジトリ API の読み取り専用操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="53bd1-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="53bd1-113">通話品質ダッシュボードは、レポートやクエリをリポジトリデータベースのアイテムとして保存します。</span><span class="sxs-lookup"><span data-stu-id="53bd1-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="53bd1-114">アイテムにはオプションのサブアイテムを含めることができ、通話品質ダッシュボードは、サブアイテム機能を使用して階層構造の構造でレポートとクエリを整理します。</span><span class="sxs-lookup"><span data-stu-id="53bd1-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="53bd1-115">項目サービスには、次のような概念があります。</span><span class="sxs-lookup"><span data-stu-id="53bd1-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="53bd1-116">**アイテム**-リポジトリの基本要素。</span><span class="sxs-lookup"><span data-stu-id="53bd1-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="53bd1-117">各項目は、1人のユーザーによって所有されます。</span><span class="sxs-lookup"><span data-stu-id="53bd1-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="53bd1-118">**サブ項目**-リポジトリの基本的な構造です。</span><span class="sxs-lookup"><span data-stu-id="53bd1-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="53bd1-119">項目には、0、1、またはそれ以上の下位項目を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="53bd1-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="53bd1-120">**項目の先祖**-一番上の項目 (ユーザーの既定の項目である) から始まり、特定の項目に至る項目の一覧。</span><span class="sxs-lookup"><span data-stu-id="53bd1-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="53bd1-121">**項目コンテンツ**-項目に格納されているアプリケーション固有のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="53bd1-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="53bd1-122">通話品質ダッシュボードは、レポートとクエリの JSON 表現をコンテンツに保存します。</span><span class="sxs-lookup"><span data-stu-id="53bd1-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="53bd1-123">REST 操作は、次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="53bd1-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="53bd1-124">**操作**</span><span class="sxs-lookup"><span data-stu-id="53bd1-124">**Operation**</span></span>|<span data-ttu-id="53bd1-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="53bd1-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="53bd1-126">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="53bd1-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="53bd1-127">アイテムの取得リポジトリ内のすべてのアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="53bd1-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="53bd1-128">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="53bd1-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="53bd1-129">項目を取得すると、特定の項目が返されます。</span><span class="sxs-lookup"><span data-stu-id="53bd1-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="53bd1-130">サブアイテムの取得</span><span class="sxs-lookup"><span data-stu-id="53bd1-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="53bd1-131">サブ項目の取得: 特定の項目のサブ項目を返します。</span><span class="sxs-lookup"><span data-stu-id="53bd1-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="53bd1-132">アイテムの親の取得</span><span class="sxs-lookup"><span data-stu-id="53bd1-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="53bd1-133">項目の先祖を取得すると、特定の項目の先祖が返されます。</span><span class="sxs-lookup"><span data-stu-id="53bd1-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="53bd1-134">アイテムの更新</span><span class="sxs-lookup"><span data-stu-id="53bd1-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="53bd1-135">リポジトリ内の特定のアイテムを更新します。</span><span class="sxs-lookup"><span data-stu-id="53bd1-135">Update a specific item in the repository.</span></span>  <br/> |
   

