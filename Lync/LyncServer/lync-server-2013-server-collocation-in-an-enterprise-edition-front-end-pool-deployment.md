---
title: Lync Server 2013 の Enterprise Edition フロント エンド プール展開でのサーバーの併置
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
ms.openlocfilehash: ad549c614fc14b74126a7e81e0223ad584e68141
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="c3b86-102">Lync Server 2013 の Enterprise Edition フロント エンド プール展開でのサーバーの併置</span><span class="sxs-lookup"><span data-stu-id="c3b86-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3b86-103">_**最終更新日:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="c3b86-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="c3b86-104">このセクションでは、Lync Server 2013 フロントエンドプールの展開で検索できるサーバーの役割、データベース、およびファイル共有について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3b86-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="c3b86-105">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="c3b86-105">Server Roles</span></span>

<span data-ttu-id="c3b86-106">Lync Server 2013 では、A/V 会議サービス、仲介サービス、監視、およびアーカイブはフロントエンドサーバーに併置されますが、有効にするには追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="c3b86-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="c3b86-107">フロントエンドサーバーで仲介サーバーを検索したくない場合は、スタンドアロンの仲介サーバーとして別のコンピューターに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="c3b86-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="c3b86-108">サーバーを使用して、信頼できるアプリケーションサーバーを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="c3b86-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="c3b86-109">次のサーバーロールはそれぞれ別のコンピューターに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b86-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="c3b86-110">ディレクター</span><span class="sxs-lookup"><span data-stu-id="c3b86-110">Director</span></span>

  - <span data-ttu-id="c3b86-111">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="c3b86-111">Edge Server</span></span>

  - <span data-ttu-id="c3b86-112">仲介サーバー (フロントエンドサーバーに併置されていない場合)</span><span class="sxs-lookup"><span data-stu-id="c3b86-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="c3b86-113">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="c3b86-113">Office Web Apps Server</span></span>

<span data-ttu-id="c3b86-114">フロントエンドサーバーで常設チャットサーバーの役割を検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="c3b86-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="c3b86-115">データベース</span><span class="sxs-lookup"><span data-stu-id="c3b86-115">Databases</span></span>

<span data-ttu-id="c3b86-116">同じデータベースサーバー上で、次の各データベースを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="c3b86-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="c3b86-117">バックエンドデータベース</span><span class="sxs-lookup"><span data-stu-id="c3b86-117">Back-end database</span></span>

  - <span data-ttu-id="c3b86-118">監視データベース</span><span class="sxs-lookup"><span data-stu-id="c3b86-118">Monitoring database</span></span>

  - <span data-ttu-id="c3b86-119">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="c3b86-119">Archiving database</span></span>

  - <span data-ttu-id="c3b86-120">常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="c3b86-120">Persistent Chat database</span></span>

  - <span data-ttu-id="c3b86-121">常設チャットのコンプライアンスデータベース</span><span class="sxs-lookup"><span data-stu-id="c3b86-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="c3b86-122">SQL Server の1つのインスタンスでこれらのデータベースのいずれかまたはすべてを検索することも、SQL Server の個別のインスタンスを使用することもできます。次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="c3b86-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="c3b86-123">SQL Server の各インスタンスには、1つのバックエンドデータベース、単一の監視データベース、単一のアーカイブデータベース、1つの常設チャットデータベース、1つの常設チャットのコンプライアンスデータベースのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c3b86-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="c3b86-124">データベースサーバーでは、複数のフロントエンドプール、1つのアーカイブ展開、および1つの監視展開をサポートすることはできませんが、データベースが SQL Server の同じインスタンスと SQL Server の別のインスタンスのどちらを使うかに関係なく、どちらか1つをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="c3b86-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="c3b86-125">このセクションの後半で説明するように、データベースとのファイル共有を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="c3b86-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c3b86-126">Lync Server 2013 では、展開内の一部またはすべてのユーザーについて、アーカイブストレージと Exchange 2013 ストレージを統合するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c3b86-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="c3b86-127">Lync Server やコンポーネントを実行しているサーバーを Exchange ストレージと同じサーバー上に展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="c3b86-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c3b86-128">データベースの collocation はサポートされていますが、データベースのサイズが急速に増大する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3b86-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="c3b86-129">たとえば、アーカイブデータベースを他のデータベースとの間で検索することを検討している場合、アーカイブデータベースに必要なディスク領域が非常に大きくなる可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c3b86-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="c3b86-130">このため、複数のデータベース、特にアーカイブデータベース、常設チャットデータベース、またはバックエンドデータベースを含む永続的なチャットのコンプライアンスデータベースを検索することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="c3b86-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="c3b86-131">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="c3b86-131">File Share</span></span>

<span data-ttu-id="c3b86-132">ファイル共有は、個別のサーバーにすることも、次のいずれか、またはすべてを同じサーバー上に置いておくこともできます。</span><span class="sxs-lookup"><span data-stu-id="c3b86-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="c3b86-133">データベースサーバー (Enterprise Edition フロントエンドプールのバックエンドサーバーを含む)</span><span class="sxs-lookup"><span data-stu-id="c3b86-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="c3b86-134">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="c3b86-134">Archiving database</span></span>

  - <span data-ttu-id="c3b86-135">監視データベース</span><span class="sxs-lookup"><span data-stu-id="c3b86-135">Monitoring database</span></span>

  - <span data-ttu-id="c3b86-136">常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="c3b86-136">Persistent Chat database</span></span>

  - <span data-ttu-id="c3b86-137">常設チャットのコンプライアンスデータベース</span><span class="sxs-lookup"><span data-stu-id="c3b86-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="c3b86-138">1つのファイル共有は、複数のフロントエンドプール、標準エディションサーバー (すべて同じサイト内) に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3b86-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c3b86-139">Lync Server 2013 の [監視とアーカイブ] では、Lync Server のファイル共有をフロントエンドサーバーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="c3b86-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="c3b86-140">その他のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="c3b86-140">Other Components</span></span>

<span data-ttu-id="c3b86-141">Lync server 2013 コンポーネントではないリバースプロキシサーバーを検索することはできませんが、Lync Server 2013 サーバーの役割を持つフェデレーションユーザーの web コンテンツの共有をサポートする場合は、展開で必要になります。</span><span class="sxs-lookup"><span data-stu-id="c3b86-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="c3b86-142">ただし、他のアプリケーションで使用されている既存のリバースプロキシサーバーのサポートを構成することによって、Lync Server 2013 の展開にリバースプロキシサポートを実装することはできます。</span><span class="sxs-lookup"><span data-stu-id="c3b86-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="c3b86-143">任意の SharePoint Server の役割で Exchange ユニファイドメッセージング (UM) コンポーネントまたは SharePoint コンポーネントを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="c3b86-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

