---
title: アイテムの更新
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: '概要: 項目サービスの一部である、項目の更新操作について説明します。 項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 460e6b26375bba28887d170c9827864bfc600138
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816676"
---
# <a name="update-item"></a><span data-ttu-id="e05fe-105">アイテムの更新</span><span class="sxs-lookup"><span data-stu-id="e05fe-105">Update Item</span></span>
 
<span data-ttu-id="e05fe-106">**概要:** 項目サービスの一部である、項目の更新操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="e05fe-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="e05fe-107">項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="e05fe-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="e05fe-108">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="e05fe-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e05fe-109">アイテムの更新操作は、[リポジトリ API for Call Quality] ダッシュボードのアイテムサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="e05fe-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="e05fe-110">アイテムの更新</span><span class="sxs-lookup"><span data-stu-id="e05fe-110">Update Item</span></span>

<span data-ttu-id="e05fe-111">更新アイテムによって、リポジトリ内の特定のアイテムが更新されます。</span><span class="sxs-lookup"><span data-stu-id="e05fe-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="e05fe-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="e05fe-112">**Method**</span></span>|<span data-ttu-id="e05fe-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="e05fe-113">**Request URI**</span></span>|<span data-ttu-id="e05fe-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="e05fe-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e05fe-115">言う</span><span class="sxs-lookup"><span data-stu-id="e05fe-115">PUT</span></span>  <br/> |<span data-ttu-id="e05fe-116">https://\<ポータル\>の/QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="e05fe-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="e05fe-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="e05fe-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="e05fe-118">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="e05fe-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="e05fe-119">**要求ヘッダー** -Content-Type: application/json。</span><span class="sxs-lookup"><span data-stu-id="e05fe-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="e05fe-120">**要求本文**-JSON。</span><span class="sxs-lookup"><span data-stu-id="e05fe-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="e05fe-121">要求ペイロードの例:</span><span class="sxs-lookup"><span data-stu-id="e05fe-121">Sample request payload:</span></span>
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="e05fe-122">*コンテンツ* 既存のサブ項目の新しいコンテンツとして保存される JSON 形式のデータ。</span><span class="sxs-lookup"><span data-stu-id="e05fe-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="e05fe-123">技術的には、リポジトリには任意のスキーマのコンテンツを保存できますが、通話品質ダッシュボードに使用する場合は、レポートまたはクエリのいずれかにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e05fe-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="e05fe-124">*入力* 通話品質ダッシュボードの場合は、常に "application/json" を指定します。</span><span class="sxs-lookup"><span data-stu-id="e05fe-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="e05fe-125">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e05fe-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="e05fe-126">**状態コード**-正常に動作している操作は、状態コード 204 (コンテンツなし) を返します。</span><span class="sxs-lookup"><span data-stu-id="e05fe-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="e05fe-127">指定した項目 ID が見つからない場合は、状態コード 404 (見つからない) が返されます。</span><span class="sxs-lookup"><span data-stu-id="e05fe-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e05fe-128">"コンテンツなし" はエラー状態ではありません。</span><span class="sxs-lookup"><span data-stu-id="e05fe-128">"No Content" is not an error status.</span></span> <span data-ttu-id="e05fe-129">これは、応答が本文に何も返されなかったことを意味します (これは、200 OK は本文の内容を返します)。</span><span class="sxs-lookup"><span data-stu-id="e05fe-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="e05fe-130">項目が正常に更新されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="e05fe-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="e05fe-131">**応答ヘッダー** -なし。</span><span class="sxs-lookup"><span data-stu-id="e05fe-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="e05fe-132">**応答本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="e05fe-132">**Response Body** - None.</span></span>
  

