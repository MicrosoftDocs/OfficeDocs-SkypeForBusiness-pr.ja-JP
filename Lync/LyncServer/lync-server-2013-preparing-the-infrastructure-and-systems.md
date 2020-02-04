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
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="bcc7c-102">Lync Server 2013 のインフラストラクチャとシステムの準備</span><span class="sxs-lookup"><span data-stu-id="bcc7c-102">Preparing the infrastructure and systems for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcc7c-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="bcc7c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="bcc7c-104">Lync Server 2013 を展開するには、トポロジの設計を定義して公開するために、トポロジビルダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-104">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="bcc7c-105">トポロジに必要なコンポーネントを特定するには、トポロジビルダーを使用してトポロジの設計を作成し、保存します。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-105">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="bcc7c-106">トポロジビルダーでトポロジを公開する前に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-106">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="bcc7c-107">必要なすべてのコンピューター (すべての必須コンピューター (Lync Server 2013、データベースサーバー、インターネットインフォメーションサービスを実行しているサーバーを実行しているサーバーなど) を含むトポロジ設計の各コンポーネントのハードウェアを入手してインストールします (IIS) とリバースプロキシサーバー (該当する場合)、ネットワークアダプター、ハードウェアロードバランサー、ストレージデバイス (ファイルサーバーなど)。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-107">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="bcc7c-108">展開に必要なコンポーネントを指定するトポロジの定義方法について詳しくは、「 [Lync Server 2013 でトポロジを定義して構成](lync-server-2013-defining-and-configuring-the-topology.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-108">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="bcc7c-109">サーバーのハードウェア要件の詳細については、サポートされているドキュメントで「 [Lync Server 2013 に](lync-server-2013-supported-hardware.md)対応したハードウェア」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-109">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="bcc7c-110">ネットワークインフラストラクチャが要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-110">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="bcc7c-111">詳細については、計画ドキュメントの「 [Lync Server 2013 のネットワークインフラストラクチャ要件](lync-server-2013-network-infrastructure-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-111">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="bcc7c-112">Active Directory ドメインサービスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-112">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="bcc7c-113">トポロジを公開して有効にするには、内部サーバーを AD DS のコンピューターアカウントで表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-113">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="bcc7c-114">これは、コンピューターを AD DS に結合することで実現されます。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-114">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="bcc7c-115">AD DS の準備の詳細については、「 [Lync Server 2013 用の Active Directory ドメインサービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="bcc7c-116">ファイル共有を作成します。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-116">Create a file share.</span></span> <span data-ttu-id="bcc7c-117">Standard Edition サーバーは、必要なファイルのファイル共有をホストできますが、エンタープライズ展開では、ファイル共有をフロントエンドサーバーでホストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-117">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="bcc7c-118">フォルダーおよび共有に対してアクセス制御リスト (ACL) を展開して設定するために必要なアクセス許可とグループメンバーシップは、トポロジビルダーが正常に完了するために適切に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-118">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="bcc7c-119">Topology Builder を実行しているユーザーには、次の権限とグループメンバーシップがあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-119">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="bcc7c-120">ローカル管理者のメンバー</span><span class="sxs-lookup"><span data-stu-id="bcc7c-120">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="bcc7c-121">ドメインユーザーのメンバー</span><span class="sxs-lookup"><span data-stu-id="bcc7c-121">Member of Domain Users</span></span>
    
      - <span data-ttu-id="bcc7c-122">ファイルストアの共有とフォルダーのフルコントロール</span><span class="sxs-lookup"><span data-stu-id="bcc7c-122">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="bcc7c-123">Enterprise Edition の場合、SQL Server をインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-123">For Enterprise Edition, install and configure SQL Server.</span></span> <span data-ttu-id="bcc7c-124">SQL Server のセットアップを完了するには、SQL Server ベースのサーバーがオンラインであり、トポロジを発行したユーザーが sql Server のローカル管理者であり、sql server インスタンスの SQL Server sysadmin グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-124">For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="bcc7c-125">このトピックで説明したすべての準備作業を完了した後で、トポロジを公開する前に、Windows オペレーティングシステムやその他の前提条件となるソフトウェアのインストール、セットアップなど、その他の準備作業も実行する必要があります。IIS と DNS の構成。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-125">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="bcc7c-126">これらのタスクの詳細については、「 [Lync server 2013 を実行しているサーバーのシステム要件](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md)」を参照してください。「lync [server 2013 用に IIS を構成する](lync-server-2013-configure-iis.md)」および「 [lync server 2013 用のインフラストラクチャとシステムの準備](lync-server-2013-preparing-the-infrastructure-and-systems.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-126">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="bcc7c-127">さらに、クライアントとクライアントの要件について理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-127">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="bcc7c-128">詳細については、「 [Lync Server 2013 でのクライアントとデバイスの展開](lync-server-2013-deploying-clients-and-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-128">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bcc7c-129">このセクション中</span><span class="sxs-lookup"><span data-stu-id="bcc7c-129">In This Section</span></span>

  - [<span data-ttu-id="bcc7c-130">Lync Server 2013 のハードウェアのセットアップ</span><span class="sxs-lookup"><span data-stu-id="bcc7c-130">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="bcc7c-131">Lync Server 2013 のソフトウェアのセットアップ</span><span class="sxs-lookup"><span data-stu-id="bcc7c-131">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="bcc7c-132">Lync Server 2013 用の Active Directory ドメイン サービスの準備</span><span class="sxs-lookup"><span data-stu-id="bcc7c-132">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="bcc7c-133">Lync Server 2013 用 SQL Server の構成</span><span class="sxs-lookup"><span data-stu-id="bcc7c-133">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="bcc7c-134">Lync Server 2013 でのフロント エンド プールまたは Standard Edition サーバー用の DNS レコードの構成</span><span class="sxs-lookup"><span data-stu-id="bcc7c-134">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="bcc7c-135">Lync Server 2013 管理ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="bcc7c-135">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

