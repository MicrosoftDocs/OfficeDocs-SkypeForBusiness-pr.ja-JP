---
title: DNS の概要-拡張統合エッジ (ロードバランサー機器を使用)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c45802282c57ebcf80fbc55b030c985fe7d977cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="9a774-102">DNS の概要-Lync Server 2013 でのハードウェアロードバランサーを使用した拡張統合エッジ</span><span class="sxs-lookup"><span data-stu-id="9a774-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a774-103">_**トピックの最終更新日:** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="9a774-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="9a774-104">Lync Server 2013 へのリモートアクセスの DNS レコードの要件は、証明書とポートの場合と比べて非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="9a774-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="9a774-105">また、Lync 2013 を実行しているクライアントを構成する方法と、フェデレーションを有効にするかどうかに応じて、多くのレコードがオプションになります。</span><span class="sxs-lookup"><span data-stu-id="9a774-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="9a774-106">Lync 2013 DNS の要件の詳細については、「 [Lync Server 2013 の dns 要件を決定](lync-server-2013-determine-dns-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a774-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="9a774-107">スプリットブレイン DNS が構成されていない場合の Lync 2013 クライアントの自動構成の構成の詳細については、「 [Lync Server 2013 の DNS 要件を決定](lync-server-2013-determine-dns-requirements.md)する」の「スプリットブレイン dns なしの自動構成」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a774-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="9a774-108">次の表に、拡張統合エッジ トポロジ (ロード バランサー機器) の図をサポートするのに必要な DNS レコードの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="9a774-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="9a774-109">特定の DNS レコードは、Lync クライアントの自動構成にのみ必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9a774-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="9a774-110">グループポリシーオブジェクト (Gpo) を使用して Lync クライアントを構成することを計画している場合は、関連付けられたレコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9a774-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="9a774-111">重要: エッジサーバーのネットワークアダプターの要件</span><span class="sxs-lookup"><span data-stu-id="9a774-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="9a774-112">ルーティングに関する問題を回避するには、エッジサーバーに少なくとも2つのネットワークアダプターがあり、既定のゲートウェイが、外部インターフェイスに関連付けられているネットワークアダプター上でのみ設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a774-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="9a774-113">たとえば、スケール統合エッジシナリオの図のように、「[拡張統合エッジ」と「ハードウェアロードバランサーを使用する Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)」のように、既定のゲートウェイは外部ファイアウォールを指しています。</span><span class="sxs-lookup"><span data-stu-id="9a774-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="9a774-114">各エッジサーバーでは、2つのネットワークアダプターを次のように構成できます。</span><span class="sxs-lookup"><span data-stu-id="9a774-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="9a774-115">**ネットワーク アダプター 1 (内部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="9a774-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="9a774-116">172.25.33.10 が割り当てられた内部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9a774-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="9a774-117">デフォルト ゲートウェイはありません。</span><span class="sxs-lookup"><span data-stu-id="9a774-117">No default gateway.</span></span>
    
    <span data-ttu-id="9a774-118">エッジサーバーの内部インターフェイスを含むネットワークから、lync server クライアントまたは Lync Server を実行しているサーバー (たとえば、172.25.33.0 から 192.168.10.0) があるネットワークからのルートがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a774-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="9a774-119">**ネットワーク アダプター 2 (外部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="9a774-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="9a774-120">このネットワークアダプターには3つのパブリック IP アドレスが割り当てられます。たとえば、アクセスエッジサービスの131.107.155.10、Web 会議エッジサービスの131.107.155.20、音声ビデオエッジサービスの 131.107.155.30)。</span><span class="sxs-lookup"><span data-stu-id="9a774-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9a774-121">エッジサーバーの実際の外部ネットワークインターフェイスに割り当てられる IP アドレスは、選択するハードウェアロードバランサーによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9a774-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="9a774-122">実際の IP アドレス要件については、使用するハードウェアロードバランサーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a774-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="9a774-123">お勧めはできませんが、3 つのエッジ サービス インターフェイスすべてに 1 つの IP アドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9a774-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="9a774-124">これによって IP アドレスを節約できますが、サービスごとに異なるポート番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="9a774-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="9a774-125">既定のポート番号は 443/TCP で、リモート ファイアウォールの大部分がトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="9a774-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="9a774-126">アクセスエッジサービスのポート値 (たとえば、アクセスエッジサービスの 5061/TCP、Web 会議エッジサービスの 444/tcp、および音声ビデオエッジサービスの 443/TCP) を変更すると、遅延しているファイアウォールが 5061/TCP および 444/TCP 経由のトラフィックを許可しないリモートユーザーに対して問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9a774-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="9a774-127">また、3 つの異なる IP アドレスを使用すると、IP アドレスのフィルター処理が可能になるのでトラブルシューティングが容易になります。</span><span class="sxs-lookup"><span data-stu-id="9a774-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="9a774-128">アクセスエッジサービスの IP アドレスは、既定のゲートウェイがインターネットに接続するルーター (131.107.155.1) に設定されているプライマリアドレスです。</span><span class="sxs-lookup"><span data-stu-id="9a774-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="9a774-129">Web 会議エッジサービスおよび音声ビデオエッジサービスの IP アドレスセカンダリ。</span><span class="sxs-lookup"><span data-stu-id="9a774-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="9a774-130">2つのネットワークアダプターを使用してエッジサーバーを構成するには、2つのオプションのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="9a774-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="9a774-131">もう1つの方法は、エッジサーバーの内部側と外部側に3つのネットワークアダプターを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="9a774-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="9a774-132">このオプションの主な利点は、エッジサーバーサービスごとに別個のネットワークアダプターがあり、トラブルシューティングを行う際により簡潔なデータ収集を行うことができるということです。</span><span class="sxs-lookup"><span data-stu-id="9a774-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="9a774-133">拡張統合エッジ (ロード バランサー機器) で必要な DNS レコード (例)</span><span class="sxs-lookup"><span data-stu-id="9a774-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a774-134">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="9a774-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="9a774-135">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="9a774-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="9a774-136">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="9a774-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="9a774-137">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="9a774-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a774-138">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="9a774-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9a774-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a774-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a774-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="9a774-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="9a774-141">アクセスエッジサービスの外部インターフェイス (Contoso)。</span><span class="sxs-lookup"><span data-stu-id="9a774-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="9a774-142">すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9a774-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a774-143">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="9a774-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9a774-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a774-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a774-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="9a774-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="9a774-146">Web 会議エッジサービスの外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a774-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a774-147">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="9a774-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9a774-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a774-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a774-149">131.107.155.30)</span><span class="sxs-lookup"><span data-stu-id="9a774-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="9a774-150">音声ビデオエッジサービスの外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a774-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a774-151">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="9a774-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="9a774-152">_sip の _tls</span><span class="sxs-lookup"><span data-stu-id="9a774-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a774-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a774-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a774-154">アクセスエッジサービスの外部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9a774-154">Access Edge service external interface.</span></span> <span data-ttu-id="9a774-155">Lync 2013 および Lync 2010 クライアントを外部で動作するように自動構成するために必要です。</span><span class="sxs-lookup"><span data-stu-id="9a774-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="9a774-156">必要に応じて、Lync が有効なユーザーのいるすべての SIP ドメインに対して繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9a774-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a774-157">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="9a774-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="9a774-158">_sipfederationtls の _tcp</span><span class="sxs-lookup"><span data-stu-id="9a774-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a774-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a774-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a774-160">"許可済み SIP ドメイン" (以前のリリースでは拡張フェデレーションと呼ばれました) と呼ばれるフェデレーションパートナーの自動 DNS 検出に必要な、SIP アクセスエッジサービスの外部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9a774-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="9a774-161">プッシュ通知サービスまたは Apple プッシュ通知サービスのいずれかを使用する Lync が有効なユーザーと Microsoft Lync モバイルクライアントを含むすべての SIP ドメインについて、必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9a774-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a774-162">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="9a774-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9a774-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9a774-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="9a774-164">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="9a774-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="9a774-165">統合エッジ内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a774-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

