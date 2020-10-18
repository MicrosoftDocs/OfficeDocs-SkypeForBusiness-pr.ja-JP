---
title: 'Lync Server 2013: アーカイブ用のコンポーネントとトポロジ'
description: 'Lync Server 2013: アーカイブ用のコンポーネントとトポロジ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6ccb62993dc6a8dbc098d4a9c5f28b9b3f7fac9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576923"
---
# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="22352-103">Lync Server 2013 でのアーカイブ用のコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="22352-103">Components and topologies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22352-104">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="22352-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="22352-105">Lync Server 2013 IM および会議コンテンツをアーカイブする場合は、Lync Server でのアーカイブを実装できます。</span><span class="sxs-lookup"><span data-stu-id="22352-105">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="22352-106">アーカイブ コンポーネント</span><span class="sxs-lookup"><span data-stu-id="22352-106">Archiving Components</span></span>

<span data-ttu-id="22352-107">アーカイブ機能には次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="22352-107">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="22352-p101">**アーカイブ エージェント:** 統合データ収集エージェントとも呼ばれます。すべてのフロントエンド プールと Standard Edition サーバーに自動的にインストールされ、アクティブ化されます。アーカイブ エージェントは自動的にアクティブ化されますが、アーカイブを有効にし、適切に構成するまで、実際にはメッセージは取得されません。</span><span class="sxs-lookup"><span data-stu-id="22352-p101">**Archiving agents**. Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server. Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="22352-111">**アーカイブデータストレージ**。</span><span class="sxs-lookup"><span data-stu-id="22352-111">**Archiving data storage**.</span></span> <span data-ttu-id="22352-112">Lync Server 2013 のデータ記憶域には、次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="22352-112">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="22352-113">Exchange 2013 ストレージ。</span><span class="sxs-lookup"><span data-stu-id="22352-113">Exchange 2013 storage.</span></span> <span data-ttu-id="22352-114">Microsoft Exchange 統合オプションを有効にした場合、Exchange 2013 サーバーに所属するユーザーメールボックスは、アーカイブされたデータに Exchange 2013 ストレージを使用します。ただし、メールボックスが In-Place ホールドに設定されている場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="22352-114">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="22352-115">SQL Server ストレージ。</span><span class="sxs-lookup"><span data-stu-id="22352-115">SQL Server storage.</span></span> <span data-ttu-id="22352-116">Lync Server 2013 に所属している展開にユーザーがいる場合、サポートされているバージョンの SQL Server を実行するアーカイブデータベースをセットアップして、それらのユーザーのアーカイブを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="22352-116">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="22352-117">アーカイブにはファイル記憶域 ストレージも必要ですが、アーカイブはフロントエンド サーバーまたは Standard Edition サーバーと同じファイル ストレージを使用します。</span><span class="sxs-lookup"><span data-stu-id="22352-117">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="22352-118">アーカイブのハードウェアとソフトウェアの要件の一覧については、「サポート」のドキュメントの「lync server [2013 の場合はサポートされるハードウェア](lync-server-2013-supported-hardware.md) 」および「 [lync Server 2013 のサーバーソフトウェアとインフラストラクチャのサポート](lync-server-2013-server-software-and-infrastructure-support.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22352-118">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="22352-119">サポートされるトポロジ</span><span class="sxs-lookup"><span data-stu-id="22352-119">Supported Topologies</span></span>

<span data-ttu-id="22352-120">アーカイブのサポートを必要とするユーザーを持つ各プールでアーカイブを展開します。</span><span class="sxs-lookup"><span data-stu-id="22352-120">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="22352-121">アーカイブは、Enterprise Edition プールおよび Standard Edition サーバーのフロントエンドサーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="22352-121">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="22352-122">アーカイブ データ ストレージでは以下が可能です。</span><span class="sxs-lookup"><span data-stu-id="22352-122">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="22352-123">Exchange 2013 ストレージとの統合</span><span class="sxs-lookup"><span data-stu-id="22352-123">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="22352-124">個別の SQL Server データベースを使用して展開されている</span><span class="sxs-lookup"><span data-stu-id="22352-124">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="22352-125">Exchange 2013 展開に Lync Server 展開のすべてのユーザーが含まれていない場合は、Exchange 2013 サーバー上のメールボックスを持つユーザーに対して Microsoft Exchange 統合を使用する必要があります。また、アーカイブに使用するために他のすべての Lync ユーザーに対して個別の SQL Server データベースを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22352-125">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="22352-126">サポートされる配置</span><span class="sxs-lookup"><span data-stu-id="22352-126">Supported Collocation</span></span>

<span data-ttu-id="22352-127">Lync Server 2013 では、さまざまな併置シナリオがサポートされており、1台のサーバーで複数のコンポーネントを実行 (小規模な組織の場合)、または個別のコンポーネントを異なるサーバーで実行することによって、ハードウェアコストを節約することができます (スケーラビリティとパフォーマンスを必要とする組織が大規模な場合)。</span><span class="sxs-lookup"><span data-stu-id="22352-127">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="22352-128">コンポーネントを併置するかどうかを決定する前に、スケーラビリティの要因を必ず検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22352-128">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="22352-129">アーカイブは、プールまたは Standard Edition サーバーのフロントエンドサーバーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="22352-129">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="22352-130">そこに併置できるコンポーネントの詳細については、「サポート」のドキュメントの「supported [server 併置 in Lync server 2013](lync-server-2013-supported-server-collocation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22352-130">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="22352-131">ストレージを Exchange 2013 ストレージと統合するのではなく、アーカイブに個別の SQL Server データベースを使用する場合は、アーカイブデータベースを次のいずれかの場所で併置できます。</span><span class="sxs-lookup"><span data-stu-id="22352-131">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="22352-132">監視データベース</span><span class="sxs-lookup"><span data-stu-id="22352-132">Monitoring database</span></span>

  - <span data-ttu-id="22352-133">Enterprise Edition フロントエンド プールのバックエンド データベース</span><span class="sxs-lookup"><span data-stu-id="22352-133">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22352-p108">アーカイブ データベースをホストするサーバーでは、他のデータベースもホストできます。ただし、アーカイブ データベースと他のデータベースを併置することを考慮するときには、数名以上のユーザーのメッセージをアーカイブすると、アーカイブ データベースに必要なディスク領域が非常に大きくなる可能性があることに注意してください。そのため、アーカイブ データベースとバックエンド データベースを併置することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="22352-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="22352-137">アーカイブ データベースを、監視データベースとバックエンド データベースのどちらか一方または両方と併置する場合は、一部のデータベースまたはすべてのデータベースに対して 1 つの SQL インスタンスを使用することも、各データベースに個別の SQL インスタンスを使用することもできます。ただし、次のような制限があります。</span><span class="sxs-lookup"><span data-stu-id="22352-137">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="22352-138">各 SQL インスタンスは、単一のバックエンド データベース、単一の監視データベース、および単一のアーカイブ データベースのみを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="22352-138">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="22352-139">すべてのサーバーの役割およびデータベースの併置の詳細については、「サポート」のドキュメントの「supported [server 併置 in Lync server 2013](lync-server-2013-supported-server-collocation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22352-139">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

