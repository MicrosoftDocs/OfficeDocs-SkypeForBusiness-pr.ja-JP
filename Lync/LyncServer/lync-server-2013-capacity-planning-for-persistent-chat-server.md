---
title: 'Lync Server 2013: 常設チャットサーバーの容量計画'
description: 'Lync Server 2013: 常設チャットサーバーの容量計画。'
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
ms.openlocfilehash: f78f9f3666fb272b808ef36da2d3010f451d0079
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544493"
---
# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="6c8be-103">Lync Server 2013 の常設チャットサーバーの容量計画</span><span class="sxs-lookup"><span data-stu-id="6c8be-103">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c8be-104">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6c8be-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6c8be-105">常設チャットサーバーは、今後の取得と検索に備えて保持できる、複数ユーザーのリアルタイムチャットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-105">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="6c8be-106">ユーザーのメールボックスに保存されるグループインスタントメッセージング (IM) とは異なり、会話履歴が構成されている場合は、常設チャットサーバーセッションが開いたままになり、そのコンテンツがサーバーに保存されます。メッセージ、ファイル、Url、および進行中の会話の一部であるその他のデータも保存されます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-106">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="6c8be-107">容量計画は、常設チャットサーバーを展開するための準備の重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="6c8be-107">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="6c8be-108">このトピックでは、サポートされている常設チャットサーバートポロジと、展開に最適な構成を決定するために使用できる容量計画の表について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-108">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="6c8be-109">また、ピーク時により多くの容量を必要とする常設チャットサーバーの展開を最適に管理する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-109">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="6c8be-110">常設チャットサーバーをダウンロードするには、「」の「Microsoft Lync Server 13 常設チャットサーバー」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539) 。</span><span class="sxs-lookup"><span data-stu-id="6c8be-110">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="6c8be-111">常設チャットサーバーのインストールの詳細については、「展開」のドキュメントの「lync server [2013 での常設チャットサーバーのインストール](lync-server-2013-installing-persistent-chat-server.md) 」および「 [lync server 2013 での常設チャットサーバーの構成](lync-server-2013-configuring-persistent-chat-server.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c8be-111">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="6c8be-112">Lync Server 計画ツールなどのサポート ツールは、容量計画の際に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-112">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="6c8be-113">計画ツールの詳細については、「計画」のドキュメントの「 [Lync Server 2013 の計画プロセスの開始](lync-server-2013-beginning-the-planning-process.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c8be-113">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="6c8be-114">常設チャットサーバーでサポートされているトポロジ</span><span class="sxs-lookup"><span data-stu-id="6c8be-114">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="6c8be-115">常設チャットサーバーは、単一サーバーまたは複数サーバーのプールに、単一プールまたは複数プールトポロジを使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-115">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="6c8be-116">また、新しい Lync Server 2013 の展開用に、Standard Edition サーバー上の常設チャットサーバーもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-116">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="6c8be-117">ただし、パフォーマンスと規模は影響を受け、この新しい展開に高可用性オプションが存在しないため、主に、概念の実証、評価などを目的として使用することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-117">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6c8be-118">両方のトポロジの詳細については、「展開」のドキュメントの「lync server <A href="lync-server-2013-planning-for-persistent-chat-server.md">2013 での常設チャットサーバーの計画</A> 」および「 <A href="lync-server-2013-deploying-persistent-chat-server.md">lync Server 2013 の常設チャットサーバーの展開</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c8be-118">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="6c8be-119">単一サーバー トポロジ</span><span class="sxs-lookup"><span data-stu-id="6c8be-119">Single-Server Topology</span></span>

<span data-ttu-id="6c8be-120">常設チャットサーバーの最小構成と最も簡単な展開は、1つの常設チャットサーバーのフロントエンドサーバートポロジです。</span><span class="sxs-lookup"><span data-stu-id="6c8be-120">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="6c8be-121">この展開では、常設チャットサーバーを実行する単一のサーバー (オプションで、コンプライアンスが有効な場合はコンプライアンスサービスを実行します)、SQL Server データベースの両方をホストするサーバー、およびコンプライアンスが必要な場合は、コンプライアンスデータを格納する SQL Server データベースを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-121">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6c8be-122">トポロジビルダーでは、単一サーバー展開として開始される常設チャットサーバープールにサーバーを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="6c8be-122">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="6c8be-123">単一のサーバーを使用している場合でも、複数のサーバープールトポロジを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6c8be-123">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="6c8be-124">これにより、必要に応じて後でサーバーを追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-124">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="6c8be-125">次の図は、コンプライアンスを備えた単一の常設チャットサーバーフロントエンドサーバーのトポロジの必須およびオプションのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-125">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="6c8be-126">**単一の常設チャット サーバー**</span><span class="sxs-lookup"><span data-stu-id="6c8be-126">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="6c8be-127">![コンプライアンスサービスを使用する単一サーバートポロジ](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "コンプライアンスサービスを使用する単一サーバートポロジ")</span><span class="sxs-lookup"><span data-stu-id="6c8be-127">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="6c8be-128">複数サーバー トポロジ</span><span class="sxs-lookup"><span data-stu-id="6c8be-128">Multiple-Server Topology</span></span>

