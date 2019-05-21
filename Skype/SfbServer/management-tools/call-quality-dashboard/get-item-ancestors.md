---
title: アイテムの親の取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: '概要: 項目サービスの一部である "項目の親の取得" 操作について説明します。 項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 77fb5f46ada278bcb172a51620317182fe5d61b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274731"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="c8ab2-105">アイテムの親の取得</span><span class="sxs-lookup"><span data-stu-id="c8ab2-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="c8ab2-106">**概要:** 項目サービスの一部である、項目の親の取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="c8ab2-107">項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c8ab2-108">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c8ab2-109">"項目の先祖の取得" 操作は、"通話品質ダッシュボード用リポジトリ API" の項目サービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="c8ab2-110">アイテムの親の取得</span><span class="sxs-lookup"><span data-stu-id="c8ab2-110">Get Item Ancestors</span></span>

<span data-ttu-id="c8ab2-111">項目の先祖を取得すると、リポジトリから特定の項目の先祖が返されます。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="c8ab2-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="c8ab2-112">**Method**</span></span>|<span data-ttu-id="c8ab2-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="c8ab2-113">**Request URI**</span></span>|<span data-ttu-id="c8ab2-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="c8ab2-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c8ab2-115">取得</span><span class="sxs-lookup"><span data-stu-id="c8ab2-115">GET</span></span>  <br/> |<span data-ttu-id="c8ab2-116">https://\<ポータル\>の/QoERepositoryService/repository/itemAncestors/{itemId}</span><span class="sxs-lookup"><span data-stu-id="c8ab2-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="c8ab2-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c8ab2-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c8ab2-118">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c8ab2-119">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c8ab2-120">**要求本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="c8ab2-121">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c8ab2-122">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="c8ab2-123">指定したユーザー ID が見つからない場合は、状態コード 404 (見つかりません) が返されます。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="c8ab2-124">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c8ab2-125">**応答本文**-以下は JSON のサンプル応答ペイロードです。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
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

 <span data-ttu-id="c8ab2-126">*アイテム 1,* -アイテムの ID です。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="c8ab2-127">*アイテム 2*は、項目からの距離です。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="c8ab2-128">0は、直接の親です。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="c8ab2-129">*Item3* -項目のタイトル。</span><span class="sxs-lookup"><span data-stu-id="c8ab2-129">*Item3*  - Title of the item.</span></span>
  

