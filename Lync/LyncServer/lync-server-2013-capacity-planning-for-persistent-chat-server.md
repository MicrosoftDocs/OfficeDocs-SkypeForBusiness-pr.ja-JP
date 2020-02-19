---
title: 'Lync Server 2013: 常設チャットサーバーの容量計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0cd27f961d3b4857cf13d5786897bd29a657851
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="fe6a8-102">Lync Server 2013 の常設チャットサーバーの容量計画</span><span class="sxs-lookup"><span data-stu-id="fe6a8-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe6a8-103">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="fe6a8-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="fe6a8-104">常設チャットサーバーは、今後の取得と検索に備えて保持できる、複数ユーザーのリアルタイムチャットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="fe6a8-105">ユーザーのメールボックスに保存されるグループインスタントメッセージング (IM) とは異なり、会話履歴が構成されている場合は、常設チャットサーバーセッションが開いたままになり、コンテンツがサーバーに保存されます。メッセージ、ファイル、Url、およびその他のデータは、進行中の会話。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="fe6a8-106">容量計画は、常設チャットサーバーを展開するための準備の重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="fe6a8-107">このトピックでは、サポートされている常設チャットサーバートポロジと、展開に最適な構成を決定するために使用できる容量計画の表について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="fe6a8-108">また、ピーク時により多くの容量を必要とする常設チャットサーバーの展開を最適に管理する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="fe6a8-109">常設チャットサーバーをダウンロードするには、「」の「Microsoft Lync Server 13 [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539)常設チャットサーバー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="fe6a8-110">常設チャットサーバーのインストールの詳細については、「展開」のドキュメントの「lync server [2013 での常設チャットサーバーのインストール](lync-server-2013-installing-persistent-chat-server.md)」および「 [lync server 2013 での常設チャットサーバーの構成](lync-server-2013-configuring-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="fe6a8-111">Lync Server 計画ツールなどのサポート ツールは、容量計画の際に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="fe6a8-112">計画ツールの詳細については、「計画」のドキュメントの「 [Lync Server 2013 の計画プロセスの開始](lync-server-2013-beginning-the-planning-process.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="fe6a8-113">常設チャットサーバーでサポートされているトポロジ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="fe6a8-114">常設チャットサーバーは、単一サーバーまたは複数サーバーのプールに、単一プールまたは複数プールトポロジを使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="fe6a8-115">また、新しい Lync Server 2013 の展開用に、Standard Edition サーバー上の常設チャットサーバーもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="fe6a8-116">ただし、パフォーマンスと規模は影響を受け、この新しい展開に高可用性オプションが存在しないため、主に、概念の実証、評価などを目的として使用することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe6a8-117">両方のトポロジの詳細については、「展開」のドキュメントの「lync server <A href="lync-server-2013-planning-for-persistent-chat-server.md">2013 での常設チャットサーバーの計画</A>」および「 <A href="lync-server-2013-deploying-persistent-chat-server.md">lync Server 2013 の常設チャットサーバーの展開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="fe6a8-118">単一サーバー トポロジ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-118">Single-Server Topology</span></span>

<span data-ttu-id="fe6a8-119">常設チャットサーバーの最小構成と最も簡単な展開は、1つの常設チャットサーバーのフロントエンドサーバートポロジです。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="fe6a8-120">この展開では、常設チャットサーバーを実行する単一のサーバー (オプションで、コンプライアンスが有効な場合はコンプライアンスサービスを実行します)、SQL Server データベースの両方をホストするサーバー、およびコンプライアンスが必要な場合は、それを格納する SQL Server データベースを使用する必要があります。コンプライアンスデータ。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fe6a8-121">トポロジビルダーでは、単一サーバー展開として開始される常設チャットサーバープールにサーバーを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="fe6a8-122">単一のサーバーを使用している場合でも、複数のサーバープールトポロジを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="fe6a8-123">これにより、必要に応じて後でサーバーを追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="fe6a8-124">次の図は、コンプライアンスを備えた単一の常設チャットサーバーフロントエンドサーバーのトポロジの必須およびオプションのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="fe6a8-125">**単一の常設チャット サーバー**</span><span class="sxs-lookup"><span data-stu-id="fe6a8-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="fe6a8-126">![コンプライアンスサービスを使用する単一サーバートポロジ](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "コンプライアンスサービスを使用する単一サーバートポロジ")</span><span class="sxs-lookup"><span data-stu-id="fe6a8-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="fe6a8-127">複数サーバー トポロジ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-127">Multiple-Server Topology</span></span>

