---
title: キャッシュのクリア
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: '概要: 通話品質ダッシュボードのデータ API の一部であるキャッシュのクリア操作について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806417"
---
# <a name="clear-cache"></a><span data-ttu-id="4a340-104">キャッシュのクリア</span><span class="sxs-lookup"><span data-stu-id="4a340-104">Clear Cache</span></span>
 
<span data-ttu-id="4a340-105">**概要:** 通話品質ダッシュボードのデータ API の一部であるキャッシュのクリア操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a340-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="4a340-106">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="4a340-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4a340-107">キャッシュのクリア操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="4a340-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="4a340-108">キャッシュのクリア</span><span class="sxs-lookup"><span data-stu-id="4a340-108">Clear Cache</span></span>

<span data-ttu-id="4a340-109">キャッシュをクリア操作すると、クエリとデータのサーバー上のキャッシュが削除されます。</span><span class="sxs-lookup"><span data-stu-id="4a340-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="4a340-110">これによりキャッシュがリセットされ、後で新しい要求の QoE キューブから新しいデータが取得されます。</span><span class="sxs-lookup"><span data-stu-id="4a340-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="4a340-111">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="4a340-111">**Method**</span></span>|<span data-ttu-id="4a340-112">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="4a340-112">**Request URI**</span></span>|<span data-ttu-id="4a340-113">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="4a340-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4a340-114">POST</span><span class="sxs-lookup"><span data-stu-id="4a340-114">POST</span></span>  <br/> |<span data-ttu-id="4a340-115">https:// \<portal\> /QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="4a340-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="4a340-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="4a340-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="4a340-117">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="4a340-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="4a340-118">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="4a340-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4a340-119">**要求本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="4a340-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="4a340-120">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4a340-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="4a340-121">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="4a340-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="4a340-122">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="4a340-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4a340-123">**応答本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="4a340-123">**Response Body** - None.</span></span>
  

