---
title: Skype for Business Server の通話品質ダッシュボード (CQD) 用リポジトリ API
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: '概要: 通話品質ダッシュボードのリポジトリ API について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 283ef7544435c3954898b2d5ae9e5f5b38762f3c
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888786"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Skype for Business Server の通話品質ダッシュボード (CQD) 用リポジトリ API
 
**概要:** 通話品質ダッシュボードのリポジトリ API について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
リポジトリ API は、Skype for Business Server の通話品質ダッシュボードへのプログラムによるアクセスを提供します。
  
## <a name="repository-api-for-call-quality-dashboard"></a>通話品質ダッシュボードのリポジトリ API

リポジトリ API は、リポジトリデータベースへのデータアクセスインターフェイスを提供します。 リポジトリを使用すると、コンテンツをツリーまたはグラフ構造で整理し、ユーザーにとって意味のある方法でグループ化することができます。 リポジトリでサポートされているユーザーには、リポジトリを表すビルトインユーザーであるシステムユーザーと、リポジトリの権限を持つユーザーを表す通常のユーザーの2種類があります。
  
リポジトリ API は、次の3つの一般的なサービスで構成されます。 
  
- [CQD のユーザーサービス](user-service.md)-ユーザーへのアクセスに使用します。
    
- [通話品質ダッシュボード (CQD) の項目サービス](item-service.md)-項目とアイテムに保存されているコンテンツにアクセスする場合に使用します。
    
- ユーザー設定[サービス通話品質ダッシュボード (CQD)](user-settings-service.md) -ユーザー設定へのアクセスに使用します。
    
通話品質ダッシュボードは、リポジトリ API を使って次の情報を管理します。 
  
- リポジトリへのアクセス権を**持つユーザーの**表現。
    
- **レポート**-リポジトリアイテム内のコンテンツとして保存されているクエリの一覧が表示されます。
    
- **クエリ**-データ API からデータを取得するために使用されます。リポジトリアイテムのコンテンツとして保存されます。
    
- **ユーザー設定**-ユーザーのオプションのアプリケーション動作を記述します。
    
  **リポジトリ API のクロスオリジンリソース共有 (CORS) のサポート**
  
リポジトリ API は、クロスオリジンリソース共有 (CORS) をサポートしています。 CORS は、あるドメインで実行されている web アプリケーションが別のドメインのリソースにアクセスできるようにするための HTTP 機能です。 Web ブラウザーでは、web ページが別のドメインの Api を呼び出すことを防ぐ、同じ元のポリシーと同じ元の[ポリシー](https://www.w3.org/Security/wiki/Same_Origin_Policy)と呼ばれるセキュリティ制限が実装されています。 CORS は、1つのドメイン (元のドメイン) が別のドメインの Api を呼び出すことを許可する安全な方法を提供します。 CORS の詳細については、「 [cors の仕様](https://www.w3.org/TR/cors/)」を参照してください。
  
 **リポジトリ API の CORS を有効にする**
  
 次に示すのは、corsTrustedOrigin アプリケーションの設定で一覧表示されている2つのドメインを示すリポジトリ API の web.config の抜粋です。 これらのサーバーから読み込まれたスクリプトによって行われたすべての要求は、リポジトリ API によって信頼されます。
  
正確なプロトコル、ホスト名、ポート (存在する場合) を必ず含めてください。 末尾にスラッシュ文字 (/) を入力しないでください。 複数のエントリを指定するには、コンマで区切ります。
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


