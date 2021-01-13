---
title: キューブの取得
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: '概要: 呼び出し品質ダッシュボードのデータ API の一部であるキューブの取得操作について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: a3527f21bc1751c23bba088ae06c3e6702cb8c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832627"
---
# <a name="get-cube"></a><span data-ttu-id="25393-104">キューブの取得</span><span class="sxs-lookup"><span data-stu-id="25393-104">Get Cube</span></span>
 
<span data-ttu-id="25393-105">**概要:** 呼び出し品質ダッシュボードのデータ API の一部であるキューブの取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="25393-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="25393-106">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="25393-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="25393-107">キューブの取得操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="25393-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="25393-108">キューブの取得</span><span class="sxs-lookup"><span data-stu-id="25393-108">Get Cube</span></span>

<span data-ttu-id="25393-109">キューブの取得操作は、使用可能なディメンションと測定値の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="25393-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="25393-110">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="25393-110">**Method**</span></span>|<span data-ttu-id="25393-111">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="25393-111">**Request URI**</span></span>|<span data-ttu-id="25393-112">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="25393-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="25393-113">GET</span><span class="sxs-lookup"><span data-stu-id="25393-113">GET</span></span>  <br/> |<span data-ttu-id="25393-114">https:// \<portal\> /QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="25393-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="25393-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="25393-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="25393-116">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="25393-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="25393-117">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="25393-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="25393-118">**要求本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="25393-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="25393-119">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="25393-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="25393-120">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="25393-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="25393-121">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="25393-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="25393-122">**応答本文** - JSON の応答ペイロードのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="25393-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="25393-123">このサンプルでは、Cube 要素の各グループの最初の 2 つの要素のみを示しています。</span><span class="sxs-lookup"><span data-stu-id="25393-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```json
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

 <span data-ttu-id="25393-124">*KPI -*  予約済み。</span><span class="sxs-lookup"><span data-stu-id="25393-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="25393-125">要求ペイロードの KPI セクションを使用すると、クエリの実行操作で、キューブで定義された KPI の値を返します。</span><span class="sxs-lookup"><span data-stu-id="25393-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="25393-126">QoE キューブにはまだ KPI が存在しません。</span><span class="sxs-lookup"><span data-stu-id="25393-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="25393-127">*ディメンション*  - クエリ実行操作の要求ペイロードの [フィルター] セクションと [ディメンション] セクションで使用できるディメンションのリスト。</span><span class="sxs-lookup"><span data-stu-id="25393-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="25393-128">フィルター式でディメンションを使用するには、ディメンション メンバーを指定する必要があります。このメンバーは、ディメンション メンバーの取得操作を使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="25393-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="25393-129">*測定値*  : クエリ実行操作の要求ペイロードの [Measurements] セクションで使用できる測定値の一覧です。</span><span class="sxs-lookup"><span data-stu-id="25393-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

