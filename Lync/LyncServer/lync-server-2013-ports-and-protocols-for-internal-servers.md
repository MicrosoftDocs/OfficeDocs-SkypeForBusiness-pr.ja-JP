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
ms.openlocfilehash: 858ec90cf3811318cc29a902b56ac8ff31c46a22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513404"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="1a500-102">Lync Server 2013 の内部サーバーのポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="1a500-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a500-103">_**トピックの最終更新日:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="1a500-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="1a500-104">このセクションでは、Lync Server 展開のサーバー、ロードバランサー、およびクライアントで使用されるポートとプロトコルの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a500-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1a500-105">1対1の通信に関係する Lync および Communicator クライアントは、ピアツーピアと呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="1a500-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="1a500-106">技術的には、2つのクライアントは1つの会話に、インスタントメッセージング multipoint control unit (IMMCU) を中央に持つ1つの会話と通信します。</span><span class="sxs-lookup"><span data-stu-id="1a500-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="1a500-107">IMMCU はフロントエンドサーバーのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="1a500-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="1a500-108">必要な通信ワークフローに IMMCU を配置すると、フロントエンドサーバーが有効になっている通話詳細記録およびその他の機能を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1a500-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="1a500-109">クライアント上の動的送信元ポートからフロントエンドサーバーポート TLS/TCP/5061 への通信です (推奨トランスポート層セキュリティを使用していることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="1a500-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="1a500-110">設計上、Lync Server と IMMCU がアクティブで利用可能な場合にのみ、ピアツーピア通信 (およびマルチパーティ IM) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a500-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="1a500-111">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="1a500-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a500-112">Lync server がファイアウォールで必要なポートを開くときに、サーバー上で Lync Server サービスを開始する前に、Windows ファイアウォールを実行しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a500-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="1a500-113">エッジコンポーネントのファイアウォール構成の詳細については、「 [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a500-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="1a500-114">次の表に、各内部サーバー役割で開く必要のあるポートの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="1a500-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="1a500-115">必要なサーバー ポート (サーバー役割別)</span><span class="sxs-lookup"><span data-stu-id="1a500-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="1a500-116">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="1a500-116">Server role</span></span></th>
<th><span data-ttu-id="1a500-117">サービス名</span><span class="sxs-lookup"><span data-stu-id="1a500-117">Service name</span></span></th>
<th><span data-ttu-id="1a500-118">ポート</span><span class="sxs-lookup"><span data-stu-id="1a500-118">Port</span></span></th>
<th><span data-ttu-id="1a500-119">プロトコル</span><span class="sxs-lookup"><span data-stu-id="1a500-119">Protocol</span></span></th>
<th><span data-ttu-id="1a500-120">Notes</span><span class="sxs-lookup"><span data-stu-id="1a500-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a500-121">すべてのサーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-122">SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="1a500-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="1a500-123">1434</span><span class="sxs-lookup"><span data-stu-id="1a500-123">1434</span></span></p></td>
<td><p><span data-ttu-id="1a500-124">受信</span><span class="sxs-lookup"><span data-stu-id="1a500-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="1a500-125">中央管理ストアデータベースのローカルにレプリケートされたコピーの SQL ブラウザー。</span><span class="sxs-lookup"><span data-stu-id="1a500-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-126">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-127">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="1a500-128">5060</span><span class="sxs-lookup"><span data-stu-id="1a500-128">5060</span></span></p></td>
<td><p><span data-ttu-id="1a500-129">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-130">リモート通話コントロール サーバーなどの Standard Edition サーバーとフロント エンド サーバーで、信頼されたサービスへの静的ルートの場合にオプションとして使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-131">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-132">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="1a500-133">5061</span><span class="sxs-lookup"><span data-stu-id="1a500-133">5061</span></span></p></td>
<td><p><span data-ttu-id="1a500-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="1a500-p102">サーバー間のすべての内部 SIP 通信 (MTLS)、サーバーとクライアントの間の SIP 通信 (TLS)、およびフロント エンド サーバーと仲介サーバーの間の SIP 通信 (MTLS) において、Standard Edition サーバーとフロント エンド プールで使用。 監視サーバーとの通信でも使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-137">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-138">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="1a500-139">444</span><span class="sxs-lookup"><span data-stu-id="1a500-139">444</span></span></p></td>
<td><p><span data-ttu-id="1a500-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1a500-140">HTTPS</span></span></p>
<p><span data-ttu-id="1a500-141">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-142">フォーカス (会議の状態を管理する Lync Server コンポーネント) と個々のサーバーとの間の HTTPS 通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a500-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="1a500-143">このポートは、存続可能ブランチアプライアンスとフロントエンドサーバー間の TCP 通信にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a500-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-144">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-145">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="1a500-146">135</span><span class="sxs-lookup"><span data-stu-id="1a500-146">135</span></span></p></td>
<td><p><span data-ttu-id="1a500-147">DCOM およびリモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="1a500-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="1a500-148">ユーザーの移行、ユーザー レプリケーター同期、およびアドレス帳同期などの DCOM ベースの操作で使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-149">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-150">Lync Server IM 会議サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="1a500-151">5062</span><span class="sxs-lookup"><span data-stu-id="1a500-151">5062</span></span></p></td>
<td><p><span data-ttu-id="1a500-152">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-153">インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-154">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-155">Lync Server Web 会議サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="1a500-156">8057</span><span class="sxs-lookup"><span data-stu-id="1a500-156">8057</span></span></p></td>
<td><p><span data-ttu-id="1a500-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="1a500-158">クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-159">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-160">Lync Server Web 会議互換性サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="1a500-161">8058</span><span class="sxs-lookup"><span data-stu-id="1a500-161">8058</span></span></p></td>
<td><p><span data-ttu-id="1a500-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="1a500-163">Live Meeting クライアントおよび以前のバージョンの Lync Server からの、永続的な共有オブジェクトモデル (PSOM) 接続をリッスンするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a500-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-164">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-165">Lync Server 音声ビデオ会議サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="1a500-166">5063</span><span class="sxs-lookup"><span data-stu-id="1a500-166">5063</span></span></p></td>
<td><p><span data-ttu-id="1a500-167">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-168">音声ビデオ会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-169">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-170">Lync Server 音声ビデオ会議サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="1a500-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="1a500-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="1a500-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="1a500-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="1a500-173">ビデオ会議で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="1a500-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-174">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-175">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="1a500-176">80</span><span class="sxs-lookup"><span data-stu-id="1a500-176">80</span></span></p></td>
<td><p><span data-ttu-id="1a500-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="1a500-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="1a500-178">HTTPS が使用されない場合の、フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-179">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-180">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="1a500-181">443</span><span class="sxs-lookup"><span data-stu-id="1a500-181">443</span></span></p></td>
<td><p><span data-ttu-id="1a500-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1a500-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="1a500-183">フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-184">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-185">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="1a500-186">8080</span><span class="sxs-lookup"><span data-stu-id="1a500-186">8080</span></span></p></td>
<td><p><span data-ttu-id="1a500-187">TCP および HTTP</span><span class="sxs-lookup"><span data-stu-id="1a500-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="1a500-188">外部アクセスのために web コンポーネントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a500-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-189">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-190">Web サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="1a500-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="1a500-191">4443</span><span class="sxs-lookup"><span data-stu-id="1a500-191">4443</span></span></p></td>
<td><p><span data-ttu-id="1a500-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1a500-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="1a500-193">自動検出サインインの HTTPS (リバースプロキシから) および HTTPS フロントエンドプール間通信。</span><span class="sxs-lookup"><span data-stu-id="1a500-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-194">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-195">Web サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="1a500-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="1a500-196">8060</span><span class="sxs-lookup"><span data-stu-id="1a500-196">8060</span></span></p></td>
<td><p><span data-ttu-id="1a500-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-198">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-199">Web サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="1a500-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="1a500-200">8061</span><span class="sxs-lookup"><span data-stu-id="1a500-200">8061</span></span></p></td>
<td><p><span data-ttu-id="1a500-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-202">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-203">Mobility Services コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1a500-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="1a500-204">5086</span><span class="sxs-lookup"><span data-stu-id="1a500-204">5086</span></span></p></td>
<td><p><span data-ttu-id="1a500-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="1a500-206">Mobility Services 内部プロセスで使用される SIP ポート</span><span class="sxs-lookup"><span data-stu-id="1a500-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-207">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-208">Mobility Services コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1a500-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="1a500-209">5087</span><span class="sxs-lookup"><span data-stu-id="1a500-209">5087</span></span></p></td>
<td><p><span data-ttu-id="1a500-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="1a500-211">Mobility Services 内部プロセスで使用される SIP ポート</span><span class="sxs-lookup"><span data-stu-id="1a500-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-212">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-213">Mobility Services コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1a500-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="1a500-214">443</span><span class="sxs-lookup"><span data-stu-id="1a500-214">443</span></span></p></td>
<td><p><span data-ttu-id="1a500-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1a500-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-216">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-217">Lync Server 会議アテンダントサービス (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="1a500-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="1a500-218">5064</span><span class="sxs-lookup"><span data-stu-id="1a500-218">5064</span></span></p></td>
<td><p><span data-ttu-id="1a500-219">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-220">ダイヤルイン会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-221">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-222">Lync Server 会議アテンダントサービス (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="1a500-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="1a500-223">5072</span><span class="sxs-lookup"><span data-stu-id="1a500-223">5072</span></span></p></td>
<td><p><span data-ttu-id="1a500-224">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-225">アテンダント (ダイヤルイン会議) の SIP 要求を受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a500-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-226">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="1a500-227">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="1a500-228">5070</span><span class="sxs-lookup"><span data-stu-id="1a500-228">5070</span></span></p></td>
<td><p><span data-ttu-id="1a500-229">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-230">フロント エンド サーバーから仲介サーバーへの要求を受信するために仲介サーバーで使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-231">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="1a500-232">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="1a500-233">5067</span><span class="sxs-lookup"><span data-stu-id="1a500-233">5067</span></span></p></td>
<td><p><span data-ttu-id="1a500-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="1a500-235">PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-236">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="1a500-237">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="1a500-238">5068</span><span class="sxs-lookup"><span data-stu-id="1a500-238">5068</span></span></p></td>
<td><p><span data-ttu-id="1a500-239">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-240">PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-241">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="1a500-242">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="1a500-243">5081</span><span class="sxs-lookup"><span data-stu-id="1a500-243">5081</span></span></p></td>
<td><p><span data-ttu-id="1a500-244">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-245">仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-246">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="1a500-247">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="1a500-248">5082</span><span class="sxs-lookup"><span data-stu-id="1a500-248">5082</span></span></p></td>
<td><p><span data-ttu-id="1a500-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="1a500-250">仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-251">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-252">Lync Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="1a500-253">5065</span><span class="sxs-lookup"><span data-stu-id="1a500-253">5065</span></span></p></td>
<td><p><span data-ttu-id="1a500-254">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-255">アプリケーション共有の SIP リッスン要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-256">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-257">Lync Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="1a500-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="1a500-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="1a500-259">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-260">アプリケーション共有で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="1a500-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-261">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-262">Lync Server 会議アナウンスサービス</span><span class="sxs-lookup"><span data-stu-id="1a500-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="1a500-263">5073</span><span class="sxs-lookup"><span data-stu-id="1a500-263">5073</span></span></p></td>
<td><p><span data-ttu-id="1a500-264">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-265">Lync Server 会議アナウンスサービス (ダイヤルイン会議) の SIP 要求を受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a500-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-266">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-267">Lync Server コール パーク サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="1a500-268">5075</span><span class="sxs-lookup"><span data-stu-id="1a500-268">5075</span></span></p></td>
<td><p><span data-ttu-id="1a500-269">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-270">コール パーク アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-271">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-272">Lync Server Audio Test service</span><span class="sxs-lookup"><span data-stu-id="1a500-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="1a500-273">5076</span><span class="sxs-lookup"><span data-stu-id="1a500-273">5076</span></span></p></td>
<td><p><span data-ttu-id="1a500-274">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-275">オーディオ テスト サービスの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-276">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-277">該当なし</span><span class="sxs-lookup"><span data-stu-id="1a500-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="1a500-278">5066</span><span class="sxs-lookup"><span data-stu-id="1a500-278">5066</span></span></p></td>
<td><p><span data-ttu-id="1a500-279">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-280">発信 Enhanced 9-1-1 (E9-1-1) ゲートウェイで使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-281">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-282">Lync Server 応答グループ サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="1a500-283">5071</span><span class="sxs-lookup"><span data-stu-id="1a500-283">5071</span></span></p></td>
<td><p><span data-ttu-id="1a500-284">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-285">応答グループ アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-286">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-287">Lync Server 応答グループ サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="1a500-288">8404</span><span class="sxs-lookup"><span data-stu-id="1a500-288">8404</span></span></p></td>
<td><p><span data-ttu-id="1a500-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="1a500-290">応答グループ アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-291">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-292">Lync Server 帯域幅ポリシーサービス</span><span class="sxs-lookup"><span data-stu-id="1a500-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="1a500-293">5080</span><span class="sxs-lookup"><span data-stu-id="1a500-293">5080</span></span></p></td>
<td><p><span data-ttu-id="1a500-294">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-295">音声ビデオ エッジ TURN トラフィックの帯域幅ポリシー サービスによる通話受付管理で使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-296">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-297">Lync Server 帯域幅ポリシーサービス</span><span class="sxs-lookup"><span data-stu-id="1a500-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="1a500-298">448</span><span class="sxs-lookup"><span data-stu-id="1a500-298">448</span></span></p></td>
<td><p><span data-ttu-id="1a500-299">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-300">Lync Server 帯域幅ポリシーサービスによる通話受付管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a500-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-301">中央管理ストアが存在するフロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="1a500-302">Lync Server マスター レプリケーター エージェント サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="1a500-303">445</span><span class="sxs-lookup"><span data-stu-id="1a500-303">445</span></span></p></td>
<td><p><span data-ttu-id="1a500-304">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-305">中央管理ストアから Lync Server を実行しているサーバーに構成データをプッシュするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a500-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-306">すべてのサーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-307">SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="1a500-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="1a500-308">1434</span><span class="sxs-lookup"><span data-stu-id="1a500-308">1434</span></span></p></td>
<td><p><span data-ttu-id="1a500-309">受信</span><span class="sxs-lookup"><span data-stu-id="1a500-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="1a500-310">ローカルの SQL Server インスタンスの中央管理ストアデータのローカルにレプリケートされたコピーのための SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="1a500-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-311">すべての内部サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-312">各種</span><span class="sxs-lookup"><span data-stu-id="1a500-312">Various</span></span></p></td>
<td><p><span data-ttu-id="1a500-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="1a500-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="1a500-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="1a500-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="1a500-315">すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="1a500-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="1a500-316">オーディオを終了するすべてのサーバーで使用します。フロントエンドサーバー (Lync Server 会議アテンダントサービス、lync Server 会議アナウンスサービス、および Lync Server 音声ビデオ会議サービスの場合)、および仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="1a500-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-317">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1a500-318">443</span><span class="sxs-lookup"><span data-stu-id="1a500-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1a500-319">Lync Server 2013 が Office Web Apps サーバーに接続するために使用します。</span><span class="sxs-lookup"><span data-stu-id="1a500-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-320">レ</span><span class="sxs-lookup"><span data-stu-id="1a500-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="1a500-321">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="1a500-322">5060</span><span class="sxs-lookup"><span data-stu-id="1a500-322">5060</span></span></p></td>
<td><p><span data-ttu-id="1a500-323">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-324">リモート通話コントロール サーバーなど、信頼されたサービスへの静的ルートの場合にオプションで使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-325">レ</span><span class="sxs-lookup"><span data-stu-id="1a500-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="1a500-326">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="1a500-327">444</span><span class="sxs-lookup"><span data-stu-id="1a500-327">444</span></span></p></td>
<td><p><span data-ttu-id="1a500-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1a500-328">HTTPS</span></span></p>
<p><span data-ttu-id="1a500-329">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-330">フロントエンドとディレクターの間のサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="1a500-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="1a500-331">さらに、クライアント証明書を (フロントエンドサーバーに) 公開するか、クライアント証明書が既に公開されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a500-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-332">レ</span><span class="sxs-lookup"><span data-stu-id="1a500-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="1a500-333">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="1a500-334">80</span><span class="sxs-lookup"><span data-stu-id="1a500-334">80</span></span></p></td>
<td><p><span data-ttu-id="1a500-335">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-p105">ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への初期通信に使用。通常の動作では HTTPS トラフィックに切り替わり、ポート 443 およびプロトコル TCP を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a500-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-338">レ</span><span class="sxs-lookup"><span data-stu-id="1a500-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="1a500-339">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="1a500-340">443</span><span class="sxs-lookup"><span data-stu-id="1a500-340">443</span></span></p></td>
<td><p><span data-ttu-id="1a500-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1a500-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="1a500-342">ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-343">レ</span><span class="sxs-lookup"><span data-stu-id="1a500-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="1a500-344">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="1a500-345">5061</span><span class="sxs-lookup"><span data-stu-id="1a500-345">5061</span></span></p></td>
<td><p><span data-ttu-id="1a500-346">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-347">サーバー間の内部通信とクライアント接続に使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-348">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-349">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="1a500-350">5070</span><span class="sxs-lookup"><span data-stu-id="1a500-350">5070</span></span></p></td>
<td><p><span data-ttu-id="1a500-351">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-352">フロント エンド サーバーからの要求を受信するために仲介サーバーで使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-353">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-354">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="1a500-355">5067</span><span class="sxs-lookup"><span data-stu-id="1a500-355">5067</span></span></p></td>
<td><p><span data-ttu-id="1a500-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="1a500-357">PSTN ゲートウェイからの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-358">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-359">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="1a500-360">5068</span><span class="sxs-lookup"><span data-stu-id="1a500-360">5068</span></span></p></td>
<td><p><span data-ttu-id="1a500-361">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-362">PSTN ゲートウェイからの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-363">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="1a500-364">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="1a500-365">5070</span><span class="sxs-lookup"><span data-stu-id="1a500-365">5070</span></span></p></td>
<td><p><span data-ttu-id="1a500-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="1a500-367">フロント エンド サーバーからの SIP 要求で使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-368">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="1a500-369">常設チャット SIP</span><span class="sxs-lookup"><span data-stu-id="1a500-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="1a500-370">5041</span><span class="sxs-lookup"><span data-stu-id="1a500-370">5041</span></span></p></td>
<td><p><span data-ttu-id="1a500-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-372">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="1a500-373">常設チャット Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="1a500-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="1a500-374">881</span><span class="sxs-lookup"><span data-stu-id="1a500-374">881</span></span></p></td>
<td><p><span data-ttu-id="1a500-375">TCP (TLS) と TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-376">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1a500-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="1a500-377">常設チャットのファイル転送サービス</span><span class="sxs-lookup"><span data-stu-id="1a500-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="1a500-378">443</span><span class="sxs-lookup"><span data-stu-id="1a500-378">443</span></span></p></td>
<td><p><span data-ttu-id="1a500-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="1a500-380">リモート通話コントロールのシナリオによっては、フロントエンドサーバーまたはディレクターと PBX との間に TCP 接続が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a500-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="1a500-381">Lync Server は TCP ポート5060を使用しなくなりましたが、リモート通話コントロールの展開時には、RCC Line サーバーの FQDN を、フロントエンドサーバーまたはディレクターが PBX システムに接続するために使用する TCP ポートに関連付ける信頼できるサーバー構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="1a500-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="1a500-382">詳細については、「Lync Server Management Shell」のドキュメントの「 <STRONG>CsTrustedApplicationComputer</STRONG> コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a500-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="1a500-383">次の表に、(DNS 負荷分散ではない) ハードウェア負荷分散のみを使用するプールでハードウェア ロード バランサーを開くために必要なポートを示します。</span><span class="sxs-lookup"><span data-stu-id="1a500-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="1a500-384">ハードウェア負荷分散のみを使用する場合のハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a500-385">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-385">Load Balancer</span></span></th>
<th><span data-ttu-id="1a500-386">ポート</span><span class="sxs-lookup"><span data-stu-id="1a500-386">Port</span></span></th>
<th><span data-ttu-id="1a500-387">プロトコル</span><span class="sxs-lookup"><span data-stu-id="1a500-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a500-388">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-389">5061</span><span class="sxs-lookup"><span data-stu-id="1a500-389">5061</span></span></p></td>
<td><p><span data-ttu-id="1a500-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-391">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-392">444</span><span class="sxs-lookup"><span data-stu-id="1a500-392">444</span></span></p></td>
<td><p><span data-ttu-id="1a500-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1a500-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-394">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-395">135</span><span class="sxs-lookup"><span data-stu-id="1a500-395">135</span></span></p></td>
<td><p><span data-ttu-id="1a500-396">DCOM およびリモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="1a500-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-397">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-398">80</span><span class="sxs-lookup"><span data-stu-id="1a500-398">80</span></span></p></td>
<td><p><span data-ttu-id="1a500-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="1a500-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-400">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-401">8080</span><span class="sxs-lookup"><span data-stu-id="1a500-401">8080</span></span></p></td>
<td><p><span data-ttu-id="1a500-402">TCP - フロント エンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</span><span class="sxs-lookup"><span data-stu-id="1a500-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-403">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-404">443</span><span class="sxs-lookup"><span data-stu-id="1a500-404">443</span></span></p></td>
<td><p><span data-ttu-id="1a500-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1a500-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-406">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-407">4443</span><span class="sxs-lookup"><span data-stu-id="1a500-407">4443</span></span></p></td>
<td><p><span data-ttu-id="1a500-408">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="1a500-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-409">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-410">5072</span><span class="sxs-lookup"><span data-stu-id="1a500-410">5072</span></span></p></td>
<td><p><span data-ttu-id="1a500-411">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-412">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-413">5073</span><span class="sxs-lookup"><span data-stu-id="1a500-413">5073</span></span></p></td>
<td><p><span data-ttu-id="1a500-414">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-415">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-416">5075</span><span class="sxs-lookup"><span data-stu-id="1a500-416">5075</span></span></p></td>
<td><p><span data-ttu-id="1a500-417">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-418">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-419">5076</span><span class="sxs-lookup"><span data-stu-id="1a500-419">5076</span></span></p></td>
<td><p><span data-ttu-id="1a500-420">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-421">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-422">5071</span><span class="sxs-lookup"><span data-stu-id="1a500-422">5071</span></span></p></td>
<td><p><span data-ttu-id="1a500-423">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-424">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-425">5080</span><span class="sxs-lookup"><span data-stu-id="1a500-425">5080</span></span></p></td>
<td><p><span data-ttu-id="1a500-426">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-427">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-428">448</span><span class="sxs-lookup"><span data-stu-id="1a500-428">448</span></span></p></td>
<td><p><span data-ttu-id="1a500-429">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-430">仲介サーバーのロードバランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-431">5070</span><span class="sxs-lookup"><span data-stu-id="1a500-431">5070</span></span></p></td>
<td><p><span data-ttu-id="1a500-432">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-433">フロントエンドサーバーのロードバランサー (プールが仲介サーバーも実行している場合)</span><span class="sxs-lookup"><span data-stu-id="1a500-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="1a500-434">5070</span><span class="sxs-lookup"><span data-stu-id="1a500-434">5070</span></span></p></td>
<td><p><span data-ttu-id="1a500-435">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-436">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-437">443</span><span class="sxs-lookup"><span data-stu-id="1a500-437">443</span></span></p></td>
<td><p><span data-ttu-id="1a500-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1a500-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-439">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-440">444</span><span class="sxs-lookup"><span data-stu-id="1a500-440">444</span></span></p></td>
<td><p><span data-ttu-id="1a500-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1a500-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-442">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-443">5061</span><span class="sxs-lookup"><span data-stu-id="1a500-443">5061</span></span></p></td>
<td><p><span data-ttu-id="1a500-444">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-445">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-446">4443</span><span class="sxs-lookup"><span data-stu-id="1a500-446">4443</span></span></p></td>
<td><p><span data-ttu-id="1a500-447">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="1a500-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1a500-p107">DNS 負荷分散を使用するフロント エンド プールとディレクター プールでも、ハードウェア ロード バランサーを展開しておく必要があります。 次の表に、これらのハードウェア ロード バランサーで開く必要があるポートを示します。</span><span class="sxs-lookup"><span data-stu-id="1a500-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="1a500-450">DNS 負荷分散を使用する場合のハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a500-451">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-451">Load Balancer</span></span></th>
<th><span data-ttu-id="1a500-452">ポート</span><span class="sxs-lookup"><span data-stu-id="1a500-452">Port</span></span></th>
<th><span data-ttu-id="1a500-453">プロトコル</span><span class="sxs-lookup"><span data-stu-id="1a500-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a500-454">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-455">80</span><span class="sxs-lookup"><span data-stu-id="1a500-455">80</span></span></p></td>
<td><p><span data-ttu-id="1a500-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="1a500-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-457">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-458">443</span><span class="sxs-lookup"><span data-stu-id="1a500-458">443</span></span></p></td>
<td><p><span data-ttu-id="1a500-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1a500-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-460">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-461">8080</span><span class="sxs-lookup"><span data-stu-id="1a500-461">8080</span></span></p></td>
<td><p><span data-ttu-id="1a500-462">TCP - フロント エンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</span><span class="sxs-lookup"><span data-stu-id="1a500-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-463">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-464">4443</span><span class="sxs-lookup"><span data-stu-id="1a500-464">4443</span></span></p></td>
<td><p><span data-ttu-id="1a500-465">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="1a500-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-466">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-467">443</span><span class="sxs-lookup"><span data-stu-id="1a500-467">443</span></span></p></td>
<td><p><span data-ttu-id="1a500-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1a500-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-469">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="1a500-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="1a500-470">4443</span><span class="sxs-lookup"><span data-stu-id="1a500-470">4443</span></span></p></td>
<td><p><span data-ttu-id="1a500-471">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="1a500-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="1a500-472">必要なクライアント ポート</span><span class="sxs-lookup"><span data-stu-id="1a500-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a500-473">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1a500-473">Component</span></span></th>
<th><span data-ttu-id="1a500-474">ポート</span><span class="sxs-lookup"><span data-stu-id="1a500-474">Port</span></span></th>
<th><span data-ttu-id="1a500-475">プロトコル</span><span class="sxs-lookup"><span data-stu-id="1a500-475">Protocol</span></span></th>
<th><span data-ttu-id="1a500-476">Notes</span><span class="sxs-lookup"><span data-stu-id="1a500-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a500-477">クライアント</span><span class="sxs-lookup"><span data-stu-id="1a500-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="1a500-478">67/68</span><span class="sxs-lookup"><span data-stu-id="1a500-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="1a500-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="1a500-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-480">Lync Server によって、レジストラーの FQDN を検索するために使用されます (つまり、DNS SRV に障害が発生し、手動設定が構成されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="1a500-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-481">クライアント</span><span class="sxs-lookup"><span data-stu-id="1a500-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="1a500-482">443</span><span class="sxs-lookup"><span data-stu-id="1a500-482">443</span></span></p></td>
<td><p><span data-ttu-id="1a500-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="1a500-484">外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-485">クライアント</span><span class="sxs-lookup"><span data-stu-id="1a500-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="1a500-486">443</span><span class="sxs-lookup"><span data-stu-id="1a500-486">443</span></span></p></td>
<td><p><span data-ttu-id="1a500-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="1a500-488">Web 会議セッションへの外部ユーザー アクセスで使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-489">クライアント</span><span class="sxs-lookup"><span data-stu-id="1a500-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="1a500-490">443</span><span class="sxs-lookup"><span data-stu-id="1a500-490">443</span></span></p></td>
<td><p><span data-ttu-id="1a500-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="1a500-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="1a500-492">音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用</span><span class="sxs-lookup"><span data-stu-id="1a500-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-493">クライアント</span><span class="sxs-lookup"><span data-stu-id="1a500-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="1a500-494">3478</span><span class="sxs-lookup"><span data-stu-id="1a500-494">3478</span></span></p></td>
<td><p><span data-ttu-id="1a500-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="1a500-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="1a500-496">音声ビデオセッションおよびメディアへの外部ユーザーアクセスに使用されます (UDP)</span><span class="sxs-lookup"><span data-stu-id="1a500-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-497">クライアント</span><span class="sxs-lookup"><span data-stu-id="1a500-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="1a500-498">5061</span><span class="sxs-lookup"><span data-stu-id="1a500-498">5061</span></span></p></td>
<td><p><span data-ttu-id="1a500-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="1a500-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="1a500-500">外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</span><span class="sxs-lookup"><span data-stu-id="1a500-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-501">クライアント</span><span class="sxs-lookup"><span data-stu-id="1a500-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="1a500-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="1a500-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="1a500-503">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-504">Lync クライアントと以前のクライアントの間のファイル転送に使用されます (Microsoft Office Communications Server 2007 R2、Microsoft Office Communications Server 2007、および Live Communications Server 2005)。</span><span class="sxs-lookup"><span data-stu-id="1a500-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-505">クライアント</span><span class="sxs-lookup"><span data-stu-id="1a500-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="1a500-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="1a500-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="1a500-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="1a500-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="1a500-508">オーディオ ポート範囲 (少なくとも 20 個のポートが必要)</span><span class="sxs-lookup"><span data-stu-id="1a500-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-509">クライアント</span><span class="sxs-lookup"><span data-stu-id="1a500-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="1a500-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="1a500-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="1a500-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="1a500-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="1a500-512">ビデオ ポート範囲 (少なくとも 20 個のポートが必要)</span><span class="sxs-lookup"><span data-stu-id="1a500-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-513">クライアント</span><span class="sxs-lookup"><span data-stu-id="1a500-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="1a500-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="1a500-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="1a500-515">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-516">ピアツーピア ファイル転送 (会議ファイル転送の場合、クライアントは PSOM を使用)。</span><span class="sxs-lookup"><span data-stu-id="1a500-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a500-517">クライアント</span><span class="sxs-lookup"><span data-stu-id="1a500-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="1a500-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="1a500-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="1a500-519">TCP</span><span class="sxs-lookup"><span data-stu-id="1a500-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-520">アプリケーション共有。</span><span class="sxs-lookup"><span data-stu-id="1a500-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a500-521">Aastra 6721ip 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="1a500-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="1a500-522">Aastra 6725ip 卓上電話</span><span class="sxs-lookup"><span data-stu-id="1a500-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="1a500-523">HP 4110 IP 電話 (共通領域電話)</span><span class="sxs-lookup"><span data-stu-id="1a500-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="1a500-524">HP 4120 IP 電話 (卓上電話)</span><span class="sxs-lookup"><span data-stu-id="1a500-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="1a500-525">Polycom CX500 IP 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="1a500-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="1a500-526">Polycom CX600 IP 卓上電話</span><span class="sxs-lookup"><span data-stu-id="1a500-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="1a500-527">Polycom CX700 IP 卓上電話</span><span class="sxs-lookup"><span data-stu-id="1a500-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="1a500-528">Polycom CX3000 IP 会議電話</span><span class="sxs-lookup"><span data-stu-id="1a500-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="1a500-529">67/68</span><span class="sxs-lookup"><span data-stu-id="1a500-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="1a500-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="1a500-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="1a500-531">Lync Server 証明書、プロビジョニング FQDN、レジストラー FQDN を検索するために、リストされているデバイスによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a500-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1a500-532">**\*** これらのメディアの種類に対して特定のポートを構成するには、Get-csconferencingconfiguration コマンドレット (ClientMediaPortRangeEnabled、ClientMediaPort、および ClientMediaPortRange パラメーター) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a500-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a500-533">Lync クライアント用のプログラムを設定すると、クライアントコンピューターに必要なオペレーティングシステムファイアウォールの例外が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="1a500-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1a500-534">外部ユーザー アクセス用に使用されるポートは、クライアントが組織のファイアウォールを通過する必要のあるすべてのシナリオにおいて必要です (たとえば、他の組織によってホストされる外部の通信や会議)。</span><span class="sxs-lookup"><span data-stu-id="1a500-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

