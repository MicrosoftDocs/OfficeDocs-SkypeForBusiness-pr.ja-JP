---
title: 'Lync Server 2013: 外部の音声ビデオファイアウォールおよびポートの要件を決定する'
description: 'Lync Server 2013: 外部の音声ビデオファイアウォールおよびポートの要件を決定します。'
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
ms.openlocfilehash: 38c2a8c1e8e332a4a1e65adb87a1e962e82941c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550933"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="06746-103">Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="06746-103">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06746-104">_**トピックの最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="06746-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="06746-105">音声ビデオ (A/V) 通信は複雑な場合があります。</span><span class="sxs-lookup"><span data-stu-id="06746-105">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="06746-106">A/V で使用されるプロトコルの性質と、クライアントとサーバーのプロトコルの使用方法によって、クライアントとサーバーのバージョンの違いについて説明する特別なセクションが保証されています。</span><span class="sxs-lookup"><span data-stu-id="06746-106">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="06746-107">次の A/V ファイアウォールとポートの表を使用して、ファイアウォール要件と開くポートを決定します。</span><span class="sxs-lookup"><span data-stu-id="06746-107">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="06746-108">次に、NAT をさまざまな方法で実装できるため、ネットワークアドレス変換 (NAT) 用語を確認します。</span><span class="sxs-lookup"><span data-stu-id="06746-108">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="06746-109">ファイアウォールポート設定の詳細な例については、「 [Lync Server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」の参照アーキテクチャを参照してください。</span><span class="sxs-lookup"><span data-stu-id="06746-109">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="06746-110">音声ビデオおよびメディアトラフィックでの UDP および TCP の一般的なプロトコル使用法</span><span class="sxs-lookup"><span data-stu-id="06746-110">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06746-111">音声ビデオトランスポート</span><span class="sxs-lookup"><span data-stu-id="06746-111">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="06746-112">使用方法</span><span class="sxs-lookup"><span data-stu-id="06746-112">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06746-113">受信</span><span class="sxs-lookup"><span data-stu-id="06746-113">UDP</span></span></p></td>
<td><p><span data-ttu-id="06746-114">オーディオとビデオの優先トランスポート層プロトコル</span><span class="sxs-lookup"><span data-stu-id="06746-114">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06746-115">TCP</span><span class="sxs-lookup"><span data-stu-id="06746-115">TCP</span></span></p></td>
<td><p><span data-ttu-id="06746-116">オーディオおよびビデオのフォールバックトランスポート層プロトコル</span><span class="sxs-lookup"><span data-stu-id="06746-116">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="06746-117">Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 へのアプリケーション共有に必要なトランスポート層プロトコル</span><span class="sxs-lookup"><span data-stu-id="06746-117">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="06746-118">Lync Server 2010 および Lync Server 2013 へのファイル転送に必要なトランスポート層プロトコル</span><span class="sxs-lookup"><span data-stu-id="06746-118">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="06746-119">外部ユーザー アクセス用の外部の音声ビデオ ファイアウォール ポートの要件</span><span class="sxs-lookup"><span data-stu-id="06746-119">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="06746-120">外部 (および内部) SIP と会議インターフェイスのファイアウォールポート要件は、クライアントのバージョンやフェデレーションパートナーのバージョンに関係なく一貫しています。</span><span class="sxs-lookup"><span data-stu-id="06746-120">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="06746-121">音声ビデオ エッジの外部インターフェイスの場合は、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="06746-121">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="06746-122">Office Communications Server 2007 とのフェデレーションの場合、音声ビデオエッジサービスでは、外部ファイアウォールの規則によって、5万 ~ 59999 のポート範囲にある RTP/TCP トラフィックと RTP/UDP トラフィックが双方向に流れることが要求されます。</span><span class="sxs-lookup"><span data-stu-id="06746-122">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="06746-123">前の表では、Lync Server 2013 がプライマリフェデレーションパートナーであり、リストされている他のフェデレーションパートナーの種類のいずれかと通信するように構成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="06746-123">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="06746-124">59999の音声/ビデオポート範囲を構成するには、ポート範囲にフェデレーションパートナーと通信するための送信元ポートが含まれる必要があることを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06746-124">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="06746-125">詳細については、フェデレーションパートナーからの通信が開始されることを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="06746-125">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="06746-126">59999の範囲内の音声ビデオエッジサービスポートからの通信は、パートナーの音声ビデオエッジサービスの TCP 443 の予想ポートに接続します。</span><span class="sxs-lookup"><span data-stu-id="06746-126">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="06746-127">反対に、音声ビデオエッジサービスポート TCP 443 への受信トラフィックには、59999の範囲の送信元ポートがあります。</span><span class="sxs-lookup"><span data-stu-id="06746-127">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="06746-128">ファイアウォール管理のためのファイアウォールとポリシーによっては、構成する必要があるのは宛先のルールだけであるか、またはソースと宛先の両方を構成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="06746-128">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="06746-129">宛先ポートのみの要件の場合は、音声ビデオの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="06746-129">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06746-130">発信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="06746-130">Source IP</span></span></th>
<th><span data-ttu-id="06746-131">送信先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="06746-131">Destination IP</span></span></th>
<th><span data-ttu-id="06746-132">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="06746-132">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06746-133">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="06746-133">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="06746-134">任意</span><span class="sxs-lookup"><span data-stu-id="06746-134">Any</span></span></p></td>
<td><p><span data-ttu-id="06746-135">TCP 443</span><span class="sxs-lookup"><span data-stu-id="06746-135">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06746-136">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="06746-136">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="06746-137">任意</span><span class="sxs-lookup"><span data-stu-id="06746-137">Any</span></span></p></td>
<td><p><span data-ttu-id="06746-138">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="06746-138">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06746-139">任意</span><span class="sxs-lookup"><span data-stu-id="06746-139">Any</span></span></p></td>
<td><p><span data-ttu-id="06746-140">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="06746-140">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="06746-141">TCP 443</span><span class="sxs-lookup"><span data-stu-id="06746-141">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06746-142">任意</span><span class="sxs-lookup"><span data-stu-id="06746-142">Any</span></span></p></td>
<td><p><span data-ttu-id="06746-143">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="06746-143">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="06746-144">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="06746-144">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="06746-145">ポリシーで受信と送信の両方のファイアウォールルール定義が必要な場合、音声/ビデオの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="06746-145">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06746-146">発信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="06746-146">Source IP</span></span></th>
<th><span data-ttu-id="06746-147">送信先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="06746-147">Destination IP</span></span></th>
<th><span data-ttu-id="06746-148">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="06746-148">Source Port</span></span></th>
<th><span data-ttu-id="06746-149">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="06746-149">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06746-150">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="06746-150">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="06746-151">任意</span><span class="sxs-lookup"><span data-stu-id="06746-151">Any</span></span></p></td>
<td><p><span data-ttu-id="06746-152">TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="06746-152">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="06746-153">TCP 443</span><span class="sxs-lookup"><span data-stu-id="06746-153">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06746-154">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="06746-154">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="06746-155">任意</span><span class="sxs-lookup"><span data-stu-id="06746-155">Any</span></span></p></td>
<td><p><span data-ttu-id="06746-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="06746-156">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="06746-157">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="06746-157">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06746-158">任意</span><span class="sxs-lookup"><span data-stu-id="06746-158">Any</span></span></p></td>
<td><p><span data-ttu-id="06746-159">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="06746-159">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="06746-160">任意</span><span class="sxs-lookup"><span data-stu-id="06746-160">Any</span></span></p></td>
<td><p><span data-ttu-id="06746-161">TCP 443</span><span class="sxs-lookup"><span data-stu-id="06746-161">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06746-162">任意</span><span class="sxs-lookup"><span data-stu-id="06746-162">Any</span></span></p></td>
<td><p><span data-ttu-id="06746-163">音声ビデオエッジサービスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="06746-163">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="06746-164">任意</span><span class="sxs-lookup"><span data-stu-id="06746-164">Any</span></span></p></td>
<td><p><span data-ttu-id="06746-165">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="06746-165">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="06746-166">Microsoft Office Communications Server 2007 には、若干異なる構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="06746-166">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="06746-167">59999の TCP および UDP ポート範囲は、受信および送信を開いている必要があります。</span><span class="sxs-lookup"><span data-stu-id="06746-167">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="06746-168">この要件は、Office Communicator 2007 に対してのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="06746-168">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="06746-169">Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 には、TCP 範囲 50000-59999 open outbound のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="06746-169">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="06746-170">エッジサービスの NAT 要件</span><span class="sxs-lookup"><span data-stu-id="06746-170">NAT requirements for the Edge service</span></span>

