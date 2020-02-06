---
title: キューブの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: '概要: 通話品質ダッシュボードのデータ API の一部である [キューブの取得] 操作について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 7ae24309ea49d8f7d8d2684c141adb44c5bff2b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816836"
---
# <a name="get-cube"></a>キューブの取得
 
**概要:** 通話品質ダッシュボードのデータ API の一部である [キューブの取得] 操作について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
"キューブの取得" 操作は、通話品質ダッシュボードのデータ API の一部です。
  
## <a name="get-cube"></a>キューブの取得

[キューブの取得] 操作利用可能な寸法と測定値のリストを返します。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>の/QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** -なし。
  
 **ヘッダーを要求**する-追加のヘッダーは不要です。
  
 **要求本文**-なし。
  
 **応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。
  
 **応答ヘッダー** -ヘッダーは追加されません。
  
 **応答本文**-以下は JSON のサンプル応答ペイロードです。
  
> [!NOTE]
> このサンプルは、立方体要素の各グループの最初の2つの要素のみを示しています。 
  
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

 *Kpi* -予約済み。 要求ペイロードの Kpi セクションでは、[クエリの実行] 操作で、キューブで定義されている Kpi の値を返すことができます。 まだ QoE キューブに Kpi は存在しません。
  
 [*次元*]-[クエリの実行] 操作の要求ペイロードのフィルターとディメンションセクションで使用できるディメンションの一覧です。 フィルター式でディメンションを使うには、ディメンションメンバーを指定する必要があります。これは、ディメンションメンバーの取得操作を使って取得できます。
  
 *測定*値: 実行クエリ操作の要求ペイロードの測定セクションで使うことができる測定値の一覧です。
  

