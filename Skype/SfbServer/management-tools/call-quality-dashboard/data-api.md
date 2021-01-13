---
title: Skype for Business Server の通話品質ダッシュボード (CQD) のデータ API
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
description: '概要: 通話品質ダッシュボードのデータ API について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 367aa1bf1103863fff37fbcd4f8d9fa379de7c1d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832697"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Skype for Business Server の通話品質ダッシュボード (CQD) のデータ API
 
**概要:** 通話品質ダッシュボードのデータ API について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
データ API は、Skype for Business Server の通話品質ダッシュボードへのプログラムによるアクセスを提供します。
  
## <a name="data-api-for-call-quality-dashboard"></a>通話品質ダッシュボードのデータ API

データ API は、QoE キューブへのクエリ インターフェイスを提供します。 データ API は、指定されたディメンションとフィルターに基づいて集計 QoE 指標を提供する、多次元データベースを操作する REST API です。
  
REST 操作を次の表に示します。
  

|**操作**|**説明**|
|:-----|:-----|
|[キューブの取得](get-cube.md) <br/> |使用可能なディメンションと測定値の一覧を取得します。  <br/> |
|[ディメンションのメンバーの取得](get-dimension-members.md) <br/> |ディメンション メンバーの取得操作は、特定のディメンションのメンバーのリストを返します。 また、メンバー リストをフィルター処理してサブセットを取得し、電信送金コストを削減する機能も提供します。  <br/> |
|[クエリの実行](run-query.md) <br/> |クエリの実行操作では、指定したディメンション、測定値、およびフィルターに基づいてキューブに対してクエリを実行し、データを返す機能が提供されます。  <br/> |
|[キャッシュのクリア](clear-cache.md) <br/> |キャッシュをクリア操作すると、クエリとデータのサーバー上のキャッシュが削除されます。 これによりキャッシュがリセットされ、後で新しい要求の QoE キューブから新しいデータが取得されます。  <br/> |
|[統合ログの取得](get-integration-log.md) <br/> |統合ログの取得操作は、QoE キューブ処理のアクティビティを記述するログ エントリのリストを返します。  <br/> |
|[直近の統合データの取得](get-last-integration-data.md) <br/> |キューブから最後の統合データを取得します。  <br/> |
   
 **データ API のクロスオリジン リソース共有 (CORS) のサポート**
  
データ API はクロスオリジン リソース共有 (CORS) をサポートしています。 CORS は、あるドメインで実行されている Web アプリケーションが別のドメインのリソースにアクセスできる HTTP 機能です。 Web ブラウザーは [、Same-Origin Policy の同](https://www.w3.org/Security/wiki/Same_Origin_Policy) 一発生元ポリシーと呼ばれるセキュリティ制限を実装します。このポリシーにより、Web ページが別のドメイン内の API を呼び出すのを防止できます。 CORS は、1 つのドメイン (元のドメイン) が別のドメインの API を呼び出すのを許可する安全な方法を提供します。 [CORS の詳細については、CORS](https://www.w3.org/TR/cors/)の仕様を参照してください。
  
 **データ API に対する CORS の有効化**
  
 以下は、corsTrustedOrigin アプリケーション設定に一覧表示されている 2 つのドメインweb.configデータ API アプリケーションの抜粋です。 これらのサーバーから読み込まれたスクリプトによって行われたすべての要求は、データ API によって信頼されます。
  
正確なプロトコル、ホスト名、およびポート (ポートがある場合) を含める必要があります。 末尾にスラッシュ (/) を入れ込む必要があります。 コンマで区切って、複数のエントリを指定できます。
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


