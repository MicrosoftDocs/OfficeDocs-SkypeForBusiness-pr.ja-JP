---
title: サブ項目を取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: '概要: は、項目のサービスの一部では、サブ項目の取得操作について説明します。 項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 648f514ff03361673962052445d25076437057b9
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035653"
---
# <a name="get-sub-items"></a><span data-ttu-id="e4f66-105">サブ項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e4f66-105">Get Sub-Items</span></span>
 
<span data-ttu-id="e4f66-106">**の概要:** 品目サービスの一部では、サブ項目の取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4f66-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="e4f66-107">項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="e4f66-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="e4f66-108">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="e4f66-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e4f66-109">サブ項目の取得操作は、リポジトリ api の呼び出し品質のダッシュ ボードの項目のサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="e4f66-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="e4f66-110">サブ項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e4f66-110">Get Sub-Items</span></span>

<span data-ttu-id="e4f66-111">サブ項目を返します。 特定の項目のサブ項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e4f66-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="e4f66-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="e4f66-112">**Method**</span></span>|<span data-ttu-id="e4f66-113">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="e4f66-113">**Request URI**</span></span>|<span data-ttu-id="e4f66-114">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="e4f66-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e4f66-115">取得</span><span class="sxs-lookup"><span data-stu-id="e4f66-115">GET</span></span>  <br/> |<span data-ttu-id="e4f66-116">https://\<ポータル\>/QoERepositoryService/リポジトリ/アイテム/{itemId} subitem/</span><span class="sxs-lookup"><span data-stu-id="e4f66-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="e4f66-117">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="e4f66-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="e4f66-118">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="e4f66-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="e4f66-119">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="e4f66-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e4f66-120">**リクエストの本文**の [なし] です。</span><span class="sxs-lookup"><span data-stu-id="e4f66-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="e4f66-121">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4f66-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="e4f66-122">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="e4f66-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="e4f66-123">特定のユーザ ID が見つからない場合は、ステータス コード 404 (見つかりません) を返します。</span><span class="sxs-lookup"><span data-stu-id="e4f66-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="e4f66-124">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="e4f66-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e4f66-125">**応答本体**の JSON のサンプル応答の内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4f66-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4f66-126">アイテム オブジェクトの配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="e4f66-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="e4f66-127">サブ項目の操作によって返される項目のオブジェクトには、次の 3 つのフィールドのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4f66-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="e4f66-128">*アイテム Id*の項目の ID です。</span><span class="sxs-lookup"><span data-stu-id="e4f66-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="e4f66-129">*ユーザー Id* - このアイテムを所有するユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="e4f66-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="e4f66-130">*型*のコンテンツの種類です。</span><span class="sxs-lookup"><span data-stu-id="e4f66-130">*type*  - The type of the content.</span></span> <span data-ttu-id="e4f66-131">このフィールドは、アプリケーションによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="e4f66-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="e4f66-132">`Content``subItems`フィールドは、応答をネットワーク経由で送信されるデータの量を減らすには含まれません。</span><span class="sxs-lookup"><span data-stu-id="e4f66-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

