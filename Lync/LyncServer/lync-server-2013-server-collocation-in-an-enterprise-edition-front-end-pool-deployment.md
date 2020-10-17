---
title: Enterprise Edition フロントエンドプール展開における Lync Server 2013 サーバーの併置
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
ms.openlocfilehash: 0162a4338a1504ed425015e5b9391fca9903d4ab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510284"
---
# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="bb420-102">Lync Server 2013 の Enterprise Edition フロントエンドプール展開でのサーバーの併置</span><span class="sxs-lookup"><span data-stu-id="bb420-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb420-103">_**トピックの最終更新日:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="bb420-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="bb420-104">このセクションでは、Lync Server 2013 のフロントエンドプール展開で併置できるサーバーの役割、データベース、およびファイル共有について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb420-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="bb420-105">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="bb420-105">Server Roles</span></span>

<span data-ttu-id="bb420-106">Lync Server 2013 では、音声ビデオ会議サービス、仲介サービス、監視、およびアーカイブはフロントエンドサーバーに併置されていますが、これを有効にするには追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb420-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="bb420-107">仲介サーバーは、フロントエンド サーバーと併置しない場合、スタンドアロンの仲介サーバーとして別のコンピューター上に展開できます。</span><span class="sxs-lookup"><span data-stu-id="bb420-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="bb420-108">信頼されたアプリケーション サーバーは、フロントエンド サーバーと併置できます。</span><span class="sxs-lookup"><span data-stu-id="bb420-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="bb420-109">次のサーバーの役割は、それぞれ別のコンピューターに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb420-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="bb420-110">ディレクター</span><span class="sxs-lookup"><span data-stu-id="bb420-110">Director</span></span>

  - <span data-ttu-id="bb420-111">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="bb420-111">Edge Server</span></span>

  - <span data-ttu-id="bb420-112">仲介サーバー (フロントエンド サーバーと併置しない場合)</span><span class="sxs-lookup"><span data-stu-id="bb420-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="bb420-113">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="bb420-113">Office Web Apps Server</span></span>

<span data-ttu-id="bb420-114">常設チャットサーバーの役割をフロントエンドサーバーと併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb420-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="bb420-115">Databases</span><span class="sxs-lookup"><span data-stu-id="bb420-115">Databases</span></span>

<span data-ttu-id="bb420-116">次のそれぞれのデータベースは、同じデータベース サーバーに併置できます。</span><span class="sxs-lookup"><span data-stu-id="bb420-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="bb420-117">バック エンド データベース</span><span class="sxs-lookup"><span data-stu-id="bb420-117">Back-end database</span></span>

  - <span data-ttu-id="bb420-118">監視データベース</span><span class="sxs-lookup"><span data-stu-id="bb420-118">Monitoring database</span></span>

  - <span data-ttu-id="bb420-119">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="bb420-119">Archiving database</span></span>

  - <span data-ttu-id="bb420-120">常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="bb420-120">Persistent Chat database</span></span>

  - <span data-ttu-id="bb420-121">常設チャットコンプライアンスデータベース</span><span class="sxs-lookup"><span data-stu-id="bb420-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="bb420-122">これらのデータベースのいずれかまたはすべてを1つの SQL Server インスタンスで併置するか、または SQL Server の個別のインスタンスを使用することができます。これには次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="bb420-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="bb420-123">SQL Server の各インスタンスには、1つのバックエンドデータベース、単一の監視データベース、1つのアーカイブデータベース、1つの常設チャットデータベース、および1つの常設チャットコンプライアンスデータベースのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bb420-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="bb420-124">データベースサーバーは、複数のフロントエンドプール、1つのアーカイブ展開、および1つの監視展開をサポートできませんが、データベースが SQL Server の同じインスタンスを使用するか、SQL Server の別のインスタンスを使用するかに関係なく、それぞれの1つをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="bb420-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="bb420-125">このセクションで後述するように、ファイル共有をデータベースと併置できます。</span><span class="sxs-lookup"><span data-stu-id="bb420-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bb420-126">Lync Server 2013 では、展開内の一部またはすべてのユーザーに対してアーカイブストレージを Exchange 2013 ストレージと統合するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="bb420-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="bb420-127">Exchange ストレージと同じサーバーに Lync Server またはコンポーネントを実行しているサーバーを展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb420-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bb420-128">データベースの併置がサポートされていても、データベースのサイズはすぐに大きくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="bb420-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="bb420-129">たとえば、アーカイブ データベースと他のデータベースを併置することを考慮するときには、数名以上のユーザーのメッセージをアーカイブすると、アーカイブ データベースが必要とするディスク容量が非常に大きくなる可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bb420-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="bb420-130">このため、複数のデータベース (特に、アーカイブデータベース、常設チャットデータベース、または常設チャットコンプライアンスデータベースとバックエンドデータベース) を併置することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="bb420-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="bb420-131">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="bb420-131">File Share</span></span>

<span data-ttu-id="bb420-132">ファイル共有は、別個のサーバーを使用することも、次のいくつか、またはすべてと同じサーバーに併置することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb420-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="bb420-133">データベース サーバー (Enterprise Edition フロントエンド プールのバック エンド サーバーを含む)</span><span class="sxs-lookup"><span data-stu-id="bb420-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="bb420-134">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="bb420-134">Archiving database</span></span>

  - <span data-ttu-id="bb420-135">監視データベース</span><span class="sxs-lookup"><span data-stu-id="bb420-135">Monitoring database</span></span>

  - <span data-ttu-id="bb420-136">常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="bb420-136">Persistent Chat database</span></span>

  - <span data-ttu-id="bb420-137">常設チャットコンプライアンスデータベース</span><span class="sxs-lookup"><span data-stu-id="bb420-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="bb420-138">単一のファイル共有を複数のフロントエンド プール、および複数の Standard Edition サーバーで使用できます (これらのプールやサーバーはすべて同じサイトに存在)。</span><span class="sxs-lookup"><span data-stu-id="bb420-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bb420-139">Lync Server 2013 の監視およびアーカイブでは、Lync Server のファイル共有をフロントエンドサーバーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="bb420-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="bb420-140">その他のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="bb420-140">Other Components</span></span>

<span data-ttu-id="bb420-141">Lync server 2013 コンポーネントではないリバースプロキシサーバーを併置することはできませんが、任意の Lync Server 2013 サーバーの役割を持つフェデレーションユーザーに対して web コンテンツの共有をサポートする必要がある場合は、展開で必要になります。</span><span class="sxs-lookup"><span data-stu-id="bb420-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="bb420-142">ただし、他のアプリケーションで使用されている組織内の既存のリバースプロキシサーバーのサポートを構成することによって、Lync Server 2013 展開のリバースプロキシサポートを実装できます。</span><span class="sxs-lookup"><span data-stu-id="bb420-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="bb420-143">Exchange ユニファイドメッセージング (UM) コンポーネントまたは SharePoint コンポーネントを任意の SharePoint Server の役割と併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb420-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

