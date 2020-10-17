---
title: 'Lync Server 2013: DNS の概要-拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散'
description: 'Lync Server 2013: DNS の概要-拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散。'
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
ms.openlocfilehash: 2eef3029323c1c2f798fddc721df832a932524c8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559403"
---
# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="4c02e-103">DNS の概要-Lync Server 2013 での NAT を使用したプライベート IP アドレスを使用した拡張統合エッジ、DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="4c02e-103">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c02e-104">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="4c02e-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="4c02e-105">Lync Server 2013 へのリモートアクセスの DNS レコードの要件は、証明書とポートの場合と比べて非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="4c02e-105">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="4c02e-106">また、Lync 2013 を実行しているクライアントを構成する方法と、フェデレーションを有効にするかどうかに応じて、多くのレコードがオプションになります。</span><span class="sxs-lookup"><span data-stu-id="4c02e-106">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="4c02e-107">Lync 2013 DNS の要件の詳細については、「 [Lync Server 2013 の dns 要件を決定](lync-server-2013-determine-dns-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c02e-107">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="4c02e-108">スプリットブレイン DNS が構成されていない場合の Lync 2013 クライアントの自動構成の構成の詳細については、「 [Lync Server 2013 の DNS 要件を決定](lync-server-2013-determine-dns-requirements.md)する」の「スプリットブレイン dns なしの自動構成」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c02e-108">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="4c02e-109">次の表に、単一統合エッジ トポロジの図に示される単一統合エッジ トポロジのサポートに必要な DNS レコードの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="4c02e-109">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="4c02e-110">特定の DNS レコードは、Lync 2013 クライアントの自動構成にのみ必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4c02e-110">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="4c02e-111">グループポリシーオブジェクト (Gpo) を使用して Lync クライアントを構成することを計画している場合は、関連付けられたレコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4c02e-111">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="4c02e-112">重要: エッジサーバーのネットワークアダプターの要件</span><span class="sxs-lookup"><span data-stu-id="4c02e-112">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="4c02e-113">ルーティングに関する問題を回避するには、エッジサーバーに少なくとも2つのネットワークアダプターがあり、既定のゲートウェイが、外部インターフェイスに関連付けられているネットワークアダプター上でのみ設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c02e-113">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="4c02e-114">たとえば、拡張統合エッジシナリオ図では、 [拡張統合エッジ、Lync Server 2013 の NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)では、既定のゲートウェイが外部ファイアウォールを指しています。</span><span class="sxs-lookup"><span data-stu-id="4c02e-114">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="4c02e-115">それぞれのエッジ サーバーでは、2 つのネットワーク アダプターを次のように構成できます。</span><span class="sxs-lookup"><span data-stu-id="4c02e-115">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="4c02e-116">**ネットワーク アダプター 1 - ノード 1 (内部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="4c02e-116">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="4c02e-117">172.25.33.10 が割り当てられた内部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="4c02e-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="4c02e-118">デフォルト ゲートウェイは定義されません。</span><span class="sxs-lookup"><span data-stu-id="4c02e-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="4c02e-119">Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバーが含まれるネットワーク (たとえば、172.25.33.0 から 192.168.10.0) に、エッジの内部インターフェイスを含むネットワークからのルートがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c02e-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="4c02e-120">**ネットワーク アダプター 1 - ノード 2 (内部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="4c02e-120">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="4c02e-121">172.25.33.11 が割り当てられた内部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="4c02e-121">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="4c02e-122">デフォルト ゲートウェイは定義されません。</span><span class="sxs-lookup"><span data-stu-id="4c02e-122">No default gateway is defined.</span></span>
    
    <span data-ttu-id="4c02e-123">Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバーが含まれるネットワーク (たとえば、172.25.33.0 から 192.168.10.0) に、エッジの内部インターフェイスを含むネットワークからのルートがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c02e-123">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="4c02e-124">**ネットワーク アダプター 2 ノード 1 (外部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="4c02e-124">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="4c02e-125">このネットワーク アダプターには、3 つのプライベート IP アドレスが割り当てられます。たとえば、アクセス エッジには 10.45.16.10、Web 会議エッジには 10.45.16.20、音声ビデオ エッジには 10.45.16.30 です。</span><span class="sxs-lookup"><span data-stu-id="4c02e-125">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4c02e-p104">推奨の方法ではありませんが、単一の IP アドレスを 3 つのエッジ サービス インターフェイスすべてで使用することもできます。この方法は IP アドレスの節約にはなりますが、サービスごとにポート番号を変える必要があります。既定のポート番号は 443/TCP で、この場合にはほとんどのリモート ファイアウォールでトラフィックが許可されます。ポート番号を変更し、たとえばアクセス エッジは 5061/TCP、Web 会議エッジは 444/TCP、音声ビデオ エッジは 443/TCP に変えた場合、5061/TCP と 444/TCP のトラフィックを許可しないファイアウォールを使用しているリモート ユーザーで問題が生じる可能性があります。また、3 つの IP アドレスを別個に使用すると、IP アドレスによるフィルターを行えるため、トラブルシューティングも簡単になります。</span><span class="sxs-lookup"><span data-stu-id="4c02e-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="4c02e-131">アクセス エッジのパブリック IP アドレスは、デフォルト ゲートウェイを統合ルーター (10.45.16.1) に設定した、プライマリ アドレスです。</span><span class="sxs-lookup"><span data-stu-id="4c02e-131">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="4c02e-132">Web 会議と音声ビデオ エッジのプライベート IP アドレスは、Windows Server の [**ローカル エリアの接続プロパティ**] で [**インターネット プロトコル バージョン 4 (TCP/IPv4)**] と [**インターネット プロトコル バージョン 6 (TCP/IPv6)**] のプロパティの [**詳細設定**] セクションにある追加の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="4c02e-132">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="4c02e-133">**ネットワーク アダプター 2 ノード 2 (外部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="4c02e-133">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="4c02e-134">このネットワーク アダプターには、3 つのプライベート IP アドレスが割り当てられます。たとえば、アクセス エッジには 10.45.16.11、Web 会議エッジには 10.45.16.21、音声ビデオ エッジには 10.45.16.31 です。</span><span class="sxs-lookup"><span data-stu-id="4c02e-134">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="4c02e-135">アクセス エッジのパブリック IP アドレスは、デフォルト ゲートウェイを統合ルーター (10.45.16.1) に設定した、プライマリ アドレスです。</span><span class="sxs-lookup"><span data-stu-id="4c02e-135">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="4c02e-136">Web 会議と音声ビデオ エッジのプライベート IP アドレスは、Windows Server の [**ローカル エリアの接続プロパティ**] で [**インターネット プロトコル バージョン 4 (TCP/IPv4)**] と [**インターネット プロトコル バージョン 6 (TCP/IPv6)**] のプロパティの [**詳細設定**] セクションにある追加の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="4c02e-136">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4c02e-137">2つのネットワークアダプターを使用してエッジサーバーを構成するには、2つのオプションのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c02e-137">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="4c02e-138">もう1つの方法は、エッジサーバーの内部側と外部側に3つのネットワークアダプターを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="4c02e-138">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="4c02e-139">このオプションの主な利点は、エッジサーバーサービスごとに別個のネットワークアダプターがあり、トラブルシューティングを行う際により簡潔なデータ収集を行うことができるということです。</span><span class="sxs-lookup"><span data-stu-id="4c02e-139">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="4c02e-140">拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散に必要な DNS レコード (例)</span><span class="sxs-lookup"><span data-stu-id="4c02e-140">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c02e-141">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="4c02e-141">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4c02e-142">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="4c02e-142">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="4c02e-143">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="4c02e-143">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="4c02e-144">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="4c02e-144">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c02e-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="4c02e-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4c02e-146">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c02e-146">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4c02e-147">131.107.155.10 および 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="4c02e-147">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="4c02e-148">アクセス エッジ外部インターフェイス (Contoso)。すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4c02e-148">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c02e-149">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="4c02e-149">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4c02e-150">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c02e-150">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4c02e-151">131.107.155.20 および 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="4c02e-151">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="4c02e-152">Web 会議エッジ外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c02e-152">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c02e-153">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="4c02e-153">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4c02e-154">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c02e-154">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4c02e-155">131.107.155.30 および 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="4c02e-155">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="4c02e-156">音声ビデオ エッジ外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c02e-156">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c02e-157">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="4c02e-157">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="4c02e-158">_sip _sip._tls</span><span class="sxs-lookup"><span data-stu-id="4c02e-158">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4c02e-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c02e-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4c02e-160">アクセス エッジ外部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="4c02e-160">Access Edge external interface.</span></span> <span data-ttu-id="4c02e-161">Lync 2013 および Lync 2010 クライアントを外部で動作するように自動構成するために必要です。</span><span class="sxs-lookup"><span data-stu-id="4c02e-161">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="4c02e-162">必要に応じて、Lync が有効なユーザーのいるすべての SIP ドメインに対して繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4c02e-162">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c02e-163">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="4c02e-163">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="4c02e-164">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="4c02e-164">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4c02e-165">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c02e-165">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4c02e-p107">SIP アドレス エッジ外部インターフェイス。"許可済み SIP ドメイン" (以前のリリースでは拡張フェデレーションと呼ばれました) という名前のフェデレーション パートナーの自動 DNS 検出に必要です。すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4c02e-p107">SIP Access Edge external interface. Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases). Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c02e-169">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="4c02e-169">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4c02e-170">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4c02e-170">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="4c02e-171">172.25.33.10 および 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="4c02e-171">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="4c02e-172">統合エッジ内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c02e-172">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="4c02e-173">フェデレーションに必要なレコード</span><span class="sxs-lookup"><span data-stu-id="4c02e-173">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c02e-174">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="4c02e-174">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4c02e-175">FQDN</span><span class="sxs-lookup"><span data-stu-id="4c02e-175">FQDN</span></span></th>
