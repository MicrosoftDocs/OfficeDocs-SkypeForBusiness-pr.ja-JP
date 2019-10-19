---
title: Skype for Business Server の通話品質ダッシュボード (CQD) のデータ API
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: '概要: 通話品質ダッシュボードのデータ API について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 016cc1be9f5cd5506f8ee7d8ddbe2765e0015ffd
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "36571921"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Skype for Business Server の通話品質ダッシュボード (CQD) のデータ API
 
**概要:** 通話品質ダッシュボードのデータ API について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
データ API は、Skype for Business Server の通話品質ダッシュボードへのプログラムによるアクセスを提供します。
  
## <a name="data-api-for-call-quality-dashboard"></a>通話品質ダッシュボードのデータ API

データ API には、QoE キューブへのクエリインターフェイスが用意されています。 データ API は、指定したサイズとフィルターに基づいて、集計された QoE メトリックを提供する多次元データベースを操作するための REST API です。
  
REST 操作は、次の表に記載されています。
  

|**操作**|**説明**|
|:-----|:-----|
|[キューブの取得](get-cube.md) <br/> |使用可能な寸法と測定値の一覧を取得します。  <br/> |
|[ディメンションのメンバーの取得](get-dimension-members.md) <br/> |ディメンションメンバーの取得操作特定のディメンションのメンバーの一覧を返します。 また、メンバーリストをフィルター処理して、送金料金を削減することができます。  <br/> |
|[クエリの実行](run-query.md) <br/> |クエリの実行操作指定したサイズ、測定値、フィルターに基づいてキューブに対してクエリを実行し、データを戻すことができるようにします。  <br/> |
|[キャッシュのクリア](clear-cache.md) <br/> |[キャッシュの消去] 操作は、クエリとデータのためにサーバー上のキャッシュを削除します。 これによりキャッシュがリセットされ、新しい要求があった場合は QoE キューブから最新のデータが取得されます。  <br/> |
|[統合ログの取得](get-integration-log.md) <br/> |統合ログの取得操作 QoE キューブ処理のアクティビティを説明するログエントリの一覧を返します。  <br/> |
|[直近の統合データの取得](get-last-integration-data.md) <br/> |キューブから最新の統合データを取得します。  <br/> |
   
 **データ API のクロスオリジンリソース共有 (CORS) のサポート**
  
データ API は、クロスオリジンリソース共有 (CORS) をサポートします。 CORS は、あるドメインで実行されている web アプリケーションが別のドメインのリソースにアクセスできるようにするための HTTP 機能です。 Web ブラウザーでは、web ページが別のドメインの Api を呼び出すことを防ぐ、同じ元のポリシーと同じ元の[ポリシー](https://www.w3.org/Security/wiki/Same_Origin_Policy)と呼ばれるセキュリティ制限が実装されています。 CORS は、1つのドメイン (元のドメイン) が別のドメインの Api を呼び出すことを許可する安全な方法を提供します。 CORS の詳細については、「 [cors の仕様](https://www.w3.org/TR/cors/)」を参照してください。
  
 **データ API に対して CORS を有効にする**
  
 次に示すのは、corsTrustedOrigin アプリケーションの設定で一覧表示されている2つのドメインを示すデータ API web.config の抜粋です。 これらのサーバーから読み込まれたスクリプトによって行われたすべての要求は、データ API によって信頼されます。
  
正確なプロトコル、ホスト名、ポート (存在する場合) を必ず含めてください。 末尾にスラッシュ文字 (/) を入力しないでください。 複数のエントリを指定するには、コンマで区切ります。
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