<span data-ttu-id="fe6a8-128">容量と信頼性を高めるために、「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」に記載されているように、複数サーバートポロジを展開できます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="fe6a8-129">複数サーバートポロジには、常設チャットサーバーを実行しているアクティブなコンピューターを4台まで含めることができます (高可用性と障害復旧の構成では最大8を使用できますが、残りの4つはスタンバイ時)。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="fe6a8-130">各サーバーは、最大2万の同時ユーザーをサポートできます。合計で8万同時ユーザーは、4台のサーバーがある常設チャットサーバープールに接続されます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="fe6a8-131">複数サーバートポロジは、複数のサーバーが常設チャットサーバーをホストすることを除けば、1台のサーバートポロジと同じであり、拡張性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="fe6a8-132">常設チャットサーバーを実行している複数のコンピューターは、Lync Server およびコンプライアンスサービスと同じ Active Directory ドメインサービスドメインに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="fe6a8-133">次の図は、常設チャットサーバーを実行する複数のコンピューター、オプションのコンプライアンスサービス、および独立したコンプライアンスデータベースで構成される複数サーバートポロジのすべてのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="fe6a8-134">**複数の常設チャット サーバー**</span><span class="sxs-lookup"><span data-stu-id="fe6a8-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="fe6a8-135">![複数サーバートポロジ](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "複数サーバートポロジ")</span><span class="sxs-lookup"><span data-stu-id="fe6a8-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="fe6a8-136">4台のサーバーによる常設チャットサーバーの展開では、8万ユーザーが同時にサインインして常設チャットを使用できるようにすると、サーバーあたりの2万ユーザーに負荷が均等に分配されます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="fe6a8-137">1つのサーバーが使用できなくなった場合、そのサーバーに接続しているユーザーは、常設チャットサーバーへのアクセスを失います。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="fe6a8-138">切断されたユーザーは、利用できなくなったサーバーが復元されるまでは、残りのサーバーに自動的に転送されます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="fe6a8-139">ネットワーク上の常設チャットトラフィックの量によっては、この転送に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="fe6a8-140">残りの各サーバーが 30,000 ものユーザーをホストすることになる可能性があるので、パフォーマンスの問題を回避するために、利用できなくなったサーバーをできるだけ早く復元することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="fe6a8-141">それ以外の場合は、トポロジビルダーまたは Windows PowerShell コマンドレット**set-cspersistentchatactiveserver**を使用して、別の常設チャットサーバーを使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="fe6a8-142">常設チャットサーバーの処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="fe6a8-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="fe6a8-143">次の表は、常設チャットサーバーの容量計画に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="fe6a8-144">これらは、さまざまな常設チャットサーバー設定の変更が容量機能に与える影響をモデル化します。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="fe6a8-145">常設チャットサーバーの最大容量を計画する</span><span class="sxs-lookup"><span data-stu-id="fe6a8-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="fe6a8-146">次のサンプル表を使用して、サポートすることができるユーザー数を判断します。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="fe6a8-147">常設チャットサーバープールの最大容量のサンプル</span><span class="sxs-lookup"><span data-stu-id="fe6a8-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-148">アクティブな常設チャットサービスインスタンス</span><span class="sxs-lookup"><span data-stu-id="fe6a8-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-149"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-150">常設チャットサービスのインスタンス</span><span class="sxs-lookup"><span data-stu-id="fe6a8-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-151"><em>8 (4 は非アクティブである必要がありますが、最大値は4です)</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-152">アクティブな接続ユーザー数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-153"><em>80,000</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-154">プロビジョニング対象ユーザーの総数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-155">15万</span><span class="sxs-lookup"><span data-stu-id="fe6a8-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-156">エンドポイント数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-157">12万</span><span class="sxs-lookup"><span data-stu-id="fe6a8-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fe6a8-158">上記のサンプルでは、常設チャットサーバーが使用できる最大ユーザー数をサポートすることを計画しています。常設チャットサービスの4つのサーバーまたはインスタンス (高可用性と障害復旧のために常設チャットサーバーを実行している場合は 2万)、サーバーあたりのユーザー数は合計8万のアクティブユーザーです。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="fe6a8-159">常設チャットルームへのアクセスを管理するための処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="fe6a8-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="fe6a8-160">次のサンプル表は、常設チャットサーバープールでの常設チャットルームへのアクセスの管理を計画するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="fe6a8-161">チャット ルームのアクセス管理のサンプル</span><span class="sxs-lookup"><span data-stu-id="fe6a8-161">Managing Chat Room Access Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="fe6a8-162">小規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="fe6a8-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="fe6a8-163">中規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="fe6a8-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="fe6a8-164">大規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="fe6a8-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="fe6a8-165">合計</span><span class="sxs-lookup"><span data-stu-id="fe6a8-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-166">チャット ルームのサイズ (接続ユーザー数)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-167">ルームあたり 30 ユーザー</span><span class="sxs-lookup"><span data-stu-id="fe6a8-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-168">ルームあたり 150 ユーザー</span><span class="sxs-lookup"><span data-stu-id="fe6a8-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-169">ルームあたり 16,000 ユーザー</span><span class="sxs-lookup"><span data-stu-id="fe6a8-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-170">チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="fe6a8-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-171">32000</span><span class="sxs-lookup"><span data-stu-id="fe6a8-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-172">1067</span><span class="sxs-lookup"><span data-stu-id="fe6a8-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-173">10 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-173">10</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-174">33077</span><span class="sxs-lookup"><span data-stu-id="fe6a8-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-175">大会議室の割合 (%)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-176">1%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-176">1%</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-177">1%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-177">1%</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-178">50%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-179">オープン ルームの割合 (%)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-180">3%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-180">3%</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-181">3%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-181">3%</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-182">50%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-183">オープン ルーム数 (明示的なメンバーシップなし)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-184">960</span><span class="sxs-lookup"><span data-stu-id="fe6a8-184">960</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-185">32</span><span class="sxs-lookup"><span data-stu-id="fe6a8-185">32</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-186">5</span><span class="sxs-lookup"><span data-stu-id="fe6a8-186">5</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-187">997</span><span class="sxs-lookup"><span data-stu-id="fe6a8-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-188">非オープン ルーム数 (明示的なメンバーシップがある通常のルーム)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-189">31040</span><span class="sxs-lookup"><span data-stu-id="fe6a8-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-190">1.035</span><span class="sxs-lookup"><span data-stu-id="fe6a8-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-191">5</span><span class="sxs-lookup"><span data-stu-id="fe6a8-191">5</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-192">32080</span><span class="sxs-lookup"><span data-stu-id="fe6a8-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-193">大会議室数 (追加の発表者エントリ)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-194">.0</span><span class="sxs-lookup"><span data-stu-id="fe6a8-194">0</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-195">32</span><span class="sxs-lookup"><span data-stu-id="fe6a8-195">32</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-196">5</span><span class="sxs-lookup"><span data-stu-id="fe6a8-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-197">直接メンバーシップによって管理されるルーム</span><span class="sxs-lookup"><span data-stu-id="fe6a8-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-198">50%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-198">50%</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-199">10%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-199">10%</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-200">0%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-201">ユーザー グループによって管理されるルーム</span><span class="sxs-lookup"><span data-stu-id="fe6a8-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-202">50%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-202">50%</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-203">90%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-203">90%</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-204">100%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-205">各チャット ルームのメンバーシップ一覧におけるユーザー グループ数 (オープン ルーム (明示的には指定されていない))</span><span class="sxs-lookup"><span data-stu-id="fe6a8-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-206">.0</span><span class="sxs-lookup"><span data-stu-id="fe6a8-206">0</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-207">.0</span><span class="sxs-lookup"><span data-stu-id="fe6a8-207">0</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-208">.0</span><span class="sxs-lookup"><span data-stu-id="fe6a8-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-209">各チャット ルームのメンバーシップ一覧におけるユーザー数 (非オープン ルーム)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-210">31</span><span class="sxs-lookup"><span data-stu-id="fe6a8-210">30</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-211">150</span><span class="sxs-lookup"><span data-stu-id="fe6a8-211">150</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-212">16000</span><span class="sxs-lookup"><span data-stu-id="fe6a8-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-213">各チャット ルームのメンバーシップ一覧におけるユーザー グループ数 (非オープン ルーム)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-214">1/3</span><span class="sxs-lookup"><span data-stu-id="fe6a8-214">3</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-215">5</span><span class="sxs-lookup"><span data-stu-id="fe6a8-215">5</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-216">10 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-217">各チャット ルームのマネージャー一覧におけるユーザーおよびユーザー グループ数 (オープン ルームと非オープン ルーム)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-218">6 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-218">6</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-219">6 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-219">6</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-220">6 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-221">各大会議室のチャット ルームの発表者一覧におけるユーザーおよびユーザー グループ数 (オープン ルームと非オープン ルーム)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-222">6 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-222">6</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-223">6 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-223">6</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-224">6 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-225">すべての非オープン ルームにおけるユーザー ベースのメンバーシップ エンティティ数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-226">465600</span><span class="sxs-lookup"><span data-stu-id="fe6a8-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-227">15520</span><span class="sxs-lookup"><span data-stu-id="fe6a8-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-228">すべての非オープン ルームにおけるユーザー グループ ベースのメンバーシップ エンティティ数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-229">46560</span><span class="sxs-lookup"><span data-stu-id="fe6a8-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-230">4656</span><span class="sxs-lookup"><span data-stu-id="fe6a8-230">4656</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-231">50</span><span class="sxs-lookup"><span data-stu-id="fe6a8-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-232">すべての大会議室のチャット ルームにおけるユーザーおよびユーザー グループ ベースのエンティティ数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-233">.0</span><span class="sxs-lookup"><span data-stu-id="fe6a8-233">0</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-234">192</span><span class="sxs-lookup"><span data-stu-id="fe6a8-234">192</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-235">50</span><span class="sxs-lookup"><span data-stu-id="fe6a8-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-236">すべてのチャット ルーム マネージャー一覧におけるユーザーおよびユーザー グループ ベースのマネージャー エンティティ数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-237">192000</span><span class="sxs-lookup"><span data-stu-id="fe6a8-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-238">6400</span><span class="sxs-lookup"><span data-stu-id="fe6a8-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-239">60</span><span class="sxs-lookup"><span data-stu-id="fe6a8-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-240">チャット ルームあたりのアクティブ ユーザー</span><span class="sxs-lookup"><span data-stu-id="fe6a8-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-241"><em>31</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="fe6a8-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="fe6a8-243"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-244">ユーザーあたりのチャット ルーム</span><span class="sxs-lookup"><span data-stu-id="fe6a8-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-245"><em>個</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="fe6a8-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="fe6a8-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="fe6a8-248"><em>16</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-249">各チャット ルームのメンバーシップ リストのユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-250"><em>個</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="fe6a8-251"><em>個</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="fe6a8-252"><em>約</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-253">ユーザー グループによって管理されるルーム</span><span class="sxs-lookup"><span data-stu-id="fe6a8-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="fe6a8-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="fe6a8-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-257">すべてのチャット ルームのユーザー グループ ベースのメンバーシップ エンティティ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-258">155200</span><span class="sxs-lookup"><span data-stu-id="fe6a8-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-259">5173</span><span class="sxs-lookup"><span data-stu-id="fe6a8-259">5173</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-260">68</span><span class="sxs-lookup"><span data-stu-id="fe6a8-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-261">すべてのチャット ルームのユーザー ベースのメンバーシップ エンティティ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-262">465600</span><span class="sxs-lookup"><span data-stu-id="fe6a8-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-263">77600</span><span class="sxs-lookup"><span data-stu-id="fe6a8-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-264">72000</span><span class="sxs-lookup"><span data-stu-id="fe6a8-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-265">各チャット ルームのマネージャーの一覧、発表者の一覧、およびスコープの一覧のユーザーおよびユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-266">6 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-266">6</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-267">6 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-267">6</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-268">6 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-269">すべてのチャット ルームのマネージャーの一覧、発表者の一覧、およびスコープの一覧のユーザーおよびユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-270">192000</span><span class="sxs-lookup"><span data-stu-id="fe6a8-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-271">6400</span><span class="sxs-lookup"><span data-stu-id="fe6a8-271">6400</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-272">60</span><span class="sxs-lookup"><span data-stu-id="fe6a8-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-273">アクセス制御エントリ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-274">704160</span><span class="sxs-lookup"><span data-stu-id="fe6a8-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-275">26768</span><span class="sxs-lookup"><span data-stu-id="fe6a8-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-276">160</span><span class="sxs-lookup"><span data-stu-id="fe6a8-276">160</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-277">731088</span><span class="sxs-lookup"><span data-stu-id="fe6a8-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-278">最大アクセス制御エントリ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="fe6a8-279">200万</span><span class="sxs-lookup"><span data-stu-id="fe6a8-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fe6a8-280">前のサンプルでは、推奨ガイドラインに従って常設チャットサーバーを展開すると、コンプライアンスが有効になっている4台のサーバープールで最大8万のアクティブユーザーを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="fe6a8-p110">このサンプルは、小規模 (常時 30 のアクティブ ユーザー)、中規模 (150 のアクティブ ユーザー)、および大規模 (16,000 のアクティブ ユーザー) として分類されたチャット ルームを示しています。 特定のサイズのチャット ルームの数は、次の合計数に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-p110">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users). The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="fe6a8-283">システム内のアクティブ ユーザー</span><span class="sxs-lookup"><span data-stu-id="fe6a8-283">Active users in the system</span></span>

  - <span data-ttu-id="fe6a8-284">特定のサイズのチャット ルームのアクティブ ユーザー</span><span class="sxs-lookup"><span data-stu-id="fe6a8-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="fe6a8-285">単一ユーザーが参加する特定のサイズのチャット ルーム</span><span class="sxs-lookup"><span data-stu-id="fe6a8-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="fe6a8-p111">上記の処理能力の計画表では、各チャット ルームについて、チャット ルームに直接割り当てられたエントリなど、チャット ルームに関連付けられたアクセス制御エントリの数を示しています。アクセス制御リスト (ACL) を使用して、個々のチャット ルームへのアクセスを制御できます。また、カテゴリ レベルでアクセスを制御することもできます。ACL では、個々のアクセス制御エントリは、ユーザー グループ (セキュリティ グループ、配布リストなど) または単一ユーザーのどちらかになります。アクセス制御エントリは、チャット ルームのマネージャー、発表者、およびメンバーに対して定義できます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-p111">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room. You can control access to individual chat rooms by using access control lists (ACLs). You can also control access at the category level. In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user. You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fe6a8-p112">チャット ルームの管理戦略を計画する際に、許容されるアクセス制御エントリの合計数は 200 万であることに注意してください。計算されたアクセス制御エントリが 200 万を超える場合は、サーバーのパフォーマンスが大幅に低下する可能性があります。この問題を可能な限り回避するには、アクセス制御エントリが個々のユーザーではなくユーザー グループとなるようにします。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-p112">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million. If the calculated access control entries exceed 2 million, server performance could degrade significantly. To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="fe6a8-294">チャット ルームのアクセスを招待別に管理するための処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="fe6a8-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="fe6a8-295">次の容量計画の表を使用して、会議出席依頼を送信するように構成されている場合に常設チャットサーバーが作成して保存する招待の数を把握できます。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="fe6a8-296">カテゴリの招待を管理するには、Lync Server コントロールパネルの [**チャットルームのカテゴリ設定**] ページを使用するか、Windows PowerShell コマンドレットを使用して**new-cspersistentchatcategory**を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="fe6a8-297">チャットルームの招待を管理するには、Lync クライアントから起動されたチャットルームの**管理**ページを使用するか、または Windows PowerShell コマンドレットを使用して、 **clear-cspersistentchatroom**を行います。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="fe6a8-298">次の表のサンプル データでは、[**チャット ルームの設定**] ページの [**招待**] オプションがすべてのチャット ルームの 50 パーセントで [**はい**] に設定されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fe6a8-299">サーバーによって生成された招待の数の計算値が 100 万を超えると、サーバーのパフォーマンスが大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="fe6a8-300">この問題を回避するには、招待を送信するように構成されているチャットルームの数を最小限に抑えるか、招待状を送信するように構成されているチャットルームに参加できるユーザーの数を制限してください。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="fe6a8-301">招待別のチャット ルームのアクセスのサンプル</span><span class="sxs-lookup"><span data-stu-id="fe6a8-301">Chat Room Access by Invitation Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="fe6a8-302">小規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="fe6a8-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="fe6a8-303">中規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="fe6a8-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="fe6a8-304">大規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="fe6a8-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="fe6a8-305">合計</span><span class="sxs-lookup"><span data-stu-id="fe6a8-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-306">チャット ルームにアクセスできるユーザー数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-307">ルームあたり 30 ユーザー</span><span class="sxs-lookup"><span data-stu-id="fe6a8-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-308">ルームあたり 150 ユーザー</span><span class="sxs-lookup"><span data-stu-id="fe6a8-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-309">ルームあたり 16,000 ユーザー</span><span class="sxs-lookup"><span data-stu-id="fe6a8-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-310">招待があるルームの割合</span><span class="sxs-lookup"><span data-stu-id="fe6a8-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-311">50%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-311">50%</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-312">50%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-312">50%</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-313">50%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-314">招待を送信するように構成されているチャット ルーム</span><span class="sxs-lookup"><span data-stu-id="fe6a8-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-315"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="fe6a8-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="fe6a8-317"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-318">チャット ルームにアクセスできるユーザー</span><span class="sxs-lookup"><span data-stu-id="fe6a8-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="fe6a8-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="fe6a8-321"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="fe6a8-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-322">常設チャットサーバーによって生成された招待</span><span class="sxs-lookup"><span data-stu-id="fe6a8-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-323">96万</span><span class="sxs-lookup"><span data-stu-id="fe6a8-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-324">12万</span><span class="sxs-lookup"><span data-stu-id="fe6a8-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-325">80,000</span><span class="sxs-lookup"><span data-stu-id="fe6a8-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-326">116万</span><span class="sxs-lookup"><span data-stu-id="fe6a8-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-327">招待の上限数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="fe6a8-328">200万</span><span class="sxs-lookup"><span data-stu-id="fe6a8-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-329">モデル 1 - 1 日、1 ルームあたりの想定メッセージ数で開始</span><span class="sxs-lookup"><span data-stu-id="fe6a8-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-330">ルームあたりのチャット レート (1 日あたり)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-331">50</span><span class="sxs-lookup"><span data-stu-id="fe6a8-331">50</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-332">500</span><span class="sxs-lookup"><span data-stu-id="fe6a8-332">500</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-333">100</span><span class="sxs-lookup"><span data-stu-id="fe6a8-333">100</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-334">650</span><span class="sxs-lookup"><span data-stu-id="fe6a8-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-335">すべてのチャット ルームにおけるチャット レート (1 秒あたり)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-336">55.56</span><span class="sxs-lookup"><span data-stu-id="fe6a8-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-337">18.52</span><span class="sxs-lookup"><span data-stu-id="fe6a8-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-338">0.03</span><span class="sxs-lookup"><span data-stu-id="fe6a8-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-339">74</span><span class="sxs-lookup"><span data-stu-id="fe6a8-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-340">モデル 2 - 1 日、1 ユーザーあたりの投稿メッセージ数で開始</span><span class="sxs-lookup"><span data-stu-id="fe6a8-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-341">ユーザーあたりのチャット レート (1 日あたり)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-342">15 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-342">15</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-343">5</span><span class="sxs-lookup"><span data-stu-id="fe6a8-343">5</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-344">0.1</span><span class="sxs-lookup"><span data-stu-id="fe6a8-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-345">1280</span><span class="sxs-lookup"><span data-stu-id="fe6a8-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-346">ルームあたりのチャット レート (1 日あたり)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-347">38</span><span class="sxs-lookup"><span data-stu-id="fe6a8-347">38</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-348">375</span><span class="sxs-lookup"><span data-stu-id="fe6a8-348">375</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-349">800</span><span class="sxs-lookup"><span data-stu-id="fe6a8-349">800</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-350">1213</span><span class="sxs-lookup"><span data-stu-id="fe6a8-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-351">すべてのチャット ルームにおけるチャット レート (1 秒あたり)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-352">41.67</span><span class="sxs-lookup"><span data-stu-id="fe6a8-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-353">13.89</span><span class="sxs-lookup"><span data-stu-id="fe6a8-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-354">0.28</span><span class="sxs-lookup"><span data-stu-id="fe6a8-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-355">56</span><span class="sxs-lookup"><span data-stu-id="fe6a8-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="fe6a8-356">常設チャットサーバーのパフォーマンスユーザーモデル</span><span class="sxs-lookup"><span data-stu-id="fe6a8-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="fe6a8-357">次の表では、常設チャットサーバーのユーザーモデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="fe6a8-358">この表は、処理能力の計画の要件に関する基礎を提供し、4 台のサーバーで同時に 80,000 のユーザーに対処できる一般的な組織を表しています。</span><span class="sxs-lookup"><span data-stu-id="fe6a8-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="fe6a8-359">常設チャットサーバーのパフォーマンスユーザーモデル</span><span class="sxs-lookup"><span data-stu-id="fe6a8-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-360">アクティブな接続ユーザー数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-361">80,000</span><span class="sxs-lookup"><span data-stu-id="fe6a8-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-362">常設チャットサーバーサービスインスタンスの数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-363">2/4</span><span class="sxs-lookup"><span data-stu-id="fe6a8-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-364">小規模チャット ルームのサイズ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-365">30 ユーザー</span><span class="sxs-lookup"><span data-stu-id="fe6a8-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-366">中規模チャット ルームのサイズ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-367">150 ユーザー</span><span class="sxs-lookup"><span data-stu-id="fe6a8-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-368">大規模チャット ルームのサイズ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-369">16,000 ユーザー</span><span class="sxs-lookup"><span data-stu-id="fe6a8-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-370">チャット ルームの合計数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-371">33077</span><span class="sxs-lookup"><span data-stu-id="fe6a8-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-372">小規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-373">32000</span><span class="sxs-lookup"><span data-stu-id="fe6a8-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-374">中規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-375">1067</span><span class="sxs-lookup"><span data-stu-id="fe6a8-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-376">大規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-377">10 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-378">ユーザーあたりのチャット ルームの合計数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-379">16 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-380">ユーザーあたりの小規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-381">12</span><span class="sxs-lookup"><span data-stu-id="fe6a8-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-382">ユーザーあたりの中規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-383">pbm-2</span><span class="sxs-lookup"><span data-stu-id="fe6a8-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-384">ユーザーあたりの大規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-385">pbm-2</span><span class="sxs-lookup"><span data-stu-id="fe6a8-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-386">ユーザーあたりの参加ルーム数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-387">ソケット</span><span class="sxs-lookup"><span data-stu-id="fe6a8-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-388">ピーク時の参加レート</span><span class="sxs-lookup"><span data-stu-id="fe6a8-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-389">10/秒</span><span class="sxs-lookup"><span data-stu-id="fe6a8-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-390">チャット レート合計</span><span class="sxs-lookup"><span data-stu-id="fe6a8-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-391">24/秒</span><span class="sxs-lookup"><span data-stu-id="fe6a8-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-392">小規模チャット ルームのチャット レート</span><span class="sxs-lookup"><span data-stu-id="fe6a8-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-393">22.22/second</span><span class="sxs-lookup"><span data-stu-id="fe6a8-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-394">中規模チャット ルームのチャット レート</span><span class="sxs-lookup"><span data-stu-id="fe6a8-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-395">1.67/second</span><span class="sxs-lookup"><span data-stu-id="fe6a8-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-396">大規模チャット ルームのチャット レート</span><span class="sxs-lookup"><span data-stu-id="fe6a8-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-397">~ 0.15/秒</span><span class="sxs-lookup"><span data-stu-id="fe6a8-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-398">招待が構成されているチャット ルームの割合</span><span class="sxs-lookup"><span data-stu-id="fe6a8-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-399">50%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-400">直接メンバーシップの割合</span><span class="sxs-lookup"><span data-stu-id="fe6a8-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-401">50%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-402">グループ メンバーシップの割合</span><span class="sxs-lookup"><span data-stu-id="fe6a8-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-403">50%</span><span class="sxs-lookup"><span data-stu-id="fe6a8-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-404">Active Directory ドメインサービスの先祖所属の平均数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="fe6a8-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-406">ユーザーごとの加入する連絡先の数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-407">80</span><span class="sxs-lookup"><span data-stu-id="fe6a8-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-408">ユーザーあたりの平均エンドポイント数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-409">1.5</span><span class="sxs-lookup"><span data-stu-id="fe6a8-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-410">エンドポイントあたりの表示されるチャット ルームの平均数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-411">1.5</span><span class="sxs-lookup"><span data-stu-id="fe6a8-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-412">ユーザーあたりの表示されるチャット ルームの平均数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-413">2.25 (1 ルームと 2 ルームが 50% ずつ)。最大 6 ルームがオープン (1 モニターにつき 1 つ)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-414">一定間隔でポーリングされる参加者の数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-415">25 (表示されるチャット ルーム 1 つあたり)</span><span class="sxs-lookup"><span data-stu-id="fe6a8-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-416">ポーリング間隔の長さ</span><span class="sxs-lookup"><span data-stu-id="fe6a8-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-417">5 分</span><span class="sxs-lookup"><span data-stu-id="fe6a8-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-418">1 秒あたりにポーリングされる参加者の数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-419">15,000</span><span class="sxs-lookup"><span data-stu-id="fe6a8-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe6a8-420">1 時間あたりのユーザーごとのプレゼンス変更の数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-421">6 </span><span class="sxs-lookup"><span data-stu-id="fe6a8-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe6a8-422">1 秒あたりのプレゼンス変更の数</span><span class="sxs-lookup"><span data-stu-id="fe6a8-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="fe6a8-423">133.33</span><span class="sxs-lookup"><span data-stu-id="fe6a8-423">133.33</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

