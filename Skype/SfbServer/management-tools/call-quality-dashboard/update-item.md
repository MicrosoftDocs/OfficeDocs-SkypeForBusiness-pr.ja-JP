---
title: アイテムの更新
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: '概要: は、項目のサービスの一部は、更新プログラムの項目の操作について説明します。 項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 3ac56b8761f565663ffaa689c666e285b2347ed5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887950"
---
# <a name="update-item"></a><span data-ttu-id="ecec8-105">アイテムの更新</span><span class="sxs-lookup"><span data-stu-id="ecec8-105">Update Item</span></span>
 
<span data-ttu-id="ecec8-106">**の概要:** 品目サービスの一部は、更新プログラムの項目の操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="ecec8-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="ecec8-107">項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="ecec8-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="ecec8-108">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="ecec8-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="ecec8-109">更新項目の操作は、リポジトリ api の呼び出し品質のダッシュ ボードの項目のサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="ecec8-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="ecec8-110">アイテムの更新</span><span class="sxs-lookup"><span data-stu-id="ecec8-110">Update Item</span></span>

<span data-ttu-id="ecec8-111">更新プログラムの項目では、リポジトリ内の特定のアイテムを更新します。</span><span class="sxs-lookup"><span data-stu-id="ecec8-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="ecec8-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="ecec8-112">**Method**</span></span>|<span data-ttu-id="ecec8-113">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="ecec8-113">**Request URI**</span></span>|<span data-ttu-id="ecec8-114">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="ecec8-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ecec8-115">配置</span><span class="sxs-lookup"><span data-stu-id="ecec8-115">PUT</span></span>  <br/> |<span data-ttu-id="ecec8-116">https://\<ポータル\>/QoERepositoryService/リポジトリ/アイテム/{アイテム Id}</span><span class="sxs-lookup"><span data-stu-id="ecec8-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="ecec8-117">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="ecec8-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ecec8-118">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="ecec8-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ecec8-119">**要求ヘッダー**のコンテンツ ・ タイプ: アプリケーションまたは json。</span><span class="sxs-lookup"><span data-stu-id="ecec8-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="ecec8-120">**リクエストの本文**に JSON。</span><span class="sxs-lookup"><span data-stu-id="ecec8-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="ecec8-121">要求ペイロードをサンプルします。</span><span class="sxs-lookup"><span data-stu-id="ecec8-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="ecec8-122">*コンテンツ* JSON では、既存のサブ項目の新しいコンテンツとして格納するデータが書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="ecec8-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="ecec8-123">技術的には、リポジトリは、任意のスキーマのすべてのコンテンツを格納できますが、使用すると、品質のダッシュ ボードを呼び出すことがレポートまたはクエリのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="ecec8-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="ecec8-124">*タイプ* 品質のダッシュ ボードを呼び出すため、「アプリケーションと json」を必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="ecec8-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="ecec8-125">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ecec8-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ecec8-126">**ステータス コード**が正常終了した操作では、ステータス コード 204 (コンテンツなし) を返します。</span><span class="sxs-lookup"><span data-stu-id="ecec8-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="ecec8-127">指定した項目の ID が見つからない場合は、ステータス コード 404 (見つかりません) を返します。</span><span class="sxs-lookup"><span data-stu-id="ecec8-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ecec8-128">「コンテンツなし」は、エラー状態ではありません。</span><span class="sxs-lookup"><span data-stu-id="ecec8-128">"No Content" is not an error status.</span></span> <span data-ttu-id="ecec8-129">ある応答何も返しませんでした (これに対して、本文に 200 OK を返します。 コンテンツ) の本文を意味します。</span><span class="sxs-lookup"><span data-stu-id="ecec8-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="ecec8-130">アイテムが正常に更新されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="ecec8-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="ecec8-131">**応答ヘッダー**の [なし] です。</span><span class="sxs-lookup"><span data-stu-id="ecec8-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="ecec8-132">**応答本体**がないです。</span><span class="sxs-lookup"><span data-stu-id="ecec8-132">**Response Body** - None.</span></span>
  