<span data-ttu-id="6c8be-129">容量と信頼性を高めるために、「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」に記載されているように、複数サーバートポロジを展開できます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-129">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="6c8be-130">複数サーバートポロジには、常設チャットサーバーを実行しているアクティブなコンピューターを4台まで含めることができます (高可用性と障害復旧の構成では最大8を使用できますが、残りの4つはスタンバイ時)。</span><span class="sxs-lookup"><span data-stu-id="6c8be-130">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="6c8be-131">各サーバーは、最大2万の同時ユーザーをサポートできます。合計で8万同時ユーザーは、4台のサーバーがある常設チャットサーバープールに接続されます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-131">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="6c8be-132">複数サーバートポロジは、複数のサーバーが常設チャットサーバーをホストすることを除けば、1台のサーバートポロジと同じであり、拡張性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-132">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="6c8be-133">常設チャットサーバーを実行している複数のコンピューターは、Lync Server およびコンプライアンスサービスと同じ Active Directory ドメインサービスドメインに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-133">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="6c8be-134">次の図は、常設チャットサーバーを実行する複数のコンピューター、オプションのコンプライアンスサービス、および独立したコンプライアンスデータベースで構成される複数サーバートポロジのすべてのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-134">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="6c8be-135">**複数の常設チャット サーバー**</span><span class="sxs-lookup"><span data-stu-id="6c8be-135">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="6c8be-136">![複数サーバートポロジ](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "複数サーバートポロジ")</span><span class="sxs-lookup"><span data-stu-id="6c8be-136">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="6c8be-137">4台のサーバーによる常設チャットサーバーの展開では、8万ユーザーが同時にサインインして常設チャットを使用できるようにすると、サーバーあたりの2万ユーザーに負荷が均等に分配されます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-137">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="6c8be-138">1つのサーバーが使用できなくなった場合、そのサーバーに接続しているユーザーは、常設チャットサーバーへのアクセスを失います。</span><span class="sxs-lookup"><span data-stu-id="6c8be-138">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="6c8be-139">切断されたユーザーは、利用できなくなったサーバーが復元されるまでは、残りのサーバーに自動的に転送されます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-139">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="6c8be-140">ネットワーク上の常設チャットトラフィックの量によっては、この転送に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-140">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="6c8be-141">残りの各サーバーが 30,000 ものユーザーをホストすることになる可能性があるので、パフォーマンスの問題を回避するために、利用できなくなったサーバーをできるだけ早く復元することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6c8be-141">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="6c8be-142">それ以外の場合は、トポロジビルダーまたは Windows PowerShell コマンドレット **set-cspersistentchatactiveserver**を使用して、別の常設チャットサーバーを使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-142">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="6c8be-143">常設チャットサーバーの処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="6c8be-143">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="6c8be-144">次の表は、常設チャットサーバーの容量計画に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-144">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="6c8be-145">これらは、さまざまな常設チャットサーバー設定の変更が容量機能に与える影響をモデル化します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-145">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="6c8be-146">常設チャットサーバーの最大容量を計画する</span><span class="sxs-lookup"><span data-stu-id="6c8be-146">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="6c8be-147">次のサンプル表を使用して、サポートすることができるユーザー数を判断します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-147">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="6c8be-148">常設チャットサーバープールの最大容量のサンプル</span><span class="sxs-lookup"><span data-stu-id="6c8be-148">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-149">アクティブな常設チャットサービスインスタンス</span><span class="sxs-lookup"><span data-stu-id="6c8be-149">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="6c8be-150"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-150"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-151">常設チャットサービスのインスタンス</span><span class="sxs-lookup"><span data-stu-id="6c8be-151">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="6c8be-152"><em>8 (4 は非アクティブである必要がありますが、最大値は4です)</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-152"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-153">アクティブな接続ユーザー数</span><span class="sxs-lookup"><span data-stu-id="6c8be-153">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="6c8be-154"><em>80,000</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-154"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-155">プロビジョニング対象ユーザーの総数</span><span class="sxs-lookup"><span data-stu-id="6c8be-155">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="6c8be-156">15万</span><span class="sxs-lookup"><span data-stu-id="6c8be-156">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-157">エンドポイント数</span><span class="sxs-lookup"><span data-stu-id="6c8be-157">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="6c8be-158">12万</span><span class="sxs-lookup"><span data-stu-id="6c8be-158">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6c8be-159">上記のサンプルでは、常設チャットサーバーが使用できる最大ユーザー数をサポートすることを計画しています。常設チャットサービスの4つのサーバーまたはインスタンス (高可用性と障害復旧のために常設チャットサーバーを実行している場合は 2万)、サーバーあたりのユーザー数は合計8万のアクティブユーザーです。</span><span class="sxs-lookup"><span data-stu-id="6c8be-159">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="6c8be-160">常設チャットルームへのアクセスを管理するための処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="6c8be-160">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="6c8be-161">次のサンプル表は、常設チャットサーバープールでの常設チャットルームへのアクセスの管理を計画するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-161">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="6c8be-162">チャット ルームのアクセス管理のサンプル</span><span class="sxs-lookup"><span data-stu-id="6c8be-162">Managing Chat Room Access Sample</span></span>

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
<th><span data-ttu-id="6c8be-163">小規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="6c8be-163">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="6c8be-164">中規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="6c8be-164">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="6c8be-165">大規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="6c8be-165">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="6c8be-166">合計</span><span class="sxs-lookup"><span data-stu-id="6c8be-166">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-167">チャット ルームのサイズ (接続ユーザー数)</span><span class="sxs-lookup"><span data-stu-id="6c8be-167">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="6c8be-168">ルームあたり 30 ユーザー</span><span class="sxs-lookup"><span data-stu-id="6c8be-168">30 per room</span></span></p></td>
<td><p><span data-ttu-id="6c8be-169">ルームあたり 150 ユーザー</span><span class="sxs-lookup"><span data-stu-id="6c8be-169">150 per room</span></span></p></td>
<td><p><span data-ttu-id="6c8be-170">ルームあたり 16,000 ユーザー</span><span class="sxs-lookup"><span data-stu-id="6c8be-170">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-171">チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="6c8be-171">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-172">32000</span><span class="sxs-lookup"><span data-stu-id="6c8be-172">32,000</span></span></p></td>
<td><p><span data-ttu-id="6c8be-173">1067</span><span class="sxs-lookup"><span data-stu-id="6c8be-173">1,067</span></span></p></td>
<td><p><span data-ttu-id="6c8be-174">10  </span><span class="sxs-lookup"><span data-stu-id="6c8be-174">10</span></span></p></td>
<td><p><span data-ttu-id="6c8be-175">33077</span><span class="sxs-lookup"><span data-stu-id="6c8be-175">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-176">大会議室の割合 (%)</span><span class="sxs-lookup"><span data-stu-id="6c8be-176">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="6c8be-177">1%</span><span class="sxs-lookup"><span data-stu-id="6c8be-177">1%</span></span></p></td>
<td><p><span data-ttu-id="6c8be-178">1%</span><span class="sxs-lookup"><span data-stu-id="6c8be-178">1%</span></span></p></td>
<td><p><span data-ttu-id="6c8be-179">50%</span><span class="sxs-lookup"><span data-stu-id="6c8be-179">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-180">オープン ルームの割合 (%)</span><span class="sxs-lookup"><span data-stu-id="6c8be-180">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="6c8be-181">3%</span><span class="sxs-lookup"><span data-stu-id="6c8be-181">3%</span></span></p></td>
<td><p><span data-ttu-id="6c8be-182">3%</span><span class="sxs-lookup"><span data-stu-id="6c8be-182">3%</span></span></p></td>
<td><p><span data-ttu-id="6c8be-183">50%</span><span class="sxs-lookup"><span data-stu-id="6c8be-183">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-184">オープン ルーム数 (明示的なメンバーシップなし)</span><span class="sxs-lookup"><span data-stu-id="6c8be-184">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="6c8be-185">960</span><span class="sxs-lookup"><span data-stu-id="6c8be-185">960</span></span></p></td>
<td><p><span data-ttu-id="6c8be-186">32</span><span class="sxs-lookup"><span data-stu-id="6c8be-186">32</span></span></p></td>
<td><p><span data-ttu-id="6c8be-187">5 </span><span class="sxs-lookup"><span data-stu-id="6c8be-187">5</span></span></p></td>
<td><p><span data-ttu-id="6c8be-188">997</span><span class="sxs-lookup"><span data-stu-id="6c8be-188">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-189">非オープン ルーム数 (明示的なメンバーシップがある通常のルーム)</span><span class="sxs-lookup"><span data-stu-id="6c8be-189">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="6c8be-190">31040</span><span class="sxs-lookup"><span data-stu-id="6c8be-190">31,040</span></span></p></td>
<td><p><span data-ttu-id="6c8be-191">1.035</span><span class="sxs-lookup"><span data-stu-id="6c8be-191">1.035</span></span></p></td>
<td><p><span data-ttu-id="6c8be-192">5 </span><span class="sxs-lookup"><span data-stu-id="6c8be-192">5</span></span></p></td>
<td><p><span data-ttu-id="6c8be-193">32080</span><span class="sxs-lookup"><span data-stu-id="6c8be-193">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-194">大会議室数 (追加の発表者エントリ)</span><span class="sxs-lookup"><span data-stu-id="6c8be-194">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="6c8be-195">.0</span><span class="sxs-lookup"><span data-stu-id="6c8be-195">0</span></span></p></td>
<td><p><span data-ttu-id="6c8be-196">32</span><span class="sxs-lookup"><span data-stu-id="6c8be-196">32</span></span></p></td>
<td><p><span data-ttu-id="6c8be-197">5 </span><span class="sxs-lookup"><span data-stu-id="6c8be-197">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-198">直接メンバーシップによって管理されるルーム</span><span class="sxs-lookup"><span data-stu-id="6c8be-198">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="6c8be-199">50%</span><span class="sxs-lookup"><span data-stu-id="6c8be-199">50%</span></span></p></td>
<td><p><span data-ttu-id="6c8be-200">10%</span><span class="sxs-lookup"><span data-stu-id="6c8be-200">10%</span></span></p></td>
<td><p><span data-ttu-id="6c8be-201">0%</span><span class="sxs-lookup"><span data-stu-id="6c8be-201">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-202">ユーザー グループによって管理されるルーム</span><span class="sxs-lookup"><span data-stu-id="6c8be-202">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="6c8be-203">50%</span><span class="sxs-lookup"><span data-stu-id="6c8be-203">50%</span></span></p></td>
<td><p><span data-ttu-id="6c8be-204">90%</span><span class="sxs-lookup"><span data-stu-id="6c8be-204">90%</span></span></p></td>
<td><p><span data-ttu-id="6c8be-205">100%</span><span class="sxs-lookup"><span data-stu-id="6c8be-205">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-206">各チャット ルームのメンバーシップ一覧におけるユーザー グループ数 (オープン ルーム (明示的には指定されていない))</span><span class="sxs-lookup"><span data-stu-id="6c8be-206">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="6c8be-207">.0</span><span class="sxs-lookup"><span data-stu-id="6c8be-207">0</span></span></p></td>
<td><p><span data-ttu-id="6c8be-208">.0</span><span class="sxs-lookup"><span data-stu-id="6c8be-208">0</span></span></p></td>
<td><p><span data-ttu-id="6c8be-209">.0</span><span class="sxs-lookup"><span data-stu-id="6c8be-209">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-210">各チャット ルームのメンバーシップ一覧におけるユーザー数 (非オープン ルーム)</span><span class="sxs-lookup"><span data-stu-id="6c8be-210">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-211">31</span><span class="sxs-lookup"><span data-stu-id="6c8be-211">30</span></span></p></td>
<td><p><span data-ttu-id="6c8be-212">150</span><span class="sxs-lookup"><span data-stu-id="6c8be-212">150</span></span></p></td>
<td><p><span data-ttu-id="6c8be-213">16000</span><span class="sxs-lookup"><span data-stu-id="6c8be-213">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-214">各チャット ルームのメンバーシップ一覧におけるユーザー グループ数 (非オープン ルーム)</span><span class="sxs-lookup"><span data-stu-id="6c8be-214">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-215">1/3</span><span class="sxs-lookup"><span data-stu-id="6c8be-215">3</span></span></p></td>
<td><p><span data-ttu-id="6c8be-216">5 </span><span class="sxs-lookup"><span data-stu-id="6c8be-216">5</span></span></p></td>
<td><p><span data-ttu-id="6c8be-217">10  </span><span class="sxs-lookup"><span data-stu-id="6c8be-217">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-218">各チャット ルームのマネージャー一覧におけるユーザーおよびユーザー グループ数 (オープン ルームと非オープン ルーム)</span><span class="sxs-lookup"><span data-stu-id="6c8be-218">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="6c8be-219">6 </span><span class="sxs-lookup"><span data-stu-id="6c8be-219">6</span></span></p></td>
<td><p><span data-ttu-id="6c8be-220">6 </span><span class="sxs-lookup"><span data-stu-id="6c8be-220">6</span></span></p></td>
<td><p><span data-ttu-id="6c8be-221">6 </span><span class="sxs-lookup"><span data-stu-id="6c8be-221">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-222">各大会議室のチャット ルームの発表者一覧におけるユーザーおよびユーザー グループ数 (オープン ルームと非オープン ルーム)</span><span class="sxs-lookup"><span data-stu-id="6c8be-222">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="6c8be-223">6 </span><span class="sxs-lookup"><span data-stu-id="6c8be-223">6</span></span></p></td>
<td><p><span data-ttu-id="6c8be-224">6 </span><span class="sxs-lookup"><span data-stu-id="6c8be-224">6</span></span></p></td>
<td><p><span data-ttu-id="6c8be-225">6 </span><span class="sxs-lookup"><span data-stu-id="6c8be-225">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-226">すべての非オープン ルームにおけるユーザー ベースのメンバーシップ エンティティ数</span><span class="sxs-lookup"><span data-stu-id="6c8be-226">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-227">465600</span><span class="sxs-lookup"><span data-stu-id="6c8be-227">465,600</span></span></p></td>
<td><p><span data-ttu-id="6c8be-228">15520</span><span class="sxs-lookup"><span data-stu-id="6c8be-228">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-229">すべての非オープン ルームにおけるユーザー グループ ベースのメンバーシップ エンティティ数</span><span class="sxs-lookup"><span data-stu-id="6c8be-229">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-230">46560</span><span class="sxs-lookup"><span data-stu-id="6c8be-230">46,560</span></span></p></td>
<td><p><span data-ttu-id="6c8be-231">4656</span><span class="sxs-lookup"><span data-stu-id="6c8be-231">4656</span></span></p></td>
<td><p><span data-ttu-id="6c8be-232">50</span><span class="sxs-lookup"><span data-stu-id="6c8be-232">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-233">すべての大会議室のチャット ルームにおけるユーザーおよびユーザー グループ ベースのエンティティ数</span><span class="sxs-lookup"><span data-stu-id="6c8be-233">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-234">.0</span><span class="sxs-lookup"><span data-stu-id="6c8be-234">0</span></span></p></td>
<td><p><span data-ttu-id="6c8be-235">192</span><span class="sxs-lookup"><span data-stu-id="6c8be-235">192</span></span></p></td>
<td><p><span data-ttu-id="6c8be-236">50</span><span class="sxs-lookup"><span data-stu-id="6c8be-236">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-237">すべてのチャット ルーム マネージャー一覧におけるユーザーおよびユーザー グループ ベースのマネージャー エンティティ数</span><span class="sxs-lookup"><span data-stu-id="6c8be-237">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="6c8be-238">192000</span><span class="sxs-lookup"><span data-stu-id="6c8be-238">192,000</span></span></p></td>
<td><p><span data-ttu-id="6c8be-239">6400</span><span class="sxs-lookup"><span data-stu-id="6c8be-239">6,400</span></span></p></td>
<td><p><span data-ttu-id="6c8be-240">60</span><span class="sxs-lookup"><span data-stu-id="6c8be-240">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-241">チャット ルームあたりのアクティブ ユーザー</span><span class="sxs-lookup"><span data-stu-id="6c8be-241">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="6c8be-242"><em>31</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-242"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="6c8be-243"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-243"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="6c8be-244"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-244"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-245">ユーザーあたりのチャット ルーム</span><span class="sxs-lookup"><span data-stu-id="6c8be-245">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="6c8be-246"><em>個</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-246"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="6c8be-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="6c8be-248"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-248"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="6c8be-249"><em>16</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-249"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-250">各チャット ルームのメンバーシップ リストのユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="6c8be-250">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="6c8be-251"><em>個</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="6c8be-252"><em>個</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-252"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="6c8be-253"><em>約</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-253"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-254">ユーザー グループによって管理されるルーム</span><span class="sxs-lookup"><span data-stu-id="6c8be-254">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="6c8be-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="6c8be-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-256"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="6c8be-257"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-257"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-258">すべてのチャット ルームのユーザー グループ ベースのメンバーシップ エンティティ</span><span class="sxs-lookup"><span data-stu-id="6c8be-258">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-259">155200</span><span class="sxs-lookup"><span data-stu-id="6c8be-259">155,200</span></span></p></td>
<td><p><span data-ttu-id="6c8be-260">5173</span><span class="sxs-lookup"><span data-stu-id="6c8be-260">5173</span></span></p></td>
<td><p><span data-ttu-id="6c8be-261">68</span><span class="sxs-lookup"><span data-stu-id="6c8be-261">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-262">すべてのチャット ルームのユーザー ベースのメンバーシップ エンティティ</span><span class="sxs-lookup"><span data-stu-id="6c8be-262">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-263">465600</span><span class="sxs-lookup"><span data-stu-id="6c8be-263">465,600</span></span></p></td>
<td><p><span data-ttu-id="6c8be-264">77600</span><span class="sxs-lookup"><span data-stu-id="6c8be-264">77,600</span></span></p></td>
<td><p><span data-ttu-id="6c8be-265">72000</span><span class="sxs-lookup"><span data-stu-id="6c8be-265">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-266">各チャット ルームのマネージャーの一覧、発表者の一覧、およびスコープの一覧のユーザーおよびユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="6c8be-266">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="6c8be-267">6 </span><span class="sxs-lookup"><span data-stu-id="6c8be-267">6</span></span></p></td>
<td><p><span data-ttu-id="6c8be-268">6 </span><span class="sxs-lookup"><span data-stu-id="6c8be-268">6</span></span></p></td>
<td><p><span data-ttu-id="6c8be-269">6 </span><span class="sxs-lookup"><span data-stu-id="6c8be-269">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-270">すべてのチャット ルームのマネージャーの一覧、発表者の一覧、およびスコープの一覧のユーザーおよびユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="6c8be-270">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="6c8be-271">192000</span><span class="sxs-lookup"><span data-stu-id="6c8be-271">192,000</span></span></p></td>
<td><p><span data-ttu-id="6c8be-272">6400</span><span class="sxs-lookup"><span data-stu-id="6c8be-272">6400</span></span></p></td>
<td><p><span data-ttu-id="6c8be-273">60</span><span class="sxs-lookup"><span data-stu-id="6c8be-273">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-274">アクセス制御エントリ</span><span class="sxs-lookup"><span data-stu-id="6c8be-274">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="6c8be-275">704160</span><span class="sxs-lookup"><span data-stu-id="6c8be-275">704,160</span></span></p></td>
<td><p><span data-ttu-id="6c8be-276">26768</span><span class="sxs-lookup"><span data-stu-id="6c8be-276">26,768</span></span></p></td>
<td><p><span data-ttu-id="6c8be-277">160</span><span class="sxs-lookup"><span data-stu-id="6c8be-277">160</span></span></p></td>
<td><p><span data-ttu-id="6c8be-278">731088</span><span class="sxs-lookup"><span data-stu-id="6c8be-278">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-279">最大アクセス制御エントリ</span><span class="sxs-lookup"><span data-stu-id="6c8be-279">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="6c8be-280">200万</span><span class="sxs-lookup"><span data-stu-id="6c8be-280">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6c8be-281">前のサンプルでは、推奨ガイドラインに従って常設チャットサーバーを展開すると、コンプライアンスが有効になっている4台のサーバープールで最大8万のアクティブユーザーを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-281">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="6c8be-p110">このサンプルは、小規模 (常時 30 のアクティブ ユーザー)、中規模 (150 のアクティブ ユーザー)、および大規模 (16,000 のアクティブ ユーザー) として分類されたチャット ルームを示しています。 特定のサイズのチャット ルームの数は、次の合計数に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-p110">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users). The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="6c8be-284">システム内のアクティブ ユーザー</span><span class="sxs-lookup"><span data-stu-id="6c8be-284">Active users in the system</span></span>

  - <span data-ttu-id="6c8be-285">特定のサイズのチャット ルームのアクティブ ユーザー</span><span class="sxs-lookup"><span data-stu-id="6c8be-285">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="6c8be-286">単一ユーザーが参加する特定のサイズのチャット ルーム</span><span class="sxs-lookup"><span data-stu-id="6c8be-286">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="6c8be-p111">上記の処理能力の計画表では、各チャット ルームについて、チャット ルームに直接割り当てられたエントリなど、チャット ルームに関連付けられたアクセス制御エントリの数を示しています。アクセス制御リスト (ACL) を使用して、個々のチャット ルームへのアクセスを制御できます。また、カテゴリ レベルでアクセスを制御することもできます。ACL では、個々のアクセス制御エントリは、ユーザー グループ (セキュリティ グループ、配布リストなど) または単一ユーザーのどちらかになります。アクセス制御エントリは、チャット ルームのマネージャー、発表者、およびメンバーに対して定義できます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-p111">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room. You can control access to individual chat rooms by using access control lists (ACLs). You can also control access at the category level. In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user. You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6c8be-p112">チャット ルームの管理戦略を計画する際に、許容されるアクセス制御エントリの合計数は 200 万であることに注意してください。計算されたアクセス制御エントリが 200 万を超える場合は、サーバーのパフォーマンスが大幅に低下する可能性があります。この問題を可能な限り回避するには、アクセス制御エントリが個々のユーザーではなくユーザー グループとなるようにします。</span><span class="sxs-lookup"><span data-stu-id="6c8be-p112">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million. If the calculated access control entries exceed 2 million, server performance could degrade significantly. To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="6c8be-295">チャット ルームのアクセスを招待別に管理するための処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="6c8be-295">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="6c8be-296">次の容量計画の表を使用して、会議出席依頼を送信するように構成されている場合に常設チャットサーバーが作成して保存する招待の数を把握できます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-296">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="6c8be-297">カテゴリの招待を管理するには、Lync Server コントロールパネルの [ **チャットルームのカテゴリ設定** ] ページを使用するか、Windows PowerShell コマンドレットを使用して **new-cspersistentchatcategory**を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-297">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="6c8be-298">チャットルームの招待を管理するには、Lync クライアントから起動されたチャットルームの **管理** ページを使用するか、または Windows PowerShell コマンドレットを使用して、 **clear-cspersistentchatroom**を行います。</span><span class="sxs-lookup"><span data-stu-id="6c8be-298">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="6c8be-299">次の表のサンプル データでは、[**チャット ルームの設定**] ページの [**招待**] オプションがすべてのチャット ルームの 50 パーセントで [**はい**] に設定されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-299">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6c8be-300">サーバーによって生成された招待の数の計算値が 100 万を超えると、サーバーのパフォーマンスが大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-300">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="6c8be-301">この問題を回避するには、招待を送信するように構成されているチャットルームの数を最小限に抑えるか、招待状を送信するように構成されているチャットルームに参加できるユーザーの数を制限してください。</span><span class="sxs-lookup"><span data-stu-id="6c8be-301">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="6c8be-302">招待別のチャット ルームのアクセスのサンプル</span><span class="sxs-lookup"><span data-stu-id="6c8be-302">Chat Room Access by Invitation Sample</span></span>

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
<th><span data-ttu-id="6c8be-303">小規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="6c8be-303">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="6c8be-304">中規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="6c8be-304">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="6c8be-305">大規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="6c8be-305">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="6c8be-306">合計</span><span class="sxs-lookup"><span data-stu-id="6c8be-306">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-307">チャット ルームにアクセスできるユーザー数</span><span class="sxs-lookup"><span data-stu-id="6c8be-307">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="6c8be-308">ルームあたり 30 ユーザー</span><span class="sxs-lookup"><span data-stu-id="6c8be-308">30 per room</span></span></p></td>
<td><p><span data-ttu-id="6c8be-309">ルームあたり 150 ユーザー</span><span class="sxs-lookup"><span data-stu-id="6c8be-309">150 per room</span></span></p></td>
<td><p><span data-ttu-id="6c8be-310">ルームあたり 16,000 ユーザー</span><span class="sxs-lookup"><span data-stu-id="6c8be-310">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-311">招待があるルームの割合</span><span class="sxs-lookup"><span data-stu-id="6c8be-311">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="6c8be-312">50%</span><span class="sxs-lookup"><span data-stu-id="6c8be-312">50%</span></span></p></td>
<td><p><span data-ttu-id="6c8be-313">50%</span><span class="sxs-lookup"><span data-stu-id="6c8be-313">50%</span></span></p></td>
<td><p><span data-ttu-id="6c8be-314">50%</span><span class="sxs-lookup"><span data-stu-id="6c8be-314">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-315">招待を送信するように構成されているチャット ルーム</span><span class="sxs-lookup"><span data-stu-id="6c8be-315">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="6c8be-316"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-316"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="6c8be-317"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-317"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="6c8be-318"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-318"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-319">チャット ルームにアクセスできるユーザー</span><span class="sxs-lookup"><span data-stu-id="6c8be-319">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="6c8be-320"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-320"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="6c8be-321"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-321"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="6c8be-322"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="6c8be-322"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-323">常設チャットサーバーによって生成された招待</span><span class="sxs-lookup"><span data-stu-id="6c8be-323">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="6c8be-324">96万</span><span class="sxs-lookup"><span data-stu-id="6c8be-324">960,000</span></span></p></td>
<td><p><span data-ttu-id="6c8be-325">12万</span><span class="sxs-lookup"><span data-stu-id="6c8be-325">120,000</span></span></p></td>
<td><p><span data-ttu-id="6c8be-326">80,000</span><span class="sxs-lookup"><span data-stu-id="6c8be-326">80,000</span></span></p></td>
<td><p><span data-ttu-id="6c8be-327">116万</span><span class="sxs-lookup"><span data-stu-id="6c8be-327">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-328">招待の上限数</span><span class="sxs-lookup"><span data-stu-id="6c8be-328">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="6c8be-329">200万</span><span class="sxs-lookup"><span data-stu-id="6c8be-329">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-330">モデル 1 - 1 日、1 ルームあたりの想定メッセージ数で開始</span><span class="sxs-lookup"><span data-stu-id="6c8be-330">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-331">ルームあたりのチャット レート (1 日あたり)</span><span class="sxs-lookup"><span data-stu-id="6c8be-331">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="6c8be-332">50</span><span class="sxs-lookup"><span data-stu-id="6c8be-332">50</span></span></p></td>
<td><p><span data-ttu-id="6c8be-333">500</span><span class="sxs-lookup"><span data-stu-id="6c8be-333">500</span></span></p></td>
<td><p><span data-ttu-id="6c8be-334">100</span><span class="sxs-lookup"><span data-stu-id="6c8be-334">100</span></span></p></td>
<td><p><span data-ttu-id="6c8be-335">650</span><span class="sxs-lookup"><span data-stu-id="6c8be-335">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-336">すべてのチャット ルームにおけるチャット レート (1 秒あたり)</span><span class="sxs-lookup"><span data-stu-id="6c8be-336">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-337">55.56</span><span class="sxs-lookup"><span data-stu-id="6c8be-337">55.56</span></span></p></td>
<td><p><span data-ttu-id="6c8be-338">18.52</span><span class="sxs-lookup"><span data-stu-id="6c8be-338">18.52</span></span></p></td>
<td><p><span data-ttu-id="6c8be-339">0.03</span><span class="sxs-lookup"><span data-stu-id="6c8be-339">0.03</span></span></p></td>
<td><p><span data-ttu-id="6c8be-340">74</span><span class="sxs-lookup"><span data-stu-id="6c8be-340">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-341">モデル 2 - 1 日、1 ユーザーあたりの投稿メッセージ数で開始</span><span class="sxs-lookup"><span data-stu-id="6c8be-341">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-342">ユーザーあたりのチャット レート (1 日あたり)</span><span class="sxs-lookup"><span data-stu-id="6c8be-342">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="6c8be-343">15 </span><span class="sxs-lookup"><span data-stu-id="6c8be-343">15</span></span></p></td>
<td><p><span data-ttu-id="6c8be-344">5 </span><span class="sxs-lookup"><span data-stu-id="6c8be-344">5</span></span></p></td>
<td><p><span data-ttu-id="6c8be-345">0.1</span><span class="sxs-lookup"><span data-stu-id="6c8be-345">0.1</span></span></p></td>
<td><p><span data-ttu-id="6c8be-346">1280</span><span class="sxs-lookup"><span data-stu-id="6c8be-346">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-347">ルームあたりのチャット レート (1 日あたり)</span><span class="sxs-lookup"><span data-stu-id="6c8be-347">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="6c8be-348">38</span><span class="sxs-lookup"><span data-stu-id="6c8be-348">38</span></span></p></td>
<td><p><span data-ttu-id="6c8be-349">375</span><span class="sxs-lookup"><span data-stu-id="6c8be-349">375</span></span></p></td>
<td><p><span data-ttu-id="6c8be-350">800</span><span class="sxs-lookup"><span data-stu-id="6c8be-350">800</span></span></p></td>
<td><p><span data-ttu-id="6c8be-351">1213</span><span class="sxs-lookup"><span data-stu-id="6c8be-351">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-352">すべてのチャット ルームにおけるチャット レート (1 秒あたり)</span><span class="sxs-lookup"><span data-stu-id="6c8be-352">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-353">41.67</span><span class="sxs-lookup"><span data-stu-id="6c8be-353">41.67</span></span></p></td>
<td><p><span data-ttu-id="6c8be-354">13.89</span><span class="sxs-lookup"><span data-stu-id="6c8be-354">13.89</span></span></p></td>
<td><p><span data-ttu-id="6c8be-355">0.28</span><span class="sxs-lookup"><span data-stu-id="6c8be-355">0.28</span></span></p></td>
<td><p><span data-ttu-id="6c8be-356">56</span><span class="sxs-lookup"><span data-stu-id="6c8be-356">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="6c8be-357">常設チャットサーバーのパフォーマンスユーザーモデル</span><span class="sxs-lookup"><span data-stu-id="6c8be-357">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="6c8be-358">次の表では、常設チャットサーバーのユーザーモデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-358">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="6c8be-359">この表は、処理能力の計画の要件に関する基礎を提供し、4 台のサーバーで同時に 80,000 のユーザーに対処できる一般的な組織を表しています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-359">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="6c8be-360">常設チャットサーバーのパフォーマンスユーザーモデル</span><span class="sxs-lookup"><span data-stu-id="6c8be-360">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-361">アクティブな接続ユーザー数</span><span class="sxs-lookup"><span data-stu-id="6c8be-361">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="6c8be-362">80,000</span><span class="sxs-lookup"><span data-stu-id="6c8be-362">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-363">常設チャットサーバーサービスインスタンスの数</span><span class="sxs-lookup"><span data-stu-id="6c8be-363">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="6c8be-364">4 </span><span class="sxs-lookup"><span data-stu-id="6c8be-364">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-365">小規模チャット ルームのサイズ</span><span class="sxs-lookup"><span data-stu-id="6c8be-365">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-366">30 ユーザー</span><span class="sxs-lookup"><span data-stu-id="6c8be-366">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-367">中規模チャット ルームのサイズ</span><span class="sxs-lookup"><span data-stu-id="6c8be-367">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-368">150 ユーザー</span><span class="sxs-lookup"><span data-stu-id="6c8be-368">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-369">大規模チャット ルームのサイズ</span><span class="sxs-lookup"><span data-stu-id="6c8be-369">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-370">16,000 ユーザー</span><span class="sxs-lookup"><span data-stu-id="6c8be-370">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-371">チャット ルームの合計数</span><span class="sxs-lookup"><span data-stu-id="6c8be-371">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-372">33077</span><span class="sxs-lookup"><span data-stu-id="6c8be-372">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-373">小規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="6c8be-373">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-374">32000</span><span class="sxs-lookup"><span data-stu-id="6c8be-374">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-375">中規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="6c8be-375">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-376">1067</span><span class="sxs-lookup"><span data-stu-id="6c8be-376">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-377">大規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="6c8be-377">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-378">10  </span><span class="sxs-lookup"><span data-stu-id="6c8be-378">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-379">ユーザーあたりのチャット ルームの合計数</span><span class="sxs-lookup"><span data-stu-id="6c8be-379">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="6c8be-380">16 </span><span class="sxs-lookup"><span data-stu-id="6c8be-380">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-381">ユーザーあたりの小規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="6c8be-381">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="6c8be-382">12 </span><span class="sxs-lookup"><span data-stu-id="6c8be-382">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-383">ユーザーあたりの中規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="6c8be-383">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="6c8be-384">pbm-2</span><span class="sxs-lookup"><span data-stu-id="6c8be-384">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-385">ユーザーあたりの大規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="6c8be-385">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="6c8be-386">pbm-2</span><span class="sxs-lookup"><span data-stu-id="6c8be-386">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-387">ユーザーあたりの参加ルーム数</span><span class="sxs-lookup"><span data-stu-id="6c8be-387">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="6c8be-388">ソケット</span><span class="sxs-lookup"><span data-stu-id="6c8be-388">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-389">ピーク時の参加レート</span><span class="sxs-lookup"><span data-stu-id="6c8be-389">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="6c8be-390">10/秒</span><span class="sxs-lookup"><span data-stu-id="6c8be-390">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-391">チャット レート合計</span><span class="sxs-lookup"><span data-stu-id="6c8be-391">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="6c8be-392">24/秒</span><span class="sxs-lookup"><span data-stu-id="6c8be-392">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-393">小規模チャット ルームのチャット レート</span><span class="sxs-lookup"><span data-stu-id="6c8be-393">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-394">22.22/second</span><span class="sxs-lookup"><span data-stu-id="6c8be-394">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-395">中規模チャット ルームのチャット レート</span><span class="sxs-lookup"><span data-stu-id="6c8be-395">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-396">1.67/second</span><span class="sxs-lookup"><span data-stu-id="6c8be-396">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-397">大規模チャット ルームのチャット レート</span><span class="sxs-lookup"><span data-stu-id="6c8be-397">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6c8be-398">~ 0.15/秒</span><span class="sxs-lookup"><span data-stu-id="6c8be-398">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-399">招待が構成されているチャット ルームの割合</span><span class="sxs-lookup"><span data-stu-id="6c8be-399">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="6c8be-400">50%</span><span class="sxs-lookup"><span data-stu-id="6c8be-400">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-401">直接メンバーシップの割合</span><span class="sxs-lookup"><span data-stu-id="6c8be-401">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="6c8be-402">50%</span><span class="sxs-lookup"><span data-stu-id="6c8be-402">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-403">グループ メンバーシップの割合</span><span class="sxs-lookup"><span data-stu-id="6c8be-403">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="6c8be-404">50%</span><span class="sxs-lookup"><span data-stu-id="6c8be-404">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-405">Active Directory ドメインサービスの先祖所属の平均数</span><span class="sxs-lookup"><span data-stu-id="6c8be-405">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="6c8be-406">100 - 200</span><span class="sxs-lookup"><span data-stu-id="6c8be-406">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-407">ユーザーごとの加入する連絡先の数</span><span class="sxs-lookup"><span data-stu-id="6c8be-407">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="6c8be-408">80</span><span class="sxs-lookup"><span data-stu-id="6c8be-408">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-409">ユーザーあたりの平均エンドポイント数</span><span class="sxs-lookup"><span data-stu-id="6c8be-409">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="6c8be-410">1.5</span><span class="sxs-lookup"><span data-stu-id="6c8be-410">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-411">エンドポイントあたりの表示されるチャット ルームの平均数</span><span class="sxs-lookup"><span data-stu-id="6c8be-411">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="6c8be-412">1.5</span><span class="sxs-lookup"><span data-stu-id="6c8be-412">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-413">ユーザーあたりの表示されるチャット ルームの平均数</span><span class="sxs-lookup"><span data-stu-id="6c8be-413">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="6c8be-414">2.25 (1 ルームと 2 ルームが 50% ずつ)。最大 6 ルームがオープン (1 モニターにつき 1 つ)</span><span class="sxs-lookup"><span data-stu-id="6c8be-414">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-415">一定間隔でポーリングされる参加者の数</span><span class="sxs-lookup"><span data-stu-id="6c8be-415">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="6c8be-416">25 (表示されるチャット ルーム 1 つあたり)</span><span class="sxs-lookup"><span data-stu-id="6c8be-416">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-417">ポーリング間隔の長さ</span><span class="sxs-lookup"><span data-stu-id="6c8be-417">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="6c8be-418">5 分</span><span class="sxs-lookup"><span data-stu-id="6c8be-418">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-419">1 秒あたりにポーリングされる参加者の数</span><span class="sxs-lookup"><span data-stu-id="6c8be-419">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="6c8be-420">15,000</span><span class="sxs-lookup"><span data-stu-id="6c8be-420">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8be-421">1 時間あたりのユーザーごとのプレゼンス変更の数</span><span class="sxs-lookup"><span data-stu-id="6c8be-421">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="6c8be-422">6 </span><span class="sxs-lookup"><span data-stu-id="6c8be-422">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8be-423">1 秒あたりのプレゼンス変更の数</span><span class="sxs-lookup"><span data-stu-id="6c8be-423">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="6c8be-424">133.33</span><span class="sxs-lookup"><span data-stu-id="6c8be-424">133.33</span></span></p></td>
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

