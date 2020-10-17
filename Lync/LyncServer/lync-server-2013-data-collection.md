---
title: 'Lync Server 2013: データ収集'
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
ms.openlocfilehash: 01e6c75a4a557ff44d626f006210bec3a3c38472
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516574"
---
# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="5d16b-102">Lync Server 2013 のデータ収集</span><span class="sxs-lookup"><span data-stu-id="5d16b-102">Data collection in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d16b-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="5d16b-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="5d16b-104">Microsoft Lync Server 2013 communications software では、既存の IP アドレスとエッジサーバーの完全修飾ドメイン名 (Fqdn) を文書化することなく、Microsoft Lync Server 2013、計画ツールを実行できますが、構成エラーが発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="5d16b-104">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="5d16b-105">たとえば、長期間に共存が必要な場合は、Lync Server 2013 エッジ展開の既存のエッジ展開から Fqdn を再利用することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="5d16b-105">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="5d16b-106">既存の IP アドレスと Fqdn を、スプレッドシート、テーブル、またはその他のビジュアルフォームに書き込まれるようにすることで、インストール時のセットアップの問題を防止するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5d16b-106">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5d16b-107">以前のバージョンの計画ツールを使用していた場合は、トポロジを作成するためにツールを使用し、トポロジビルダーで使用するトポロジドキュメントをエクスポートしてトポロジを公開している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d16b-107">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="5d16b-108">トポロジをエクスポートする機能は、計画ツールから削除されました。</span><span class="sxs-lookup"><span data-stu-id="5d16b-108">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="5d16b-109">以前のバージョンの計画ツールを使用して Lync Server 2013 のトポロジドキュメントを作成することはお勧めしません。予期しない結果が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="5d16b-109">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="5d16b-110">そのため、推奨される方法は、エッジトポロジに対応する次のデータ収集テンプレートを使用して、計画ツールに入力する必要のあるさまざまな FQDN と IP アドレスを収集することです。</span><span class="sxs-lookup"><span data-stu-id="5d16b-110">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="5d16b-111">現在の構成と提案されている構成を記録して、運用環境の適切なコンテキストに値を入力できます。</span><span class="sxs-lookup"><span data-stu-id="5d16b-111">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="5d16b-112">また、簡単な URL、ファイル共有、負荷分散などの新機能および共存をどのように構成するかを検討できます。</span><span class="sxs-lookup"><span data-stu-id="5d16b-112">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="5d16b-113">Microsoft Lync Server 2013 を正常に展開するには、個々のコンポーネントに対する相互作用とその依存について理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d16b-113">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="5d16b-114">既存のネットワークおよびサーバーインフラストラクチャからデータを収集し、これらのセクションの計画ガイダンスを適用することで、Lync Server 2013 エッジサーバーコンポーネントをインフラストラクチャに統合することができます。</span><span class="sxs-lookup"><span data-stu-id="5d16b-114">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="5d16b-115">[「Lync Server 2013 でのトポロジの選択](lync-server-2013-choosing-a-topology.md)」で導入された3つの主要なアーキテクチャには、合計5つの展開シナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="5d16b-115">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="5d16b-116">これらのシナリオの1つは、データコレクションの開始点となります。</span><span class="sxs-lookup"><span data-stu-id="5d16b-116">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="5d16b-117">IP アドレス、サーバー名、およびドメイン名は、完全な計画ソリューションに必要な情報を詳述した、一致する証明書、ファイアウォール、および DNS の図と一致する例です。</span><span class="sxs-lookup"><span data-stu-id="5d16b-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="5d16b-118">必要な証明書、DNS、およびファイアウォールの値を図に記入することは、特に、展開を計画しているチーム以外のチームによって認証機関、ファイアウォール構成、DNS が管理されるチーム間通信では重要です。</span><span class="sxs-lookup"><span data-stu-id="5d16b-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="5d16b-119">これらの図は、チーム間のグループ作業のためにこれらの要件を伝えるために使用できる必要なコンポーネントについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5d16b-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="5d16b-120">示されているダイアグラムには、意図的に汎用性を持たせていますが、ネットワーク、ファイアウォール、証明書の作成と管理、サーバーの展開、およびサーバーの管理が異なるグループによって処理される複数チームにわたるシナリオでの、要件の伝達に必要なすべての関連データの収集が可能です。</span><span class="sxs-lookup"><span data-stu-id="5d16b-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="5d16b-121">Lync Server の展開時には、ネットワーク、ファイアウォール、ポート、プロトコル、証明書、およびサーバーの構成について必要な詳細情報が非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5d16b-121">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="5d16b-122">**エッジサーバーとエッジプール**</span><span class="sxs-lookup"><span data-stu-id="5d16b-122">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="5d16b-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="5d16b-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="5d16b-124">**リバース プロキシ**</span><span class="sxs-lookup"><span data-stu-id="5d16b-124">**Reverse Proxy**</span></span>

<span data-ttu-id="5d16b-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="5d16b-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="5d16b-126">**ディレクターまたはディレクター プール**</span><span class="sxs-lookup"><span data-stu-id="5d16b-126">**Director or Director pool**</span></span>

<span data-ttu-id="5d16b-127">![56ba29ffe130947 d5debf5ce353 72169ebtx 7](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ffe130947 d5debf5ce353 72169ebtx 7")</span><span class="sxs-lookup"><span data-stu-id="5d16b-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

