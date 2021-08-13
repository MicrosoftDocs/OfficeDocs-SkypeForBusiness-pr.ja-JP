---
title: データ API for Call Quality Dashboard (CQD) in Skype for Business Server
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
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: '概要: 通話品質ダッシュボードのデータ API について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: cadb726714816f80fa818d9a706640fa52bd75529e6fc58d39ab63fe907b3bb8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333329"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>データ API for Call Quality Dashboard (CQD) in Skype for Business Server
 
**概要:** 通話品質ダッシュボードのデータ API について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
データ API は、通話品質ダッシュボードのプログラムによるアクセスを提供Skype for Business Server。
  
## <a name="data-api-for-call-quality-dashboard"></a>通話品質ダッシュボードのデータ API

データ API は、QoE キューブへのクエリ インターフェイスを提供します。 Data API は、指定したディメンションとフィルターに基づいて集約された QoE メトリックを提供する多次元データベースを操作する REST API です。
  
REST 操作は、次の表に含まれています。
  

|**操作名**|**説明**|
|:-----|:-----|
|[キューブの取得](get-cube.md) <br/> |使用可能なディメンションと測定値の一覧を取得します。  <br/> |
|[ディメンションのメンバーの取得](get-dimension-members.md) <br/> |[ディメンション メンバーの取得] 操作は、特定のディメンションのメンバーの一覧を返します。 また、メンバー リストをフィルター処理してサブセットを取得し、ワイヤー転送コストを削減する機能も提供します。  <br/> |
|[クエリの実行](run-query.md) <br/> |クエリの実行操作では、指定したディメンション、測定値、フィルターに基づいてキューブでクエリを実行し、データを返す機能を提供します。  <br/> |
|[キャッシュのクリア](clear-cache.md) <br/> |[キャッシュのクリア] 操作を実行すると、クエリとデータのサーバー上のキャッシュが削除されます。 これにより、キャッシュがリセットされ、新しい要求に対して QoE キューブから新しいデータが取得されます。  <br/> |
|[統合ログの取得](get-integration-log.md) <br/> |統合ログの取得操作は、QoE キューブ処理のアクティビティを説明するログ エントリの一覧を返します。  <br/> |
|[直近の統合データの取得](get-last-integration-data.md) <br/> |キューブから最後の統合データを取得します。  <br/> |
   
 **クロスオリジン リソース共有 (CORS) データ API のサポート**
  
データ API では、クロスオリジン リソース共有 (CORS) がサポートされています。 CORS は、あるドメインで実行されている Web アプリケーションが別のドメインのリソースにアクセスできる HTTP 機能です。 Web ブラウザーは、Web ページが別のドメインで API を呼び出すのを防ぐ [Same-Origin Policy same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) と呼ばれるセキュリティ制限を実装します。 CORS は、あるドメイン (オリジン ドメイン) が別のドメインで API を呼び出す安全な方法を提供します。 [CORS の詳細については、CORS](https://www.w3.org/TR/cors/)仕様を参照してください。
  
 **データ API の CORS の有効化**
  
 次に示すのは、corsTrustedOrigin アプリケーション設定にweb.config 2 つのドメインを示す Data API アプリケーションの抜粋です。 これらのサーバーから読み込まれたスクリプトによって行われたすべての要求は、データ API によって信頼されます。
  
正確なプロトコル、ホスト名、およびポート (必要な場合) を含める必要があります。 スラッシュ文字 (/) を末尾に置かねない。 コンマで区切って複数のエントリを指定できます。
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


