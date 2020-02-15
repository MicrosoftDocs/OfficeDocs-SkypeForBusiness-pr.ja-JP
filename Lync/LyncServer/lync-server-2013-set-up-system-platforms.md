---
title: 'Lync Server 2013: システムプラットフォームのセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda0cebf15cb1d575978eb0984dc7d9b5a53a30f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="6403d-102">Lync Server 2013 でのシステムプラットフォームのセットアップ</span><span class="sxs-lookup"><span data-stu-id="6403d-102">Set up system platforms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6403d-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="6403d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6403d-104">常設チャットサーバーの展開を開始する前に、サーバーのシステム要件を満たすハードウェアに、必要なオペレーティングシステムをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6403d-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="6403d-105">Lync Server 2013、データベースサーバー、およびファイルサーバーを実行しているサーバーでサポートされているハードウェアの詳細については、「サポート」のドキュメントの「supported [hardware For Lync Server 2013](lync-server-2013-supported-hardware.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6403d-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="6403d-106">サポートされているオペレーティングシステムとデータベースソフトウェアの詳細については、「サポート」のドキュメントの「 [server software and infrastructure support In Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6403d-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="6403d-107">Windows 更新の要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 の追加サーバーサポートと要件](lync-server-2013-additional-server-support-and-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6403d-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="6403d-108">常設チャットサーバーのフロントエンドサーバー **PersistentChatService**は、Lync Server 2013 Enterprise Edition プール内の1台以上のスタンドアロンコンピューターに展開できます。</span><span class="sxs-lookup"><span data-stu-id="6403d-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="6403d-109">Lync Server Enterprise Edition フロントエンドサーバーに併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="6403d-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="6403d-110">常設チャットサーバーは、他の Lync Server の役割と同様に、ブートストラップによって展開できます。</span><span class="sxs-lookup"><span data-stu-id="6403d-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="6403d-111">**ファイルのアップロード/ダウンロード用の常設チャット Web サービス**、および**チャットルーム管理用の常設チャット web**サービスは、Lync Server 2013 フロントエンドサーバーに展開される web コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="6403d-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="6403d-112">1台の常設チャットサーバーフロントエンドサーバーでは、2万アクティブユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="6403d-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="6403d-113">最大4つのアクティブなフロントエンドを持つ常設チャットサーバープールを使用して、合計8万の同時ユーザーをサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="6403d-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="6403d-114">常設チャットのバックエンドサーバー **PersistentChatStore**は、チャットルームとカテゴリを格納します。</span><span class="sxs-lookup"><span data-stu-id="6403d-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="6403d-115">**PersistentChatStore**は、Enterprise Edition プールの専用の SQL Server バックエンドサーバーにインストールすることをお勧めします。Lync Server 2013 バックエンドサーバーと**PersistentChatStore**を同じ SQL Server インスタンスに併置するのは、併置をサポートするものです。</span><span class="sxs-lookup"><span data-stu-id="6403d-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="6403d-116">組織でコンプライアンスのサポートが必要な場合は、トポロジビルダーを使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="6403d-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="6403d-117">常設チャットサーバーのコンプライアンスサービスは、常設チャットサーバーのフロントエンドサーバーと同じコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6403d-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="6403d-118">コンプライアンスには別のデータベースが必要です。</span><span class="sxs-lookup"><span data-stu-id="6403d-118">A separate database is required for compliance.</span></span> <span data-ttu-id="6403d-119">常設チャットサーバーのコンプライアンス要件の詳細については、「計画」のドキュメントの「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6403d-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="6403d-120">少なくとも、各トポロジには、Lync Server 2013 がインストールされたサーバーと SQL Server データベースソフトウェアがインストールされたサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="6403d-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="6403d-121">トポロジビルダーは、複数の常設チャットサーバープールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6403d-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="6403d-122">展開のドキュメントで[Lync Server 2013](lync-server-2013-deploying-lync-server.md)を展開する場合と同じように、複数の常設チャットサーバープールを展開する場合と同じ展開手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6403d-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="6403d-123">また、Lync Server 2013 Standard Edition を使用して常設チャットサーバーを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="6403d-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="6403d-124">この場合、 **PersistentChatService**フロントエンドサーバーは Standard Edition サーバーに併置されており、ローカルの SQL Server Express インスタンスに**PersistentChatStore**バックエンドサーバーを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="6403d-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6403d-125">高可用性のために常設チャット&nbsp;サーバー Standard Edition はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6403d-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="6403d-126">パフォーマンスとスケーラビリティ には制限があります。</span><span class="sxs-lookup"><span data-stu-id="6403d-126">Performance and scale will be limited.</span></span> <span data-ttu-id="6403d-127">さらに、新しい常設チャットサーバー&nbsp;Standard Edition サーバーの展開のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6403d-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="6403d-128">Lync server 2013&nbsp;常設チャットサーバー&nbsp;Standard Edition への lync server 2010 のアップグレードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6403d-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6403d-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="6403d-129">See Also</span></span>


[<span data-ttu-id="6403d-130">Lync Server 2013 におけるその他のサーバーのサポートおよび要件</span><span class="sxs-lookup"><span data-stu-id="6403d-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="6403d-131">Lync Server 2013 でサポートされているハードウェア</span><span class="sxs-lookup"><span data-stu-id="6403d-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="6403d-132">Lync Server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート</span><span class="sxs-lookup"><span data-stu-id="6403d-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="6403d-133">Lync Server 2013 での常設チャットサーバーの計画</span><span class="sxs-lookup"><span data-stu-id="6403d-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="6403d-134">Lync Server 2013 の展開 </span><span class="sxs-lookup"><span data-stu-id="6403d-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

