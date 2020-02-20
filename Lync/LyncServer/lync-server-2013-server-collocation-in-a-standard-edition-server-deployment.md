---
title: Standard Edition サーバー展開における Lync Server 2013 サーバーの併置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7390c3cee8be94f6bead96ff990e380b06011eb7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="b8f09-102">Lync Server 2013 の Standard Edition サーバー展開でのサーバーの併置</span><span class="sxs-lookup"><span data-stu-id="b8f09-102">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8f09-103">_**トピックの最終更新日:** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="b8f09-103">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="b8f09-104">このセクションでは、Lync Server 2013 Standard Edition サーバー展開で併置できるサーバーの役割、データベース、およびファイル共有について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8f09-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="b8f09-105">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="b8f09-105">Server Roles</span></span>

<span data-ttu-id="b8f09-106">Lync Server 2013 では、音声ビデオ会議サービス、仲介サービス、監視、およびアーカイブが Standard Edition サーバーに併置されていますが、これを有効にするには追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="b8f09-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="b8f09-107">仲介サービスを別のサーバーに展開することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b8f09-107">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="b8f09-108">信頼されたアプリケーションサーバーと Standard Edition サーバーを併置して検索することができます。</span><span class="sxs-lookup"><span data-stu-id="b8f09-108">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="b8f09-109">次のサーバーの役割は、それぞれ別のコンピューターに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8f09-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="b8f09-110">ディレクター</span><span class="sxs-lookup"><span data-stu-id="b8f09-110">Director</span></span>

  - <span data-ttu-id="b8f09-111">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="b8f09-111">Edge Server</span></span>

  - <span data-ttu-id="b8f09-112">仲介サーバー (Standard Edition サーバーと併置されていない場合)</span><span class="sxs-lookup"><span data-stu-id="b8f09-112">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="b8f09-113">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="b8f09-113">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="b8f09-114">Databases</span><span class="sxs-lookup"><span data-stu-id="b8f09-114">Databases</span></span>

<span data-ttu-id="b8f09-115">既定では、SQL Server Express バックエンドデータベースは Standard Edition サーバーに併置されています。</span><span class="sxs-lookup"><span data-stu-id="b8f09-115">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="b8f09-116">別のコンピューターに移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8f09-116">You cannot move it to a separate computer.</span></span> <span data-ttu-id="b8f09-117">1つの例外を除き、Standard Edition サーバーで他のデータベースを併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8f09-117">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="b8f09-118">常設チャットサーバーを Standard Edition サーバーに展開する場合は、同一の Standard Edition サーバーで常設チャットデータベースと常設チャットコンプライアンスデータベースを併置して検索できます。</span><span class="sxs-lookup"><span data-stu-id="b8f09-118">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="b8f09-119">1つのデータベースサーバー上で、次の各データベースを併置できます。</span><span class="sxs-lookup"><span data-stu-id="b8f09-119">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="b8f09-120">監視データベース</span><span class="sxs-lookup"><span data-stu-id="b8f09-120">Monitoring database</span></span>

  - <span data-ttu-id="b8f09-121">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="b8f09-121">Archiving database</span></span>

  - <span data-ttu-id="b8f09-122">Enterprise Edition フロントエンドプールのバックエンドデータベース</span><span class="sxs-lookup"><span data-stu-id="b8f09-122">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="b8f09-123">これらのデータベースのいずれかまたはすべてを1つの SQL インスタンスで併置したり、それぞれに個別の SQL インスタンスを使用したりするには、次のような制限があります。</span><span class="sxs-lookup"><span data-stu-id="b8f09-123">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="b8f09-124">各 SQL インスタンスには、1つのバックエンドデータベース (Enterprise Edition フロントエンドプールの場合)、単一の監視データベース、単一のアーカイブデータベース、単一の常設チャットデータベース、および単一の常設チャットコンプライアンスデータベースのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b8f09-124">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="b8f09-125">データベースサーバーは、複数の Enterprise Edition フロントエンドプール、アーカイブを実行している1台のサーバー、監視を実行している1台のサーバー、単一の常設チャットデータベース、および単一の常設チャットコンプライアンスデータベースをサポートできませんが、それぞれの1つをサポートできます。データベースが SQL Server の同じインスタンスを使用するか、SQL Server の別のインスタンスを使用するかに関係なく、</span><span class="sxs-lookup"><span data-stu-id="b8f09-125">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="b8f09-126">このセクションで後述するように、ファイル共有をデータベースと併置できます。</span><span class="sxs-lookup"><span data-stu-id="b8f09-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8f09-127">Lync Server 2013 では、展開内の一部またはすべてのユーザーについて、監視およびアーカイブストレージと Exchange 2013 ストレージを統合するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b8f09-127">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="b8f09-128">Exchange ストレージと同じサーバーに Lync Server またはコンポーネントを実行しているサーバーを展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8f09-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b8f09-129">データベースの併置がサポートされていても、データベースのサイズはすぐに大きくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="b8f09-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="b8f09-130">たとえば、アーカイブ データベースと他のデータベースを併置することを考慮するときには、数名以上のユーザーのメッセージをアーカイブすると、アーカイブ データベースが必要とするディスク容量が非常に大きくなる可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b8f09-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="b8f09-131">このため、エンタープライズプールのバックエンドデータベースを使用して、アーカイブデータベース、常設チャットデータベース、および常設チャットコンプライアンスデータベースなど、複数のデータベースを併置することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="b8f09-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="b8f09-132">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="b8f09-132">File Shares</span></span>

