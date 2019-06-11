---
title: 'Lync Server 2013: システム プラットフォームを設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 317bfe0efed0417d49cc59dc8f6e7ad3bcca7d7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="bc6bc-102">Lync Server 2013 でシステム プラットフォームを設定する</span><span class="sxs-lookup"><span data-stu-id="bc6bc-102">Set up system platforms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc6bc-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="bc6bc-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="bc6bc-104">常設チャットサーバーの展開を開始する前に、サーバー上のシステム要件を満たすハードウェアに必要なオペレーティングシステムをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="bc6bc-105">Lync Server 2013、データベースサーバー、およびファイルサーバーを実行しているサーバーでサポートされているハードウェアの詳細については、サポートされているドキュメントで「 [Lync server 2013 でサポートされているハードウェア](lync-server-2013-supported-hardware.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="bc6bc-106">サポートされているオペレーティングシステムとデータベースソフトウェアの詳細については、サポートドキュメントの「 [Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート](lync-server-2013-server-software-and-infrastructure-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="bc6bc-107">Windows の更新の要件の詳細については、サポートドキュメントの「 [Lync server 2013 のその他のサーバーのサポートと要件](lync-server-2013-additional-server-support-and-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="bc6bc-108">常設チャットサーバーのフロントエンドサーバーである**PersistentChatService**は、Lync Server 2013 Enterprise Edition プールの1つ以上のスタンドアロンコンピューターに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="bc6bc-109">Lync Server Enterprise Edition のフロントエンドサーバーには、それらを併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="bc6bc-110">常設チャットサーバーは、他の Lync Server の役割と同じように、ブートストラップによって展開できます。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="bc6bc-111">**ファイルのアップロード/ダウンロード用の常設チャット Web サービス**と**チャットルーム管理用の常設チャット web サービス**は、Lync Server 2013 フロントエンドサーバーに展開されている web コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="bc6bc-112">1つの常設チャットサーバーフロントエンドサーバーは、2万アクティブユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="bc6bc-113">最大4つのアクティブなフロントエンドの常設チャットサーバープールで、合計8万人の同時ユーザーをサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="bc6bc-114">常設チャットバックエンドサーバー **PersistentChatStore**は、チャットルームとカテゴリを保存します。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="bc6bc-115">**PersistentChatStore**は、Enterprise Edition プールの専用 SQL Server バックエンドサーバーにインストールすることをお勧めします。ただし、同じ SQL Server インスタンス上での Lync Server 2013 バックエンドサーバーと**PersistentChatStore**の検索はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="bc6bc-116">組織でコンプライアンスのサポートが必要な場合は、トポロジビルダーを使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="bc6bc-117">常設チャット Server コンプライアンスサービスは、常設チャットサーバーフロントエンドサーバーと同じコンピューターにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="bc6bc-118">コンプライアンスには、別のデータベースが必要です。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-118">A separate database is required for compliance.</span></span> <span data-ttu-id="bc6bc-119">常設チャットサーバーのコンプライアンス要件の詳細については、計画ドキュメントの「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="bc6bc-120">少なくとも、各トポロジには、Lync Server 2013 がインストールされているサーバーと SQL Server データベースソフトウェアがインストールされたサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="bc6bc-121">Topology Builder は、複数の常設チャットサーバープールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="bc6bc-122">展開ドキュメントに[Lync Server 2013 を展開](lync-server-2013-deploying-lync-server.md)する場合と同様に、複数の常設チャットサーバープールを展開する場合と同じ展開手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="bc6bc-123">また、Lync Server 2013 Standard Edition で常設チャットサーバーを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="bc6bc-124">この場合、 **PersistentChatService**フロントエンドサーバーは Standard Edition サーバー上に配置されているため、 **PersistentChatStore**バックエンドサーバーをローカルの SQL Server Express インスタンスに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bc6bc-125">高可用性を実現する常設 Chat&nbsp;Server 標準エディションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="bc6bc-126">パフォーマンスとスケールは制限されます。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-126">Performance and scale will be limited.</span></span> <span data-ttu-id="bc6bc-127">さらに、新しい常設チャット Server&nbsp;Standard Edition server の展開のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="bc6bc-128">Lync server 2010、グループチャットサーバーを Lync Server 2013&nbsp;常設 Chat Server&nbsp;Standard Edition にアップグレードすることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bc6bc-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc6bc-129">See Also</span></span>


[<span data-ttu-id="bc6bc-130">Lync Server 2013 の追加サーバー サポートおよび要件</span><span class="sxs-lookup"><span data-stu-id="bc6bc-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="bc6bc-131">Lync Server 2013 でサポートされるハードウェア</span><span class="sxs-lookup"><span data-stu-id="bc6bc-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="bc6bc-132">Lync Server 2013 でのサーバーのソフトウェアおよびインフラストラクチャ サポート</span><span class="sxs-lookup"><span data-stu-id="bc6bc-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="bc6bc-133">Lync Server 2013 での常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="bc6bc-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="bc6bc-134">Lync Server 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="bc6bc-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

