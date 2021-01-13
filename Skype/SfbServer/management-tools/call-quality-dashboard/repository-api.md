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
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="5cd60-104">Skype for Business Server の通話品質ダッシュボード (CQD) 用リポジトリ API</span><span class="sxs-lookup"><span data-stu-id="5cd60-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="5cd60-105">**概要:** 通話品質ダッシュボードのリポジトリ API について説明します。</span><span class="sxs-lookup"><span data-stu-id="5cd60-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="5cd60-106">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="5cd60-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="5cd60-107">リポジトリ API は、Skype for Business Server の通話品質ダッシュボードへのプログラムによるアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5cd60-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="5cd60-108">通話品質ダッシュボード用リポジトリ API</span><span class="sxs-lookup"><span data-stu-id="5cd60-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="5cd60-109">リポジトリ API は、リポジトリ データベースへのデータ アクセス インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5cd60-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="5cd60-110">リポジトリを使用すると、ユーザーがユーザーに意味のある方法でコンテンツをグループ化できるよう、コンテンツをツリー構造またはグラフ構造で整理できます。</span><span class="sxs-lookup"><span data-stu-id="5cd60-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="5cd60-111">リポジトリは、リポジトリを表す組み込みのユーザーであるシステム ユーザーと、リポジトリの承認されたユーザーを表す通常のユーザーの 2 種類の一般的なユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5cd60-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="5cd60-112">リポジトリ API は、次の 3 つの一般的なサービスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5cd60-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="5cd60-113">[CQD のユーザー サービス](user-service.md) - ユーザーにアクセスする場合。</span><span class="sxs-lookup"><span data-stu-id="5cd60-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="5cd60-114">[通話品質ダッシュボード (CQD)](item-service.md) のアイテム サービス - アイテムおよびアイテムに格納されているコンテンツにアクセスするためのサービス。</span><span class="sxs-lookup"><span data-stu-id="5cd60-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="5cd60-115">[通話品質ダッシュボード (CQD)](user-settings-service.md) のユーザー設定サービス - ユーザー設定にアクセスするためのサービス。</span><span class="sxs-lookup"><span data-stu-id="5cd60-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="5cd60-116">通話品質ダッシュボードでは、リポジトリ API を使用して次の情報を管理します。</span><span class="sxs-lookup"><span data-stu-id="5cd60-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="5cd60-117">**ユーザー** - リポジトリにアクセスできるユーザーの表現。</span><span class="sxs-lookup"><span data-stu-id="5cd60-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="5cd60-118">**レポート** - リポジトリ アイテムにコンテンツとして格納されたクエリのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5cd60-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="5cd60-119">**クエリ** - リポジトリ アイテムにコンテンツとして格納されているデータ API からデータを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5cd60-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="5cd60-120">**[ユーザー設定** ] - ユーザーのオプションのアプリケーション動作を記述します。</span><span class="sxs-lookup"><span data-stu-id="5cd60-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="5cd60-121">**リポジトリ API のクロスオリジン リソース共有 (CORS) のサポート**</span><span class="sxs-lookup"><span data-stu-id="5cd60-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="5cd60-122">リポジトリ API は、クロスオリジン リソース共有 (CORS) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="5cd60-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="5cd60-123">CORS は、あるドメインで実行されている Web アプリケーションが別のドメインのリソースにアクセスできる HTTP 機能です。</span><span class="sxs-lookup"><span data-stu-id="5cd60-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="5cd60-124">Web ブラウザーは [、Same-Origin Policy same-origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) と呼ばれるセキュリティ制限を実装します。このポリシーにより、Web ページが別のドメイン内の API を呼び出すのを防止できます。</span><span class="sxs-lookup"><span data-stu-id="5cd60-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="5cd60-125">CORS は、1 つのドメイン (オリジン ドメイン) が別のドメインの API を呼び出すのを許可する安全な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="5cd60-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="5cd60-126">[CORS の詳細については、CORS](https://www.w3.org/TR/cors/)の仕様を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cd60-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="5cd60-127">**リポジトリ API に対する CORS の有効化**</span><span class="sxs-lookup"><span data-stu-id="5cd60-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="5cd60-128">次に示すのは、Repository API アプリケーションの抜粋web.config、corsTrustedOrigin アプリケーション設定に一覧表示されている 2 つのドメインを示しています。</span><span class="sxs-lookup"><span data-stu-id="5cd60-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="5cd60-129">これらのサーバーから読み込まれたスクリプトによって行われたすべての要求は、リポジトリ API によって信頼されます。</span><span class="sxs-lookup"><span data-stu-id="5cd60-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="5cd60-130">正確なプロトコル、ホスト名、およびポート (ポートがある場合) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cd60-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="5cd60-131">末尾にスラッシュ (/) を入れ込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cd60-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="5cd60-132">コンマで区切って、複数のエントリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5cd60-132">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


