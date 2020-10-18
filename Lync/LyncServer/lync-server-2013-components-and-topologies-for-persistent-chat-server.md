---
title: 'Lync Server 2013: 常設チャットサーバーのコンポーネントとトポロジ'
description: 'Lync Server 2013: 常設チャットサーバーのコンポーネントとトポロジ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937b3d6f2716d9471e61cffd651847f6de9d83f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576813"
---
# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="d2b5b-103">Lync Server 2013 の常設チャットサーバーのコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="d2b5b-103">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2b5b-104">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d2b5b-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d2b5b-105">常設チャットサーバーは、単一サーバー構成と複数サーバー構成の両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-105">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="d2b5b-106">常設チャットサーバーは、Lync Server 2013 Standard Edition サーバー上でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-106">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="d2b5b-107">これらの構成は、次の常設チャットサーバーのコンポーネントとトポロジで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-107">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="d2b5b-108">常設チャットサーバーのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="d2b5b-108">Persistent Chat Server Components</span></span>

<span data-ttu-id="d2b5b-109">常設チャットサーバーの最新バージョンをインストールするには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-109">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="d2b5b-110">常設チャットサーバーを実行し、次のサービスを提供する1台以上のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-110">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="d2b5b-111">Persistent Chat Service</span><span class="sxs-lookup"><span data-stu-id="d2b5b-111">Persistent Chat service</span></span>
    
      - <span data-ttu-id="d2b5b-112">コンプライアンスが有効な場合にオンになるコンプライアンス サービス</span><span class="sxs-lookup"><span data-stu-id="d2b5b-112">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d2b5b-113">Lync Server 2013 で、ファイルのアップロード/ダウンロード用の常設チャット Web サービスが Lync Server 2013 フロントエンドサーバーと併置されました &nbsp; 。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-113">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="d2b5b-114">チャットルーム管理用の常設チャット Web サービスも、Lync Server 2013 フロントエンドサーバーと併置されてい &nbsp; ます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-114">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="d2b5b-115">チャットルームのコンテンツ、ルーム、およびカテゴリが格納される常設チャットコンテンツデータベースをホストする SQL Server バックエンドデータベースをホストするサーバー (ミラーリングが使用されている場合は複数のサーバー)。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-115">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2b5b-116">バックエンドデータベースは、作成されたカテゴリおよび常設チャットルームに関する情報を含む、チャット履歴データを格納します。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-116">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="d2b5b-117">コンプライアンスが有効になっている場合は、常設チャットコンプライアンスデータベースをホストする SQL Server バックエンドデータベースをホストするサーバー (ミラーリングが使用されている場合は複数のサーバー) が保存されます。コンプライアンスイベントと、コンプライアンスのためのチャットコンテンツが保存されます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-117">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="d2b5b-118">別のコンピューター (管理コンソールなど) から常設チャットサーバーを管理するには、コンピューターの Lync Server コントロールパネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-118">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="d2b5b-119">このコンピューターは、Active Directory ドメインサービスのドメインに展開し、フォレストのルートに少なくとも1つのグローバルカタログサーバーを配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-119">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="d2b5b-120">常設チャットサーバーのハードウェア要件およびソフトウェア要件の詳細については、「サポート」のドキュメントの「lync server [2013 の常設チャットサーバーの技術要件](lync-server-2013-technical-requirements-for-persistent-chat-server.md)」、「lync server [2013 のサポートされているハードウェア](lync-server-2013-supported-hardware.md)」、および「 [Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート](lync-server-2013-server-software-and-infrastructure-support.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-120">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="d2b5b-121">サポートされる配置</span><span class="sxs-lookup"><span data-stu-id="d2b5b-121">Supported Collocation</span></span>

