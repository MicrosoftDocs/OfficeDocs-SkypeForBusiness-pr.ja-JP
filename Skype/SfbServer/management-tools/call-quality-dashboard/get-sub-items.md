---
title: サブアイテムの取得
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: '概要: Item Service の一部Sub-Items取得操作について学習します。 アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832507"
---
# <a name="get-sub-items"></a><span data-ttu-id="795a6-105">サブアイテムの取得</span><span class="sxs-lookup"><span data-stu-id="795a6-105">Get Sub-Items</span></span>
 
<span data-ttu-id="795a6-106">**概要:** Item Service の一Sub-Items取得操作について学習します。</span><span class="sxs-lookup"><span data-stu-id="795a6-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="795a6-107">アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="795a6-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="795a6-108">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="795a6-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="795a6-109">Get Sub-Items操作は、呼び出し品質ダッシュボードのリポジトリ API のアイテム サービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="795a6-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="795a6-110">サブアイテムの取得</span><span class="sxs-lookup"><span data-stu-id="795a6-110">Get Sub-Items</span></span>

<span data-ttu-id="795a6-111">取得Sub-Itemsアイテムのサブアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="795a6-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="795a6-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="795a6-112">**Method**</span></span>|<span data-ttu-id="795a6-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="795a6-113">**Request URI**</span></span>|<span data-ttu-id="795a6-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="795a6-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="795a6-115">GET</span><span class="sxs-lookup"><span data-stu-id="795a6-115">GET</span></span>  <br/> |<span data-ttu-id="795a6-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem</span><span class="sxs-lookup"><span data-stu-id="795a6-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="795a6-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="795a6-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="795a6-118">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="795a6-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="795a6-119">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="795a6-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="795a6-120">**要求本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="795a6-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="795a6-121">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="795a6-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="795a6-122">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="795a6-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="795a6-123">指定されたユーザー ID が見つからない場合は、状態コード 404 (Not Found) が返されます。</span><span class="sxs-lookup"><span data-stu-id="795a6-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="795a6-124">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="795a6-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="795a6-125">**応答本文** - JSON の応答ペイロードのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="795a6-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="795a6-126">Item オブジェクトの配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="795a6-126">An array of Item object is returned.</span></span> 
  
```json
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

<span data-ttu-id="795a6-127">この操作によって返される Item Sub-Itemsには、次の 3 つのフィールドだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="795a6-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="795a6-128">*itemId*  - アイテムの ID。</span><span class="sxs-lookup"><span data-stu-id="795a6-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="795a6-129">*userId*  - このアイテムを所有するユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="795a6-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="795a6-130">*type:*  コンテンツの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="795a6-130">*type*  - The type of the content.</span></span> <span data-ttu-id="795a6-131">このフィールドは、アプリケーションによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="795a6-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="795a6-132">`Content` およびフィールドは、ネットワーク経由で送信されるデータの量を減らすために `subItems` 応答に含まれません。</span><span class="sxs-lookup"><span data-stu-id="795a6-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

