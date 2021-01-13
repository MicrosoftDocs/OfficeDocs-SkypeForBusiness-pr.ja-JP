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
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="7693c-104">Skype for Business Server の通話品質ダッシュボード (CQD) のデータ API</span><span class="sxs-lookup"><span data-stu-id="7693c-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="7693c-105">**概要:** 通話品質ダッシュボードのデータ API について説明します。</span><span class="sxs-lookup"><span data-stu-id="7693c-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="7693c-106">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="7693c-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="7693c-107">データ API は、Skype for Business Server の通話品質ダッシュボードへのプログラムによるアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7693c-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="7693c-108">通話品質ダッシュボードのデータ API</span><span class="sxs-lookup"><span data-stu-id="7693c-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="7693c-109">データ API は、QoE キューブへのクエリ インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7693c-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="7693c-110">データ API は、指定されたディメンションとフィルターに基づいて集計 QoE 指標を提供する、多次元データベースを操作する REST API です。</span><span class="sxs-lookup"><span data-stu-id="7693c-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="7693c-111">REST 操作を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="7693c-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="7693c-112">**操作**</span><span class="sxs-lookup"><span data-stu-id="7693c-112">**Operation**</span></span>|<span data-ttu-id="7693c-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="7693c-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7693c-114">キューブの取得</span><span class="sxs-lookup"><span data-stu-id="7693c-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="7693c-115">使用可能なディメンションと測定値の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="7693c-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="7693c-116">ディメンションのメンバーの取得</span><span class="sxs-lookup"><span data-stu-id="7693c-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="7693c-117">ディメンション メンバーの取得操作は、特定のディメンションのメンバーのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="7693c-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="7693c-118">また、メンバー リストをフィルター処理してサブセットを取得し、電信送金コストを削減する機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="7693c-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="7693c-119">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="7693c-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="7693c-120">クエリの実行操作では、指定したディメンション、測定値、およびフィルターに基づいてキューブに対してクエリを実行し、データを返す機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7693c-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="7693c-121">キャッシュのクリア</span><span class="sxs-lookup"><span data-stu-id="7693c-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="7693c-122">キャッシュをクリア操作すると、クエリとデータのサーバー上のキャッシュが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7693c-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="7693c-123">これによりキャッシュがリセットされ、後で新しい要求の QoE キューブから新しいデータが取得されます。</span><span class="sxs-lookup"><span data-stu-id="7693c-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="7693c-124">統合ログの取得</span><span class="sxs-lookup"><span data-stu-id="7693c-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="7693c-125">統合ログの取得操作は、QoE キューブ処理のアクティビティを記述するログ エントリのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="7693c-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="7693c-126">直近の統合データの取得</span><span class="sxs-lookup"><span data-stu-id="7693c-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="7693c-127">キューブから最後の統合データを取得します。</span><span class="sxs-lookup"><span data-stu-id="7693c-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="7693c-128">**データ API のクロスオリジン リソース共有 (CORS) のサポート**</span><span class="sxs-lookup"><span data-stu-id="7693c-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="7693c-129">データ API はクロスオリジン リソース共有 (CORS) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7693c-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="7693c-130">CORS は、あるドメインで実行されている Web アプリケーションが別のドメインのリソースにアクセスできる HTTP 機能です。</span><span class="sxs-lookup"><span data-stu-id="7693c-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="7693c-131">Web ブラウザーは [、Same-Origin Policy の同](https://www.w3.org/Security/wiki/Same_Origin_Policy) 一発生元ポリシーと呼ばれるセキュリティ制限を実装します。このポリシーにより、Web ページが別のドメイン内の API を呼び出すのを防止できます。</span><span class="sxs-lookup"><span data-stu-id="7693c-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="7693c-132">CORS は、1 つのドメイン (元のドメイン) が別のドメインの API を呼び出すのを許可する安全な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="7693c-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="7693c-133">[CORS の詳細については、CORS](https://www.w3.org/TR/cors/)の仕様を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7693c-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="7693c-134">**データ API に対する CORS の有効化**</span><span class="sxs-lookup"><span data-stu-id="7693c-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="7693c-135">以下は、corsTrustedOrigin アプリケーション設定に一覧表示されている 2 つのドメインweb.configデータ API アプリケーションの抜粋です。</span><span class="sxs-lookup"><span data-stu-id="7693c-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="7693c-136">これらのサーバーから読み込まれたスクリプトによって行われたすべての要求は、データ API によって信頼されます。</span><span class="sxs-lookup"><span data-stu-id="7693c-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="7693c-137">正確なプロトコル、ホスト名、およびポート (ポートがある場合) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7693c-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="7693c-138">末尾にスラッシュ (/) を入れ込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="7693c-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="7693c-139">コンマで区切って、複数のエントリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7693c-139">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


