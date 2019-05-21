---
title: キューブの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: '概要: 通話品質ダッシュボードのデータ API の一部である [キューブの取得] 操作について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 970187ce9f95700185ab09bd7aadf9045575b393
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274773"
---
# <a name="get-cube"></a><span data-ttu-id="692bd-104">キューブの取得</span><span class="sxs-lookup"><span data-stu-id="692bd-104">Get Cube</span></span>
 
<span data-ttu-id="692bd-105">**概要:** 通話品質ダッシュボードのデータ API の一部である [キューブの取得] 操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="692bd-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="692bd-106">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="692bd-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="692bd-107">"キューブの取得" 操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="692bd-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="692bd-108">キューブの取得</span><span class="sxs-lookup"><span data-stu-id="692bd-108">Get Cube</span></span>

<span data-ttu-id="692bd-109">[キューブの取得] 操作利用可能な寸法と測定値のリストを返します。</span><span class="sxs-lookup"><span data-stu-id="692bd-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="692bd-110">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="692bd-110">**Method**</span></span>|<span data-ttu-id="692bd-111">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="692bd-111">**Request URI**</span></span>|<span data-ttu-id="692bd-112">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="692bd-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="692bd-113">取得</span><span class="sxs-lookup"><span data-stu-id="692bd-113">GET</span></span>  <br/> |<span data-ttu-id="692bd-114">https://\<ポータル\>の/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="692bd-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="692bd-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="692bd-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="692bd-116">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="692bd-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="692bd-117">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="692bd-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="692bd-118">**要求本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="692bd-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="692bd-119">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="692bd-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="692bd-120">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="692bd-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="692bd-121">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="692bd-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="692bd-122">**応答本文**-以下は JSON のサンプル応答ペイロードです。</span><span class="sxs-lookup"><span data-stu-id="692bd-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="692bd-123">このサンプルは、立方体要素の各グループの最初の2つの要素のみを示しています。</span><span class="sxs-lookup"><span data-stu-id="692bd-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="692bd-124">*Kpi* -予約済み。</span><span class="sxs-lookup"><span data-stu-id="692bd-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="692bd-125">要求ペイロードの Kpi セクションでは、[クエリの実行] 操作で、キューブで定義されている Kpi の値を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="692bd-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="692bd-126">まだ QoE キューブに Kpi は存在しません。</span><span class="sxs-lookup"><span data-stu-id="692bd-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="692bd-127">[*次元*]-[クエリの実行] 操作の要求ペイロードのフィルターとディメンションセクションで使用できるディメンションの一覧です。</span><span class="sxs-lookup"><span data-stu-id="692bd-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="692bd-128">フィルター式でディメンションを使うには、ディメンションメンバーを指定する必要があります。これは、ディメンションメンバーの取得操作を使って取得できます。</span><span class="sxs-lookup"><span data-stu-id="692bd-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="692bd-129">*測定*値: 実行クエリ操作の要求ペイロードの測定セクションで使うことができる測定値の一覧です。</span><span class="sxs-lookup"><span data-stu-id="692bd-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

