---
title: クエリの実行
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: '概要: 呼び出し品質ダッシュボードのデータ API の一部であるクエリの実行操作について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: 65ff47013f1f11d6d9e5a26ea9031b993f134973
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766405"
---
# <a name="run-query"></a>クエリの実行

**概要:** 呼び出し品質ダッシュボードのデータ API の一部であるクエリの実行操作について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。

クエリの実行操作は、通話品質ダッシュボードのデータ API の一部です。

## <a name="run-query"></a>クエリの実行

クエリの実行操作では、指定したディメンション、測定値、フィルターに基づいてキューブでクエリを実行し、データを返す機能を提供します。


|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **URI パラメーター** - なし。

 **要求ヘッダー** - 追加のヘッダーはありません。

 **要求本文** - JSON のサンプル要求ペイロードを次に示します。 クエリに必要なディメンション、フィルター、および測定が含まれる。

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

 *フィルター*  - 結果のデータ セットが関心のあるデータのサブセットのみを反映するように適用するフィルター式の一覧。

 *ディメンション*  - データの集計に使用されるディメンションの一覧です。 少なくとも 1 つのディメンションが必要ですが、追加のレベルのサブ集計を取得するために複数のディメンションを指定できます。

 *[測定値*  ] - 指定したディメンションに基づいて集計する目的の指標である、ファクトとも呼ばれる測定値の一覧です。

 *Trend*  - 結果データをカスタマイズするための追加のコントロール命令。

 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。

 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。

 **応答ヘッダー** - 追加のヘッダーはありません。

 **応答本文** - JSON の応答ペイロードの例を以下に示します。 このテーブルには、データを含むデータ テーブルが含まれており、また、クエリの実行時間と、データがキャッシュからのデータであるかどうかを示すメタデータも含まれる。

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

 *実行時間*  - サーバーがデータを返すのにかかった合計時間。 これは、キャッシュを含む場合と含めない場合があります。

 *データの結果*  - クエリの結果。 この配列は、ディメンションのメンバーのすべての配列と、ディメンションのメンバー名と指定した Measurements の集計値を含む各要素を含む 2 次元配列です。

 *結果はキャッシュから*  - 診断の場合です。 結果がキャッシュから来たのか、QoE キューブから来たのかを示します。
