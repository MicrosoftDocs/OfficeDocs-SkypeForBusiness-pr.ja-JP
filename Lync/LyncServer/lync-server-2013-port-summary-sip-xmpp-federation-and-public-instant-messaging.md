---
title: ポートの概要-SIP、XMPP フェデレーション、パブリックインスタントメッセージ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2edcad9806c5e6c8714f3face301211633a53fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="672fc-102">[ポートの概要]-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="672fc-102">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="672fc-103">_**最終更新日:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="672fc-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="672fc-104">Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server とのフェデレーションのためのポート、プロトコル、ファイアウォールの要件は、展開されたエッジサーバーの場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="672fc-104">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="672fc-105">クライアントは、TLS/SIP/TCP 443 経由でアクセスエッジサービスとの通信を開始します。</span><span class="sxs-lookup"><span data-stu-id="672fc-105">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="672fc-106">ただし、フェデレーションパートナーは、MTLS/SIP/TCP 5061 経由でアクセスエッジサービスへの通信を開始します。</span><span class="sxs-lookup"><span data-stu-id="672fc-106">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="672fc-107">パブリックインスタントメッセージング接続をサポートするために必要なポートとプロトコル用にファイアウォールを構成するには、まず、SIP/MTLS/TCP 5061 は、パブリック IM プロバイダーの連絡先が Lync クライアントまたは Lync に連絡する機能を提供するための双方向アカウントであることに注意してください。パブリック IM の連絡先に連絡します。</span><span class="sxs-lookup"><span data-stu-id="672fc-107">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="672fc-108">Windows Live Messenger は、Lync クライアントとの音声/ビデオ通信に参加できます。</span><span class="sxs-lookup"><span data-stu-id="672fc-108">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="672fc-109">通常、ファイアウォールを使用して、外部ユーザーとして Lync クライアントをサポートする、非常に類似したファイアウォールポートおよびプロトコル構成については、このアカウントをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="672fc-109">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="672fc-110">Lync は、組織間、および世界各地の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="672fc-110">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="672fc-111">Windows Live Messenger とのフェデレーションには、Lync Standard クライアントアクセスライセンス (CAL) を超える追加のユーザー/デバイスライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="672fc-111">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="672fc-112">Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="672fc-112">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="672fc-113">Messenger クライアント連絡先とのフェデレーションは、2013年3月15日に正式に終了します。中国とは異なります。</span><span class="sxs-lookup"><span data-stu-id="672fc-113">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="672fc-114">Skype は、以前に Messenger を使用したフェデレーションユーザーのフェデレーションクライアントになります。</span><span class="sxs-lookup"><span data-stu-id="672fc-114">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="672fc-115">エッジサーバーに展開された拡張メッセージングとプレゼンスプロトコル (XMPP) プロキシ用に定義されたポートとプロトコルを使うと、XMPP フェデレーションパートナーからエッジサーバーへの通信が可能になり、エッジサーバーから XMPP への通信も可能になります。フェデレーションパートナー。</span><span class="sxs-lookup"><span data-stu-id="672fc-115">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="672fc-116">フロントエンドサーバーまたはフロントエンドプールからエッジサーバーまたはエッジプールへのルールも定義されています。</span><span class="sxs-lookup"><span data-stu-id="672fc-116">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="672fc-117">ファイアウォールの概要-SIP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="672fc-117">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="672fc-118">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="672fc-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="672fc-119">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="672fc-119">Source IP address</span></span></th>
<th><span data-ttu-id="672fc-120">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="672fc-120">Destination IP address</span></span></th>
<th><span data-ttu-id="672fc-121">メモ</span><span class="sxs-lookup"><span data-stu-id="672fc-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="672fc-122">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="672fc-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="672fc-123">アクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="672fc-123">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="672fc-124">任意</span><span class="sxs-lookup"><span data-stu-id="672fc-124">Any</span></span></p></td>
<td><p><span data-ttu-id="672fc-125">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="672fc-125">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="672fc-126">ファイアウォールの概要–パブリックインスタントメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="672fc-126">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="672fc-127">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="672fc-127">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="672fc-128">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="672fc-128">Source IP address</span></span></th>
<th><span data-ttu-id="672fc-129">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="672fc-129">Destination IP address</span></span></th>
<th><span data-ttu-id="672fc-130">メモ</span><span class="sxs-lookup"><span data-stu-id="672fc-130">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="672fc-131">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="672fc-131">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="672fc-132">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="672fc-132">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="672fc-133">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="672fc-133">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="672fc-134">SIP を使うフェデレーションおよびパブリック IM 接続の場合。</span><span class="sxs-lookup"><span data-stu-id="672fc-134">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="672fc-135">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="672fc-135">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="672fc-136">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="672fc-136">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="672fc-137">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="672fc-137">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="672fc-138">SIP を使うフェデレーションおよびパブリック IM 接続の場合。</span><span class="sxs-lookup"><span data-stu-id="672fc-138">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="672fc-139">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="672fc-139">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="672fc-140">クライアント</span><span class="sxs-lookup"><span data-stu-id="672fc-140">Clients</span></span></p></td>
<td><p><span data-ttu-id="672fc-141">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="672fc-141">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="672fc-142">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="672fc-142">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="672fc-143">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="672fc-143">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="672fc-144">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="672fc-144">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="672fc-145">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="672fc-145">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="672fc-146">パブリック IM 接続が構成されている場合、Windows Live Messenger でのセッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="672fc-146">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="672fc-147">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="672fc-147">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="672fc-148">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="672fc-148">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="672fc-149">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="672fc-149">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="672fc-150">Windows Live Messenger とのパブリック IM 接続に必要。</span><span class="sxs-lookup"><span data-stu-id="672fc-150">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="672fc-151">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="672fc-151">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="672fc-152">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="672fc-152">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="672fc-153">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="672fc-153">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="672fc-154">Windows Live Messenger とのパブリック IM 接続に必要。</span><span class="sxs-lookup"><span data-stu-id="672fc-154">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="672fc-155">ファイアウォールの概要-拡張可能なメッセージングとプレゼンスプロトコル (XMPP)</span><span class="sxs-lookup"><span data-stu-id="672fc-155">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="672fc-156">Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="672fc-156">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="672fc-157">ソース (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="672fc-157">Source (IP address)</span></span></th>
<th><span data-ttu-id="672fc-158">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="672fc-158">Destination (IP address)</span></span></th>
<th><span data-ttu-id="672fc-159">コメント</span><span class="sxs-lookup"><span data-stu-id="672fc-159">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="672fc-160">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="672fc-160">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="672fc-161">任意</span><span class="sxs-lookup"><span data-stu-id="672fc-161">Any</span></span></p></td>
<td><p><span data-ttu-id="672fc-162">Access Edge サービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="672fc-162">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="672fc-163">XMPP 向けの標準的なサーバー間通信ポート。</span><span class="sxs-lookup"><span data-stu-id="672fc-163">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="672fc-164">フェデレーションされた XMPP パートナーからエッジサーバーの XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="672fc-164">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="672fc-165">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="672fc-165">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="672fc-166">Access Edge サービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="672fc-166">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="672fc-167">任意</span><span class="sxs-lookup"><span data-stu-id="672fc-167">Any</span></span></p></td>
<td><p><span data-ttu-id="672fc-168">XMPP 向けの標準的なサーバー間通信ポート。</span><span class="sxs-lookup"><span data-stu-id="672fc-168">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="672fc-169">エッジサーバーの XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="672fc-169">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="672fc-170">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="672fc-170">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="672fc-171">任意</span><span class="sxs-lookup"><span data-stu-id="672fc-171">Any</span></span></p></td>
<td><p><span data-ttu-id="672fc-172">内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="672fc-172">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="672fc-173">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイからエッジサーバーへの内部の XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="672fc-173">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="672fc-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="672fc-174">See Also</span></span>


[<span data-ttu-id="672fc-175">Lync Server 2013 の外部ユーザー アクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="672fc-175">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="672fc-176">Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="672fc-176">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="672fc-177">Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理</span><span class="sxs-lookup"><span data-stu-id="672fc-177">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

