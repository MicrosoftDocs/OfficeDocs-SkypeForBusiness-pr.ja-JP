---
title: 'Lync Server 2013: 内部サーバーのポートとプロトコル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026843216e433ebea120384209ed90f38be3437b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="fec01-102">Lync Server 2013 の内部サーバーのポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="fec01-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fec01-103">_**最終更新日:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="fec01-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="fec01-104">このセクションでは、Lync Server 展開のサーバー、ロードバランサー、クライアントで使用されるポートとプロトコルについて概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="fec01-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fec01-105">Lync と Communicator クライアントが1対1の通信に関わる場合、ピアツーピアと呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="fec01-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="fec01-106">技術的には、2つのクライアントは1つの会話と1つの会話の間でやり取りされ、中央にはインスタントメッセージング multipoint コントロールユニット (IMMCU) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fec01-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="fec01-107">IMMCU は、フロントエンドサーバーのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="fec01-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="fec01-108">必要な通信ワークフローに IMMCU を配置すると、フロントエンドサーバーが有効になっている通話の詳細の記録とその他の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fec01-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="fec01-109">通信は、クライアント上の動的ソースポートからフロントエンドサーバーポート TLS/TCP/5061 に送信されます (推奨トランスポート層セキュリティを使用していることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="fec01-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="fec01-110">設計上、ピアツーピア通信 (およびマルチパーティの IM) は、Lync Server と IMMCU がアクティブで利用可能な場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="fec01-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="fec01-111">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="fec01-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fec01-112">サーバー上で Lync Server サービスを開始する前に、Windows ファイアウォールが実行されている必要があります。そのため、Lync Server はファイアウォールで必要なポートを開くことになります。</span><span class="sxs-lookup"><span data-stu-id="fec01-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="fec01-113">エッジコンポーネントのファイアウォール構成の詳細については、「 [Lync Server 2013 の外部の A/V ファイアウォールとポートの要件を確認](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fec01-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="fec01-114">次の表に、各内部サーバー役割で開く必要のあるポートの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="fec01-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="fec01-115">必要なサーバー ポート (サーバー役割別)</span><span class="sxs-lookup"><span data-stu-id="fec01-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="fec01-116">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="fec01-116">Server role</span></span></th>
<th><span data-ttu-id="fec01-117">サービス名</span><span class="sxs-lookup"><span data-stu-id="fec01-117">Service name</span></span></th>
<th><span data-ttu-id="fec01-118">ポート</span><span class="sxs-lookup"><span data-stu-id="fec01-118">Port</span></span></th>
<th><span data-ttu-id="fec01-119">プロトコル</span><span class="sxs-lookup"><span data-stu-id="fec01-119">Protocol</span></span></th>
<th><span data-ttu-id="fec01-120">メモ</span><span class="sxs-lookup"><span data-stu-id="fec01-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fec01-121">すべてのサーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-122">SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="fec01-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="fec01-123">1434</span><span class="sxs-lookup"><span data-stu-id="fec01-123">1434</span></span></p></td>
<td><p><span data-ttu-id="fec01-124">UDP</span><span class="sxs-lookup"><span data-stu-id="fec01-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="fec01-125">中央管理ストアデータベースのローカルでレプリケートされたコピーの SQL ブラウザー。</span><span class="sxs-lookup"><span data-stu-id="fec01-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-126">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-127">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="fec01-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fec01-128">5060</span><span class="sxs-lookup"><span data-stu-id="fec01-128">5060</span></span></p></td>
<td><p><span data-ttu-id="fec01-129">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-130">リモート通話コントロール サーバーなどの Standard Edition サーバーとフロントエンド サーバーで、信頼されたサービスへの静的ルートの場合にオプションとして使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-131">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-132">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="fec01-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fec01-133">5061</span><span class="sxs-lookup"><span data-stu-id="fec01-133">5061</span></span></p></td>
<td><p><span data-ttu-id="fec01-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fec01-135">サーバー間のすべての内部 SIP 通信 (MTLS)、サーバーとクライアントの間の SIP 通信 (TLS)、およびフロントエンド サーバーと仲介サーバーの間の SIP 通信 (MTLS) において、Standard Edition サーバーとフロントエンド プールで使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="fec01-136">監視サーバーとの通信にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="fec01-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-137">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-138">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="fec01-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fec01-139">444</span><span class="sxs-lookup"><span data-stu-id="fec01-139">444</span></span></p></td>
<td><p><span data-ttu-id="fec01-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec01-140">HTTPS</span></span></p>
<p><span data-ttu-id="fec01-141">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-142">フォーカス (会議の状態を管理する Lync Server コンポーネント) と個々のサーバーの間の HTTPS 通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fec01-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="fec01-143">このポートは、Survivable Branch アプライアンスとフロントエンドサーバー間の TCP 通信にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="fec01-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-144">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-145">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="fec01-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fec01-146">135</span><span class="sxs-lookup"><span data-stu-id="fec01-146">135</span></span></p></td>
<td><p><span data-ttu-id="fec01-147">DCOM およびリモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="fec01-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="fec01-148">ユーザーの移行、ユーザー レプリケーター同期、およびアドレス帳同期などの DCOM ベースの操作で使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-149">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-150">Lync Server IM 会議サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="fec01-151">5062</span><span class="sxs-lookup"><span data-stu-id="fec01-151">5062</span></span></p></td>
<td><p><span data-ttu-id="fec01-152">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-153">インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-154">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-155">Lync Server Web 会議サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="fec01-156">8057</span><span class="sxs-lookup"><span data-stu-id="fec01-156">8057</span></span></p></td>
<td><p><span data-ttu-id="fec01-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fec01-158">クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-159">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-160">Lync Server Web 会議互換サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fec01-161">8058</span><span class="sxs-lookup"><span data-stu-id="fec01-161">8058</span></span></p></td>
<td><p><span data-ttu-id="fec01-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fec01-163">Live Meeting クライアントと以前のバージョンの Lync Server からの永続的な共有オブジェクトモデル (PSOM) 接続をリッスンするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fec01-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-164">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-165">Lync Server の音声/ビデオ会議サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="fec01-166">5063</span><span class="sxs-lookup"><span data-stu-id="fec01-166">5063</span></span></p></td>
<td><p><span data-ttu-id="fec01-167">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-168">音声ビデオ会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-169">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-170">Lync Server の音声/ビデオ会議サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="fec01-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="fec01-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="fec01-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fec01-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="fec01-173">ビデオ会議で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="fec01-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-174">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-175">Lync Server Web 互換サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fec01-176">80</span><span class="sxs-lookup"><span data-stu-id="fec01-176">80</span></span></p></td>
<td><p><span data-ttu-id="fec01-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="fec01-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="fec01-178">HTTPS が使用されない場合の、フロントエンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-179">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-180">Lync Server Web 互換サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fec01-181">443</span><span class="sxs-lookup"><span data-stu-id="fec01-181">443</span></span></p></td>
<td><p><span data-ttu-id="fec01-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec01-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="fec01-183">フロントエンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-184">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-185">Lync Server Web 互換サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fec01-186">8080</span><span class="sxs-lookup"><span data-stu-id="fec01-186">8080</span></span></p></td>
<td><p><span data-ttu-id="fec01-187">TCP および HTTP</span><span class="sxs-lookup"><span data-stu-id="fec01-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="fec01-188">外部アクセスのために Web コンポーネントで使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-189">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-190">Web サーバー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fec01-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="fec01-191">4443</span><span class="sxs-lookup"><span data-stu-id="fec01-191">4443</span></span></p></td>
<td><p><span data-ttu-id="fec01-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec01-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="fec01-193">Autodiscover サインインのための HTTPS (リバース プロキシから) および HTTPS フロント エンドのプール間通信。</span><span class="sxs-lookup"><span data-stu-id="fec01-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-194">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-195">Web サーバー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fec01-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="fec01-196">8060</span><span class="sxs-lookup"><span data-stu-id="fec01-196">8060</span></span></p></td>
<td><p><span data-ttu-id="fec01-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-198">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-199">Web サーバー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fec01-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="fec01-200">8061</span><span class="sxs-lookup"><span data-stu-id="fec01-200">8061</span></span></p></td>
<td><p><span data-ttu-id="fec01-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-202">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-203">Mobility Service コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fec01-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="fec01-204">5086</span><span class="sxs-lookup"><span data-stu-id="fec01-204">5086</span></span></p></td>
<td><p><span data-ttu-id="fec01-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fec01-206">Mobility Service の内部プロセスに使用される SIP ポート。</span><span class="sxs-lookup"><span data-stu-id="fec01-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-207">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-208">Mobility Service コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fec01-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="fec01-209">5087</span><span class="sxs-lookup"><span data-stu-id="fec01-209">5087</span></span></p></td>
<td><p><span data-ttu-id="fec01-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fec01-211">Mobility Service の内部プロセスに使用される SIP ポート。</span><span class="sxs-lookup"><span data-stu-id="fec01-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-212">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-213">Mobility Service コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fec01-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="fec01-214">443</span><span class="sxs-lookup"><span data-stu-id="fec01-214">443</span></span></p></td>
<td><p><span data-ttu-id="fec01-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec01-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-216">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-217">Lync Server 会議アテンダントサービス (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="fec01-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="fec01-218">5064</span><span class="sxs-lookup"><span data-stu-id="fec01-218">5064</span></span></p></td>
<td><p><span data-ttu-id="fec01-219">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-220">ダイヤルイン会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-221">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-222">Lync Server 会議アテンダントサービス (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="fec01-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="fec01-223">5072</span><span class="sxs-lookup"><span data-stu-id="fec01-223">5072</span></span></p></td>
<td><p><span data-ttu-id="fec01-224">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-225">応答の受信 SIP 要求 (ダイヤルイン会議) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fec01-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-226">併置された仲介サーバーも実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fec01-227">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fec01-228">5070</span><span class="sxs-lookup"><span data-stu-id="fec01-228">5070</span></span></p></td>
<td><p><span data-ttu-id="fec01-229">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-230">フロントエンド サーバーから仲介サーバーへの要求を受信するために仲介サーバーで使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-231">併置された仲介サーバーも実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fec01-232">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fec01-233">5067</span><span class="sxs-lookup"><span data-stu-id="fec01-233">5067</span></span></p></td>
<td><p><span data-ttu-id="fec01-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fec01-235">PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-236">併置された仲介サーバーも実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fec01-237">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fec01-238">5068</span><span class="sxs-lookup"><span data-stu-id="fec01-238">5068</span></span></p></td>
<td><p><span data-ttu-id="fec01-239">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-240">PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-241">併置された仲介サーバーも実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fec01-242">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fec01-243">5081</span><span class="sxs-lookup"><span data-stu-id="fec01-243">5081</span></span></p></td>
<td><p><span data-ttu-id="fec01-244">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-245">仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-246">併置された仲介サーバーも実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fec01-247">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fec01-248">5082</span><span class="sxs-lookup"><span data-stu-id="fec01-248">5082</span></span></p></td>
<td><p><span data-ttu-id="fec01-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fec01-250">仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-251">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-252">Lync Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="fec01-253">5065</span><span class="sxs-lookup"><span data-stu-id="fec01-253">5065</span></span></p></td>
<td><p><span data-ttu-id="fec01-254">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-255">アプリケーション共有の SIP リッスン要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-256">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-257">Lync Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="fec01-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="fec01-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="fec01-259">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-260">アプリケーション共有で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="fec01-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-261">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-262">Lync Server 会議のアナウンスメントサービス</span><span class="sxs-lookup"><span data-stu-id="fec01-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="fec01-263">5073</span><span class="sxs-lookup"><span data-stu-id="fec01-263">5073</span></span></p></td>
<td><p><span data-ttu-id="fec01-264">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-265">Lync Server 会議のアナウンスメントサービス (ダイヤルイン会議) の受信 SIP 要求に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fec01-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-266">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-267">Lync Server コール パーク サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="fec01-268">5075</span><span class="sxs-lookup"><span data-stu-id="fec01-268">5075</span></span></p></td>
<td><p><span data-ttu-id="fec01-269">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-270">コール パーク アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-271">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-272">Lync Server の音声テストサービス</span><span class="sxs-lookup"><span data-stu-id="fec01-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="fec01-273">5076</span><span class="sxs-lookup"><span data-stu-id="fec01-273">5076</span></span></p></td>
<td><p><span data-ttu-id="fec01-274">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-275">オーディオ テスト サービスの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-276">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-277">該当なし</span><span class="sxs-lookup"><span data-stu-id="fec01-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="fec01-278">5066</span><span class="sxs-lookup"><span data-stu-id="fec01-278">5066</span></span></p></td>
<td><p><span data-ttu-id="fec01-279">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-280">発信 Enhanced 9-1-1 (E9-1-1) ゲートウェイで使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-281">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-282">Lync Server 応答グループ サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="fec01-283">5071</span><span class="sxs-lookup"><span data-stu-id="fec01-283">5071</span></span></p></td>
<td><p><span data-ttu-id="fec01-284">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-285">応答グループ アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-286">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-287">Lync Server 応答グループ サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="fec01-288">8404</span><span class="sxs-lookup"><span data-stu-id="fec01-288">8404</span></span></p></td>
<td><p><span data-ttu-id="fec01-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fec01-290">応答グループ アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-291">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-292">Lync Server 帯域幅ポリシーサービス</span><span class="sxs-lookup"><span data-stu-id="fec01-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="fec01-293">5080</span><span class="sxs-lookup"><span data-stu-id="fec01-293">5080</span></span></p></td>
<td><p><span data-ttu-id="fec01-294">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-295">音声ビデオ エッジ TURN トラフィックの帯域幅ポリシー サービスによる通話受付管理で使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-296">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-297">Lync Server 帯域幅ポリシーサービス</span><span class="sxs-lookup"><span data-stu-id="fec01-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="fec01-298">448</span><span class="sxs-lookup"><span data-stu-id="fec01-298">448</span></span></p></td>
<td><p><span data-ttu-id="fec01-299">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-300">Lync Server 帯域幅ポリシーサービスによる通話受付制御に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fec01-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-301">中央管理ストアが配置されているフロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="fec01-302">Lync Server マスターレプリケーターエージェントサービス</span><span class="sxs-lookup"><span data-stu-id="fec01-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="fec01-303">445</span><span class="sxs-lookup"><span data-stu-id="fec01-303">445</span></span></p></td>
<td><p><span data-ttu-id="fec01-304">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-305">Lync Server を実行しているサーバーに、中央の管理ストアから構成データをプッシュするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fec01-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-306">すべてのサーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-307">SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="fec01-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="fec01-308">1434</span><span class="sxs-lookup"><span data-stu-id="fec01-308">1434</span></span></p></td>
<td><p><span data-ttu-id="fec01-309">UDP</span><span class="sxs-lookup"><span data-stu-id="fec01-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="fec01-310">ローカルの SQL Server インスタンスの中央管理ストアデータのローカルにレプリケートされたコピー用の SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="fec01-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-311">すべての内部サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-312">各種</span><span class="sxs-lookup"><span data-stu-id="fec01-312">Various</span></span></p></td>
<td><p><span data-ttu-id="fec01-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="fec01-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="fec01-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fec01-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="fec01-315">すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="fec01-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="fec01-316">オーディオを終了するすべてのサーバーで使用されます。フロントエンドサーバー (Lync Server 会議アテンダントサービス、Lync Server 会議のアナウンスメントサービス、Lync Server Audio/ビデオ会議サービス、および仲介サーバー)。</span><span class="sxs-lookup"><span data-stu-id="fec01-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-317">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fec01-318">443</span><span class="sxs-lookup"><span data-stu-id="fec01-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fec01-319">Lync Server 2013 で Office Web Apps サーバーに接続するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fec01-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-320">ディレクター</span><span class="sxs-lookup"><span data-stu-id="fec01-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="fec01-321">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="fec01-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fec01-322">5060</span><span class="sxs-lookup"><span data-stu-id="fec01-322">5060</span></span></p></td>
<td><p><span data-ttu-id="fec01-323">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-324">リモート通話コントロール サーバーなど、信頼されたサービスへの静的ルートの場合にオプションで使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-325">ディレクター</span><span class="sxs-lookup"><span data-stu-id="fec01-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="fec01-326">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="fec01-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fec01-327">444</span><span class="sxs-lookup"><span data-stu-id="fec01-327">444</span></span></p></td>
<td><p><span data-ttu-id="fec01-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec01-328">HTTPS</span></span></p>
<p><span data-ttu-id="fec01-329">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-330">フロントエンドとディレクターの間のサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="fec01-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="fec01-331">さらに、クライアント証明書公開 (フロントエンドサーバー) またはクライアント証明書が既に公開されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="fec01-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-332">ディレクター</span><span class="sxs-lookup"><span data-stu-id="fec01-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="fec01-333">Lync Server Web 互換サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fec01-334">80</span><span class="sxs-lookup"><span data-stu-id="fec01-334">80</span></span></p></td>
<td><p><span data-ttu-id="fec01-335">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-p105">ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への初期通信に使用。通常の動作では HTTPS トラフィックに切り替わり、ポート 443 およびプロトコル TCP を使用します。</span><span class="sxs-lookup"><span data-stu-id="fec01-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-338">ディレクター</span><span class="sxs-lookup"><span data-stu-id="fec01-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="fec01-339">Lync Server Web 互換サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fec01-340">443</span><span class="sxs-lookup"><span data-stu-id="fec01-340">443</span></span></p></td>
<td><p><span data-ttu-id="fec01-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec01-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="fec01-342">ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-343">ディレクター</span><span class="sxs-lookup"><span data-stu-id="fec01-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="fec01-344">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="fec01-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fec01-345">5061</span><span class="sxs-lookup"><span data-stu-id="fec01-345">5061</span></span></p></td>
<td><p><span data-ttu-id="fec01-346">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-347">サーバー間の内部通信とクライアント接続に使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-348">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-349">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fec01-350">5070</span><span class="sxs-lookup"><span data-stu-id="fec01-350">5070</span></span></p></td>
<td><p><span data-ttu-id="fec01-351">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-352">フロントエンド サーバーからの要求を受信するために仲介サーバーで使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-353">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-354">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fec01-355">5067</span><span class="sxs-lookup"><span data-stu-id="fec01-355">5067</span></span></p></td>
<td><p><span data-ttu-id="fec01-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fec01-357">PSTN ゲートウェイからの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-358">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-359">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fec01-360">5068</span><span class="sxs-lookup"><span data-stu-id="fec01-360">5068</span></span></p></td>
<td><p><span data-ttu-id="fec01-361">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-362">PSTN ゲートウェイからの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-363">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="fec01-364">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fec01-365">5070</span><span class="sxs-lookup"><span data-stu-id="fec01-365">5070</span></span></p></td>
<td><p><span data-ttu-id="fec01-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fec01-367">フロントエンド サーバーからの SIP 要求で使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-368">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="fec01-369">常設チャット SIP</span><span class="sxs-lookup"><span data-stu-id="fec01-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="fec01-370">5041</span><span class="sxs-lookup"><span data-stu-id="fec01-370">5041</span></span></p></td>
<td><p><span data-ttu-id="fec01-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-372">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="fec01-373">常設チャット Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="fec01-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="fec01-374">881</span><span class="sxs-lookup"><span data-stu-id="fec01-374">881</span></span></p></td>
<td><p><span data-ttu-id="fec01-375">TCP (TLS) および TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-376">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fec01-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="fec01-377">常設チャット ファイル転送サービス</span><span class="sxs-lookup"><span data-stu-id="fec01-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="fec01-378">443</span><span class="sxs-lookup"><span data-stu-id="fec01-378">443</span></span></p></td>
<td><p><span data-ttu-id="fec01-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fec01-380">一部のリモート通話コントロールシナリオでは、フロントエンドサーバーまたはディレクターと PBX の間に TCP 接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="fec01-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="fec01-381">Lync Server は TCP ポート5060を使用しなくなりましたが、リモートコールコントロールの展開時には、RCC Line Server の FQDN と、フロントエンドサーバーまたはディレクターが PBX システムに接続するために使用する TCP ポートを関連付ける信頼されたサーバー構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="fec01-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="fec01-382">詳細については、「Lync Server 管理シェルドキュメントの<STRONG>CsTrustedApplicationComputer</STRONG>コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fec01-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="fec01-383">次の表に、(DNS 負荷分散ではない) ハードウェア負荷分散のみを使用するプールでハードウェア ロード バランサーを開くために必要なポートを示します。</span><span class="sxs-lookup"><span data-stu-id="fec01-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="fec01-384">ハードウェア負荷分散のみを使用する場合のハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fec01-385">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-385">Load Balancer</span></span></th>
<th><span data-ttu-id="fec01-386">ポート</span><span class="sxs-lookup"><span data-stu-id="fec01-386">Port</span></span></th>
<th><span data-ttu-id="fec01-387">プロトコル</span><span class="sxs-lookup"><span data-stu-id="fec01-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fec01-388">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-389">5061</span><span class="sxs-lookup"><span data-stu-id="fec01-389">5061</span></span></p></td>
<td><p><span data-ttu-id="fec01-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-391">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-392">444</span><span class="sxs-lookup"><span data-stu-id="fec01-392">444</span></span></p></td>
<td><p><span data-ttu-id="fec01-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec01-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-394">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-395">135</span><span class="sxs-lookup"><span data-stu-id="fec01-395">135</span></span></p></td>
<td><p><span data-ttu-id="fec01-396">DCOM およびリモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="fec01-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-397">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-398">80</span><span class="sxs-lookup"><span data-stu-id="fec01-398">80</span></span></p></td>
<td><p><span data-ttu-id="fec01-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="fec01-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-400">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-401">8080</span><span class="sxs-lookup"><span data-stu-id="fec01-401">8080</span></span></p></td>
<td><p><span data-ttu-id="fec01-402">TCP - フロントエンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</span><span class="sxs-lookup"><span data-stu-id="fec01-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-403">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-404">443</span><span class="sxs-lookup"><span data-stu-id="fec01-404">443</span></span></p></td>
<td><p><span data-ttu-id="fec01-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec01-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-406">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-407">4443</span><span class="sxs-lookup"><span data-stu-id="fec01-407">4443</span></span></p></td>
<td><p><span data-ttu-id="fec01-408">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="fec01-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-409">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-410">5072</span><span class="sxs-lookup"><span data-stu-id="fec01-410">5072</span></span></p></td>
<td><p><span data-ttu-id="fec01-411">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-412">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-413">5073</span><span class="sxs-lookup"><span data-stu-id="fec01-413">5073</span></span></p></td>
<td><p><span data-ttu-id="fec01-414">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-415">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-416">5075</span><span class="sxs-lookup"><span data-stu-id="fec01-416">5075</span></span></p></td>
<td><p><span data-ttu-id="fec01-417">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-418">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-419">5076</span><span class="sxs-lookup"><span data-stu-id="fec01-419">5076</span></span></p></td>
<td><p><span data-ttu-id="fec01-420">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-421">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-422">5071</span><span class="sxs-lookup"><span data-stu-id="fec01-422">5071</span></span></p></td>
<td><p><span data-ttu-id="fec01-423">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-424">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-425">5080</span><span class="sxs-lookup"><span data-stu-id="fec01-425">5080</span></span></p></td>
<td><p><span data-ttu-id="fec01-426">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-427">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-428">448</span><span class="sxs-lookup"><span data-stu-id="fec01-428">448</span></span></p></td>
<td><p><span data-ttu-id="fec01-429">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-430">仲介サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-431">5070</span><span class="sxs-lookup"><span data-stu-id="fec01-431">5070</span></span></p></td>
<td><p><span data-ttu-id="fec01-432">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-433">フロントエンド サーバーのロード バランサー (プールで仲介サーバーも稼働する場合)</span><span class="sxs-lookup"><span data-stu-id="fec01-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="fec01-434">5070</span><span class="sxs-lookup"><span data-stu-id="fec01-434">5070</span></span></p></td>
<td><p><span data-ttu-id="fec01-435">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-436">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-437">443</span><span class="sxs-lookup"><span data-stu-id="fec01-437">443</span></span></p></td>
<td><p><span data-ttu-id="fec01-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec01-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-439">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-440">444</span><span class="sxs-lookup"><span data-stu-id="fec01-440">444</span></span></p></td>
<td><p><span data-ttu-id="fec01-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec01-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-442">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-443">5061</span><span class="sxs-lookup"><span data-stu-id="fec01-443">5061</span></span></p></td>
<td><p><span data-ttu-id="fec01-444">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-445">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-446">4443</span><span class="sxs-lookup"><span data-stu-id="fec01-446">4443</span></span></p></td>
<td><p><span data-ttu-id="fec01-447">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="fec01-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fec01-p107">DNS 負荷分散を使用するフロントエンド プールとディレクター プールでも、ハードウェア ロード バランサーを展開しておく必要があります。次の表に、これらのハードウェア ロード バランサーで開く必要があるポートを示します。</span><span class="sxs-lookup"><span data-stu-id="fec01-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="fec01-450">DNS 負荷分散を使用する場合のハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fec01-451">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-451">Load Balancer</span></span></th>
<th><span data-ttu-id="fec01-452">ポート</span><span class="sxs-lookup"><span data-stu-id="fec01-452">Port</span></span></th>
<th><span data-ttu-id="fec01-453">プロトコル</span><span class="sxs-lookup"><span data-stu-id="fec01-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fec01-454">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-455">80</span><span class="sxs-lookup"><span data-stu-id="fec01-455">80</span></span></p></td>
<td><p><span data-ttu-id="fec01-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="fec01-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-457">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-458">443</span><span class="sxs-lookup"><span data-stu-id="fec01-458">443</span></span></p></td>
<td><p><span data-ttu-id="fec01-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec01-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-460">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-461">8080</span><span class="sxs-lookup"><span data-stu-id="fec01-461">8080</span></span></p></td>
<td><p><span data-ttu-id="fec01-462">TCP - フロントエンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</span><span class="sxs-lookup"><span data-stu-id="fec01-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-463">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-464">4443</span><span class="sxs-lookup"><span data-stu-id="fec01-464">4443</span></span></p></td>
<td><p><span data-ttu-id="fec01-465">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="fec01-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-466">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-467">443</span><span class="sxs-lookup"><span data-stu-id="fec01-467">443</span></span></p></td>
<td><p><span data-ttu-id="fec01-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec01-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-469">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="fec01-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fec01-470">4443</span><span class="sxs-lookup"><span data-stu-id="fec01-470">4443</span></span></p></td>
<td><p><span data-ttu-id="fec01-471">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="fec01-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="fec01-472">必要なクライアント ポート</span><span class="sxs-lookup"><span data-stu-id="fec01-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fec01-473">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fec01-473">Component</span></span></th>
<th><span data-ttu-id="fec01-474">ポート</span><span class="sxs-lookup"><span data-stu-id="fec01-474">Port</span></span></th>
<th><span data-ttu-id="fec01-475">プロトコル</span><span class="sxs-lookup"><span data-stu-id="fec01-475">Protocol</span></span></th>
<th><span data-ttu-id="fec01-476">メモ</span><span class="sxs-lookup"><span data-stu-id="fec01-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fec01-477">クライアント</span><span class="sxs-lookup"><span data-stu-id="fec01-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="fec01-478">67/68</span><span class="sxs-lookup"><span data-stu-id="fec01-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="fec01-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="fec01-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-480">Lync Server によってレジストラーの FQDN が検索されます (つまり、DNS SRV に障害が発生した場合は、手動の設定が構成されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="fec01-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-481">クライアント</span><span class="sxs-lookup"><span data-stu-id="fec01-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="fec01-482">443</span><span class="sxs-lookup"><span data-stu-id="fec01-482">443</span></span></p></td>
<td><p><span data-ttu-id="fec01-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fec01-484">外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-485">クライアント</span><span class="sxs-lookup"><span data-stu-id="fec01-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="fec01-486">443</span><span class="sxs-lookup"><span data-stu-id="fec01-486">443</span></span></p></td>
<td><p><span data-ttu-id="fec01-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="fec01-488">Web 会議セッションへの外部ユーザー アクセスで使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-489">クライアント</span><span class="sxs-lookup"><span data-stu-id="fec01-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="fec01-490">443</span><span class="sxs-lookup"><span data-stu-id="fec01-490">443</span></span></p></td>
<td><p><span data-ttu-id="fec01-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="fec01-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="fec01-492">音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-493">クライアント</span><span class="sxs-lookup"><span data-stu-id="fec01-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="fec01-494">3478</span><span class="sxs-lookup"><span data-stu-id="fec01-494">3478</span></span></p></td>
<td><p><span data-ttu-id="fec01-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="fec01-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="fec01-496">音声ビデオ セッションとメディアへの外部ユーザー アクセス (UDP) で使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-497">クライアント</span><span class="sxs-lookup"><span data-stu-id="fec01-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="fec01-498">5061</span><span class="sxs-lookup"><span data-stu-id="fec01-498">5061</span></span></p></td>
<td><p><span data-ttu-id="fec01-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="fec01-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fec01-500">外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</span><span class="sxs-lookup"><span data-stu-id="fec01-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-501">クライアント</span><span class="sxs-lookup"><span data-stu-id="fec01-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="fec01-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="fec01-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="fec01-503">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-504">Lync クライアントと以前のクライアント (Microsoft Office Communications Server 2007 R2、Microsoft Office Communications Server 2007、Live Communications Server 2005) の間でのファイル送信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fec01-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-505">クライアント</span><span class="sxs-lookup"><span data-stu-id="fec01-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="fec01-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="fec01-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="fec01-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fec01-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="fec01-508">オーディオ ポート範囲 (少なくとも 20 個のポートが必要)。</span><span class="sxs-lookup"><span data-stu-id="fec01-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-509">クライアント</span><span class="sxs-lookup"><span data-stu-id="fec01-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="fec01-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="fec01-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="fec01-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fec01-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="fec01-512">ビデオ ポート範囲 (少なくとも 20 個のポートが必要)。</span><span class="sxs-lookup"><span data-stu-id="fec01-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-513">クライアント</span><span class="sxs-lookup"><span data-stu-id="fec01-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="fec01-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="fec01-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="fec01-515">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-516">ピアツーピア ファイル転送 (会議ファイル転送の場合、クライアントは PSOM を使用)。</span><span class="sxs-lookup"><span data-stu-id="fec01-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec01-517">クライアント</span><span class="sxs-lookup"><span data-stu-id="fec01-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="fec01-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="fec01-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="fec01-519">TCP</span><span class="sxs-lookup"><span data-stu-id="fec01-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-520">アプリケーション共有。</span><span class="sxs-lookup"><span data-stu-id="fec01-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec01-521">Aastra 6721ip 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="fec01-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="fec01-522">Aastra 6725ip 卓上電話</span><span class="sxs-lookup"><span data-stu-id="fec01-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="fec01-523">HP 4110 IP 電話 (共通領域電話)</span><span class="sxs-lookup"><span data-stu-id="fec01-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="fec01-524">HP 4120 IP 電話 (卓上電話)</span><span class="sxs-lookup"><span data-stu-id="fec01-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="fec01-525">Polycom CX500 IP 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="fec01-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="fec01-526">Polycom CX600 IP 卓上電話</span><span class="sxs-lookup"><span data-stu-id="fec01-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="fec01-527">Polycom CX700 IP 卓上電話</span><span class="sxs-lookup"><span data-stu-id="fec01-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="fec01-528">Polycom CX3000 IP 会議電話</span><span class="sxs-lookup"><span data-stu-id="fec01-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="fec01-529">67/68</span><span class="sxs-lookup"><span data-stu-id="fec01-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="fec01-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="fec01-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="fec01-531">リストされているデバイスで使用され、Lync Server 証明書、プロビジョニング FQDN、レジストラー FQDN を検索します。</span><span class="sxs-lookup"><span data-stu-id="fec01-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fec01-532">**\*** これらのメディアの種類に対して特定のポートを構成するには、CsConferencingConfiguration コマンドレット (ClientMediaPortRangeEnabled、ClientMediaPort、ClientMediaPortRange parameters) を使用します。</span><span class="sxs-lookup"><span data-stu-id="fec01-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fec01-533">Lync クライアント用のプログラムを設定すると、必要なオペレーティングシステムファイアウォール例外がクライアントコンピューターに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="fec01-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fec01-534">外部ユーザー アクセス用に使用されるポートは、クライアントが組織のファイアウォールを通過する必要のあるすべてのシナリオにおいて必要です (たとえば、他の組織によってホストされる外部の通信や会議)。</span><span class="sxs-lookup"><span data-stu-id="fec01-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

