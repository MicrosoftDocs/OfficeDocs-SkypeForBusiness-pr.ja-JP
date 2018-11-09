---
title: 項目を取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: '概要: は、項目のサービスの一部の項目の取得操作について説明します。 項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 12b52bdd51e8ba59f1aa90e2a366b3e11fb54805
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035583"
---
# <a name="get-item"></a><span data-ttu-id="fdce8-105">項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="fdce8-105">Get Item</span></span>
 
<span data-ttu-id="fdce8-106">**の概要:** 項目のサービスの一部の項目の取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="fdce8-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="fdce8-107">項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="fdce8-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="fdce8-108">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="fdce8-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="fdce8-109">項目の取得操作は、リポジトリ api の呼び出し品質のダッシュ ボードの項目のサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="fdce8-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="fdce8-110">項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="fdce8-110">Get Item</span></span>

<span data-ttu-id="fdce8-111">リポジトリ内のアイテムを返します。 特定の項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="fdce8-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="fdce8-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="fdce8-112">**Method**</span></span>|<span data-ttu-id="fdce8-113">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="fdce8-113">**Request URI**</span></span>|<span data-ttu-id="fdce8-114">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="fdce8-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fdce8-115">取得</span><span class="sxs-lookup"><span data-stu-id="fdce8-115">GET</span></span>  <br/> |<span data-ttu-id="fdce8-116">https://\<ポータル\>/QoERepositoryService/リポジトリ/アイテム/{アイテム Id}</span><span class="sxs-lookup"><span data-stu-id="fdce8-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="fdce8-117">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="fdce8-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="fdce8-118">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="fdce8-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="fdce8-119">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="fdce8-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="fdce8-120">**リクエストの本文**の [なし] です。</span><span class="sxs-lookup"><span data-stu-id="fdce8-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="fdce8-121">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fdce8-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="fdce8-122">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="fdce8-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="fdce8-123">指定した項目の ID が見つからない場合は、ステータス コード 404 (見つかりません) を返します。</span><span class="sxs-lookup"><span data-stu-id="fdce8-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="fdce8-124">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="fdce8-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="fdce8-125">**応答本体**の JSON のサンプル応答の内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fdce8-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="fdce8-126">*アイテム Id*の項目の ID です。</span><span class="sxs-lookup"><span data-stu-id="fdce8-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="fdce8-127">*ユーザー Id* - このアイテムを所有するユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="fdce8-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="fdce8-128">*コンテンツ*・ アプリケーションに固有のコンテンツです。</span><span class="sxs-lookup"><span data-stu-id="fdce8-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="fdce8-129">*型*のコンテンツの種類です。</span><span class="sxs-lookup"><span data-stu-id="fdce8-129">*type*  - The type of the content.</span></span> <span data-ttu-id="fdce8-130">このフィールドは、アプリケーションによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="fdce8-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="fdce8-131">*subItemIds* - の場合は、すべてのサブ項目の Id です。</span><span class="sxs-lookup"><span data-stu-id="fdce8-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="fdce8-132">呼び出しを保存するのには、サブ項目の取得操作の short-circuit です。</span><span class="sxs-lookup"><span data-stu-id="fdce8-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="fdce8-133">アプリケーションは、サブ項目の取得操作を使用して同じ情報を取得またはことができます。</span><span class="sxs-lookup"><span data-stu-id="fdce8-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

