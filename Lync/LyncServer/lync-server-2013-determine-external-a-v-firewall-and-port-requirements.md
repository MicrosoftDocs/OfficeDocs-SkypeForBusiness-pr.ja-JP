---
title: 'Lync Server 2013: 外部の音声ビデオ ファイアウォールおよびポートの要件を決定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b278c60eaca69fd17508d0e82198a002484ce586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="8bc0b-102">Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="8bc0b-102">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bc0b-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="8bc0b-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="8bc0b-104">音声/ビデオ (A/V) 通信は複雑な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-104">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="8bc0b-105">A/V で使用されるプロトコルの性質、およびクライアントとサーバーでのプロトコルの使用方法については、クライアントとサーバーのバージョンの違いを説明するための特別なセクションが保証されています。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-105">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="8bc0b-106">ファイアウォール要件と開くポートを決定するには、次の A/V ファイアウォールとポートテーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-106">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="8bc0b-107">次に、NAT がさまざまな方法で実装されるため、ネットワークアドレス変換 (NAT) 用語を確認します。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-107">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="8bc0b-108">ファイアウォールポート設定の詳細な例については、「 [Lync Server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)でのリファレンスアーキテクチャ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-108">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="8bc0b-109">音声/ビデオおよびメディアトラフィックでの UDP および TCP の一般的なプロトコルの使用</span><span class="sxs-lookup"><span data-stu-id="8bc0b-109">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bc0b-110">音声/ビデオトランスポート</span><span class="sxs-lookup"><span data-stu-id="8bc0b-110">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="8bc0b-111">用途</span><span class="sxs-lookup"><span data-stu-id="8bc0b-111">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bc0b-112">UDP</span><span class="sxs-lookup"><span data-stu-id="8bc0b-112">UDP</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-113">オーディオおよびビデオの優先トランスポート層プロトコル</span><span class="sxs-lookup"><span data-stu-id="8bc0b-113">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc0b-114">TCP</span><span class="sxs-lookup"><span data-stu-id="8bc0b-114">TCP</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-115">オーディオおよびビデオのフォールバックトランスポート層プロトコル</span><span class="sxs-lookup"><span data-stu-id="8bc0b-115">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="8bc0b-116">Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 へのアプリケーション共有に必要なトランスポートレイヤープロトコル</span><span class="sxs-lookup"><span data-stu-id="8bc0b-116">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="8bc0b-117">Lync Server 2010 および Lync Server 2013 へのファイル転送に必要なトランスポートレイヤープロトコル</span><span class="sxs-lookup"><span data-stu-id="8bc0b-117">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="8bc0b-118">外部ユーザーアクセスの外部の A/V ファイアウォールポートの要件</span><span class="sxs-lookup"><span data-stu-id="8bc0b-118">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="8bc0b-119">クライアントのバージョンやフェデレーションパートナーのバージョンに関係なく、外部 (および内部) SIP と会議インターフェイスのファイアウォールポート要件は一貫しています。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-119">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="8bc0b-120">オーディオ/ビデオエッジの外部インターフェイスには、同じことが当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-120">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="8bc0b-121">Office Communications Server 2007 とのフェデレーションの場合、A/V Edge サービスでは、外部ファイアウォールルールによって、5万 ~ 59999 ポート範囲内の RTP/TCP トラフィックと RTP/UDP トラフィックが両方の方向に流れるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-121">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="8bc0b-122">上記の表では、Lync Server 2013 がプライマリフェデレーションパートナーであり、一覧されている他のフェデレーションパートナーのいずれかと通信するように構成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-122">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="8bc0b-123">59,999 の音声/ビデオポート範囲を構成するには、ポート範囲にフェデレーションパートナーへの通信のソースポートが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-123">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="8bc0b-124">詳細については、通信がフェデレーションパートナーから開始されることを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-124">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="8bc0b-125">59,999 範囲の A/V Edge サービスポートからの通信は、パートナーの A/V Edge サービスの予期されるポート TCP 443 に接続します。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-125">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="8bc0b-126">反対に、A/V Edge サービス443ポートへの受信トラフィックは、59,999 の範囲のソースポートを持ちます。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-126">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="8bc0b-127">ファイアウォール管理用のさまざまなファイアウォールとポリシーには、構成するためのターゲットルールのみを設定するか、またはソースとターゲットの両方を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-127">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="8bc0b-128">目的が宛先ポート専用の場合は、オーディオ/ビデオの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-128">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bc0b-129">発信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="8bc0b-129">Source IP</span></span></th>
<th><span data-ttu-id="8bc0b-130">送信先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="8bc0b-130">Destination IP</span></span></th>
<th><span data-ttu-id="8bc0b-131">送信先ポート</span><span class="sxs-lookup"><span data-stu-id="8bc0b-131">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bc0b-132">A/V Edge サービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bc0b-132">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-133">任意</span><span class="sxs-lookup"><span data-stu-id="8bc0b-133">Any</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-134">TCP 443</span><span class="sxs-lookup"><span data-stu-id="8bc0b-134">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc0b-135">A/V Edge サービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bc0b-135">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-136">任意</span><span class="sxs-lookup"><span data-stu-id="8bc0b-136">Any</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-137">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="8bc0b-137">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc0b-138">任意</span><span class="sxs-lookup"><span data-stu-id="8bc0b-138">Any</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-139">A/V Edge サービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bc0b-139">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-140">TCP 443</span><span class="sxs-lookup"><span data-stu-id="8bc0b-140">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc0b-141">任意</span><span class="sxs-lookup"><span data-stu-id="8bc0b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-142">A/V Edge サービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bc0b-142">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-143">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="8bc0b-143">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8bc0b-144">ポリシーで受信と送信の両方のファイアウォール規則の定義が必要な場合、音声/ビデオの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-144">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bc0b-145">発信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="8bc0b-145">Source IP</span></span></th>
<th><span data-ttu-id="8bc0b-146">送信先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="8bc0b-146">Destination IP</span></span></th>
<th><span data-ttu-id="8bc0b-147">発信元ポート</span><span class="sxs-lookup"><span data-stu-id="8bc0b-147">Source Port</span></span></th>
<th><span data-ttu-id="8bc0b-148">送信先ポート</span><span class="sxs-lookup"><span data-stu-id="8bc0b-148">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bc0b-149">A/V Edge サービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bc0b-149">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-150">任意</span><span class="sxs-lookup"><span data-stu-id="8bc0b-150">Any</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-151">TCP 50,000 ～ 59,999</span><span class="sxs-lookup"><span data-stu-id="8bc0b-151">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-152">TCP 443</span><span class="sxs-lookup"><span data-stu-id="8bc0b-152">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc0b-153">A/V Edge サービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bc0b-153">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-154">任意</span><span class="sxs-lookup"><span data-stu-id="8bc0b-154">Any</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-155">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="8bc0b-155">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="8bc0b-156">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc0b-157">任意</span><span class="sxs-lookup"><span data-stu-id="8bc0b-157">Any</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-158">A/V Edge サービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bc0b-158">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-159">任意</span><span class="sxs-lookup"><span data-stu-id="8bc0b-159">Any</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-160">TCP 443</span><span class="sxs-lookup"><span data-stu-id="8bc0b-160">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc0b-161">任意</span><span class="sxs-lookup"><span data-stu-id="8bc0b-161">Any</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-162">A/V Edge サービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bc0b-162">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-163">任意</span><span class="sxs-lookup"><span data-stu-id="8bc0b-163">Any</span></span></p></td>
<td><p><span data-ttu-id="8bc0b-164">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="8bc0b-164">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="8bc0b-165">Microsoft Office Communications Server 2007 では、若干異なる構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-165">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="8bc0b-166">59,999 の TCP ポート範囲と UDP ポート範囲は、受信と送信が開いている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-166">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="8bc0b-167">この要件は、Office Communicator 2007 に限定されます。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-167">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="8bc0b-168">Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 には、TCP 範囲 50000-59,999 open outbound が必要です。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-168">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="8bc0b-169">エッジサービスの NAT 要件</span><span class="sxs-lookup"><span data-stu-id="8bc0b-169">NAT requirements for the Edge service</span></span>

