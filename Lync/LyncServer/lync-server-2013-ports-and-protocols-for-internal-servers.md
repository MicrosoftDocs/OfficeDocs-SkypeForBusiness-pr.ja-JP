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
ms.openlocfilehash: c748a79fe118c9b1d233a7a276bd8298a0e1c3e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="e31da-102">Lync Server 2013 の内部サーバーのポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="e31da-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e31da-103">_**トピックの最終更新日:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="e31da-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="e31da-104">このセクションでは、Lync Server 展開のサーバー、ロードバランサー、およびクライアントで使用されるポートとプロトコルの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="e31da-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e31da-105">1対1の通信に関係する Lync および Communicator クライアントは、ピアツーピアと呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="e31da-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="e31da-106">技術的には、2つのクライアントは1つの会話に、インスタントメッセージング multipoint control unit (IMMCU) を中央に持つ1つの会話と通信します。</span><span class="sxs-lookup"><span data-stu-id="e31da-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="e31da-107">IMMCU はフロントエンドサーバーのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e31da-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="e31da-108">必要な通信ワークフローに IMMCU を配置すると、フロントエンドサーバーが有効になっている通話詳細記録およびその他の機能を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e31da-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="e31da-109">クライアント上の動的送信元ポートからフロントエンドサーバーポート TLS/TCP/5061 への通信です (推奨トランスポート層セキュリティを使用していることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="e31da-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="e31da-110">設計上、Lync Server と IMMCU がアクティブで利用可能な場合にのみ、ピアツーピア通信 (およびマルチパーティ IM) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e31da-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="e31da-111">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="e31da-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e31da-112">Lync server がファイアウォールで必要なポートを開くときに、サーバー上で Lync Server サービスを開始する前に、Windows ファイアウォールを実行しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e31da-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="e31da-113">エッジコンポーネントのファイアウォール構成の詳細については、「 [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e31da-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="e31da-114">次の表に、各内部サーバー役割で開く必要のあるポートの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e31da-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="e31da-115">必要なサーバー ポート (サーバー役割別)</span><span class="sxs-lookup"><span data-stu-id="e31da-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="e31da-116">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="e31da-116">Server role</span></span></th>
<th><span data-ttu-id="e31da-117">サービス名</span><span class="sxs-lookup"><span data-stu-id="e31da-117">Service name</span></span></th>
<th><span data-ttu-id="e31da-118">ポート</span><span class="sxs-lookup"><span data-stu-id="e31da-118">Port</span></span></th>
<th><span data-ttu-id="e31da-119">プロトコル</span><span class="sxs-lookup"><span data-stu-id="e31da-119">Protocol</span></span></th>
<th><span data-ttu-id="e31da-120">メモ</span><span class="sxs-lookup"><span data-stu-id="e31da-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e31da-121">すべてのサーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-122">SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="e31da-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="e31da-123">1434</span><span class="sxs-lookup"><span data-stu-id="e31da-123">1434</span></span></p></td>
<td><p><span data-ttu-id="e31da-124">受信</span><span class="sxs-lookup"><span data-stu-id="e31da-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="e31da-125">中央管理ストアデータベースのローカルにレプリケートされたコピーの SQL ブラウザー。</span><span class="sxs-lookup"><span data-stu-id="e31da-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-126">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-127">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e31da-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e31da-128">5060</span><span class="sxs-lookup"><span data-stu-id="e31da-128">5060</span></span></p></td>
<td><p><span data-ttu-id="e31da-129">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-130">リモート通話コントロール サーバーなどの Standard Edition サーバーとフロント エンド サーバーで、信頼されたサービスへの静的ルートの場合にオプションとして使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-131">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-132">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e31da-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e31da-133">5061</span><span class="sxs-lookup"><span data-stu-id="e31da-133">5061</span></span></p></td>
<td><p><span data-ttu-id="e31da-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e31da-p102">サーバー間のすべての内部 SIP 通信 (MTLS)、サーバーとクライアントの間の SIP 通信 (TLS)、およびフロント エンド サーバーと仲介サーバーの間の SIP 通信 (MTLS) において、Standard Edition サーバーとフロント エンド プールで使用。 監視サーバーとの通信でも使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-137">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-138">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e31da-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e31da-139">444</span><span class="sxs-lookup"><span data-stu-id="e31da-139">444</span></span></p></td>
<td><p><span data-ttu-id="e31da-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e31da-140">HTTPS</span></span></p>
<p><span data-ttu-id="e31da-141">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-142">フォーカス (会議の状態を管理する Lync Server コンポーネント) と個々のサーバーとの間の HTTPS 通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e31da-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="e31da-143">このポートは、存続可能ブランチアプライアンスとフロントエンドサーバー間の TCP 通信にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="e31da-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-144">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-145">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e31da-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e31da-146">135</span><span class="sxs-lookup"><span data-stu-id="e31da-146">135</span></span></p></td>
<td><p><span data-ttu-id="e31da-147">DCOM およびリモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="e31da-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="e31da-148">ユーザーの移行、ユーザー レプリケーター同期、およびアドレス帳同期などの DCOM ベースの操作で使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-149">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-150">Lync Server IM 会議サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="e31da-151">5062</span><span class="sxs-lookup"><span data-stu-id="e31da-151">5062</span></span></p></td>
<td><p><span data-ttu-id="e31da-152">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-153">インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-154">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-155">Lync Server Web 会議サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="e31da-156">8057</span><span class="sxs-lookup"><span data-stu-id="e31da-156">8057</span></span></p></td>
<td><p><span data-ttu-id="e31da-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e31da-158">クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-159">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-160">Lync Server Web 会議互換性サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e31da-161">8058</span><span class="sxs-lookup"><span data-stu-id="e31da-161">8058</span></span></p></td>
<td><p><span data-ttu-id="e31da-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e31da-163">Live Meeting クライアントおよび以前のバージョンの Lync Server からの、永続的な共有オブジェクトモデル (PSOM) 接続をリッスンするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e31da-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-164">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-165">Lync Server 音声ビデオ会議サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="e31da-166">5063</span><span class="sxs-lookup"><span data-stu-id="e31da-166">5063</span></span></p></td>
<td><p><span data-ttu-id="e31da-167">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-168">音声ビデオ会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-169">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-170">Lync Server 音声ビデオ会議サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="e31da-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="e31da-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="e31da-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="e31da-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="e31da-173">ビデオ会議で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="e31da-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-174">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-175">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e31da-176">80</span><span class="sxs-lookup"><span data-stu-id="e31da-176">80</span></span></p></td>
<td><p><span data-ttu-id="e31da-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="e31da-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="e31da-178">HTTPS が使用されない場合の、フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-179">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-180">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e31da-181">443</span><span class="sxs-lookup"><span data-stu-id="e31da-181">443</span></span></p></td>
<td><p><span data-ttu-id="e31da-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e31da-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="e31da-183">フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-184">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-185">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e31da-186">8080</span><span class="sxs-lookup"><span data-stu-id="e31da-186">8080</span></span></p></td>
<td><p><span data-ttu-id="e31da-187">TCP および HTTP</span><span class="sxs-lookup"><span data-stu-id="e31da-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="e31da-188">外部アクセスのために web コンポーネントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e31da-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-189">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-190">Web サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="e31da-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="e31da-191">4443</span><span class="sxs-lookup"><span data-stu-id="e31da-191">4443</span></span></p></td>
<td><p><span data-ttu-id="e31da-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e31da-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="e31da-193">自動検出サインインの HTTPS (リバースプロキシから) および HTTPS フロントエンドプール間通信。</span><span class="sxs-lookup"><span data-stu-id="e31da-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-194">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-195">Web サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="e31da-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="e31da-196">8060</span><span class="sxs-lookup"><span data-stu-id="e31da-196">8060</span></span></p></td>
<td><p><span data-ttu-id="e31da-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-198">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-199">Web サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="e31da-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="e31da-200">8061</span><span class="sxs-lookup"><span data-stu-id="e31da-200">8061</span></span></p></td>
<td><p><span data-ttu-id="e31da-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-202">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-203">Mobility Services コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e31da-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="e31da-204">5086</span><span class="sxs-lookup"><span data-stu-id="e31da-204">5086</span></span></p></td>
<td><p><span data-ttu-id="e31da-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e31da-206">Mobility Services 内部プロセスで使用される SIP ポート</span><span class="sxs-lookup"><span data-stu-id="e31da-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-207">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-208">Mobility Services コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e31da-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="e31da-209">5087</span><span class="sxs-lookup"><span data-stu-id="e31da-209">5087</span></span></p></td>
<td><p><span data-ttu-id="e31da-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e31da-211">Mobility Services 内部プロセスで使用される SIP ポート</span><span class="sxs-lookup"><span data-stu-id="e31da-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-212">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-213">Mobility Services コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e31da-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="e31da-214">443</span><span class="sxs-lookup"><span data-stu-id="e31da-214">443</span></span></p></td>
<td><p><span data-ttu-id="e31da-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e31da-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-216">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-217">Lync Server 会議アテンダントサービス (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="e31da-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="e31da-218">5064</span><span class="sxs-lookup"><span data-stu-id="e31da-218">5064</span></span></p></td>
<td><p><span data-ttu-id="e31da-219">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-220">ダイヤルイン会議の SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-221">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-222">Lync Server 会議アテンダントサービス (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="e31da-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="e31da-223">5072</span><span class="sxs-lookup"><span data-stu-id="e31da-223">5072</span></span></p></td>
<td><p><span data-ttu-id="e31da-224">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-225">アテンダント (ダイヤルイン会議) の SIP 要求を受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e31da-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-226">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e31da-227">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e31da-228">5070</span><span class="sxs-lookup"><span data-stu-id="e31da-228">5070</span></span></p></td>
<td><p><span data-ttu-id="e31da-229">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-230">フロント エンド サーバーから仲介サーバーへの要求を受信するために仲介サーバーで使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-231">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e31da-232">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e31da-233">5067</span><span class="sxs-lookup"><span data-stu-id="e31da-233">5067</span></span></p></td>
<td><p><span data-ttu-id="e31da-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e31da-235">PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-236">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e31da-237">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e31da-238">5068</span><span class="sxs-lookup"><span data-stu-id="e31da-238">5068</span></span></p></td>
<td><p><span data-ttu-id="e31da-239">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-240">PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-241">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e31da-242">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e31da-243">5081</span><span class="sxs-lookup"><span data-stu-id="e31da-243">5081</span></span></p></td>
<td><p><span data-ttu-id="e31da-244">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-245">仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-246">併置された仲介サーバーも実行するフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e31da-247">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e31da-248">5082</span><span class="sxs-lookup"><span data-stu-id="e31da-248">5082</span></span></p></td>
<td><p><span data-ttu-id="e31da-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e31da-250">仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-251">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-252">Lync Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="e31da-253">5065</span><span class="sxs-lookup"><span data-stu-id="e31da-253">5065</span></span></p></td>
<td><p><span data-ttu-id="e31da-254">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-255">アプリケーション共有の SIP リッスン要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-256">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-257">Lync Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="e31da-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="e31da-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="e31da-259">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-260">アプリケーション共有で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="e31da-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-261">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-262">Lync Server 会議アナウンスサービス</span><span class="sxs-lookup"><span data-stu-id="e31da-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="e31da-263">5073</span><span class="sxs-lookup"><span data-stu-id="e31da-263">5073</span></span></p></td>
<td><p><span data-ttu-id="e31da-264">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-265">Lync Server 会議アナウンスサービス (ダイヤルイン会議) の SIP 要求を受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e31da-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-266">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-267">Lync Server コール パーク サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="e31da-268">5075</span><span class="sxs-lookup"><span data-stu-id="e31da-268">5075</span></span></p></td>
<td><p><span data-ttu-id="e31da-269">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-270">コール パーク アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-271">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-272">Lync Server Audio Test service</span><span class="sxs-lookup"><span data-stu-id="e31da-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="e31da-273">5076</span><span class="sxs-lookup"><span data-stu-id="e31da-273">5076</span></span></p></td>
<td><p><span data-ttu-id="e31da-274">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-275">オーディオ テスト サービスの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-276">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-277">該当なし</span><span class="sxs-lookup"><span data-stu-id="e31da-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="e31da-278">5066</span><span class="sxs-lookup"><span data-stu-id="e31da-278">5066</span></span></p></td>
<td><p><span data-ttu-id="e31da-279">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-280">発信 Enhanced 9-1-1 (E9-1-1) ゲートウェイで使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-281">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-282">Lync Server 応答グループ サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="e31da-283">5071</span><span class="sxs-lookup"><span data-stu-id="e31da-283">5071</span></span></p></td>
<td><p><span data-ttu-id="e31da-284">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-285">応答グループ アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-286">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-287">Lync Server 応答グループ サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="e31da-288">8404</span><span class="sxs-lookup"><span data-stu-id="e31da-288">8404</span></span></p></td>
<td><p><span data-ttu-id="e31da-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e31da-290">応答グループ アプリケーションの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-291">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-292">Lync Server 帯域幅ポリシーサービス</span><span class="sxs-lookup"><span data-stu-id="e31da-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="e31da-293">5080</span><span class="sxs-lookup"><span data-stu-id="e31da-293">5080</span></span></p></td>
<td><p><span data-ttu-id="e31da-294">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-295">音声ビデオ エッジ TURN トラフィックの帯域幅ポリシー サービスによる通話受付管理で使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-296">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-297">Lync Server 帯域幅ポリシーサービス</span><span class="sxs-lookup"><span data-stu-id="e31da-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="e31da-298">448</span><span class="sxs-lookup"><span data-stu-id="e31da-298">448</span></span></p></td>
<td><p><span data-ttu-id="e31da-299">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-300">Lync Server 帯域幅ポリシーサービスによる通話受付管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e31da-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-301">中央管理ストアが存在するフロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="e31da-302">Lync Server マスター レプリケーター エージェント サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="e31da-303">445</span><span class="sxs-lookup"><span data-stu-id="e31da-303">445</span></span></p></td>
<td><p><span data-ttu-id="e31da-304">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-305">中央管理ストアから Lync Server を実行しているサーバーに構成データをプッシュするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e31da-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-306">すべてのサーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-307">SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="e31da-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="e31da-308">1434</span><span class="sxs-lookup"><span data-stu-id="e31da-308">1434</span></span></p></td>
<td><p><span data-ttu-id="e31da-309">受信</span><span class="sxs-lookup"><span data-stu-id="e31da-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="e31da-310">ローカルの SQL Server インスタンスの中央管理ストアデータのローカルにレプリケートされたコピーのための SQL ブラウザー</span><span class="sxs-lookup"><span data-stu-id="e31da-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-311">すべての内部サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-312">各種</span><span class="sxs-lookup"><span data-stu-id="e31da-312">Various</span></span></p></td>
<td><p><span data-ttu-id="e31da-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="e31da-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="e31da-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="e31da-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="e31da-315">すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="e31da-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="e31da-316">オーディオを終了するすべてのサーバーで使用します。フロントエンドサーバー (Lync Server 会議アテンダントサービス、lync Server 会議アナウンスサービス、および Lync Server 音声ビデオ会議サービスの場合)、および仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="e31da-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-317">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e31da-318">443</span><span class="sxs-lookup"><span data-stu-id="e31da-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e31da-319">Lync Server 2013 が Office Web Apps サーバーに接続するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e31da-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-320">レ</span><span class="sxs-lookup"><span data-stu-id="e31da-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="e31da-321">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e31da-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e31da-322">5060</span><span class="sxs-lookup"><span data-stu-id="e31da-322">5060</span></span></p></td>
<td><p><span data-ttu-id="e31da-323">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-324">リモート通話コントロール サーバーなど、信頼されたサービスへの静的ルートの場合にオプションで使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-325">レ</span><span class="sxs-lookup"><span data-stu-id="e31da-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="e31da-326">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e31da-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e31da-327">444</span><span class="sxs-lookup"><span data-stu-id="e31da-327">444</span></span></p></td>
<td><p><span data-ttu-id="e31da-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e31da-328">HTTPS</span></span></p>
<p><span data-ttu-id="e31da-329">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-330">フロントエンドとディレクターの間のサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="e31da-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="e31da-331">さらに、クライアント証明書を (フロントエンドサーバーに) 公開するか、クライアント証明書が既に公開されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e31da-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-332">レ</span><span class="sxs-lookup"><span data-stu-id="e31da-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="e31da-333">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e31da-334">80</span><span class="sxs-lookup"><span data-stu-id="e31da-334">80</span></span></p></td>
<td><p><span data-ttu-id="e31da-335">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-p105">ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への初期通信に使用。通常の動作では HTTPS トラフィックに切り替わり、ポート 443 およびプロトコル TCP を使用します。</span><span class="sxs-lookup"><span data-stu-id="e31da-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-338">レ</span><span class="sxs-lookup"><span data-stu-id="e31da-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="e31da-339">Lync Server Web 互換性サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e31da-340">443</span><span class="sxs-lookup"><span data-stu-id="e31da-340">443</span></span></p></td>
<td><p><span data-ttu-id="e31da-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e31da-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="e31da-342">ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-343">レ</span><span class="sxs-lookup"><span data-stu-id="e31da-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="e31da-344">Lync Server フロントエンドサービス</span><span class="sxs-lookup"><span data-stu-id="e31da-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e31da-345">5061</span><span class="sxs-lookup"><span data-stu-id="e31da-345">5061</span></span></p></td>
<td><p><span data-ttu-id="e31da-346">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-347">サーバー間の内部通信とクライアント接続に使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-348">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-349">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e31da-350">5070</span><span class="sxs-lookup"><span data-stu-id="e31da-350">5070</span></span></p></td>
<td><p><span data-ttu-id="e31da-351">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-352">フロント エンド サーバーからの要求を受信するために仲介サーバーで使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-353">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-354">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e31da-355">5067</span><span class="sxs-lookup"><span data-stu-id="e31da-355">5067</span></span></p></td>
<td><p><span data-ttu-id="e31da-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e31da-357">PSTN ゲートウェイからの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-358">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-359">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e31da-360">5068</span><span class="sxs-lookup"><span data-stu-id="e31da-360">5068</span></span></p></td>
<td><p><span data-ttu-id="e31da-361">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-362">PSTN ゲートウェイからの SIP 要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-363">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="e31da-364">Lync Server 仲介サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e31da-365">5070</span><span class="sxs-lookup"><span data-stu-id="e31da-365">5070</span></span></p></td>
<td><p><span data-ttu-id="e31da-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e31da-367">フロント エンド サーバーからの SIP 要求で使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-368">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="e31da-369">常設チャット SIP</span><span class="sxs-lookup"><span data-stu-id="e31da-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="e31da-370">5041</span><span class="sxs-lookup"><span data-stu-id="e31da-370">5041</span></span></p></td>
<td><p><span data-ttu-id="e31da-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-372">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="e31da-373">常設チャット Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="e31da-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="e31da-374">881</span><span class="sxs-lookup"><span data-stu-id="e31da-374">881</span></span></p></td>
<td><p><span data-ttu-id="e31da-375">TCP (TLS) と TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-376">常設チャット フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e31da-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="e31da-377">常設チャットのファイル転送サービス</span><span class="sxs-lookup"><span data-stu-id="e31da-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="e31da-378">443</span><span class="sxs-lookup"><span data-stu-id="e31da-378">443</span></span></p></td>
<td><p><span data-ttu-id="e31da-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e31da-380">リモート通話コントロールのシナリオによっては、フロントエンドサーバーまたはディレクターと PBX との間に TCP 接続が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e31da-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="e31da-381">Lync Server は TCP ポート5060を使用しなくなりましたが、リモート通話コントロールの展開時には、RCC Line サーバーの FQDN を、フロントエンドサーバーまたはディレクターが PBX システムに接続するために使用する TCP ポートに関連付ける信頼できるサーバー構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="e31da-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="e31da-382">詳細については、「Lync Server Management Shell」のドキュメントの「 <STRONG>CsTrustedApplicationComputer</STRONG>コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e31da-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="e31da-383">次の表に、(DNS 負荷分散ではない) ハードウェア負荷分散のみを使用するプールでハードウェア ロード バランサーを開くために必要なポートを示します。</span><span class="sxs-lookup"><span data-stu-id="e31da-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="e31da-384">ハードウェア負荷分散のみを使用する場合のハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e31da-385">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-385">Load Balancer</span></span></th>
<th><span data-ttu-id="e31da-386">ポート</span><span class="sxs-lookup"><span data-stu-id="e31da-386">Port</span></span></th>
<th><span data-ttu-id="e31da-387">プロトコル</span><span class="sxs-lookup"><span data-stu-id="e31da-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e31da-388">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-389">5061</span><span class="sxs-lookup"><span data-stu-id="e31da-389">5061</span></span></p></td>
<td><p><span data-ttu-id="e31da-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-391">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-392">444</span><span class="sxs-lookup"><span data-stu-id="e31da-392">444</span></span></p></td>
<td><p><span data-ttu-id="e31da-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e31da-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-394">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-395">135</span><span class="sxs-lookup"><span data-stu-id="e31da-395">135</span></span></p></td>
<td><p><span data-ttu-id="e31da-396">DCOM およびリモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="e31da-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-397">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-398">80</span><span class="sxs-lookup"><span data-stu-id="e31da-398">80</span></span></p></td>
<td><p><span data-ttu-id="e31da-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="e31da-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-400">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-401">8080</span><span class="sxs-lookup"><span data-stu-id="e31da-401">8080</span></span></p></td>
<td><p><span data-ttu-id="e31da-402">TCP - フロント エンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</span><span class="sxs-lookup"><span data-stu-id="e31da-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-403">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-404">443</span><span class="sxs-lookup"><span data-stu-id="e31da-404">443</span></span></p></td>
<td><p><span data-ttu-id="e31da-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e31da-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-406">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-407">4443</span><span class="sxs-lookup"><span data-stu-id="e31da-407">4443</span></span></p></td>
<td><p><span data-ttu-id="e31da-408">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="e31da-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-409">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-410">5072</span><span class="sxs-lookup"><span data-stu-id="e31da-410">5072</span></span></p></td>
<td><p><span data-ttu-id="e31da-411">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-412">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-413">5073</span><span class="sxs-lookup"><span data-stu-id="e31da-413">5073</span></span></p></td>
<td><p><span data-ttu-id="e31da-414">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-415">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-416">5075</span><span class="sxs-lookup"><span data-stu-id="e31da-416">5075</span></span></p></td>
<td><p><span data-ttu-id="e31da-417">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-418">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-419">5076</span><span class="sxs-lookup"><span data-stu-id="e31da-419">5076</span></span></p></td>
<td><p><span data-ttu-id="e31da-420">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-421">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-422">5071</span><span class="sxs-lookup"><span data-stu-id="e31da-422">5071</span></span></p></td>
<td><p><span data-ttu-id="e31da-423">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-424">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-425">5080</span><span class="sxs-lookup"><span data-stu-id="e31da-425">5080</span></span></p></td>
<td><p><span data-ttu-id="e31da-426">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-427">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-428">448</span><span class="sxs-lookup"><span data-stu-id="e31da-428">448</span></span></p></td>
<td><p><span data-ttu-id="e31da-429">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-430">仲介サーバーのロードバランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-431">5070</span><span class="sxs-lookup"><span data-stu-id="e31da-431">5070</span></span></p></td>
<td><p><span data-ttu-id="e31da-432">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-433">フロントエンドサーバーのロードバランサー (プールが仲介サーバーも実行している場合)</span><span class="sxs-lookup"><span data-stu-id="e31da-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="e31da-434">5070</span><span class="sxs-lookup"><span data-stu-id="e31da-434">5070</span></span></p></td>
<td><p><span data-ttu-id="e31da-435">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-436">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-437">443</span><span class="sxs-lookup"><span data-stu-id="e31da-437">443</span></span></p></td>
<td><p><span data-ttu-id="e31da-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e31da-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-439">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-440">444</span><span class="sxs-lookup"><span data-stu-id="e31da-440">444</span></span></p></td>
<td><p><span data-ttu-id="e31da-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e31da-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-442">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-443">5061</span><span class="sxs-lookup"><span data-stu-id="e31da-443">5061</span></span></p></td>
<td><p><span data-ttu-id="e31da-444">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-445">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-446">4443</span><span class="sxs-lookup"><span data-stu-id="e31da-446">4443</span></span></p></td>
<td><p><span data-ttu-id="e31da-447">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="e31da-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e31da-p107">DNS 負荷分散を使用するフロント エンド プールとディレクター プールでも、ハードウェア ロード バランサーを展開しておく必要があります。 次の表に、これらのハードウェア ロード バランサーで開く必要があるポートを示します。</span><span class="sxs-lookup"><span data-stu-id="e31da-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="e31da-450">DNS 負荷分散を使用する場合のハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e31da-451">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-451">Load Balancer</span></span></th>
<th><span data-ttu-id="e31da-452">ポート</span><span class="sxs-lookup"><span data-stu-id="e31da-452">Port</span></span></th>
<th><span data-ttu-id="e31da-453">プロトコル</span><span class="sxs-lookup"><span data-stu-id="e31da-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e31da-454">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-455">80</span><span class="sxs-lookup"><span data-stu-id="e31da-455">80</span></span></p></td>
<td><p><span data-ttu-id="e31da-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="e31da-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-457">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-458">443</span><span class="sxs-lookup"><span data-stu-id="e31da-458">443</span></span></p></td>
<td><p><span data-ttu-id="e31da-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e31da-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-460">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-461">8080</span><span class="sxs-lookup"><span data-stu-id="e31da-461">8080</span></span></p></td>
<td><p><span data-ttu-id="e31da-462">TCP - フロント エンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</span><span class="sxs-lookup"><span data-stu-id="e31da-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-463">フロント エンド サーバーのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-464">4443</span><span class="sxs-lookup"><span data-stu-id="e31da-464">4443</span></span></p></td>
<td><p><span data-ttu-id="e31da-465">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="e31da-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-466">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-467">443</span><span class="sxs-lookup"><span data-stu-id="e31da-467">443</span></span></p></td>
<td><p><span data-ttu-id="e31da-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e31da-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-469">ディレクターのロード バランサー</span><span class="sxs-lookup"><span data-stu-id="e31da-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e31da-470">4443</span><span class="sxs-lookup"><span data-stu-id="e31da-470">4443</span></span></p></td>
<td><p><span data-ttu-id="e31da-471">HTTPS (リバース プロキシから)</span><span class="sxs-lookup"><span data-stu-id="e31da-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="e31da-472">必要なクライアント ポート</span><span class="sxs-lookup"><span data-stu-id="e31da-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e31da-473">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e31da-473">Component</span></span></th>
<th><span data-ttu-id="e31da-474">ポート</span><span class="sxs-lookup"><span data-stu-id="e31da-474">Port</span></span></th>
<th><span data-ttu-id="e31da-475">プロトコル</span><span class="sxs-lookup"><span data-stu-id="e31da-475">Protocol</span></span></th>
<th><span data-ttu-id="e31da-476">メモ</span><span class="sxs-lookup"><span data-stu-id="e31da-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e31da-477">クライアント</span><span class="sxs-lookup"><span data-stu-id="e31da-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="e31da-478">67/68</span><span class="sxs-lookup"><span data-stu-id="e31da-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="e31da-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="e31da-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-480">Lync Server によって、レジストラーの FQDN を検索するために使用されます (つまり、DNS SRV に障害が発生し、手動設定が構成されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="e31da-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-481">クライアント</span><span class="sxs-lookup"><span data-stu-id="e31da-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="e31da-482">443</span><span class="sxs-lookup"><span data-stu-id="e31da-482">443</span></span></p></td>
<td><p><span data-ttu-id="e31da-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e31da-484">外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-485">クライアント</span><span class="sxs-lookup"><span data-stu-id="e31da-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="e31da-486">443</span><span class="sxs-lookup"><span data-stu-id="e31da-486">443</span></span></p></td>
<td><p><span data-ttu-id="e31da-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="e31da-488">Web 会議セッションへの外部ユーザー アクセスで使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-489">クライアント</span><span class="sxs-lookup"><span data-stu-id="e31da-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="e31da-490">443</span><span class="sxs-lookup"><span data-stu-id="e31da-490">443</span></span></p></td>
<td><p><span data-ttu-id="e31da-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="e31da-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="e31da-492">音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用</span><span class="sxs-lookup"><span data-stu-id="e31da-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-493">クライアント</span><span class="sxs-lookup"><span data-stu-id="e31da-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="e31da-494">3478</span><span class="sxs-lookup"><span data-stu-id="e31da-494">3478</span></span></p></td>
<td><p><span data-ttu-id="e31da-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="e31da-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="e31da-496">音声ビデオセッションおよびメディアへの外部ユーザーアクセスに使用されます (UDP)</span><span class="sxs-lookup"><span data-stu-id="e31da-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-497">クライアント</span><span class="sxs-lookup"><span data-stu-id="e31da-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="e31da-498">5061</span><span class="sxs-lookup"><span data-stu-id="e31da-498">5061</span></span></p></td>
<td><p><span data-ttu-id="e31da-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e31da-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e31da-500">外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</span><span class="sxs-lookup"><span data-stu-id="e31da-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-501">クライアント</span><span class="sxs-lookup"><span data-stu-id="e31da-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="e31da-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="e31da-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="e31da-503">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-504">Lync クライアントと以前のクライアントの間のファイル転送に使用されます (Microsoft Office Communications Server 2007 R2、Microsoft Office Communications Server 2007、および Live Communications Server 2005)。</span><span class="sxs-lookup"><span data-stu-id="e31da-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-505">クライアント</span><span class="sxs-lookup"><span data-stu-id="e31da-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="e31da-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="e31da-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="e31da-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="e31da-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="e31da-508">オーディオ ポート範囲 (少なくとも 20 個のポートが必要)</span><span class="sxs-lookup"><span data-stu-id="e31da-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-509">クライアント</span><span class="sxs-lookup"><span data-stu-id="e31da-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="e31da-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="e31da-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="e31da-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="e31da-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="e31da-512">ビデオ ポート範囲 (少なくとも 20 個のポートが必要)</span><span class="sxs-lookup"><span data-stu-id="e31da-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-513">クライアント</span><span class="sxs-lookup"><span data-stu-id="e31da-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="e31da-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="e31da-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="e31da-515">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-516">ピアツーピア ファイル転送 (会議ファイル転送の場合、クライアントは PSOM を使用)。</span><span class="sxs-lookup"><span data-stu-id="e31da-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31da-517">クライアント</span><span class="sxs-lookup"><span data-stu-id="e31da-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="e31da-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="e31da-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="e31da-519">TCP</span><span class="sxs-lookup"><span data-stu-id="e31da-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-520">アプリケーション共有。</span><span class="sxs-lookup"><span data-stu-id="e31da-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31da-521">Aastra 6721ip 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="e31da-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="e31da-522">Aastra 6725ip 卓上電話</span><span class="sxs-lookup"><span data-stu-id="e31da-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="e31da-523">HP 4110 IP 電話 (共通領域電話)</span><span class="sxs-lookup"><span data-stu-id="e31da-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="e31da-524">HP 4120 IP 電話 (卓上電話)</span><span class="sxs-lookup"><span data-stu-id="e31da-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="e31da-525">Polycom CX500 IP 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="e31da-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="e31da-526">Polycom CX600 IP 卓上電話</span><span class="sxs-lookup"><span data-stu-id="e31da-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="e31da-527">Polycom CX700 IP 卓上電話</span><span class="sxs-lookup"><span data-stu-id="e31da-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="e31da-528">Polycom CX3000 IP 会議電話</span><span class="sxs-lookup"><span data-stu-id="e31da-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="e31da-529">67/68</span><span class="sxs-lookup"><span data-stu-id="e31da-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="e31da-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="e31da-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="e31da-531">Lync Server 証明書、プロビジョニング FQDN、レジストラー FQDN を検索するために、リストされているデバイスによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e31da-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e31da-532">**\*** これらのメディアの種類に対して特定のポートを構成するには、Get-csconferencingconfiguration コマンドレット (ClientMediaPortRangeEnabled、ClientMediaPort、および ClientMediaPortRange パラメーター) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e31da-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e31da-533">Lync クライアント用のプログラムを設定すると、クライアントコンピューターに必要なオペレーティングシステムファイアウォールの例外が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="e31da-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e31da-534">外部ユーザー アクセス用に使用されるポートは、クライアントが組織のファイアウォールを通過する必要のあるすべてのシナリオにおいて必要です (たとえば、他の組織によってホストされる外部の通信や会議)。</span><span class="sxs-lookup"><span data-stu-id="e31da-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