<th><span data-ttu-id="4c02e-176">IP アドレス/FQDN ホスト レコード</span><span class="sxs-lookup"><span data-stu-id="4c02e-176">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="4c02e-177">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="4c02e-177">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c02e-178">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="4c02e-178">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="4c02e-179">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="4c02e-179">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4c02e-180">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c02e-180">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4c02e-181">他の潜在的フェデレーション パートナーによるフェデレーションの自動 DNS 検出に必要な SIP アクセス エッジ外部インターフェイス。"許可済み SIP ドメイン" (以前のリリースでは拡張フェデレーションと呼ばれていました) と呼ばれます。すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4c02e-181">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="4c02e-182">この SRV レコードは、モビリティおよびプッシュ通知決済機関に必要です</span><span class="sxs-lookup"><span data-stu-id="4c02e-182">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="4c02e-183">DNS の概要 - パブリック インスタント メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="4c02e-183">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c02e-184">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="4c02e-184">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4c02e-185">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="4c02e-185">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="4c02e-186">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="4c02e-186">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="4c02e-187">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="4c02e-187">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c02e-188">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="4c02e-188">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4c02e-189">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c02e-189">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4c02e-190">アクセスエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c02e-190">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4c02e-191">アクセス エッジ外部インターフェイス (Contoso)。すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4c02e-191">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="4c02e-192">XMPP の DNS の概要</span><span class="sxs-lookup"><span data-stu-id="4c02e-192">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c02e-193">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="4c02e-193">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4c02e-194">FQDN</span><span class="sxs-lookup"><span data-stu-id="4c02e-194">FQDN</span></span></th>
<th><span data-ttu-id="4c02e-195">IP アドレス/FQDN ホスト レコード</span><span class="sxs-lookup"><span data-stu-id="4c02e-195">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="4c02e-196">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="4c02e-196">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c02e-197">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="4c02e-197">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="4c02e-198">_xmpp-server._tcp</span><span class="sxs-lookup"><span data-stu-id="4c02e-198">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4c02e-199">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c02e-199">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4c02e-200">アクセスエッジサービスまたはエッジプール上の XMPP プロキシの外部インターフェイス。必要に応じて、Lync が有効になっているすべての内部 SIP ドメインについて、グローバルポリシー、ユーザーが配置されているサイトポリシー、Lync が有効なユーザーに適用されているユーザーポリシーを使用して、外部アクセスポリシーの構成を通じて、外部アクセスポリシーの構成を通じて実行できます。</span><span class="sxs-lookup"><span data-stu-id="4c02e-200">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="4c02e-201">許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c02e-201">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="4c02e-202">詳細については、 <strong>「</strong> 関連項目」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c02e-202">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c02e-203">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="4c02e-203">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4c02e-204">xmpp.contoso.com (例)</span><span class="sxs-lookup"><span data-stu-id="4c02e-204">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="4c02e-205">XMPP プロキシをホストしているエッジサーバーまたはエッジプールのアクセスエッジサービスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4c02e-205">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="4c02e-206">XMPP プロキシサービスをホストするアクセスエッジサービスまたはエッジプールを指します。</span><span class="sxs-lookup"><span data-stu-id="4c02e-206">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="4c02e-207">通常、作成する SRV レコードはこのホスト (A または AAAA) レコードを指し示します。</span><span class="sxs-lookup"><span data-stu-id="4c02e-207">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

