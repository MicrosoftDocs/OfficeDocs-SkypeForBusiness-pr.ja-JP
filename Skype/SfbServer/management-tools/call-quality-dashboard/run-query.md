---
title: クエリの実行
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: '概要: 通話品質ダッシュボードのデータ API の一部である [クエリの実行] 操作について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 8d31ea4c597ea3353fdd5da3e863938aababe819
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991402"
---
# <a name="run-query"></a><span data-ttu-id="00f97-104">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="00f97-104">Run Query</span></span>

<span data-ttu-id="00f97-105">**概要:** 通話品質ダッシュボードのデータ API の一部である [クエリの実行] 操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="00f97-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="00f97-106">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="00f97-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="00f97-107">クエリの実行操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="00f97-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="00f97-108">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="00f97-108">Run Query</span></span>

<span data-ttu-id="00f97-109">クエリの実行操作指定したサイズ、測定値、フィルターに基づいてキューブに対してクエリを実行し、データを戻すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="00f97-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="00f97-110">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="00f97-110">**Method**</span></span>|<span data-ttu-id="00f97-111">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="00f97-111">**Request URI**</span></span>|<span data-ttu-id="00f97-112">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="00f97-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="00f97-113">投稿</span><span class="sxs-lookup"><span data-stu-id="00f97-113">POST</span></span>  <br/> |<span data-ttu-id="00f97-114">https://\<ポータル\>の/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="00f97-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="00f97-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="00f97-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="00f97-116">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="00f97-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="00f97-117">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="00f97-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="00f97-118">**要求本文**: JSON での要求ペイロードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="00f97-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="00f97-119">クエリに必要なディメンション、フィルター、測定値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="00f97-119">It contains dimensions, filters, and measurement required for a query.</span></span>

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

 <span data-ttu-id="00f97-120">*フィルター* -結果として得られるデータのサブセットのみが反映されるように、フィルター式の一覧が適用されます。</span><span class="sxs-lookup"><span data-stu-id="00f97-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="00f97-121">[*次元*]-データの集計に使用されるディメンションの一覧です。</span><span class="sxs-lookup"><span data-stu-id="00f97-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="00f97-122">少なくとも1つのディメンションが必要ですが、サブ集計の追加レベルを取得するために複数の次元が指定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="00f97-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="00f97-123">*測定*値: 指定した寸法に基づいて集計する必要がある測定値の一覧です。ファクトとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="00f97-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="00f97-124">*傾向*-結果データをカスタマイズするための追加のコントロール命令。</span><span class="sxs-lookup"><span data-stu-id="00f97-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="00f97-125">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="00f97-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="00f97-126">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="00f97-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="00f97-127">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="00f97-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="00f97-128">**応答本文**-以下は JSON のサンプル応答ペイロードです。</span><span class="sxs-lookup"><span data-stu-id="00f97-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="00f97-129">データを含むデータテーブルも含まれています。これには、クエリの実行時間と、そのデータがキャッシュからのものかどうかを示すメタデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="00f97-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

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

 <span data-ttu-id="00f97-130">*実行時間*: サーバーがデータを返すのにかかった時間の合計です。</span><span class="sxs-lookup"><span data-stu-id="00f97-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="00f97-131">これには、キャッシュが含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="00f97-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="00f97-132">*データ結果*-クエリの結果。</span><span class="sxs-lookup"><span data-stu-id="00f97-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="00f97-133">これは、次元のメンバーのすべての順列と、次元のメンバー名を含む各要素、および指定された測定値の集計値を含む2次元配列です。</span><span class="sxs-lookup"><span data-stu-id="00f97-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="00f97-134">結果は、診断用の*キャッシュから得られ*ます。</span><span class="sxs-lookup"><span data-stu-id="00f97-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="00f97-135">結果がキャッシュからのものか、QoE キューブからのものかを示します。</span><span class="sxs-lookup"><span data-stu-id="00f97-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
