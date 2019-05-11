---
title: 通話品質のダッシュ ボード (救難) ビジネス サーバーの Skype でのデータ API
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: '概要: は、通話品質のダッシュ ボードの期間の API について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: e1143752031406885a77e5afab975463d5732220
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930701"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="ea4e4-104">通話品質のダッシュ ボード (救難) ビジネス サーバーの Skype でのデータ API</span><span class="sxs-lookup"><span data-stu-id="ea4e4-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="ea4e4-105">**の概要:** 通話品質のダッシュ ボードには、期間の API について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-105">**Summary:** Learn about the Rata API for Call Quality Dashboard.</span></span> <span data-ttu-id="ea4e4-106">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="ea4e4-107">データ API は、ビジネスのサーバーの Skype の品質のダッシュ ボードを呼び出すためのプログラムによるアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="ea4e4-108">通話品質のダッシュ ボードのデータ API</span><span class="sxs-lookup"><span data-stu-id="ea4e4-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="ea4e4-109">データ API では、QoE のキューブにクエリ インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="ea4e4-110">データ API では、REST API を指定した寸法とフィルターに基づいて集計の QoE 評価尺度を提供する多次元データベースを操作するためです。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="ea4e4-111">次の表には、他の操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="ea4e4-112">**操作**</span><span class="sxs-lookup"><span data-stu-id="ea4e4-112">**Operation**</span></span>|<span data-ttu-id="ea4e4-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="ea4e4-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ea4e4-114">キューブの取得</span><span class="sxs-lookup"><span data-stu-id="ea4e4-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="ea4e4-115">使用可能なディメンションと測定値の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="ea4e4-116">ディメンションのメンバーの取得</span><span class="sxs-lookup"><span data-stu-id="ea4e4-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="ea4e4-117">ディメンション メンバーの取得操作は、特定のディメンションのメンバーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="ea4e4-118">また、メンバーの一覧をフィルター処理し、ワイヤ転送コストを削減するのには、サブセットを取得する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="ea4e4-119">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="ea4e4-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="ea4e4-120">操作には、指定した寸法、測定、およびフィルターに基づいて、キューブに対してクエリを実行する機能が用意されています。 クエリを実行し、データを返します。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="ea4e4-121">キャッシュのクリア</span><span class="sxs-lookup"><span data-stu-id="ea4e4-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="ea4e4-122">キャッシュのクリアの操作は、クエリとデータのサーバー上のキャッシュを削除します。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="ea4e4-123">キャッシュがリセットし、紹介最新データ QoE キューブから後で新しい要求をします。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="ea4e4-124">統合ログの取得</span><span class="sxs-lookup"><span data-stu-id="ea4e4-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="ea4e4-125">操作が返されます QoE のキューブに含まれるアクティビティを説明するログ エントリの一覧を処理する統合ログを取得します。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="ea4e4-126">直近の統合データの取得</span><span class="sxs-lookup"><span data-stu-id="ea4e4-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="ea4e4-127">最後の統合データをキューブから取得します。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="ea4e4-128">**クロス元のリソース共有先のデータ API のサポートを (CORS)**</span><span class="sxs-lookup"><span data-stu-id="ea4e4-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="ea4e4-129">データ API には、クロス元リソース共有 (CORS) がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="ea4e4-130">CORS は、1 つのドメインを実行している別のドメインのリソースにアクセスする web アプリケーションを有効にする HTTP 機能です。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="ea4e4-131">Web ブラウザーは、web ページから別のドメイン内の Api を呼び出すことを防止する原点が同じポリシーを[同一生成元ポリシー](https://www.w3.org/Security/wiki/Same_Origin_Policy)と呼ばれるセキュリティの制限を実装します。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="ea4e4-132">CORS は、セキュリティで保護された Api を呼び出して、別のドメイン内に 1 つのドメイン (元のドメイン) を許可する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="ea4e4-133">CORS の詳細については、 [CORS 仕様](https://www.w3.org/TR/cors/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="ea4e4-134">**データ API の CORS を有効にします。**</span><span class="sxs-lookup"><span data-stu-id="ea4e4-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="ea4e4-135">CorsTrustedOrigin アプリケーションの設定に含まれる 2 つのドメインを表示、データの API の web.config ファイルの抜粋を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="ea4e4-136">データ API では、これらのサーバーから読み込まれたスクリプトによって行われたすべての要求が信頼されています。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="ea4e4-137">(存在する場合)、正確なプロトコル、ホスト名、およびポートを含めることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="ea4e4-138">置かないようにする、スラッシュ文字 (/)、最後にします。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="ea4e4-139">複数のエントリをカンマで区切って指定できます。</span><span class="sxs-lookup"><span data-stu-id="ea4e4-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


