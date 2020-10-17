---
title: 'Lync Server 2013: DNS の概要-拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 269d5a687baba53ed0bd60d4854b79643f23f0e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532124"
---
# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="63b2a-102">DNS の概要-Lync Server 2013 での NAT を使用したプライベート IP アドレスを使用した拡張統合エッジ、DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="63b2a-102">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63b2a-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="63b2a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="63b2a-104">Lync Server 2013 へのリモートアクセスの DNS レコードの要件は、証明書とポートの場合と比べて非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="63b2a-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="63b2a-105">また、Lync 2013 を実行しているクライアントを構成する方法と、フェデレーションを有効にするかどうかに応じて、多くのレコードがオプションになります。</span><span class="sxs-lookup"><span data-stu-id="63b2a-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="63b2a-106">Lync 2013 DNS の要件の詳細については、「 [Lync Server 2013 の dns 要件を決定](lync-server-2013-determine-dns-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b2a-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="63b2a-107">スプリットブレイン DNS が構成されていない場合の Lync 2013 クライアントの自動構成の構成の詳細については、「 [Lync Server 2013 の DNS 要件を決定](lync-server-2013-determine-dns-requirements.md)する」の「スプリットブレイン dns なしの自動構成」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b2a-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="63b2a-108">次の表に、単一統合エッジ トポロジの図に示される単一統合エッジ トポロジのサポートに必要な DNS レコードの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="63b2a-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="63b2a-109">特定の DNS レコードは、Lync 2013 クライアントの自動構成にのみ必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="63b2a-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="63b2a-110">グループポリシーオブジェクト (Gpo) を使用して Lync クライアントを構成することを計画している場合は、関連付けられたレコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="63b2a-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="63b2a-111">重要: エッジサーバーのネットワークアダプターの要件</span><span class="sxs-lookup"><span data-stu-id="63b2a-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="63b2a-112">ルーティングに関する問題を回避するには、エッジサーバーに少なくとも2つのネットワークアダプターがあり、既定のゲートウェイが、外部インターフェイスに関連付けられているネットワークアダプター上でのみ設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63b2a-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="63b2a-113">たとえば、拡張統合エッジシナリオ図では、 [拡張統合エッジ、Lync Server 2013 の NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)では、既定のゲートウェイが外部ファイアウォールを指しています。</span><span class="sxs-lookup"><span data-stu-id="63b2a-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="63b2a-114">それぞれのエッジ サーバーでは、2 つのネットワーク アダプターを次のように構成できます。</span><span class="sxs-lookup"><span data-stu-id="63b2a-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="63b2a-115">**ネットワーク アダプター 1 - ノード 1 (内部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="63b2a-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="63b2a-116">172.25.33.10 が割り当てられた内部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="63b2a-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="63b2a-117">デフォルト ゲートウェイは定義されません。</span><span class="sxs-lookup"><span data-stu-id="63b2a-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="63b2a-118">Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバーが含まれるネットワーク (たとえば、172.25.33.0 から 192.168.10.0) に、エッジの内部インターフェイスを含むネットワークからのルートがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63b2a-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="63b2a-119">**ネットワーク アダプター 1 - ノード 2 (内部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="63b2a-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="63b2a-120">172.25.33.11 が割り当てられた内部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="63b2a-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="63b2a-121">デフォルト ゲートウェイは定義されません。</span><span class="sxs-lookup"><span data-stu-id="63b2a-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="63b2a-122">Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバーが含まれるネットワーク (たとえば、172.25.33.0 から 192.168.10.0) に、エッジの内部インターフェイスを含むネットワークからのルートがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63b2a-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="63b2a-123">**ネットワーク アダプター 2 ノード 1 (外部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="63b2a-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="63b2a-124">このネットワーク アダプターには、3 つのプライベート IP アドレスが割り当てられます。たとえば、アクセス エッジには 10.45.16.10、Web 会議エッジには 10.45.16.20、音声ビデオ エッジには 10.45.16.30 です。</span><span class="sxs-lookup"><span data-stu-id="63b2a-124">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63b2a-p104">推奨の方法ではありませんが、単一の IP アドレスを 3 つのエッジ サービス インターフェイスすべてで使用することもできます。この方法は IP アドレスの節約にはなりますが、サービスごとにポート番号を変える必要があります。既定のポート番号は 443/TCP で、この場合にはほとんどのリモート ファイアウォールでトラフィックが許可されます。ポート番号を変更し、たとえばアクセス エッジは 5061/TCP、Web 会議エッジは 444/TCP、音声ビデオ エッジは 443/TCP に変えた場合、5061/TCP と 444/TCP のトラフィックを許可しないファイアウォールを使用しているリモート ユーザーで問題が生じる可能性があります。また、3 つの IP アドレスを別個に使用すると、IP アドレスによるフィルターを行えるため、トラブルシューティングも簡単になります。</span><span class="sxs-lookup"><span data-stu-id="63b2a-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="63b2a-130">アクセス エッジのパブリック IP アドレスは、デフォルト ゲートウェイを統合ルーター (10.45.16.1) に設定した、プライマリ アドレスです。</span><span class="sxs-lookup"><span data-stu-id="63b2a-130">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="63b2a-131">Web 会議と音声ビデオ エッジのプライベート IP アドレスは、Windows Server の [**ローカル エリアの接続プロパティ**] で [**インターネット プロトコル バージョン 4 (TCP/IPv4)**] と [**インターネット プロトコル バージョン 6 (TCP/IPv6)**] のプロパティの [**詳細設定**] セクションにある追加の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="63b2a-131">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="63b2a-132">**ネットワーク アダプター 2 ノード 2 (外部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="63b2a-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="63b2a-133">このネットワーク アダプターには、3 つのプライベート IP アドレスが割り当てられます。たとえば、アクセス エッジには 10.45.16.11、Web 会議エッジには 10.45.16.21、音声ビデオ エッジには 10.45.16.31 です。</span><span class="sxs-lookup"><span data-stu-id="63b2a-133">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="63b2a-134">アクセス エッジのパブリック IP アドレスは、デフォルト ゲートウェイを統合ルーター (10.45.16.1) に設定した、プライマリ アドレスです。</span><span class="sxs-lookup"><span data-stu-id="63b2a-134">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="63b2a-135">Web 会議と音声ビデオ エッジのプライベート IP アドレスは、Windows Server の [**ローカル エリアの接続プロパティ**] で [**インターネット プロトコル バージョン 4 (TCP/IPv4)**] と [**インターネット プロトコル バージョン 6 (TCP/IPv6)**] のプロパティの [**詳細設定**] セクションにある追加の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="63b2a-135">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="63b2a-136">2つのネットワークアダプターを使用してエッジサーバーを構成するには、2つのオプションのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="63b2a-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="63b2a-137">もう1つの方法は、エッジサーバーの内部側と外部側に3つのネットワークアダプターを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="63b2a-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="63b2a-138">このオプションの主な利点は、エッジサーバーサービスごとに別個のネットワークアダプターがあり、トラブルシューティングを行う際により簡潔なデータ収集を行うことができるということです。</span><span class="sxs-lookup"><span data-stu-id="63b2a-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="63b2a-139">拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散に必要な DNS レコード (例)</span><span class="sxs-lookup"><span data-stu-id="63b2a-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63b2a-140">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="63b2a-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="63b2a-141">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="63b2a-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="63b2a-142">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="63b2a-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="63b2a-143">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="63b2a-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63b2a-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="63b2a-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="63b2a-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63b2a-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63b2a-146">131.107.155.10 および 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="63b2a-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="63b2a-147">アクセス エッジ外部インターフェイス (Contoso)。すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="63b2a-147">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b2a-148">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="63b2a-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="63b2a-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63b2a-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63b2a-150">131.107.155.20 および 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="63b2a-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="63b2a-151">Web 会議エッジ外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63b2a-151">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b2a-152">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="63b2a-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="63b2a-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63b2a-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63b2a-154">131.107.155.30 および 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="63b2a-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="63b2a-155">音声ビデオ エッジ外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63b2a-155">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b2a-156">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="63b2a-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="63b2a-157">_sip _sip._tls</span><span class="sxs-lookup"><span data-stu-id="63b2a-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63b2a-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63b2a-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63b2a-159">アクセス エッジ外部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="63b2a-159">Access Edge external interface.</span></span> <span data-ttu-id="63b2a-160">Lync 2013 および Lync 2010 クライアントを外部で動作するように自動構成するために必要です。</span><span class="sxs-lookup"><span data-stu-id="63b2a-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="63b2a-161">必要に応じて、Lync が有効なユーザーのいるすべての SIP ドメインに対して繰り返します。</span><span class="sxs-lookup"><span data-stu-id="63b2a-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b2a-162">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="63b2a-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="63b2a-163">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="63b2a-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63b2a-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63b2a-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63b2a-p107">SIP アドレス エッジ外部インターフェイス。"許可済み SIP ドメイン" (以前のリリースでは拡張フェデレーションと呼ばれました) という名前のフェデレーション パートナーの自動 DNS 検出に必要です。すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="63b2a-p107">SIP Access Edge external interface. Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases). Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b2a-168">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="63b2a-168">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="63b2a-169">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="63b2a-169">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="63b2a-170">172.25.33.10 および 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="63b2a-170">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="63b2a-171">統合エッジ内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63b2a-171">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="63b2a-172">フェデレーションに必要なレコード</span><span class="sxs-lookup"><span data-stu-id="63b2a-172">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63b2a-173">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="63b2a-173">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="63b2a-174">FQDN</span><span class="sxs-lookup"><span data-stu-id="63b2a-174">FQDN</span></span></th>
<th><span data-ttu-id="63b2a-175">IP アドレス/FQDN ホスト レコード</span><span class="sxs-lookup"><span data-stu-id="63b2a-175">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="63b2a-176">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="63b2a-176">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63b2a-177">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="63b2a-177">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="63b2a-178">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="63b2a-178">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63b2a-179">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63b2a-179">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63b2a-180">他の潜在的フェデレーション パートナーによるフェデレーションの自動 DNS 検出に必要な SIP アクセス エッジ外部インターフェイス。"許可済み SIP ドメイン" (以前のリリースでは拡張フェデレーションと呼ばれていました) と呼ばれます。すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="63b2a-180">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="63b2a-181">この SRV レコードは、モビリティおよびプッシュ通知決済機関に必要です</span><span class="sxs-lookup"><span data-stu-id="63b2a-181">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="63b2a-182">DNS の概要 - パブリック インスタント メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="63b2a-182">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63b2a-183">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="63b2a-183">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="63b2a-184">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="63b2a-184">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="63b2a-185">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="63b2a-185">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="63b2a-186">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="63b2a-186">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63b2a-187">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="63b2a-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="63b2a-188">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63b2a-188">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63b2a-189">アクセスエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="63b2a-189">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="63b2a-190">アクセス エッジ外部インターフェイス (Contoso)。すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="63b2a-190">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="63b2a-191">XMPP の DNS の概要</span><span class="sxs-lookup"><span data-stu-id="63b2a-191">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63b2a-192">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="63b2a-192">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="63b2a-193">FQDN</span><span class="sxs-lookup"><span data-stu-id="63b2a-193">FQDN</span></span></th>
<th><span data-ttu-id="63b2a-194">IP アドレス/FQDN ホスト レコード</span><span class="sxs-lookup"><span data-stu-id="63b2a-194">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="63b2a-195">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="63b2a-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63b2a-196">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="63b2a-196">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="63b2a-197">_xmpp-server._tcp</span><span class="sxs-lookup"><span data-stu-id="63b2a-197">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63b2a-198">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63b2a-198">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63b2a-199">アクセスエッジサービスまたはエッジプール上の XMPP プロキシの外部インターフェイス。必要に応じて、Lync が有効になっているすべての内部 SIP ドメインについて、グローバルポリシー、ユーザーが配置されているサイトポリシー、Lync が有効なユーザーに適用されているユーザーポリシーを使用して、外部アクセスポリシーの構成を通じて、外部アクセスポリシーの構成を通じて実行できます。</span><span class="sxs-lookup"><span data-stu-id="63b2a-199">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="63b2a-200">許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63b2a-200">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="63b2a-201">詳細については、 <strong>「</strong> 関連項目」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b2a-201">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b2a-202">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="63b2a-202">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="63b2a-203">xmpp.contoso.com (例)</span><span class="sxs-lookup"><span data-stu-id="63b2a-203">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="63b2a-204">XMPP プロキシをホストしているエッジサーバーまたはエッジプールのアクセスエッジサービスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="63b2a-204">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="63b2a-205">XMPP プロキシサービスをホストするアクセスエッジサービスまたはエッジプールを指します。</span><span class="sxs-lookup"><span data-stu-id="63b2a-205">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="63b2a-206">通常、作成する SRV レコードはこのホスト (A または AAAA) レコードを指し示します。</span><span class="sxs-lookup"><span data-stu-id="63b2a-206">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

