---
title: 'Lync Server 2013: サポートされているサーバー移行パスと共存のシナリオ'
description: 'Lync Server 2013: サポートされているサーバー移行パスと共存のシナリオ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44d0a40ac6cc6570cf79b56dc896277c83909b5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560233"
---
# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a><span data-ttu-id="27e59-103">Lync Server 2013 でサポートされているサーバー移行パスと共存のシナリオ</span><span class="sxs-lookup"><span data-stu-id="27e59-103">Supported server migration paths and coexistence scenarios in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27e59-104">_**トピックの最終更新日:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="27e59-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="27e59-105">Lync Server 2013 は、以下のいずれかの移行をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="27e59-105">Lync Server 2013 supports migration from either of the following:</span></span>

  - <span data-ttu-id="27e59-106">Microsoft Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="27e59-106">Microsoft Lync Server 2010</span></span>

  - <span data-ttu-id="27e59-107">Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="27e59-107">Microsoft Office Communications Server 2007 R2</span></span>

<span data-ttu-id="27e59-108">これらの以前のバージョンの両方を実行している環境からの移行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27e59-108">Migration from an environment running both of these previous versions is not supported.</span></span> <span data-ttu-id="27e59-109">Microsoft Office Communications Server 2007 または Live Communications Server 2005 などの以前のバージョンからの移行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27e59-109">Migration from earlier versions, such as Microsoft Office Communications Server 2007 or Live Communications Server 2005, is not supported.</span></span> <span data-ttu-id="27e59-110">以前の展開にグループチャットが含まれていた場合は、個別に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e59-110">If your previous deployment included Group Chat, you must migrate it separately.</span></span>

<div>

## <a name="migration-methods"></a><span data-ttu-id="27e59-111">移行方法</span><span class="sxs-lookup"><span data-stu-id="27e59-111">Migration Methods</span></span>

<span data-ttu-id="27e59-112">すべての Lync Server トポロジおよびサーバーの役割の移行がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="27e59-112">Migration of all Lync Server topologies and server roles is supported.</span></span> <span data-ttu-id="27e59-113">Standard Edition サーバーから Enterprise Edition サーバーへのトポロジを含め、あるトポロジから別のトポロジに移行できます。</span><span class="sxs-lookup"><span data-stu-id="27e59-113">You can migrate from one topology to a different topology, including from Standard Edition server to Enterprise Edition server.</span></span>

<span data-ttu-id="27e59-114">Lync Server 2013 でサポートされるのは、次の移行方法のみです。</span><span class="sxs-lookup"><span data-stu-id="27e59-114">Lync Server 2013 supports only the following migration method:</span></span>

  - <span></span>  
    <span data-ttu-id="27e59-115">**並行した移行。**</span><span class="sxs-lookup"><span data-stu-id="27e59-115">**Side-by-side migration.**</span></span> <span data-ttu-id="27e59-116">Side-by-side 移行では、Lync Server 2013 が既存の Microsoft Lync Server 2010 または Office Communications Server 2007 R2 展開と共に展開され、その後、運用を新しいサーバーに移行して、ユーザーを Lync Server 2013 に移行します。</span><span class="sxs-lookup"><span data-stu-id="27e59-116">In side-by-side migration, Lync Server 2013 is deployed alongside an existing Microsoft Lync Server 2010 or Office Communications Server 2007 R2 deployment, and then you transfer operations to the new servers and move users to Lync Server 2013.</span></span> <span data-ttu-id="27e59-117">この方法では、移行中にハードウェアとソフトウェアを含む追加のサーバープラットフォームが必要です。また、新しい構成ではシステム名とプール名が異なります。</span><span class="sxs-lookup"><span data-stu-id="27e59-117">This method requires additional server platforms, including hardware and software, during migration, and system names and pool names are different in the new configuration.</span></span> <span data-ttu-id="27e59-118">以前のバージョンにロールバックする必要が生じた場合は、操作を以前のサーバーに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="27e59-118">If it becomes necessary to roll back to the previous version, you can shift operations back to the previous servers.</span></span>

<span data-ttu-id="27e59-119">Active Directory ドメインサービスフォレスト間での移行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27e59-119">Migration across Active Directory Domain Services forests is not supported.</span></span>

