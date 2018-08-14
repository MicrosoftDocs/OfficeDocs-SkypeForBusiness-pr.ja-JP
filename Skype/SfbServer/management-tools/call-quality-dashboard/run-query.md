---
title: クエリを実行します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: '概要: は、品質のダッシュ ボードを呼び出すためのデータ API の一部であるクエリの実行の操作について説明します。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。'
ms.openlocfilehash: 3720ce118537963e5093741c4f05315e887bd60d
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569748"
---
# <a name="run-query"></a>クエリを実行します。
 
**の概要:** 品質のダッシュ ボードを呼び出すためのデータ API の一部であるクエリの実行の操作について説明します。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。
  
クエリの実行操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部です。
  
## <a name="run-query"></a>クエリを実行します。

操作には、指定した寸法、測定、およびフィルターに基づいて、キューブに対してクエリを実行する機能が用意されています。 クエリを実行し、データを返します。
  

|**メソッド**|**URI を要求します。**|**HTTP のバージョン**|
|:-----|:-----|:-----|
|投稿  <br/> |https://\<ポータル\>/QoEDataService/RunQuery  <br/> |HTTP 1.1/  <br/> |
   
 **URI パラメーター**を [なし] です。
  
 **要求ヘッダー**の追加のヘッダーではありません。
  
 **要求の本体**をここでは、JSON 内のサンプル要求ペイロードです。 ディメンション、フィルター、およびクエリに必要な測定が含まれています。
  
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

 *フィルター*の結果のデータ セットは、興味のあるデータのサブセットのみを反映するように適用するフィルター式の一覧です。
  
 *ディメンション*のデータを集約するために使用されるディメンションの一覧です。 1 つ以上のディメンションが必要ですが、サブの集計の追加レベルを取得するのには複数のディメンションを指定することがあります。
  
 *測定値*- 測定値とも呼ばれるファクトは、集計に必要な基準のリストは、指定した寸法に基づいています。
  
 *傾向*の結果データをカスタマイズするのには追加のコントロールの説明です。
  
 **応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。
  
 **ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。
  
 **応答ヘッダー**の追加のヘッダーではありません。
  
 **応答本体**の JSON のサンプル応答の内容を次に示します。 データを格納するデータ テーブルが含まれている、メタ ・ データは、クエリの実行時間とキャッシュからデータがあるかどうかが表示を含めることもできます。
  
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

 *実行時*のサーバーにデータを返すにかかった時間の合計です。 これは、キャッシュされない場合があります。
  
 *データ結果*のクエリの結果です。 ディメンションのメンバーのすべての順列とディメンションのメンバーの名前として指定された測定値の集計値を格納している各要素を含む 2 次元配列することをお勧めします。
  
 *結果はキャッシュから*の診断です。 QoE キューブと、キャッシュから結果が付属しているかどうかを示します。