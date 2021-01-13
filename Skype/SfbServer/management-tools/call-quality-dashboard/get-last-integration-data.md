---
title: 直近の統合データの取得
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: '概要: 通話品質ダッシュボードのデータ API の一部である、最後の統合データの取得操作について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: c40041e41e04d2bdc62a9eb9fa1eb699697a5b3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832517"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="b423a-104">直近の統合データの取得</span><span class="sxs-lookup"><span data-stu-id="b423a-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="b423a-105">**概要:** 呼び出し品質ダッシュボードのデータ API の一部である、最後の統合データの取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="b423a-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="b423a-106">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="b423a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b423a-107">最後の統合データの取得操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="b423a-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="b423a-108">直近の統合データの取得</span><span class="sxs-lookup"><span data-stu-id="b423a-108">Get Last Integration Data</span></span>

<span data-ttu-id="b423a-109">[最後の統合データの取得] 操作では、アーカイブとキューブ処理の最後の 5 つの成功/失敗のリストが返されます。</span><span class="sxs-lookup"><span data-stu-id="b423a-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="b423a-110">この機能は既定で無効になっています。データ API を構成して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b423a-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="b423a-111">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="b423a-111">**Method**</span></span>|<span data-ttu-id="b423a-112">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="b423a-112">**Request URI**</span></span>|<span data-ttu-id="b423a-113">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="b423a-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b423a-114">GET</span><span class="sxs-lookup"><span data-stu-id="b423a-114">GET</span></span>  <br/> |<span data-ttu-id="b423a-115">https:// \<portal\> /QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="b423a-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="b423a-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="b423a-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="b423a-117">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="b423a-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="b423a-118">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="b423a-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b423a-119">**要求本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="b423a-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="b423a-120">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b423a-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="b423a-121">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="b423a-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="b423a-122">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="b423a-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b423a-123">**応答本文** - 以下にログの状態のサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="b423a-123">**Response Body** - Below is a sample log status.</span></span>
  
```json
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
