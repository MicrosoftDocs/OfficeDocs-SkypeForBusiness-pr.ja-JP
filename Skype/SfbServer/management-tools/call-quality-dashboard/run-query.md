---
title: クエリの実行
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
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: '概要: 呼び出し品質ダッシュボードのデータ API の一部であるクエリの実行操作について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: bff24ca5a4d651ba276b4b0d795afabce3c6d0dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803117"
---
# <a name="run-query"></a><span data-ttu-id="410cd-104">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="410cd-104">Run Query</span></span>

<span data-ttu-id="410cd-105">**概要:** 呼び出し品質ダッシュボードのデータ API の一部であるクエリの実行操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="410cd-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="410cd-106">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="410cd-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="410cd-107">クエリの実行操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="410cd-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="410cd-108">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="410cd-108">Run Query</span></span>

<span data-ttu-id="410cd-109">クエリの実行操作では、指定したディメンション、測定値、およびフィルターに基づいてキューブに対してクエリを実行し、データを返す機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="410cd-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="410cd-110">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="410cd-110">**Method**</span></span>|<span data-ttu-id="410cd-111">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="410cd-111">**Request URI**</span></span>|<span data-ttu-id="410cd-112">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="410cd-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="410cd-113">POST</span><span class="sxs-lookup"><span data-stu-id="410cd-113">POST</span></span>  <br/> |<span data-ttu-id="410cd-114">https:// \<portal\> /QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="410cd-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="410cd-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="410cd-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="410cd-116">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="410cd-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="410cd-117">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="410cd-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="410cd-118">**要求本文** - JSON のサンプル要求ペイロードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="410cd-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="410cd-119">クエリに必要なディメンション、フィルター、測定が含まれる。</span><span class="sxs-lookup"><span data-stu-id="410cd-119">It contains dimensions, filters, and measurement required for a query.</span></span>

```json
{
"Filters": [{
"DataModelName": "[StartDate].[Month]",
"Caption": "July 2013",
"Value": "[2015-03-01T00:00:00]",
"Operand": 0,
"UnionGroup": ""
}],
"Dimensions": [{
"DataModelName": "[StartDate].[Month]"
}],
"Measurements": [{
"DataModelName": "[Measures].[Audio Good Streams Count]"
},
{
"DataModelName": "[Measures].[Audio UnClassified Streams Count]"
},
{
"DataModelName": "[Measures].[Audio Poor Streams Count]"
},
{
"DataModelName": "[Measures].[AudioPoorPercentage]"
}],
"Trend": {
"EnableTrend": true,
"SpanCount": 7,
"TrendDate": "2015-3",
"Type": 0
}
}
```

 <span data-ttu-id="410cd-120">*フィルター*  : 結果のデータ セットに、関心のあるデータのサブセットのみが反映される、適用するフィルター式のリスト。</span><span class="sxs-lookup"><span data-stu-id="410cd-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="410cd-121">*ディメンション*  : データの集計に使用されるディメンションのリストです。</span><span class="sxs-lookup"><span data-stu-id="410cd-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="410cd-122">少なくとも 1 つのディメンションが必要ですが、追加レベルのサブ集約を取得するために複数のディメンションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="410cd-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="410cd-123">*測定値*  : 指定したディメンションに基づいて集計する目的の指標である、ファクトとも呼ばれる測定値のリストです。</span><span class="sxs-lookup"><span data-stu-id="410cd-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="410cd-124">*傾向*  : 結果データをカスタマイズするための追加のコントロール命令。</span><span class="sxs-lookup"><span data-stu-id="410cd-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="410cd-125">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="410cd-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="410cd-126">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="410cd-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="410cd-127">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="410cd-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="410cd-128">**応答本文** - JSON の応答ペイロードのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="410cd-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="410cd-129">このテーブルには、データを含むデータ テーブルが含まれており、また、クエリの実行時間と、そのデータがキャッシュからのデータであるかどうかを示すメタ データも含まれる。</span><span class="sxs-lookup"><span data-stu-id="410cd-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

```json
{
"ExecutionTime": "00:00:00.2102630",
"DataResult": [["September 2014",
        1792,
        34,
        78,
        4.171],
        ["October 2014",
        37017,
        1731,
        3305,
        8.197],
        ["November 2014",
        79184,
        3033,
        5556,
        6.557],
        ["December 2014",
        122253,
        4050,
        5444,
        4.263],
        ["January 2015",
        31246,
        1069,
        1342,
        4.118]],
"ResultIsFromCache": false,
"ErrorType": 0
}
```

 <span data-ttu-id="410cd-130">*実行時間*  : サーバーがデータを返すのにかかった合計時間。</span><span class="sxs-lookup"><span data-stu-id="410cd-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="410cd-131">キャッシュが関係する場合と含めない場合があります。</span><span class="sxs-lookup"><span data-stu-id="410cd-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="410cd-132">*データ結果*  : クエリの結果を指定します。</span><span class="sxs-lookup"><span data-stu-id="410cd-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="410cd-133">次元のメンバーのすべての列と、次元のメンバー名と指定された測定値の集計値を含む各要素を含む 2 次元配列です。</span><span class="sxs-lookup"><span data-stu-id="410cd-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="410cd-134">*結果はキャッシュから*  - 診断の場合です。</span><span class="sxs-lookup"><span data-stu-id="410cd-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="410cd-135">結果がキャッシュから取得されたのか、QoE キューブから得たのかを示します。</span><span class="sxs-lookup"><span data-stu-id="410cd-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
