---
title: 'Lync Server 2013: インフラストラクチャとシステムの準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95156c862c2c6fbee1b3a4625d8b9db234012a91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="62ad3-102">Lync Server 2013 のインフラストラクチャとシステムの準備</span><span class="sxs-lookup"><span data-stu-id="62ad3-102">Preparing the infrastructure and systems for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62ad3-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="62ad3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="62ad3-104">Lync Server 2013 の展開では、トポロジビルダーを使用してトポロジ設計を定義して公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62ad3-104">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="62ad3-105">トポロジに必要なコンポーネントを特定するには、トポロジビルダーを使用してトポロジ設計を作成し、保存します。</span><span class="sxs-lookup"><span data-stu-id="62ad3-105">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="62ad3-106">トポロジ ビルダーでトポロジを公開する前に、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="62ad3-106">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="62ad3-107">必要なすべてのコンピューター (Lync Server 2013、データベースサーバー、インターネットインフォメーションサービスを実行しているサーバーを実行しているサーバー) を含む、トポロジビルダーを使用して作成および保存した各コンポーネントのハードウェアを取得してインストールします (IIS)、リバースプロキシサーバー、必要に応じて、ネットワークアダプター、ハードウェアロードバランサー、およびストレージデバイス (ファイルサーバーなど)。</span><span class="sxs-lookup"><span data-stu-id="62ad3-107">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="62ad3-108">展開に必要なコンポーネントを指定するトポロジを定義する方法の詳細については、「 [Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62ad3-108">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="62ad3-109">サーバーのハードウェア要件の詳細については、「サポート」のドキュメントの「supported [hardware For Lync Server 2013](lync-server-2013-supported-hardware.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62ad3-109">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="62ad3-110">ネットワークインフラストラクチャが要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="62ad3-110">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="62ad3-111">詳細については、「計画」のドキュメントの「 [Lync Server 2013 のネットワークインフラストラクチャ要件](lync-server-2013-network-infrastructure-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62ad3-111">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="62ad3-112">Active Directory ドメインサービスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="62ad3-112">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="62ad3-113">トポロジを公開し、有効化するには、内部サーバーが AD DS のコンピューター アカウントで表される必要があります。</span><span class="sxs-lookup"><span data-stu-id="62ad3-113">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="62ad3-114">そのようにするには、コンピューターを AD DS に参加させます。</span><span class="sxs-lookup"><span data-stu-id="62ad3-114">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="62ad3-115">AD DS の準備の詳細については、「 [Lync Server 2013 用の Active Directory ドメインサービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62ad3-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="62ad3-116">ファイル共有を作成します。</span><span class="sxs-lookup"><span data-stu-id="62ad3-116">Create a file share.</span></span> <span data-ttu-id="62ad3-117">Standard Edition サーバーは必要なファイルのファイル共有をホストできますが、Enterprise 展開ではフロントエンド サーバーでファイル共有をホストできません。</span><span class="sxs-lookup"><span data-stu-id="62ad3-117">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="62ad3-118">トポロジ ビルダーが正常に完了するには、フォルダーと共有に対するアクセス制御リスト (ACL) の展開と設定に必要なアクセス許可とグループ メンバーシップを正しく設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62ad3-118">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="62ad3-119">トポロジビルダーを実行しているユーザーに、次のアクセス許可とグループメンバーシップがあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62ad3-119">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="62ad3-120">ローカルの Administrators グループのメンバー</span><span class="sxs-lookup"><span data-stu-id="62ad3-120">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="62ad3-121">Domain Users グループのメンバー</span><span class="sxs-lookup"><span data-stu-id="62ad3-121">Member of Domain Users</span></span>
    
      - <span data-ttu-id="62ad3-122">ファイル ストアの共有とフォルダーに対するフル コントロール</span><span class="sxs-lookup"><span data-stu-id="62ad3-122">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="62ad3-p106">Enterprise Edition の場合は、SQL Server をインストールし、構成します。SQL Server を正常にセットアップするには、SQL Server ベースのサーバーがオンラインであることと、トポロジを公開する担当者が SQL Server のローカル管理者であり、SQL Server インスタンスの SQL Server sysadmin グループのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="62ad3-p106">For Enterprise Edition, install and configure SQL Server. For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="62ad3-125">このトピックで説明する準備タスクをすべて完了した後、トポロジを公開する前に、Windows オペレーティング システムや前提条件となる他のソフトウェアのインストール、IIS のセットアップ、DNS の構成など、他の準備タスクも行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="62ad3-125">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="62ad3-126">これらのタスクの詳細については、「 [Lync server 2013 を実行するサーバーのシステム要件](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md)」、「 [Configure IIS for lync server 2013](lync-server-2013-configure-iis.md)」、および「 [lync server 2013 のインフラストラクチャとシステムの準備](lync-server-2013-preparing-the-infrastructure-and-systems.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62ad3-126">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="62ad3-127">また、クライアントとクライアントの要件についても把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="62ad3-127">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="62ad3-128">詳細については、「 [Lync Server 2013 でのクライアントとデバイスの展開](lync-server-2013-deploying-clients-and-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62ad3-128">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="62ad3-129">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="62ad3-129">In This Section</span></span>

  - [<span data-ttu-id="62ad3-130">Lync Server 2013 のハードウェアのセットアップ</span><span class="sxs-lookup"><span data-stu-id="62ad3-130">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="62ad3-131">Lync Server 2013 のソフトウェアのセットアップ</span><span class="sxs-lookup"><span data-stu-id="62ad3-131">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="62ad3-132">Lync Server 2013 用の Active Directory ドメイン サービスの準備</span><span class="sxs-lookup"><span data-stu-id="62ad3-132">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="62ad3-133">Lync Server 2013 用 SQL Server の構成</span><span class="sxs-lookup"><span data-stu-id="62ad3-133">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="62ad3-134">フロントエンドプールまたは Standard Edition サーバーの Lync Server 2013 で DNS レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="62ad3-134">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="62ad3-135">Lync Server 2013 管理ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="62ad3-135">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

