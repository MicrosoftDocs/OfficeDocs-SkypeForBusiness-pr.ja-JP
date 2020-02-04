---
title: DNS の概要 - 拡張統合エッジ (ロード バランサー機器を使用)
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
ms.openlocfilehash: c6be703e13ec50eb66ba52c981196df06adc6e5b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="1d051-102">DNS の概要 - Lync Server 2013 の拡張統合エッジ (ロード バランサー機器を使用)</span><span class="sxs-lookup"><span data-stu-id="1d051-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d051-103">_**最終更新日:** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="1d051-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="1d051-104">Lync Server 2013 へのリモートアクセスの DNS レコード要件は、証明書やポートの場合と非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="1d051-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="1d051-105">また、Lync 2013 を実行しているクライアントの構成方法とフェデレーションを有効にするかどうかによって、多くのレコードがオプションになります。</span><span class="sxs-lookup"><span data-stu-id="1d051-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="1d051-106">Lync 2013 DNS の要件の詳細については、「 [Lync Server 2013 の dns 要件を確認](lync-server-2013-determine-dns-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d051-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="1d051-107">Lync 2013 クライアントの自動構成の構成の詳細については、「 [Lync Server 2013 の DNS 要件を特定](lync-server-2013-determine-dns-requirements.md)する」の「スプリットブレイン dns を使わない自動構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d051-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="1d051-108">次の表には、スケーリングされた統合エッジトポロジ (ハードウェア負荷分散) 図をサポートするために必要な DNS レコードの概要が記載されています。</span><span class="sxs-lookup"><span data-stu-id="1d051-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="1d051-109">特定の DNS レコードは、Lync クライアントの自動構成の場合にのみ必須であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1d051-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="1d051-110">グループポリシーオブジェクト (Gpo) を使って Lync クライアントを構成することを計画している場合は、関連付けられたレコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1d051-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="1d051-111">重要: エッジサーバーのネットワークアダプターの要件</span><span class="sxs-lookup"><span data-stu-id="1d051-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="1d051-112">ルーティングの問題を回避するには、エッジサーバーに少なくとも2つのネットワークアダプターがあり、その外部インターフェイスに関連付けられているネットワークアダプターでのみ既定のゲートウェイが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1d051-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="1d051-113">たとえば、スケーリングされた統合エッジシナリオでは、 [Lync Server 2013 のハードウェアロードバランサーを使用したスケーリング](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)された統合エッジの図に示すように、既定のゲートウェイは外部ファイアウォールを指しています。</span><span class="sxs-lookup"><span data-stu-id="1d051-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="1d051-114">次のように、各エッジサーバーで2つのネットワークアダプターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1d051-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="1d051-115">**ネットワークアダプター 1 (内部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="1d051-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="1d051-116">172.25.33.10 が割り当てられている内部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="1d051-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="1d051-117">既定のゲートウェイがありません。</span><span class="sxs-lookup"><span data-stu-id="1d051-117">No default gateway.</span></span>
    
    <span data-ttu-id="1d051-118">Lync Server クライアントまたは Lync Server が実行されているサーバー (172.25.33.0 から192.168.10.0 など) に、エッジサーバーの内部インターフェイスが含まれているネットワークからのルートがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1d051-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="1d051-119">**ネットワークアダプター 2 (外部インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="1d051-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="1d051-120">3つのパブリック IP アドレスがこのネットワークアダプターに割り当てられます。たとえば、アクセスエッジサービスの場合は131.107.155.10、Web 会議エッジサービスの場合は131.107.155.20、A/V Edge サービスの場合は131.107.155.30。</span><span class="sxs-lookup"><span data-stu-id="1d051-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1d051-121">エッジサーバーの実際の外部ネットワークインターフェイスに割り当てられている IP アドレスは、どのハードウェアロードバランサーを選択するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1d051-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="1d051-122">実際の IP アドレス要件については、ハードウェアロードバランサーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d051-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="1d051-123">すべての3エッジサービスインターフェイスで単一の IP アドレスを使うことはできますが、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="1d051-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="1d051-124">これにより、IP アドレスが保存されますが、サービスごとに異なるポート番号が必要になります。</span><span class="sxs-lookup"><span data-stu-id="1d051-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="1d051-125">既定のポート番号は 443/TCP であり、ほとんどのリモートファイアウォールでトラフィックが許可されます。</span><span class="sxs-lookup"><span data-stu-id="1d051-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="1d051-126">ポートの値を変更する (たとえば、アクセスエッジサービスの場合は 5061/tcp、Web 会議エッジサービスの場合は 444/TCP、A/V Edge サービスの場合は、443/tcp) という問題が発生する可能性があります。これは、相手のファイアウォールによって 5061/TCP および 444/TCP 経由のトラフィックが許可されないリモート</span><span class="sxs-lookup"><span data-stu-id="1d051-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="1d051-127">さらに、3つの異なる IP アドレスで、IP アドレスをフィルター処理できるため、トラブルシューティングが容易になります。</span><span class="sxs-lookup"><span data-stu-id="1d051-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="1d051-128">アクセスエッジサービスの IP アドレスは、既定のゲートウェイがインターネットフェーシングルータ (131.107.155.1) に設定されているプライマリサーバーです。</span><span class="sxs-lookup"><span data-stu-id="1d051-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="1d051-129">Web 会議エッジサービスと A/V Edge サービス IP アドレスセカンダリ。</span><span class="sxs-lookup"><span data-stu-id="1d051-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="1d051-130">2つのネットワークアダプターでエッジサーバーを構成するには、2つのオプションのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d051-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="1d051-131">もう1つの方法として、内部側とエッジサーバーの外部側の3つのネットワークアダプター用に1つのネットワークアダプターを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="1d051-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="1d051-132">このオプションの主な利点は、Edge Server サービスごとの個別のネットワークアダプターであり、トラブルシューティングが必要な場合は、より簡潔なデータ収集を行うことです。</span><span class="sxs-lookup"><span data-stu-id="1d051-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="1d051-133">スケーリングされた統合エッジに必要な DNS レコード、ハードウェア負荷分散 (例)</span><span class="sxs-lookup"><span data-stu-id="1d051-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d051-134">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="1d051-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1d051-135">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="1d051-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="1d051-136">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="1d051-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="1d051-137">マップ先/コメント</span><span class="sxs-lookup"><span data-stu-id="1d051-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d051-138">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1d051-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1d051-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d051-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1d051-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="1d051-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="1d051-141">Access Edge サービスの外部インターフェイス (Contoso)。</span><span class="sxs-lookup"><span data-stu-id="1d051-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="1d051-142">Lync を有効にしたユーザーがいるすべての SIP ドメインで、必要に応じて繰り返す</span><span class="sxs-lookup"><span data-stu-id="1d051-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d051-143">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1d051-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1d051-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d051-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1d051-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="1d051-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="1d051-146">Web 会議エッジサービスの外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1d051-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d051-147">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1d051-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1d051-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d051-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1d051-149">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="1d051-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="1d051-150">A/V Edge サービスの外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1d051-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d051-151">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="1d051-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="1d051-152">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d051-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1d051-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d051-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1d051-154">Access Edge サービスの外部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="1d051-154">Access Edge service external interface.</span></span> <span data-ttu-id="1d051-155">Lync 2013 および Lync 2010 クライアントを外部で動作させるために、自動構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="1d051-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="1d051-156">Lync が有効になっているユーザーがいるすべての SIP ドメインで、必要に応じてこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1d051-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d051-157">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="1d051-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="1d051-158">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d051-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1d051-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d051-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1d051-160">SIP アクセスエッジサービスの外部インターフェイスは、"許可された SIP ドメイン" と呼ばれるフェデレーションパートナー (以前のリリースで拡張フェデレーションと呼ばれる) を自動的に検出するために必要です。</span><span class="sxs-lookup"><span data-stu-id="1d051-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="1d051-161">Lync が有効なユーザーと、プッシュ通知サービスまたは Apple プッシュ通知サービスを使用している Microsoft Lync モバイルクライアントが含まれるすべての SIP ドメインで、必要に応じてこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1d051-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d051-162">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1d051-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1d051-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1d051-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1d051-164">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="1d051-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="1d051-165">統合エッジ内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1d051-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

