---
title: リポジトリ API 呼び出し品質ダッシュ ボード (救難) ビジネス サーバーの Skype での
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: '概要: は、通話品質のダッシュ ボードは、リポジトリ API について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: cc3e7709255ae8fce2821b6555b9bc230658565a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915270"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="4a470-104">リポジトリ API 呼び出し品質ダッシュ ボード (救難) ビジネス サーバーの Skype での</span><span class="sxs-lookup"><span data-stu-id="4a470-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="4a470-105">**の概要:** 通話品質のダッシュ ボードには、リポジトリ API について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a470-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="4a470-106">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="4a470-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4a470-107">リポジトリ API は、ビジネスのサーバーの Skype の品質のダッシュ ボードを呼び出すためのプログラムによるアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4a470-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="4a470-108">リポジトリ API の呼び出し品質のダッシュ ボードの</span><span class="sxs-lookup"><span data-stu-id="4a470-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="4a470-109">リポジトリ API には、リポジトリ データベースへのデータ アクセス インターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4a470-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="4a470-110">リポジトリは、ユーザーをグループ化できます、ユーザーに意味のある方法でするようにツリーやグラフ構造で整理することの内容を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a470-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="4a470-111">リポジトリは、2 つの一般的な種類のユーザーをサポートしています: システムのユーザーは、リポジトリを表す組み込みのユーザーは、リポジトリの認証されたユーザーを表す正規のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="4a470-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="4a470-112">リポジトリ API は、次の 3 つの全般的なサービスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="4a470-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="4a470-113">[救難のユーザー サービス](user-service.md)のユーザーにアクセスするためです。</span><span class="sxs-lookup"><span data-stu-id="4a470-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="4a470-114">[品目サービスの呼び出し品質ダッシュ ボード (救難)](item-service.md) - アイテムおよびアイテムに格納されている内容にアクセスするため。</span><span class="sxs-lookup"><span data-stu-id="4a470-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="4a470-115">[ユーザー設定のサービスの呼び出し品質ダッシュ ボード (救難)](user-settings-service.md) - ユーザーの設定にアクセスするためです。</span><span class="sxs-lookup"><span data-stu-id="4a470-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="4a470-116">通話品質のダッシュ ボードは、次の情報を管理するのにリポジトリ API を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a470-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="4a470-117">**ユーザー**のリポジトリにアクセスできるユーザーの表現です。</span><span class="sxs-lookup"><span data-stu-id="4a470-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="4a470-118">**レポート**- には、リポジトリのアイテムにコンテンツとして保存されているクエリの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a470-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="4a470-119">**クエリ**のリポジトリ アイテムのコンテンツとして格納されているデータの API からデータを取得するために使用します。</span><span class="sxs-lookup"><span data-stu-id="4a470-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="4a470-120">**ユーザー設定**- では、ユーザーの省略可能なアプリケーションの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a470-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="4a470-121">**クロスの原点のリソース共有 (CORS) リポジトリ API のサポート**</span><span class="sxs-lookup"><span data-stu-id="4a470-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="4a470-122">リポジトリ API には、クロス元リソース共有 (CORS) がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4a470-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="4a470-123">CORS は、1 つのドメインを実行している別のドメインのリソースにアクセスする web アプリケーションを有効にする HTTP 機能です。</span><span class="sxs-lookup"><span data-stu-id="4a470-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="4a470-124">Web ブラウザーは、web ページから別のドメイン内の Api を呼び出すことを防止する原点が同じポリシーを[同一生成元ポリシー](https://www.w3.org/Security/wiki/Same_Origin_Policy)と呼ばれるセキュリティの制限を実装します。</span><span class="sxs-lookup"><span data-stu-id="4a470-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="4a470-125">CORS は、セキュリティで保護された Api を呼び出して、別のドメイン内に 1 つのドメイン (元のドメイン) を許可する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="4a470-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="4a470-126">CORS の詳細については、 [CORS 仕様](https://www.w3.org/TR/cors/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a470-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="4a470-127">**リポジトリ API の CORS を有効にします。**</span><span class="sxs-lookup"><span data-stu-id="4a470-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="4a470-128">CorsTrustedOrigin アプリケーションの設定に含まれる 2 つのドメインを表示する、リポジトリ API の web.config ファイルの抜粋を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4a470-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="4a470-129">これらのサーバーから読み込まれたスクリプトによって行われたすべての要求は、リポジトリ API によって信頼されます。</span><span class="sxs-lookup"><span data-stu-id="4a470-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="4a470-130">(存在する場合)、正確なプロトコル、ホスト名、およびポートを含めることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="4a470-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="4a470-131">置かないようにする、スラッシュ文字 (/)、最後にします。</span><span class="sxs-lookup"><span data-stu-id="4a470-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="4a470-132">複数のエントリをカンマで区切って指定できます。</span><span class="sxs-lookup"><span data-stu-id="4a470-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


