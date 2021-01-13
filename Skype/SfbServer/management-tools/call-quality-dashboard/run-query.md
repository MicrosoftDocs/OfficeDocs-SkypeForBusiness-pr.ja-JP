---
title: クエリの実行
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
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: '概要: 呼び出し品質ダッシュボードのデータ API の一部であるクエリの実行操作について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: bff24ca5a4d651ba276b4b0d795afabce3c6d0dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803117"
---
# <a name="run-query"></a>クエリの実行

**概要:** 呼び出し品質ダッシュボードのデータ API の一部であるクエリの実行操作について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。

クエリの実行操作は、通話品質ダッシュボードのデータ API の一部です。

## <a name="run-query"></a>クエリの実行

クエリの実行操作では、指定したディメンション、測定値、およびフィルターに基づいてキューブに対してクエリを実行し、データを返す機能が提供されます。


|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **URI パラメーター** - なし。

 **要求ヘッダー** - 追加のヘッダーはありません。

 **要求本文** - JSON のサンプル要求ペイロードを次に示します。 クエリに必要なディメンション、フィルター、測定が含まれる。

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

 *フィルター*  : 結果のデータ セットに、関心のあるデータのサブセットのみが反映される、適用するフィルター式のリスト。

 *ディメンション*  : データの集計に使用されるディメンションのリストです。 少なくとも 1 つのディメンションが必要ですが、追加レベルのサブ集約を取得するために複数のディメンションを指定できます。

 *測定値*  : 指定したディメンションに基づいて集計する目的の指標である、ファクトとも呼ばれる測定値のリストです。

 *傾向*  : 結果データをカスタマイズするための追加のコントロール命令。

 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。

 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。

 **応答ヘッダー** - 追加のヘッダーはありません。

 **応答本文** - JSON の応答ペイロードのサンプルを次に示します。 このテーブルには、データを含むデータ テーブルが含まれており、また、クエリの実行時間と、そのデータがキャッシュからのデータであるかどうかを示すメタ データも含まれる。

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

 *実行時間*  : サーバーがデータを返すのにかかった合計時間。 キャッシュが関係する場合と含めない場合があります。

 *データ結果*  : クエリの結果を指定します。 次元のメンバーのすべての列と、次元のメンバー名と指定された測定値の集計値を含む各要素を含む 2 次元配列です。

 *結果はキャッシュから*  - 診断の場合です。 結果がキャッシュから取得されたのか、QoE キューブから得たのかを示します。
