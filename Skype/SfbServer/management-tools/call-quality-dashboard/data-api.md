---
title: Skype for Business Server の通話品質ダッシュボード (CQD) のデータ API
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: '概要: 通話品質ダッシュボードのデータ API について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 016cc1be9f5cd5506f8ee7d8ddbe2765e0015ffd
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "36571921"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="c6f35-104">Skype for Business Server の通話品質ダッシュボード (CQD) のデータ API</span><span class="sxs-lookup"><span data-stu-id="c6f35-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="c6f35-105">**概要:** 通話品質ダッシュボードのデータ API について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6f35-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="c6f35-106">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="c6f35-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c6f35-107">データ API は、Skype for Business Server の通話品質ダッシュボードへのプログラムによるアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c6f35-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="c6f35-108">通話品質ダッシュボードのデータ API</span><span class="sxs-lookup"><span data-stu-id="c6f35-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="c6f35-109">データ API には、QoE キューブへのクエリインターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c6f35-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="c6f35-110">データ API は、指定したサイズとフィルターに基づいて、集計された QoE メトリックを提供する多次元データベースを操作するための REST API です。</span><span class="sxs-lookup"><span data-stu-id="c6f35-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="c6f35-111">REST 操作は、次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="c6f35-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="c6f35-112">**操作**</span><span class="sxs-lookup"><span data-stu-id="c6f35-112">**Operation**</span></span>|<span data-ttu-id="c6f35-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="c6f35-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c6f35-114">キューブの取得</span><span class="sxs-lookup"><span data-stu-id="c6f35-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="c6f35-115">使用可能な寸法と測定値の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c6f35-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="c6f35-116">ディメンションのメンバーの取得</span><span class="sxs-lookup"><span data-stu-id="c6f35-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="c6f35-117">ディメンションメンバーの取得操作特定のディメンションのメンバーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="c6f35-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="c6f35-118">また、メンバーリストをフィルター処理して、送金料金を削減することができます。</span><span class="sxs-lookup"><span data-stu-id="c6f35-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="c6f35-119">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="c6f35-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="c6f35-120">クエリの実行操作指定したサイズ、測定値、フィルターに基づいてキューブに対してクエリを実行し、データを戻すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="c6f35-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="c6f35-121">キャッシュのクリア</span><span class="sxs-lookup"><span data-stu-id="c6f35-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="c6f35-122">[キャッシュの消去] 操作は、クエリとデータのためにサーバー上のキャッシュを削除します。</span><span class="sxs-lookup"><span data-stu-id="c6f35-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="c6f35-123">これによりキャッシュがリセットされ、新しい要求があった場合は QoE キューブから最新のデータが取得されます。</span><span class="sxs-lookup"><span data-stu-id="c6f35-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="c6f35-124">統合ログの取得</span><span class="sxs-lookup"><span data-stu-id="c6f35-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="c6f35-125">統合ログの取得操作 QoE キューブ処理のアクティビティを説明するログエントリの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="c6f35-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="c6f35-126">直近の統合データの取得</span><span class="sxs-lookup"><span data-stu-id="c6f35-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="c6f35-127">キューブから最新の統合データを取得します。</span><span class="sxs-lookup"><span data-stu-id="c6f35-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="c6f35-128">**データ API のクロスオリジンリソース共有 (CORS) のサポート**</span><span class="sxs-lookup"><span data-stu-id="c6f35-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="c6f35-129">データ API は、クロスオリジンリソース共有 (CORS) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c6f35-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="c6f35-130">CORS は、あるドメインで実行されている web アプリケーションが別のドメインのリソースにアクセスできるようにするための HTTP 機能です。</span><span class="sxs-lookup"><span data-stu-id="c6f35-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="c6f35-131">Web ブラウザーでは、web ページが別のドメインの Api を呼び出すことを防ぐ、同じ元のポリシーと同じ元の[ポリシー](https://www.w3.org/Security/wiki/Same_Origin_Policy)と呼ばれるセキュリティ制限が実装されています。</span><span class="sxs-lookup"><span data-stu-id="c6f35-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="c6f35-132">CORS は、1つのドメイン (元のドメイン) が別のドメインの Api を呼び出すことを許可する安全な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6f35-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="c6f35-133">CORS の詳細については、「 [cors の仕様](https://www.w3.org/TR/cors/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6f35-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="c6f35-134">**データ API に対して CORS を有効にする**</span><span class="sxs-lookup"><span data-stu-id="c6f35-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="c6f35-135">次に示すのは、corsTrustedOrigin アプリケーションの設定で一覧表示されている2つのドメインを示すデータ API web.config の抜粋です。</span><span class="sxs-lookup"><span data-stu-id="c6f35-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="c6f35-136">これらのサーバーから読み込まれたスクリプトによって行われたすべての要求は、データ API によって信頼されます。</span><span class="sxs-lookup"><span data-stu-id="c6f35-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="c6f35-137">正確なプロトコル、ホスト名、ポート (存在する場合) を必ず含めてください。</span><span class="sxs-lookup"><span data-stu-id="c6f35-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="c6f35-138">末尾にスラッシュ文字 (/) を入力しないでください。</span><span class="sxs-lookup"><span data-stu-id="c6f35-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="c6f35-139">複数のエントリを指定するには、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="c6f35-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


