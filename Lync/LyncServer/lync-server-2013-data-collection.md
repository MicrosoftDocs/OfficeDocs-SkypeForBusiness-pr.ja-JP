---
title: 'Lync Server 2013: データの収集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7c3d066aff26e06c003a31a58b4771d67f54f34
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="f01ad-102">Lync Server 2013 のデータの収集</span><span class="sxs-lookup"><span data-stu-id="f01ad-102">Data collection in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f01ad-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="f01ad-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="f01ad-104">Microsoft Lync Server 2013 通信ソフトウェアでは、既存および提案された IP アドレスとエッジサーバーの完全修飾ドメイン名 (Fqdn) を文書化することなく、Microsoft Lync Server 2013、計画ツールを実行できますが、これは非常に困難です。そのため、構成エラーが発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="f01ad-104">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="f01ad-105">たとえば、一定の期間共存が必要な場合は、Lync Server 2013 Edge の展開のために既存のエッジ展開から Fqdn を再利用することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="f01ad-105">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="f01ad-106">既存の IP アドレスと Fqdn をスプレッドシート、表、またはその他の視覚的な形式で書き留めておくと、インストール時のセットアップの問題を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f01ad-106">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f01ad-107">計画ツールの以前のバージョンを使用したことがある場合は、トポロジの作成にこのツールを使用し、トポロジビルダーで使用するトポロジドキュメントをエクスポートしてトポロジを公開している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f01ad-107">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="f01ad-108">トポロジのエクスポート機能が計画ツールから削除されました。</span><span class="sxs-lookup"><span data-stu-id="f01ad-108">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="f01ad-109">以前のバージョンの計画ツールを使用して、Lync Server 2013 のトポロジドキュメントを作成することはお勧めできません。予期しない結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f01ad-109">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="f01ad-110">したがって、推奨される方法は、次のデータコレクションテンプレートを使用することです。これは、Edge トポロジに対応しており、計画ツールに入力する必要があるさまざまな FQDN と IP アドレスを収集します。</span><span class="sxs-lookup"><span data-stu-id="f01ad-110">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="f01ad-111">現在の構成と提案された構成を文書化することで、実稼働環境の適切なコンテキストに値を配置することができます。</span><span class="sxs-lookup"><span data-stu-id="f01ad-111">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="f01ad-112">また、単純な Url、ファイル共有、負荷分散などの共存と機能をどのように構成するかを考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="f01ad-112">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="f01ad-113">Microsoft Lync Server 2013 を正常に展開するには、個々のコンポーネントに対する操作と依存関係を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f01ad-113">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="f01ad-114">既存のネットワークとサーバーインフラストラクチャからデータを収集し、計画ガイダンスを適用することで、Lync Server 2013 エッジサーバーコンポーネントをインフラストラクチャに統合することができます。</span><span class="sxs-lookup"><span data-stu-id="f01ad-114">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="f01ad-115">「 [Lync Server 2013 でのトポロジの選択](lync-server-2013-choosing-a-topology.md)」で説明した3つの主要なアーキテクチャには、合計5つの展開シナリオが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f01ad-115">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="f01ad-116">これらのシナリオのいずれかが、データ収集の出発点になります。</span><span class="sxs-lookup"><span data-stu-id="f01ad-116">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="f01ad-117">IP アドレス、サーバー名、ドメイン名は、完全な計画ソリューションに必要な情報について説明する、一致する証明書、ファイアウォール、DNS ダイアグラムと一致する例です。</span><span class="sxs-lookup"><span data-stu-id="f01ad-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="f01ad-118">必要な証明書、DNS、ファイアウォールの値の図と入力は、チーム間通信では特に重要であり、証明機関、ファイアウォール構成、DNS はチーム以外のチームによって管理されます。展開を計画します。</span><span class="sxs-lookup"><span data-stu-id="f01ad-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="f01ad-119">これらの図は、チーム間での共同作業のためにこれらの要件を伝えるために使用できる必須コンポーネントについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="f01ad-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="f01ad-120">提供されているダイアグラムは意図的に標準であり、ネットワーク、ファイアウォール、証明書の作成と管理、サーバーなど、チーム間での要件の通信に必要なすべての関連データを収集することを許可します。展開とサーバー管理は、さまざまなグループで処理されます。</span><span class="sxs-lookup"><span data-stu-id="f01ad-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="f01ad-121">Lync Server の展開が進行中の場合は、ネットワーク、ファイアウォール、ポート、プロトコル、証明書、サーバーの構成に必要な詳細情報が非常に重要になります。</span><span class="sxs-lookup"><span data-stu-id="f01ad-121">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="f01ad-122">**エッジサーバーとエッジプール**</span><span class="sxs-lookup"><span data-stu-id="f01ad-122">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="f01ad-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="f01ad-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="f01ad-124">**リバースプロキシ**</span><span class="sxs-lookup"><span data-stu-id="f01ad-124">**Reverse Proxy**</span></span>

<span data-ttu-id="f01ad-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="f01ad-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="f01ad-126">**ディレクターまたはディレクタープール**</span><span class="sxs-lookup"><span data-stu-id="f01ad-126">**Director or Director pool**</span></span>

<span data-ttu-id="f01ad-127">![56 ba29ff001 130916d5d56 72169e・デ・・・・・・・・・・ライド7](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56 ba29ff001 130916d5d56 72169e・デ・・・・・・・・・・ライド7")</span><span class="sxs-lookup"><span data-stu-id="f01ad-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

