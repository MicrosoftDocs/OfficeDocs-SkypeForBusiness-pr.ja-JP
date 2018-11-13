---
title: アイテムの親を取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: '概要: は、項目のサービスの一部では、アイテムの先祖を取得する操作について説明します。 項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。'
ms.openlocfilehash: 872af4deb7f6cf7ad1d519b41b7e2405121b1eea
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294423"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="73652-105">アイテムの親を取得します。</span><span class="sxs-lookup"><span data-stu-id="73652-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="73652-106">**の概要:** 項目のサービスの一部では、アイテムの先祖を取得する操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="73652-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="73652-107">項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="73652-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="73652-108">通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。</span><span class="sxs-lookup"><span data-stu-id="73652-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="73652-109">アイテムの先祖を取得する操作は、リポジトリ api の呼び出し品質のダッシュ ボードの項目のサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="73652-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="73652-110">アイテムの親を取得します。</span><span class="sxs-lookup"><span data-stu-id="73652-110">Get Item Ancestors</span></span>

<span data-ttu-id="73652-111">Get アイテムの先祖は、リポジトリから特定のアイテムの親を返します。</span><span class="sxs-lookup"><span data-stu-id="73652-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="73652-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="73652-112">**Method**</span></span>|<span data-ttu-id="73652-113">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="73652-113">**Request URI**</span></span>|<span data-ttu-id="73652-114">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="73652-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73652-115">取得</span><span class="sxs-lookup"><span data-stu-id="73652-115">GET</span></span>  <br/> |<span data-ttu-id="73652-116">https://\<ポータル\>/QoERepositoryService/リポジトリ/itemAncestors/{アイテム Id}</span><span class="sxs-lookup"><span data-stu-id="73652-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="73652-117">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="73652-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="73652-118">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="73652-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="73652-119">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="73652-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="73652-120">**リクエストの本文**の [なし] です。</span><span class="sxs-lookup"><span data-stu-id="73652-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="73652-121">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="73652-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="73652-122">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="73652-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="73652-123">特定のユーザ ID が見つからない場合は、ステータス コード 404 (見つかりません) を返します。</span><span class="sxs-lookup"><span data-stu-id="73652-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="73652-124">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="73652-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="73652-125">**応答本体**の JSON のサンプル応答の内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="73652-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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

 <span data-ttu-id="73652-126">*項目 1*項目の ID です。</span><span class="sxs-lookup"><span data-stu-id="73652-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="73652-127">*項目 2*の深さは、項目からの距離です。</span><span class="sxs-lookup"><span data-stu-id="73652-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="73652-128">0 は、直接の親です。</span><span class="sxs-lookup"><span data-stu-id="73652-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="73652-129">*項目 3* - アイテムのタイトル。</span><span class="sxs-lookup"><span data-stu-id="73652-129">*Item3*  - Title of the item.</span></span>
  

