---
title: 'Lync Server 2013: 監視の展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e10cd492679cb412c57ea37698df198eef7721b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="742a7-102">Lync Server 2013 での監視の展開</span><span class="sxs-lookup"><span data-stu-id="742a7-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="742a7-103">_**トピックの最終更新日:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="742a7-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="742a7-104">Microsoft Lync Server 2013 監視インフラストラクチャに対して大きな変更が加えられました。これは、監視サーバーの役割が廃止されたという事実から始まります。</span><span class="sxs-lookup"><span data-stu-id="742a7-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="742a7-105">別個の監視サーバーの役割 (通常、監視サーバーの役割を実行する専用のコンピューターを組織でセットアップすることが必要でした) に代わり、各フロントエンド サーバーに監視サービスを併置するようになりました。</span><span class="sxs-lookup"><span data-stu-id="742a7-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="742a7-106">この変更には主に次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="742a7-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="742a7-107">Lync Server 2013 を実装するときに必要なサーバーの役割の数を減らします。</span><span class="sxs-lookup"><span data-stu-id="742a7-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="742a7-108">この場合、監視サーバーの役割をなくすことによって監視専用のサーバーを維持する必要性がなくなり、コストの削減にもなります。</span><span class="sxs-lookup"><span data-stu-id="742a7-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="742a7-109">Lync Server のセットアップと管理の複雑さを軽減します。</span><span class="sxs-lookup"><span data-stu-id="742a7-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="742a7-110">各フロントエンド サーバーに監視サービスを自動的に共存させることによって、監視サーバーの役割をインストール、構成、および管理する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="742a7-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="742a7-111">アーカイブサーバーの役割も、Lync Server 2013 で廃止されました。</span><span class="sxs-lookup"><span data-stu-id="742a7-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="742a7-112">監視サービスと同様に、Lync Server 2013 アーカイブサービスは各フロントエンドサーバーに併置されました。</span><span class="sxs-lookup"><span data-stu-id="742a7-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="742a7-113">監視とアーカイブは同じ SQL Server データベース インスタンスを共有することが多いので、この点は重要です。</span><span class="sxs-lookup"><span data-stu-id="742a7-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="742a7-114">推測できるとおり、この変更は監視サービスのインストールと管理の方法に大きく影響します。</span><span class="sxs-lookup"><span data-stu-id="742a7-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="742a7-115">たとえば、監視サーバーの役割が存在しなくなったため、監視サーバーノードが Lync Server トポロジビルダーから削除されました。これはつまり、トポロジに新しい監視サーバーを追加するために、トポロジビルダーの新しい監視サーバーウィザードを使用しなくなったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="742a7-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="742a7-116">(このウィザードはもう存在しません。)代わりに、通常は次の2つの手順を実行して、トポロジ内で監視サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="742a7-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="742a7-117">新しい Lync Server プールを設定したときに、同時に監視を有効にします。</span><span class="sxs-lookup"><span data-stu-id="742a7-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="742a7-118">(Lync Server 2013 では、プールごとに監視が有効または無効になります)。このドキュメントの「通話詳細記録の構成」および「qoe の設定」セクションで説明されているプロセスでは、監視データを実際に収集せずにプールの監視を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="742a7-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="742a7-p107">新しいプールに監視ストア (監視データベース) を関連付けます。1 つの監視ストアを複数のプールに関連付けることができます。レジストラー プールに所属しているユーザーの数によっては、プールごとに別個の監視データベースをセットアップする必要がない場合もあります。代わりに、複数のプールで 1 つの監視ストアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="742a7-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="742a7-p108">多くの場合、新しいプールの作成と同時に監視を有効化する方が簡単ですが、監視を無効化した状態で新しいプールを作成することもできます。その場合は、後でトポロジ ビルダーを使用してサービスを有効化できます。トポロジ ビルダーでは、プールの監視を有効化または無効化したり、プールと監視ストアを関連付けたりできます。監視サーバーの役割は使用しなくなりましたが、監視ストア (監視サービスで収集したデータを格納するバックエンド データベース) は今後も作成する必要があります。このバックエンド データベースは、Microsoft SQL Server 2008 R2 または Microsoft SQL Server 2012 を使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="742a7-p108">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled. If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store. Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service. These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="742a7-127">プールに対して監視が有効になっている場合は、トポロジを変更せずに監視データを収集するプロセスを無効にすることができます。 Lync Server 管理シェルを使用すると、通話詳細記録 (CDR) または品質を無効にし、その後で再び有効にすることができます。QoE (quality of Experience) データの収集。</span><span class="sxs-lookup"><span data-stu-id="742a7-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="742a7-128">詳細については、このドキュメントの「通話詳細記録と qoe (Quality of Experience) 設定の構成」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="742a7-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="742a7-129">2013 Lync server の監視に関するその他の重要な拡張機能として、Lync Server Monitoring Reports が IPv6 をサポートしていることが挙げられます。 IP アドレスフィールドを使用するレポートには、使用されている SQL クエリに応じて、IPv4 または IPv6 アドレスのいずれかが表示されます。and, 2) IPv6 アドレスが監視データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="742a7-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="742a7-130">SQL Server エージェントサービスのスタートアップの種類が自動で、監視データベースを保持している SQL インスタンスに対して SQL Server エージェントサービスが実行されていることを確認します。これにより、既定の監視 SQL Server メンテナンスジョブを定期的に実行することができます。SQL Server エージェントサービスの制御下にあります。</span><span class="sxs-lookup"><span data-stu-id="742a7-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="742a7-131">このドキュメントでは、Lync Server 2013 の監視および監視レポートのインストールと構成のプロセスについて順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="742a7-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="742a7-132">このドキュメントでは、次の操作のステップバイステップの手順を示します。</span><span class="sxs-lookup"><span data-stu-id="742a7-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="742a7-133">トポロジで監視を有効化し、監視ストアとフロントエンド プールを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="742a7-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="742a7-134">SQL Server Reporting Services と Lync Server 監視レポートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="742a7-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="742a7-135">監視レポートは、監視データベースに格納されている情報をさまざまなビューで表示する事前構成済みのレポートです。</span><span class="sxs-lookup"><span data-stu-id="742a7-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="742a7-136">通話詳細記録 (CDR) および Quality of Experience (QoE) データ収集を構成します。</span><span class="sxs-lookup"><span data-stu-id="742a7-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="742a7-137">通話詳細記録は、ボイスオーバー IP (VoIP) 通話などの Lync Server の機能の使用状況を追跡する方法を提供します。インスタントメッセージング (IM)、ファイル転送。音声ビデオ (A/V) 会議。アプリケーション共有セッション。</span><span class="sxs-lookup"><span data-stu-id="742a7-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="742a7-138">QoE 指標は、損失ネットワーク パケット数、バックグラウンド ノイズ、および "ジッター" の大きさ (パケット遅延の差) など、組織で行われる音声通話やビデオ通話の品質を追跡します。</span><span class="sxs-lookup"><span data-stu-id="742a7-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="742a7-139">監視データベースから CDR や QoE のレコードを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="742a7-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

