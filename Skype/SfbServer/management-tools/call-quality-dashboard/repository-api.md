---
title: リポジトリ API 呼び出し品質ダッシュ ボード (救難) ビジネス サーバーの Skype での
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: '概要: は、通話品質のダッシュ ボードは、リポジトリ API について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 9181cd1454311bb5446bb18f51af56914387e7c3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217657"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>リポジトリ API 呼び出し品質ダッシュ ボード (救難) ビジネス サーバーの Skype での
 
**の概要:** 通話品質のダッシュ ボードには、リポジトリ API について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。
  
リポジトリ API は、ビジネスのサーバーの Skype の品質のダッシュ ボードを呼び出すためのプログラムによるアクセスを提供します。
  
## <a name="repository-api-for-call-quality-dashboard"></a>リポジトリ API の呼び出し品質のダッシュ ボードの

リポジトリ API には、リポジトリ データベースへのデータ アクセス インターフェイスが用意されています。 リポジトリは、ユーザーをグループ化できます、ユーザーに意味のある方法でするようにツリーやグラフ構造で整理することの内容を使用できます。 リポジトリは、2 つの一般的な種類のユーザーをサポートしています: システムのユーザーは、リポジトリを表す組み込みのユーザーは、リポジトリの認証されたユーザーを表す正規のユーザーです。
  
リポジトリ API は、次の 3 つの全般的なサービスで構成されます。 
  
- [救難のユーザー サービス](user-service.md)のユーザーにアクセスするためです。
    
- [品目サービスの呼び出し品質ダッシュ ボード (救難)](item-service.md) - アイテムおよびアイテムに格納されている内容にアクセスするため。
    
- [ユーザー設定のサービスの呼び出し品質ダッシュ ボード (救難)](user-settings-service.md) - ユーザーの設定にアクセスするためです。
    
通話品質のダッシュ ボードは、次の情報を管理するのにリポジトリ API を使用します。 
  
- **ユーザー**のリポジトリにアクセスできるユーザーの表現です。
    
- **レポート**- には、リポジトリのアイテムにコンテンツとして保存されているクエリの一覧が含まれています。
    
- **クエリ**のリポジトリ アイテムのコンテンツとして格納されているデータの API からデータを取得するために使用します。
    
- **ユーザー設定**- では、ユーザーの省略可能なアプリケーションの動作について説明します。
    
  **クロスの原点のリソース共有 (CORS) リポジトリ API のサポート**
  
リポジトリ API には、クロス元リソース共有 (CORS) がサポートされています。 CORS は、1 つのドメインを実行している別のドメインのリソースにアクセスする web アプリケーションを有効にする HTTP 機能です。 Web ブラウザーは、web ページから別のドメイン内の Api を呼び出すことを防止する原点が同じポリシーを[同一生成元ポリシー](https://www.w3.org/Security/wiki/Same_Origin_Policy)と呼ばれるセキュリティの制限を実装します。 CORS は、セキュリティで保護された Api を呼び出して、別のドメイン内に 1 つのドメイン (元のドメイン) を許可する手段を提供します。 CORS の詳細については、 [CORS 仕様](https://www.w3.org/TR/cors/)を参照してください。
  
 **リポジトリ API の CORS を有効にします。**
  
 CorsTrustedOrigin アプリケーションの設定に含まれる 2 つのドメインを表示する、リポジトリ API の web.config ファイルの抜粋を次に示します。 これらのサーバーから読み込まれたスクリプトによって行われたすべての要求は、リポジトリ API によって信頼されます。
  
(存在する場合)、正確なプロトコル、ホスト名、およびポートを含めることを忘れないでください。 置かないようにする、スラッシュ文字 (/)、最後にします。 複数のエントリをカンマで区切って指定できます。
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


