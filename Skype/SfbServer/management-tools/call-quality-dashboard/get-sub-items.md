---
title: サブアイテムの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: '概要: 項目サービスの一部である [サブ項目の取得] 操作について説明します。 項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 7be427ed4ea90cd46c6f8cea4ffe3a97be98479b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274661"
---
# <a name="get-sub-items"></a><span data-ttu-id="897af-105">サブアイテムの取得</span><span class="sxs-lookup"><span data-stu-id="897af-105">Get Sub-Items</span></span>
 
<span data-ttu-id="897af-106">**概要:** 項目サービスの一部である [サブ項目の取得] 操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="897af-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="897af-107">項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="897af-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="897af-108">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="897af-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="897af-109">[サブアイテムの取得] 操作は、[リポジトリ API for Call Quality] ダッシュボードのアイテムサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="897af-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="897af-110">サブアイテムの取得</span><span class="sxs-lookup"><span data-stu-id="897af-110">Get Sub-Items</span></span>

<span data-ttu-id="897af-111">サブ項目の取得: 特定の項目のサブ項目を返します。</span><span class="sxs-lookup"><span data-stu-id="897af-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="897af-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="897af-112">**Method**</span></span>|<span data-ttu-id="897af-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="897af-113">**Request URI**</span></span>|<span data-ttu-id="897af-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="897af-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="897af-115">取得</span><span class="sxs-lookup"><span data-stu-id="897af-115">GET</span></span>  <br/> |<span data-ttu-id="897af-116">https://\<ポータル\>の/QoERepositoryService/repository/item/{itemId}/subitem</span><span class="sxs-lookup"><span data-stu-id="897af-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="897af-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="897af-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="897af-118">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="897af-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="897af-119">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="897af-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="897af-120">**要求本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="897af-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="897af-121">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="897af-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="897af-122">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="897af-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="897af-123">指定したユーザー ID が見つからない場合は、状態コード 404 (見つかりません) が返されます。</span><span class="sxs-lookup"><span data-stu-id="897af-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="897af-124">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="897af-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="897af-125">**応答本文**-以下は JSON のサンプル応答ペイロードです。</span><span class="sxs-lookup"><span data-stu-id="897af-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="897af-126">項目オブジェクトの配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="897af-126">An array of Item object is returned.</span></span> 
  
```
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

<span data-ttu-id="897af-127">サブ項目操作によって返される Item オブジェクトには、次の3つのフィールドのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="897af-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="897af-128">*itemId* -項目の ID です。</span><span class="sxs-lookup"><span data-stu-id="897af-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="897af-129">*userId* -このアイテムを所有しているユーザーの id です。</span><span class="sxs-lookup"><span data-stu-id="897af-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="897af-130">*type* -コンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="897af-130">*type*  - The type of the content.</span></span> <span data-ttu-id="897af-131">このフィールドは、アプリケーションによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="897af-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="897af-132">`Content`また`subItems` 、ネットワーク経由で送信されるデータの量を減らすために、フィールドは返信に含まれません。</span><span class="sxs-lookup"><span data-stu-id="897af-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