<span data-ttu-id="b8f09-133">ファイル共有は、別個のサーバーを使用することも、次のいくつか、またはすべてと同じサーバーに併置することもできます。</span><span class="sxs-lookup"><span data-stu-id="b8f09-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="b8f09-134">データベース サーバー (Enterprise Edition フロントエンド プールのバック エンド サーバーを含む)</span><span class="sxs-lookup"><span data-stu-id="b8f09-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="b8f09-135">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="b8f09-135">Archiving database</span></span>

  - <span data-ttu-id="b8f09-136">監視データベース</span><span class="sxs-lookup"><span data-stu-id="b8f09-136">Monitoring database</span></span>

  - <span data-ttu-id="b8f09-137">常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="b8f09-137">Persistent Chat database</span></span>

  - <span data-ttu-id="b8f09-138">常設チャットコンプライアンスデータベース</span><span class="sxs-lookup"><span data-stu-id="b8f09-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="b8f09-139">単一のファイル共有を複数のフロントエンド プール、および複数の Standard Edition サーバーで使用できます (これらのプールやサーバーはすべて同じサイトに存在)。</span><span class="sxs-lookup"><span data-stu-id="b8f09-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8f09-140">Lync Server 2013 の監視およびアーカイブでは、Lync Server のファイル共有を Standard Edition サーバーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="b8f09-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="b8f09-141">その他のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="b8f09-141">Other Components</span></span>

<span data-ttu-id="b8f09-142">Lync server 2013 コンポーネントではないリバースプロキシサーバーを併置することはできませんが、任意の Lync Server 2013 サーバーの役割を持つフェデレーションユーザーに対して web コンテンツの共有をサポートする必要がある場合は、展開で必要になります。</span><span class="sxs-lookup"><span data-stu-id="b8f09-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="b8f09-143">ただし、他のアプリケーションで使用されている組織内の既存のリバースプロキシサーバーのサポートを構成することによって、Lync Server 2013 展開のリバースプロキシサポートを実装できます。</span><span class="sxs-lookup"><span data-stu-id="b8f09-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="b8f09-144">任意の Exchange UM コンポーネントまたは SharePoint コンポーネントを任意の Lync Server 2013 の役割で併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8f09-144">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

