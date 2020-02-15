---
title: 'Lync Server 2013: 常設チャットサーバーの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba8e3e02efeddc1229d3616c0cdcaf4ca241bf24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42024408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ceec6-102">Lync Server 2013 の常設チャットサーバーの技術要件</span><span class="sxs-lookup"><span data-stu-id="ceec6-102">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ceec6-103">_**トピックの最終更新日:** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="ceec6-103">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="ceec6-104">常設チャットサーバーをホストする各コンピューターは、以下のコンポーネントを使用して、既存の Lync Server 2013 トポロジにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceec6-104">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="ceec6-105">**Lync Server 2013、フロントエンドサーバー。** フロントエンドサーバーは、セッション開始プロトコル (SIP) ルーティングの基盤であり、常設チャットサーバーと常設チャット機能を実行しているコンピューター間の通信を可能にします。</span><span class="sxs-lookup"><span data-stu-id="ceec6-105">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="ceec6-106">常設チャットサーバーの展開を開始する前に、組織に合わせて lync server 2013、Standard Edition、lync Server フロントエンドプール、および Lync server を実行している他の内部コンピューターの展開を確認します。</span><span class="sxs-lookup"><span data-stu-id="ceec6-106">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="ceec6-107">次のセクションでは、常設チャットサーバーおよび常設チャットデータを格納するデータベースの特定の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="ceec6-107">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="ceec6-108">常設チャットサーバーの要件</span><span class="sxs-lookup"><span data-stu-id="ceec6-108">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="ceec6-109">Lync Server および常設チャットサーバーの最新バージョンを展開するために推奨されるハードウェアの詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceec6-109">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ceec6-110">Lync Server および常設チャットサーバーのサーバーおよびツールのオペレーティングシステムのサポートの詳細については、「サポート」のドキュメントの「 [Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceec6-110">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ceec6-111">常設チャットサーバーの展開に必要な追加ソフトウェアの詳細については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceec6-111">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="ceec6-112">常設チャットサーバーソフトウェアの前提条件</span><span class="sxs-lookup"><span data-stu-id="ceec6-112">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ceec6-113">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="ceec6-113">Software</span></span></th>
<th><span data-ttu-id="ceec6-114">説明</span><span class="sxs-lookup"><span data-stu-id="ceec6-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ceec6-115">メッセージ キュー</span><span class="sxs-lookup"><span data-stu-id="ceec6-115">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="ceec6-116">常設チャットサーバーおよび常設チャットコンプライアンスサービス (展開されている場合) によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="ceec6-116">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="ceec6-117">常設チャットサーバーのデータベースの要件</span><span class="sxs-lookup"><span data-stu-id="ceec6-117">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="ceec6-118">常設チャットサーバーは、常設チャットデータベースを使用して、チャットの履歴、構成、およびユーザープロビジョニングデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="ceec6-118">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="ceec6-119">必要に応じて、常設チャットコンプライアンスデータベースを使用してコンプライアンスデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="ceec6-119">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ceec6-120">常設チャットデータベース (mgc) とコンプライアンスデータベース (メンバーサーバー) は、SQL Server の同じインスタンスまたは別の SQL Server に配置できます。</span><span class="sxs-lookup"><span data-stu-id="ceec6-120">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="ceec6-121">データベースサーバープラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認してから、前提条件となるソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ceec6-121">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="ceec6-122">常設チャットデータベースサーバーのサーバープラットフォームには、Lync Server バックエンドデータベースサーバーと同じハードウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="ceec6-122">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="ceec6-123">詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceec6-123">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ceec6-124">データベースサーバーで、次のいずれかのソフトウェアアプリケーションがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ceec6-124">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="ceec6-125">Microsoft SQL Server 2012。</span><span class="sxs-lookup"><span data-stu-id="ceec6-125">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="ceec6-126">Microsoft SQL Server 2012 をインストールする方法の詳細については、「SQL Server 2012 [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)をインストールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceec6-126">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="ceec6-127">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ceec6-127">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="ceec6-128">Microsoft SQL Server 2008 R2 のインストール方法の詳細については、「」の「SQL Server のインストール (SQL [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)Server 2008 R2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceec6-128">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="ceec6-129">常設チャットサーバーの証明書の要件</span><span class="sxs-lookup"><span data-stu-id="ceec6-129">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="ceec6-130">証明書の取得、SQL Server データベースの作成、およびファイルストアの作成の詳細については、「展開」のドキュメントの「[展開 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceec6-130">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

