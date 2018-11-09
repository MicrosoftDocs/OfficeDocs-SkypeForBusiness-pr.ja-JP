---
title: キューブを取得します。
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
ms.openlocfilehash: 228ebd8f9bcb6db919f418ef9809bce1b3eb7f90
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035674"
---
# <a name="get-cube"></a>キューブを取得します。
 
**の概要:** 品質のダッシュ ボードを呼び出すためのデータ API の一部では、キューブの取得操作について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。
  
キューブの取得操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部です。
  
## <a name="get-cube"></a>キューブを取得します。

キューブの取得操作は、使用可能なディメンションと測定値の一覧を返します。
  

|**メソッド**|**URI を要求します。**|**HTTP のバージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>/QoEDataService/CubeStructure  <br/> |HTTP 1.1/  <br/> |
   
 **URI パラメーター**を [なし] です。
  
 **要求ヘッダー**の追加のヘッダーではありません。
  
 **リクエストの本文**の [なし] です。
  
 **応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。
  
 **ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。
  
 **応答ヘッダー**の追加のヘッダーではありません。
  
 **応答本体**の JSON のサンプル応答の内容を次に示します。
  
> [!NOTE]
> このサンプルを表示しているキューブの要素の各グループの最初の 2 つの要素です。 
  
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

 *Kpi*に予約されています。 要求ペイロードの Kpi セクションは、キューブで定義されている Kpi の値を返すクエリの実行操作を使用します。 Kpi が存在しない QoE キューブにまだです。
  
 *ディメンション*のクエリの実行操作の要求のペイロードのフィルターと分析コードのセクションで使用できるディメンションの一覧です。 フィルター式でディメンションを使用して、ディメンション メンバーの取得操作を使用して取得できるディメンション メンバーを指定する必要があります。
  
 *測定値*のクエリの実行操作の要求の内容の測定に使用できる値の一覧です。
  

