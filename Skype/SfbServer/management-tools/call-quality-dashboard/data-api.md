---
title: Skype for Business Serverの通話品質ダッシュボード (CQD) 用データ API
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: '概要: 通話品質ダッシュボードのデータ API について説明します。 通話品質ダッシュボードは、Skype for Business Server用のツールです。'
ms.openlocfilehash: 3204398dcf667f785f1efe71cc4d6dc5478ce54d
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675739"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Skype for Business Serverの通話品質ダッシュボード (CQD) 用データ API
 
**概要：** 通話品質ダッシュボード用データ API について説明します。 通話品質ダッシュボードは、Skype for Business Server用のツールです。
  
Data API は、Skype for Business Serverの通話品質ダッシュボードにプログラムによるアクセスを提供します。
  
## <a name="data-api-for-call-quality-dashboard"></a>通話品質ダッシュボード用データ API

Data API は、QoE キューブへのクエリ インターフェイスを提供します。 Data API は、指定したディメンションとフィルターに基づいて集計された QoE メトリックを提供する多次元データベースを操作するための REST API です。
  
REST 操作を次の表に示します。
  

|**操作**|**説明**|
|:-----|:-----|
|[キューブの取得](get-cube.md) <br/> |使用可能なディメンションと測定値の一覧を取得します。  <br/> |
|[ディメンションのメンバーの取得](get-dimension-members.md) <br/> |ディメンション メンバーの取得操作は、特定のディメンションのメンバーの一覧を返します。 また、メンバー リストをフィルター処理してサブセットを取得し、電信送金コストを削減することもできます。  <br/> |
|[クエリの実行](run-query.md) <br/> |クエリの実行操作では、指定したディメンション、測定値、フィルターに基づいてキューブに対してクエリを実行し、データを返す機能が提供されます。  <br/> |
|[キャッシュのクリア](clear-cache.md) <br/> |キャッシュのクリア操作では、クエリとデータのサーバー上のキャッシュが削除されます。 これによりキャッシュがリセットされ、新しい要求に対して QoE キューブから新しいデータが取得されます。  <br/> |
|[統合ログの取得](get-integration-log.md) <br/> |統合ログの取得操作は、QoE キューブ処理のアクティビティを説明するログ エントリの一覧を返します。  <br/> |
|[直近の統合データの取得](get-last-integration-data.md) <br/> |キューブから最後の統合データを取得します。  <br/> |
   
 **データ API のクロスオリジン リソース共有 (CORS) のサポート**
  
Data API では、クロスオリジン リソース共有 (CORS) がサポートされます。 CORS は、あるドメインで実行されている Web アプリケーションが別のドメインのリソースにアクセスできるようにする HTTP 機能です。 Web ブラウザーでは、 [同じ配信元ポリシー](https://www.w3.org/Security/wiki/Same_Origin_Policy) と呼ばれるセキュリティ制限が実装されています。これにより、Web ページが別のドメインの API を呼び出すのを防ぎます。 CORS は、あるドメイン (配信元ドメイン) が別のドメインの API を呼び出せるようにするための安全な方法を提供します。 CORS の詳細については、 [CORS](https://www.w3.org/TR/cors/) 仕様を参照してください。
  
 **データ API の CORS を有効にする**
  
 次に、corsTrustedOrigin アプリケーション設定に一覧表示されている 2 つのドメインを示す Data API web.configの抜粋を示します。 これらのサーバーから読み込まれたスクリプトによって行われたすべての要求は、Data API によって信頼されます。
  
プロトコル、ホスト名、ポート (存在する場合) を必ず含めます。 末尾にスラッシュ文字 (/) を入れないでください。 コンマで区切ることで、複数のエントリを指定できます。
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
...  </appSettings>
</configuration>
```


