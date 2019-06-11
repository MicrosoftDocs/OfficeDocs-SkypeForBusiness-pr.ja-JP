---
title: 'Lync Server 2013: 常設チャットサーバーの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b84f1a2932b76c8030c907463e8f0f2e93bedda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="40037-102">Lync Server 2013 の常設チャットサーバーの技術要件</span><span class="sxs-lookup"><span data-stu-id="40037-102">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40037-103">_**最終更新日:** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="40037-103">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="40037-104">常設チャットサーバーをホストする各コンピューターは、次のコンポーネントを使用して、既存の Lync Server 2013 トポロジにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="40037-104">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="40037-105">**Lync Server 2013、フロントエンドサーバー。** フロントエンドサーバーは、セッション開始プロトコル (SIP) ルーティングの基盤です。これにより、常設チャットサーバーを実行しているコンピューターと常設チャット機能を実行しているコンピューター間の通信が可能になります。</span><span class="sxs-lookup"><span data-stu-id="40037-105">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="40037-106">常設チャットサーバーの展開を開始する前に、組織に合わせて、lync server 2013、Standard Edition、または lync server のフロントエンドプールと lync server が実行されているその他の内部コンピューターの展開を確認します。</span><span class="sxs-lookup"><span data-stu-id="40037-106">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="40037-107">以下のセクションでは、常設チャットサーバーと永続的なチャットデータを格納するデータベースの固有の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="40037-107">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="40037-108">常設チャットサーバーの要件</span><span class="sxs-lookup"><span data-stu-id="40037-108">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="40037-109">Lync Server および最新バージョンの常設チャットサーバーの展開に推奨されるハードウェアの詳細については、サポートドキュメントの「 [Lync server 2013 用のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40037-109">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="40037-110">Lync Server および常設チャットサーバー向けのサーバーとツールのオペレーティングシステムサポートの詳細については、サポートドキュメントの「 [Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40037-110">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="40037-111">常設チャットサーバーの展開に必要なその他のソフトウェアの詳細については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40037-111">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="40037-112">常設チャットサーバーソフトウェアの前提条件</span><span class="sxs-lookup"><span data-stu-id="40037-112">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40037-113">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="40037-113">Software</span></span></th>
<th><span data-ttu-id="40037-114">説明</span><span class="sxs-lookup"><span data-stu-id="40037-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40037-115">メッセージキュー</span><span class="sxs-lookup"><span data-stu-id="40037-115">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="40037-116">常設チャットサーバーと常設チャットコンプライアンスサービス (展開されている場合)。</span><span class="sxs-lookup"><span data-stu-id="40037-116">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="40037-117">常設チャットサーバーのデータベース要件</span><span class="sxs-lookup"><span data-stu-id="40037-117">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="40037-118">常設チャットサーバーは、常設チャットデータベースを使って、チャット履歴、構成、ユーザープロビジョニングデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="40037-118">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="40037-119">必要に応じて、常設チャットのコンプライアンスデータベースを使ってコンプライアンスデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="40037-119">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="40037-120">常設チャットデータベース (行う) とコンプライアンスデータベース () は、SQL Server の同じインスタンスまたは別の SQL server に配置できます。</span><span class="sxs-lookup"><span data-stu-id="40037-120">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="40037-121">データベース サーバー プラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認した後、必要なソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="40037-121">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="40037-122">常設チャットデータベースサーバーのサーバープラットフォームには、Lync Server バックエンドデータベースサーバーと同じハードウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="40037-122">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="40037-123">詳細については、サポートドキュメントの「 [Lync server 2013 用のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40037-123">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="40037-124">次のどちらかのソフトウェア アプリケーションがデータベース サーバーにインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="40037-124">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="40037-125">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="40037-125">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="40037-126">Microsoft SQL Server 2012 のインストール方法の詳細については、「SQL Server 2012 を[http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)インストールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40037-126">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="40037-127">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="40037-127">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="40037-128">Microsoft SQL Server 2008 R2 のインストール方法の詳細については、「SQL Server のインストール (SQL Server 2008 R2 [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40037-128">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="40037-129">常設チャットサーバー証明書の要件</span><span class="sxs-lookup"><span data-stu-id="40037-129">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="40037-130">証明書の取得、SQL Server データベースの作成、ファイルストアの作成の詳細については、「展開ドキュメントに[Lync Server 2013 を展開](lync-server-2013-deploying-lync-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40037-130">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

