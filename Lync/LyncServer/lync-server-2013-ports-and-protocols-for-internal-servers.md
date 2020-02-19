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
ms.openlocfilehash: 8f730a0af21abfbff8058aa51c1163c1dae1ff3a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="e7db5-102">Lync Server 2013 の内部サーバーのポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="e7db5-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7db5-103">_**トピックの最終更新日:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="e7db5-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="e7db5-104">このセクションでは、Lync Server 展開のサーバー、ロードバランサー、およびクライアントで使用されるポートとプロトコルの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7db5-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7db5-105">1対1の通信に関係する Lync および Communicator クライアントは、ピアツーピアと呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="e7db5-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="e7db5-106">技術的には、2つのクライアントは1つの会話に、インスタントメッセージング multipoint control unit (IMMCU) を中央に持つ1つの会話と通信します。</span><span class="sxs-lookup"><span data-stu-id="e7db5-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="e7db5-107">IMMCU はフロントエンドサーバーのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e7db5-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="e7db5-108">必要な通信ワークフローに IMMCU を配置すると、フロントエンドサーバーが有効になっている通話詳細記録およびその他の機能を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e7db5-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="e7db5-109">クライアント上の動的送信元ポートからフロントエンドサーバーポート TLS/TCP/5061 への通信です (推奨トランスポート層セキュリティを使用していることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="e7db5-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="e7db5-110">設計上、Lync Server と IMMCU がアクティブで利用可能な場合にのみ、ピアツーピア通信 (およびマルチパーティ IM) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e7db5-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="e7db5-111">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="e7db5-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7db5-112">Lync server がファイアウォールで必要なポートを開くときに、サーバー上で Lync Server サービスを開始する前に、Windows ファイアウォールを実行しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7db5-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="e7db5-113">エッジコンポーネントのファイアウォール構成の詳細については、「 [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7db5-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="e7db5-114">次の表に、各内部サーバー役割で開く必要のあるポートの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e7db5-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="e7db5-115">必要なサーバー ポート (サーバー役割別)</span><span class="sxs-lookup"><span data-stu-id="e7db5-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="e7db5-116">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="e7db5-116">Server role</span></span></th>
<th><span data-ttu-id="e7db5-117">サービス名</span><span class="sxs-lookup"><span data-stu-id="e7db5-117">Service name</span></span></th>
<th><span data-ttu-id="e7db5-118">ポート</span><span class="sxs-lookup"><span data-stu-id="e7db5-118">Port</span></span></th>
<th><span data-ttu-id="e7db5-119">プロトコル</span><span class="sxs-lookup"><span data-stu-id="e7db5-119">Protocol</span></span></th>
<th><span data-ttu-id="e7db5-120">メモ</span><span class="sxs-lookup"><span data-stu-id="e7db5-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-121">すべてのサーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-122">SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="e7db5-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="e7db5-123">1434</span><span class="sxs-lookup"><span data-stu-id="e7db5-123">1434</span></span></p></td>
<td><p><span data-ttu-id="e7db5-124">受信</span><span class="sxs-lookup"><span data-stu-id="e7db5-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-125">中央管理ストアデータベースのローカルにレプリケートされたコピーの SQL ブラウザー。</span><span class="sxs-lookup"><span data-stu-id="e7db5-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-126">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-127">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-128">5060</span><span class="sxs-lookup"><span data-stu-id="e7db5-128">5060</span></span></p></td>
<td><p><span data-ttu-id="e7db5-129">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-130">リモート通話コントロール サーバーなどの Standard Edition サーバーとフロント エンド サーバーで、信頼されたサービスへの静的ルートの場合にオプションとして使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-131">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-132">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-133">5061</span><span class="sxs-lookup"><span data-stu-id="e7db5-133">5061</span></span></p></td>
<td><p><span data-ttu-id="e7db5-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-p102">サーバー間のすべての内部 SIP 通信 (MTLS)、サーバーとクライアントの間の SIP 通信 (TLS)、およびフロント エンド サーバーと仲介サーバーの間の SIP 通信 (MTLS) において、Standard Edition サーバーとフロント エンド プールで使用。 監視サーバーとの通信でも使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-137">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-138">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-139">444</span><span class="sxs-lookup"><span data-stu-id="e7db5-139">444</span></span></p></td>
<td><p><span data-ttu-id="e7db5-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e7db5-140">HTTPS</span></span></p>
<p><span data-ttu-id="e7db5-141">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-142">フォーカス (会議の状態を管理する Lync Server コンポーネント) と個々のサーバーとの間の HTTPS 通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7db5-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="e7db5-143">このポートは、存続可能ブランチアプライアンスとフロントエンドサーバー間の TCP 通信にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7db5-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-144">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-145">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-146">135</span><span class="sxs-lookup"><span data-stu-id="e7db5-146">135</span></span></p></td>
<td><p><span data-ttu-id="e7db5-147">DCOM およびリモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="e7db5-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-148">ユーザーの移行、ユーザー レプリケーター同期、およびアドレス帳同期などの DCOM ベースの操作で使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-149">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-150">Lync Server IM 会議サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-151">5062</span><span class="sxs-lookup"><span data-stu-id="e7db5-151">5062</span></span></p></td>
<td><p><span data-ttu-id="e7db5-152">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-153">インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-154">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-155">Lync Server Web 会議サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-156">8057</span><span class="sxs-lookup"><span data-stu-id="e7db5-156">8057</span></span></p></td>
<td><p><span data-ttu-id="e7db5-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-158">クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-159">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-160">Lync Server Web 会議互換性サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-161">8058</span><span class="sxs-lookup"><span data-stu-id="e7db5-161">8058</span></span></p></td>
<td><p><span data-ttu-id="e7db5-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-163">Live Meeting クライアントおよび以前のバージョンの Lync Server からの、永続的な共有オブジェクトモデル (PSOM) 接続をリッスンするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7db5-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-164">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-165">Lync Server 音声ビデオ会議サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-166">5063</span><span class="sxs-lookup"><span data-stu-id="e7db5-166">5063</span></span></p></td>
<td><p><span data-ttu-id="e7db5-167">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-168">音声ビデオ会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-169">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-170">Lync Server 音声ビデオ会議サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="e7db5-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="e7db5-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="e7db5-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-173">ビデオ会議で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="e7db5-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-174">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-175">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-176">80</span><span class="sxs-lookup"><span data-stu-id="e7db5-176">80</span></span></p></td>
<td><p><span data-ttu-id="e7db5-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="e7db5-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-178">HTTPS が使用されない場合の、フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-179">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-180">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-181">443</span><span class="sxs-lookup"><span data-stu-id="e7db5-181">443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e7db5-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="e7db5-183">フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-184">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-185">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-186">8080</span><span class="sxs-lookup"><span data-stu-id="e7db5-186">8080</span></span></p></td>
<td><p><span data-ttu-id="e7db5-187">TCP および HTTP</span><span class="sxs-lookup"><span data-stu-id="e7db5-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-188">外部アクセスのために web コンポーネントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7db5-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-189">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-190">Web サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="e7db5-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="e7db5-191">4443</span><span class="sxs-lookup"><span data-stu-id="e7db5-191">4443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e7db5-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="e7db5-193">自動検出サインインの HTTPS (リバースプロキシから) および HTTPS フロントエンドプール間通信。</span><span class="sxs-lookup"><span data-stu-id="e7db5-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-194">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-195">Web サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="e7db5-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="e7db5-196">8060</span><span class="sxs-lookup"><span data-stu-id="e7db5-196">8060</span></span></p></td>
<td><p><span data-ttu-id="e7db5-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-198">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-199">Web サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="e7db5-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="e7db5-200">8061</span><span class="sxs-lookup"><span data-stu-id="e7db5-200">8061</span></span></p></td>
<td><p><span data-ttu-id="e7db5-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-202">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-203">Mobility Services コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e7db5-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="e7db5-204">5086</span><span class="sxs-lookup"><span data-stu-id="e7db5-204">5086</span></span></p></td>
<td><p><span data-ttu-id="e7db5-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-206">Mobility Services 内部プロセスで使用される SIP ポート</span><span class="sxs-lookup"><span data-stu-id="e7db5-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-207">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-208">Mobility Services コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e7db5-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="e7db5-209">5087</span><span class="sxs-lookup"><span data-stu-id="e7db5-209">5087</span></span></p></td>
<td><p><span data-ttu-id="e7db5-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-211">Mobility Services 内部プロセスで使用される SIP ポート</span><span class="sxs-lookup"><span data-stu-id="e7db5-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-212">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-213">Mobility Services コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e7db5-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="e7db5-214">443</span><span class="sxs-lookup"><span data-stu-id="e7db5-214">443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e7db5-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-216">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-217">Lync Server 会議アテンダントサービス (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="e7db5-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-218">5064</span><span class="sxs-lookup"><span data-stu-id="e7db5-218">5064</span></span></p></td>
<td><p><span data-ttu-id="e7db5-219">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-220">ダイヤルイン会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-221">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-222">Lync Server 会議アテンダントサービス (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="e7db5-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-223">5072</span><span class="sxs-lookup"><span data-stu-id="e7db5-223">5072</span></span></p></td>
<td><p><span data-ttu-id="e7db5-224">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-225">アテンダント (ダイヤルイン会議) の SIP 要求を受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7db5-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-226">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e7db5-227">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-228">5070</span><span class="sxs-lookup"><span data-stu-id="e7db5-228">5070</span></span></p></td>
<td><p><span data-ttu-id="e7db5-229">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-230">フロント エンド サーバーから仲介サーバーへの要求を受信するために仲介サーバーで使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-231">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e7db5-232">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-233">5067</span><span class="sxs-lookup"><span data-stu-id="e7db5-233">5067</span></span></p></td>
<td><p><span data-ttu-id="e7db5-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-235">PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-236">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e7db5-237">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-238">5068</span><span class="sxs-lookup"><span data-stu-id="e7db5-238">5068</span></span></p></td>
<td><p><span data-ttu-id="e7db5-239">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-240">PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-241">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e7db5-242">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-243">5081</span><span class="sxs-lookup"><span data-stu-id="e7db5-243">5081</span></span></p></td>
<td><p><span data-ttu-id="e7db5-244">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-245">仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-246">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e7db5-247">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-248">5082</span><span class="sxs-lookup"><span data-stu-id="e7db5-248">5082</span></span></p></td>
<td><p><span data-ttu-id="e7db5-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-250">仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-251">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-252">Lync Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-253">5065</span><span class="sxs-lookup"><span data-stu-id="e7db5-253">5065</span></span></p></td>
<td><p><span data-ttu-id="e7db5-254">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-255">アプリケーション共有の SIP リッスン要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-256">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-257">Lync Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="e7db5-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="e7db5-259">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-260">アプリケーション共有で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="e7db5-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-261">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-262">Lync Server 会議アナウンスサービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-263">5073</span><span class="sxs-lookup"><span data-stu-id="e7db5-263">5073</span></span></p></td>
<td><p><span data-ttu-id="e7db5-264">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-265">Lync Server 会議アナウンスサービス (ダイヤルイン会議) の SIP 要求を受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7db5-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-266">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-267">Lync Server コール パーク サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-268">5075</span><span class="sxs-lookup"><span data-stu-id="e7db5-268">5075</span></span></p></td>
<td><p><span data-ttu-id="e7db5-269">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-270">コール パーク アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-271">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-272">Lync Server Audio Test service</span><span class="sxs-lookup"><span data-stu-id="e7db5-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-273">5076</span><span class="sxs-lookup"><span data-stu-id="e7db5-273">5076</span></span></p></td>
<td><p><span data-ttu-id="e7db5-274">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-275">オーディオ テスト サービスの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-276">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-277">該当なし</span><span class="sxs-lookup"><span data-stu-id="e7db5-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="e7db5-278">5066</span><span class="sxs-lookup"><span data-stu-id="e7db5-278">5066</span></span></p></td>
<td><p><span data-ttu-id="e7db5-279">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-280">発信 Enhanced 9-1-1 (E9-1-1) ゲートウェイで使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-281">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-282">Lync Server 応答グループ サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-283">5071</span><span class="sxs-lookup"><span data-stu-id="e7db5-283">5071</span></span></p></td>
<td><p><span data-ttu-id="e7db5-284">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-285">応答グループ アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-286">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-287">Lync Server 応答グループ サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-288">8404</span><span class="sxs-lookup"><span data-stu-id="e7db5-288">8404</span></span></p></td>
<td><p><span data-ttu-id="e7db5-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-290">応答グループ アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-291">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-292">Lync Server 帯域幅ポリシーサービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-293">5080</span><span class="sxs-lookup"><span data-stu-id="e7db5-293">5080</span></span></p></td>
<td><p><span data-ttu-id="e7db5-294">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-295">音声ビデオ エッジ TURN トラフィックの帯域幅ポリシー サービスによる通話受付管理で使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-296">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-297">Lync Server 帯域幅ポリシーサービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-298">448</span><span class="sxs-lookup"><span data-stu-id="e7db5-298">448</span></span></p></td>
<td><p><span data-ttu-id="e7db5-299">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-300">Lync Server 帯域幅ポリシーサービスによる通話受付管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7db5-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-301">中央管理ストアが存在するフロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="e7db5-302">Lync Server マスター レプリケーター エージェント サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-303">445</span><span class="sxs-lookup"><span data-stu-id="e7db5-303">445</span></span></p></td>
<td><p><span data-ttu-id="e7db5-304">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-305">中央管理ストアから Lync Server を実行しているサーバーに構成データをプッシュするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7db5-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-306">すべてのサーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-307">SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="e7db5-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="e7db5-308">1434</span><span class="sxs-lookup"><span data-stu-id="e7db5-308">1434</span></span></p></td>
<td><p><span data-ttu-id="e7db5-309">受信</span><span class="sxs-lookup"><span data-stu-id="e7db5-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-310">ローカルの SQL Server インスタンスの中央管理ストアデータのローカルにレプリケートされたコピーのための SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="e7db5-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-311">すべての内部サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-312">各種</span><span class="sxs-lookup"><span data-stu-id="e7db5-312">Various</span></span></p></td>
<td><p><span data-ttu-id="e7db5-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="e7db5-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="e7db5-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="e7db5-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-315">すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="e7db5-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="e7db5-316">オーディオを終了するすべてのサーバーで使用します。フロントエンドサーバー (Lync Server 会議アテンダントサービス、lync Server 会議アナウンスサービス、および Lync Server 音声ビデオ会議サービスの場合)、および仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="e7db5-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-317">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7db5-318">443</span><span class="sxs-lookup"><span data-stu-id="e7db5-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7db5-319">Lync Server 2013 が Office Web Apps サーバーに接続するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e7db5-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-320">レ</span><span class="sxs-lookup"><span data-stu-id="e7db5-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="e7db5-321">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-322">5060</span><span class="sxs-lookup"><span data-stu-id="e7db5-322">5060</span></span></p></td>
<td><p><span data-ttu-id="e7db5-323">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-324">リモート通話コントロール サーバーなど、信頼されたサービスへの静的ルートの場合にオプションで使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-325">レ</span><span class="sxs-lookup"><span data-stu-id="e7db5-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="e7db5-326">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-327">444</span><span class="sxs-lookup"><span data-stu-id="e7db5-327">444</span></span></p></td>
<td><p><span data-ttu-id="e7db5-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e7db5-328">HTTPS</span></span></p>
<p><span data-ttu-id="e7db5-329">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-330">フロントエンドとディレクターの間のサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="e7db5-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="e7db5-331">さらに、クライアント証明書を (フロントエンドサーバーに) 公開するか、クライアント証明書が既に公開されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7db5-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-332">レ</span><span class="sxs-lookup"><span data-stu-id="e7db5-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="e7db5-333">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-334">80</span><span class="sxs-lookup"><span data-stu-id="e7db5-334">80</span></span></p></td>
<td><p><span data-ttu-id="e7db5-335">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-p105">ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への初期通信に使用。通常の動作では HTTPS トラフィックに切り替わり、ポート 443 およびプロトコル TCP を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7db5-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-338">レ</span><span class="sxs-lookup"><span data-stu-id="e7db5-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="e7db5-339">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-340">443</span><span class="sxs-lookup"><span data-stu-id="e7db5-340">443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e7db5-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="e7db5-342">ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-343">レ</span><span class="sxs-lookup"><span data-stu-id="e7db5-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="e7db5-344">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-345">5061</span><span class="sxs-lookup"><span data-stu-id="e7db5-345">5061</span></span></p></td>
<td><p><span data-ttu-id="e7db5-346">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-347">サーバー間の内部通信とクライアント接続に使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-348">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-349">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-350">5070</span><span class="sxs-lookup"><span data-stu-id="e7db5-350">5070</span></span></p></td>
<td><p><span data-ttu-id="e7db5-351">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-352">フロント エンド サーバーからの要求を受信するために仲介サーバーで使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-353">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-354">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-355">5067</span><span class="sxs-lookup"><span data-stu-id="e7db5-355">5067</span></span></p></td>
<td><p><span data-ttu-id="e7db5-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-357">PSTN ゲートウェイからの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-358">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-359">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-360">5068</span><span class="sxs-lookup"><span data-stu-id="e7db5-360">5068</span></span></p></td>
<td><p><span data-ttu-id="e7db5-361">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-362">PSTN ゲートウェイからの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-363">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="e7db5-364">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-365">5070</span><span class="sxs-lookup"><span data-stu-id="e7db5-365">5070</span></span></p></td>
<td><p><span data-ttu-id="e7db5-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-367">フロント エンド サーバーからの SIP 要求で使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-368">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="e7db5-369">常設チャット SIP</span><span class="sxs-lookup"><span data-stu-id="e7db5-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-370">5041</span><span class="sxs-lookup"><span data-stu-id="e7db5-370">5041</span></span></p></td>
<td><p><span data-ttu-id="e7db5-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-372">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="e7db5-373">常設チャット Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="e7db5-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-374">881</span><span class="sxs-lookup"><span data-stu-id="e7db5-374">881</span></span></p></td>
<td><p><span data-ttu-id="e7db5-375">TCP (TLS) と TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-376">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e7db5-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="e7db5-377">常設チャットのファイル転送サービス</span><span class="sxs-lookup"><span data-stu-id="e7db5-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="e7db5-378">443</span><span class="sxs-lookup"><span data-stu-id="e7db5-378">443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e7db5-380">リモート通話コントロールのシナリオによっては、フロントエンドサーバーまたはディレクターと PBX との間に TCP 接続が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7db5-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="e7db5-381">Lync Server は TCP ポート5060を使用しなくなりましたが、リモート通話コントロールの展開時には、RCC Line サーバーの FQDN を、フロントエンドサーバーまたはディレクターが PBX システムに接続するために使用する TCP ポートに関連付ける信頼できるサーバー構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="e7db5-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="e7db5-382">詳細については、「Lync Server Management Shell」のドキュメントの「 <STRONG>CsTrustedApplicationComputer</STRONG>コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7db5-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="e7db5-383">次の表に、(DNS 負荷分散ではない) ハードウェア負荷分散のみを使用するプールでハードウェア ロード バランサーを開くために必要なポートを示します。</span><span class="sxs-lookup"><span data-stu-id="e7db5-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="e7db5-384">ハードウェア負荷分散のみを使用する場合のハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7db5-385">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-385">Load Balancer</span></span></th>
<th><span data-ttu-id="e7db5-386">ポート</span><span class="sxs-lookup"><span data-stu-id="e7db5-386">Port</span></span></th>
<th><span data-ttu-id="e7db5-387">プロトコル</span><span class="sxs-lookup"><span data-stu-id="e7db5-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-388">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-389">5061</span><span class="sxs-lookup"><span data-stu-id="e7db5-389">5061</span></span></p></td>
<td><p><span data-ttu-id="e7db5-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-391">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-392">444</span><span class="sxs-lookup"><span data-stu-id="e7db5-392">444</span></span></p></td>
<td><p><span data-ttu-id="e7db5-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e7db5-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-394">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-395">135</span><span class="sxs-lookup"><span data-stu-id="e7db5-395">135</span></span></p></td>
<td><p><span data-ttu-id="e7db5-396">DCOM およびリモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="e7db5-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-397">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-398">80</span><span class="sxs-lookup"><span data-stu-id="e7db5-398">80</span></span></p></td>
<td><p><span data-ttu-id="e7db5-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="e7db5-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-400">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-401">8080</span><span class="sxs-lookup"><span data-stu-id="e7db5-401">8080</span></span></p></td>
<td><p><span data-ttu-id="e7db5-402">TCP - フロント エンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</span><span class="sxs-lookup"><span data-stu-id="e7db5-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-403">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-404">443</span><span class="sxs-lookup"><span data-stu-id="e7db5-404">443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e7db5-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-406">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-407">4443</span><span class="sxs-lookup"><span data-stu-id="e7db5-407">4443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-408">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="e7db5-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-409">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-410">5072</span><span class="sxs-lookup"><span data-stu-id="e7db5-410">5072</span></span></p></td>
<td><p><span data-ttu-id="e7db5-411">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-412">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-413">5073</span><span class="sxs-lookup"><span data-stu-id="e7db5-413">5073</span></span></p></td>
<td><p><span data-ttu-id="e7db5-414">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-415">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-416">5075</span><span class="sxs-lookup"><span data-stu-id="e7db5-416">5075</span></span></p></td>
<td><p><span data-ttu-id="e7db5-417">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-418">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-419">5076</span><span class="sxs-lookup"><span data-stu-id="e7db5-419">5076</span></span></p></td>
<td><p><span data-ttu-id="e7db5-420">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-421">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-422">5071</span><span class="sxs-lookup"><span data-stu-id="e7db5-422">5071</span></span></p></td>
<td><p><span data-ttu-id="e7db5-423">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-424">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-425">5080</span><span class="sxs-lookup"><span data-stu-id="e7db5-425">5080</span></span></p></td>
<td><p><span data-ttu-id="e7db5-426">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-427">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-428">448</span><span class="sxs-lookup"><span data-stu-id="e7db5-428">448</span></span></p></td>
<td><p><span data-ttu-id="e7db5-429">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-430">仲介サーバーのロードバランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-431">5070</span><span class="sxs-lookup"><span data-stu-id="e7db5-431">5070</span></span></p></td>
<td><p><span data-ttu-id="e7db5-432">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-433">フロントエンドサーバーのロードバランサー (プールが仲介サーバーも実行している場合)</span><span class="sxs-lookup"><span data-stu-id="e7db5-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-434">5070</span><span class="sxs-lookup"><span data-stu-id="e7db5-434">5070</span></span></p></td>
<td><p><span data-ttu-id="e7db5-435">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-436">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-437">443</span><span class="sxs-lookup"><span data-stu-id="e7db5-437">443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e7db5-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-439">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-440">444</span><span class="sxs-lookup"><span data-stu-id="e7db5-440">444</span></span></p></td>
<td><p><span data-ttu-id="e7db5-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e7db5-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-442">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-443">5061</span><span class="sxs-lookup"><span data-stu-id="e7db5-443">5061</span></span></p></td>
<td><p><span data-ttu-id="e7db5-444">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-445">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-446">4443</span><span class="sxs-lookup"><span data-stu-id="e7db5-446">4443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-447">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="e7db5-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e7db5-p107">DNS 負荷分散を使用するフロント エンド プールとディレクター プールでも、ハードウェア ロード バランサーを展開しておく必要があります。 次の表に、これらのハードウェア ロード バランサーで開く必要があるポートを示します。</span><span class="sxs-lookup"><span data-stu-id="e7db5-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="e7db5-450">DNS 負荷分散を使用する場合のハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7db5-451">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-451">Load Balancer</span></span></th>
<th><span data-ttu-id="e7db5-452">ポート</span><span class="sxs-lookup"><span data-stu-id="e7db5-452">Port</span></span></th>
<th><span data-ttu-id="e7db5-453">プロトコル</span><span class="sxs-lookup"><span data-stu-id="e7db5-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-454">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-455">80</span><span class="sxs-lookup"><span data-stu-id="e7db5-455">80</span></span></p></td>
<td><p><span data-ttu-id="e7db5-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="e7db5-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-457">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-458">443</span><span class="sxs-lookup"><span data-stu-id="e7db5-458">443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e7db5-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-460">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-461">8080</span><span class="sxs-lookup"><span data-stu-id="e7db5-461">8080</span></span></p></td>
<td><p><span data-ttu-id="e7db5-462">TCP - フロント エンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</span><span class="sxs-lookup"><span data-stu-id="e7db5-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-463">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-464">4443</span><span class="sxs-lookup"><span data-stu-id="e7db5-464">4443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-465">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="e7db5-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-466">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-467">443</span><span class="sxs-lookup"><span data-stu-id="e7db5-467">443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e7db5-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-469">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e7db5-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e7db5-470">4443</span><span class="sxs-lookup"><span data-stu-id="e7db5-470">4443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-471">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="e7db5-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="e7db5-472">必要なクライアント ポート</span><span class="sxs-lookup"><span data-stu-id="e7db5-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7db5-473">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e7db5-473">Component</span></span></th>
<th><span data-ttu-id="e7db5-474">ポート</span><span class="sxs-lookup"><span data-stu-id="e7db5-474">Port</span></span></th>
<th><span data-ttu-id="e7db5-475">プロトコル</span><span class="sxs-lookup"><span data-stu-id="e7db5-475">Protocol</span></span></th>
<th><span data-ttu-id="e7db5-476">メモ</span><span class="sxs-lookup"><span data-stu-id="e7db5-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-477">クライアント</span><span class="sxs-lookup"><span data-stu-id="e7db5-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="e7db5-478">67/68</span><span class="sxs-lookup"><span data-stu-id="e7db5-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="e7db5-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-480">Lync Server によって、レジストラーの FQDN を検索するために使用されます (つまり、DNS SRV に障害が発生し、手動設定が構成されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="e7db5-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-481">クライアント</span><span class="sxs-lookup"><span data-stu-id="e7db5-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="e7db5-482">443</span><span class="sxs-lookup"><span data-stu-id="e7db5-482">443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-484">外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-485">クライアント</span><span class="sxs-lookup"><span data-stu-id="e7db5-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="e7db5-486">443</span><span class="sxs-lookup"><span data-stu-id="e7db5-486">443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-488">Web 会議セッションへの外部ユーザー アクセスで使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-489">クライアント</span><span class="sxs-lookup"><span data-stu-id="e7db5-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="e7db5-490">443</span><span class="sxs-lookup"><span data-stu-id="e7db5-490">443</span></span></p></td>
<td><p><span data-ttu-id="e7db5-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="e7db5-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-492">音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用</span><span class="sxs-lookup"><span data-stu-id="e7db5-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-493">クライアント</span><span class="sxs-lookup"><span data-stu-id="e7db5-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="e7db5-494">3478</span><span class="sxs-lookup"><span data-stu-id="e7db5-494">3478</span></span></p></td>
<td><p><span data-ttu-id="e7db5-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="e7db5-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-496">音声ビデオセッションおよびメディアへの外部ユーザーアクセスに使用されます (UDP)</span><span class="sxs-lookup"><span data-stu-id="e7db5-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-497">クライアント</span><span class="sxs-lookup"><span data-stu-id="e7db5-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="e7db5-498">5061</span><span class="sxs-lookup"><span data-stu-id="e7db5-498">5061</span></span></p></td>
<td><p><span data-ttu-id="e7db5-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e7db5-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e7db5-500">外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</span><span class="sxs-lookup"><span data-stu-id="e7db5-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-501">クライアント</span><span class="sxs-lookup"><span data-stu-id="e7db5-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="e7db5-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="e7db5-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="e7db5-503">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-504">Lync クライアントと以前のクライアントの間のファイル転送に使用されます (Microsoft Office Communications Server 2007 R2、Microsoft Office Communications Server 2007、および Live Communications Server 2005)。</span><span class="sxs-lookup"><span data-stu-id="e7db5-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-505">クライアント</span><span class="sxs-lookup"><span data-stu-id="e7db5-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="e7db5-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="e7db5-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="e7db5-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="e7db5-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-508">オーディオ ポート範囲 (少なくとも 20 個のポートが必要)</span><span class="sxs-lookup"><span data-stu-id="e7db5-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-509">クライアント</span><span class="sxs-lookup"><span data-stu-id="e7db5-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="e7db5-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="e7db5-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="e7db5-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="e7db5-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-512">ビデオ ポート範囲 (少なくとも 20 個のポートが必要)</span><span class="sxs-lookup"><span data-stu-id="e7db5-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-513">クライアント</span><span class="sxs-lookup"><span data-stu-id="e7db5-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="e7db5-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="e7db5-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="e7db5-515">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-516">ピアツーピア ファイル転送 (会議ファイル転送の場合、クライアントは PSOM を使用)。</span><span class="sxs-lookup"><span data-stu-id="e7db5-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db5-517">クライアント</span><span class="sxs-lookup"><span data-stu-id="e7db5-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="e7db5-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="e7db5-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="e7db5-519">TCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-520">アプリケーション共有。</span><span class="sxs-lookup"><span data-stu-id="e7db5-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db5-521">Aastra 6721ip 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="e7db5-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="e7db5-522">Aastra 6725ip 卓上電話</span><span class="sxs-lookup"><span data-stu-id="e7db5-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="e7db5-523">HP 4110 IP 電話 (共通領域電話)</span><span class="sxs-lookup"><span data-stu-id="e7db5-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="e7db5-524">HP 4120 IP 電話 (卓上電話)</span><span class="sxs-lookup"><span data-stu-id="e7db5-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="e7db5-525">Polycom CX500 IP 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="e7db5-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="e7db5-526">Polycom CX600 IP 卓上電話</span><span class="sxs-lookup"><span data-stu-id="e7db5-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="e7db5-527">Polycom CX700 IP 卓上電話</span><span class="sxs-lookup"><span data-stu-id="e7db5-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="e7db5-528">Polycom CX3000 IP 会議電話</span><span class="sxs-lookup"><span data-stu-id="e7db5-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="e7db5-529">67/68</span><span class="sxs-lookup"><span data-stu-id="e7db5-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="e7db5-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="e7db5-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="e7db5-531">Lync Server 証明書、プロビジョニング FQDN、レジストラー FQDN を検索するために、リストされているデバイスによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7db5-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e7db5-532">**\*** これらのメディアの種類に対して特定のポートを構成するには、Get-csconferencingconfiguration コマンドレット (ClientMediaPortRangeEnabled、ClientMediaPort、および ClientMediaPortRange パラメーター) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7db5-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7db5-533">Lync クライアント用のプログラムを設定すると、クライアントコンピューターに必要なオペレーティングシステムファイアウォールの例外が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="e7db5-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e7db5-534">外部ユーザー アクセス用に使用されるポートは、クライアントが組織のファイアウォールを通過する必要のあるすべてのシナリオにおいて必要です (たとえば、他の組織によってホストされる外部の通信や会議)。</span><span class="sxs-lookup"><span data-stu-id="e7db5-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

