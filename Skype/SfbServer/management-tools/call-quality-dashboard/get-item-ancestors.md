---
title: アイテムの親の取得
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: '概要: アイテム サービスの一部であるアイテムの先祖の取得操作について学習します。 アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 59fcd10f620b32151346e8732e67ae6151a258ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832577"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="500bc-105">アイテムの親の取得</span><span class="sxs-lookup"><span data-stu-id="500bc-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="500bc-106">**概要:** アイテム サービスの一部であるアイテムの先祖の取得操作について学習します。</span><span class="sxs-lookup"><span data-stu-id="500bc-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="500bc-107">アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="500bc-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="500bc-108">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="500bc-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="500bc-109">アイテムの先祖の取得操作は、呼び出し品質ダッシュボードのリポジトリ API のアイテム サービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="500bc-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="500bc-110">アイテムの親の取得</span><span class="sxs-lookup"><span data-stu-id="500bc-110">Get Item Ancestors</span></span>

<span data-ttu-id="500bc-111">アイテムの先祖を取得すると、リポジトリから特定のアイテムの先祖が返されます。</span><span class="sxs-lookup"><span data-stu-id="500bc-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="500bc-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="500bc-112">**Method**</span></span>|<span data-ttu-id="500bc-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="500bc-113">**Request URI**</span></span>|<span data-ttu-id="500bc-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="500bc-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="500bc-115">GET</span><span class="sxs-lookup"><span data-stu-id="500bc-115">GET</span></span>  <br/> |<span data-ttu-id="500bc-116">https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}</span><span class="sxs-lookup"><span data-stu-id="500bc-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="500bc-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="500bc-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="500bc-118">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="500bc-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="500bc-119">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="500bc-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="500bc-120">**要求本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="500bc-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="500bc-121">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="500bc-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="500bc-122">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="500bc-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="500bc-123">指定されたユーザー ID が見つからない場合は、状態コード 404 (Not Found) が返されます。</span><span class="sxs-lookup"><span data-stu-id="500bc-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="500bc-124">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="500bc-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="500bc-125">**応答本文** - JSON の応答ペイロードのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="500bc-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 <span data-ttu-id="500bc-126">*Item1*  - アイテムの ID。</span><span class="sxs-lookup"><span data-stu-id="500bc-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="500bc-127">*Item2*  - 深度はアイテムからの距離です。</span><span class="sxs-lookup"><span data-stu-id="500bc-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="500bc-128">0 は直接の親です。</span><span class="sxs-lookup"><span data-stu-id="500bc-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="500bc-129">*Item3*  - アイテムのタイトル。</span><span class="sxs-lookup"><span data-stu-id="500bc-129">*Item3*  - Title of the item.</span></span>
  

