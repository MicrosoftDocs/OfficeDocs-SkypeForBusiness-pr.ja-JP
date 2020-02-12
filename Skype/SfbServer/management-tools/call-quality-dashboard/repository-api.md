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
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="491de-104">Skype for Business Server の通話品質ダッシュボード (CQD) 用リポジトリ API</span><span class="sxs-lookup"><span data-stu-id="491de-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="491de-105">**概要:** 通話品質ダッシュボードのリポジトリ API について説明します。</span><span class="sxs-lookup"><span data-stu-id="491de-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="491de-106">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="491de-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="491de-107">リポジトリ API は、Skype for Business Server の通話品質ダッシュボードへのプログラムによるアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="491de-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="491de-108">通話品質ダッシュボードのリポジトリ API</span><span class="sxs-lookup"><span data-stu-id="491de-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="491de-109">リポジトリ API は、リポジトリデータベースへのデータアクセスインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="491de-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="491de-110">リポジトリを使用すると、コンテンツをツリーまたはグラフ構造で整理し、ユーザーにとって意味のある方法でグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="491de-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="491de-111">リポジトリでサポートされているユーザーには、リポジトリを表すビルトインユーザーであるシステムユーザーと、リポジトリの権限を持つユーザーを表す通常のユーザーの2種類があります。</span><span class="sxs-lookup"><span data-stu-id="491de-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="491de-112">リポジトリ API は、次の3つの一般的なサービスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="491de-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="491de-113">[CQD のユーザーサービス](user-service.md)-ユーザーへのアクセスに使用します。</span><span class="sxs-lookup"><span data-stu-id="491de-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="491de-114">[通話品質ダッシュボード (CQD) の項目サービス](item-service.md)-項目とアイテムに保存されているコンテンツにアクセスする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="491de-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="491de-115">ユーザー設定[サービス通話品質ダッシュボード (CQD)](user-settings-service.md) -ユーザー設定へのアクセスに使用します。</span><span class="sxs-lookup"><span data-stu-id="491de-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="491de-116">通話品質ダッシュボードは、リポジトリ API を使って次の情報を管理します。</span><span class="sxs-lookup"><span data-stu-id="491de-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="491de-117">リポジトリへのアクセス権を**持つユーザーの**表現。</span><span class="sxs-lookup"><span data-stu-id="491de-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="491de-118">**レポート**-リポジトリアイテム内のコンテンツとして保存されているクエリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="491de-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="491de-119">**クエリ**-データ API からデータを取得するために使用されます。リポジトリアイテムのコンテンツとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="491de-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="491de-120">**ユーザー設定**-ユーザーのオプションのアプリケーション動作を記述します。</span><span class="sxs-lookup"><span data-stu-id="491de-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="491de-121">**リポジトリ API のクロスオリジンリソース共有 (CORS) のサポート**</span><span class="sxs-lookup"><span data-stu-id="491de-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="491de-122">リポジトリ API は、クロスオリジンリソース共有 (CORS) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="491de-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="491de-123">CORS は、あるドメインで実行されている web アプリケーションが別のドメインのリソースにアクセスできるようにするための HTTP 機能です。</span><span class="sxs-lookup"><span data-stu-id="491de-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="491de-124">Web ブラウザーでは、web ページが別のドメインの Api を呼び出すことを防ぐ、同じ元のポリシーと同じ元の[ポリシー](https://www.w3.org/Security/wiki/Same_Origin_Policy)と呼ばれるセキュリティ制限が実装されています。</span><span class="sxs-lookup"><span data-stu-id="491de-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="491de-125">CORS は、1つのドメイン (元のドメイン) が別のドメインの Api を呼び出すことを許可する安全な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="491de-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="491de-126">CORS の詳細については、「 [cors の仕様](https://www.w3.org/TR/cors/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="491de-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="491de-127">**リポジトリ API の CORS を有効にする**</span><span class="sxs-lookup"><span data-stu-id="491de-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="491de-128">次に示すのは、corsTrustedOrigin アプリケーションの設定で一覧表示されている2つのドメインを示すリポジトリ API の web.config の抜粋です。</span><span class="sxs-lookup"><span data-stu-id="491de-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="491de-129">これらのサーバーから読み込まれたスクリプトによって行われたすべての要求は、リポジトリ API によって信頼されます。</span><span class="sxs-lookup"><span data-stu-id="491de-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="491de-130">正確なプロトコル、ホスト名、ポート (存在する場合) を必ず含めてください。</span><span class="sxs-lookup"><span data-stu-id="491de-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="491de-131">末尾にスラッシュ文字 (/) を入力しないでください。</span><span class="sxs-lookup"><span data-stu-id="491de-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="491de-132">複数のエントリを指定するには、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="491de-132">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


