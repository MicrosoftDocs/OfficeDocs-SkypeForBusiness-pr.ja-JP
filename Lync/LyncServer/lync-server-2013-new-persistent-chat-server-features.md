---
title: 'Lync Server 2013: 新しい常設チャットサーバーの機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6203e6a7ee99f4b080fa93976a2a937e62fe9d3c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="c4cb4-102">Lync Server 2013 の新しい常設チャットサーバーの機能</span><span class="sxs-lookup"><span data-stu-id="c4cb4-102">New Persistent Chat Server features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4cb4-103">_**トピックの最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="c4cb4-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="c4cb4-104">Lync Server 2013、常設チャットサーバーを使用すると、時間の経過と共に持続するマルチパーティのトピックベースの会話に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="c4cb4-105">常設チャットサーバーは、組織が次のことを行えるように支援します。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="c4cb4-106">地理的に分散されたチームや職能上の枠を越えたチーム間でのコミュニケーションを深めます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="c4cb4-107">情報を広めて参加の輪を広げます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="c4cb4-108">組織外の人間とのコミュニケーションを深めます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="c4cb4-109">情報過多を緩和します。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-109">Reduce information overload</span></span>

  - <span data-ttu-id="c4cb4-110">情報の認知を高めます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-110">Improve information awareness</span></span>

  - <span data-ttu-id="c4cb4-111">重要な知識と情報の分散を促進します。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="c4cb4-112">Lync Server 2013、常設チャットサーバーは、Microsoft 365 または Office 365 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c4cb4-113">現時点では、オンプレミスの Lync 2013 ユーザーのみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="c4cb4-114">Lync 2013 では、常設チャット機能は Lync 2013 クライアントに統合されています。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="c4cb4-115">その結果、ユーザーは Lync 2013 クライアントでインスタントメッセージング/プレゼンス、音声ビデオ、会議、および常設チャットへのアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="c4cb4-116">Lync 2013 クライアントの詳細については、「」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=270877> 。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-116">For more information about the Lync 2013 client, see <https://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="c4cb4-117">このトピックでは、新しいバージョンの Lync Server 2013、常設チャットサーバーと以前のバージョン (Microsoft Lync Server 2010、グループチャット) の機能の変更点について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="c4cb4-118">Lync Server コントロールパネルでの管理者の操作を提供し、グループチャット管理ツールを削除する</span><span class="sxs-lookup"><span data-stu-id="c4cb4-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="c4cb4-119">グループチャット構成ツールを削除して、常設チャットサーバーの構成設定をトポロジビルダーに統合する</span><span class="sxs-lookup"><span data-stu-id="c4cb4-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="c4cb4-120">以前のバージョンの常設チャットサーバーからの移行とアップグレードが容易</span><span class="sxs-lookup"><span data-stu-id="c4cb4-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="c4cb4-121">高可用性および障害復旧ソリューションを提供する</span><span class="sxs-lookup"><span data-stu-id="c4cb4-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="c4cb4-122">常設チャットサーバーの最新バージョンの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="c4cb4-123">常設チャットのヘルプには、 <https://go.microsoft.com/fwlink/p/?linkid=270945> 常設チャットの機能の詳細な一覧、機能、および常設チャットサーバーの実行中に使用する方法が記載されています。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-123">The Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="c4cb4-124">「計画」のドキュメントの「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。「展開」のドキュメントの「 [lync server 2013 での常設チャットサーバーの展開](lync-server-2013-deploying-persistent-chat-server.md)」、「 [Lync server 2010、グループチャットまたは Office Communications server 2007 R2 グループチャットから Lync server 2013 への移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)」、および「操作」のドキュメントの「 [lync Server 2013、](managing-lync-server-2013-persistent-chat-server.md)常設チャットサーバーの管理」を参照して、常設チャットサーバーをセットアップする手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="c4cb4-125">常設チャットサーバーのドキュメント .msi ファイル (Windows Installer ファイル) を使用すると、ユーザーは常設チャットサーバーに関する包括的なオフラインドキュメントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="c4cb4-126">常設チャットサーバーの主要なトポロジの変更点</span><span class="sxs-lookup"><span data-stu-id="c4cb4-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="c4cb4-127">常設チャットサーバーの次のような高レベルの変更点があります。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="c4cb4-128">常設チャットサーバーは、サーバーの役割になっています。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="c4cb4-129">Microsoft Lync Server 2010 のグループチャットサーバーは、Microsoft Lync Server 2010 用のサードパーティの信頼されたアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="c4cb4-130">常設チャットは、トポロジビルダーを使用して Lync Server 2013 トポロジに追加できます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="c4cb4-131">Lync Server 2013 では、次の3つの新しいサーバーの役割を使用して常設チャットサーバーの機能が実装されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="c4cb4-132">**PersistentChatService:** これは、常設チャットのフロントエンドの役割です。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="c4cb4-133">Standard Edition の展開では、他の Lync Server の役割と同様に、常設チャットサーバーサービスの役割はブートストラップが展開した Standard Edition サーバーに併置されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="c4cb4-134">Enterprise Edition の展開では、常設チャットサービスの役割は、他の Lync Server の役割と同様に、ブートストラップによってスタンドアロンコンピューターに展開されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="c4cb4-135">**PersistentChatStore:** 常設チャットコンテンツデータベースに対応するバックエンドサーバー。すべてのチャットコンテンツが保存されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="c4cb4-136">**PersistentChatComplianceStore:** 常設チャットコンプライアンスデータベースに対応するバックエンドサーバーの役割。すべてのコンプライアンスイベントが保存されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="c4cb4-137">これらの常設チャットサーバーの役割はオプションであり、包括的な常設チャットサーバーの機能を必要とするお客様のみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="c4cb4-138">常設チャットのコンプライアンスを展開することを選択した場合にのみ、 **PersistentChatComplianceStore**の役割が必要になります。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="c4cb4-139">**PersistentChatService**の役割は、次の2つのサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="c4cb4-140">Persistent Chat Service</span><span class="sxs-lookup"><span data-stu-id="c4cb4-140">Persistent Chat service</span></span>

  - <span data-ttu-id="c4cb4-141">Persistent Chat Compliance Service</span><span class="sxs-lookup"><span data-stu-id="c4cb4-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="c4cb4-142">これらのサービスを各常設チャットサーバーで実行すると、マルチサーバーの常設チャットサーバープール内のこれらのサービスに高可用性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="c4cb4-143">さらに、常設チャットルームでのファイルのアップロードとダウンロードをサポートするために、常設チャットサーバーには web サービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="c4cb4-144">以前は、このサービスは、必須コンポーネントとしてインストールされる常設チャットサーバー、フロントエンドサーバー、および必要なインターネットインフォメーションサービス (IIS) に併置されていました。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="c4cb4-145">Lync Server 2013 常設チャットサーバーでは、ファイルアップロード/ダウンロード web サービスが Lync Server 2013 フロントエンドサーバーと併置されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="c4cb4-146">副次的な影響として、インターネットインフォメーションサービス (IIS) は常設チャットサーバーの前提条件ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="c4cb4-147">ファイルのアップロード/ダウンロード web サービスは、インターネットインフォメーションサービス (IIS) マネージャーで**PersistentChat**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c4cb4-148"><STRONG>PersistentChatService</STRONG>の役割は、 &nbsp; そのフロントエンドサーバーが Standard Edition フロントエンドサーバーである場合にのみ、Lync Server 2013 フロントエンドサーバーと同じサーバー上で実行でき &nbsp; ます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="c4cb4-149"><STRONG>PersistentChatService</STRONG>の役割は、Lync Server 2013 フロントエンドサーバーとは独立して実行することはできません &nbsp; 。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="c4cb4-150">Lync Server 2013 の展開のコンテキストにのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="c4cb4-151">常設チャットサーバーでは、Lookup サービスは廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="c4cb4-152">Lync Server 2010 のグループチャットでは、参照サービスはすべてのグループチャットサーバーのフロントエンドサーバー上で実行され、チャネルサーバーの1つに対してルーティングが実行されました。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="c4cb4-153">Lync Server 2013 は、連絡先オブジェクトを使用してルーティングに依存します。各常設チャットサーバープールは、Lync Server フロントエンドサーバーによって使用される連絡先オブジェクトによって表され、要求を特定して適切な常設チャットサーバープールにルーティングし、プール内で常設チャットサーバーを実行しているコンピューターの1つにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="c4cb4-154">Lync Server 2013 には、コンプライアンスサービスの変更があります。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="c4cb4-155">Lync Server 2010 では、コンプライアンスサービスがスタンドアロン (併置されていない) で、1台のサーバー上でのみ実行されていました。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="c4cb4-156">コンプライアンスサービスは、常設チャットサービスと共にすべての常設チャットサーバーのフロントエンドサーバー上で実行されるようになり、マルチサーバーの常設チャットサーバープールで高可用性が提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="c4cb4-157">単一のコンプライアンスアダプターを構成して、コンプライアンスデータベースからデータを抽出したり、他のシステム (XML ファイル、Exchange ホスト型アーカイブなど) のいずれかにデータを抽出したりできます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="c4cb4-158">常設チャットサーバーには、XML アダプターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="c4cb4-159">常設チャットサービスと、各常設チャットサーバーフロントエンドサーバーのコンプライアンスサービスによって共有されるメッセージキュー (MSMQ とも呼ばれる) キューは、2つのサービスによってのみ共有されるプライベートキューになっています。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="c4cb4-160">すべてのコンプライアンスサービスは、同じコンプライアンスバックエンドデータベースに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="c4cb4-161">また、アダプターのインスタンスにデータを送信することを目的として、そのデータベースからも読み取られます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="c4cb4-162">コンプライアンスバックエンドサーバーは、新しいバックエンドサーバーの役割として表されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c4cb4-163">以前のバージョンと同様に、すべてのコンプライアンスデータは1回だけ処理されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="c4cb4-164">データは、さまざまな Lync Server 2013、常設チャットサーバーコンピューター上で実行されているコンプライアンスサービスによって呼び出される、いずれかのアダプターインスタンスによって処理されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="c4cb4-165">常設チャットサーバーでは、いずれかのアダプターインスタンスがデータを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c4cb4-166">メッセージキューのインストールの詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install server For Lync Server 2013 のサーバーへのオペレーティングシステムと必要なソフトウェアのインストール</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="c4cb4-167">Lync Server 2013 では、高可用性と障害復旧の両方が強化されています。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="c4cb4-168">高可用性の強化: SQL Server ミラーリングを使用して、常設チャットサーバーのコンテンツデータベースおよび常設チャットのコンプライアンスデータベースをデータセンター (サイト内) に高可用性で提供します。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="c4cb4-169">障害復旧機能の向上: 常設チャットサーバーは、1つの常設チャットサーバープールを2つのサイト (つまり、トポロジ内の単一の論理プールで、2つのサイト間で物理的に配置されたプール内の複数のサイト) に拡張できる拡張プールアーキテクチャをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="c4cb4-170">SQL Server のログ配布は、クロスサイトの障害復旧に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="c4cb4-171">高可用性と障害復旧の詳細については、「展開」のドキュメントの「 [Lync server 2013 での高可用性および障害復旧のための常設チャットサーバーの構成](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="c4cb4-172">常設チャットサーバーの主要な管理および管理の変更</span><span class="sxs-lookup"><span data-stu-id="c4cb4-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="c4cb4-173">Lync Server 2013 では、以下を提供することで、常設チャットサーバーの管理と管理が簡単になりました。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="c4cb4-174">統合された管理と管理。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-174">Unified administration and management.</span></span> <span data-ttu-id="c4cb4-175">Lync Server 2013 を使用すると、既に Lync 管理者になじみのあるツールを使用して、常設チャットサーバーの管理と管理を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="c4cb4-176">常設チャットサーバーには、Lync Server コントロールパネルと統合された管理ユーザーインターフェイスの操作が含まれています。これは、以前のバージョンのグループチャットサーバーのユーザーインターフェイスのパフォーマンスの問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="c4cb4-177">また、常設チャットサーバーには Windows PowerShell コマンドレットのコレクションが含まれています。これには、常設チャットサーバーカテゴリ、常設チャットサーバールーム (削除されたルームを削除したり、廃止されたコンテンツを削除することを含む)、アドインを管理します。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="c4cb4-178">簡素化された管理モデル。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-178">Simplified administration model.</span></span> <span data-ttu-id="c4cb4-179">Lync Server 2013 は、次のお客様の主要な要件に対応することで、常設チャットサーバーモデルを変更し、簡素化しました。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="c4cb4-180">スコープとカテゴリの複雑なネストされた階層を削除します。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="c4cb4-181">常設チャットサーバーへの移行を計画している現在の MindAlign のお客様に対して、拒否リストと許可リスト (スコープ) を定義することをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="c4cb4-182">以前のグループチャットサーバーのバージョンのユーザーの役割については、どのような違いがありますか。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="c4cb4-183">Lync Server 2010、グループチャットには、ユーザー管理者の役割、チャットルーム管理者の役割、およびアドインを管理できる Lync Server 管理者の役割があります。常設チャットサーバーは、常設チャット管理者の役割 (他の Lync Server の役割ベースのアクセス制御 (RBAC) の役割に似ています) を提供します。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="c4cb4-184">この RBAC の役割のメンバーであるすべてのユーザーは、チャットルーム、アドイン、およびカテゴリを管理でき (そのためこれらのカテゴリのユーザーアクセス権を取得する)、および常設チャットサーバープールの構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="c4cb4-185">以前のグループチャットサーバーのバージョンからのチャットルームのカテゴリについては、どのような違いがありますか。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="c4cb4-186">チャットルームのカテゴリを入れ子にすることはできなくなり、ルートカテゴリを変更することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="c4cb4-187">AllowedMembers/DeniedMembers は、従来のグループチャットサーバーのバージョンで使用される範囲を構成します (拒否リストの指定をサポートしていない点が異なります)。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="c4cb4-188">ネストされたカテゴリがないので、スコープを上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="c4cb4-189">Lync Server 2013 の常設チャット管理者は、チャットルームのカテゴリを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="c4cb4-190">チャットルームカテゴリの作成と管理の一環として、常設チャット管理者は、特定のカテゴリのチャットルームのメンバー/作成者にアクセスできるプリンシパル (Active Directory グループ/コンテナー/ユーザー) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="c4cb4-191">常設チャット管理者は、DeniedMembers をカテゴリに追加することもできます。これは、許可リストに明示的に除外されることになります。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="c4cb4-192">DeniedMembers は、AllowedMembers のものをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="c4cb4-193">以前のグループチャットサーバーのバージョンのチャットルームのプロパティについては、どのような違いがありますか?</span><span class="sxs-lookup"><span data-stu-id="c4cb4-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="c4cb4-194">オープンチャットルームの新しい概念は、Lync Server 2013 の常設チャットサーバーに存在します。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="c4cb4-195">許可されたメンバーはすべて、排他的なメンバーシップなしでチャットルームに参加できます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="c4cb4-196">以前のバージョンの常設チャットサーバーに含まれていた次のチャットルームのプロパティは削除されました。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="c4cb4-197">トピック: ルームには、説明のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="c4cb4-198">新しいメンバーリストの作成: 常設チャットサーバーでは、すべてのチャットルームは空のメンバーシップで始まり、許可されたメンバーのメンバーシップを最大化することができます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="c4cb4-199">ファイルのアップロード: ファイルのアップロード/ダウンロードが許可されたかどうかを制御するチャットルームごとの設定として使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="c4cb4-200">これで、カテゴリレベルのみが設定され、そのカテゴリのすべてのルームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="c4cb4-201">チャット履歴: チャット履歴が有効になっているかどうかを制御するチャットルームごとの設定として使用されますが、現在はカテゴリレベルでのみ設定され、そのカテゴリ内のすべてのルームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="c4cb4-202">招待: ルームは常に、カテゴリの招待の設定を継承します。または、会議室で無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="c4cb4-203">カテゴリが以前に招待をオフに設定していた場合、会議室は招待を有効にできません。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="c4cb4-204">以前のグループチャットサーバーのバージョンのポリシーについて、どのような違いがありますか。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="c4cb4-205">常設チャットサーバーには、ユーザー/プール/サイト/グローバル設定ごとに常設チャットが有効になっている新しい Lync ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="c4cb4-206">Lync 2013 クライアントでは、常設チャット環境は、常設チャットのポリシーによって有効になっているユーザー (直接またはプール/サイト/グローバル設定) に対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="c4cb4-207">グループチャットサーバーの以前のバージョンには、Lync Server ポリシーに統合されたポリシーがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="c4cb4-208">ユーザーごと、およびカテゴリ/ルームごとに、[ユーザーごとに**ファイルをアップロードできる**] 機能を使用して、ユーザーをユーザーの管理者、チャットルーム管理者、またはユーザーがファイルをアップロードできるように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="c4cb4-209">常設チャットサーバーの**ファイルアップロード**機能は、カテゴリごとにあります。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="c4cb4-210">ログ</span><span class="sxs-lookup"><span data-stu-id="c4cb4-210">Logging</span></span>

<span data-ttu-id="c4cb4-211">常設チャットサーバーおよび System Center Operations Manager のログは、Lync Server 2013 トレースログに統合されています。</span><span class="sxs-lookup"><span data-stu-id="c4cb4-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c4cb4-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4cb4-212">See Also</span></span>


[<span data-ttu-id="c4cb4-213">Lync Server 2013 での常設チャットサーバーの計画</span><span class="sxs-lookup"><span data-stu-id="c4cb4-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