<span data-ttu-id="06746-171">エッジサービスに対してルーティング不能なプライベート IP アドレスを構成する場合は、次の NAT 要件を適用します。</span><span class="sxs-lookup"><span data-stu-id="06746-171">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="06746-172">NAT は、DNS 負荷分散でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="06746-172">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="06746-173">NAT は、ハードウェア負荷分散 (HLB) エッジトポロジではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="06746-173">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="06746-174">NAT は、外部エッジインターフェイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="06746-174">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="06746-175">NAT は、内部エッジインターフェイスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="06746-175">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="06746-176">NAT は、受信および送信トラフィック用に対称でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="06746-176">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="06746-177">インターネットからのトラフィックの場合、NAT は、音声ビデオエッジサービスの NAT が有効なパブリック IP アドレスから、外部 IP アドレスに宛先 IP アドレスを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06746-177">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="06746-178">音声ビデオエッジサービスが最適なメディアパスを見つけることができるように、送信元 IP アドレスは変更されないままにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="06746-178">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="06746-179">たとえば、次の図の受信方向では、パブリック IP アドレス 131.107.155.30) が外部 (プライベート) IP アドレス10.45.16.10 というに変更されました。</span><span class="sxs-lookup"><span data-stu-id="06746-179">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="06746-180">送信元 IP アドレスは変更されていません。</span><span class="sxs-lookup"><span data-stu-id="06746-180">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="06746-181">音声ビデオエッジサービスからインターネットへのトラフィックの場合、NAT は、音声ビデオエッジサービスの外部 IP アドレスから NAT が有効なパブリック IP アドレスへの送信元 IP アドレスを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06746-181">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="06746-182">たとえば、次の図の送信方向では、外部 (プライベート) IP アドレス10.45.16.10 というがパブリック IP アドレス 131.107.155.30) に変更されました。</span><span class="sxs-lookup"><span data-stu-id="06746-182">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="06746-183">**次の図は、NAT が受信トラフィックの宛先 IP アドレスと送信トラフィックの送信元 IP アドレスを変更する方法を示しています。**</span><span class="sxs-lookup"><span data-stu-id="06746-183">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="06746-184">![宛先/送信元 IP アドレスの変更](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "宛先/送信元 IP アドレスの変更")</span><span class="sxs-lookup"><span data-stu-id="06746-184">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="06746-185">主な点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="06746-185">The key points are:</span></span>

  - <span data-ttu-id="06746-186">音声ビデオエッジサービスを実行しているサーバーが受信するトラフィックは、送信元 IP アドレスは変更されませんが、宛先 IP アドレスは 131.107.155.30) から10.45.16.10 というの変換された IP アドレスに変更されます。</span><span class="sxs-lookup"><span data-stu-id="06746-186">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="06746-187">音声ビデオエッジサービスを実行しているサーバーからワークステーションに送信されるトラフィックは、送信元 IP アドレスがサーバーのパブリック IP アドレスから、音声ビデオエッジサービスを実行しているサーバーのパブリック IP アドレスに変更されます。</span><span class="sxs-lookup"><span data-stu-id="06746-187">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="06746-188">宛先 IP はワークステーションのパブリック IP アドレスのままです。</span><span class="sxs-lookup"><span data-stu-id="06746-188">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="06746-189">パケットが最初の NAT デバイスを送信した後、NAT デバイス上のルールは、音声ビデオエッジサービスの外部インターフェイスの IP アドレス (10.45.16.10 という) を実行しているサーバーの送信元 IP アドレスをパブリック IP アドレス (131.107.155.30)) に変更します。</span><span class="sxs-lookup"><span data-stu-id="06746-189">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

