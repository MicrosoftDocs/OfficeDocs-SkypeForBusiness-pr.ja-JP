---
title: キューブの取得
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: '概要: は、品質のダッシュ ボードを呼び出すためのデータ API の一部では、キューブの取得操作について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 5c0623b92c9169a9e54f92d21358fb377c84a8f8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897137"
---
# <a name="get-cube"></a><span data-ttu-id="f4999-104">キューブの取得</span><span class="sxs-lookup"><span data-stu-id="f4999-104">Get Cube</span></span>
 
<span data-ttu-id="f4999-105">**の概要:** 品質のダッシュ ボードを呼び出すためのデータ API の一部では、キューブの取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="f4999-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="f4999-106">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="f4999-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f4999-107">キューブの取得操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="f4999-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="f4999-108">キューブの取得</span><span class="sxs-lookup"><span data-stu-id="f4999-108">Get Cube</span></span>

<span data-ttu-id="f4999-109">キューブの取得操作は、使用可能なディメンションと測定値の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="f4999-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="f4999-110">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="f4999-110">**Method**</span></span>|<span data-ttu-id="f4999-111">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="f4999-111">**Request URI**</span></span>|<span data-ttu-id="f4999-112">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="f4999-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4999-113">取得</span><span class="sxs-lookup"><span data-stu-id="f4999-113">GET</span></span>  <br/> |<span data-ttu-id="f4999-114">https://\<ポータル\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="f4999-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="f4999-115">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="f4999-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="f4999-116">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="f4999-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="f4999-117">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="f4999-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f4999-118">**リクエストの本文**の [なし] です。</span><span class="sxs-lookup"><span data-stu-id="f4999-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="f4999-119">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4999-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="f4999-120">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="f4999-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="f4999-121">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="f4999-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f4999-122">**応答本体**の JSON のサンプル応答の内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f4999-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4999-123">このサンプルを表示しているキューブの要素の各グループの最初の 2 つの要素です。</span><span class="sxs-lookup"><span data-stu-id="f4999-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}
```

 <span data-ttu-id="f4999-124">*Kpi*に予約されています。</span><span class="sxs-lookup"><span data-stu-id="f4999-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="f4999-125">要求ペイロードの Kpi セクションは、キューブで定義されている Kpi の値を返すクエリの実行操作を使用します。</span><span class="sxs-lookup"><span data-stu-id="f4999-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="f4999-126">Kpi が存在しない QoE キューブにまだです。</span><span class="sxs-lookup"><span data-stu-id="f4999-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="f4999-127">*ディメンション*のクエリの実行操作の要求のペイロードのフィルターと分析コードのセクションで使用できるディメンションの一覧です。</span><span class="sxs-lookup"><span data-stu-id="f4999-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="f4999-128">フィルター式でディメンションを使用して、ディメンション メンバーの取得操作を使用して取得できるディメンション メンバーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4999-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="f4999-129">*測定値*のクエリの実行操作の要求の内容の測定に使用できる値の一覧です。</span><span class="sxs-lookup"><span data-stu-id="f4999-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

