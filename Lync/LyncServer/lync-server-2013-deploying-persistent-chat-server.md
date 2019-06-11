---
title: 'Lync Server 2013: 常設チャット サーバーの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a730057735f187dc5e5080d532515a4eb9db110
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="512e1-102">Lync Server 2013 での常設チャット サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="512e1-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="512e1-103">_**最終更新日:** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="512e1-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="512e1-104">Lync Server 2013、常設チャットサーバーは Lync Server 2013 インフラストラクチャの一部です。</span><span class="sxs-lookup"><span data-stu-id="512e1-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="512e1-105">常設チャットサーバーを展開するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="512e1-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="512e1-106">トポロジビルダーを使って、トポロジと展開するコンポーネントを定義またはインポートして、その後で公開します。</span><span class="sxs-lookup"><span data-stu-id="512e1-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="512e1-107">常設チャットサーバーコンポーネントを展開するための環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="512e1-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="512e1-108">展開用の常設チャットサーバーコンポーネントをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="512e1-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="512e1-109">常設チャットサーバーは、Lync Server 2013 Enterprise Edition と個別のプールとして利用できます (Enterprise Edition のフロントエンドサーバーとは対応していません)。</span><span class="sxs-lookup"><span data-stu-id="512e1-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="512e1-110">常設チャットサーバーには、チャットルームのコンテンツやその他の関連するメタデータを保存するために、Enterprise Edition プールに SQL Server バックエンドサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="512e1-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="512e1-111">**PersistentChatStore**は、専用の Sql server バックエンドサーバーにインストールすることをお勧めします。ただし、同一の sql server インスタンスで Lync server 2013 のバックエンドサーバーと**PersistentChatStore**を同じ列に配置することはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="512e1-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="512e1-112">常設チャットサーバーは、Lync Server 2013 Standard Edition と共に展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="512e1-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="512e1-113">この場合、 **PersistentChatService**フロントエンドサーバーは Standard Edition コンピューターにあり、 **PersistentChatStore**バックエンドサーバーはローカルの SQL Server Express インスタンスに展開できます。</span><span class="sxs-lookup"><span data-stu-id="512e1-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="512e1-114">サポートされているコロケーション構成の詳細については、「 [Lync server 2013 でサポートされているサーバーの collocation](lync-server-2013-supported-server-collocation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="512e1-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="512e1-115">常設チャット Server&nbsp;Standard Edition では、高可用性をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="512e1-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="512e1-116">パフォーマンスとスケールは制限されます。</span><span class="sxs-lookup"><span data-stu-id="512e1-116">Performance and scale will be limited.</span></span> <span data-ttu-id="512e1-117">さらに、新しい常設チャット Server&nbsp;Standard Edition Server のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="512e1-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="512e1-118">Lync Server 2010、グループチャットサーバーを Lync Server 2013&nbsp;常設 Chat Server&nbsp;Standard Edition にアップグレードすることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="512e1-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="512e1-119">組織でコンプライアンスのサポートが必要な場合は、常設チャットサーバーコンプライアンスサービスを常設チャットサーバーのフロントエンドサーバーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="512e1-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="512e1-120">コンプライアンスには、別のデータベースが必要です。</span><span class="sxs-lookup"><span data-stu-id="512e1-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="512e1-121">少なくとも、各トポロジには、Lync Server 2013 がインストールされているサーバーと SQL Server データベースソフトウェアがインストールされたサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="512e1-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="512e1-122">[トポロジビルダーを使用して、Lync Server 2013 展開に常設チャットサーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="512e1-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="512e1-123">Topology Builder を使用して、1つ以上の常設チャットサーバープールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="512e1-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="512e1-124">任意のプールの場合と同様に、複数の常設チャットサーバープールを展開する場合と同じ展開手順に従います。</span><span class="sxs-lookup"><span data-stu-id="512e1-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="512e1-125">詳細については、「展開ドキュメントの[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="512e1-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="512e1-126">利用可能なトポロジと、常設チャットサーバーをインストールするための技術およびソフトウェアの要件の詳細については、「 [Lync server 2013 での](lync-server-2013-planning-for-persistent-chat-server.md)常設チャットサーバーの計画」を参照してください。 [Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)の計画ドキュメント、展開ドキュメント、または運用マニュアルに記載されています。また、[サポートされているドキュメントの lync server 2013 でサポートされているハードウェア](lync-server-2013-supported-hardware.md)。</span><span class="sxs-lookup"><span data-stu-id="512e1-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="512e1-127">証明書の取得、SQL Server データベースの作成、ファイルストアの作成の詳細については、「展開ドキュメントに[Lync Server 2013 を展開](lync-server-2013-deploying-lync-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="512e1-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="512e1-128">1つの常設チャットサーバーフロントエンドサーバーは、2万アクティブユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="512e1-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="512e1-129">最大4つのアクティブなフロントエンドサーバーには、常設チャットサーバープールを含めることができます。これには、合計8万の同時ユーザーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="512e1-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="512e1-130">常設チャットサーバーも仮想サーバーでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="512e1-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="512e1-131">仮想サーバーは、物理サーバーの仕様と一致した場合に、最大で2万の同時ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="512e1-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="512e1-132">ファイルシステムのセキュリティを適用するには、常設チャットサーバーが NTFS ファイルシステムにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="512e1-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="512e1-133">FAT32 は、常設チャットサーバーでサポートされているファイルシステムではありません。</span><span class="sxs-lookup"><span data-stu-id="512e1-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="512e1-134">このセクション中</span><span class="sxs-lookup"><span data-stu-id="512e1-134">In This Section</span></span>

  - [<span data-ttu-id="512e1-135">Lync Server 2013 での常設チャットサーバーの動作方法</span><span class="sxs-lookup"><span data-stu-id="512e1-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="512e1-136">Lync Server 2013 の常設チャット サーバーの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="512e1-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="512e1-137">Lync Server 2013 の常設チャットサーバーの技術要件</span><span class="sxs-lookup"><span data-stu-id="512e1-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="512e1-138">Lync Server 2013 での常設チャット サーバーのシステムおよびインフラストラクチャのセットアップ</span><span class="sxs-lookup"><span data-stu-id="512e1-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="512e1-139">Lync Server 2013 での展開への常設チャットサーバーの追加</span><span class="sxs-lookup"><span data-stu-id="512e1-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="512e1-140">Lync Server 2013 での常設チャット サーバーのインストール</span><span class="sxs-lookup"><span data-stu-id="512e1-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="512e1-141">Lync Server 2013 での常設チャット管理者の追加</span><span class="sxs-lookup"><span data-stu-id="512e1-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="512e1-142">Lync Server 2013 での常設チャット サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="512e1-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="512e1-143">Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="512e1-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="512e1-144">Lync Server 2013 での Windows PowerShell コマンドレットを使用した常設チャット サーバー構成のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="512e1-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="512e1-145">Lync Server 2013 の高可用性と障害復旧に対応した常設チャット サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="512e1-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="512e1-146">Lync Server 2013 での常設チャット サーバーのフェールオーバーとフェールバック</span><span class="sxs-lookup"><span data-stu-id="512e1-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

