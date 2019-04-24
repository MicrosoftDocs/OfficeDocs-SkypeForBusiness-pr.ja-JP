---
title: キャッシュのクリア
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: '概要: は、品質のダッシュ ボードを呼び出すためのデータ API の一部では、キャッシュのクリア操作について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: c2371a7f99eb37e8e01be919bf6c31b0c9a452cb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32195552"
---
# <a name="clear-cache"></a><span data-ttu-id="68fbf-104">キャッシュのクリア</span><span class="sxs-lookup"><span data-stu-id="68fbf-104">Clear Cache</span></span>
 
<span data-ttu-id="68fbf-105">**の概要:** 品質のダッシュ ボードを呼び出すためのデータ API の一部では、キャッシュのクリア操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="68fbf-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="68fbf-106">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="68fbf-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="68fbf-107">キャッシュのクリアの操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="68fbf-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="68fbf-108">キャッシュのクリア</span><span class="sxs-lookup"><span data-stu-id="68fbf-108">Clear Cache</span></span>

<span data-ttu-id="68fbf-109">キャッシュのクリアの操作は、クエリとデータのサーバー上のキャッシュを削除します。</span><span class="sxs-lookup"><span data-stu-id="68fbf-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="68fbf-110">キャッシュがリセットし、紹介最新データ QoE キューブから後で新しい要求をします。</span><span class="sxs-lookup"><span data-stu-id="68fbf-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="68fbf-111">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="68fbf-111">**Method**</span></span>|<span data-ttu-id="68fbf-112">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="68fbf-112">**Request URI**</span></span>|<span data-ttu-id="68fbf-113">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="68fbf-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="68fbf-114">投稿</span><span class="sxs-lookup"><span data-stu-id="68fbf-114">POST</span></span>  <br/> |<span data-ttu-id="68fbf-115">https://\<ポータル\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="68fbf-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="68fbf-116">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="68fbf-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="68fbf-117">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="68fbf-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="68fbf-118">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="68fbf-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="68fbf-119">**リクエストの本文**の [なし] です。</span><span class="sxs-lookup"><span data-stu-id="68fbf-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="68fbf-120">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="68fbf-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="68fbf-121">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="68fbf-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="68fbf-122">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="68fbf-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="68fbf-123">**応答本体**がないです。</span><span class="sxs-lookup"><span data-stu-id="68fbf-123">**Response Body** - None.</span></span>
  

