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
ms.openlocfilehash: 0b4c44c93009e014579a53872de82297c1486573
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274563"
---
# <a name="run-query"></a>クエリの実行

**概要:** 通話品質ダッシュボードのデータ API の一部である [クエリの実行] 操作について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。

クエリの実行操作は、通話品質ダッシュボードのデータ API の一部です。

## <a name="run-query"></a>クエリの実行

クエリの実行操作指定したサイズ、測定値、フィルターに基づいてキューブに対してクエリを実行し、データを戻すことができるようにします。


|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|投稿  <br/> |https://\<ポータル\>の/QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **URI パラメーター** -なし。

 **ヘッダーを要求**する-追加のヘッダーは不要です。

 **要求本文**: JSON での要求ペイロードの例を次に示します。 クエリに必要なディメンション、フィルター、測定値が含まれています。

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

 *フィルター* -結果として得られるデータのサブセットのみが反映されるように、フィルター式の一覧が適用されます。

 [*次元*]-データの集計に使用されるディメンションの一覧です。 少なくとも1つのディメンションが必要ですが、サブ集計の追加レベルを取得するために複数の次元が指定されている可能性があります。

 *測定*値: 指定した寸法に基づいて集計する必要がある測定値の一覧です。ファクトとも呼ばれます。

 *傾向*-結果データをカスタマイズするための追加のコントロール命令。

 **応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。

 **状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。

 **応答ヘッダー** -ヘッダーは追加されません。

 **応答本文**-以下は JSON のサンプル応答ペイロードです。 データを含むデータテーブルも含まれています。これには、クエリの実行時間と、そのデータがキャッシュからのものかどうかを示すメタデータが含まれます。

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

 *実行時間*: サーバーがデータを返すのにかかった時間の合計です。 これには、キャッシュが含まれていることがあります。

 *データ結果*-クエリの結果。 これは、次元のメンバーのすべての順列と、次元のメンバー名を含む各要素、および指定された測定値の集計値を含む2次元配列です。

 結果は、診断用の*キャッシュから得られ*ます。 結果がキャッシュからのものか、QoE キューブからのものかを示します。
