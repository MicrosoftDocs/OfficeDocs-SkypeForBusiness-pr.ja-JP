---
title: 最後の統合データを取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: '概要: は、品質のダッシュ ボードを呼び出すためのデータ API の一部では、最後の統合データの取得操作について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: b2e759766987b6ee52795845ee55546920181807
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035596"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="89e97-104">最後の統合データを取得します。</span><span class="sxs-lookup"><span data-stu-id="89e97-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="89e97-105">**の概要:** 品質のダッシュ ボードを呼び出すためのデータ API の一部では、最後の統合データの取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="89e97-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="89e97-106">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="89e97-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="89e97-107">最後の統合データの取得操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="89e97-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="89e97-108">最後の統合データを取得します。</span><span class="sxs-lookup"><span data-stu-id="89e97-108">Get Last Integration Data</span></span>

<span data-ttu-id="89e97-109">最後の統合データの取得操作では、アーカイブ、およびキューブの処理の最後の 5 の成功または失敗のリストを返します。</span><span class="sxs-lookup"><span data-stu-id="89e97-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="89e97-110">この機能が既定で無効になっているし、データの API を構成することによって有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89e97-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="89e97-111">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="89e97-111">**Method**</span></span>|<span data-ttu-id="89e97-112">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="89e97-112">**Request URI**</span></span>|<span data-ttu-id="89e97-113">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="89e97-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89e97-114">取得</span><span class="sxs-lookup"><span data-stu-id="89e97-114">GET</span></span>  <br/> |<span data-ttu-id="89e97-115">https://\<ポータル\>/QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="89e97-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="89e97-116">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="89e97-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="89e97-117">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="89e97-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="89e97-118">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="89e97-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="89e97-119">**リクエストの本文**の [なし] です。</span><span class="sxs-lookup"><span data-stu-id="89e97-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="89e97-120">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="89e97-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="89e97-121">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="89e97-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="89e97-122">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="89e97-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="89e97-123">**応答本文**のサンプル ログの状態を次に示します。</span><span class="sxs-lookup"><span data-stu-id="89e97-123">**Response Body** - Below is a sample log status.</span></span>
  
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