---
title: 'Lync Server 2013: アーカイブ用のコンポーネントとトポロジ'
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
ms.openlocfilehash: cea07370fc0ccaebb5e89cfea958067b3d6373bb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="ebcba-102">Lync Server 2013 でのアーカイブ用のコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="ebcba-102">Components and topologies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebcba-103">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="ebcba-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="ebcba-104">Lync Server 2013 IM および会議コンテンツをアーカイブする場合は、Lync Server でのアーカイブを実装できます。</span><span class="sxs-lookup"><span data-stu-id="ebcba-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="ebcba-105">アーカイブ コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ebcba-105">Archiving Components</span></span>

<span data-ttu-id="ebcba-106">アーカイブ機能には次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ebcba-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="ebcba-p101">**アーカイブ エージェント:** 統合データ収集エージェントとも呼ばれます。すべてのフロントエンド プールと Standard Edition サーバーに自動的にインストールされ、アクティブ化されます。アーカイブ エージェントは自動的にアクティブ化されますが、アーカイブを有効にし、適切に構成するまで、実際にはメッセージは取得されません。</span><span class="sxs-lookup"><span data-stu-id="ebcba-p101">**Archiving agents**. Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server. Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="ebcba-110">**アーカイブデータストレージ**。</span><span class="sxs-lookup"><span data-stu-id="ebcba-110">**Archiving data storage**.</span></span> <span data-ttu-id="ebcba-111">Lync Server 2013 のデータ記憶域には、次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ebcba-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="ebcba-112">Exchange 2013 ストレージ。</span><span class="sxs-lookup"><span data-stu-id="ebcba-112">Exchange 2013 storage.</span></span> <span data-ttu-id="ebcba-113">Microsoft Exchange 統合オプションを有効にした場合、Exchange 2013 サーバーに所属するユーザーメールボックスは、アーカイブされたデータに Exchange 2013 ストレージを使用します。ただし、メールボックスがインプレース保持の対象になっている場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="ebcba-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="ebcba-114">SQL Server ストレージ。</span><span class="sxs-lookup"><span data-stu-id="ebcba-114">SQL Server storage.</span></span> <span data-ttu-id="ebcba-115">Lync Server 2013 に所属している展開にユーザーがいる場合、サポートされているバージョンの SQL Server を実行するアーカイブデータベースをセットアップして、それらのユーザーのアーカイブを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ebcba-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="ebcba-116">アーカイブにはファイル記憶域 ストレージも必要ですが、アーカイブはフロントエンド サーバーまたは Standard Edition サーバーと同じファイル ストレージを使用します。</span><span class="sxs-lookup"><span data-stu-id="ebcba-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="ebcba-117">アーカイブのハードウェアとソフトウェアの要件の一覧については、「サポート」のドキュメントの「lync server [2013 の場合はサポートされるハードウェア](lync-server-2013-supported-hardware.md)」および「 [lync Server 2013 のサーバーソフトウェアとインフラストラクチャのサポート](lync-server-2013-server-software-and-infrastructure-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebcba-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="ebcba-118">サポートされるトポロジ</span><span class="sxs-lookup"><span data-stu-id="ebcba-118">Supported Topologies</span></span>

<span data-ttu-id="ebcba-119">アーカイブのサポートを必要とするユーザーを持つ各プールでアーカイブを展開します。</span><span class="sxs-lookup"><span data-stu-id="ebcba-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="ebcba-120">アーカイブは、Enterprise Edition プールおよび Standard Edition サーバーのフロントエンドサーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="ebcba-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="ebcba-121">アーカイブ データ ストレージでは以下が可能です。</span><span class="sxs-lookup"><span data-stu-id="ebcba-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="ebcba-122">Exchange 2013 ストレージとの統合</span><span class="sxs-lookup"><span data-stu-id="ebcba-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="ebcba-123">個別の SQL Server データベースを使用して展開されている</span><span class="sxs-lookup"><span data-stu-id="ebcba-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="ebcba-124">Exchange 2013 の展開に Lync Server 展開のすべてのユーザーが含まれていない場合は、Exchange 2013 サーバー上のメールボックスがホームになっているユーザーに対して Microsoft Exchange 統合を使用する必要があります。また、他のすべてのデータベースに対して個別の SQL Server データベースを展開する必要があります。アーカイブに使用する Lync ユーザー。</span><span class="sxs-lookup"><span data-stu-id="ebcba-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="ebcba-125">サポートされる配置</span><span class="sxs-lookup"><span data-stu-id="ebcba-125">Supported Collocation</span></span>

<span data-ttu-id="ebcba-126">Lync Server 2013 はさまざまな併置シナリオをサポートしており、1台のサーバーで複数のコンポーネントを実行することによって (小規模な組織の場合)、または別々のサーバーで個別のコンポーネントを実行することによって、ハードウェアコストを節約できます (より大きなスケーラビリティとパフォーマンスを必要とする組織。</span><span class="sxs-lookup"><span data-stu-id="ebcba-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="ebcba-127">コンポーネントを併置するかどうかを決定する前に、スケーラビリティの要因を必ず検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebcba-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="ebcba-128">アーカイブは、プールまたは Standard Edition サーバーのフロントエンドサーバーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="ebcba-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="ebcba-129">そこに併置できるコンポーネントの詳細については、「サポート」のドキュメントの「supported [server 併置 in Lync server 2013](lync-server-2013-supported-server-collocation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebcba-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ebcba-130">ストレージを Exchange 2013 ストレージと統合するのではなく、アーカイブに個別の SQL Server データベースを使用する場合は、アーカイブデータベースを次のいずれかの場所で併置できます。</span><span class="sxs-lookup"><span data-stu-id="ebcba-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="ebcba-131">監視データベース</span><span class="sxs-lookup"><span data-stu-id="ebcba-131">Monitoring database</span></span>

  - <span data-ttu-id="ebcba-132">Enterprise Edition フロントエンド プールのバックエンド データベース</span><span class="sxs-lookup"><span data-stu-id="ebcba-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ebcba-p108">アーカイブ データベースをホストするサーバーでは、他のデータベースもホストできます。ただし、アーカイブ データベースと他のデータベースを併置することを考慮するときには、数名以上のユーザーのメッセージをアーカイブすると、アーカイブ データベースに必要なディスク領域が非常に大きくなる可能性があることに注意してください。そのため、アーカイブ データベースとバックエンド データベースを併置することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="ebcba-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="ebcba-136">アーカイブ データベースを、監視データベースとバックエンド データベースのどちらか一方または両方と併置する場合は、一部のデータベースまたはすべてのデータベースに対して 1 つの SQL インスタンスを使用することも、各データベースに個別の SQL インスタンスを使用することもできます。ただし、次のような制限があります。</span><span class="sxs-lookup"><span data-stu-id="ebcba-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="ebcba-137">各 SQL インスタンスは、単一のバックエンド データベース、単一の監視データベース、および単一のアーカイブ データベースのみを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="ebcba-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="ebcba-138">すべてのサーバーの役割およびデータベースの併置の詳細については、「サポート」のドキュメントの「supported [server 併置 in Lync server 2013](lync-server-2013-supported-server-collocation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebcba-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

