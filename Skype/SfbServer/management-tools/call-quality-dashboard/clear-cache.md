---
title: キャッシュのクリア
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: '概要: 通話品質ダッシュボードのデータ API の一部である、消去キャッシュ操作について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 38648e1a910f93a30bd6da8807321acad0330e62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274836"
---
# <a name="clear-cache"></a><span data-ttu-id="4ae45-104">キャッシュのクリア</span><span class="sxs-lookup"><span data-stu-id="4ae45-104">Clear Cache</span></span>
 
<span data-ttu-id="4ae45-105">**概要:** 通話品質ダッシュボードのデータ API の一部である、キャッシュのクリア操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ae45-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="4ae45-106">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="4ae45-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4ae45-107">キャッシュのクリア操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="4ae45-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="4ae45-108">キャッシュのクリア</span><span class="sxs-lookup"><span data-stu-id="4ae45-108">Clear Cache</span></span>

<span data-ttu-id="4ae45-109">[キャッシュの消去] 操作は、クエリとデータのためにサーバー上のキャッシュを削除します。</span><span class="sxs-lookup"><span data-stu-id="4ae45-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="4ae45-110">これによりキャッシュがリセットされ、新しい要求があった場合は QoE キューブから最新のデータが取得されます。</span><span class="sxs-lookup"><span data-stu-id="4ae45-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="4ae45-111">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="4ae45-111">**Method**</span></span>|<span data-ttu-id="4ae45-112">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="4ae45-112">**Request URI**</span></span>|<span data-ttu-id="4ae45-113">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="4ae45-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4ae45-114">投稿</span><span class="sxs-lookup"><span data-stu-id="4ae45-114">POST</span></span>  <br/> |<span data-ttu-id="4ae45-115">https://\<ポータル\>の/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="4ae45-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="4ae45-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="4ae45-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="4ae45-117">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="4ae45-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="4ae45-118">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="4ae45-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4ae45-119">**要求本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="4ae45-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="4ae45-120">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4ae45-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="4ae45-121">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="4ae45-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="4ae45-122">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="4ae45-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4ae45-123">**応答本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="4ae45-123">**Response Body** - None.</span></span>
  

