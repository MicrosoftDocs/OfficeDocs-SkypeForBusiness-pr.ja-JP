---
title: 'Lync Server 2013: 外部の音声ビデオファイアウォールおよびポートの要件を決定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f28e1f18a0d2f2d51e835332d6abc8c67905d647
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="1a501-102">Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="1a501-102">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a501-103">_**トピックの最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="1a501-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="1a501-104">音声ビデオ (A/V) 通信は複雑な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a501-104">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="1a501-105">A/V で使用されるプロトコルの性質と、クライアントとサーバーのプロトコルの使用方法によって、クライアントとサーバーのバージョンの違いについて説明する特別なセクションが保証されています。</span><span class="sxs-lookup"><span data-stu-id="1a501-105">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="1a501-106">次の A/V ファイアウォールとポートの表を使用して、ファイアウォール要件と開くポートを決定します。</span><span class="sxs-lookup"><span data-stu-id="1a501-106">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="1a501-107">次に、NAT をさまざまな方法で実装できるため、ネットワークアドレス変換 (NAT) 用語を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a501-107">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="1a501-108">ファイアウォールポート設定の詳細な例については、「 [Lync Server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」の参照アーキテクチャを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a501-108">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="1a501-109">音声ビデオおよびメディアトラフィックでの UDP および TCP の一般的なプロトコル使用法</span><span class="sxs-lookup"><span data-stu-id="1a501-109">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a501-110">音声ビデオトランスポート</span><span class="sxs-lookup"><span data-stu-id="1a501-110">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="1a501-111">使用方法</span><span class="sxs-lookup"><span data-stu-id="1a501-111">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a501-112">受信</span><span class="sxs-lookup"><span data-stu-id="1a501-112">UDP</span></span></p></td>
<td><p><span data-ttu-id="1a501-113">オーディオとビデオの優先トランスポート層プロトコル</span><span class="sxs-lookup"><span data-stu-id="1a501-113">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a501-114">TCP</span><span class="sxs-lookup"><span data-stu-id="1a501-114">TCP</span></span></p></td>
<td><p><span data-ttu-id="1a501-115">オーディオおよびビデオのフォールバックトランスポート層プロトコル</span><span class="sxs-lookup"><span data-stu-id="1a501-115">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="1a501-116">Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 へのアプリケーション共有に必要なトランスポート層プロトコル</span><span class="sxs-lookup"><span data-stu-id="1a501-116">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="1a501-117">Lync Server 2010 および Lync Server 2013 へのファイル転送に必要なトランスポート層プロトコル</span><span class="sxs-lookup"><span data-stu-id="1a501-117">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="1a501-118">外部ユーザー アクセス用の外部の音声ビデオ ファイアウォール ポートの要件</span><span class="sxs-lookup"><span data-stu-id="1a501-118">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="1a501-119">外部 (および内部) SIP と会議インターフェイスのファイアウォールポート要件は、クライアントのバージョンやフェデレーションパートナーのバージョンに関係なく一貫しています。</span><span class="sxs-lookup"><span data-stu-id="1a501-119">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="1a501-120">音声ビデオ エッジの外部インターフェイスの場合は、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="1a501-120">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="1a501-121">Office Communications Server 2007 とのフェデレーションの場合、音声ビデオエッジサービスでは、外部ファイアウォールの規則によって、5万 ~ 59999 のポート範囲にある RTP/TCP トラフィックと RTP/UDP トラフィックが双方向に流れることが要求されます。</span><span class="sxs-lookup"><span data-stu-id="1a501-121">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="1a501-122">前の表では、Lync Server 2013 がプライマリフェデレーションパートナーであり、リストされている他のフェデレーションパートナーの種類のいずれかと通信するように構成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="1a501-122">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="1a501-123">59999の音声/ビデオポート範囲を構成するには、ポート範囲にフェデレーションパートナーと通信するための送信元ポートが含まれる必要があることを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a501-123">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="1a501-124">詳細については、フェデレーションパートナーからの通信が開始されることを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="1a501-124">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="1a501-125">59999の範囲内の音声ビデオエッジサービスポートからの通信は、パートナーの音声ビデオエッジサービスの TCP 443 の予想ポートに接続します。</span><span class="sxs-lookup"><span data-stu-id="1a501-125">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="1a501-126">反対に、音声ビデオエッジサービスポート TCP 443 への受信トラフィックには、59999の範囲の送信元ポートがあります。</span><span class="sxs-lookup"><span data-stu-id="1a501-126">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="1a501-127">ファイアウォール管理のためのファイアウォールとポリシーによっては、構成する必要があるのは宛先のルールだけであるか、またはソースと宛先の両方を構成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a501-127">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="1a501-128">宛先ポートのみの要件の場合は、音声ビデオの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a501-128">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a501-129">発信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="1a501-129">Source IP</span></span></th>
<th><span data-ttu-id="1a501-130">送信先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="1a501-130">Destination IP</span></span></th>
<th><span data-ttu-id="1a501-131">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="1a501-131">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a501-132">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a501-132">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="1a501-133">任意</span><span class="sxs-lookup"><span data-stu-id="1a501-133">Any</span></span></p></td>
<td><p><span data-ttu-id="1a501-134">TCP 443</span><span class="sxs-lookup"><span data-stu-id="1a501-134">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a501-135">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a501-135">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="1a501-136">任意</span><span class="sxs-lookup"><span data-stu-id="1a501-136">Any</span></span></p></td>
<td><p><span data-ttu-id="1a501-137">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="1a501-137">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a501-138">任意</span><span class="sxs-lookup"><span data-stu-id="1a501-138">Any</span></span></p></td>
<td><p><span data-ttu-id="1a501-139">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a501-139">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="1a501-140">TCP 443</span><span class="sxs-lookup"><span data-stu-id="1a501-140">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a501-141">任意</span><span class="sxs-lookup"><span data-stu-id="1a501-141">Any</span></span></p></td>
<td><p><span data-ttu-id="1a501-142">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a501-142">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="1a501-143">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="1a501-143">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1a501-144">ポリシーで受信と送信の両方のファイアウォールルール定義が必要な場合、音声/ビデオの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a501-144">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a501-145">発信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="1a501-145">Source IP</span></span></th>
<th><span data-ttu-id="1a501-146">送信先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="1a501-146">Destination IP</span></span></th>
<th><span data-ttu-id="1a501-147">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="1a501-147">Source Port</span></span></th>
<th><span data-ttu-id="1a501-148">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="1a501-148">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a501-149">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a501-149">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="1a501-150">任意</span><span class="sxs-lookup"><span data-stu-id="1a501-150">Any</span></span></p></td>
<td><p><span data-ttu-id="1a501-151">TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="1a501-151">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1a501-152">TCP 443</span><span class="sxs-lookup"><span data-stu-id="1a501-152">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a501-153">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a501-153">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="1a501-154">任意</span><span class="sxs-lookup"><span data-stu-id="1a501-154">Any</span></span></p></td>
<td><p><span data-ttu-id="1a501-155">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="1a501-155">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="1a501-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="1a501-156">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a501-157">任意</span><span class="sxs-lookup"><span data-stu-id="1a501-157">Any</span></span></p></td>
<td><p><span data-ttu-id="1a501-158">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a501-158">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="1a501-159">任意</span><span class="sxs-lookup"><span data-stu-id="1a501-159">Any</span></span></p></td>
<td><p><span data-ttu-id="1a501-160">TCP 443</span><span class="sxs-lookup"><span data-stu-id="1a501-160">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a501-161">任意</span><span class="sxs-lookup"><span data-stu-id="1a501-161">Any</span></span></p></td>
<td><p><span data-ttu-id="1a501-162">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a501-162">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="1a501-163">任意</span><span class="sxs-lookup"><span data-stu-id="1a501-163">Any</span></span></p></td>
<td><p><span data-ttu-id="1a501-164">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="1a501-164">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="1a501-165">Microsoft Office Communications Server 2007 には、若干異なる構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="1a501-165">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="1a501-166">59999の TCP および UDP ポート範囲は、受信および送信を開いている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a501-166">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="1a501-167">この要件は、Office Communicator 2007 に対してのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="1a501-167">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="1a501-168">Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 には、TCP 範囲 50000-59999 open outbound のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="1a501-168">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="1a501-169">エッジサービスの NAT 要件</span><span class="sxs-lookup"><span data-stu-id="1a501-169">NAT requirements for the Edge service</span></span>

<span data-ttu-id="1a501-170">エッジサービスに対してルーティング不能なプライベート IP アドレスを構成する場合は、次の NAT 要件を適用します。</span><span class="sxs-lookup"><span data-stu-id="1a501-170">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="1a501-171">NAT は、DNS 負荷分散でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a501-171">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="1a501-172">NAT は、ハードウェア負荷分散 (HLB) エッジトポロジではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1a501-172">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="1a501-173">NAT は、外部エッジインターフェイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a501-173">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="1a501-174">NAT は、内部エッジインターフェイスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1a501-174">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="1a501-175">NAT は、受信および送信トラフィック用に対称でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="1a501-175">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="1a501-176">インターネットからのトラフィックの場合、NAT は、音声ビデオエッジサービスの NAT が有効なパブリック IP アドレスから、外部 IP アドレスに宛先 IP アドレスを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a501-176">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="1a501-177">音声ビデオエッジサービスが最適なメディアパスを見つけることができるように、送信元 IP アドレスは変更されないままにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a501-177">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="1a501-178">たとえば、次の図の受信方向では、パブリック IP アドレス 131.107.155.30) が外部 (プライベート) IP アドレス10.45.16.10 というに変更されました。</span><span class="sxs-lookup"><span data-stu-id="1a501-178">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="1a501-179">送信元 IP アドレスは変更されていません。</span><span class="sxs-lookup"><span data-stu-id="1a501-179">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="1a501-180">音声ビデオエッジサービスからインターネットへのトラフィックの場合、NAT は、音声ビデオエッジサービスの外部 IP アドレスから NAT が有効なパブリック IP アドレスへの送信元 IP アドレスを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a501-180">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="1a501-181">たとえば、次の図の送信方向では、外部 (プライベート) IP アドレス10.45.16.10 というがパブリック IP アドレス 131.107.155.30) に変更されました。</span><span class="sxs-lookup"><span data-stu-id="1a501-181">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="1a501-182">**次の図は、NAT が受信トラフィックの宛先 IP アドレスと送信トラフィックの送信元 IP アドレスを変更する方法を示しています。**</span><span class="sxs-lookup"><span data-stu-id="1a501-182">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="1a501-183">![宛先/送信元 IP アドレスの変更](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "宛先/送信元 IP アドレスの変更")</span><span class="sxs-lookup"><span data-stu-id="1a501-183">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="1a501-184">主な点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a501-184">The key points are:</span></span>

  - <span data-ttu-id="1a501-185">音声ビデオエッジサービスを実行しているサーバーが受信するトラフィックは、送信元 IP アドレスは変更されませんが、宛先 IP アドレスは 131.107.155.30) から10.45.16.10 というの変換された IP アドレスに変更されます。</span><span class="sxs-lookup"><span data-stu-id="1a501-185">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="1a501-186">音声ビデオエッジサービスを実行しているサーバーからワークステーションに送信されるトラフィックは、送信元 IP アドレスがサーバーのパブリック IP アドレスから、音声ビデオエッジサービスを実行しているサーバーのパブリック IP アドレスに変更されます。</span><span class="sxs-lookup"><span data-stu-id="1a501-186">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="1a501-187">宛先 IP はワークステーションのパブリック IP アドレスのままです。</span><span class="sxs-lookup"><span data-stu-id="1a501-187">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="1a501-188">パケットが最初の NAT デバイスを送信した後、NAT デバイス上のルールは、音声ビデオエッジサービスの外部インターフェイスの IP アドレス (10.45.16.10 という) を実行しているサーバーの送信元 IP アドレスをパブリック IP アドレス (131.107.155.30)) に変更します。</span><span class="sxs-lookup"><span data-stu-id="1a501-188">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

