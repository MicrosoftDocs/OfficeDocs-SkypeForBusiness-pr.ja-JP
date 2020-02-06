---
title: アイテムの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: '概要: 項目サービスの一部である [項目の取得] 操作について説明します。 項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 6345201fe3843e3fe8cf6671f01d2db30fb4e22e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816786"
---
# <a name="get-items"></a><span data-ttu-id="09456-105">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="09456-105">Get Items</span></span>
 
<span data-ttu-id="09456-106">**概要:** 項目サービスの一部である [項目の取得] 操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="09456-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="09456-107">項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="09456-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="09456-108">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="09456-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="09456-109">"アイテムの取得" 操作は、[リポジトリ API for Call Quality] ダッシュボードのアイテムサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="09456-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="09456-110">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="09456-110">Get Items</span></span>

<span data-ttu-id="09456-111">アイテムの取得リポジトリ内のすべてのアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="09456-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="09456-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="09456-112">**Method**</span></span>|<span data-ttu-id="09456-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="09456-113">**Request URI**</span></span>|<span data-ttu-id="09456-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="09456-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="09456-115">取得</span><span class="sxs-lookup"><span data-stu-id="09456-115">GET</span></span>  <br/> |<span data-ttu-id="09456-116">https://\<ポータル\>の/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="09456-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="09456-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="09456-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="09456-118">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="09456-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="09456-119">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="09456-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="09456-120">**要求本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="09456-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="09456-121">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09456-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="09456-122">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="09456-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="09456-123">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="09456-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="09456-124">**応答本文**-以下は JSON のサンプル応答ペイロードです。</span><span class="sxs-lookup"><span data-stu-id="09456-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09456-125">項目オブジェクトの配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="09456-125">An array of Item objects is returned.</span></span> <span data-ttu-id="09456-126">Item オブジェクトの詳細については、「アイテムの取得」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09456-126">For details about Item object, see Get Item.</span></span> 
  
```json
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
