---
title: Lync Server 2013 でサポートされているトポロジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4754881d2ed3205c4f06d5468001c6e45880278c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523964"
---
# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="869bf-102">Lync Server 2013 でサポートされているトポロジ</span><span class="sxs-lookup"><span data-stu-id="869bf-102">Supported topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="869bf-103">_**トピックの最終更新日:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="869bf-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="869bf-104">Lync Server 2013 では、組織内のオンプレミスのサイトの展開と、ハイブリッド展開として知られている Lync Online 展開によるオンプレミス展開の統合をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="869bf-104">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="869bf-105">ハイブリッド展開では、あるユーザーは内部設置型に所属し、あるユーザーはオンラインに所属します。</span><span class="sxs-lookup"><span data-stu-id="869bf-105">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="869bf-106">オンプレミス展開の場合、Lync Server 2013 では、高可用性および場所の要件を満たすように拡張できる1つ以上のサイトの展開がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="869bf-106">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="869bf-107">これらのサイトとそのコンポーネントは、組織のアクセスおよび復元の要件を満たすように構成できます。</span><span class="sxs-lookup"><span data-stu-id="869bf-107">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="869bf-108">Lync Server 2013 の社内展開は、次の内容で構成されます。</span><span class="sxs-lookup"><span data-stu-id="869bf-108">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="869bf-p103">展開には、1 つ以上の中央サイト (データ センターとも呼ばれます) を含める必要があります。各中央サイトには、1 つ以上の Enterprise Edition フロントエンド プールまたは 1 つの Standard Edition サーバーが必要です。これらは、次で構成されます。</span><span class="sxs-lookup"><span data-stu-id="869bf-p103">Your deployment must include at least one central site (also known as a data center). Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server. These consist of the following:</span></span>
    
      - <span data-ttu-id="869bf-112">Enterprise Edition フロントエンドプール。これは、1つまたは複数のフロントエンドサーバー (通常は、少なくとも2台のフロントエンドサーバーがスケーラビリティを備えている) と、個別のバックエンドサーバーで構成されます。</span><span class="sxs-lookup"><span data-stu-id="869bf-112">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="869bf-113">フロントエンドプールには、最大12台のフロントエンドサーバーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="869bf-113">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="869bf-114">複数のフロントエンドサーバーには負荷分散が必要です。</span><span class="sxs-lookup"><span data-stu-id="869bf-114">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="869bf-115">SIP トラフィックでは、DNS 負荷分散を使用することをお勧めしますが、ハードウェア負荷分散もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="869bf-115">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="869bf-116">SIP トラフィックに DNS 負荷分散を使用する場合でも、HTTP トラフィック用のハードウェアロードバランサーが必要です。</span><span class="sxs-lookup"><span data-stu-id="869bf-116">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="869bf-117">データベースの高可用性を実現するため、SQL Server のミラーリングをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="869bf-117">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="869bf-118">バックエンドデータベースには個別のインスタンスが必要ですが、アーカイブデータベース、監視データベース、常設チャットデータベース、および常設チャットのコンプライアンスデータベースを併置することができます。</span><span class="sxs-lookup"><span data-stu-id="869bf-118">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="869bf-119">Lync Server 2013 では、展開内のファイル共有に対して共有クラスターの使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="869bf-119">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="869bf-120">データベース記憶域の要件の詳細については、「 [Lync Server 2013 のデータベースソフトウェアサポート](lync-server-2013-database-software-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="869bf-120">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="869bf-121">ファイル記憶域の要件の詳細については、「 [Lync Server 2013 のファイル記憶域サポート](lync-server-2013-file-storage-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="869bf-121">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="869bf-122">Lync Server データベースを併置する場合は、可用性とパフォーマンスに影響する可能性のあるすべての要因を評価することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="869bf-122">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="869bf-123">フェールオーバー機能を検証する場合は、すべてのフェールオーバー シナリオをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="869bf-123">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="869bf-124">併置する SQL Server Express データベースを含む Standard Edition サーバー。</span><span class="sxs-lookup"><span data-stu-id="869bf-124">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="869bf-125">展開には、中央サイトに関連付けられた 1 つ以上のブランチ サイトも含むことができます。</span><span class="sxs-lookup"><span data-stu-id="869bf-125">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="869bf-126">このセクションでは、Lync Server 2013 の展開のサイトとコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="869bf-126">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="869bf-127">Lync server 2013 のサイト、トポロジ、およびコンポーネントの計画の詳細については、「計画」のドキュメントの「lync server [2013 を計画する前に知っておく必要のあるトポロジの基礎](lync-server-2013-topology-basics-you-must-know-before-planning.md) 」および「 [lync Server 2013 の参照トポロジ](lync-server-2013-reference-topologies.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="869bf-127">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="869bf-128">以前のリリースのコンポーネントの統合の詳細については、「 [Lync Server 2013 でのサポートされる移行パスと共存のシナリオ](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="869bf-128">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="869bf-129">拡張されたプールは、フロントエンド、エッジ、仲介、およびディレクターサーバーの役割ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="869bf-129">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="869bf-130">中央サイトのトポロジとコンポーネント (内部設置型)</span><span class="sxs-lookup"><span data-stu-id="869bf-130">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="869bf-131">中央サイト トポロジには、1 つのフロントエンド プールまたは Standard Edition サーバーを含む必要がありますが、各中央サイトは次のコンポーネントも含むことができます。</span><span class="sxs-lookup"><span data-stu-id="869bf-131">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="869bf-p107">複数のフロントエンド プール。同じドメインに所属することも別のドメインに所属することもできます。ただし、1 つのフロントエンド プールに含まれるすべてのフロントエンド サーバーおよびそのプールのバック エンド サーバーは、同じドメインに所属する必要があります。</span><span class="sxs-lookup"><span data-stu-id="869bf-p107">Multiple Front End pools, which can be in the same domain or different domains. However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="869bf-134">複数の Standard Edition サーバー。</span><span class="sxs-lookup"><span data-stu-id="869bf-134">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="869bf-135">Office Web Apps サーバー。 Lync Server 2013 の Office Web アプリケーションで使用され、Microsoft PowerPoint プレゼンテーションの共有とレンダリングを処理します。</span><span class="sxs-lookup"><span data-stu-id="869bf-135">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="869bf-136">境界ネットワークのエッジサーバーまたはエッジプール。展開でフェデレーションパートナーのサポートが必要な場合、パブリック IM 接続、拡張可能なメッセージングとプレゼンスプロトコル (XMPP) ゲートウェイ、リモートユーザーアクセス、会議での匿名ユーザーの参加、または Exchange ユニファイドメッセージング (UM) をサポートする場合。</span><span class="sxs-lookup"><span data-stu-id="869bf-136">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="869bf-137">他のサーバーの役割をエッジサーバーと併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="869bf-137">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="869bf-138">必要な場合は DNS 負荷分散を推奨しますが、ハードウェア負荷分散もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="869bf-138">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="869bf-139">内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="869bf-139">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="869bf-140">1 つのいエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="869bf-140">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="869bf-141">負荷分散の要件とサポートの詳細については、「展開」のドキュメントの「計画」のドキュメントの「 [Lync server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md) 」および「展開」のドキュメントの「planning for external user [Access in lync server 2013](lync-server-2013-deploying-external-user-access.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="869bf-141">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="869bf-142">中央サイトのフロントエンドプールでエンタープライズ Voip またはダイヤルイン会議をサポートする必要がある場合は、仲介サーバーまたはプール。</span><span class="sxs-lookup"><span data-stu-id="869bf-142">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="869bf-143">エンタープライズ Voip サポートの展開方法によっては、仲介サーバーをフロントエンドプール (既定) に併置したり、スタンドアロンの仲介サーバーまたはプールを展開したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="869bf-143">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="869bf-144">DNS、ハードウェア、またはアプリケーションの負荷分散 (適切な場合) を使用して、PSTN ゲートウェイ、ip-pbx、または SIP トランクセッションボーダーコントロール (SBC) を含む仲介サーバープールのゲートウェイピアからのトラフィックを分散させることができます。適切な仲介サーバートポロジの計画の詳細については、「計画」のドキュメントの「 [Lync server 2013 の仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="869bf-144">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="869bf-145">常設チャットサーバー (ユーザーが長期間にわたって保持されるマルチパーティの会話に参加できるようにする場合)。</span><span class="sxs-lookup"><span data-stu-id="869bf-145">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="869bf-146">容量と信頼性を向上させるために、常設チャットサーバーを実行している複数のコンピューターをトポロジに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="869bf-146">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="869bf-147">エンタープライズプール内の他のサーバーの役割と常設チャットサーバーを併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="869bf-147">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="869bf-148">ただし、常設チャットサーバーは、Standard Edition サーバーで併置することができます。</span><span class="sxs-lookup"><span data-stu-id="869bf-148">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="869bf-149">常設チャットでは、データベースが必要であり、常設チャットのコンプライアンスデータベースを実装している場合は、アーカイブデータベース、監視データベース、または Enterprise Edition フロントエンドプールのバックエンドサーバーにデータベースを併置することができます。</span><span class="sxs-lookup"><span data-stu-id="869bf-149">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="869bf-150">適切な常設チャットサーバートポロジの計画の詳細については、「計画」のドキュメントの「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="869bf-150">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="869bf-151">監視 (audio/video Quality of Experience (QoE) のデータ収集および展開内の音声ビデオ会議のための通話詳細記録 (CDR) をサポートする場合)。</span><span class="sxs-lookup"><span data-stu-id="869bf-151">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="869bf-152">必要に応じて、Microsoft System Center Operations Manager (旧称 Microsoft Operations Manager) をインストールすることができます。これは、監視 CDR と QoE データを使用して、通話の信頼性とメディア品質の状態を示すほぼリアルタイム通知を生成します。</span><span class="sxs-lookup"><span data-stu-id="869bf-152">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="869bf-153">展開されている場合、監視はフロントエンドサーバーまたは Standard Edition サーバーに併置されます。</span><span class="sxs-lookup"><span data-stu-id="869bf-153">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="869bf-154">監視にはデータベースが必要ですが、データベースはアーカイブデータベース、常設チャットデータベース、常設チャットコンプライアンスデータベース、または Enterprise Edition フロントエンドプールのバックエンドサーバーに併置できます。</span><span class="sxs-lookup"><span data-stu-id="869bf-154">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="869bf-155">アーカイブ (コンプライアンス上の理由で) IM 通信と会議コンテンツをアーカイブする場合は、[アーカイブ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="869bf-155">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="869bf-156">展開した場合、アーカイブはフロントエンドサーバーまたは Standard Edition サーバーに併置されます。</span><span class="sxs-lookup"><span data-stu-id="869bf-156">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="869bf-157">アーカイブ記憶域には、アーカイブデータベースを展開するか、Exchange 2013 ストレージと統合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="869bf-157">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="869bf-158">*混在モード*と呼ばれる両方を使用する場合、exchange 2013 ストレージを使用して、exchange 2013 に所属しているユーザーのアーカイブデータを保存し、アーカイブデータベースを使用して、展開内の他のすべてのユーザーのデータをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="869bf-158">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="869bf-159">アーカイブデータベースが必要な場合は、データベースを監視データベース、常設チャットデータベース、常設チャットコンプライアンスデータベース、またはフロントエンドプールのバックエンドサーバーに併置できます。</span><span class="sxs-lookup"><span data-stu-id="869bf-159">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="869bf-160">適切なアーカイブトポロジの計画の詳細については、「計画」のドキュメントの「 [planning For アーカイビング In Lync Server 2013](lync-server-2013-planning-for-archiving.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="869bf-160">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="869bf-161">ディレクターまたはディレクタープール。 Lync Server 2013 ユーザー要求の復元とリダイレクトをユーザーのホームプールに容易にするには、Enterprise Edition フロントエンドプールまたは Standard Edition サーバーのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="869bf-161">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="869bf-162">外部ユーザーアクセスをサポートする各中央サイトにディレクターまたはディレクタープールを展開すること、または1つまたは複数のフロントエンドプールを展開する各中央サイトにディレクタープールを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="869bf-162">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="869bf-163">各ディレクタープールには、最大10個のディレクターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="869bf-163">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="869bf-164">ディレクターを他のサーバーの役割と併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="869bf-164">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="869bf-165">適切なディレクタートポロジの計画の詳細については、「計画」のドキュメントの「 [Lync Server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="869bf-165">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="869bf-166">リバースプロキシ。 Lync Server 2013 コンポーネントではありませんが、フェデレーションユーザーのための web コンテンツの共有をサポートする場合、または Mobility トラフィックをサポートする場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="869bf-166">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="869bf-167">任意の Lync Server 2013 サーバーの役割でリバースプロキシサーバーを併置することはできませんが、他のアプリケーションで使用されている組織内の既存のリバースプロキシサーバーのサポートを構成することによって、Lync Server 2013 展開のリバースプロキシサポートを実装できます。</span><span class="sxs-lookup"><span data-stu-id="869bf-167">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="869bf-168">リバースプロキシサーバーの詳細については、「展開」のドキュメントの「 [Setting up reverse proxy servers For Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="869bf-168">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="869bf-169">Lync Server 2013 では、フロントエンドサーバー上で実行される音声ビデオ会議、監視、およびアーカイブは、独立したサーバーの役割ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="869bf-169">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="869bf-170">中央サイトに展開されるすべてのフロントエンド プールおよび Standard Edition サーバーは、中央サイトで展開される次のサーバーをどれでも共有できます。</span><span class="sxs-lookup"><span data-stu-id="869bf-170">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="869bf-171">ディレクターまたはディレクター プール</span><span class="sxs-lookup"><span data-stu-id="869bf-171">Director or Director pool</span></span>

  - <span data-ttu-id="869bf-172">スタンドアロン仲介サーバーまたはプール</span><span class="sxs-lookup"><span data-stu-id="869bf-172">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="869bf-173">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="869bf-173">Office Web Apps Server</span></span>

  - <span data-ttu-id="869bf-174">エッジ サーバーまたはエッジ プール</span><span class="sxs-lookup"><span data-stu-id="869bf-174">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="869bf-175">常設チャット サーバーまたはプール</span><span class="sxs-lookup"><span data-stu-id="869bf-175">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="869bf-176">監視</span><span class="sxs-lookup"><span data-stu-id="869bf-176">Monitoring</span></span>

  - <span data-ttu-id="869bf-177">アーカイブ</span><span class="sxs-lookup"><span data-stu-id="869bf-177">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="869bf-178">Exchange 2013 ユニファイドメッセージングの統合をサポートする必要がある場合は、Exchange UM サーバーを Lync Server 2013 展開に実装できますが、Lync Server 2013 サイトのコンポーネントではありません。</span><span class="sxs-lookup"><span data-stu-id="869bf-178">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="869bf-179">また、複数の中央サイトが、1 つの中央サイトに展開されている次のサーバーをどれでも共有できます。</span><span class="sxs-lookup"><span data-stu-id="869bf-179">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="869bf-180">スタンドアロン仲介サーバーまたはプール</span><span class="sxs-lookup"><span data-stu-id="869bf-180">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="869bf-181">エッジ サーバーまたはエッジ プール</span><span class="sxs-lookup"><span data-stu-id="869bf-181">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="869bf-182">常設チャット サーバーまたはプール</span><span class="sxs-lookup"><span data-stu-id="869bf-182">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="869bf-183">アーカイブ</span><span class="sxs-lookup"><span data-stu-id="869bf-183">Archiving</span></span>

  - <span data-ttu-id="869bf-184">監視</span><span class="sxs-lookup"><span data-stu-id="869bf-184">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="869bf-185">Exchange UM サーバーは、Lync server 2013 展開で実装し、複数の中央サイトで共有できますが、Lync Server 2013 サイトのコンポーネントではありません。</span><span class="sxs-lookup"><span data-stu-id="869bf-185">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="869bf-186">Lync Server 2013 のサーバーの役割と機能の詳細については、「計画」のドキュメントの「 [Lync server 2013 のサーバーの役割](lync-server-2013-server-roles.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="869bf-186">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="869bf-187">Lync Server 2013 のサーバーの併置のサポートの概要については、「 [Lync server 2013 でサポートされるサーバーの併置](lync-server-2013-supported-server-collocation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="869bf-187">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="869bf-188">このセクションで前述したサーバーの役割と機能に加えて、Lync Server 2013 には追加のコンポーネントとオプションがあり、次の一部またはすべてを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="869bf-188">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="869bf-189">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="869bf-189">Firewalls</span></span>

  - <span data-ttu-id="869bf-190">PSTN ゲートウェイ (エンタープライズ VoIP を展開する場合)</span><span class="sxs-lookup"><span data-stu-id="869bf-190">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="869bf-191">Exchange UM サーバー</span><span class="sxs-lookup"><span data-stu-id="869bf-191">Exchange UM Server</span></span>

  - <span data-ttu-id="869bf-192">DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="869bf-192">DNS load balancing</span></span>

  - <span data-ttu-id="869bf-193">ハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="869bf-193">Hardware load balancers</span></span>

  - <span data-ttu-id="869bf-194">SQL Server データベース</span><span class="sxs-lookup"><span data-stu-id="869bf-194">SQL Server databases</span></span>

  - <span data-ttu-id="869bf-195">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="869bf-195">File shares</span></span>

<span data-ttu-id="869bf-196">Lync Server 2013 のすべての機能、コンポーネント、およびオプションの詳細については、「計画」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="869bf-196">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="869bf-197">ブランチ サイトのトポロジとコンポーネント (内部設置型)</span><span class="sxs-lookup"><span data-stu-id="869bf-197">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="869bf-p115">ブランチ サイトは中央サイトと関連付けられ、ブランチ サイトの各存続可能ブランチ アプライアンスは、関連付けられた中央サイトの Enterprise Edition フロントエンド プールまたは Standard Edition サーバーと関連付けられます。ブランチ サイトは、その機能のほとんどを中央サイトに依存することから、ブランチ サイトのコンポーネントに含まれるのは次の項目だけです。</span><span class="sxs-lookup"><span data-stu-id="869bf-p115">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site. Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="869bf-200">存続可能 Branch Appliance。公衆交換電話網 (PSTN) ゲートウェイと一部の Lync Server 機能を組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="869bf-200">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="869bf-201">存続可能 Branch アプライアンスでは、仲介サーバーをレジストラーのインスタンスと併置でき、仲介サーバーのスタンドアロン仲介サーバーまたはプールを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="869bf-201">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="869bf-202">存続可能ブランチサーバー。 Lync Server 2013 レジストラーおよび仲介サーバーソフトウェアがインストールされている Windows Server を実行しているサーバーです。</span><span class="sxs-lookup"><span data-stu-id="869bf-202">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="869bf-203">スタンドアロン PSTN ゲートウェイ (存続可能ブランチ アプライアンスの一部ではありません) およびスタンドアロン仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="869bf-203">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="869bf-204">存続可能ブランチサーバーの要件は、すべての Lync Server 2013 のサーバーの役割の要件と同じです。</span><span class="sxs-lookup"><span data-stu-id="869bf-204">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

