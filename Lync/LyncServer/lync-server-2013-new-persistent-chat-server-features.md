---
title: 'Lync Server 2013: 常設チャット サーバーの新機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6d5cd0b8197b64abfc0761dfb333f338b507ff7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="b75f7-102">Lync Server 2013 の常設チャット サーバーの新機能</span><span class="sxs-lookup"><span data-stu-id="b75f7-102">New Persistent Chat Server features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b75f7-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="b75f7-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="b75f7-104">Lync Server 2013 の常設チャットサーバーでは、時間の経過に伴う、トピックベースの会話に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="b75f7-105">常設チャットサーバーは、組織が次のことを行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="b75f7-106">地理的に分散したチームと部門間のチーム間のコミュニケーションを向上させる</span><span class="sxs-lookup"><span data-stu-id="b75f7-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="b75f7-107">情報の認識と参加を広げる</span><span class="sxs-lookup"><span data-stu-id="b75f7-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="b75f7-108">拡張組織とのコミュニケーションを向上させる</span><span class="sxs-lookup"><span data-stu-id="b75f7-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="b75f7-109">情報過多の削減</span><span class="sxs-lookup"><span data-stu-id="b75f7-109">Reduce information overload</span></span>

  - <span data-ttu-id="b75f7-110">情報認識の向上</span><span class="sxs-lookup"><span data-stu-id="b75f7-110">Improve information awareness</span></span>

  - <span data-ttu-id="b75f7-111">重要な知識と情報の分散を増やす</span><span class="sxs-lookup"><span data-stu-id="b75f7-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="b75f7-112">Lync Server 2013、常設チャットサーバーは Microsoft Office 365 では利用できません。</span><span class="sxs-lookup"><span data-stu-id="b75f7-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft Office 365.</span></span> <span data-ttu-id="b75f7-113">現時点では、オンプレミスの Lync 2013 ユーザーのみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="b75f7-114">Lync 2013 では、常設チャット機能は Lync 2013 クライアントに統合されています。</span><span class="sxs-lookup"><span data-stu-id="b75f7-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="b75f7-115">この結果、ユーザーは Lync 2013 クライアントで、インスタントメッセージ/プレゼンス、音声/ビデオ、会議、常設チャットにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="b75f7-116">Lync 2013 クライアントの詳細については、 <http://go.microsoft.com/fwlink/p/?linkid=270877>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b75f7-116">For more information about the Lync 2013 client, see <http://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="b75f7-117">このトピックでは、次のような新しいバージョンの Lync Server 2013、常設チャットサーバー、および以前のバージョン (Microsoft Lync Server 2010、グループチャット) の機能の変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="b75f7-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="b75f7-118">Lync Server コントロールパネルで管理者エクスペリエンスを提供し、グループチャット管理ツールを削除する</span><span class="sxs-lookup"><span data-stu-id="b75f7-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="b75f7-119">グループチャット構成ツールを削除して、常設チャットサーバーの構成設定をトポロジビルダーに統合する</span><span class="sxs-lookup"><span data-stu-id="b75f7-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="b75f7-120">以前のバージョンの常設チャットサーバーからの移行とアップグレードを容易にする</span><span class="sxs-lookup"><span data-stu-id="b75f7-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="b75f7-121">高可用性と災害復旧のソリューションを提供する</span><span class="sxs-lookup"><span data-stu-id="b75f7-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="b75f7-122">常設チャットサーバーの最新バージョンについて詳しくは、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b75f7-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="b75f7-123">常設チャットのヘルプ<http://go.microsoft.com/fwlink/p/?linkid=270945>では、常設チャットの機能の詳細な一覧、機能、および常設チャットサーバーの実行時に使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b75f7-123">The Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="b75f7-124">計画ドキュメントの[Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)、展開ドキュメントの[lync server 2013 での常設チャットサーバーの展開](lync-server-2013-deploying-persistent-chat-server.md)、 [Lync server 2010 からの移行、グループチャット、または OfficeCommunications Server 2007 R2 グループチャット: 移行ドキュメントの Lync Server 2013、常設チャットサーバー](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) 、および運用ドキュメントでの[lync server 2013、常設チャットサーバーの管理](managing-lync-server-2013-persistent-chat-server.md)について説明します。常設チャットサーバーを設定しています。</span><span class="sxs-lookup"><span data-stu-id="b75f7-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="b75f7-125">常設チャットサーバーのドキュメント .msi ファイル (Windows Installer ファイル) を使用すると、ユーザーは常設チャットサーバーに関する包括的なオフラインドキュメントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="b75f7-126">常設チャットサーバーの主要なトポロジの変更</span><span class="sxs-lookup"><span data-stu-id="b75f7-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="b75f7-127">常設チャットサーバーの次のような上位の変更があります。</span><span class="sxs-lookup"><span data-stu-id="b75f7-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="b75f7-128">常設チャットサーバーがサーバーの役割になりました。</span><span class="sxs-lookup"><span data-stu-id="b75f7-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="b75f7-129">Microsoft Lync Server 2010 では、グループチャットサーバーは Microsoft Lync Server 2010 用のサードパーティの信頼済みアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="b75f7-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="b75f7-130">常設チャットは、トポロジビルダーを使用して、Lync Server 2013 トポロジに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="b75f7-131">Lync Server 2013 では、次の3つの新しいサーバーの役割を使用して、常設チャットサーバー機能が実装されます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="b75f7-132">**PersistentChatService:** これは、常設チャットのフロントエンドロールです。</span><span class="sxs-lookup"><span data-stu-id="b75f7-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="b75f7-133">Standard Edition の展開では、他の Lync Server の役割と同じように、ブートストラップによって展開された Standard Edition server に、常設チャットサーバーサービスの役割が併置されています。</span><span class="sxs-lookup"><span data-stu-id="b75f7-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="b75f7-134">Enterprise Edition の展開では、常設チャットサービスの役割は、他の Lync Server の役割と同じように、ブートストラップによってスタンドアロンコンピューターに展開されます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="b75f7-135">**PersistentChatStore:** 常設チャットコンテンツデータベースに対応し、すべてのチャットコンテンツが保存されているバックエンドサーバー。</span><span class="sxs-lookup"><span data-stu-id="b75f7-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="b75f7-136">**PersistentChatComplianceStore:** 常設チャットのコンプライアンスデータベースに対応し、すべてのコンプライアンスイベントが保存されているバックエンドサーバーの役割。</span><span class="sxs-lookup"><span data-stu-id="b75f7-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="b75f7-137">これらの常設チャットサーバーの役割はオプションであり、包括的な常設チャットサーバー機能を必要としているユーザーによってのみインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="b75f7-138">**PersistentChatComplianceStore**の役割は、常設チャットのコンプライアンスの展開を選んだ場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="b75f7-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="b75f7-139">**PersistentChatService** role は、次の2つのサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="b75f7-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="b75f7-140">常設チャットサービス</span><span class="sxs-lookup"><span data-stu-id="b75f7-140">Persistent Chat service</span></span>

  - <span data-ttu-id="b75f7-141">常設チャットのコンプライアンスサービス</span><span class="sxs-lookup"><span data-stu-id="b75f7-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="b75f7-142">これらのサービスを各常設チャットサーバーで実行すると、マルチサーバーの常設チャットサーバープールでこれらのサービスの高可用性が実現されます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="b75f7-143">さらに、常設チャットルームでのファイルのアップロードとダウンロードをサポートするには、常設チャットサーバーに web サービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b75f7-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="b75f7-144">以前は、このサービスは永続的チャットサーバー、フロントエンドサーバー、必須のインターネットインフォメーションサービス (IIS) に、前提条件としてインストールされています。</span><span class="sxs-lookup"><span data-stu-id="b75f7-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="b75f7-145">Lync Server 2013 常設チャットサーバーでは、ファイルアップロード/ダウンロード web サービスは Lync Server 2013 フロントエンドサーバーと併置されています。</span><span class="sxs-lookup"><span data-stu-id="b75f7-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="b75f7-146">副次的効果として、インターネットインフォメーションサービス (IIS) は、常設チャットサーバーの前提条件を超えています。</span><span class="sxs-lookup"><span data-stu-id="b75f7-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="b75f7-147">ファイルのアップロード/ダウンロード web サービスは、インターネットインフォメーションサービス (IIS) マネージャーで**PersistentChat**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b75f7-148"><STRONG>PersistentChatService</STRONG>の役割は、フロントエンドサーバーが標準エディション&nbsp;&nbsp;のフロントエンドサーバーである場合にのみ、Lync server 2013 フロントエンドサーバーと同じサーバーで実行できます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="b75f7-149"><STRONG>PersistentChatService</STRONG> role は、Lync Server 2013&nbsp;フロントエンドサーバーとは独立して実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="b75f7-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="b75f7-150">このツールは、Lync Server 2013 展開のコンテキストでのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="b75f7-151">常設チャットサーバーでは、Lookup サービスは廃止されました。</span><span class="sxs-lookup"><span data-stu-id="b75f7-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="b75f7-152">Lync Server 2010 のグループチャットでは、検索サービスはすべてのグループチャットサーバーフロントエンドサーバーで実行され、チャネルサーバーの1つへのルーティングが実行されました。</span><span class="sxs-lookup"><span data-stu-id="b75f7-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="b75f7-153">Lync Server 2013 は、連絡先オブジェクトを使ってルーティングを利用します。各常設チャットサーバープールは、適切な常設チャットサーバープールへの要求を特定してルーティングするために、Lync Server フロントエンドサーバーによって使用される連絡先オブジェクトで表されます。プールで常設チャットサーバーを実行しているコンピューターの1つ。</span><span class="sxs-lookup"><span data-stu-id="b75f7-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="b75f7-154">Lync Server 2013 には、コンプライアンスサービスの変更があります。</span><span class="sxs-lookup"><span data-stu-id="b75f7-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="b75f7-155">Lync Server 2010 では、コンプライアンスサービスがスタンドアロン (併置されていない) で実行され、1つのサーバーでのみ実行されています。</span><span class="sxs-lookup"><span data-stu-id="b75f7-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="b75f7-156">コンプライアンスサービスは、常設チャットサービスと共にすべての常設チャットサーバーのフロントエンドサーバーで実行されるようになり、マルチサーバーの常設チャットサーバープールで高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="b75f7-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="b75f7-157">1つのコンプライアンスアダプターは、コンプライアンスデータベースからデータを抽出するように構成することができます (XML ファイル、Exchange でホストされるアーカイブなど)。</span><span class="sxs-lookup"><span data-stu-id="b75f7-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="b75f7-158">常設チャットサーバーには XML アダプターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b75f7-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="b75f7-159">常設チャットサービスで共有されるメッセージキュー (MSMQ とも呼ばれます) キューと、各常設チャットサーバーのフロントエンドサーバーのコンプライアンスサービスは、2つのサービスによってのみ共有されるプライベートキューになりました。</span><span class="sxs-lookup"><span data-stu-id="b75f7-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="b75f7-160">すべてのコンプライアンスサービスは、同じコンプライアンスバックエンドデータベースに書き込みを行います。</span><span class="sxs-lookup"><span data-stu-id="b75f7-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="b75f7-161">また、これらのユーザーは、アダプターのインスタンスにデータを送信する目的で、そのデータベースからすべて読み取ります。</span><span class="sxs-lookup"><span data-stu-id="b75f7-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="b75f7-162">コンプライアンスバックエンドサーバーは、新しいバックエンドサーバーの役割として表されます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b75f7-163">以前のバージョンと同様に、すべてのコンプライアンスデータは1回のみ処理されます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="b75f7-164">データは、さまざまな Lync Server 2013、常設チャットサーバーコンピューターで実行されているコンプライアンスサービスによって呼び出されたいずれかのアダプターインスタンスによって処理される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b75f7-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="b75f7-165">常設チャットサーバーでは、いずれかのアダプターインスタンスでデータを処理できます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b75f7-166">メッセージキューのインストールの詳細については、展開ドキュメントの「 <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Lync Server 2013 のサーバーにオペレーティングシステムと必須ソフトウェアをインストール</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b75f7-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="b75f7-167">Lync Server 2013 では、高可用性と障害回復の両方が強化されています。</span><span class="sxs-lookup"><span data-stu-id="b75f7-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="b75f7-168">高可用性の強化: SQL Server のミラーリングは、常設チャットサーバーコンテンツデータベースと永続的なチャットのコンプライアンスデータベース (インサイト) で高可用性を実現するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="b75f7-169">障害回復機能の改善: 常設チャットサーバーは、ストレッチプールアーキテクチャをサポートしており、2つのサイト間で1つの常設チャットサーバープールを拡張することができます (つまり、トポロジの1つの論理プールであり、プール内のサーバーは物理的に物理的に使用されています)。2つのサイトに配置されています)。</span><span class="sxs-lookup"><span data-stu-id="b75f7-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="b75f7-170">SQL Server のログ配布は、クロスサイトの障害回復に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="b75f7-171">高可用性と障害回復の詳細については、「展開ドキュメントの[Lync server 2013 で高可用性と障害復旧のための常設チャットサーバーを構成](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b75f7-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="b75f7-172">常設チャットサーバーのキーの管理と管理の変更</span><span class="sxs-lookup"><span data-stu-id="b75f7-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="b75f7-173">Lync Server 2013 では、次のような方法で永続的なチャットサーバーの管理と管理が簡単になりました。</span><span class="sxs-lookup"><span data-stu-id="b75f7-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="b75f7-174">管理の統合</span><span class="sxs-lookup"><span data-stu-id="b75f7-174">Unified administration and management.</span></span> <span data-ttu-id="b75f7-175">Lync Server 2013 を使用すると、Lync 管理者が既に使い慣れているツールを使用して、より簡単に永続的なチャットサーバーの管理と管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="b75f7-176">常設チャットサーバーには、Lync Server コントロールパネルと統合された管理ユーザーインターフェイスエクスペリエンスが含まれています。これは、グループチャットサーバーのユーザーインターフェイスの以前のバージョンに関するパフォーマンスの問題に対処するものです。</span><span class="sxs-lookup"><span data-stu-id="b75f7-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="b75f7-177">また、常設チャットサーバーには Windows PowerShell コマンドレットのコレクションが含まれており、常設チャットサーバーのカテゴリ、常設チャットサーバールーム (会議室の削除、廃止されたコンテンツの削除を含む)、アドインを管理して管理します。</span><span class="sxs-lookup"><span data-stu-id="b75f7-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="b75f7-178">簡素化された管理モデル。</span><span class="sxs-lookup"><span data-stu-id="b75f7-178">Simplified administration model.</span></span> <span data-ttu-id="b75f7-179">Lync Server 2013 は、次の主要な顧客要件に対応して、常設チャットサーバーモデルを変更し、簡素化しました。</span><span class="sxs-lookup"><span data-stu-id="b75f7-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="b75f7-180">スコープとカテゴリの複雑な入れ子になった階層を削除します。</span><span class="sxs-lookup"><span data-stu-id="b75f7-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="b75f7-181">許可リストと、現在の MindAlign のユーザーに対して許可されているリスト (スコープ) と、常設チャットサーバーへの移行を計画していることをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b75f7-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="b75f7-182">グループチャットサーバの以前のバージョンからのユーザロールについては、どのような違いがありますか?</span><span class="sxs-lookup"><span data-stu-id="b75f7-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="b75f7-183">Lync Server 2010、グループチャットには、ユーザー管理者の役割、チャットルーム管理者の役割、アドインを管理できる Lync Server 管理者の役割があります。常設チャットサーバーは、他の Lync に似た常設チャット管理者の役割を提供します。サーバーの役割ベースのアクセス制御 (RBAC) ロール)。</span><span class="sxs-lookup"><span data-stu-id="b75f7-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="b75f7-184">この RBAC ロールのメンバーであればだれでも、チャットルーム、アドイン、カテゴリ (そのため、これらのカテゴリのユーザーアクセスを取得)、および常設チャットサーバープールの構成を管理できます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="b75f7-185">チャットルームのカテゴリについては、以前のグループチャットサーバのバージョンとはどのような違いがありますか?</span><span class="sxs-lookup"><span data-stu-id="b75f7-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="b75f7-186">チャットルームのカテゴリを入れ子にすることはできなくなり、ルートカテゴリを変更することはできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b75f7-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="b75f7-187">AllowedMembers/DeniedMembers は、従来のグループチャットサーバーバージョンで使用されていたスコープ (拒否されたリストの指定をサポートしていないことを除く) を構成します。</span><span class="sxs-lookup"><span data-stu-id="b75f7-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="b75f7-188">スコープは入れ子になっていないため、無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b75f7-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="b75f7-189">Lync Server 2013 の常設チャット管理者は、チャットルームのカテゴリを作成して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="b75f7-190">チャットルームカテゴリの作成と管理の一環として、常設チャット管理者は、特定のカテゴリのチャットルームのメンバー/作成者としてアクセスできるプリンシパル (Active Directory グループ/コンテナー/ユーザー) を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="b75f7-191">常設チャット管理者は、カテゴリに DeniedMembers を追加することもできます。これは、許可リストに明示的に除外されることになります。</span><span class="sxs-lookup"><span data-stu-id="b75f7-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="b75f7-192">拒否されたメンバーは許可されたメンバーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="b75f7-193">チャットルームのプロパティについては、以前のグループチャットサーバのバージョンとはどのような違いがありますか?</span><span class="sxs-lookup"><span data-stu-id="b75f7-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="b75f7-194">オープンチャットルームの新しい概念は、Lync Server 2013 の常設チャットサーバーにあります。</span><span class="sxs-lookup"><span data-stu-id="b75f7-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="b75f7-195">このチャットルームには、排他的なメンバーシップなしで、許可されているすべてのメンバーが参加できます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="b75f7-196">以前のバージョンの常設チャットサーバーに含まれていた次のチャットルームのプロパティは廃止されました。</span><span class="sxs-lookup"><span data-stu-id="b75f7-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="b75f7-197">トピック: 会議室には、説明しかありません。</span><span class="sxs-lookup"><span data-stu-id="b75f7-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="b75f7-198">新しいメンバーリストの作成: 常設チャットサーバーでは、すべてのチャットルームが空のメンバーシップで開始されます。また、メンバーのメンバーシップを最大化することもできます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="b75f7-199">ファイルアップロード: チャットルームごとの設定で、ファイルのアップロードとダウンロードが許可されたかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b75f7-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="b75f7-200">これでカテゴリレベルのみが設定され、そのカテゴリのすべてのルームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="b75f7-201">チャット履歴: チャット履歴が有効になっているかどうかを制御するために、チャットルームごとに設定されていますが、これではカテゴリレベルでのみ設定され、そのカテゴリ内のすべてのルームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="b75f7-202">招待: 会議室は、カテゴリの [招待] 設定を常に継承します。または、ルームで無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="b75f7-203">このカテゴリが以前に「オフ」に設定されている場合、チャットルームは「招待」を有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b75f7-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="b75f7-204">グループチャットサーバの以前のバージョンのポリシーについては、どのような違いがありますか?</span><span class="sxs-lookup"><span data-stu-id="b75f7-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="b75f7-205">常設チャットサーバーでは、ユーザー/プール/サイト/グローバル設定ごとに常設チャットを使用して、新しい Lync ポリシーが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b75f7-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="b75f7-206">Lync 2013 クライアントの常設チャット環境は、常設チャットのポリシーによって有効になっているユーザー (直接またはプール/サイト/グローバル設定) でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="b75f7-207">グループチャットサーバーの以前のバージョンには、Lync Server ポリシーに統合されたポリシーがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="b75f7-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="b75f7-208">ユーザーごとおよびカテゴリごとに、[ユーザーごとに**ファイルをアップロード可能**] 機能を使用して、ユーザーをユーザー管理者、チャットルーム管理者、またはユーザーがファイルをアップロードできるように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="b75f7-209">常設チャットサーバーの**ファイルアップロード**機能は、1つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="b75f7-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="b75f7-210">Logging</span><span class="sxs-lookup"><span data-stu-id="b75f7-210">Logging</span></span>

<span data-ttu-id="b75f7-211">常設チャットサーバーと System Center Operations Manager のログは、Lync Server 2013 のトレースログに統合されています。</span><span class="sxs-lookup"><span data-stu-id="b75f7-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b75f7-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="b75f7-212">See Also</span></span>


[<span data-ttu-id="b75f7-213">Lync Server 2013 での常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="b75f7-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

