---
title: DNS の概要-パブリック IP アドレスを使用する単一統合エッジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e0604a018b4b558612e2e2a3802ca97676b58b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501234"
---
# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="9a33f-102">DNS の概要-Lync Server 2013 でのパブリック IP アドレスを使用する単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="9a33f-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a33f-103">_**トピックの最終更新日:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="9a33f-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="9a33f-104">Lync Server 2013 へのリモートアクセスの DNS レコードの要件は、証明書とポートの場合と比べて非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="9a33f-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="9a33f-105">また、Lync 2013 を実行しているクライアントを構成する方法と、フェデレーションを有効にするかどうかに応じて、多くのレコードがオプションになります。</span><span class="sxs-lookup"><span data-stu-id="9a33f-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="9a33f-106">Lync 2013 DNS の要件の詳細については、「 [Lync Server 2013 の dns 要件を決定](lync-server-2013-determine-dns-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a33f-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="9a33f-107">スプリットブレイン DNS が構成されていない場合に、Lync 2013 を実行しているクライアントの自動構成の詳細については、「 [Lync Server 2013 の dns 要件を決定する](lync-server-2013-determine-dns-requirements.md)」の「Split-Brain dns を使用しない自動構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a33f-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="9a33f-108">次の表に、単一統合エッジ トポロジの図に示される単一統合エッジ トポロジのサポートに必要な DNS レコードの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="9a33f-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="9a33f-109">特定の DNS レコードは、Lync 2013 および Lync 2010 クライアントの自動構成にのみ必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9a33f-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="9a33f-110">グループポリシーオブジェクト (Gpo) を使用して Lync クライアントを構成することを計画している場合は、関連付けられている自動構成レコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9a33f-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="9a33f-111">重要: エッジサーバーのネットワークアダプターの要件</span><span class="sxs-lookup"><span data-stu-id="9a33f-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="9a33f-112">ルーティングに関する問題を回避するには、エッジサーバーに少なくとも2つのネットワークアダプターがあり、既定のゲートウェイが、外部インターフェイスに関連付けられているネットワークアダプター上でのみ設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a33f-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="9a33f-113">たとえば、パブリック ip アドレスを使用する単一の統合エッジトポロジ図に示すように、 [Lync Server 2013 のパブリック ip アドレスを使用する単一統合エッジ](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)トポロジでは、既定のゲートウェイは、パブリック ip アドレスを提供できるインターネット境界またはファイアウォールの外部ルーターを指します。</span><span class="sxs-lookup"><span data-stu-id="9a33f-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="9a33f-114">エッジサーバーインターフェイスのネットワーク関係は、NAT 関係ではなくルート関係です。</span><span class="sxs-lookup"><span data-stu-id="9a33f-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="9a33f-115">エッジ サーバーの 2 つのネットワーク アダプターは、次のように構成できます。</span><span class="sxs-lookup"><span data-stu-id="9a33f-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="9a33f-116">**ネットワーク アダプター 1 (内部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="9a33f-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="9a33f-117">172.25.33.10 が割り当てられた内部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9a33f-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="9a33f-118">デフォルト ゲートウェイは定義されません。</span><span class="sxs-lookup"><span data-stu-id="9a33f-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="9a33f-119">Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバーが含まれるネットワーク (たとえば、172.25.33.0 から 192.168.10.0) に、エッジの内部インターフェイスを含むネットワークからのルートがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a33f-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="9a33f-120">**ネットワーク アダプター 2 (外部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="9a33f-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="9a33f-121">3 つのパブリック IP アドレスがこのネットワーク アダプターに割り当てられます (例: アクセス エッジ用の 131.107.155.10、Web 会議エッジ用の 131.107.155.20、音声ビデオ用の 131.107.155.30)。</span><span class="sxs-lookup"><span data-stu-id="9a33f-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9a33f-p104">推奨はされませんが、1 つの IP アドレスを 3 つのエッジ サービス インターフェイスのすべてで使用することもできます。この場合、IP アドレスの節約になりますが、サービスごとに別々のポート番号が必要です。既定のポート番号は 443/TCP であり、このトラフィックはほとんどのリモート ファイアウォールで許可されます。ポートの各値を (たとえば) アクセス エッジ用の 5061/TCP、Web 会議エッジ用の 444/TCP、および AV エッジ用の 443/TCP に変更すると、リモート ユーザーを隔てるファイアウォールで 5061/TCP および 444/TCP 経由のトラフィックが許可されないという問題が発生する可能性があります。また、3 つの異なる IP アドレスを使用すると、IP アドレスのフィルター処理が可能になるのでトラブルシューティングが容易になります。</span><span class="sxs-lookup"><span data-stu-id="9a33f-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="9a33f-127">アクセス エッジのパブリック IP アドレスは、デフォルト ゲートウェイをパブリック ルーター (131.107.155.1) に設定した、プライマリ アドレスです。</span><span class="sxs-lookup"><span data-stu-id="9a33f-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="9a33f-128">Web 会議および A/V エッジのパブリック IP アドレスは、Windows Server の**ローカル エリアの接続プロパティ**にある **インターネット プロトコル バージョン 4 (TCP/IPv4)** および**インターネット プロトコル バージョン 6 (TCP/IPv6)** のプロパティの [**詳細**] セクションで指定される追加の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="9a33f-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="9a33f-129">2つのネットワークアダプターを使用してエッジサーバーを構成するには、2つのオプションのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="9a33f-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="9a33f-130">もう1つの方法は、エッジサーバーの内部側と外部側に3つのネットワークアダプターを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="9a33f-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="9a33f-131">このオプションの主な利点は、エッジサーバーサービスごとに別個のネットワークアダプターがあり、トラブルシューティングを行う際により簡潔なデータ収集を行うことができるということです。</span><span class="sxs-lookup"><span data-stu-id="9a33f-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="9a33f-132">パブリック IP アドレスを持つ単一統合トポロジ エッジで必要な DNS レコード (例)</span><span class="sxs-lookup"><span data-stu-id="9a33f-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a33f-133">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="9a33f-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="9a33f-134">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="9a33f-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="9a33f-135">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="9a33f-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="9a33f-136">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="9a33f-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a33f-137">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="9a33f-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9a33f-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a33f-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a33f-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="9a33f-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="9a33f-140">アクセス エッジ外部インターフェイス (Contoso)。必要に応じて、Lync が有効なユーザーのいるすべての SIP ドメインに対して繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9a33f-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a33f-141">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="9a33f-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9a33f-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a33f-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a33f-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="9a33f-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="9a33f-144">Web 会議エッジ外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a33f-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a33f-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="9a33f-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9a33f-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a33f-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a33f-147">131.107.155.30)</span><span class="sxs-lookup"><span data-stu-id="9a33f-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="9a33f-148">音声ビデオ エッジ外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a33f-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a33f-149">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="9a33f-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="9a33f-150">_sip _sip._tls</span><span class="sxs-lookup"><span data-stu-id="9a33f-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a33f-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a33f-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a33f-152">アクセス エッジ外部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9a33f-152">Access Edge external interface.</span></span> <span data-ttu-id="9a33f-153">Lync 2013 および Lync 2010 クライアントを外部で動作するように自動構成するために必要です。</span><span class="sxs-lookup"><span data-stu-id="9a33f-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="9a33f-154">必要に応じて、Lync が有効なユーザーのいるすべての SIP ドメインに対して繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9a33f-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a33f-155">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="9a33f-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="9a33f-156">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="9a33f-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a33f-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a33f-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a33f-158">SIP アクセス エッジ外部インターフェイス。"許可済み SIP ドメイン" (以前のリリースでは拡張フェデレーション) と呼ばれるフェデレーション パートナーの自動 DNS 検出で必要です。必要に応じて、Lync が有効なユーザーのいるすべての SIP ドメインに対して繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9a33f-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a33f-159">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="9a33f-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9a33f-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9a33f-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="9a33f-161">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="9a33f-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="9a33f-162">統合エッジ内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a33f-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="9a33f-163">前の表に記載されているレコードは、 <EM>.net</EM> 内線番号または <EM>.com</EM> 拡張子のどちらかを使用して表示され、スプリットブレイン DNS を使用していない場合にどの領域を含める必要があるかを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="9a33f-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="9a33f-164">スプリットブレイン DNS を使用している場合は、すべてのレコードが同一の領域にあり、内部と外部のどちらのバージョンであるかだけが区別されます。</span><span class="sxs-lookup"><span data-stu-id="9a33f-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="9a33f-165">詳細については、「 <A href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 の DNS 要件を決定する</A>」の「スプリットブレイン dns」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a33f-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="9a33f-166">フェデレーションに必要なレコード</span><span class="sxs-lookup"><span data-stu-id="9a33f-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a33f-167">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="9a33f-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="9a33f-168">FQDN</span><span class="sxs-lookup"><span data-stu-id="9a33f-168">FQDN</span></span></th>
<th><span data-ttu-id="9a33f-169">IP アドレス/FQDN ホスト レコード</span><span class="sxs-lookup"><span data-stu-id="9a33f-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="9a33f-170">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="9a33f-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a33f-171">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="9a33f-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="9a33f-172">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="9a33f-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a33f-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a33f-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a33f-174">他の潜在的フェデレーション パートナーによるフェデレーションの自動 DNS 検出に必要な SIP アクセス エッジ外部インターフェイス。"許可済み SIP ドメイン" (以前のリリースでは拡張フェデレーションと呼ばれていました) と呼ばれます。すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9a33f-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="9a33f-175">この SRV レコードは、モビリティおよびプッシュ通知決済機関に必要です</span><span class="sxs-lookup"><span data-stu-id="9a33f-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="9a33f-176">XMPP の DNS の概要</span><span class="sxs-lookup"><span data-stu-id="9a33f-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a33f-177">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="9a33f-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="9a33f-178">FQDN</span><span class="sxs-lookup"><span data-stu-id="9a33f-178">FQDN</span></span></th>
<th><span data-ttu-id="9a33f-179">IP アドレス/FQDN ホスト レコード</span><span class="sxs-lookup"><span data-stu-id="9a33f-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="9a33f-180">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="9a33f-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a33f-181">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="9a33f-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="9a33f-182">_xmpp-server._tcp</span><span class="sxs-lookup"><span data-stu-id="9a33f-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a33f-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a33f-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9a33f-184">アクセスエッジサービスまたはエッジプール上の XMPP プロキシの外部インターフェイス。必要に応じて、Lync が有効になっているすべての内部 SIP ドメインについて、グローバルポリシー、ユーザーが配置されているサイトポリシー、Lync が有効なユーザーに適用されているユーザーポリシーを使用して、外部アクセスポリシーの構成を通じて、外部アクセスポリシーの構成を通じて実行できます。</span><span class="sxs-lookup"><span data-stu-id="9a33f-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="9a33f-185">許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a33f-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="9a33f-186">詳細については、 <strong>「</strong> 関連項目」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a33f-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a33f-187">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="9a33f-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9a33f-188">xmpp.contoso.com (例)</span><span class="sxs-lookup"><span data-stu-id="9a33f-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="9a33f-189">XMPP プロキシをホストしているエッジサーバーまたはエッジプールのアクセスエッジサービスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="9a33f-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="9a33f-190">XMPP プロキシサービスをホストするアクセスエッジサービスまたはエッジプールを指します。</span><span class="sxs-lookup"><span data-stu-id="9a33f-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="9a33f-191">通常、作成する SRV レコードはこのホスト (A または AAAA) レコードを指し示します。</span><span class="sxs-lookup"><span data-stu-id="9a33f-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

