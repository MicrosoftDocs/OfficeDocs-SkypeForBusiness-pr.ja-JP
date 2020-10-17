---
title: 'Lync Server 2013: 内部サーバーのポートとプロトコル'
description: 'Lync Server 2013: 内部サーバーのポートとプロトコル。'
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
ms.openlocfilehash: d7d8f12c78c5dec5caacaeb1156f4d228b7cd591
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566360"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="bb5b2-103">Lync Server 2013 の内部サーバーのポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="bb5b2-103">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb5b2-104">_**トピックの最終更新日:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="bb5b2-104">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="bb5b2-105">このセクションでは、Lync Server 展開のサーバー、ロードバランサー、およびクライアントで使用されるポートとプロトコルの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-105">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bb5b2-106">1対1の通信に関係する Lync および Communicator クライアントは、ピアツーピアと呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-106">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="bb5b2-107">技術的には、2つのクライアントは1つの会話に、インスタントメッセージング multipoint control unit (IMMCU) を中央に持つ1つの会話と通信します。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-107">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="bb5b2-108">IMMCU はフロントエンドサーバーのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-108">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="bb5b2-109">必要な通信ワークフローに IMMCU を配置すると、フロントエンドサーバーが有効になっている通話詳細記録およびその他の機能を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-109">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="bb5b2-110">クライアント上の動的送信元ポートからフロントエンドサーバーポート TLS/TCP/5061 への通信です (推奨トランスポート層セキュリティを使用していることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-110">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="bb5b2-111">設計上、Lync Server と IMMCU がアクティブで利用可能な場合にのみ、ピアツーピア通信 (およびマルチパーティ IM) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-111">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="bb5b2-112">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="bb5b2-112">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bb5b2-113">Lync server がファイアウォールで必要なポートを開くときに、サーバー上で Lync Server サービスを開始する前に、Windows ファイアウォールを実行しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-113">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="bb5b2-114">エッジコンポーネントのファイアウォール構成の詳細については、「 [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-114">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="bb5b2-115">次の表に、各内部サーバー役割で開く必要のあるポートの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-115">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="bb5b2-116">必要なサーバー ポート (サーバー役割別)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-116">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="bb5b2-117">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="bb5b2-117">Server role</span></span></th>
<th><span data-ttu-id="bb5b2-118">サービス名</span><span class="sxs-lookup"><span data-stu-id="bb5b2-118">Service name</span></span></th>
<th><span data-ttu-id="bb5b2-119">ポート</span><span class="sxs-lookup"><span data-stu-id="bb5b2-119">Port</span></span></th>
<th><span data-ttu-id="bb5b2-120">プロトコル</span><span class="sxs-lookup"><span data-stu-id="bb5b2-120">Protocol</span></span></th>
<th><span data-ttu-id="bb5b2-121">Notes</span><span class="sxs-lookup"><span data-stu-id="bb5b2-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-122">すべてのサーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-122">All Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-123">SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-123">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-124">1434</span><span class="sxs-lookup"><span data-stu-id="bb5b2-124">1434</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-125">受信</span><span class="sxs-lookup"><span data-stu-id="bb5b2-125">UDP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-126">中央管理ストアデータベースのローカルにレプリケートされたコピーの SQL ブラウザー。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-126">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-127">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-127">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-128">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-128">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-129">5060</span><span class="sxs-lookup"><span data-stu-id="bb5b2-129">5060</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-130">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-130">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-131">リモート通話コントロール サーバーなどの Standard Edition サーバーとフロント エンド サーバーで、信頼されたサービスへの静的ルートの場合にオプションとして使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-131">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-132">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-132">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-133">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-133">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-134">5061</span><span class="sxs-lookup"><span data-stu-id="bb5b2-134">5061</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-135">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-135">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-p102">サーバー間のすべての内部 SIP 通信 (MTLS)、サーバーとクライアントの間の SIP 通信 (TLS)、およびフロント エンド サーバーと仲介サーバーの間の SIP 通信 (MTLS) において、Standard Edition サーバーとフロント エンド プールで使用。 監視サーバーとの通信でも使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-138">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-138">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-139">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-139">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-140">444</span><span class="sxs-lookup"><span data-stu-id="bb5b2-140">444</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-141">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bb5b2-141">HTTPS</span></span></p>
<p><span data-ttu-id="bb5b2-142">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-142">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-143">フォーカス (会議の状態を管理する Lync Server コンポーネント) と個々のサーバーとの間の HTTPS 通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-143">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="bb5b2-144">このポートは、存続可能ブランチアプライアンスとフロントエンドサーバー間の TCP 通信にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-144">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-145">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-145">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-146">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-146">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-147">135</span><span class="sxs-lookup"><span data-stu-id="bb5b2-147">135</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-148">DCOM およびリモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-148">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-149">ユーザーの移行、ユーザー レプリケーター同期、およびアドレス帳同期などの DCOM ベースの操作で使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-149">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-150">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-150">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-151">Lync Server IM 会議サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-151">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-152">5062</span><span class="sxs-lookup"><span data-stu-id="bb5b2-152">5062</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-153">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-153">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-154">インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-154">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-155">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-155">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-156">Lync Server Web 会議サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-156">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-157">8057</span><span class="sxs-lookup"><span data-stu-id="bb5b2-157">8057</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-158">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-158">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-159">クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-159">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-160">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-160">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-161">Lync Server Web 会議互換性サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-161">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-162">8058</span><span class="sxs-lookup"><span data-stu-id="bb5b2-162">8058</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-163">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-163">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-164">Live Meeting クライアントおよび以前のバージョンの Lync Server からの、永続的な共有オブジェクトモデル (PSOM) 接続をリッスンするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-164">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-165">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-165">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-166">Lync Server 音声ビデオ会議サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-166">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-167">5063</span><span class="sxs-lookup"><span data-stu-id="bb5b2-167">5063</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-168">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-168">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-169">音声ビデオ会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-169">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-170">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-170">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-171">Lync Server 音声ビデオ会議サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-171">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-172">57501-65535</span><span class="sxs-lookup"><span data-stu-id="bb5b2-172">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-173">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-173">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-174">ビデオ会議で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-174">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-175">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-176">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-176">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-177">80</span><span class="sxs-lookup"><span data-stu-id="bb5b2-177">80</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-178">HTTP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-178">HTTP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-179">HTTPS が使用されない場合の、フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-179">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-180">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-180">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-181">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-181">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-182">443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-182">443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-183">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bb5b2-183">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-184">フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-184">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-185">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-185">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-186">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-186">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-187">8080</span><span class="sxs-lookup"><span data-stu-id="bb5b2-187">8080</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-188">TCP および HTTP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-188">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-189">外部アクセスのために web コンポーネントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-189">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-190">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-190">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-191">Web サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-191">Web server component</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-192">4443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-192">4443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-193">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bb5b2-193">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-194">自動検出サインインの HTTPS (リバースプロキシから) および HTTPS フロントエンドプール間通信。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-194">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-195">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-195">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-196">Web サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-196">Web server component</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-197">8060</span><span class="sxs-lookup"><span data-stu-id="bb5b2-197">8060</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-198">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-198">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-199">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-199">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-200">Web サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-200">Web server component</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-201">8061</span><span class="sxs-lookup"><span data-stu-id="bb5b2-201">8061</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-202">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-202">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-203">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-203">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-204">Mobility Services コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-204">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-205">5086</span><span class="sxs-lookup"><span data-stu-id="bb5b2-205">5086</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-206">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-206">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-207">Mobility Services 内部プロセスで使用される SIP ポート</span><span class="sxs-lookup"><span data-stu-id="bb5b2-207">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-208">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-208">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-209">Mobility Services コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-209">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-210">5087</span><span class="sxs-lookup"><span data-stu-id="bb5b2-210">5087</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-211">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-211">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-212">Mobility Services 内部プロセスで使用される SIP ポート</span><span class="sxs-lookup"><span data-stu-id="bb5b2-212">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-213">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-213">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-214">Mobility Services コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-214">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-215">443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-215">443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-216">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bb5b2-216">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-217">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-217">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-218">Lync Server 会議アテンダントサービス (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-218">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-219">5064</span><span class="sxs-lookup"><span data-stu-id="bb5b2-219">5064</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-220">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-220">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-221">ダイヤルイン会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-221">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-222">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-222">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-223">Lync Server 会議アテンダントサービス (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-223">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-224">5072</span><span class="sxs-lookup"><span data-stu-id="bb5b2-224">5072</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-225">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-225">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-226">アテンダント (ダイヤルイン会議) の SIP 要求を受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-226">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-227">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-227">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-228">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-228">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-229">5070</span><span class="sxs-lookup"><span data-stu-id="bb5b2-229">5070</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-230">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-230">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-231">フロント エンド サーバーから仲介サーバーへの要求を受信するために仲介サーバーで使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-231">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-232">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-232">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-233">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-233">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-234">5067</span><span class="sxs-lookup"><span data-stu-id="bb5b2-234">5067</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-235">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-235">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-236">PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-236">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-237">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-237">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-238">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-238">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-239">5068</span><span class="sxs-lookup"><span data-stu-id="bb5b2-239">5068</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-240">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-240">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-241">PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-241">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-242">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-242">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-243">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-243">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-244">5081</span><span class="sxs-lookup"><span data-stu-id="bb5b2-244">5081</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-245">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-245">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-246">仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-246">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-247">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-247">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-248">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-248">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-249">5082</span><span class="sxs-lookup"><span data-stu-id="bb5b2-249">5082</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-250">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-250">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-251">仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-251">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-252">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-252">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-253">Lync Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-253">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-254">5065</span><span class="sxs-lookup"><span data-stu-id="bb5b2-254">5065</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-255">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-255">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-256">アプリケーション共有の SIP リッスン要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-256">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-257">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-257">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-258">Lync Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-258">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-259">49152-65535</span><span class="sxs-lookup"><span data-stu-id="bb5b2-259">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-260">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-260">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-261">アプリケーション共有で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-261">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-262">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-262">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-263">Lync Server 会議アナウンスサービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-263">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-264">5073</span><span class="sxs-lookup"><span data-stu-id="bb5b2-264">5073</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-265">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-265">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-266">Lync Server 会議アナウンスサービス (ダイヤルイン会議) の SIP 要求を受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-266">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-267">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-267">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-268">Lync Server コール パーク サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-268">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-269">5075</span><span class="sxs-lookup"><span data-stu-id="bb5b2-269">5075</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-270">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-270">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-271">コール パーク アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-271">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-272">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-272">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-273">Lync Server Audio Test service</span><span class="sxs-lookup"><span data-stu-id="bb5b2-273">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-274">5076</span><span class="sxs-lookup"><span data-stu-id="bb5b2-274">5076</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-275">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-275">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-276">オーディオ テスト サービスの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-276">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-277">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-277">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-278">該当なし</span><span class="sxs-lookup"><span data-stu-id="bb5b2-278">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-279">5066</span><span class="sxs-lookup"><span data-stu-id="bb5b2-279">5066</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-280">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-280">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-281">発信 Enhanced 9-1-1 (E9-1-1) ゲートウェイで使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-281">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-282">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-282">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-283">Lync Server 応答グループ サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-283">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-284">5071</span><span class="sxs-lookup"><span data-stu-id="bb5b2-284">5071</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-285">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-285">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-286">応答グループ アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-286">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-287">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-287">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-288">Lync Server 応答グループ サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-288">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-289">8404</span><span class="sxs-lookup"><span data-stu-id="bb5b2-289">8404</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-290">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-290">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-291">応答グループ アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-291">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-292">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-292">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-293">Lync Server 帯域幅ポリシーサービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-293">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-294">5080</span><span class="sxs-lookup"><span data-stu-id="bb5b2-294">5080</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-295">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-295">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-296">音声ビデオ エッジ TURN トラフィックの帯域幅ポリシー サービスによる通話受付管理で使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-296">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-297">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-297">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-298">Lync Server 帯域幅ポリシーサービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-298">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-299">448</span><span class="sxs-lookup"><span data-stu-id="bb5b2-299">448</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-300">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-300">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-301">Lync Server 帯域幅ポリシーサービスによる通話受付管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-301">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-302">中央管理ストアが存在するフロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-302">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-303">Lync Server マスター レプリケーター エージェント サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-303">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-304">445</span><span class="sxs-lookup"><span data-stu-id="bb5b2-304">445</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-305">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-305">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-306">中央管理ストアから Lync Server を実行しているサーバーに構成データをプッシュするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-306">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-307">すべてのサーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-307">All Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-308">SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-308">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-309">1434</span><span class="sxs-lookup"><span data-stu-id="bb5b2-309">1434</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-310">受信</span><span class="sxs-lookup"><span data-stu-id="bb5b2-310">UDP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-311">ローカルの SQL Server インスタンスの中央管理ストアデータのローカルにレプリケートされたコピーのための SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-311">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-312">すべての内部サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-312">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-313">各種</span><span class="sxs-lookup"><span data-stu-id="bb5b2-313">Various</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-314">49152-57500</span><span class="sxs-lookup"><span data-stu-id="bb5b2-314">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-315">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-315">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-316">すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-316">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="bb5b2-317">オーディオを終了するすべてのサーバーで使用します。フロントエンドサーバー (Lync Server 会議アテンダントサービス、lync Server 会議アナウンスサービス、および Lync Server 音声ビデオ会議サービスの場合)、および仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-317">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-318">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-318">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb5b2-319">443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-319">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb5b2-320">Lync Server 2013 が Office Web Apps サーバーに接続するために使用します。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-320">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-321">レ</span><span class="sxs-lookup"><span data-stu-id="bb5b2-321">Directors</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-322">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-322">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-323">5060</span><span class="sxs-lookup"><span data-stu-id="bb5b2-323">5060</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-324">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-324">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-325">リモート通話コントロール サーバーなど、信頼されたサービスへの静的ルートの場合にオプションで使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-325">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-326">レ</span><span class="sxs-lookup"><span data-stu-id="bb5b2-326">Directors</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-327">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-327">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-328">444</span><span class="sxs-lookup"><span data-stu-id="bb5b2-328">444</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-329">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bb5b2-329">HTTPS</span></span></p>
<p><span data-ttu-id="bb5b2-330">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-330">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-331">フロントエンドとディレクターの間のサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-331">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="bb5b2-332">さらに、クライアント証明書を (フロントエンドサーバーに) 公開するか、クライアント証明書が既に公開されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-332">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-333">レ</span><span class="sxs-lookup"><span data-stu-id="bb5b2-333">Directors</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-334">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-334">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-335">80</span><span class="sxs-lookup"><span data-stu-id="bb5b2-335">80</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-336">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-336">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-p105">ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への初期通信に使用。通常の動作では HTTPS トラフィックに切り替わり、ポート 443 およびプロトコル TCP を使用します。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-339">レ</span><span class="sxs-lookup"><span data-stu-id="bb5b2-339">Directors</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-340">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-340">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-341">443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-341">443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-342">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bb5b2-342">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-343">ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-343">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-344">レ</span><span class="sxs-lookup"><span data-stu-id="bb5b2-344">Directors</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-345">Lync Server Front-End サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-345">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-346">5061</span><span class="sxs-lookup"><span data-stu-id="bb5b2-346">5061</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-347">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-347">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-348">サーバー間の内部通信とクライアント接続に使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-348">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-349">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-349">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-350">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-350">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-351">5070</span><span class="sxs-lookup"><span data-stu-id="bb5b2-351">5070</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-352">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-352">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-353">フロント エンド サーバーからの要求を受信するために仲介サーバーで使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-353">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-354">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-354">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-355">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-355">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-356">5067</span><span class="sxs-lookup"><span data-stu-id="bb5b2-356">5067</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-357">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-357">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-358">PSTN ゲートウェイからの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-358">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-359">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-359">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-360">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-360">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-361">5068</span><span class="sxs-lookup"><span data-stu-id="bb5b2-361">5068</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-362">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-362">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-363">PSTN ゲートウェイからの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-363">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-364">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-364">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-365">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-365">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-366">5070</span><span class="sxs-lookup"><span data-stu-id="bb5b2-366">5070</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-367">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-367">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-368">フロント エンド サーバーからの SIP 要求で使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-368">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-369">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-369">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-370">常設チャット SIP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-370">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-371">5041</span><span class="sxs-lookup"><span data-stu-id="bb5b2-371">5041</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-372">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-372">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-373">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-373">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-374">常設チャット Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-374">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-375">881</span><span class="sxs-lookup"><span data-stu-id="bb5b2-375">881</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-376">TCP (TLS) と TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-376">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-377">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-377">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-378">常設チャットのファイル転送サービス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-378">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-379">443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-379">443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-380">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-380">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="bb5b2-381">リモート通話コントロールのシナリオによっては、フロントエンドサーバーまたはディレクターと PBX との間に TCP 接続が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-381">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="bb5b2-382">Lync Server は TCP ポート5060を使用しなくなりましたが、リモート通話コントロールの展開時には、RCC Line サーバーの FQDN を、フロントエンドサーバーまたはディレクターが PBX システムに接続するために使用する TCP ポートに関連付ける信頼できるサーバー構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-382">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="bb5b2-383">詳細については、「Lync Server Management Shell」のドキュメントの「 <STRONG>CsTrustedApplicationComputer</STRONG> コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-383">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="bb5b2-384">次の表に、(DNS 負荷分散ではない) ハードウェア負荷分散のみを使用するプールでハードウェア ロード バランサーを開くために必要なポートを示します。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-384">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="bb5b2-385">ハードウェア負荷分散のみを使用する場合のハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-385">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb5b2-386">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-386">Load Balancer</span></span></th>
<th><span data-ttu-id="bb5b2-387">ポート</span><span class="sxs-lookup"><span data-stu-id="bb5b2-387">Port</span></span></th>
<th><span data-ttu-id="bb5b2-388">プロトコル</span><span class="sxs-lookup"><span data-stu-id="bb5b2-388">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-389">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-389">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-390">5061</span><span class="sxs-lookup"><span data-stu-id="bb5b2-390">5061</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-391">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-391">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-392">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-392">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-393">444</span><span class="sxs-lookup"><span data-stu-id="bb5b2-393">444</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-394">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bb5b2-394">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-395">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-395">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-396">135</span><span class="sxs-lookup"><span data-stu-id="bb5b2-396">135</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-397">DCOM およびリモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-397">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-398">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-398">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-399">80</span><span class="sxs-lookup"><span data-stu-id="bb5b2-399">80</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-400">HTTP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-400">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-401">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-401">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-402">8080</span><span class="sxs-lookup"><span data-stu-id="bb5b2-402">8080</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-403">TCP - フロント エンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-403">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-404">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-404">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-405">443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-405">443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-406">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bb5b2-406">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-407">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-407">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-408">4443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-408">4443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-409">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-409">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-410">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-410">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-411">5072</span><span class="sxs-lookup"><span data-stu-id="bb5b2-411">5072</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-412">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-412">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-413">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-413">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-414">5073</span><span class="sxs-lookup"><span data-stu-id="bb5b2-414">5073</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-415">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-415">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-416">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-416">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-417">5075</span><span class="sxs-lookup"><span data-stu-id="bb5b2-417">5075</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-418">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-418">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-419">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-419">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-420">5076</span><span class="sxs-lookup"><span data-stu-id="bb5b2-420">5076</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-421">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-421">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-422">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-422">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-423">5071</span><span class="sxs-lookup"><span data-stu-id="bb5b2-423">5071</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-424">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-424">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-425">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-425">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-426">5080</span><span class="sxs-lookup"><span data-stu-id="bb5b2-426">5080</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-427">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-427">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-428">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-428">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-429">448</span><span class="sxs-lookup"><span data-stu-id="bb5b2-429">448</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-430">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-430">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-431">仲介サーバーのロードバランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-431">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-432">5070</span><span class="sxs-lookup"><span data-stu-id="bb5b2-432">5070</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-433">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-433">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-434">フロントエンドサーバーのロードバランサー (プールが仲介サーバーも実行している場合)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-434">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-435">5070</span><span class="sxs-lookup"><span data-stu-id="bb5b2-435">5070</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-436">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-436">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-437">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-437">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-438">443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-438">443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-439">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bb5b2-439">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-440">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-440">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-441">444</span><span class="sxs-lookup"><span data-stu-id="bb5b2-441">444</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-442">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bb5b2-442">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-443">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-443">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-444">5061</span><span class="sxs-lookup"><span data-stu-id="bb5b2-444">5061</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-445">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-445">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-446">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-446">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-447">4443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-447">4443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-448">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-448">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bb5b2-p107">DNS 負荷分散を使用するフロント エンド プールとディレクター プールでも、ハードウェア ロード バランサーを展開しておく必要があります。 次の表に、これらのハードウェア ロード バランサーで開く必要があるポートを示します。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="bb5b2-451">DNS 負荷分散を使用する場合のハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-451">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb5b2-452">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-452">Load Balancer</span></span></th>
<th><span data-ttu-id="bb5b2-453">ポート</span><span class="sxs-lookup"><span data-stu-id="bb5b2-453">Port</span></span></th>
<th><span data-ttu-id="bb5b2-454">プロトコル</span><span class="sxs-lookup"><span data-stu-id="bb5b2-454">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-455">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-455">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-456">80</span><span class="sxs-lookup"><span data-stu-id="bb5b2-456">80</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-457">HTTP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-457">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-458">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-458">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-459">443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-459">443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-460">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bb5b2-460">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-461">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-461">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-462">8080</span><span class="sxs-lookup"><span data-stu-id="bb5b2-462">8080</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-463">TCP - フロント エンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</span><span class="sxs-lookup"><span data-stu-id="bb5b2-463">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-464">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-464">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-465">4443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-465">4443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-466">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-466">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-467">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-467">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-468">443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-468">443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-469">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bb5b2-469">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-470">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="bb5b2-470">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-471">4443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-471">4443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-472">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-472">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="bb5b2-473">必要なクライアント ポート</span><span class="sxs-lookup"><span data-stu-id="bb5b2-473">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb5b2-474">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-474">Component</span></span></th>
<th><span data-ttu-id="bb5b2-475">ポート</span><span class="sxs-lookup"><span data-stu-id="bb5b2-475">Port</span></span></th>
<th><span data-ttu-id="bb5b2-476">プロトコル</span><span class="sxs-lookup"><span data-stu-id="bb5b2-476">Protocol</span></span></th>
<th><span data-ttu-id="bb5b2-477">Notes</span><span class="sxs-lookup"><span data-stu-id="bb5b2-477">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-478">クライアント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-478">Clients</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-479">67/68</span><span class="sxs-lookup"><span data-stu-id="bb5b2-479">67/68</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-480">DHCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-480">DHCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-481">Lync Server によって、レジストラーの FQDN を検索するために使用されます (つまり、DNS SRV に障害が発生し、手動設定が構成されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-481">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-482">クライアント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-482">Clients</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-483">443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-483">443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-484">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-484">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-485">外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-485">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-486">クライアント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-486">Clients</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-487">443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-487">443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-488">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-488">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-489">Web 会議セッションへの外部ユーザー アクセスで使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-489">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-490">クライアント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-490">Clients</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-491">443</span><span class="sxs-lookup"><span data-stu-id="bb5b2-491">443</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-492">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-492">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-493">音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用</span><span class="sxs-lookup"><span data-stu-id="bb5b2-493">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-494">クライアント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-494">Clients</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-495">3478</span><span class="sxs-lookup"><span data-stu-id="bb5b2-495">3478</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-496">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-496">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-497">音声ビデオセッションおよびメディアへの外部ユーザーアクセスに使用されます (UDP)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-497">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-498">クライアント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-498">Clients</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-499">5061</span><span class="sxs-lookup"><span data-stu-id="bb5b2-499">5061</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-500">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-500">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-501">外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-501">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-502">クライアント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-502">Clients</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-503">6891-6901</span><span class="sxs-lookup"><span data-stu-id="bb5b2-503">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-504">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-504">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-505">Lync クライアントと以前のクライアントの間のファイル転送に使用されます (Microsoft Office Communications Server 2007 R2、Microsoft Office Communications Server 2007、および Live Communications Server 2005)。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-505">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-506">クライアント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-506">Clients</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-507">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="bb5b2-507">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-508">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-508">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-509">オーディオ ポート範囲 (少なくとも 20 個のポートが必要)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-509">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-510">クライアント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-510">Clients</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-511">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="bb5b2-511">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-512">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-512">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-513">ビデオ ポート範囲 (少なくとも 20 個のポートが必要)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-513">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-514">クライアント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-514">Clients</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-515">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="bb5b2-515">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-516">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-516">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-517">ピアツーピア ファイル転送 (会議ファイル転送の場合、クライアントは PSOM を使用)。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-517">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb5b2-518">クライアント</span><span class="sxs-lookup"><span data-stu-id="bb5b2-518">Clients</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-519">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="bb5b2-519">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-520">TCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-520">TCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-521">アプリケーション共有。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-521">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb5b2-522">Aastra 6721ip 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="bb5b2-522">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="bb5b2-523">Aastra 6725ip 卓上電話</span><span class="sxs-lookup"><span data-stu-id="bb5b2-523">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="bb5b2-524">HP 4110 IP 電話 (共通領域電話)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-524">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="bb5b2-525">HP 4120 IP 電話 (卓上電話)</span><span class="sxs-lookup"><span data-stu-id="bb5b2-525">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="bb5b2-526">Polycom CX500 IP 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="bb5b2-526">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="bb5b2-527">Polycom CX600 IP 卓上電話</span><span class="sxs-lookup"><span data-stu-id="bb5b2-527">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="bb5b2-528">Polycom CX700 IP 卓上電話</span><span class="sxs-lookup"><span data-stu-id="bb5b2-528">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="bb5b2-529">Polycom CX3000 IP 会議電話</span><span class="sxs-lookup"><span data-stu-id="bb5b2-529">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-530">67/68</span><span class="sxs-lookup"><span data-stu-id="bb5b2-530">67/68</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-531">DHCP</span><span class="sxs-lookup"><span data-stu-id="bb5b2-531">DHCP</span></span></p></td>
<td><p><span data-ttu-id="bb5b2-532">Lync Server 証明書、プロビジョニング FQDN、レジストラー FQDN を検索するために、リストされているデバイスによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-532">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bb5b2-533">**\*** これらのメディアの種類に対して特定のポートを構成するには、Get-csconferencingconfiguration コマンドレット (ClientMediaPortRangeEnabled、ClientMediaPort、および ClientMediaPortRange パラメーター) を使用します。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-533">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bb5b2-534">Lync クライアント用のプログラムを設定すると、クライアントコンピューターに必要なオペレーティングシステムファイアウォールの例外が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-534">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="bb5b2-535">外部ユーザー アクセス用に使用されるポートは、クライアントが組織のファイアウォールを通過する必要のあるすべてのシナリオにおいて必要です (たとえば、他の組織によってホストされる外部の通信や会議)。</span><span class="sxs-lookup"><span data-stu-id="bb5b2-535">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

