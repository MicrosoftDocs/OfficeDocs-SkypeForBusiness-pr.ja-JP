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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: '概要: 呼び出し品質ダッシュボードのデータ API の一部であるキューブの取得操作について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: 67ac59589de8516d6b374d61646cc88763ef7234
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617813"
---
# <a name="get-cube"></a>キューブの取得
 
**概要:** 呼び出し品質ダッシュボードのデータ API の一部であるキューブの取得操作について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
Get Cube 操作は、通話品質ダッシュボードのデータ API の一部です。
  
## <a name="get-cube"></a>キューブの取得

Get Cube 操作は、使用可能なディメンションと測定値の一覧を返します。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/Cubestructure  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - JSON の応答ペイロードの例を以下に示します。
  
> [!NOTE]
> このサンプルでは、Cube 要素の各グループの最初の 2 つの要素のみを示しています。 
  
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

 *KPI*  - 予約済み。 要求ペイロードの KPI セクションでは、クエリの実行操作によって、キューブで定義された KPI の値を返します。 QoE キューブに KPI はまだ存在しません。
  
 *ディメンション*  - クエリ実行操作の要求ペイロードの [フィルターとディメンション] セクションで使用できるディメンションの一覧。 フィルター式でディメンションを使用するには、ディメンション メンバーを指定する必要があります。ディメンション メンバーの取得操作を使用して取得できます。
  
 *[測定値*  ] - クエリの実行操作の要求ペイロードの [測定値] セクションで使用できる測定値の一覧。
  