<span data-ttu-id="8bc0b-170">エッジサービスに対してルーティングできないプライベート IP アドレスを構成する場合は、次の NAT 要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-170">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="8bc0b-171">NAT は、DNS の負荷分散でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-171">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="8bc0b-172">NAT は、ハードウェア負荷分散 (HLB) エッジトポロジではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-172">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="8bc0b-173">NAT は、外部 Edge インターフェイスでのみ使うことができます。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-173">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="8bc0b-174">NAT は、内部エッジインターフェイスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-174">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="8bc0b-175">NAT は、受信トラフィックと発信トラフィックに対称である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-175">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="8bc0b-176">インターネットからのトラフィックの場合、NAT は、宛先の IP アドレスを、A/V Edge サービスの NAT 対応のパブリック IP アドレスから外部 IP アドレスに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-176">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="8bc0b-177">ソース IP アドレスはそのままにしておく必要があります。そのため、A/V Edge サービスは最適なメディアパスを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-177">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="8bc0b-178">たとえば、次の図の受信方向では、パブリック IP アドレスの131.107.155.30 が外部 (プライベート) IP アドレス10.45.16.10 に変更されました。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-178">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="8bc0b-179">ソース IP アドレスは変更されていません。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-179">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="8bc0b-180">NAT では、A/v Edge サービスからインターネットへのトラフィックについて、ソース IP アドレスを、A/V Edge サービスの外部 IP アドレスから NAT 対応のパブリック IP アドレスに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-180">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="8bc0b-181">たとえば、次の図のような送信方向の場合、外部 (プライベート) IP アドレス10.45.16.10 はパブリック IP アドレス131.107.155.30 に変更されました。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-181">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="8bc0b-182">**次の図は、NAT で受信トラフィックの送信先 IP アドレスと送信トラフィックのソース IP アドレスを変更する方法を示しています。**</span><span class="sxs-lookup"><span data-stu-id="8bc0b-182">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="8bc0b-183">![送信先/ソース IP アドレスを変更する](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "送信先/ソース IP アドレスを変更する")</span><span class="sxs-lookup"><span data-stu-id="8bc0b-183">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="8bc0b-184">重要なポイントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-184">The key points are:</span></span>

  - <span data-ttu-id="8bc0b-185">A/V Edge サービスを実行しているサーバーへのトラフィックは、ソース IP アドレスは変更されませんが、宛先 IP アドレスは131.107.155.30 から10.45.16.10 の変換済み IP アドレスに変わります。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-185">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="8bc0b-186">A/V Edge サービスを実行しているサーバーからワークステーションに送信されるトラフィックについては、ソース IP アドレスがサーバーのパブリック IP アドレスから、A/V Edge サービスを実行しているサーバーのパブリック IP アドレスに変わります。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-186">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="8bc0b-187">送信先 IP は、ワークステーションのパブリック IP アドレスのままです。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-187">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="8bc0b-188">パケットが最初の NAT デバイスから送信されると、NAT デバイス上のルールによって、A/V Edge サービスの外部インターフェイス IP アドレス (10.45.16.10) を実行しているサーバーのソース IP アドレスが、そのパブリック IP アドレス (131.107.155.30) に変更されます。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-188">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