<span data-ttu-id="d2b5b-122">Lync Server 2013 では、さまざまな併置シナリオがサポートされており、1台のサーバーで複数のコンポーネントを実行することによって (小規模な組織の場合)、または個別のコンポーネントを異なるサーバーで実行することによって、ハードウェアコストを節約することができます (スケーラビリティとパフォーマンスを必要とする組織が大きい場合)。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-122">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="d2b5b-123">コンポーネントを併置するかどうかを決定する前に、スケーラビリティの要因を必ず検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-123">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="d2b5b-124">常設チャットコンプライアンスサービスは、コンプライアンスが有効になっている場合は、Lync Server 2013 フロントエンドサーバーと併置されます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-124">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="d2b5b-125">常設チャットサーバーは、Standard Edition サーバーに展開できます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-125">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="d2b5b-126">常設チャットサーバーのバックエンドサーバーと常設チャットコンプライアンスデータベースは、ローカルの SQL Server Express バックエンドサーバー上の Standard Edition サーバーに併置できます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-126">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="d2b5b-127">そこに併置できるコンポーネントの詳細については、「サポート」のドキュメントの「supported [server 併置 in Lync server 2013](lync-server-2013-supported-server-collocation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-127">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="d2b5b-128">Lync Server 2013 Enterprise Edition では、常設チャットサーバーを Enterprise Edition サーバーに併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-128">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="d2b5b-129">常設チャットサーバーの SQL Server データベースは、Enterprise Edition フロントエンドプールのバックエンドサーバーデータベースに併置できます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-129">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="d2b5b-130">常設チャットへの準拠のための SQL Server データベースは、Enterprise Edition プールのバックエンドサーバーデータベースと併置することもできます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-130">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d2b5b-131">常設チャットデータベースをホストしているサーバーは、他のデータベースをホストできます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-131">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="d2b5b-132">ただし、他のデータベースとの間で常設チャットデータベースを併置する場合は、常設チャットデータベースで必要なディスク領域が非常に大きくなる可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-132">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="d2b5b-133">このため、常設チャットデータベースをバックエンドデータベースと併置することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-133">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="d2b5b-134">バックエンドデータベースで常設チャットデータベースを併置する場合は、任意のデータベースまたはすべてのデータベースに対して1つの SQL Server インスタンスを使用するか、またはデータベースごとに SQL Server の別のインスタンスを使用することができます。これには次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-134">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="d2b5b-135">SQL Server の各インスタンスには、1つのバックエンドデータベースと1つの常設チャットデータベースのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-135">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="d2b5b-136">すべてのサーバーの役割およびデータベースの併置の詳細については、「サポート」のドキュメントの「supported [server 併置 in Lync server 2013](lync-server-2013-supported-server-collocation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-136">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="d2b5b-137">常設チャットサーバーのトポロジ</span><span class="sxs-lookup"><span data-stu-id="d2b5b-137">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="d2b5b-138">常設チャットサーバーは、次のトポロジをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-138">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="d2b5b-139">Lync Server 2013 Enterprise Edition 1 台のサーバーの常設チャットサーバーのフロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="d2b5b-139">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="d2b5b-140">Lync Server 2013 Enterprise Edition 複数サーバーの常設チャットサーバーフロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="d2b5b-140">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="d2b5b-141">SQL Server Express を使用する Lync Server 2013 Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="d2b5b-141">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="d2b5b-142">次ホップサーバーとしての Standard Edition サーバーを使用した別のサーバー上の Lync Server 2013 Standard Edition サーバーおよび常設チャットサーバー。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-142">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="d2b5b-143">[] トポロジビルダーを使用して、常設チャットサーバーを Lync Server 2013 展開に追加できます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-143">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="d2b5b-144">トポロジには、単一サーバーまたは複数サーバーの常設チャットサーバープールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-144">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d2b5b-145">トポロジビルダーを使用して、単一のサーバーで常設チャットサーバープールを作成した後、そのプールにサーバーを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-145">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="d2b5b-146">単一サーバー トポロジ</span><span class="sxs-lookup"><span data-stu-id="d2b5b-146">Single-Server Topology</span></span>

