---
title: 'Lync Server 2013: DNS の概要-拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f2cd6350a74f4dd054d30d81ac13c15c829d122
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="35598-102">DNS の概要-Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="35598-102">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35598-103">_**トピックの最終更新日:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="35598-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="35598-104">Lync Server 2013 へのリモートアクセスの DNS レコードの要件は、証明書とポートの場合と比べて非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="35598-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="35598-105">また、Lync 2013 を実行しているクライアントを構成する方法と、フェデレーションを有効にするかどうかに応じて、多くのレコードがオプションになります。</span><span class="sxs-lookup"><span data-stu-id="35598-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="35598-106">Lync 2013 DNS の要件の詳細については、「 [Lync Server 2013 の dns 要件を決定](lync-server-2013-determine-dns-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35598-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="35598-107">スプリットブレイン DNS が構成されていない場合の Lync 2013 クライアントの自動構成の構成の詳細については、「 [Lync Server 2013 の DNS 要件を決定](lync-server-2013-determine-dns-requirements.md)する」の「スプリットブレイン dns なしの自動構成」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35598-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="35598-108">次の表に、単一統合エッジ トポロジの図に示される単一統合エッジ トポロジのサポートに必要な DNS レコードの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="35598-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="35598-109">特定の DNS レコードは、Lync 2013 クライアントの自動構成にのみ必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="35598-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="35598-110">グループポリシーオブジェクト (Gpo) を使用して Lync クライアントを構成することを計画している場合は、関連付けられたレコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="35598-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="35598-111">重要: エッジサーバーのネットワークアダプターの要件</span><span class="sxs-lookup"><span data-stu-id="35598-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="35598-112">ルーティングに関する問題を回避するには、エッジサーバーに少なくとも2つのネットワークアダプターがあり、既定のゲートウェイが、外部インターフェイスに関連付けられているネットワークアダプター上でのみ設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="35598-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="35598-113">たとえば、拡張統合エッジシナリオの図のように、[拡張統合エッジ、パブリック IP アドレスを使用した DNS 負荷分散の場合、Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)では、既定のゲートウェイが外部ファイアウォールをポイントすることになります。</span><span class="sxs-lookup"><span data-stu-id="35598-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="35598-114">それぞれのエッジ サーバーでは、2 つのネットワーク アダプターを次のように構成できます。</span><span class="sxs-lookup"><span data-stu-id="35598-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="35598-115">**ネットワーク アダプター 1 - ノード 1 (内部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="35598-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="35598-116">172.25.33.10 が割り当てられた内部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="35598-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="35598-117">デフォルト ゲートウェイは定義されていません。</span><span class="sxs-lookup"><span data-stu-id="35598-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="35598-118">Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバーが含まれるネットワーク (たとえば、172.25.33.0 から 192.168.10.0) に、エッジの内部インターフェイスを含むネットワークからのルートがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="35598-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="35598-119">**ネットワーク アダプター 1 - ノード 2 (内部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="35598-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="35598-120">172.25.33.11 が割り当てられた内部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="35598-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="35598-121">デフォルト ゲートウェイは定義されません。</span><span class="sxs-lookup"><span data-stu-id="35598-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="35598-122">Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバーが含まれるネットワーク (たとえば、172.25.33.0 から 192.168.10.0) に、エッジの内部インターフェイスを含むネットワークからのルートがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="35598-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="35598-123">**ネットワーク アダプター 2 ノード 1 (外部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="35598-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="35598-124">このネットワークアダプターには3つのプライベート IP アドレスが割り当てられます。たとえば、アクセスエッジサービスの131.107.155.10、Web 会議エッジサービスの131.107.155.20、音声ビデオエッジサービスの 131.107.155.30) のようになります。</span><span class="sxs-lookup"><span data-stu-id="35598-124">Three private IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <span data-ttu-id="35598-125">アクセスエッジサービスのパブリック IP アドレスは、デフォルトゲートウェイをパブリックルーター (131.107.155.1) に設定したプライマリアドレスです。</span><span class="sxs-lookup"><span data-stu-id="35598-125">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="35598-126">Web 会議エッジサービスおよび音声ビデオエッジサービスのプライベート IP アドレスは、Windows Server の**ローカルエリア接続プロパティ**の**インターネットプロトコルバージョン 4 (tcp/IPv4)** および**インターネットプロトコルバージョン 6 (tcp/IPv6)** のプロパティの **[詳細設定**] セクションにある追加の ip アドレスです。</span><span class="sxs-lookup"><span data-stu-id="35598-126">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="35598-127">お勧めはできませんが、3 つのエッジ サービス インターフェイスすべてに 1 つの IP アドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="35598-127">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="35598-128">これによって IP アドレスを節約できますが、サービスごとに異なるポート番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="35598-128">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="35598-129">既定のポート番号は 443/TCP で、リモート ファイアウォールの大部分がトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="35598-129">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="35598-130">アクセスエッジサービスのポート値 (たとえば、アクセスエッジサービスの 5061/TCP、Web 会議エッジサービスの 444/tcp、および音声ビデオエッジサービスの 443/TCP) を変更すると、遅延しているファイアウォールが 5061/TCP および 444/TCP 経由のトラフィックを許可しないリモートユーザーに対して問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35598-130">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="35598-131">また、3 つの異なる IP アドレスを使用すると、IP アドレスのフィルター処理が可能になるのでトラブルシューティングが容易になります。</span><span class="sxs-lookup"><span data-stu-id="35598-131">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>

  - <span data-ttu-id="35598-132">**ネットワーク アダプター 2 ノード 2 (外部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="35598-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="35598-133">このネットワークアダプターには3つのプライベート IP アドレスが割り当てられます。たとえば、アクセスエッジサービスの131.107.155.11、Web 会議エッジサービスのます (たとえば、音声ビデオエッジサービスの 131.107.155.31) のようになります。</span><span class="sxs-lookup"><span data-stu-id="35598-133">Three private IP addresses are assigned to this network adapter, for example 131.107.155.11 for Access Edge service, 131.107.155.21 for Web Conferencing Edge service, 131.107.155.31 for A/V Edge service.</span></span>
    
    <span data-ttu-id="35598-134">アクセスエッジサービスのパブリック IP アドレスは、デフォルトゲートウェイをパブリックルーター (131.107.155.1) に設定したプライマリアドレスです。</span><span class="sxs-lookup"><span data-stu-id="35598-134">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="35598-135">Web 会議エッジサービスおよび音声ビデオエッジサービスのプライベート IP アドレスは、Windows Server の**ローカルエリア接続プロパティ**の**インターネットプロトコルバージョン 4 (tcp/IPv4)** および**インターネットプロトコルバージョン 6 (tcp/IPv6)** のプロパティの **[詳細設定**] セクションにある追加の ip アドレスです。</span><span class="sxs-lookup"><span data-stu-id="35598-135">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="35598-136">2つのネットワークアダプターを使用してエッジサーバーを構成するには、2つのオプションのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="35598-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="35598-137">もう1つの方法は、エッジサーバーの内部側と外部側に3つのネットワークアダプターを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="35598-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="35598-138">このオプションの主な利点は、エッジサーバーサービスごとに別個のネットワークアダプターがあり、トラブルシューティングを行う際により簡潔なデータ収集を行うことができるということです。</span><span class="sxs-lookup"><span data-stu-id="35598-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a><span data-ttu-id="35598-139">拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散に必要な DNS レコード (例)</span><span class="sxs-lookup"><span data-stu-id="35598-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35598-140">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="35598-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="35598-141">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="35598-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="35598-142">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="35598-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="35598-143">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="35598-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35598-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="35598-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="35598-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="35598-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35598-146">131.107.155.10 および 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="35598-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="35598-147">アクセスエッジサービスの外部インターフェイス (Contoso) は、Lync が有効なユーザーを持つすべての SIP ドメインについて必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="35598-147">Access Edge service external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35598-148">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="35598-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="35598-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="35598-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35598-150">131.107.155.20 および 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="35598-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="35598-151">Web 会議エッジサービスの外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35598-151">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35598-152">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="35598-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="35598-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="35598-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35598-154">131.107.155.30 および 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="35598-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="35598-155">音声ビデオエッジサービスの外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35598-155">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35598-156">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="35598-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="35598-157">_sip の _tls</span><span class="sxs-lookup"><span data-stu-id="35598-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35598-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="35598-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35598-159">アクセスエッジサービスの外部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="35598-159">Access Edge service external interface.</span></span> <span data-ttu-id="35598-160">Lync 2013 および Lync 2010 クライアントを外部で動作するように自動構成するために必要です。</span><span class="sxs-lookup"><span data-stu-id="35598-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="35598-161">必要に応じて、Lync が有効なユーザーのいるすべての SIP ドメインに対して繰り返します。</span><span class="sxs-lookup"><span data-stu-id="35598-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35598-162">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="35598-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="35598-163">_sipfederationtls の _tcp</span><span class="sxs-lookup"><span data-stu-id="35598-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35598-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="35598-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35598-165">"許可済み SIP ドメイン" (以前のリリースでは拡張フェデレーションと呼ばれました) と呼ばれるフェデレーションパートナーの自動 DNS 検出に必要なアクセスエッジサービスの外部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="35598-165">Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="35598-166">すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="35598-166">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35598-167">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="35598-167">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="35598-168">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="35598-168">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="35598-169">172.25.33.10 および 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="35598-169">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="35598-170">統合エッジ内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35598-170">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="35598-171">フェデレーションに必要なレコード</span><span class="sxs-lookup"><span data-stu-id="35598-171">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35598-172">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="35598-172">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="35598-173">FQDN</span><span class="sxs-lookup"><span data-stu-id="35598-173">FQDN</span></span></th>
<th><span data-ttu-id="35598-174">IP アドレス/FQDN ホスト レコード</span><span class="sxs-lookup"><span data-stu-id="35598-174">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="35598-175">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="35598-175">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35598-176">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="35598-176">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="35598-177">_sipfederationtls の _tcp</span><span class="sxs-lookup"><span data-stu-id="35598-177">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35598-178">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="35598-178">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35598-179">他の潜在的フェデレーションパートナーへのフェデレーションの自動 DNS 検出に必要な SIP アクセスエッジサービスの外部インターフェイス (以前のリリースでは拡張フェデレーションと呼ばれます) と呼ばれる、"許可された SIP ドメイン" と呼ばれるものです。</span><span class="sxs-lookup"><span data-stu-id="35598-179">SIP Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="35598-180">プッシュ通知サービスまたは Apple プッシュ通知サービスのいずれかを使用する Lync が有効なユーザーと Microsoft Lync モバイルクライアントを含むすべての SIP ドメインについて、必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="35598-180">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="35598-181">XMPP の DNS の概要</span><span class="sxs-lookup"><span data-stu-id="35598-181">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35598-182">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="35598-182">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="35598-183">FQDN</span><span class="sxs-lookup"><span data-stu-id="35598-183">FQDN</span></span></th>
<th><span data-ttu-id="35598-184">IP アドレス/FQDN ホスト レコード</span><span class="sxs-lookup"><span data-stu-id="35598-184">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="35598-185">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="35598-185">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35598-186">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="35598-186">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="35598-187">_xmpp-サーバーの _tcp</span><span class="sxs-lookup"><span data-stu-id="35598-187">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35598-188">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="35598-188">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35598-189">アクセスエッジサービスまたはエッジプール上の XMPP プロキシの外部インターフェイス。すべての内部 SIP ドメインについて必要に応じて、グローバルポリシー、ユーザーが配置されているサイトポリシー、またはユーザーポリシーを使用して、外部アクセスポリシーを構成することにより、Lync が有効なユーザー。</span><span class="sxs-lookup"><span data-stu-id="35598-189">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="35598-190">許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35598-190">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="35598-191">詳細については、 <strong>「</strong>関連項目」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35598-191">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35598-192">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="35598-192">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="35598-193">xmpp.contoso.com (例)</span><span class="sxs-lookup"><span data-stu-id="35598-193">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="35598-194">XMPP プロキシをホストしているエッジサーバーまたはエッジプールのアクセスエッジサービスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="35598-194">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="35598-195">XMPP プロキシサービスをホストするアクセスエッジサービスまたはエッジプールを指します。</span><span class="sxs-lookup"><span data-stu-id="35598-195">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="35598-196">通常、作成する SRV レコードはこのホスト (A または AAAA) レコードを指し示します。</span><span class="sxs-lookup"><span data-stu-id="35598-196">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

