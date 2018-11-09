---
title: クエリを実行します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: '概要: は、品質のダッシュ ボードを呼び出すためのデータ API の一部であるクエリの実行の操作について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: ac9f042a8d5b8e016a398a0daf9595ffcb9d2fcb
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035702"
---
# <a name="run-query"></a><span data-ttu-id="7bdc4-104">クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-104">Run Query</span></span>

<span data-ttu-id="7bdc4-105">**の概要:** 品質のダッシュ ボードを呼び出すためのデータ API の一部であるクエリの実行の操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="7bdc4-106">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="7bdc4-107">クエリの実行操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="7bdc4-108">クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-108">Run Query</span></span>

<span data-ttu-id="7bdc4-109">操作には、指定した寸法、測定、およびフィルターに基づいて、キューブに対してクエリを実行する機能が用意されています。 クエリを実行し、データを返します。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="7bdc4-110">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="7bdc4-110">**Method**</span></span>|<span data-ttu-id="7bdc4-111">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="7bdc4-111">**Request URI**</span></span>|<span data-ttu-id="7bdc4-112">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="7bdc4-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7bdc4-113">投稿</span><span class="sxs-lookup"><span data-stu-id="7bdc4-113">POST</span></span>  <br/> |<span data-ttu-id="7bdc4-114">https://\<ポータル\>/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="7bdc4-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="7bdc4-115">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="7bdc4-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="7bdc4-116">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="7bdc4-117">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="7bdc4-118">**要求の本体**をここでは、JSON 内のサンプル要求ペイロードです。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="7bdc4-119">ディメンション、フィルター、およびクエリに必要な測定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-119">It contains dimensions, filters, and measurement required for a query.</span></span>

```
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

 <span data-ttu-id="7bdc4-120">*フィルター*の結果のデータ セットは、興味のあるデータのサブセットのみを反映するように適用するフィルター式の一覧です。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="7bdc4-121">*ディメンション*のデータを集約するために使用されるディメンションの一覧です。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="7bdc4-122">1 つ以上のディメンションが必要ですが、サブの集計の追加レベルを取得するのには複数のディメンションを指定することがあります。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="7bdc4-123">*測定値*- 測定値とも呼ばれるファクトは、集計に必要な基準のリストは、指定した寸法に基づいています。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="7bdc4-124">*傾向*の結果データをカスタマイズするのには追加のコントロールの説明です。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="7bdc4-125">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="7bdc4-126">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="7bdc4-127">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="7bdc4-128">**応答本体**の JSON のサンプル応答の内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="7bdc4-129">データを格納するデータ テーブルが含まれている、メタ ・ データは、クエリの実行時間とキャッシュからデータがあるかどうかが表示を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

```
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

 <span data-ttu-id="7bdc4-130">*実行時*のサーバーにデータを返すにかかった時間の合計です。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="7bdc4-131">これは、キャッシュされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="7bdc4-132">*データ結果*のクエリの結果です。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="7bdc4-133">ディメンションのメンバーのすべての順列とディメンションのメンバーの名前として指定された測定値の集計値を格納している各要素を含む 2 次元配列することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="7bdc4-134">*結果はキャッシュから*の診断です。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="7bdc4-135">QoE キューブと、キャッシュから結果が付属しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7bdc4-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>