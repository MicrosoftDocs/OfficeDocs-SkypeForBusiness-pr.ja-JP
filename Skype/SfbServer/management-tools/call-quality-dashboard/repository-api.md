---
title: Skype for Business Server の通話品質ダッシュボード (CQD) 用リポジトリ API
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: '概要: 通話品質ダッシュボードのリポジトリ API について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 982ec0932f0a57958e1929a6ae2413ada0b5c9fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803127"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Skype for Business Server の通話品質ダッシュボード (CQD) 用リポジトリ API
 
**概要:** 通話品質ダッシュボードのリポジトリ API について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
リポジトリ API は、Skype for Business Server の通話品質ダッシュボードへのプログラムによるアクセスを提供します。
  
## <a name="repository-api-for-call-quality-dashboard"></a>通話品質ダッシュボード用リポジトリ API

リポジトリ API は、リポジトリ データベースへのデータ アクセス インターフェイスを提供します。 リポジトリを使用すると、ユーザーがユーザーに意味のある方法でコンテンツをグループ化できるよう、コンテンツをツリー構造またはグラフ構造で整理できます。 リポジトリは、リポジトリを表す組み込みのユーザーであるシステム ユーザーと、リポジトリの承認されたユーザーを表す通常のユーザーの 2 種類の一般的なユーザーをサポートします。
  
リポジトリ API は、次の 3 つの一般的なサービスで構成されます。 
  
- [CQD のユーザー サービス](user-service.md) - ユーザーにアクセスする場合。
    
- [通話品質ダッシュボード (CQD)](item-service.md) のアイテム サービス - アイテムおよびアイテムに格納されているコンテンツにアクセスするためのサービス。
    
- [通話品質ダッシュボード (CQD)](user-settings-service.md) のユーザー設定サービス - ユーザー設定にアクセスするためのサービス。
    
通話品質ダッシュボードでは、リポジトリ API を使用して次の情報を管理します。 
  
- **ユーザー** - リポジトリにアクセスできるユーザーの表現。
    
- **レポート** - リポジトリ アイテムにコンテンツとして格納されたクエリのリストが含まれます。
    
- **クエリ** - リポジトリ アイテムにコンテンツとして格納されているデータ API からデータを取得するために使用されます。
    
- **[ユーザー設定** ] - ユーザーのオプションのアプリケーション動作を記述します。
    
  **リポジトリ API のクロスオリジン リソース共有 (CORS) のサポート**
  
リポジトリ API は、クロスオリジン リソース共有 (CORS) をサポートします。 CORS は、あるドメインで実行されている Web アプリケーションが別のドメインのリソースにアクセスできる HTTP 機能です。 Web ブラウザーは [、Same-Origin Policy same-origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) と呼ばれるセキュリティ制限を実装します。このポリシーにより、Web ページが別のドメイン内の API を呼び出すのを防止できます。 CORS は、1 つのドメイン (オリジン ドメイン) が別のドメインの API を呼び出すのを許可する安全な方法を提供します。 [CORS の詳細については、CORS](https://www.w3.org/TR/cors/)の仕様を参照してください。
  
 **リポジトリ API に対する CORS の有効化**
  
 次に示すのは、Repository API アプリケーションの抜粋web.config、corsTrustedOrigin アプリケーション設定に一覧表示されている 2 つのドメインを示しています。 これらのサーバーから読み込まれたスクリプトによって行われたすべての要求は、リポジトリ API によって信頼されます。
  
正確なプロトコル、ホスト名、およびポート (ポートがある場合) を含める必要があります。 末尾にスラッシュ (/) を入れ込む必要があります。 コンマで区切って、複数のエントリを指定できます。
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


