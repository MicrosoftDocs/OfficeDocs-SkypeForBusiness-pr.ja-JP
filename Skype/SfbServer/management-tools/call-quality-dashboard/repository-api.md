---
title: リポジトリ API for Call Quality Dashboard (CQD) in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: '概要: 呼び出し品質ダッシュボードのリポジトリ API について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: c042ace733782fe7a514fec6a5d0e875ddf6b728
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618823"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>リポジトリ API for Call Quality Dashboard (CQD) in Skype for Business Server
 
**概要:** 呼び出し品質ダッシュボードのリポジトリ API について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
リポジトリ API は、通話品質ダッシュボードのプログラムによるアクセスを提供Skype for Business Server。
  
## <a name="repository-api-for-call-quality-dashboard"></a>呼び出し品質ダッシュボードのリポジトリ API

リポジトリ API は、リポジトリ データベースへのデータ アクセス インターフェイスを提供します。 リポジトリを使用すると、コンテンツをツリー構造またはグラフ構造で整理し、ユーザーがユーザーに意味のある方法でグループ化できます。 リポジトリは、リポジトリを表す組み込みのユーザーであるシステム ユーザーと、リポジトリの承認されたユーザーを表す通常のユーザーの 2 つの一般的な種類のユーザーをサポートします。
  
リポジトリ API は、次の 3 つの一般的なサービスで構成されます。 
  
- [CQD のユーザー サービス](user-service.md) - ユーザーにアクセスする場合。
    
- [通話品質ダッシュボード (CQD)](item-service.md) のアイテム サービス - アイテムとアイテムに格納されているコンテンツにアクセスします。
    
- [ユーザー 設定 サービス for Call Quality Dashboard (CQD)](user-settings-service.md) - ユーザー サービスにアクセス設定。
    
品質ダッシュボードの呼び出しでは、リポジトリ API を使用して次の情報を管理します。 
  
- **ユーザー** - リポジトリにアクセスできるユーザーの表現。
    
- **レポート** - リポジトリ アイテムにコンテンツとして格納されるクエリの一覧が含まれます。
    
- **クエリ** - リポジトリ アイテムにコンテンツとして格納されたデータ API からデータを取得するために使用されます。
    
- **[ユーザー設定** ] - ユーザーのオプションのアプリケーション動作について説明します。
    
  **リポジトリ API のクロスオリジン リソース共有 (CORS) のサポート**
  
リポジトリ API では、クロスオリジン リソース共有 (CORS) がサポートされています。 CORS は、あるドメインで実行されている Web アプリケーションが別のドメインのリソースにアクセスできる HTTP 機能です。 Web ブラウザーは、Web ページが別のドメインで API を呼び出すのを防ぐ [Same-Origin Policy same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) と呼ばれるセキュリティ制限を実装します。 CORS は、あるドメイン (オリジン ドメイン) が別のドメインで API を呼び出す安全な方法を提供します。 [CORS の詳細については、CORS](https://www.w3.org/TR/cors/)仕様を参照してください。
  
 **リポジトリ API の CORS の有効化**
  
 次に示すのは、リポジトリ API web.configの抜粋で、corsTrustedOrigin アプリケーション設定に一覧表示されている 2 つのドメインを示します。 これらのサーバーから読み込まれたスクリプトによって行われたすべての要求は、リポジトリ API によって信頼されます。
  
正確なプロトコル、ホスト名、およびポート (必要な場合) を含める必要があります。 スラッシュ文字 (/) を末尾に置かねない。 コンマで区切って複数のエントリを指定できます。
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