<span data-ttu-id="d2b5b-147">常設チャットサーバーの最小構成と最も簡単な展開は、1つの常設チャットサーバーのフロントエンドサーバートポロジです。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-147">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="d2b5b-148">この展開では、常設チャットサーバーを実行する単一のサーバー (オプションで、コンプライアンスが有効な場合はコンプライアンスサービスを実行します)、SQL Server データベースの両方をホストするサーバー、およびコンプライアンスが必要な場合は、コンプライアンスデータを格納する SQL Server データベースを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-148">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d2b5b-149">トポロジビルダーでは、単一サーバー展開として開始される常設チャットサーバープールにサーバーを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-149">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="d2b5b-150">単一サーバーを使用する場合でも、後で必要に応じてサーバーを追加できるように、複数サーバー プール トポロジを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-150">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="d2b5b-151">次の図は、コンプライアンスを備えた単一の常設チャットサーバーフロントエンドサーバーのトポロジの必須およびオプションのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-151">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="d2b5b-152">**単一の常設チャット サーバー**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-152">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="d2b5b-153">![コンプライアンスサービスを使用する単一サーバートポロジ](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "コンプライアンスサービスを使用する単一サーバートポロジ")</span><span class="sxs-lookup"><span data-stu-id="d2b5b-153">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="d2b5b-154">複数サーバー トポロジ</span><span class="sxs-lookup"><span data-stu-id="d2b5b-154">Multiple-Server Topology</span></span>

<span data-ttu-id="d2b5b-155">容量と信頼性を高めるために、「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」に記載されているように、複数サーバートポロジを展開できます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-155">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="d2b5b-156">複数サーバートポロジには、常設チャットサーバーを実行しているアクティブなコンピューターを4台まで含めることができます (高可用性と障害復旧の構成では最大8を使用できますが、残りの4つはスタンバイ時)。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-156">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="d2b5b-157">各サーバーは、最大2万の同時ユーザーをサポートできます。合計で8万同時ユーザーは、4台のサーバーがある常設チャットサーバープールに接続されます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-157">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="d2b5b-158">複数サーバートポロジは、複数のサーバーが常設チャットサーバーをホストすることを除けば、1台のサーバートポロジと同じであり、拡張性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-158">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="d2b5b-159">常設チャットサーバーを実行している複数のコンピューターは、Lync Server およびコンプライアンスサービスと同じ Active Directory ドメインサービスドメインに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-159">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="d2b5b-160">次の図は、常設チャットサーバーを実行する複数のコンピューター、オプションのコンプライアンスサービス、および独立したコンプライアンスデータベースで構成される複数サーバートポロジのすべてのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-160">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="d2b5b-161">**複数の常設チャット サーバー**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-161">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="d2b5b-162">![複数サーバートポロジ](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "複数サーバートポロジ")</span><span class="sxs-lookup"><span data-stu-id="d2b5b-162">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="d2b5b-163">複数サーバー トポロジでは、サーバー機能をプールできます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-163">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="d2b5b-164">サーバープールでは、常設チャットサービスはデータの通信と共有を行います。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-164">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="d2b5b-165">たとえば、最初に1つの常設チャットサービスに投稿されたチャット履歴は、システム内の任意の常設チャットサービスから利用できます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-165">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="d2b5b-166">常設チャットサービスを介してアップロードされるファイルには、任意の常設チャットサービスからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-166">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="d2b5b-167">ユーザーは、さまざまな常設チャットサーバーのフロントエンドサーバーに接続でき、チャットして相互に通信することができます。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-167">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="d2b5b-168">TCP 8011 の既定のポートはサーバーをサーバープールに接続し、永続的なチャットサービスが自分との間で通信するため、または管理目的で使用します。</span><span class="sxs-lookup"><span data-stu-id="d2b5b-168">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