<span data-ttu-id="27e59-120">推奨される移行パスは、段階的なアプローチです。</span><span class="sxs-lookup"><span data-stu-id="27e59-120">The recommended migration path is a phased approach.</span></span> <span data-ttu-id="27e59-121">以前のリリースからの移行の詳細については、「移行」のドキュメントの次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e59-121">For details about migrating from a previous release, including the appropriate phasing of component deployment, see the following topics in the Migration documentation:</span></span>

  - [<span data-ttu-id="27e59-122">Lync Server 2010 から Lync Server 2013 への移行</span><span class="sxs-lookup"><span data-stu-id="27e59-122">Migration from Lync Server 2010 to Lync Server 2013</span></span>](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [<span data-ttu-id="27e59-123">Office Communications Server 2007 R2 から Lync Server 2013 への移行</span><span class="sxs-lookup"><span data-stu-id="27e59-123">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [<span data-ttu-id="27e59-124">Lync Server 2010、グループ チャットまたは Office Communicatins Server 2007 R2 グループ チャットから Lync Server 2013、常設チャット サーバーへの移行</span><span class="sxs-lookup"><span data-stu-id="27e59-124">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a><span data-ttu-id="27e59-125">共存シナリオ</span><span class="sxs-lookup"><span data-stu-id="27e59-125">Coexistence Scenarios</span></span>

<span data-ttu-id="27e59-126">Lync Server 2013 は、Lync Server 2010 展開または Office Communications Server 2007 R2 展開のコンポーネントと共存できます。</span><span class="sxs-lookup"><span data-stu-id="27e59-126">Lync Server 2013 can coexist with components of either a Lync Server 2010 deployment or an Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="27e59-127">Lync server 2010 と Office Communications Server 2007 R2 (すべてのバージョンの同時展開) の両方で Lync Server 2013 を同時に展開することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27e59-127">Concurrent deployment of Lync Server 2013 with both Lync Server 2010 and Office Communications Server 2007 R2 (concurrent deployment of all three versions) is not supported.</span></span>

<span data-ttu-id="27e59-128">以前の Lync Server 2010 または Office Communications Server 2007 R2 展開が新しい Lync Server 2013 展開を一時的に coexists する段階的な移行では、混在バージョンルーティングのサポートは制限されています。</span><span class="sxs-lookup"><span data-stu-id="27e59-128">During a phased migration in which a previous Lync Server 2010 or Office Communications Server 2007 R2 deployment coexists temporarily with the new Lync Server 2013 deployment, support for mixed version routing is limited.</span></span> <span data-ttu-id="27e59-129">詳細については、移行に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e59-129">For details, see the Migration documentation.</span></span>

<span data-ttu-id="27e59-130">Lync Server 2013 データベースインスタンスでは、Microsoft SQL Server 2008 R2 または Microsoft SQL Server 2012 を実行している独立した別個のコンピューターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e59-130">You must use separate and distinct computers running Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for your Lync Server 2013 database instances.</span></span> <span data-ttu-id="27e59-131">Lync Server 2010 または Office Communications Server 2007 R2 フロントエンドプールに使用する Lync Server 2013 フロントエンドプールに対して、同じ SQL Server のインスタンスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="27e59-131">You cannot use the same instance of SQL Server for a Lync Server 2013 Front End pool that you use for a Lync Server 2010 or Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="27e59-132">既に Lync 2010 Server または Office Communications Server 2007 R2 が展開されている展開のために、トポロジビルダーで Lync Server 2013 を定義して構成した場合、トポロジビルダーでは、トポロジで既に使用されている Lync Server 2013 のインスタンスを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="27e59-132">If you define and configure Lync Server 2013 in Topology Builder for a deployment that already has Lync Server 2010 or Office Communications Server 2007 R2 deployed, Topology Builder will not allow you to define an instance of a Lync Server 2013 that is already in use in the topology.</span></span>

<span data-ttu-id="27e59-133">トポロジビルダーでは、次のメッセージが表示されます。この問題については、「 \[ サーバーの sql server の FQDN \] に、sql インスタンスのホストされている役割のユーザーストアが既に含まれています。」というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27e59-133">Topology Builder will display the following message to inform you of this issue: "The SQL server \[FQDN of the server\] already contains a SQL instance hosting role 'User Store."</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="27e59-134">Lync Server 2013 の展開に新しく追加されたサーバーの役割を展開する場合は、まず、「移行」のドキュメントおよび「展開」のドキュメントで説明されているように既存の展開をアップグレードしてから、「計画」のドキュメントと「展開」のドキュメントで説明されているように、新しいサーバーの役割を展開します。</span><span class="sxs-lookup"><span data-stu-id="27e59-134">If you intend to deploy server roles that are new to your Lync Server 2013 deployment, you should first upgrade your existing deployment as described in the Migration documentation and the Deployment documentation, and then deploy the new server roles as described in the Planning documentation and Deployment documentation.</span></span> <span data-ttu-id="27e59-135">以前のバージョンのグループチャットを移行する場合は、Lync Server 2010 または Office Communications Server 2007 R2 から他のすべてのコンポーネントを移行するプロセスを完了した後、最後に移行します。</span><span class="sxs-lookup"><span data-stu-id="27e59-135">If you are migrating a previous version of Group Chat, migrate it last, after completing the process for migrating all other components from Lync Server 2010 or Office Communications Server 2007 R2.</span></span>



</div>

<span data-ttu-id="27e59-136">特定の共存要件および Lync Server 2010 または Office Communications Server 2007 R2 および Lync Server 2013 コンポーネントの共存および移行の詳細については、「移行」のドキュメントの「 [migration From Lync server 2010 To Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) 」および「 [Migration From Office Communications server 2007 R2 to lync server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e59-136">For specific coexistence requirements and other details about coexistence and migration of Lync Server 2010 or Office Communications Server 2007 R2 and Lync Server 2013 components, see [Migration from Lync Server 2010 to Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in the Migration documentation.</span></span> <span data-ttu-id="27e59-137">クライアントの混合バージョンサポートの詳細については、「 [Lync Server 2013 での以前の展開でサポートされているクライアント](lync-server-2013-supported-clients-from-previous-deployments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e59-137">For details about mixed version support for clients, see [Supported clients from previous deployments in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

