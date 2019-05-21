---
title: アイテムの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: '概要: 項目サービスの一部である、"項目の取得" 操作について説明します。 項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: bfd5015603ac73fb48c4e30635cf8ae0fb14bf13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274717"
---
# <a name="get-item"></a><span data-ttu-id="fa783-105">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="fa783-105">Get Item</span></span>
 
<span data-ttu-id="fa783-106">**概要:** 項目サービスの一部である、"項目の取得" 操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa783-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="fa783-107">項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="fa783-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="fa783-108">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="fa783-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="fa783-109">"項目の取得" 操作は、[リポジトリ API for Call Quality] ダッシュボードのアイテムサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="fa783-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="fa783-110">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="fa783-110">Get Item</span></span>

<span data-ttu-id="fa783-111">項目を取得すると、リポジトリ内の特定の項目が返されます。</span><span class="sxs-lookup"><span data-stu-id="fa783-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="fa783-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="fa783-112">**Method**</span></span>|<span data-ttu-id="fa783-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="fa783-113">**Request URI**</span></span>|<span data-ttu-id="fa783-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="fa783-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fa783-115">取得</span><span class="sxs-lookup"><span data-stu-id="fa783-115">GET</span></span>  <br/> |<span data-ttu-id="fa783-116">https://\<ポータル\>の/QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="fa783-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="fa783-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="fa783-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="fa783-118">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="fa783-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="fa783-119">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="fa783-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="fa783-120">**要求本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="fa783-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="fa783-121">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa783-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="fa783-122">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="fa783-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="fa783-123">指定した項目 ID が見つからない場合は、状態コード 404 (見つからない) が返されます。</span><span class="sxs-lookup"><span data-stu-id="fa783-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="fa783-124">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="fa783-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="fa783-125">**応答本文**-以下は JSON のサンプル応答ペイロードです。</span><span class="sxs-lookup"><span data-stu-id="fa783-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="fa783-126">*itemId* -項目の ID です。</span><span class="sxs-lookup"><span data-stu-id="fa783-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="fa783-127">*userId* -このアイテムを所有しているユーザーの id です。</span><span class="sxs-lookup"><span data-stu-id="fa783-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="fa783-128">*コンテンツ*-アプリケーション固有のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="fa783-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="fa783-129">*type* -コンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="fa783-129">*type*  - The type of the content.</span></span> <span data-ttu-id="fa783-130">このフィールドは、アプリケーションによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="fa783-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="fa783-131">*Subitemids* -サブ項目の id (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="fa783-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="fa783-132">これは、通話を保存するサブ項目取得操作のショートサーキットです。</span><span class="sxs-lookup"><span data-stu-id="fa783-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="fa783-133">アプリケーションでは、Get サブ項目操作を使って同じ情報を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa783-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

