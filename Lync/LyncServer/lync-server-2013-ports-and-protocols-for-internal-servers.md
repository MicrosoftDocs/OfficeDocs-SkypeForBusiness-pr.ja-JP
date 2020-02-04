---
title: 'Lync Server 2013: 内部サーバーのポートとプロトコル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1001cce83d9b23125b177725c77715bd19a00e03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="2a105-102">Lync Server 2013 の内部サーバーのポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="2a105-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a105-103">_**最終更新日:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="2a105-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="2a105-104">このセクションでは、Lync Server 展開のサーバー、ロードバランサー、クライアントで使用されるポートとプロトコルについて概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="2a105-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2a105-105">Lync と Communicator クライアントが1対1の通信に関わる場合、ピアツーピアと呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="2a105-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="2a105-106">技術的には、2つのクライアントは1つの会話と1つの会話の間でやり取りされ、中央にはインスタントメッセージング multipoint コントロールユニット (IMMCU) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2a105-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="2a105-107">IMMCU は、フロントエンドサーバーのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="2a105-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="2a105-108">必要な通信ワークフローに IMMCU を配置すると、フロントエンドサーバーが有効になっている通話の詳細の記録とその他の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a105-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="2a105-109">通信は、クライアント上の動的ソースポートからフロントエンドサーバーポート TLS/TCP/5061 に送信されます (推奨トランスポート層セキュリティを使用していることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="2a105-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="2a105-110">設計上、ピアツーピア通信 (およびマルチパーティの IM) は、Lync Server と IMMCU がアクティブで利用可能な場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="2a105-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="2a105-111">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="2a105-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a105-112">サーバー上で Lync Server サービスを開始する前に、Windows ファイアウォールが実行されている必要があります。そのため、Lync Server はファイアウォールで必要なポートを開くことになります。</span><span class="sxs-lookup"><span data-stu-id="2a105-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="2a105-113">エッジコンポーネントのファイアウォール構成の詳細については、「 [Lync Server 2013 の外部の A/V ファイアウォールとポートの要件を確認](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a105-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="2a105-114">次の表に、各内部サーバー役割で開く必要のあるポートの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="2a105-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="2a105-115">必要なサーバー ポート (サーバー役割別)</span><span class="sxs-lookup"><span data-stu-id="2a105-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="2a105-116">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="2a105-116">Server role</span></span></th>
<th><span data-ttu-id="2a105-117">サービス名</span><span class="sxs-lookup"><span data-stu-id="2a105-117">Service name</span></span></th>
<th><span data-ttu-id="2a105-118">ポート</span><span class="sxs-lookup"><span data-stu-id="2a105-118">Port</span></span></th>
<th><span data-ttu-id="2a105-119">プロトコル</span><span class="sxs-lookup"><span data-stu-id="2a105-119">Protocol</span></span></th>
<th><span data-ttu-id="2a105-120">メモ</span><span class="sxs-lookup"><span data-stu-id="2a105-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a105-121">すべてのサーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-122">SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="2a105-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="2a105-123">1434</span><span class="sxs-lookup"><span data-stu-id="2a105-123">1434</span></span></p></td>
<td><p><span data-ttu-id="2a105-124">UDP</span><span class="sxs-lookup"><span data-stu-id="2a105-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="2a105-125">中央管理ストアデータベースのローカルでレプリケートされたコピーの SQL ブラウザー。</span><span class="sxs-lookup"><span data-stu-id="2a105-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-126">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-127">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="2a105-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2a105-128">5060</span><span class="sxs-lookup"><span data-stu-id="2a105-128">5060</span></span></p></td>
<td><p><span data-ttu-id="2a105-129">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-130">リモート通話コントロール サーバーなどの Standard Edition サーバーとフロントエンド サーバーで、信頼されたサービスへの静的ルートの場合にオプションとして使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-131">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-132">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="2a105-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2a105-133">5061</span><span class="sxs-lookup"><span data-stu-id="2a105-133">5061</span></span></p></td>
<td><p><span data-ttu-id="2a105-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2a105-135">サーバー間のすべての内部 SIP 通信 (MTLS)、サーバーとクライアントの間の SIP 通信 (TLS)、およびフロントエンド サーバーと仲介サーバーの間の SIP 通信 (MTLS) において、Standard Edition サーバーとフロントエンド プールで使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="2a105-136">監視サーバーとの通信にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a105-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-137">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-138">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="2a105-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2a105-139">444</span><span class="sxs-lookup"><span data-stu-id="2a105-139">444</span></span></p></td>
<td><p><span data-ttu-id="2a105-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a105-140">HTTPS</span></span></p>
<p><span data-ttu-id="2a105-141">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-142">フォーカス (会議の状態を管理する Lync Server コンポーネント) と個々のサーバーの間の HTTPS 通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a105-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="2a105-143">このポートは、Survivable Branch アプライアンスとフロントエンドサーバー間の TCP 通信にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a105-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-144">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-145">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="2a105-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2a105-146">135</span><span class="sxs-lookup"><span data-stu-id="2a105-146">135</span></span></p></td>
<td><p><span data-ttu-id="2a105-147">DCOM およびリモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="2a105-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="2a105-148">ユーザーの移行、ユーザー レプリケーター同期、およびアドレス帳同期などの DCOM ベースの操作で使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-149">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-150">Lync Server IM 会議サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="2a105-151">5062</span><span class="sxs-lookup"><span data-stu-id="2a105-151">5062</span></span></p></td>
<td><p><span data-ttu-id="2a105-152">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-153">インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-154">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-155">Lync Server Web 会議サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="2a105-156">8057</span><span class="sxs-lookup"><span data-stu-id="2a105-156">8057</span></span></p></td>
<td><p><span data-ttu-id="2a105-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2a105-158">クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-159">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-160">Lync Server Web 会議互換サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="2a105-161">8058</span><span class="sxs-lookup"><span data-stu-id="2a105-161">8058</span></span></p></td>
<td><p><span data-ttu-id="2a105-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2a105-163">Live Meeting クライアントと以前のバージョンの Lync Server からの永続的な共有オブジェクトモデル (PSOM) 接続をリッスンするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a105-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-164">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-165">Lync Server の音声/ビデオ会議サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="2a105-166">5063</span><span class="sxs-lookup"><span data-stu-id="2a105-166">5063</span></span></p></td>
<td><p><span data-ttu-id="2a105-167">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-168">音声ビデオ会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-169">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-170">Lync Server の音声/ビデオ会議サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="2a105-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="2a105-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="2a105-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="2a105-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="2a105-173">ビデオ会議で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="2a105-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-174">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-175">Lync Server Web 互換サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="2a105-176">80</span><span class="sxs-lookup"><span data-stu-id="2a105-176">80</span></span></p></td>
<td><p><span data-ttu-id="2a105-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="2a105-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="2a105-178">HTTPS が使用されない場合の、フロントエンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-179">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-180">Lync Server Web 互換サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="2a105-181">443</span><span class="sxs-lookup"><span data-stu-id="2a105-181">443</span></span></p></td>
<td><p><span data-ttu-id="2a105-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a105-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="2a105-183">フロントエンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-184">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-185">Lync Server Web 互換サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="2a105-186">8080</span><span class="sxs-lookup"><span data-stu-id="2a105-186">8080</span></span></p></td>
<td><p><span data-ttu-id="2a105-187">TCP および HTTP</span><span class="sxs-lookup"><span data-stu-id="2a105-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="2a105-188">外部アクセスのために Web コンポーネントで使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-189">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-190">Web サーバー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2a105-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="2a105-191">4443</span><span class="sxs-lookup"><span data-stu-id="2a105-191">4443</span></span></p></td>
<td><p><span data-ttu-id="2a105-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a105-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="2a105-193">Autodiscover サインインのための HTTPS (リバース プロキシから) および HTTPS フロント エンドのプール間通信。</span><span class="sxs-lookup"><span data-stu-id="2a105-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-194">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-195">Web サーバー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2a105-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="2a105-196">8060</span><span class="sxs-lookup"><span data-stu-id="2a105-196">8060</span></span></p></td>
<td><p><span data-ttu-id="2a105-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-198">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-199">Web サーバー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2a105-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="2a105-200">8061</span><span class="sxs-lookup"><span data-stu-id="2a105-200">8061</span></span></p></td>
<td><p><span data-ttu-id="2a105-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-202">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-203">Mobility Service コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2a105-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="2a105-204">5086</span><span class="sxs-lookup"><span data-stu-id="2a105-204">5086</span></span></p></td>
<td><p><span data-ttu-id="2a105-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="2a105-206">Mobility Service の内部プロセスに使用される SIP ポート。</span><span class="sxs-lookup"><span data-stu-id="2a105-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-207">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-208">Mobility Service コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2a105-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="2a105-209">5087</span><span class="sxs-lookup"><span data-stu-id="2a105-209">5087</span></span></p></td>
<td><p><span data-ttu-id="2a105-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="2a105-211">Mobility Service の内部プロセスに使用される SIP ポート。</span><span class="sxs-lookup"><span data-stu-id="2a105-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-212">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-213">Mobility Service コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2a105-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="2a105-214">443</span><span class="sxs-lookup"><span data-stu-id="2a105-214">443</span></span></p></td>
<td><p><span data-ttu-id="2a105-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a105-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-216">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-217">Lync Server 会議アテンダントサービス (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="2a105-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="2a105-218">5064</span><span class="sxs-lookup"><span data-stu-id="2a105-218">5064</span></span></p></td>
<td><p><span data-ttu-id="2a105-219">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-220">ダイヤルイン会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-221">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-222">Lync Server 会議アテンダントサービス (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="2a105-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="2a105-223">5072</span><span class="sxs-lookup"><span data-stu-id="2a105-223">5072</span></span></p></td>
<td><p><span data-ttu-id="2a105-224">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-225">応答の受信 SIP 要求 (ダイヤルイン会議) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a105-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-226">併置された仲介サーバーも実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="2a105-227">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2a105-228">5070</span><span class="sxs-lookup"><span data-stu-id="2a105-228">5070</span></span></p></td>
<td><p><span data-ttu-id="2a105-229">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-230">フロントエンド サーバーから仲介サーバーへの要求を受信するために仲介サーバーで使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-231">併置された仲介サーバーも実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="2a105-232">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2a105-233">5067</span><span class="sxs-lookup"><span data-stu-id="2a105-233">5067</span></span></p></td>
<td><p><span data-ttu-id="2a105-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2a105-235">PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-236">併置された仲介サーバーも実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="2a105-237">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2a105-238">5068</span><span class="sxs-lookup"><span data-stu-id="2a105-238">5068</span></span></p></td>
<td><p><span data-ttu-id="2a105-239">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-240">PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-241">併置された仲介サーバーも実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="2a105-242">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2a105-243">5081</span><span class="sxs-lookup"><span data-stu-id="2a105-243">5081</span></span></p></td>
<td><p><span data-ttu-id="2a105-244">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-245">仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-246">併置された仲介サーバーも実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="2a105-247">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2a105-248">5082</span><span class="sxs-lookup"><span data-stu-id="2a105-248">5082</span></span></p></td>
<td><p><span data-ttu-id="2a105-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2a105-250">仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-251">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-252">Lync Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="2a105-253">5065</span><span class="sxs-lookup"><span data-stu-id="2a105-253">5065</span></span></p></td>
<td><p><span data-ttu-id="2a105-254">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-255">アプリケーション共有の SIP リッスン要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-256">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-257">Lync Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="2a105-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="2a105-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="2a105-259">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-260">アプリケーション共有で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="2a105-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-261">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-262">Lync Server 会議のアナウンスメントサービス</span><span class="sxs-lookup"><span data-stu-id="2a105-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="2a105-263">5073</span><span class="sxs-lookup"><span data-stu-id="2a105-263">5073</span></span></p></td>
<td><p><span data-ttu-id="2a105-264">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-265">Lync Server 会議のアナウンスメントサービス (ダイヤルイン会議) の受信 SIP 要求に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a105-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-266">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-267">Lync Server コール パーク サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="2a105-268">5075</span><span class="sxs-lookup"><span data-stu-id="2a105-268">5075</span></span></p></td>
<td><p><span data-ttu-id="2a105-269">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-270">コール パーク アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-271">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-272">Lync Server の音声テストサービス</span><span class="sxs-lookup"><span data-stu-id="2a105-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="2a105-273">5076</span><span class="sxs-lookup"><span data-stu-id="2a105-273">5076</span></span></p></td>
<td><p><span data-ttu-id="2a105-274">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-275">オーディオ テスト サービスの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-276">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-277">該当なし</span><span class="sxs-lookup"><span data-stu-id="2a105-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="2a105-278">5066</span><span class="sxs-lookup"><span data-stu-id="2a105-278">5066</span></span></p></td>
<td><p><span data-ttu-id="2a105-279">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-280">発信 Enhanced 9-1-1 (E9-1-1) ゲートウェイで使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-281">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-282">Lync Server 応答グループ サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="2a105-283">5071</span><span class="sxs-lookup"><span data-stu-id="2a105-283">5071</span></span></p></td>
<td><p><span data-ttu-id="2a105-284">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-285">応答グループ アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-286">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-287">Lync Server 応答グループ サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="2a105-288">8404</span><span class="sxs-lookup"><span data-stu-id="2a105-288">8404</span></span></p></td>
<td><p><span data-ttu-id="2a105-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="2a105-290">応答グループ アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-291">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-292">Lync Server 帯域幅ポリシーサービス</span><span class="sxs-lookup"><span data-stu-id="2a105-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="2a105-293">5080</span><span class="sxs-lookup"><span data-stu-id="2a105-293">5080</span></span></p></td>
<td><p><span data-ttu-id="2a105-294">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-295">音声ビデオ エッジ TURN トラフィックの帯域幅ポリシー サービスによる通話受付管理で使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-296">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-297">Lync Server 帯域幅ポリシーサービス</span><span class="sxs-lookup"><span data-stu-id="2a105-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="2a105-298">448</span><span class="sxs-lookup"><span data-stu-id="2a105-298">448</span></span></p></td>
<td><p><span data-ttu-id="2a105-299">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-300">Lync Server 帯域幅ポリシーサービスによる通話受付制御に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a105-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-301">中央管理ストアが配置されているフロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="2a105-302">Lync Server マスターレプリケーターエージェントサービス</span><span class="sxs-lookup"><span data-stu-id="2a105-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="2a105-303">445</span><span class="sxs-lookup"><span data-stu-id="2a105-303">445</span></span></p></td>
<td><p><span data-ttu-id="2a105-304">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-305">Lync Server を実行しているサーバーに、中央の管理ストアから構成データをプッシュするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a105-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-306">すべてのサーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-307">SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="2a105-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="2a105-308">1434</span><span class="sxs-lookup"><span data-stu-id="2a105-308">1434</span></span></p></td>
<td><p><span data-ttu-id="2a105-309">UDP</span><span class="sxs-lookup"><span data-stu-id="2a105-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="2a105-310">ローカルの SQL Server インスタンスの中央管理ストアデータのローカルにレプリケートされたコピー用の SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="2a105-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-311">すべての内部サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-312">各種</span><span class="sxs-lookup"><span data-stu-id="2a105-312">Various</span></span></p></td>
<td><p><span data-ttu-id="2a105-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="2a105-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="2a105-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="2a105-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="2a105-315">すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="2a105-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="2a105-316">オーディオを終了するすべてのサーバーで使用されます。フロントエンドサーバー (Lync Server 会議アテンダントサービス、Lync Server 会議のアナウンスメントサービス、Lync Server Audio/ビデオ会議サービス、および仲介サーバー)。</span><span class="sxs-lookup"><span data-stu-id="2a105-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-317">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a105-318">443</span><span class="sxs-lookup"><span data-stu-id="2a105-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a105-319">Lync Server 2013 で Office Web Apps サーバーに接続するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a105-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-320">ディレクター</span><span class="sxs-lookup"><span data-stu-id="2a105-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="2a105-321">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="2a105-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2a105-322">5060</span><span class="sxs-lookup"><span data-stu-id="2a105-322">5060</span></span></p></td>
<td><p><span data-ttu-id="2a105-323">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-324">リモート通話コントロール サーバーなど、信頼されたサービスへの静的ルートの場合にオプションで使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-325">ディレクター</span><span class="sxs-lookup"><span data-stu-id="2a105-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="2a105-326">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="2a105-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2a105-327">444</span><span class="sxs-lookup"><span data-stu-id="2a105-327">444</span></span></p></td>
<td><p><span data-ttu-id="2a105-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a105-328">HTTPS</span></span></p>
<p><span data-ttu-id="2a105-329">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-330">フロントエンドとディレクターの間のサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="2a105-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="2a105-331">さらに、クライアント証明書公開 (フロントエンドサーバー) またはクライアント証明書が既に公開されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a105-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-332">ディレクター</span><span class="sxs-lookup"><span data-stu-id="2a105-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="2a105-333">Lync Server Web 互換サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="2a105-334">80</span><span class="sxs-lookup"><span data-stu-id="2a105-334">80</span></span></p></td>
<td><p><span data-ttu-id="2a105-335">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-p105">ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への初期通信に使用。通常の動作では HTTPS トラフィックに切り替わり、ポート 443 およびプロトコル TCP を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a105-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-338">ディレクター</span><span class="sxs-lookup"><span data-stu-id="2a105-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="2a105-339">Lync Server Web 互換サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="2a105-340">443</span><span class="sxs-lookup"><span data-stu-id="2a105-340">443</span></span></p></td>
<td><p><span data-ttu-id="2a105-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a105-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="2a105-342">ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-343">ディレクター</span><span class="sxs-lookup"><span data-stu-id="2a105-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="2a105-344">Lync Server のフロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="2a105-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2a105-345">5061</span><span class="sxs-lookup"><span data-stu-id="2a105-345">5061</span></span></p></td>
<td><p><span data-ttu-id="2a105-346">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-347">サーバー間の内部通信とクライアント接続に使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-348">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-349">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2a105-350">5070</span><span class="sxs-lookup"><span data-stu-id="2a105-350">5070</span></span></p></td>
<td><p><span data-ttu-id="2a105-351">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-352">フロントエンド サーバーからの要求を受信するために仲介サーバーで使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-353">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-354">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2a105-355">5067</span><span class="sxs-lookup"><span data-stu-id="2a105-355">5067</span></span></p></td>
<td><p><span data-ttu-id="2a105-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2a105-357">PSTN ゲートウェイからの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-358">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-359">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2a105-360">5068</span><span class="sxs-lookup"><span data-stu-id="2a105-360">5068</span></span></p></td>
<td><p><span data-ttu-id="2a105-361">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-362">PSTN ゲートウェイからの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-363">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="2a105-364">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2a105-365">5070</span><span class="sxs-lookup"><span data-stu-id="2a105-365">5070</span></span></p></td>
<td><p><span data-ttu-id="2a105-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="2a105-367">フロントエンド サーバーからの SIP 要求で使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-368">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="2a105-369">常設チャット SIP</span><span class="sxs-lookup"><span data-stu-id="2a105-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="2a105-370">5041</span><span class="sxs-lookup"><span data-stu-id="2a105-370">5041</span></span></p></td>
<td><p><span data-ttu-id="2a105-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-372">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="2a105-373">常設チャット Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="2a105-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="2a105-374">881</span><span class="sxs-lookup"><span data-stu-id="2a105-374">881</span></span></p></td>
<td><p><span data-ttu-id="2a105-375">TCP (TLS) および TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-376">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="2a105-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="2a105-377">常設チャット ファイル転送サービス</span><span class="sxs-lookup"><span data-stu-id="2a105-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="2a105-378">443</span><span class="sxs-lookup"><span data-stu-id="2a105-378">443</span></span></p></td>
<td><p><span data-ttu-id="2a105-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2a105-380">一部のリモート通話コントロールシナリオでは、フロントエンドサーバーまたはディレクターと PBX の間に TCP 接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="2a105-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="2a105-381">Lync Server は TCP ポート5060を使用しなくなりましたが、リモートコールコントロールの展開時には、RCC Line Server の FQDN と、フロントエンドサーバーまたはディレクターが PBX システムに接続するために使用する TCP ポートを関連付ける信頼されたサーバー構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="2a105-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="2a105-382">詳細については、「Lync Server 管理シェルドキュメントの<STRONG>CsTrustedApplicationComputer</STRONG>コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a105-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="2a105-383">次の表に、(DNS 負荷分散ではない) ハードウェア負荷分散のみを使用するプールでハードウェア ロード バランサーを開くために必要なポートを示します。</span><span class="sxs-lookup"><span data-stu-id="2a105-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="2a105-384">ハードウェア負荷分散のみを使用する場合のハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a105-385">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-385">Load Balancer</span></span></th>
<th><span data-ttu-id="2a105-386">ポート</span><span class="sxs-lookup"><span data-stu-id="2a105-386">Port</span></span></th>
<th><span data-ttu-id="2a105-387">プロトコル</span><span class="sxs-lookup"><span data-stu-id="2a105-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a105-388">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-389">5061</span><span class="sxs-lookup"><span data-stu-id="2a105-389">5061</span></span></p></td>
<td><p><span data-ttu-id="2a105-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-391">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-392">444</span><span class="sxs-lookup"><span data-stu-id="2a105-392">444</span></span></p></td>
<td><p><span data-ttu-id="2a105-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a105-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-394">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-395">135</span><span class="sxs-lookup"><span data-stu-id="2a105-395">135</span></span></p></td>
<td><p><span data-ttu-id="2a105-396">DCOM およびリモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="2a105-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-397">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-398">80</span><span class="sxs-lookup"><span data-stu-id="2a105-398">80</span></span></p></td>
<td><p><span data-ttu-id="2a105-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="2a105-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-400">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-401">8080</span><span class="sxs-lookup"><span data-stu-id="2a105-401">8080</span></span></p></td>
<td><p><span data-ttu-id="2a105-402">TCP - フロントエンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</span><span class="sxs-lookup"><span data-stu-id="2a105-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-403">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-404">443</span><span class="sxs-lookup"><span data-stu-id="2a105-404">443</span></span></p></td>
<td><p><span data-ttu-id="2a105-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a105-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-406">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-407">4443</span><span class="sxs-lookup"><span data-stu-id="2a105-407">4443</span></span></p></td>
<td><p><span data-ttu-id="2a105-408">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="2a105-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-409">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-410">5072</span><span class="sxs-lookup"><span data-stu-id="2a105-410">5072</span></span></p></td>
<td><p><span data-ttu-id="2a105-411">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-412">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-413">5073</span><span class="sxs-lookup"><span data-stu-id="2a105-413">5073</span></span></p></td>
<td><p><span data-ttu-id="2a105-414">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-415">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-416">5075</span><span class="sxs-lookup"><span data-stu-id="2a105-416">5075</span></span></p></td>
<td><p><span data-ttu-id="2a105-417">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-418">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-419">5076</span><span class="sxs-lookup"><span data-stu-id="2a105-419">5076</span></span></p></td>
<td><p><span data-ttu-id="2a105-420">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-421">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-422">5071</span><span class="sxs-lookup"><span data-stu-id="2a105-422">5071</span></span></p></td>
<td><p><span data-ttu-id="2a105-423">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-424">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-425">5080</span><span class="sxs-lookup"><span data-stu-id="2a105-425">5080</span></span></p></td>
<td><p><span data-ttu-id="2a105-426">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-427">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-428">448</span><span class="sxs-lookup"><span data-stu-id="2a105-428">448</span></span></p></td>
<td><p><span data-ttu-id="2a105-429">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-430">仲介サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-431">5070</span><span class="sxs-lookup"><span data-stu-id="2a105-431">5070</span></span></p></td>
<td><p><span data-ttu-id="2a105-432">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-433">フロントエンド サーバーのロード バランサー (プールで仲介サーバーも稼働する場合)</span><span class="sxs-lookup"><span data-stu-id="2a105-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="2a105-434">5070</span><span class="sxs-lookup"><span data-stu-id="2a105-434">5070</span></span></p></td>
<td><p><span data-ttu-id="2a105-435">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-436">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-437">443</span><span class="sxs-lookup"><span data-stu-id="2a105-437">443</span></span></p></td>
<td><p><span data-ttu-id="2a105-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a105-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-439">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-440">444</span><span class="sxs-lookup"><span data-stu-id="2a105-440">444</span></span></p></td>
<td><p><span data-ttu-id="2a105-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a105-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-442">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-443">5061</span><span class="sxs-lookup"><span data-stu-id="2a105-443">5061</span></span></p></td>
<td><p><span data-ttu-id="2a105-444">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-445">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-446">4443</span><span class="sxs-lookup"><span data-stu-id="2a105-446">4443</span></span></p></td>
<td><p><span data-ttu-id="2a105-447">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="2a105-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2a105-p107">DNS 負荷分散を使用するフロントエンド プールとディレクター プールでも、ハードウェア ロード バランサーを展開しておく必要があります。次の表に、これらのハードウェア ロード バランサーで開く必要があるポートを示します。</span><span class="sxs-lookup"><span data-stu-id="2a105-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="2a105-450">DNS 負荷分散を使用する場合のハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a105-451">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-451">Load Balancer</span></span></th>
<th><span data-ttu-id="2a105-452">ポート</span><span class="sxs-lookup"><span data-stu-id="2a105-452">Port</span></span></th>
<th><span data-ttu-id="2a105-453">プロトコル</span><span class="sxs-lookup"><span data-stu-id="2a105-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a105-454">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-455">80</span><span class="sxs-lookup"><span data-stu-id="2a105-455">80</span></span></p></td>
<td><p><span data-ttu-id="2a105-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="2a105-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-457">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-458">443</span><span class="sxs-lookup"><span data-stu-id="2a105-458">443</span></span></p></td>
<td><p><span data-ttu-id="2a105-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a105-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-460">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-461">8080</span><span class="sxs-lookup"><span data-stu-id="2a105-461">8080</span></span></p></td>
<td><p><span data-ttu-id="2a105-462">TCP - フロントエンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</span><span class="sxs-lookup"><span data-stu-id="2a105-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-463">フロントエンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-464">4443</span><span class="sxs-lookup"><span data-stu-id="2a105-464">4443</span></span></p></td>
<td><p><span data-ttu-id="2a105-465">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="2a105-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-466">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-467">443</span><span class="sxs-lookup"><span data-stu-id="2a105-467">443</span></span></p></td>
<td><p><span data-ttu-id="2a105-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a105-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-469">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="2a105-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="2a105-470">4443</span><span class="sxs-lookup"><span data-stu-id="2a105-470">4443</span></span></p></td>
<td><p><span data-ttu-id="2a105-471">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="2a105-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="2a105-472">必要なクライアント ポート</span><span class="sxs-lookup"><span data-stu-id="2a105-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a105-473">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2a105-473">Component</span></span></th>
<th><span data-ttu-id="2a105-474">ポート</span><span class="sxs-lookup"><span data-stu-id="2a105-474">Port</span></span></th>
<th><span data-ttu-id="2a105-475">プロトコル</span><span class="sxs-lookup"><span data-stu-id="2a105-475">Protocol</span></span></th>
<th><span data-ttu-id="2a105-476">メモ</span><span class="sxs-lookup"><span data-stu-id="2a105-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a105-477">クライアント</span><span class="sxs-lookup"><span data-stu-id="2a105-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="2a105-478">67/68</span><span class="sxs-lookup"><span data-stu-id="2a105-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="2a105-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="2a105-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-480">Lync Server によってレジストラーの FQDN が検索されます (つまり、DNS SRV に障害が発生した場合は、手動の設定が構成されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="2a105-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-481">クライアント</span><span class="sxs-lookup"><span data-stu-id="2a105-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="2a105-482">443</span><span class="sxs-lookup"><span data-stu-id="2a105-482">443</span></span></p></td>
<td><p><span data-ttu-id="2a105-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2a105-484">外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-485">クライアント</span><span class="sxs-lookup"><span data-stu-id="2a105-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="2a105-486">443</span><span class="sxs-lookup"><span data-stu-id="2a105-486">443</span></span></p></td>
<td><p><span data-ttu-id="2a105-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="2a105-488">Web 会議セッションへの外部ユーザー アクセスで使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-489">クライアント</span><span class="sxs-lookup"><span data-stu-id="2a105-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="2a105-490">443</span><span class="sxs-lookup"><span data-stu-id="2a105-490">443</span></span></p></td>
<td><p><span data-ttu-id="2a105-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="2a105-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="2a105-492">音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-493">クライアント</span><span class="sxs-lookup"><span data-stu-id="2a105-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="2a105-494">3478</span><span class="sxs-lookup"><span data-stu-id="2a105-494">3478</span></span></p></td>
<td><p><span data-ttu-id="2a105-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="2a105-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="2a105-496">音声ビデオ セッションとメディアへの外部ユーザー アクセス (UDP) で使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-497">クライアント</span><span class="sxs-lookup"><span data-stu-id="2a105-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="2a105-498">5061</span><span class="sxs-lookup"><span data-stu-id="2a105-498">5061</span></span></p></td>
<td><p><span data-ttu-id="2a105-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2a105-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="2a105-500">外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</span><span class="sxs-lookup"><span data-stu-id="2a105-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-501">クライアント</span><span class="sxs-lookup"><span data-stu-id="2a105-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="2a105-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="2a105-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="2a105-503">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-504">Lync クライアントと以前のクライアント (Microsoft Office Communications Server 2007 R2、Microsoft Office Communications Server 2007、Live Communications Server 2005) の間でのファイル送信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a105-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-505">クライアント</span><span class="sxs-lookup"><span data-stu-id="2a105-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="2a105-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="2a105-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="2a105-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="2a105-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="2a105-508">オーディオ ポート範囲 (少なくとも 20 個のポートが必要)。</span><span class="sxs-lookup"><span data-stu-id="2a105-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-509">クライアント</span><span class="sxs-lookup"><span data-stu-id="2a105-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="2a105-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="2a105-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="2a105-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="2a105-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="2a105-512">ビデオ ポート範囲 (少なくとも 20 個のポートが必要)。</span><span class="sxs-lookup"><span data-stu-id="2a105-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-513">クライアント</span><span class="sxs-lookup"><span data-stu-id="2a105-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="2a105-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="2a105-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="2a105-515">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-516">ピアツーピア ファイル転送 (会議ファイル転送の場合、クライアントは PSOM を使用)。</span><span class="sxs-lookup"><span data-stu-id="2a105-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a105-517">クライアント</span><span class="sxs-lookup"><span data-stu-id="2a105-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="2a105-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="2a105-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="2a105-519">TCP</span><span class="sxs-lookup"><span data-stu-id="2a105-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-520">アプリケーション共有。</span><span class="sxs-lookup"><span data-stu-id="2a105-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a105-521">Aastra 6721ip 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="2a105-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="2a105-522">Aastra 6725ip 卓上電話</span><span class="sxs-lookup"><span data-stu-id="2a105-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="2a105-523">HP 4110 IP 電話 (共通領域電話)</span><span class="sxs-lookup"><span data-stu-id="2a105-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="2a105-524">HP 4120 IP 電話 (卓上電話)</span><span class="sxs-lookup"><span data-stu-id="2a105-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="2a105-525">Polycom CX500 IP 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="2a105-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="2a105-526">Polycom CX600 IP 卓上電話</span><span class="sxs-lookup"><span data-stu-id="2a105-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="2a105-527">Polycom CX700 IP 卓上電話</span><span class="sxs-lookup"><span data-stu-id="2a105-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="2a105-528">Polycom CX3000 IP 会議電話</span><span class="sxs-lookup"><span data-stu-id="2a105-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="2a105-529">67/68</span><span class="sxs-lookup"><span data-stu-id="2a105-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="2a105-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="2a105-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="2a105-531">リストされているデバイスで使用され、Lync Server 証明書、プロビジョニング FQDN、レジストラー FQDN を検索します。</span><span class="sxs-lookup"><span data-stu-id="2a105-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2a105-532">**\*** これらのメディアの種類に対して特定のポートを構成するには、CsConferencingConfiguration コマンドレット (ClientMediaPortRangeEnabled、ClientMediaPort、ClientMediaPortRange parameters) を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a105-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a105-533">Lync クライアント用のプログラムを設定すると、必要なオペレーティングシステムファイアウォール例外がクライアントコンピューターに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="2a105-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2a105-534">外部ユーザー アクセス用に使用されるポートは、クライアントが組織のファイアウォールを通過する必要のあるすべてのシナリオにおいて必要です (たとえば、他の組織によってホストされる外部の通信や会議)。</span><span class="sxs-lookup"><span data-stu-id="2a105-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

