---
title: 直近の統合データの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: '概要: 通話品質ダッシュボードのデータ API の一部である、[最終統合データの取得] 操作について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: d110bdc1fe88a9fe7f77abe7f7b9ed47a3324eb0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274696"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="b37f0-104">直近の統合データの取得</span><span class="sxs-lookup"><span data-stu-id="b37f0-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="b37f0-105">**概要:** 通話品質ダッシュボードのデータ API の一部である、[最終統合データの取得] 操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="b37f0-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="b37f0-106">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="b37f0-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b37f0-107">"最終の統合データの取得" 操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="b37f0-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="b37f0-108">直近の統合データの取得</span><span class="sxs-lookup"><span data-stu-id="b37f0-108">Get Last Integration Data</span></span>

<span data-ttu-id="b37f0-109">最新の統合データの取得操作アーカイブとキューブの処理の最終5回の成功/失敗のリストを返します。</span><span class="sxs-lookup"><span data-stu-id="b37f0-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="b37f0-110">この機能は既定で無効になっており、データ API を構成して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b37f0-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="b37f0-111">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="b37f0-111">**Method**</span></span>|<span data-ttu-id="b37f0-112">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="b37f0-112">**Request URI**</span></span>|<span data-ttu-id="b37f0-113">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="b37f0-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b37f0-114">取得</span><span class="sxs-lookup"><span data-stu-id="b37f0-114">GET</span></span>  <br/> |<span data-ttu-id="b37f0-115">https://\<ポータル\>の/QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="b37f0-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="b37f0-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="b37f0-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="b37f0-117">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="b37f0-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="b37f0-118">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="b37f0-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b37f0-119">**要求本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="b37f0-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="b37f0-120">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b37f0-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="b37f0-121">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="b37f0-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="b37f0-122">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="b37f0-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b37f0-123">**応答本文**-以下は、ログの状態の例です。</span><span class="sxs-lookup"><span data-stu-id="b37f0-123">**Response Body** - Below is a sample log status.</span></span>
  
```
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
