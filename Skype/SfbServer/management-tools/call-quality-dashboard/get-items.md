---
title: アイテムの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: '概要: は、項目のサービスの一部の項目の取得操作について説明します。 項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: fe8d4f9a64e0855c90ee9f2accb67424ac3edb9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926123"
---
# <a name="get-items"></a><span data-ttu-id="7c202-105">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="7c202-105">Get Items</span></span>
 
<span data-ttu-id="7c202-106">**の概要:** 品目サービスの一部の項目の取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="7c202-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="7c202-107">項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="7c202-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="7c202-108">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="7c202-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="7c202-109">項目の取得操作は、リポジトリ api の呼び出し品質のダッシュ ボードの項目のサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="7c202-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="7c202-110">アイテムの取得</span><span class="sxs-lookup"><span data-stu-id="7c202-110">Get Items</span></span>

<span data-ttu-id="7c202-111">リポジトリ内のアイテムを返します。 すべてのアイテムを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c202-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="7c202-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="7c202-112">**Method**</span></span>|<span data-ttu-id="7c202-113">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="7c202-113">**Request URI**</span></span>|<span data-ttu-id="7c202-114">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="7c202-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7c202-115">取得</span><span class="sxs-lookup"><span data-stu-id="7c202-115">GET</span></span>  <br/> |<span data-ttu-id="7c202-116">https://\<ポータル\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="7c202-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="7c202-117">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="7c202-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="7c202-118">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="7c202-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="7c202-119">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="7c202-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7c202-120">**リクエストの本文**の [なし] です。</span><span class="sxs-lookup"><span data-stu-id="7c202-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="7c202-121">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7c202-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="7c202-122">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="7c202-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="7c202-123">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="7c202-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7c202-124">**応答本体**の JSON のサンプル応答の内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7c202-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c202-125">アイテム オブジェクトの配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="7c202-125">An array of Item objects is returned.</span></span> <span data-ttu-id="7c202-126">詳細については、Item オブジェクトは、アイテムの取得を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c202-126">For details about Item object, see Get Item.</span></span> 
  
```
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
