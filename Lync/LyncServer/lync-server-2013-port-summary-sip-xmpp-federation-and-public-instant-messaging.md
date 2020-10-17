---
title: ポートの概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング
description: ポートの概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c58dbf7bdd56b4678d56f96a11332219bb40c17
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566359"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="cc753-103">ポートの概要-Lync Server 2013 の SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="cc753-103">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc753-104">_**トピックの最終更新日:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="cc753-104">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="cc753-105">Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server とのフェデレーションのためのポート、プロトコル、およびファイアウォールの要件は、展開されたエッジサーバーの場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="cc753-105">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="cc753-106">クライアントは、TLS/SIP/TCP 443 経由のアクセスエッジサービスとの通信を開始します。</span><span class="sxs-lookup"><span data-stu-id="cc753-106">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="cc753-107">ただし、フェデレーションパートナーは、MTLS/SIP/TCP 5061 を介してアクセスエッジサービスへの通信を開始します。</span><span class="sxs-lookup"><span data-stu-id="cc753-107">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="cc753-108">パブリックインスタントメッセージング接続をサポートするために必要なポートとプロトコルを使用するようにファイアウォールを構成するには、まず、SIP/MTLS/TCP 5061 は、パブリック IM プロバイダーの連絡先が Lync クライアントに接続する機能、または Lync がパブリック IM 連絡先に連絡することができるようにするための、双方向です。</span><span class="sxs-lookup"><span data-stu-id="cc753-108">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="cc753-109">Windows Live Messenger は、Lync クライアントとの音声/ビデオ通信に参加できます。</span><span class="sxs-lookup"><span data-stu-id="cc753-109">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="cc753-110">このアカウントは、通常、外部ユーザーとして Lync クライアントをサポートするためにファイアウォールを使用するのとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="cc753-110">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="cc753-111">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="cc753-111">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="cc753-112">Windows Live Messenger とのフェデレーションでは、Lync Standard クライアントアクセスライセンス (CAL) を超える追加のユーザー/デバイスライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cc753-112">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="cc753-113">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="cc753-113">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="cc753-114">Messenger クライアントの連絡先とのフェデレーションは、2013年3月15日に正式に終了します。ただし、中国では、ポルトガルが終了しています。</span><span class="sxs-lookup"><span data-stu-id="cc753-114">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="cc753-115">Skype は、既にメッセンジャーを使用していたフェデレーションユーザーのフェデレーションクライアントになります。</span><span class="sxs-lookup"><span data-stu-id="cc753-115">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="cc753-116">エッジサーバーに展開されている拡張メッセージングおよびプレゼンスプロトコル (XMPP) プロキシに対して定義されているポートとプロトコルは、XMPP フェデレーションパートナーからエッジサーバーへの通信を許可すると共に、エッジサーバーから XMPP フェデレーションパートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="cc753-116">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="cc753-117">ルールは、フロントエンドサーバーまたはフロントエンドプールからエッジサーバーまたはエッジプールへの内部接続ファイアウォール上にも定義されています。</span><span class="sxs-lookup"><span data-stu-id="cc753-117">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="cc753-118">ファイアウォールの概要-SIP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="cc753-118">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc753-119">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="cc753-119">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cc753-120">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="cc753-120">Source IP address</span></span></th>
<th><span data-ttu-id="cc753-121">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="cc753-121">Destination IP address</span></span></th>
<th><span data-ttu-id="cc753-122">Notes</span><span class="sxs-lookup"><span data-stu-id="cc753-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc753-123">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cc753-123">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cc753-124">アクセス エッジ サービス パブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="cc753-124">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cc753-125">任意</span><span class="sxs-lookup"><span data-stu-id="cc753-125">Any</span></span></p></td>
<td><p><span data-ttu-id="cc753-126">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="cc753-126">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="cc753-127">ファイアウォールの概要 ‐ パブリック インスタント メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="cc753-127">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc753-128">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="cc753-128">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cc753-129">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="cc753-129">Source IP address</span></span></th>
<th><span data-ttu-id="cc753-130">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="cc753-130">Destination IP address</span></span></th>
<th><span data-ttu-id="cc753-131">Notes</span><span class="sxs-lookup"><span data-stu-id="cc753-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc753-132">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cc753-132">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cc753-133">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="cc753-133">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="cc753-134">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc753-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="cc753-135">フェデレーションとパブリック IM 接続の場合、SIP を使用します。</span><span class="sxs-lookup"><span data-stu-id="cc753-135">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc753-136">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cc753-136">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cc753-137">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc753-137">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="cc753-138">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="cc753-138">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="cc753-139">フェデレーションとパブリック IM 接続の場合、SIP を使用します。</span><span class="sxs-lookup"><span data-stu-id="cc753-139">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc753-140">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cc753-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cc753-141">クライアント</span><span class="sxs-lookup"><span data-stu-id="cc753-141">Clients</span></span></p></td>
<td><p><span data-ttu-id="cc753-142">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc753-142">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="cc753-143">外部ユーザーアクセス用のクライアントからサーバーへの SIP トラフィック。</span><span class="sxs-lookup"><span data-stu-id="cc753-143">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc753-144">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="cc753-144">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cc753-145">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc753-145">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="cc753-146">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="cc753-146">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="cc753-147">パブリック IM 接続が構成されている場合に、Windows Live Messenger との音声ビデオ セッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cc753-147">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc753-148">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cc753-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cc753-149">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc753-149">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="cc753-150">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="cc753-150">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="cc753-151">Windows Live Messenger とのパブリック IM 接続に必要です。</span><span class="sxs-lookup"><span data-stu-id="cc753-151">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc753-152">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cc753-152">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cc753-153">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="cc753-153">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="cc753-154">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc753-154">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="cc753-155">Windows Live Messenger とのパブリック IM 接続に必要です。</span><span class="sxs-lookup"><span data-stu-id="cc753-155">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="cc753-156">ファイアウォールの概要-拡張可能なメッセージングとプレゼンスプロトコル (XMPP)</span><span class="sxs-lookup"><span data-stu-id="cc753-156">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc753-157">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="cc753-157">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cc753-158">送信元 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="cc753-158">Source (IP address)</span></span></th>
<th><span data-ttu-id="cc753-159">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="cc753-159">Destination (IP address)</span></span></th>
<th><span data-ttu-id="cc753-160">Comments</span><span class="sxs-lookup"><span data-stu-id="cc753-160">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc753-161">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cc753-161">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cc753-162">任意</span><span class="sxs-lookup"><span data-stu-id="cc753-162">Any</span></span></p></td>
<td><p><span data-ttu-id="cc753-163">アクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="cc753-163">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="cc753-164">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="cc753-164">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="cc753-165">フェデレーションされた XMPP パートナーからのエッジサーバー XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="cc753-165">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc753-166">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cc753-166">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cc753-167">アクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="cc753-167">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="cc753-168">任意</span><span class="sxs-lookup"><span data-stu-id="cc753-168">Any</span></span></p></td>
<td><p><span data-ttu-id="cc753-169">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="cc753-169">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="cc753-170">エッジサーバー XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="cc753-170">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc753-171">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="cc753-171">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="cc753-172">任意</span><span class="sxs-lookup"><span data-stu-id="cc753-172">Any</span></span></p></td>
<td><p><span data-ttu-id="cc753-173">内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="cc753-173">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="cc753-174">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイからエッジサーバーへの内部 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="cc753-174">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc753-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc753-175">See Also</span></span>


[<span data-ttu-id="cc753-176">Lync Server 2013 での外部ユーザーアクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="cc753-176">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="cc753-177">Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="cc753-177">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="cc753-178">Lync Server 2013 での XMPP フェデレーションパートナーの管理</span><span class="sxs-lookup"><span data-stu-id="cc753-178">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

