---
title: 'Lync Server 2013: 常設チャットサーバーのキャパシティ計画'
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
ms.openlocfilehash: dde4bcb499e38e729850f06bb08590bf537696e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ee218-102">Lync Server 2013 の常設チャットサーバーのキャパシティ計画</span><span class="sxs-lookup"><span data-stu-id="ee218-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee218-103">_**最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="ee218-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="ee218-104">常設チャットサーバーでは、ユーザーがリアルタイムでリアルタイムでチャットを行うことができます。これは、今後の取得や検索のために保持されます。</span><span class="sxs-lookup"><span data-stu-id="ee218-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="ee218-105">ユーザーのメールボックスに保存されているグループインスタントメッセージ (IM) とは異なり、会話履歴が構成されていると、常設チャットサーバーのセッションが開かれたままになり、コンテンツはサーバーに保存され、メッセージ、ファイル、Url、その他のデータが含まれます。進行中の会話。</span><span class="sxs-lookup"><span data-stu-id="ee218-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="ee218-106">キャパシティプランニングは、常設チャットサーバーの展開を準備するための重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="ee218-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="ee218-107">このトピックでは、サポートされている常設チャットサーバートポロジとキャパシティ計画の表について詳しく説明します。これを使用すると、展開に最適な構成を決定することができます。</span><span class="sxs-lookup"><span data-stu-id="ee218-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="ee218-108">また、ピーク時に容量を大きくする必要がある常設チャットサーバーの展開を適切に管理する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="ee218-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="ee218-109">常設チャットサーバーをダウンロードするには、の「Microsoft Lync Server 13 常設チャット[http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)サーバー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee218-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="ee218-110">常設チャットサーバーのインストールの詳細については、展開ドキュメントの「lync server [2013 での](lync-server-2013-installing-persistent-chat-server.md)常設チャットサーバーのインストールと[常設チャット2013サーバーの構成](lync-server-2013-configuring-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee218-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="ee218-111">Lync Server 計画ツールなどのサポートツールを利用すると、容量の計画をさらに助けることができます。</span><span class="sxs-lookup"><span data-stu-id="ee218-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="ee218-112">計画ツールの詳細については、計画ドキュメントの「 [Lync Server 2013 の計画プロセスの開始](lync-server-2013-beginning-the-planning-process.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee218-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="ee218-113">常設チャットサーバーでサポートされているトポロジ</span><span class="sxs-lookup"><span data-stu-id="ee218-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="ee218-114">常設チャットサーバーは、単一サーバープールまたは複数サーバープール、または単一プールトポロジまたは複数プールトポロジで展開できます。</span><span class="sxs-lookup"><span data-stu-id="ee218-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="ee218-115">新しい Lync Server 2013 の展開用に、Standard Edition server 上の常設チャットサーバーもサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ee218-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="ee218-116">ただし、パフォーマンスと規模が影響を受けます。また、この新しい展開には高可用性オプションがないため、これは主に概念や評価の証明のために使用することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ee218-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ee218-117">両方のトポロジの詳細については、このドキュメントの「<A href="lync-server-2013-planning-for-persistent-chat-server.md">常設チャット2013サーバーの計画</A>」を参照してください。展開ドキュメントには、「 <A href="lync-server-2013-deploying-persistent-chat-server.md">lync server 2013 での常設チャットサーバー</A>の設定と展開」が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ee218-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="ee218-118">単一サーバートポロジ</span><span class="sxs-lookup"><span data-stu-id="ee218-118">Single-Server Topology</span></span>

<span data-ttu-id="ee218-119">常設チャットサーバー向けの最小構成と最も簡単な展開は、1つの常設チャットサーバーのフロントエンドサーバートポロジです。</span><span class="sxs-lookup"><span data-stu-id="ee218-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="ee218-120">この展開を行うには、常設チャットサーバーを実行する単一のサーバー (必要に応じてコンプライアンスサービスを実行します)、SQL Server データベースをホストしているサーバー、コンプライアンスが必要な場合は、コンプライアンスデータ。</span><span class="sxs-lookup"><span data-stu-id="ee218-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ee218-121">トポロジビルダーでシングルサーバー展開として開始された常設チャットサーバープールにサーバーを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="ee218-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="ee218-122">単一のサーバーを使用している場合でも、複数サーバープールトポロジの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ee218-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="ee218-123">これは、必要に応じて後でサーバーを追加できるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="ee218-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="ee218-124">次の図は、コンプライアンスを備えた単一の常設チャットサーバーフロントエンドサーバーのトポロジの必須コンポーネントとオプションコンポーネントをすべて示しています。</span><span class="sxs-lookup"><span data-stu-id="ee218-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="ee218-125">**1つの常設チャットサーバー**</span><span class="sxs-lookup"><span data-stu-id="ee218-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="ee218-126">![コンプライアンスサービスを備えた単一サーバートポロジ](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "コンプライアンスサービスを備えた単一サーバートポロジ")</span><span class="sxs-lookup"><span data-stu-id="ee218-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="ee218-127">複数サーバートポロジ</span><span class="sxs-lookup"><span data-stu-id="ee218-127">Multiple-Server Topology</span></span>

<span data-ttu-id="ee218-128">より多くの容量と信頼性を実現するには、「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」で説明されているように、複数サーバートポロジを展開します。</span><span class="sxs-lookup"><span data-stu-id="ee218-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="ee218-129">複数サーバーのトポロジには、常設チャットサーバーを実行しているアクティブなコンピューターを4つまで含めることができます (高可用性および障害回復構成では最大8個まで可能)。ただし、4つはアクティブ、残りの4つはスタンバイ状態になります。</span><span class="sxs-lookup"><span data-stu-id="ee218-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="ee218-130">各サーバーは、最大で2万の同時ユーザーをサポートできます。合計で8万の同時使用ユーザーは、4台のサーバーで常設チャットサーバープールに接続されています。</span><span class="sxs-lookup"><span data-stu-id="ee218-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="ee218-131">複数サーバーのトポロジは、複数のサーバーが常設チャットサーバーをホストしていることを除いて、単一サーバートポロジと同じで、拡大縮小できます。</span><span class="sxs-lookup"><span data-stu-id="ee218-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="ee218-132">常設チャットサーバーを実行している複数のコンピューターは、Lync Server とコンプライアンスサービスと同じ Active Directory ドメインサービスドメインに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee218-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="ee218-133">次の図は、常設チャットサーバーを実行している複数のコンピューター、オプションのコンプライアンスサービス、および別のコンプライアンスデータベースの複数サーバートポロジのすべてのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="ee218-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="ee218-134">**複数の常設チャットサーバー**</span><span class="sxs-lookup"><span data-stu-id="ee218-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="ee218-135">![複数サーバートポロジ](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "複数サーバートポロジ")</span><span class="sxs-lookup"><span data-stu-id="ee218-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="ee218-136">4サーバーの常設チャットサーバーの展開では、8万ユーザーは同時にサインインして常設チャットを使用することができます。ロードは、サーバーあたり2万ユーザーに均等に配布されます。</span><span class="sxs-lookup"><span data-stu-id="ee218-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="ee218-137">1つのサーバーが利用できなくなった場合、そのサーバーに接続されているユーザーは、常設チャットサーバーにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ee218-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="ee218-138">切断されたユーザーは、利用できなくなったサーバーが復元されるまでは、残りのサーバーに自動的に転送されます。</span><span class="sxs-lookup"><span data-stu-id="ee218-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="ee218-139">ネットワーク上での常設チャットトラフィックの量によっては、この転送には数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ee218-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="ee218-140">残りの各サーバーは、最大3万ユーザーとしてホストされている可能性があるため、パフォーマンスの問題を回避するために、使用できないサーバーをできるだけ早く復元することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ee218-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="ee218-141">それ以外の場合は、Topology Builder または Windows PowerShell コマンドレット**CsPersistentChatActiveServer**を使用して、別の常設チャットサーバーを利用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ee218-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="ee218-142">常設チャットサーバーのキャパシティプランニング</span><span class="sxs-lookup"><span data-stu-id="ee218-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="ee218-143">常設チャットサーバーの容量計画については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee218-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="ee218-144">これは、常設チャットサーバー設定の変更による容量機能への影響をモデル化しています。</span><span class="sxs-lookup"><span data-stu-id="ee218-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="ee218-145">常設チャットサーバーの最大キャパシティの計画</span><span class="sxs-lookup"><span data-stu-id="ee218-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="ee218-146">次のサンプル表を使用して、サポートすることができるユーザー数を判断します。</span><span class="sxs-lookup"><span data-stu-id="ee218-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="ee218-147">常設チャットサーバープールの最大容量のサンプル</span><span class="sxs-lookup"><span data-stu-id="ee218-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee218-148">アクティブな常設チャットサービスのインスタンス</span><span class="sxs-lookup"><span data-stu-id="ee218-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="ee218-149"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="ee218-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-150">常設チャットサービスのインスタンス</span><span class="sxs-lookup"><span data-stu-id="ee218-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="ee218-151"><em>8 (4 は非アクティブにする必要がありますが、最大値は4です)</em></span><span class="sxs-lookup"><span data-stu-id="ee218-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-152">アクティブな接続ユーザー数</span><span class="sxs-lookup"><span data-stu-id="ee218-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="ee218-153"><em>80,000</em></span><span class="sxs-lookup"><span data-stu-id="ee218-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-154">プロビジョニング対象ユーザーの総数</span><span class="sxs-lookup"><span data-stu-id="ee218-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="ee218-155">150,000</span><span class="sxs-lookup"><span data-stu-id="ee218-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-156">エンドポイント数</span><span class="sxs-lookup"><span data-stu-id="ee218-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="ee218-157">120,000</span><span class="sxs-lookup"><span data-stu-id="ee218-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ee218-158">上記のサンプルでは、常設チャットサーバーで許可されているユーザーの最大数をサポートしています。常設チャットサービスの4つのサーバーとインスタンス (高可用性と障害回復のために常設チャットサーバーを実行している場合は4つのパッシブサーバー、サーバーあたりは2万ユーザー)、合計8万のアクティブユーザーを対象とします。</span><span class="sxs-lookup"><span data-stu-id="ee218-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="ee218-159">常設チャットルームへのアクセスを管理するためのキャパシティ計画</span><span class="sxs-lookup"><span data-stu-id="ee218-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="ee218-160">次のサンプルテーブルは、常設チャットサーバープールでの常設チャットルームへのアクセスを管理するための計画に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ee218-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="ee218-161">チャットルームへのアクセスサンプルの管理</span><span class="sxs-lookup"><span data-stu-id="ee218-161">Managing Chat Room Access Sample</span></span>

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
<th><span data-ttu-id="ee218-162">小規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="ee218-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="ee218-163">中規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="ee218-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="ee218-164">大規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="ee218-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="ee218-165">合計</span><span class="sxs-lookup"><span data-stu-id="ee218-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee218-166">チャット ルームのサイズ (接続ユーザー数)</span><span class="sxs-lookup"><span data-stu-id="ee218-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="ee218-167">ルームあたり 30 ユーザー</span><span class="sxs-lookup"><span data-stu-id="ee218-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="ee218-168">ルームあたり 150 ユーザー</span><span class="sxs-lookup"><span data-stu-id="ee218-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="ee218-169">ルームあたり 16,000 ユーザー</span><span class="sxs-lookup"><span data-stu-id="ee218-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-170">チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="ee218-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-171">32,000</span><span class="sxs-lookup"><span data-stu-id="ee218-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="ee218-172">1,067</span><span class="sxs-lookup"><span data-stu-id="ee218-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="ee218-173">常用</span><span class="sxs-lookup"><span data-stu-id="ee218-173">10</span></span></p></td>
<td><p><span data-ttu-id="ee218-174">33,077</span><span class="sxs-lookup"><span data-stu-id="ee218-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-175">大会議室の割合 (%)</span><span class="sxs-lookup"><span data-stu-id="ee218-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="ee218-176">1%</span><span class="sxs-lookup"><span data-stu-id="ee218-176">1%</span></span></p></td>
<td><p><span data-ttu-id="ee218-177">1%</span><span class="sxs-lookup"><span data-stu-id="ee218-177">1%</span></span></p></td>
<td><p><span data-ttu-id="ee218-178">50%</span><span class="sxs-lookup"><span data-stu-id="ee218-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-179">オープン ルームの割合 (%)</span><span class="sxs-lookup"><span data-stu-id="ee218-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="ee218-180">3%</span><span class="sxs-lookup"><span data-stu-id="ee218-180">3%</span></span></p></td>
<td><p><span data-ttu-id="ee218-181">3%</span><span class="sxs-lookup"><span data-stu-id="ee218-181">3%</span></span></p></td>
<td><p><span data-ttu-id="ee218-182">50%</span><span class="sxs-lookup"><span data-stu-id="ee218-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-183">オープン ルーム数 (明示的なメンバーシップなし)</span><span class="sxs-lookup"><span data-stu-id="ee218-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="ee218-184">960</span><span class="sxs-lookup"><span data-stu-id="ee218-184">960</span></span></p></td>
<td><p><span data-ttu-id="ee218-185">32</span><span class="sxs-lookup"><span data-stu-id="ee218-185">32</span></span></p></td>
<td><p><span data-ttu-id="ee218-186">5</span><span class="sxs-lookup"><span data-stu-id="ee218-186">5</span></span></p></td>
<td><p><span data-ttu-id="ee218-187">997</span><span class="sxs-lookup"><span data-stu-id="ee218-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-188">非オープン ルーム数 (明示的なメンバーシップがある通常のルーム)</span><span class="sxs-lookup"><span data-stu-id="ee218-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="ee218-189">31,040</span><span class="sxs-lookup"><span data-stu-id="ee218-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="ee218-190">1.035</span><span class="sxs-lookup"><span data-stu-id="ee218-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="ee218-191">5</span><span class="sxs-lookup"><span data-stu-id="ee218-191">5</span></span></p></td>
<td><p><span data-ttu-id="ee218-192">32,080</span><span class="sxs-lookup"><span data-stu-id="ee218-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-193">大会議室数 (追加の発表者エントリ)</span><span class="sxs-lookup"><span data-stu-id="ee218-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="ee218-194">0</span><span class="sxs-lookup"><span data-stu-id="ee218-194">0</span></span></p></td>
<td><p><span data-ttu-id="ee218-195">32</span><span class="sxs-lookup"><span data-stu-id="ee218-195">32</span></span></p></td>
<td><p><span data-ttu-id="ee218-196">5</span><span class="sxs-lookup"><span data-stu-id="ee218-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-197">直接メンバーシップによって管理されるルーム</span><span class="sxs-lookup"><span data-stu-id="ee218-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="ee218-198">50%</span><span class="sxs-lookup"><span data-stu-id="ee218-198">50%</span></span></p></td>
<td><p><span data-ttu-id="ee218-199">10%</span><span class="sxs-lookup"><span data-stu-id="ee218-199">10%</span></span></p></td>
<td><p><span data-ttu-id="ee218-200">0%</span><span class="sxs-lookup"><span data-stu-id="ee218-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-201">ユーザー グループによって管理されるルーム</span><span class="sxs-lookup"><span data-stu-id="ee218-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="ee218-202">50%</span><span class="sxs-lookup"><span data-stu-id="ee218-202">50%</span></span></p></td>
<td><p><span data-ttu-id="ee218-203">90%</span><span class="sxs-lookup"><span data-stu-id="ee218-203">90%</span></span></p></td>
<td><p><span data-ttu-id="ee218-204">100%</span><span class="sxs-lookup"><span data-stu-id="ee218-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-205">各チャット ルームのメンバーシップ一覧におけるユーザー グループ数 (オープン ルーム (明示的には指定されていない))</span><span class="sxs-lookup"><span data-stu-id="ee218-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="ee218-206">0</span><span class="sxs-lookup"><span data-stu-id="ee218-206">0</span></span></p></td>
<td><p><span data-ttu-id="ee218-207">0</span><span class="sxs-lookup"><span data-stu-id="ee218-207">0</span></span></p></td>
<td><p><span data-ttu-id="ee218-208">0</span><span class="sxs-lookup"><span data-stu-id="ee218-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-209">各チャット ルームのメンバーシップ一覧におけるユーザー数 (非オープン ルーム)</span><span class="sxs-lookup"><span data-stu-id="ee218-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-210">求める</span><span class="sxs-lookup"><span data-stu-id="ee218-210">30</span></span></p></td>
<td><p><span data-ttu-id="ee218-211">150</span><span class="sxs-lookup"><span data-stu-id="ee218-211">150</span></span></p></td>
<td><p><span data-ttu-id="ee218-212">16,000</span><span class="sxs-lookup"><span data-stu-id="ee218-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-213">各チャット ルームのメンバーシップ一覧におけるユーザー グループ数 (非オープン ルーム)</span><span class="sxs-lookup"><span data-stu-id="ee218-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-214">3</span><span class="sxs-lookup"><span data-stu-id="ee218-214">3</span></span></p></td>
<td><p><span data-ttu-id="ee218-215">5</span><span class="sxs-lookup"><span data-stu-id="ee218-215">5</span></span></p></td>
<td><p><span data-ttu-id="ee218-216">常用</span><span class="sxs-lookup"><span data-stu-id="ee218-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-217">各チャット ルームのマネージャー一覧におけるユーザーおよびユーザー グループ数 (オープン ルームと非オープン ルーム)</span><span class="sxs-lookup"><span data-stu-id="ee218-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="ee218-218">6</span><span class="sxs-lookup"><span data-stu-id="ee218-218">6</span></span></p></td>
<td><p><span data-ttu-id="ee218-219">6</span><span class="sxs-lookup"><span data-stu-id="ee218-219">6</span></span></p></td>
<td><p><span data-ttu-id="ee218-220">6</span><span class="sxs-lookup"><span data-stu-id="ee218-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-221">各大会議室のチャット ルームの発表者一覧におけるユーザーおよびユーザー グループ数 (オープン ルームと非オープン ルーム)</span><span class="sxs-lookup"><span data-stu-id="ee218-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="ee218-222">6</span><span class="sxs-lookup"><span data-stu-id="ee218-222">6</span></span></p></td>
<td><p><span data-ttu-id="ee218-223">6</span><span class="sxs-lookup"><span data-stu-id="ee218-223">6</span></span></p></td>
<td><p><span data-ttu-id="ee218-224">6</span><span class="sxs-lookup"><span data-stu-id="ee218-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-225">すべての非オープン ルームにおけるユーザー ベースのメンバーシップ エンティティ数</span><span class="sxs-lookup"><span data-stu-id="ee218-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-226">465,600</span><span class="sxs-lookup"><span data-stu-id="ee218-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="ee218-227">15,520</span><span class="sxs-lookup"><span data-stu-id="ee218-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-228">すべての非オープン ルームにおけるユーザー グループ ベースのメンバーシップ エンティティ数</span><span class="sxs-lookup"><span data-stu-id="ee218-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-229">46,560</span><span class="sxs-lookup"><span data-stu-id="ee218-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="ee218-230">4656</span><span class="sxs-lookup"><span data-stu-id="ee218-230">4656</span></span></p></td>
<td><p><span data-ttu-id="ee218-231">50</span><span class="sxs-lookup"><span data-stu-id="ee218-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-232">すべての大会議室のチャット ルームにおけるユーザーおよびユーザー グループ ベースのエンティティ数</span><span class="sxs-lookup"><span data-stu-id="ee218-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-233">0</span><span class="sxs-lookup"><span data-stu-id="ee218-233">0</span></span></p></td>
<td><p><span data-ttu-id="ee218-234">192</span><span class="sxs-lookup"><span data-stu-id="ee218-234">192</span></span></p></td>
<td><p><span data-ttu-id="ee218-235">50</span><span class="sxs-lookup"><span data-stu-id="ee218-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-236">すべてのチャット ルーム マネージャー一覧におけるユーザーおよびユーザー グループ ベースのマネージャー エンティティ数</span><span class="sxs-lookup"><span data-stu-id="ee218-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="ee218-237">192,000</span><span class="sxs-lookup"><span data-stu-id="ee218-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="ee218-238">6,400</span><span class="sxs-lookup"><span data-stu-id="ee218-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="ee218-239">60</span><span class="sxs-lookup"><span data-stu-id="ee218-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-240">チャット ルームあたりのアクティブ ユーザー</span><span class="sxs-lookup"><span data-stu-id="ee218-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="ee218-241"><em>求める</em></span><span class="sxs-lookup"><span data-stu-id="ee218-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="ee218-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="ee218-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="ee218-243"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="ee218-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-244">ユーザーあたりのチャット ルーム</span><span class="sxs-lookup"><span data-stu-id="ee218-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="ee218-245"><em>以内</em></span><span class="sxs-lookup"><span data-stu-id="ee218-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="ee218-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="ee218-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="ee218-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="ee218-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="ee218-248"><em>16</em></span><span class="sxs-lookup"><span data-stu-id="ee218-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-249">各チャット ルームのメンバーシップ リストのユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="ee218-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="ee218-250"><em>常用</em></span><span class="sxs-lookup"><span data-stu-id="ee218-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="ee218-251"><em>常用</em></span><span class="sxs-lookup"><span data-stu-id="ee218-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="ee218-252"><em>マート</em></span><span class="sxs-lookup"><span data-stu-id="ee218-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-253">ユーザー グループによって管理されるルーム</span><span class="sxs-lookup"><span data-stu-id="ee218-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="ee218-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="ee218-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="ee218-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="ee218-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="ee218-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="ee218-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-257">すべてのチャット ルームのユーザー グループ ベースのメンバーシップ エンティティ</span><span class="sxs-lookup"><span data-stu-id="ee218-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-258">155,200</span><span class="sxs-lookup"><span data-stu-id="ee218-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="ee218-259">5173</span><span class="sxs-lookup"><span data-stu-id="ee218-259">5173</span></span></p></td>
<td><p><span data-ttu-id="ee218-260">68</span><span class="sxs-lookup"><span data-stu-id="ee218-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-261">すべてのチャット ルームのユーザー ベースのメンバーシップ エンティティ</span><span class="sxs-lookup"><span data-stu-id="ee218-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-262">465,600</span><span class="sxs-lookup"><span data-stu-id="ee218-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="ee218-263">77,600</span><span class="sxs-lookup"><span data-stu-id="ee218-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="ee218-264">72,000</span><span class="sxs-lookup"><span data-stu-id="ee218-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-265">各チャット ルームのマネージャーの一覧、発表者の一覧、およびスコープの一覧のユーザーおよびユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="ee218-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="ee218-266">6</span><span class="sxs-lookup"><span data-stu-id="ee218-266">6</span></span></p></td>
<td><p><span data-ttu-id="ee218-267">6</span><span class="sxs-lookup"><span data-stu-id="ee218-267">6</span></span></p></td>
<td><p><span data-ttu-id="ee218-268">6</span><span class="sxs-lookup"><span data-stu-id="ee218-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-269">すべてのチャット ルームのマネージャーの一覧、発表者の一覧、およびスコープの一覧のユーザーおよびユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="ee218-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="ee218-270">192,000</span><span class="sxs-lookup"><span data-stu-id="ee218-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="ee218-271">6400</span><span class="sxs-lookup"><span data-stu-id="ee218-271">6400</span></span></p></td>
<td><p><span data-ttu-id="ee218-272">60</span><span class="sxs-lookup"><span data-stu-id="ee218-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-273">アクセス制御エントリ</span><span class="sxs-lookup"><span data-stu-id="ee218-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="ee218-274">704,160</span><span class="sxs-lookup"><span data-stu-id="ee218-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="ee218-275">26,768</span><span class="sxs-lookup"><span data-stu-id="ee218-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="ee218-276">160</span><span class="sxs-lookup"><span data-stu-id="ee218-276">160</span></span></p></td>
<td><p><span data-ttu-id="ee218-277">731,088</span><span class="sxs-lookup"><span data-stu-id="ee218-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-278">最大アクセス制御エントリ</span><span class="sxs-lookup"><span data-stu-id="ee218-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="ee218-279">2,000,000</span><span class="sxs-lookup"><span data-stu-id="ee218-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ee218-280">上記のサンプルでは、推奨されるガイドラインに従って常設チャットサーバーを展開すると、コンプライアンスが有効になっている4台のサーバープールで最大8万のアクティブユーザーを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="ee218-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="ee218-281">このサンプルは、小規模 (常時 30 のアクティブ ユーザー)、中規模 (150 のアクティブ ユーザー)、および大規模 (16,000 のアクティブ ユーザー) として分類されたチャット ルームを示しています。</span><span class="sxs-lookup"><span data-stu-id="ee218-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="ee218-282">特定のサイズのチャットルームの数は、次の合計数に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="ee218-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="ee218-283">システム内のアクティブ ユーザー</span><span class="sxs-lookup"><span data-stu-id="ee218-283">Active users in the system</span></span>

  - <span data-ttu-id="ee218-284">特定のサイズのチャット ルームのアクティブ ユーザー</span><span class="sxs-lookup"><span data-stu-id="ee218-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="ee218-285">単一ユーザーが参加する特定のサイズのチャット ルーム</span><span class="sxs-lookup"><span data-stu-id="ee218-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="ee218-p111">上記の処理能力の計画表では、各チャット ルームについて、チャット ルームに直接割り当てられたエントリなど、チャット ルームに関連付けられたアクセス制御エントリの数を示しています。アクセス制御リスト (ACL) を使用して、個々のチャット ルームへのアクセスを制御できます。また、カテゴリ レベルでアクセスを制御することもできます。ACL では、個々のアクセス制御エントリは、ユーザー グループ (セキュリティ グループ、配布リストなど) または単一ユーザーのどちらかになります。アクセス制御エントリは、チャット ルームのマネージャー、発表者、およびメンバーに対して定義できます。</span><span class="sxs-lookup"><span data-stu-id="ee218-p111">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room. You can control access to individual chat rooms by using access control lists (ACLs). You can also control access at the category level. In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user. You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ee218-p112">チャット ルームの管理戦略を計画する際に、許容されるアクセス制御エントリの合計数は 200 万であることに注意してください。計算されたアクセス制御エントリが 200 万を超える場合は、サーバーのパフォーマンスが大幅に低下する可能性があります。この問題を可能な限り回避するには、アクセス制御エントリが個々のユーザーではなくユーザー グループとなるようにします。</span><span class="sxs-lookup"><span data-stu-id="ee218-p112">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million. If the calculated access control entries exceed 2 million, server performance could degrade significantly. To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="ee218-294">招待によってチャットルームへのアクセスを管理するためのキャパシティ計画</span><span class="sxs-lookup"><span data-stu-id="ee218-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="ee218-295">次のキャパシティ計画の表を使用して、招待状を送信するように構成されている場合に、常設チャットサーバーによって作成および保存される招待状の数を理解することができます。</span><span class="sxs-lookup"><span data-stu-id="ee218-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="ee218-296">カテゴリの招待を管理するには、Lync Server コントロールパネルの [**チャットルームのカテゴリ設定**] ページを使用するか、または Windows PowerShell コマンドレット**csPersistentChatCategory**を使用します。</span><span class="sxs-lookup"><span data-stu-id="ee218-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="ee218-297">Lync クライアントから起動した [会議室の**管理**] ページ、または Windows PowerShell コマンドレット**csPersistentChatRoom**を使用して、チャットルームの招待を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="ee218-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="ee218-298">次の表のサンプル データでは、[**チャット ルームの設定**] ページの [**招待**] オプションがすべてのチャット ルームの 50 パーセントで [**はい**] に設定されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ee218-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ee218-299">サーバーによって生成された招待の数の計算値が 100 万を超えると、サーバーのパフォーマンスが大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ee218-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="ee218-300">この問題を回避するには、招待を送信するように構成されているチャットルームの数を最小化するか、招待状を送信するように設定されているチャットルームに参加できるユーザー数を制限してください。</span><span class="sxs-lookup"><span data-stu-id="ee218-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="ee218-301">招待によるチャットルームへのアクセスのサンプル</span><span class="sxs-lookup"><span data-stu-id="ee218-301">Chat Room Access by Invitation Sample</span></span>

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
<th><span data-ttu-id="ee218-302">小規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="ee218-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="ee218-303">中規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="ee218-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="ee218-304">大規模チャット ルーム</span><span class="sxs-lookup"><span data-stu-id="ee218-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="ee218-305">合計</span><span class="sxs-lookup"><span data-stu-id="ee218-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee218-306">チャット ルームにアクセスできるユーザー数</span><span class="sxs-lookup"><span data-stu-id="ee218-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="ee218-307">ルームあたり 30 ユーザー</span><span class="sxs-lookup"><span data-stu-id="ee218-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="ee218-308">ルームあたり 150 ユーザー</span><span class="sxs-lookup"><span data-stu-id="ee218-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="ee218-309">ルームあたり 16,000 ユーザー</span><span class="sxs-lookup"><span data-stu-id="ee218-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-310">招待があるルームの割合</span><span class="sxs-lookup"><span data-stu-id="ee218-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="ee218-311">50%</span><span class="sxs-lookup"><span data-stu-id="ee218-311">50%</span></span></p></td>
<td><p><span data-ttu-id="ee218-312">50%</span><span class="sxs-lookup"><span data-stu-id="ee218-312">50%</span></span></p></td>
<td><p><span data-ttu-id="ee218-313">50%</span><span class="sxs-lookup"><span data-stu-id="ee218-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-314">招待を送信するように構成されているチャット ルーム</span><span class="sxs-lookup"><span data-stu-id="ee218-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="ee218-315"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="ee218-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="ee218-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="ee218-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="ee218-317"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="ee218-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-318">チャット ルームにアクセスできるユーザー</span><span class="sxs-lookup"><span data-stu-id="ee218-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="ee218-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="ee218-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="ee218-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="ee218-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="ee218-321"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="ee218-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-322">常設チャットサーバーによって生成された招待状</span><span class="sxs-lookup"><span data-stu-id="ee218-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="ee218-323">960,000</span><span class="sxs-lookup"><span data-stu-id="ee218-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="ee218-324">120,000</span><span class="sxs-lookup"><span data-stu-id="ee218-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="ee218-325">80,000</span><span class="sxs-lookup"><span data-stu-id="ee218-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="ee218-326">1,160,000</span><span class="sxs-lookup"><span data-stu-id="ee218-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-327">招待の上限数</span><span class="sxs-lookup"><span data-stu-id="ee218-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="ee218-328">2,000,000</span><span class="sxs-lookup"><span data-stu-id="ee218-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-329">モデル 1 - 1 日、1 ルームあたりの想定メッセージ数で開始</span><span class="sxs-lookup"><span data-stu-id="ee218-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-330">ルームあたりのチャット レート (1 日あたり)</span><span class="sxs-lookup"><span data-stu-id="ee218-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="ee218-331">50</span><span class="sxs-lookup"><span data-stu-id="ee218-331">50</span></span></p></td>
<td><p><span data-ttu-id="ee218-332">500</span><span class="sxs-lookup"><span data-stu-id="ee218-332">500</span></span></p></td>
<td><p><span data-ttu-id="ee218-333">100</span><span class="sxs-lookup"><span data-stu-id="ee218-333">100</span></span></p></td>
<td><p><span data-ttu-id="ee218-334">650</span><span class="sxs-lookup"><span data-stu-id="ee218-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-335">すべてのチャット ルームにおけるチャット レート (1 秒あたり)</span><span class="sxs-lookup"><span data-stu-id="ee218-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-336">55.56</span><span class="sxs-lookup"><span data-stu-id="ee218-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="ee218-337">18.52</span><span class="sxs-lookup"><span data-stu-id="ee218-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="ee218-338">0.03</span><span class="sxs-lookup"><span data-stu-id="ee218-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="ee218-339">74</span><span class="sxs-lookup"><span data-stu-id="ee218-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-340">モデル 2 - 1 日、1 ユーザーあたりの投稿メッセージ数で開始</span><span class="sxs-lookup"><span data-stu-id="ee218-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-341">ユーザーあたりのチャット レート (1 日あたり)</span><span class="sxs-lookup"><span data-stu-id="ee218-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="ee218-342">マート</span><span class="sxs-lookup"><span data-stu-id="ee218-342">15</span></span></p></td>
<td><p><span data-ttu-id="ee218-343">5</span><span class="sxs-lookup"><span data-stu-id="ee218-343">5</span></span></p></td>
<td><p><span data-ttu-id="ee218-344">0.1</span><span class="sxs-lookup"><span data-stu-id="ee218-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="ee218-345">超える</span><span class="sxs-lookup"><span data-stu-id="ee218-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-346">ルームあたりのチャット レート (1 日あたり)</span><span class="sxs-lookup"><span data-stu-id="ee218-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="ee218-347">38</span><span class="sxs-lookup"><span data-stu-id="ee218-347">38</span></span></p></td>
<td><p><span data-ttu-id="ee218-348">375</span><span class="sxs-lookup"><span data-stu-id="ee218-348">375</span></span></p></td>
<td><p><span data-ttu-id="ee218-349">800</span><span class="sxs-lookup"><span data-stu-id="ee218-349">800</span></span></p></td>
<td><p><span data-ttu-id="ee218-350">1,213</span><span class="sxs-lookup"><span data-stu-id="ee218-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-351">すべてのチャット ルームにおけるチャット レート (1 秒あたり)</span><span class="sxs-lookup"><span data-stu-id="ee218-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-352">41.67</span><span class="sxs-lookup"><span data-stu-id="ee218-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="ee218-353">13.89</span><span class="sxs-lookup"><span data-stu-id="ee218-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="ee218-354">0.28</span><span class="sxs-lookup"><span data-stu-id="ee218-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="ee218-355">56</span><span class="sxs-lookup"><span data-stu-id="ee218-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="ee218-356">常設チャットサーバーのパフォーマンスユーザーモデル</span><span class="sxs-lookup"><span data-stu-id="ee218-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="ee218-357">次の表では、常設チャットサーバーのユーザーモデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ee218-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="ee218-358">この表は、処理能力の計画の要件に関する基礎を提供し、4 台のサーバーで同時に 80,000 のユーザーに対処できる一般的な組織を表しています。</span><span class="sxs-lookup"><span data-stu-id="ee218-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="ee218-359">常設チャットサーバーのパフォーマンスユーザーモデル</span><span class="sxs-lookup"><span data-stu-id="ee218-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee218-360">アクティブな接続ユーザー数</span><span class="sxs-lookup"><span data-stu-id="ee218-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="ee218-361">80,000</span><span class="sxs-lookup"><span data-stu-id="ee218-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-362">常設チャットサーバーサービスインスタンスの数</span><span class="sxs-lookup"><span data-stu-id="ee218-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="ee218-363">4</span><span class="sxs-lookup"><span data-stu-id="ee218-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-364">小規模チャット ルームのサイズ</span><span class="sxs-lookup"><span data-stu-id="ee218-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-365">30 ユーザー</span><span class="sxs-lookup"><span data-stu-id="ee218-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-366">中規模チャット ルームのサイズ</span><span class="sxs-lookup"><span data-stu-id="ee218-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-367">150 ユーザー</span><span class="sxs-lookup"><span data-stu-id="ee218-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-368">大規模チャット ルームのサイズ</span><span class="sxs-lookup"><span data-stu-id="ee218-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-369">16,000 ユーザー</span><span class="sxs-lookup"><span data-stu-id="ee218-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-370">チャット ルームの合計数</span><span class="sxs-lookup"><span data-stu-id="ee218-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-371">33,077</span><span class="sxs-lookup"><span data-stu-id="ee218-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-372">小規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="ee218-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-373">32,000</span><span class="sxs-lookup"><span data-stu-id="ee218-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-374">中規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="ee218-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-375">1,067</span><span class="sxs-lookup"><span data-stu-id="ee218-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-376">大規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="ee218-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-377">常用</span><span class="sxs-lookup"><span data-stu-id="ee218-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-378">ユーザーあたりのチャット ルームの合計数</span><span class="sxs-lookup"><span data-stu-id="ee218-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="ee218-379">16</span><span class="sxs-lookup"><span data-stu-id="ee218-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-380">ユーザーあたりの小規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="ee218-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="ee218-381">以内</span><span class="sxs-lookup"><span data-stu-id="ee218-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-382">ユーザーあたりの中規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="ee218-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="ee218-383">両面</span><span class="sxs-lookup"><span data-stu-id="ee218-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-384">ユーザーあたりの大規模チャット ルームの数</span><span class="sxs-lookup"><span data-stu-id="ee218-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="ee218-385">両面</span><span class="sxs-lookup"><span data-stu-id="ee218-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-386">ユーザーあたりの参加ルーム数</span><span class="sxs-lookup"><span data-stu-id="ee218-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="ee218-387">24</span><span class="sxs-lookup"><span data-stu-id="ee218-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-388">ピーク時の参加レート</span><span class="sxs-lookup"><span data-stu-id="ee218-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="ee218-389">10/秒</span><span class="sxs-lookup"><span data-stu-id="ee218-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-390">チャット レート合計</span><span class="sxs-lookup"><span data-stu-id="ee218-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="ee218-391">24/秒</span><span class="sxs-lookup"><span data-stu-id="ee218-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-392">小規模チャット ルームのチャット レート</span><span class="sxs-lookup"><span data-stu-id="ee218-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-393">22.22/second</span><span class="sxs-lookup"><span data-stu-id="ee218-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-394">中規模チャット ルームのチャット レート</span><span class="sxs-lookup"><span data-stu-id="ee218-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-395">1.67/second</span><span class="sxs-lookup"><span data-stu-id="ee218-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-396">大規模チャット ルームのチャット レート</span><span class="sxs-lookup"><span data-stu-id="ee218-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="ee218-397">~0.15/second</span><span class="sxs-lookup"><span data-stu-id="ee218-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-398">招待が構成されているチャット ルームの割合</span><span class="sxs-lookup"><span data-stu-id="ee218-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="ee218-399">50%</span><span class="sxs-lookup"><span data-stu-id="ee218-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-400">直接メンバーシップの割合</span><span class="sxs-lookup"><span data-stu-id="ee218-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="ee218-401">50%</span><span class="sxs-lookup"><span data-stu-id="ee218-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-402">グループ メンバーシップの割合</span><span class="sxs-lookup"><span data-stu-id="ee218-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="ee218-403">50%</span><span class="sxs-lookup"><span data-stu-id="ee218-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-404">Active Directory ドメインサービスの親所属の平均数</span><span class="sxs-lookup"><span data-stu-id="ee218-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="ee218-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="ee218-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-406">ユーザーごとの加入する連絡先の数</span><span class="sxs-lookup"><span data-stu-id="ee218-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="ee218-407">80</span><span class="sxs-lookup"><span data-stu-id="ee218-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-408">ユーザーあたりの平均エンドポイント数</span><span class="sxs-lookup"><span data-stu-id="ee218-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="ee218-409">1.5</span><span class="sxs-lookup"><span data-stu-id="ee218-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-410">エンドポイントあたりの表示されるチャット ルームの平均数</span><span class="sxs-lookup"><span data-stu-id="ee218-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="ee218-411">1.5</span><span class="sxs-lookup"><span data-stu-id="ee218-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-412">ユーザーあたりの表示されるチャット ルームの平均数</span><span class="sxs-lookup"><span data-stu-id="ee218-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="ee218-413">2.25 (1 ルームと 2 ルームが 50% ずつ)。最大 6 ルームがオープン (1 モニターにつき 1 つ)</span><span class="sxs-lookup"><span data-stu-id="ee218-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-414">一定間隔でポーリングされる参加者の数</span><span class="sxs-lookup"><span data-stu-id="ee218-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="ee218-415">25 (表示されるチャット ルーム 1 つあたり)</span><span class="sxs-lookup"><span data-stu-id="ee218-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-416">ポーリング間隔の長さ</span><span class="sxs-lookup"><span data-stu-id="ee218-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="ee218-417">5 分</span><span class="sxs-lookup"><span data-stu-id="ee218-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-418">1 秒あたりにポーリングされる参加者の数</span><span class="sxs-lookup"><span data-stu-id="ee218-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="ee218-419">15,000</span><span class="sxs-lookup"><span data-stu-id="ee218-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee218-420">1 時間あたりのユーザーごとのプレゼンス変更の数</span><span class="sxs-lookup"><span data-stu-id="ee218-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="ee218-421">6</span><span class="sxs-lookup"><span data-stu-id="ee218-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee218-422">1 秒あたりのプレゼンス変更の数</span><span class="sxs-lookup"><span data-stu-id="ee218-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="ee218-423">133.33</span><span class="sxs-lookup"><span data-stu-id="ee218-423">133.33</span></span></p></td>
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

