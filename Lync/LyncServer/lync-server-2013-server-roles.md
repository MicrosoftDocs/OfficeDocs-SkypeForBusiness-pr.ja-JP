---
title: Lync Server 2013 のサーバーの役割
description: Lync Server 2013 のサーバーの役割。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ee4636e602e5bfb8ce6eacdccb3d190f5728d1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580193"
---
# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="8737f-103">Lync Server 2013 のサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="8737f-103">Server roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8737f-104">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="8737f-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="8737f-105">Lync Server を実行している各サーバーは、1つ以上の *サーバーの役割*を実行します。</span><span class="sxs-lookup"><span data-stu-id="8737f-105">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="8737f-106">サーバーの役割とは、そのサーバーによって提供される、定義済みの Lync Server の機能のセットのことです。</span><span class="sxs-lookup"><span data-stu-id="8737f-106">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="8737f-107">ネットワークで使用できるサーバーの役割をすべて展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8737f-107">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="8737f-108">必要な機能が含まれているサーバーの役割のみをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8737f-108">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="8737f-109">Lync Server のサーバーの役割をよく理解していない場合でも、計画ツールを使用して、必要な機能に基づいて展開する必要があるサーバーの最適なソリューションにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8737f-109">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="8737f-110">ここでは、サーバーの役割の概要とその役割が提供する一般的な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="8737f-110">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="8737f-111">Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="8737f-111">Standard Edition Server</span></span>

  - <span data-ttu-id="8737f-112">フロントエンド サーバーおよびバック エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="8737f-112">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="8737f-113">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="8737f-113">Edge Server</span></span>

  - <span data-ttu-id="8737f-114">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="8737f-114">Mediation Server</span></span>

  - <span data-ttu-id="8737f-115">ディレクター</span><span class="sxs-lookup"><span data-stu-id="8737f-115">Director</span></span>

  - <span data-ttu-id="8737f-116">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="8737f-116">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="8737f-117">常設チャット ストア (常設チャット バックエンド サーバー)</span><span class="sxs-lookup"><span data-stu-id="8737f-117">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="8737f-118">常設チャット コンプライアンス ストア (常設チャット コンプライアンス バックエンド サーバー)</span><span class="sxs-lookup"><span data-stu-id="8737f-118">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="8737f-119">多くのサーバーの役割では、すべてが同じサーバーの役割を実行する複数のサーバーのプール\*\* を展開して、スケーラビリティと高可用性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="8737f-119">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="8737f-120">プール内の各サーバーは同じサーバーの役割を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8737f-120">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="8737f-121">Lync Server のほとんどの種類のプールでは、プール内のさまざまなサーバー間のトラフィックを分散するためにロードバランサーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8737f-121">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="8737f-122">Lync Server は、ドメインネームシステム (DNS) 負荷分散とロードバランサー機器の両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8737f-122">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="8737f-123">Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="8737f-123">Standard Edition Server</span></span>

<span data-ttu-id="8737f-124">Standard Edition サーバーは、小規模な組織や、大規模な組織のパイロット プロジェクトを対象としています。</span><span class="sxs-lookup"><span data-stu-id="8737f-124">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="8737f-125">これにより、必要なデータベースを含む Lync Server の多くの機能を1台のサーバーで実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8737f-125">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="8737f-126">これにより、Lync Server の機能を低コストで利用できるようになりますが、実際の高可用性ソリューションは提供されません。</span><span class="sxs-lookup"><span data-stu-id="8737f-126">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="8737f-127">Standard Edition サーバーでは、インスタントメッセージング (IM)、プレゼンス、会議、エンタープライズ Voip を使用して、すべてを1台のサーバー上で実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8737f-127">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="8737f-128">高可用性ソリューションの場合は、Lync Server Enterprise Edition を使用します。</span><span class="sxs-lookup"><span data-stu-id="8737f-128">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="8737f-129">フロントエンド サーバーおよびバック エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="8737f-129">Front End Server and Back End Server</span></span>

