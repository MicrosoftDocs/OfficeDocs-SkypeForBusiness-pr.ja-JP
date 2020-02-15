---
title: 'Lync Server 2013: ハードウェアセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02161765e6d3bd9c56eaddcb7f79b9d41dac3b16
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="ae57c-102">Lync Server 2013 のハードウェアのセットアップ</span><span class="sxs-lookup"><span data-stu-id="ae57c-102">Hardware setup for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae57c-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ae57c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ae57c-104">トポロジを実装するために必要なインフラストラクチャで必要なハードウェアとその他のコンポーネントを設定するには、トポロジビルダーでトポロジを公開する前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae57c-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="ae57c-105">必要なすべてのコンピューター (Lync Server 2013、データベースサーバー、インターネットインフォメーションサービス (IIS) を実行しているサーバーを実行しているサーバー) を含む、トポロジビルダーを使用して作成および保存した各コンポーネントのハードウェアをインストールし、必要に応じて、リバースプロキシサーバー、ネットワークアダプター、ハードウェアロードバランサー、およびストレージデバイス (ファイルサーバーなど)。</span><span class="sxs-lookup"><span data-stu-id="ae57c-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="ae57c-106">ネットワーク アダプターについて推奨される数および速度に従っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae57c-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="ae57c-107">ハードウェアロードバランサーを使用する場合は、それらを構成して Lync Server 2013 で使用できるようにするための適切な情報がベンダーから得られていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae57c-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="ae57c-108">ファイルサーバーまたはその他のサーバーを使用して Lync Server で必要なファイル共有を格納する場合は、サーバーが利用可能であり、ファイル共有の構成の準備が整っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae57c-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="ae57c-109">展開に必要なコンポーネントを指定するトポロジを定義する方法の詳細については、「 [Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae57c-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="ae57c-110">サーバーのハードウェア要件の詳細については、「サポート」のドキュメントの「supported [hardware For Lync Server 2013](lync-server-2013-supported-hardware.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae57c-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="ae57c-111">ネットワークインフラストラクチャが要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae57c-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="ae57c-112">詳細については、「計画」のドキュメントの「 [Lync Server 2013 のネットワークインフラストラクチャ要件](lync-server-2013-network-infrastructure-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae57c-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="ae57c-113">Active Directory ドメインサービスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="ae57c-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="ae57c-114">AD DS の設定には、AD DS の準備、AD DS に展開するすべてのコンポーネントの定義などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae57c-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="ae57c-115">AD DS の準備の詳細については、「展開」のドキュメントの「 [Active Directory ドメインサービスの Lync Server 2013 の準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae57c-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ae57c-116">ファイル共有の作成に必要なアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="ae57c-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="ae57c-117">Lync Server 2013 でファイル共有を使用するためのアクセス許可は、トポロジを公開するときに、トポロジビルダーによって自動的に構成されます。</span><span class="sxs-lookup"><span data-stu-id="ae57c-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="ae57c-118">ただし、トポロジビルダーで必要なアクセス許可を構成するためには、トポロジの公開に使用されるユーザーアカウントに、ファイル共有のフルコントロール (読み取り/書き込み/変更) が必要です。</span><span class="sxs-lookup"><span data-stu-id="ae57c-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="ae57c-119">トポロジビルダーの公開プロセス中にファイル共有を適切に管理できるようにするには、ユーザーまたはユーザーがメンバーになっているドメイングループを、ファイル共有が配置されているコンピューターのローカルの Administrators グループのメンバーにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae57c-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="ae57c-120">マルチドメイン シナリオでは、ドメイン A のユーザーまたはグループを、ファイル共有が配置されるドメイン B のマシン上でローカルの Administrators グループのメンバーにしてください。</span><span class="sxs-lookup"><span data-stu-id="ae57c-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="ae57c-121">分散ファイルシステム (DFS) でのファイル共有の使用を更新する方法の詳細については、「 [Configure file storage For Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae57c-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="ae57c-122">Lync Server 2013 Enterprise Edition のファイル共有は、フロントエンドサーバーに配置できません。</span><span class="sxs-lookup"><span data-stu-id="ae57c-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="ae57c-123">Web サービス用のロードバランサー機器をインストールしてセットアップします。</span><span class="sxs-lookup"><span data-stu-id="ae57c-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="ae57c-124">ドメイン ネーム システム (DNS) の負荷分散が展開されている場合には、その後もこれらのプールでハードウェア ロード バランサーを使用する必要がありますが、HTTP/HTTPS トラフィックの場合だけです。</span><span class="sxs-lookup"><span data-stu-id="ae57c-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="ae57c-125">ハードウェア ロード バランサーは、クライアントからのポート 443 および 80 経由での HTTPS トラフィックで使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae57c-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="ae57c-126">これらのプール用のハードウェア ロード バランサーは引き続き必要ですが、そのセットアップと管理は主に HTTP/HTTPS トラフィックに対するものであり、ハードウェア ロード バランサーの管理者にはなじみのあるものです。</span><span class="sxs-lookup"><span data-stu-id="ae57c-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="ae57c-127">このトピックの説明に従ってすべての準備タスクを完了したた場合でも、トポロジの公開前に、次のタスクを完了させておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae57c-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="ae57c-128">Lync Server 2013 のサーバーにオペレーティングシステムと必要なソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="ae57c-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="ae57c-129">Lync Server 2013 の IIS を構成する</span><span class="sxs-lookup"><span data-stu-id="ae57c-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="ae57c-130">Lync Server 2013 用 SQL Server の構成</span><span class="sxs-lookup"><span data-stu-id="ae57c-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="ae57c-131">フロントエンドプールまたは Standard Edition サーバーの Lync Server 2013 で DNS レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="ae57c-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

