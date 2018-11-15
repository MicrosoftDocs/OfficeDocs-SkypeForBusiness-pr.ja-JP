---
title: 通話品質のダッシュ ボード (救難) ビジネス サーバーの Skype でのデータ API
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: '概要: は、通話品質のダッシュ ボードの期間の API について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 0af168c46e8b2732d5c967550391ab52459ddf95
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531758"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>通話品質のダッシュ ボード (救難) ビジネス サーバーの Skype でのデータ API
 
**の概要:** 通話品質のダッシュ ボードには、期間の API について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。
  
データ API は、ビジネスのサーバーの Skype の品質のダッシュ ボードを呼び出すためのプログラムによるアクセスを提供します。
  
## <a name="data-api-for-call-quality-dashboard"></a>通話品質のダッシュ ボードのデータ API

データ API では、QoE のキューブにクエリ インターフェイスを提供します。 データ API では、REST API を指定した寸法とフィルターに基づいて集計の QoE 評価尺度を提供する多次元データベースを操作するためです。
  
次の表には、他の操作が含まれます。
  

|**操作**|**説明**|
|:-----|:-----|
|[キューブを取得します。](get-cube.md) <br/> |使用可能なディメンションと測定値の一覧を取得します。  <br/> |
|[ディメンション メンバーを取得します。](get-dimension-members.md) <br/> |ディメンション メンバーの取得操作は、特定のディメンションのメンバーの一覧を返します。 また、メンバーの一覧をフィルター処理し、ワイヤ転送コストを削減するのには、サブセットを取得する機能を提供します。  <br/> |
|[クエリを実行します。](run-query.md) <br/> |操作には、指定した寸法、測定、およびフィルターに基づいて、キューブに対してクエリを実行する機能が用意されています。 クエリを実行し、データを返します。  <br/> |
|[キャッシュのクリア](clear-cache.md) <br/> |キャッシュのクリアの操作は、クエリとデータのサーバー上のキャッシュを削除します。 キャッシュがリセットし、紹介最新データ QoE キューブから後で新しい要求をします。  <br/> |
|[統合ログを取得します。](get-integration-log.md) <br/> |操作が返されます QoE のキューブに含まれるアクティビティを説明するログ エントリの一覧を処理する統合ログを取得します。  <br/> |
|[最後の統合データを取得します。](get-last-integration-data.md) <br/> |最後の統合データをキューブから取得します。  <br/> |
   
 **クロス元のリソース共有先のデータ API のサポートを (CORS)**
  
データ API には、クロス元リソース共有 (CORS) がサポートされています。 CORS は、1 つのドメインを実行している別のドメインのリソースにアクセスする web アプリケーションを有効にする HTTP 機能です。 Web ブラウザーは、web ページから別のドメイン内の Api を呼び出すことを防止する原点が同じポリシーを[同一生成元ポリシー](https://www.w3.org/Security/wiki/Same_Origin_Policy)と呼ばれるセキュリティの制限を実装します。 CORS は、セキュリティで保護された Api を呼び出して、別のドメイン内に 1 つのドメイン (元のドメイン) を許可する手段を提供します。 CORS の詳細については、 [CORS 仕様](https://www.w3.org/TR/cors/)を参照してください。
  
 **データ API の CORS を有効にします。**
  
 CorsTrustedOrigin アプリケーションの設定に含まれる 2 つのドメインを表示、データの API の web.config ファイルの抜粋を次に示します。 データ API では、これらのサーバーから読み込まれたスクリプトによって行われたすべての要求が信頼されています。
  
(存在する場合)、正確なプロトコル、ホスト名、およびポートを含めることを忘れないでください。 置かないようにする、スラッシュ文字 (/)、最後にします。 複数のエントリをカンマで区切って指定できます。
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


