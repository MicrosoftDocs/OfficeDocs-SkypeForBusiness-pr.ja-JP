---
title: 'Lync Server 2013: 常設チャットサーバーの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a76f3bb2a3ccc182f16e2e1416bdec00aefe3e7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506094"
---
# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="0b066-102">Lync Server 2013 での常設チャットサーバーの展開</span><span class="sxs-lookup"><span data-stu-id="0b066-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b066-103">_**トピックの最終更新日:** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="0b066-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="0b066-104">Lync Server 2013、常設チャットサーバーは Lync Server 2013 インフラストラクチャの一部です。</span><span class="sxs-lookup"><span data-stu-id="0b066-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="0b066-105">常設チャットサーバーを展開するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b066-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="0b066-106">トポロジビルダーを使用して、展開するトポロジとコンポーネントを定義またはインポートし、続けて公開します。</span><span class="sxs-lookup"><span data-stu-id="0b066-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="0b066-107">常設チャットサーバーコンポーネントを展開するための環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="0b066-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="0b066-108">展開用に常設チャットサーバーコンポーネントをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="0b066-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="0b066-109">常設チャットサーバーは、Lync Server 2013 Enterprise Edition と別のプールとして使用できます (Enterprise Edition フロントエンドサーバーと併置されていません)。</span><span class="sxs-lookup"><span data-stu-id="0b066-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="0b066-110">常設チャットサーバーには、エンタープライズエディションのプールに SQL Server バックエンドサーバーが必要です。これには、チャットルームのコンテンツやその他の関連するメタデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="0b066-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="0b066-111">**PersistentChatStore**は、専用の Sql Server バックエンドサーバーにインストールすることをお勧めします。ただし、Lync server 2013 のバックエンドサーバーと**PERSISTENTCHATSTORE**を同じ sql server インスタンスに併置することはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0b066-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="0b066-112">常設チャットサーバーは、Lync Server 2013 Standard Edition と共に展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b066-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="0b066-113">この場合、 **PersistentChatService** フロントエンドサーバーは Standard Edition コンピューターに併置され、 **PersistentChatStore** バックエンドサーバーをローカルの SQL Server Express インスタンスに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="0b066-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="0b066-114">サポートされている colocation 構成の詳細については、「 [Lync server 2013 でサポートされるサーバーの併置](lync-server-2013-supported-server-collocation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b066-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0b066-115">常設チャットサーバー Standard Edition では高可用性がサポートされていません &nbsp; 。</span><span class="sxs-lookup"><span data-stu-id="0b066-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="0b066-116">パフォーマンスとスケーラビリティ には制限があります。</span><span class="sxs-lookup"><span data-stu-id="0b066-116">Performance and scale will be limited.</span></span> <span data-ttu-id="0b066-117">さらに、新しい常設チャットサーバー &nbsp; Standard Edition サーバーのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0b066-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="0b066-118">Lync server 2010 のグループチャットサーバーから Lync Server 2013 &nbsp; 常設チャットサーバー Standard Edition へのアップグレードはサポートされていません &nbsp; 。</span><span class="sxs-lookup"><span data-stu-id="0b066-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="0b066-119">組織でコンプライアンスサポートが必要な場合は、常設チャットサーバーのフロントエンドサーバーに常設チャットサーバーコンプライアンスサービスをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="0b066-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="0b066-120">コンプライアンスには別のデータベースが必要です。</span><span class="sxs-lookup"><span data-stu-id="0b066-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="0b066-121">少なくとも、各トポロジには、Lync Server 2013 がインストールされたサーバーと SQL Server データベースソフトウェアがインストールされたサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="0b066-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="0b066-122">トポロジビルダーを使用して、Lync Server 2013 展開に常設チャットサーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0b066-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="0b066-123">トポロジビルダーを使用して、1つまたは複数の常設チャットサーバープールを追加することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0b066-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="0b066-124">他のプールの場合と同じように、複数の常設チャットサーバープールを展開する場合の同じ展開手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0b066-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="0b066-125">詳細については、「展開」のドキュメントの「[Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b066-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="0b066-126">利用可能なトポロジの詳細、および常設チャットサーバーをインストールするための技術およびソフトウェアの要件の詳細については、「計画」の[How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)ドキュメントの「Planning [for persistent Chat 2013 2013 server](lync-server-2013-planning-for-persistent-chat-server.md) 」、「計画」のドキュメント、「展開」のドキュメント、または「操作」のドキュメント、および「サポート」2013のドキュメントの「[サポートされるハードウェア](lync-server-2013-supported-hardware.md)」を参照</span><span class="sxs-lookup"><span data-stu-id="0b066-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="0b066-127">証明書の取得、SQL Server データベースの作成、およびファイルストアの作成の詳細については、「展開」のドキュメントの「 [展開 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b066-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="0b066-128">1台の常設チャットサーバーフロントエンドサーバーでは、2万アクティブユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="0b066-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="0b066-129">合計8万の同時ユーザーをサポートする最大4台のアクティブなフロントエンドサーバーで、常設チャットサーバープールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0b066-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="0b066-130">常設チャットサーバーは、仮想サーバーでもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0b066-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="0b066-131">仮想サーバーは、物理サーバーの仕様に適合していれば、20,000 人のユーザーまで同時にサポートできます。</span><span class="sxs-lookup"><span data-stu-id="0b066-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0b066-132">ファイルシステムのセキュリティを適用するには、NTFS ファイルシステムに常設チャットサーバーをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b066-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="0b066-133">FAT32 は、常設チャットサーバー用のファイルシステムとしてサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0b066-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0b066-134">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0b066-134">In This Section</span></span>

  - [<span data-ttu-id="0b066-135">Lync Server 2013 での常設チャットサーバーの動作</span><span class="sxs-lookup"><span data-stu-id="0b066-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="0b066-136">Lync Server 2013 の常設チャットサーバーの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="0b066-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="0b066-137">Lync Server 2013 の常設チャットサーバーの技術要件</span><span class="sxs-lookup"><span data-stu-id="0b066-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="0b066-138">Lync Server 2013 での常設チャットサーバーのシステムおよびインフラストラクチャのセットアップ</span><span class="sxs-lookup"><span data-stu-id="0b066-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="0b066-139">Lync Server 2013 での展開への常設チャットサーバーの追加</span><span class="sxs-lookup"><span data-stu-id="0b066-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="0b066-140">Lync Server 2013 での常設チャットサーバーのインストール</span><span class="sxs-lookup"><span data-stu-id="0b066-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="0b066-141">Lync Server 2013 での常設チャット管理者の追加</span><span class="sxs-lookup"><span data-stu-id="0b066-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="0b066-142">Lync Server 2013 での常設チャットサーバーの構成</span><span class="sxs-lookup"><span data-stu-id="0b066-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="0b066-143">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="0b066-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="0b066-144">Lync Server 2013 での Windows PowerShell コマンドレットを使用した常設チャットサーバー構成のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0b066-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="0b066-145">Lync Server 2013 での高可用性および障害復旧用の常設チャットサーバーの構成</span><span class="sxs-lookup"><span data-stu-id="0b066-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="0b066-146">Lync Server 2013 での常設チャットサーバーのフェールオーバーとフェールバック</span><span class="sxs-lookup"><span data-stu-id="0b066-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