<span data-ttu-id="8737f-130">Lync Server Enterprise Edition では、フロントエンドサーバーがコアサーバーの役割で、多くの基本的な Lync Server の機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="8737f-130">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="8737f-131">フロントエンドサーバーは、バックエンドサーバーと共に、Lync Server Enterprise Edition の展開に必要な唯一のサーバーの役割です。</span><span class="sxs-lookup"><span data-stu-id="8737f-131">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="8737f-p106">フロントエンド プール\*\* は、まったく同じように構成されたフロントエンド サーバーのセットです。これらは連携して共通のユーザー グループにサービスを提供します。同じ役割を実行している複数のサーバーのプールでは、スケーラビリティとフェールオーバー機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8737f-p106">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users. A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="8737f-134">フロントエンド サーバーには次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="8737f-134">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="8737f-135">ユーザーの認証および登録</span><span class="sxs-lookup"><span data-stu-id="8737f-135">User authentication and registration</span></span>

  - <span data-ttu-id="8737f-136">プレゼンス情報および連絡先カードの交換</span><span class="sxs-lookup"><span data-stu-id="8737f-136">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="8737f-137">アドレス帳サービスおよび配布リスト展開</span><span class="sxs-lookup"><span data-stu-id="8737f-137">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="8737f-138">IM 機能 (マルチパーティ IM 会議など)</span><span class="sxs-lookup"><span data-stu-id="8737f-138">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="8737f-139">Web 会議、PSTN ダイヤルイン会議、および音声ビデオ会議 (展開されている場合)。</span><span class="sxs-lookup"><span data-stu-id="8737f-139">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="8737f-140">Lync Server に含まれているアプリケーション (会議アテンダント、応答グループアプリケーションなど)、およびサードパーティアプリケーションの両方のアプリケーションホスティング</span><span class="sxs-lookup"><span data-stu-id="8737f-140">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="8737f-141">オプションで、使用状況の情報を詳細な通話の記録 (CDR) や通話エラー記録 (CER) の形式で収集するための監視。</span><span class="sxs-lookup"><span data-stu-id="8737f-141">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="8737f-142">この情報には、エンタープライズ Voip 通話と音声ビデオ会議の両方について、ネットワークを通過するメディアの品質 (オーディオおよびビデオ) に関する指標が提供されます。</span><span class="sxs-lookup"><span data-stu-id="8737f-142">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="8737f-143">Web スケジューラーや Join Launcher など、Web ベースのタスクをサポートするための Web コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="8737f-143">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="8737f-144">オプションで、コンプライアンス上の理由で IM 通信および会議の内容をアーカイブするアーカイブ機能。</span><span class="sxs-lookup"><span data-stu-id="8737f-144">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="8737f-145">詳細については、「計画」のドキュメントの「 [planning For アーカイビング In Lync Server 2013](lync-server-2013-planning-for-archiving.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8737f-145">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="8737f-146">Lync Server 2010 および以前のバージョンでは、監視とアーカイブはフロントエンドサーバーに併置されていない個別のサーバーの役割でした。</span><span class="sxs-lookup"><span data-stu-id="8737f-146">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="8737f-147">オプションで、常設チャットが有効になっている場合は、チャット ルーム管理用の常設チャット Web サービス、およびファイルのアップロード/ダウンロード用の常設チャット Web サービス。</span><span class="sxs-lookup"><span data-stu-id="8737f-147">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="8737f-p109">フロントエンド プールは、ユーザーおよび会議データ用のプライマリ ストアでもあります。各ユーザーに関する情報は、プール内の 3 つのフロントエンド サーバーにレプリケートされ、バックエンド サーバーにバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="8737f-p109">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="8737f-150">また、展開内の1つのフロントエンドプールでも *中央管理サーバー*が実行されます。これは、基本的な構成データを管理し、Lync Server を実行しているすべてのサーバーに展開します。</span><span class="sxs-lookup"><span data-stu-id="8737f-150">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="8737f-151">中央管理サーバーは、Lync Server 管理シェルおよびファイル転送機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="8737f-151">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="8737f-152">バックエンドサーバーは、フロントエンドプールのデータベースサービスを提供する Microsoft SQL Server を実行しているデータベースサーバーです。</span><span class="sxs-lookup"><span data-stu-id="8737f-152">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="8737f-153">バックエンド サーバーは、プールのユーザーおよび会議データのバックアップ ストアとして機能し、応答グループ データベースなどの他のデータベースのプライマリ ストアになります。</span><span class="sxs-lookup"><span data-stu-id="8737f-153">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="8737f-154">バックエンドサーバーは1つしか使用できませんが、SQL Server ミラーリングを使用するソリューションはフェールオーバーに推奨されます。</span><span class="sxs-lookup"><span data-stu-id="8737f-154">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="8737f-155">バックエンドサーバーは、どの Lync Server ソフトウェアも実行しません。</span><span class="sxs-lookup"><span data-stu-id="8737f-155">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8737f-156">Lync Server データベースを他のデータベースと併置することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="8737f-156">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="8737f-157">併置すると、可用性とパフォーマンスに影響することがあります。</span><span class="sxs-lookup"><span data-stu-id="8737f-157">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="8737f-158">バックエンド サーバーのデータベースには、プレゼンス情報、ユーザーの連絡先リスト、会議データ (現在のすべての会議の状態に関する固定データなど)、および会議のスケジュール データなどの情報が格納されています。</span><span class="sxs-lookup"><span data-stu-id="8737f-158">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="8737f-159">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="8737f-159">Edge Server</span></span>

<span data-ttu-id="8737f-160">エッジ サーバーを使用すると、ユーザーは組織のファイアウォールの外側にいるユーザーと通信や共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8737f-160">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="8737f-161">これらの外部ユーザーには、現在、オフサイトで作業している組織の独自のユーザー、フェデレーションパートナー組織のユーザー、および Lync Server 展開でホストされている会議に参加するよう招待された外部ユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8737f-161">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="8737f-162">エッジサーバーでは、Windows Live、AOL、Yahoo、Google Talk を含むパブリック IM 接続サービスへの接続も可能になり \! ます。</span><span class="sxs-lookup"><span data-stu-id="8737f-162">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="8737f-163">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8737f-163">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="8737f-164">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="8737f-164">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="8737f-165">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="8737f-165">Messenger until the service shut down date.</span></span> <span data-ttu-id="8737f-166">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="8737f-166">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="8737f-167">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="8737f-167">has been announced.</span></span> <span data-ttu-id="8737f-168">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8737f-168">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="8737f-169">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="8737f-169">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="8737f-170">Messenger.</span><span class="sxs-lookup"><span data-stu-id="8737f-170">Messenger.</span></span> <span data-ttu-id="8737f-171">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</span><span class="sxs-lookup"><span data-stu-id="8737f-171">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="8737f-172">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="8737f-172">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="8737f-173">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8737f-173">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="8737f-174">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="8737f-174">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="8737f-175">エッジ サーバーを展開すると、モバイル デバイスで Lync 機能をサポートするモビリティ サービスも有効になります。</span><span class="sxs-lookup"><span data-stu-id="8737f-175">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="8737f-176">ユーザーは、サポートされる Apple iOS、Android、Windows Phone、または Nokia のモバイル デバイスを使用して、インスタント メッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8737f-176">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="8737f-177">また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、モバイル デバイスでいくつかのエンタープライズ VoIP 機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8737f-177">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="8737f-178">モビリティ機能では、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイス用のプッシュ通知\*\* もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8737f-178">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="8737f-179">プッシュ通知は、モバイル アプリケーションが非アクティブなときに発生したイベントについてモバイル デバイスに送信される通知です。</span><span class="sxs-lookup"><span data-stu-id="8737f-179">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="8737f-180">エッジ サーバーには、完全に統合された XMPP (eXtensible Messaging and Presence Protocol) プロキシと、フロントエンド サーバーに含まれる XMPP ゲートウェイも含まれます。</span><span class="sxs-lookup"><span data-stu-id="8737f-180">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="8737f-181">これらの XMPP コンポーネントを構成して、Lync Server 2013 ユーザーがインスタントメッセージングとプレゼンスの XMPP ベースのパートナー (Google Talk など) から連絡先を追加できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8737f-181">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="8737f-182">詳細については、「計画」のドキュメントの「 [planning for external user access In Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8737f-182">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="8737f-183">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="8737f-183">Mediation Server</span></span>

<span data-ttu-id="8737f-184">仲介サーバーは、エンタープライズ Voip およびダイヤルイン会議を実装するために必要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="8737f-184">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="8737f-185">仲介サーバーは、内部の Lync Server インフラストラクチャと公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはセッション開始プロトコル (SIP) トランク間のメディアを変換します。</span><span class="sxs-lookup"><span data-stu-id="8737f-185">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="8737f-186">フロントエンド サーバーと同じサーバーに配置されている、またはスタンドアロンの仲介サーバー プールに分離されている仲介サーバーを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8737f-186">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="8737f-187">詳細については、「計画」のドキュメントの「 [Lync server 2013 の仲介サーバーコンポーネント](lync-server-2013-mediation-server-component.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8737f-187">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="8737f-188">ディレクター</span><span class="sxs-lookup"><span data-stu-id="8737f-188">Director</span></span>

<span data-ttu-id="8737f-189">ディレクターは、Lync Server ユーザー要求を認証できますが、ユーザーアカウントをホームにしたり、プレゼンスや会議サービスを提供したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="8737f-189">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="8737f-190">ディレクターは、外部ユーザー アクセスが有効になっている展開でセキュリティを強化するのに非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8737f-190">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="8737f-191">内部サーバーに要求を送信する前にディレクターで認証を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8737f-191">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="8737f-192">サービス拒否攻撃が発生した場合、攻撃はディレクターによって終了され、フロントエンド サーバーには到達しません。</span><span class="sxs-lookup"><span data-stu-id="8737f-192">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="8737f-193">詳細については、「計画」のドキュメントの「 [Lync Server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8737f-193">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="8737f-194">常設チャットサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="8737f-194">Persistent Chat Server Roles</span></span>

<span data-ttu-id="8737f-p121">常設チャットでは、ユーザーがトピックに基づく長時間のマルチパーティ会話に参加できます。常設チャット フロントエンド サーバーは、常設チャット サービスを実行します。常設チャット バックエンド サーバーでは、チャット履歴データと、カテゴリおよびチャット ルームに関する情報が格納されます。オプションの常設チャット コンプライアンス バックエンド サーバーでは、コンプライアンスの目的でチャットの内容とコンプライアンス イベントを格納できます。</span><span class="sxs-lookup"><span data-stu-id="8737f-p121">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="8737f-199">Lync Server Standard Edition を実行しているサーバーは、同じサーバー上に併置された常設チャットも実行できます。</span><span class="sxs-lookup"><span data-stu-id="8737f-199">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="8737f-200">常設チャットフロントエンドサーバーを Enterprise Edition フロントエンドサーバーと併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="8737f-200">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="8737f-201">詳細については、「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8737f-201">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8737f-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="8737f-202">See Also</span></span>


[<span data-ttu-id="8737f-203">Lync Server 2013 の仲介サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="8737f-203">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="8737f-204">Lync Server 2013 でのアーカイブの計画</span><span class="sxs-lookup"><span data-stu-id="8737f-204">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="8737f-205">Lync Server 2013 での外部ユーザーアクセスの計画</span><span class="sxs-lookup"><span data-stu-id="8737f-205">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="8737f-206">Lync Server 2013 のディレクターのシナリオ</span><span class="sxs-lookup"><span data-stu-id="8737f-206">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="8737f-207">Lync Server 2013 での常設チャットサーバーの計画</span><span class="sxs-lookup"><span data-stu-id="8737f-207">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

