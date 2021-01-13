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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: '概要: アイテム サービスの一部であるアイテムの取得操作について学習します。 アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 7da3ba77e782abe44896a7c1eb51a458d9a7e0b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832537"
---
# <a name="get-items"></a><span data-ttu-id="9b68d-105">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="9b68d-105">Get Items</span></span>
 
<span data-ttu-id="9b68d-106">**概要:** アイテム サービスの一部であるアイテムの取得操作について学習します。</span><span class="sxs-lookup"><span data-stu-id="9b68d-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="9b68d-107">アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="9b68d-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9b68d-108">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="9b68d-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9b68d-109">アイテムの取得操作は、呼び出し品質ダッシュボードのリポジトリ API のアイテム サービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="9b68d-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="9b68d-110">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="9b68d-110">Get Items</span></span>

<span data-ttu-id="9b68d-111">アイテムを取得すると、リポジトリ内のすべてのアイテムが返されます。</span><span class="sxs-lookup"><span data-stu-id="9b68d-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="9b68d-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="9b68d-112">**Method**</span></span>|<span data-ttu-id="9b68d-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="9b68d-113">**Request URI**</span></span>|<span data-ttu-id="9b68d-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="9b68d-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9b68d-115">GET</span><span class="sxs-lookup"><span data-stu-id="9b68d-115">GET</span></span>  <br/> |<span data-ttu-id="9b68d-116">https:// \<portal\> /QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="9b68d-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="9b68d-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9b68d-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9b68d-118">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="9b68d-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9b68d-119">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="9b68d-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9b68d-120">**要求本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="9b68d-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9b68d-121">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b68d-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9b68d-122">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="9b68d-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="9b68d-123">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="9b68d-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9b68d-124">**応答本文** - JSON の応答ペイロードのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9b68d-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b68d-125">Item オブジェクトの配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="9b68d-125">An array of Item objects is returned.</span></span> <span data-ttu-id="9b68d-126">Item オブジェクトの詳細については、「アイテムを取得する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b68d-126">For details about Item object, see Get Item.</span></span> 
  
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
