---
title: 'Lync Server 2013: 監視の展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 584b99b6e5fad72a07a35b748ab9bafa4116701a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="8d0c2-102">Lync Server 2013 での監視の展開</span><span class="sxs-lookup"><span data-stu-id="8d0c2-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d0c2-103">_**最終更新日:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="8d0c2-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="8d0c2-104">Microsoft Lync Server 2013 監視インフラストラクチャは、監視サーバーの役割が廃止されたことから始まるため、大幅な変更が行われました。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="8d0c2-105">監視サーバーの役割 (通常は、監視サーバーとして動作するように専用のコンピューターを設定する必要があります) の代わりに、監視サービスは各フロントエンドサーバーに併置されます。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="8d0c2-106">特に、この変更は次のように役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="8d0c2-107">Lync Server 2013 を実装するときに必要なサーバーの役割の数を減らします。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="8d0c2-108">この場合、監視サーバーの役割をデクリメントすることで、監視専用のサーバーを管理する必要がなくなり、コストの削減に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="8d0c2-109">Lync Server のセットアップと管理の複雑さを軽減します。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="8d0c2-110">各フロントエンドサーバーで監視サービスを自動的に特定することで、監視サーバーの役割をインストール、構成、および管理する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d0c2-111">アーカイブサーバーの役割も Lync Server 2013 で廃止されました。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="8d0c2-112">監視サービスと同様、Lync Server 2013 アーカイブサービスは各フロントエンドサーバーに併置されました。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="8d0c2-113">これは、監視とアーカイブが同じ SQL Server データベースインスタンスを共有することが多いため、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="8d0c2-114">これらの変更は、監視サービスのインストールと管理の方法に大きな影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="8d0c2-115">たとえば、監視サーバーの役割は存在しなくなったため、監視サーバーノードは Lync Server トポロジビルダーから削除されています。これは、トポロジに新しい監視サーバーを追加するために、トポロジビルダーの新しい監視サーバーウィザードを使用しなくなったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="8d0c2-116">(ウィザードは存在しなくなりました。)代わりに、通常は、次の2つの手順を実行して、トポロジ内に監視サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="8d0c2-117">新しい Lync Server プールをセットアップしたときに同時に監視を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="8d0c2-118">(Lync Server 2013 では、プール単位で監視が有効または無効になっています)。このドキュメントの「通話の詳細の記録と品質の設定」セクションで説明したプロセスである、監視データを実際に収集することなく、プールの監視を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="8d0c2-119">監視ストア (監視データベース) と新しいプールを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-119">Associating a monitoring store (that is, a monitoring database) with the new pool.</span></span> <span data-ttu-id="8d0c2-120">1つの監視ストアを複数のプールに関連付けることができることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-120">Note that a single monitoring store can be associated with multiple pools.</span></span> <span data-ttu-id="8d0c2-121">レジストラープールに所属しているユーザー数によっては、各プールに個別の監視データベースを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-121">Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools.</span></span> <span data-ttu-id="8d0c2-122">代わりに、複数のプールで単一の監視ストアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-122">Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="8d0c2-123">新しいプールを作成するのと同時に監視を有効にする方が簡単ですが、監視を無効にして新しいプールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-123">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled.</span></span> <span data-ttu-id="8d0c2-124">この操作を行う場合、後でトポロジビルダーを使用してサービスを有効にすることができます。 Topology Builder では、プールの監視を有効または無効にする方法、またはプールを異なる監視ストアに関連付ける方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-124">If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store.</span></span> <span data-ttu-id="8d0c2-125">監視サーバーの役割がなくなった場合でも、1つ以上の監視ストアを作成する必要があることに注意してください。監視サービスによって収集されたデータを格納するために使用されるバックエンドデータベース。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-125">Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service.</span></span> <span data-ttu-id="8d0c2-126">これらのバックエンドデータベースは、Microsoft SQL Server 2008 R2 または Microsoft SQL Server 2012 を使って作成できます。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-126">These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d0c2-127">プールの監視が有効になっている場合は、トポロジを変更せずに監視データの収集プロセスを無効にすることができます。 Lync Server 管理シェルでは、通話の詳細記録 (CDR) または音質を無効にする方法を提供します。Experience (QoE) データの収集。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="8d0c2-128">詳細については、このドキュメントの「通話の詳細の記録と音質の設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="8d0c2-129">Lync server 2013 で監視するためのもう1つの重要な拡張機能として、Lync Server Monitoring レポートで IPv6 がサポートされていることがあります。使用されている SQL クエリに応じて、[IP アドレス] フィールドを使用するレポートに IPv4 アドレスまたは IPv6 アドレスのいずれかが表示されます。and, 2) IPv6 アドレスが監視データベースに格納されている場所。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d0c2-130">SQL server エージェントサービスのスタートアップの種類が [自動] であり、監視データベースを保持している SQL インスタンスに対して SQL Server エージェントサービスが実行されていることを確認します。これにより、既定の監視対象の SQL Server メンテナンスジョブは、スケジュールされた基準で実行できるようになります。SQL Server エージェントサービスの制御下。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="8d0c2-131">このドキュメントでは、Lync Server 2013 で監視および監視レポートをインストールして構成するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="8d0c2-132">このドキュメントでは、次の作業を行うための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="8d0c2-133">トポロジで監視を有効にし、フロントエンドプールに監視ストアを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="8d0c2-134">SQL Server Reporting Services と Lync Server Monitoring レポートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="8d0c2-135">監視レポートは、監視データベースに格納されている情報のさまざまなビューを提供する事前構成済みレポートです。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="8d0c2-136">通話の詳細記録 (CDR) と Quality of Experience (QoE) データの収集を構成します。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="8d0c2-137">通話の詳細レコーディングは、ボイスオーバー IP (VoIP) 通話などの Lync Server 機能の使用状況を追跡するための手段を提供します。インスタントメッセージング (IM);ファイルの転送音声/ビデオ (A/V) 会議アプリケーション共有セッション。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="8d0c2-138">QoE メトリックは、組織内で行われた音声通話とビデオ通話の品質を管理します。たとえば、紛失したネットワークパケットの数、背景の雑音、"ジッター" の量 (パケット遅延の違い) などがあります。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="8d0c2-139">CDR または QoE レコードを監視データベースから手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="8d0c2-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

