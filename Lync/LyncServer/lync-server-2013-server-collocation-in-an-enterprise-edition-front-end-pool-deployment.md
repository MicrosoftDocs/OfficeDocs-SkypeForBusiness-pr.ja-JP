---
title: Enterprise Edition フロントエンドプール展開における Lync Server 2013 サーバーの併置
description: Lync Server 2013 のサーバーの併置 Enterprise Edition フロントエンドプールの展開。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a937cd2d58e41d56fec3c7898ebcf6725086d51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576553"
---
# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="ca861-103">Lync Server 2013 の Enterprise Edition フロントエンドプール展開でのサーバーの併置</span><span class="sxs-lookup"><span data-stu-id="ca861-103">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca861-104">_**トピックの最終更新日:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="ca861-104">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="ca861-105">このセクションでは、Lync Server 2013 のフロントエンドプール展開で併置できるサーバーの役割、データベース、およびファイル共有について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca861-105">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="ca861-106">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="ca861-106">Server Roles</span></span>

<span data-ttu-id="ca861-107">Lync Server 2013 では、音声ビデオ会議サービス、仲介サービス、監視、およびアーカイブはフロントエンドサーバーに併置されていますが、これを有効にするには追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="ca861-107">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="ca861-108">仲介サーバーは、フロントエンド サーバーと併置しない場合、スタンドアロンの仲介サーバーとして別のコンピューター上に展開できます。</span><span class="sxs-lookup"><span data-stu-id="ca861-108">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="ca861-109">信頼されたアプリケーション サーバーは、フロントエンド サーバーと併置できます。</span><span class="sxs-lookup"><span data-stu-id="ca861-109">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="ca861-110">次のサーバーの役割は、それぞれ別のコンピューターに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca861-110">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="ca861-111">ディレクター</span><span class="sxs-lookup"><span data-stu-id="ca861-111">Director</span></span>

  - <span data-ttu-id="ca861-112">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="ca861-112">Edge Server</span></span>

  - <span data-ttu-id="ca861-113">仲介サーバー (フロントエンド サーバーと併置しない場合)</span><span class="sxs-lookup"><span data-stu-id="ca861-113">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="ca861-114">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="ca861-114">Office Web Apps Server</span></span>

<span data-ttu-id="ca861-115">常設チャットサーバーの役割をフロントエンドサーバーと併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="ca861-115">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="ca861-116">Databases</span><span class="sxs-lookup"><span data-stu-id="ca861-116">Databases</span></span>

<span data-ttu-id="ca861-117">次のそれぞれのデータベースは、同じデータベース サーバーに併置できます。</span><span class="sxs-lookup"><span data-stu-id="ca861-117">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="ca861-118">バック エンド データベース</span><span class="sxs-lookup"><span data-stu-id="ca861-118">Back-end database</span></span>

  - <span data-ttu-id="ca861-119">監視データベース</span><span class="sxs-lookup"><span data-stu-id="ca861-119">Monitoring database</span></span>

  - <span data-ttu-id="ca861-120">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="ca861-120">Archiving database</span></span>

  - <span data-ttu-id="ca861-121">常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="ca861-121">Persistent Chat database</span></span>

  - <span data-ttu-id="ca861-122">常設チャットコンプライアンスデータベース</span><span class="sxs-lookup"><span data-stu-id="ca861-122">Persistent Chat compliance database</span></span>

<span data-ttu-id="ca861-123">これらのデータベースのいずれかまたはすべてを1つの SQL Server インスタンスで併置するか、または SQL Server の個別のインスタンスを使用することができます。これには次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="ca861-123">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="ca861-124">SQL Server の各インスタンスには、1つのバックエンドデータベース、単一の監視データベース、1つのアーカイブデータベース、1つの常設チャットデータベース、および1つの常設チャットコンプライアンスデータベースのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ca861-124">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="ca861-125">データベースサーバーは、複数のフロントエンドプール、1つのアーカイブ展開、および1つの監視展開をサポートできませんが、データベースが SQL Server の同じインスタンスを使用するか、SQL Server の別のインスタンスを使用するかに関係なく、それぞれの1つをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="ca861-125">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="ca861-126">このセクションで後述するように、ファイル共有をデータベースと併置できます。</span><span class="sxs-lookup"><span data-stu-id="ca861-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca861-127">Lync Server 2013 では、展開内の一部またはすべてのユーザーに対してアーカイブストレージを Exchange 2013 ストレージと統合するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ca861-127">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="ca861-128">Exchange ストレージと同じサーバーに Lync Server またはコンポーネントを実行しているサーバーを展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="ca861-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca861-129">データベースの併置がサポートされていても、データベースのサイズはすぐに大きくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="ca861-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="ca861-130">たとえば、アーカイブ データベースと他のデータベースを併置することを考慮するときには、数名以上のユーザーのメッセージをアーカイブすると、アーカイブ データベースが必要とするディスク容量が非常に大きくなる可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ca861-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="ca861-131">このため、複数のデータベース (特に、アーカイブデータベース、常設チャットデータベース、または常設チャットコンプライアンスデータベースとバックエンドデータベース) を併置することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="ca861-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="ca861-132">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="ca861-132">File Share</span></span>

<span data-ttu-id="ca861-133">ファイル共有は、別個のサーバーを使用することも、次のいくつか、またはすべてと同じサーバーに併置することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca861-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="ca861-134">データベース サーバー (Enterprise Edition フロントエンド プールのバック エンド サーバーを含む)</span><span class="sxs-lookup"><span data-stu-id="ca861-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="ca861-135">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="ca861-135">Archiving database</span></span>

  - <span data-ttu-id="ca861-136">監視データベース</span><span class="sxs-lookup"><span data-stu-id="ca861-136">Monitoring database</span></span>

  - <span data-ttu-id="ca861-137">常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="ca861-137">Persistent Chat database</span></span>

  - <span data-ttu-id="ca861-138">常設チャットコンプライアンスデータベース</span><span class="sxs-lookup"><span data-stu-id="ca861-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="ca861-139">単一のファイル共有を複数のフロントエンド プール、および複数の Standard Edition サーバーで使用できます (これらのプールやサーバーはすべて同じサイトに存在)。</span><span class="sxs-lookup"><span data-stu-id="ca861-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca861-140">Lync Server 2013 の監視およびアーカイブでは、Lync Server のファイル共有をフロントエンドサーバーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="ca861-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="ca861-141">その他のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="ca861-141">Other Components</span></span>

<span data-ttu-id="ca861-142">Lync server 2013 コンポーネントではないリバースプロキシサーバーを併置することはできませんが、任意の Lync Server 2013 サーバーの役割を持つフェデレーションユーザーに対して web コンテンツの共有をサポートする必要がある場合は、展開で必要になります。</span><span class="sxs-lookup"><span data-stu-id="ca861-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="ca861-143">ただし、他のアプリケーションで使用されている組織内の既存のリバースプロキシサーバーのサポートを構成することによって、Lync Server 2013 展開のリバースプロキシサポートを実装できます。</span><span class="sxs-lookup"><span data-stu-id="ca861-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="ca861-144">Exchange ユニファイドメッセージング (UM) コンポーネントまたは SharePoint コンポーネントを任意の SharePoint Server の役割と併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="ca861-144">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

