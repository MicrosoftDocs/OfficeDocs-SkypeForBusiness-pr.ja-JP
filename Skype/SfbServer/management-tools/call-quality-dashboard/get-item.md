---
title: アイテムの取得
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: '概要: Item Service の一部であるアイテムの取得操作について学習します。 アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 896540c4572fb3991356ce055f01690ed702c6f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832567"
---
# <a name="get-item"></a><span data-ttu-id="520e1-105">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="520e1-105">Get Item</span></span>
 
<span data-ttu-id="520e1-106">**概要:** アイテム サービスの一部であるアイテムの取得操作について学習します。</span><span class="sxs-lookup"><span data-stu-id="520e1-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="520e1-107">アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="520e1-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="520e1-108">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="520e1-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="520e1-109">アイテムの取得操作は、呼び出し品質ダッシュボードのリポジトリ API のアイテム サービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="520e1-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="520e1-110">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="520e1-110">Get Item</span></span>

<span data-ttu-id="520e1-111">アイテムを取得すると、リポジトリ内の特定のアイテムが返されます。</span><span class="sxs-lookup"><span data-stu-id="520e1-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="520e1-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="520e1-112">**Method**</span></span>|<span data-ttu-id="520e1-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="520e1-113">**Request URI**</span></span>|<span data-ttu-id="520e1-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="520e1-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="520e1-115">GET</span><span class="sxs-lookup"><span data-stu-id="520e1-115">GET</span></span>  <br/> |<span data-ttu-id="520e1-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="520e1-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="520e1-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="520e1-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="520e1-118">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="520e1-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="520e1-119">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="520e1-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="520e1-120">**要求本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="520e1-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="520e1-121">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="520e1-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="520e1-122">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="520e1-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="520e1-123">指定されたアイテム ID が見つからない場合は、状態コード 404 (Not Found) が返されます。</span><span class="sxs-lookup"><span data-stu-id="520e1-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="520e1-124">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="520e1-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="520e1-125">**応答本文** - JSON の応答ペイロードのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="520e1-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="520e1-126">*itemId*  - アイテムの ID。</span><span class="sxs-lookup"><span data-stu-id="520e1-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="520e1-127">*userId*  - このアイテムを所有するユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="520e1-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="520e1-128">*content*  - アプリケーション固有のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="520e1-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="520e1-129">*type:*  コンテンツの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="520e1-129">*type*  - The type of the content.</span></span> <span data-ttu-id="520e1-130">このフィールドは、アプリケーションによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="520e1-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="520e1-131">*subItemIds*  - サブアイテムの ID (サブアイテムがある場合)。</span><span class="sxs-lookup"><span data-stu-id="520e1-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="520e1-132">これは、呼び出しを保存する Get Sub-Itemsの短い回線です。</span><span class="sxs-lookup"><span data-stu-id="520e1-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="520e1-133">アプリケーションは、Get Sub-Items操作を使用して同じ情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="520e1-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

