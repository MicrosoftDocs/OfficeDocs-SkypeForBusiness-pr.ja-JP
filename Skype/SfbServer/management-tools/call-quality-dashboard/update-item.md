---
title: アイテムを更新する
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: '概要: アイテム サービスの一部であるアイテムの更新操作について学習します。 アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803087"
---
# <a name="update-item"></a><span data-ttu-id="9cdde-105">アイテムを更新する</span><span class="sxs-lookup"><span data-stu-id="9cdde-105">Update Item</span></span>
 
<span data-ttu-id="9cdde-106">**概要:** アイテム サービスの一部であるアイテムの更新操作について学習します。</span><span class="sxs-lookup"><span data-stu-id="9cdde-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="9cdde-107">アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="9cdde-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9cdde-108">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="9cdde-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9cdde-109">アイテムの更新操作は、呼び出し品質ダッシュボードのリポジトリ API のアイテム サービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="9cdde-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="9cdde-110">アイテムを更新する</span><span class="sxs-lookup"><span data-stu-id="9cdde-110">Update Item</span></span>

<span data-ttu-id="9cdde-111">アイテムを更新すると、リポジトリ内の特定のアイテムが更新されます。</span><span class="sxs-lookup"><span data-stu-id="9cdde-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="9cdde-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="9cdde-112">**Method**</span></span>|<span data-ttu-id="9cdde-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="9cdde-113">**Request URI**</span></span>|<span data-ttu-id="9cdde-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="9cdde-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9cdde-115">PUT</span><span class="sxs-lookup"><span data-stu-id="9cdde-115">PUT</span></span>  <br/> |<span data-ttu-id="9cdde-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="9cdde-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="9cdde-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9cdde-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9cdde-118">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="9cdde-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9cdde-119">**要求ヘッダー** -Content-Type: application/json。</span><span class="sxs-lookup"><span data-stu-id="9cdde-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="9cdde-120">**要求本文** - JSON。</span><span class="sxs-lookup"><span data-stu-id="9cdde-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="9cdde-121">要求ペイロードの例:</span><span class="sxs-lookup"><span data-stu-id="9cdde-121">Sample request payload:</span></span>
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="9cdde-122">*content*  既存のサブアイテムの新しいコンテンツとして格納される JSON 形式のデータ。</span><span class="sxs-lookup"><span data-stu-id="9cdde-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="9cdde-123">技術的には、リポジトリは任意のスキーマのコンテンツを格納できますが、通話品質ダッシュボードで使用する場合は、レポートまたはクエリである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cdde-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="9cdde-124">*type*  通話品質ダッシュボードには、常に "application/json" を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cdde-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="9cdde-125">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9cdde-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9cdde-126">**状態コード** - 正常な操作では、状態コード 204 (コンテンツなし) が返されます。</span><span class="sxs-lookup"><span data-stu-id="9cdde-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="9cdde-127">指定されたアイテム ID が見つからない場合は、状態コード 404 (Not Found) が返されます。</span><span class="sxs-lookup"><span data-stu-id="9cdde-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9cdde-128">"コンテンツなし" はエラー状態ではありません。</span><span class="sxs-lookup"><span data-stu-id="9cdde-128">"No Content" is not an error status.</span></span> <span data-ttu-id="9cdde-129">これは、応答が本文に何も返しなかったことを意味します (対照的に、200 OK は本文のコンテンツを返します)。</span><span class="sxs-lookup"><span data-stu-id="9cdde-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="9cdde-130">アイテムが正常に更新されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="9cdde-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="9cdde-131">**応答ヘッダー** - なし。</span><span class="sxs-lookup"><span data-stu-id="9cdde-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="9cdde-132">**応答本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="9cdde-132">**Response Body** - None.</span></span>
  

