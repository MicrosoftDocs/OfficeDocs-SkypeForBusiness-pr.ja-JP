---
title: 'Lync Server 2013: ポートの概要-パブリックインスタントメッセージング接続'
description: 'Lync Server 2013: ポートの概要-パブリックインスタントメッセージング接続。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4137b5f92e043dc15dc9aa1f0b9593b4d9f7c2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543063"
---
# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="7f299-103">ポートの概要-Lync Server 2013 でのパブリックインスタントメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="7f299-103">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f299-104">_**トピックの最終更新日:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="7f299-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="7f299-105">パブリックインスタントメッセージング接続をサポートするために必要なポートとプロトコルを使用するようにファイアウォールを構成するには、まず、SIP/MTLS/TCP 5061 は、パブリック IM プロバイダーの連絡先が Lync クライアントに接続する機能、または Lync がパブリック IM 連絡先に連絡することができるようにするための、双方向です。</span><span class="sxs-lookup"><span data-stu-id="7f299-105">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="7f299-106">Windows Live Messenger は、Lync クライアントとの音声/ビデオ通信に参加できます。</span><span class="sxs-lookup"><span data-stu-id="7f299-106">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="7f299-107">このアカウントは、通常、外部ユーザーとして Lync クライアントをサポートするためにファイアウォールを使用するのとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="7f299-107">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7f299-108">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="7f299-108">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="7f299-109">Windows Live Messenger とのフェデレーションでは、Lync Standard クライアントアクセスライセンス (CAL) を超える追加のユーザー/デバイスライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7f299-109">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="7f299-110">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="7f299-110">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="7f299-111">Messenger クライアントの連絡先とのフェデレーションは、2013年3月15日に正式に終了します。ただし、中国では、ポルトガルが終了しています。</span><span class="sxs-lookup"><span data-stu-id="7f299-111">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="7f299-112">Skype は、既にメッセンジャーを使用していたフェデレーションユーザーのフェデレーションクライアントになります。</span><span class="sxs-lookup"><span data-stu-id="7f299-112">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="7f299-113">ファイアウォールの概要 ‐ パブリック インスタント メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="7f299-113">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f299-114">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="7f299-114">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7f299-115">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="7f299-115">Source IP address</span></span></th>
<th><span data-ttu-id="7f299-116">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="7f299-116">Destination IP address</span></span></th>
<th><span data-ttu-id="7f299-117">Notes</span><span class="sxs-lookup"><span data-stu-id="7f299-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f299-118">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7f299-118">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7f299-119">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="7f299-119">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="7f299-120">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f299-120">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="7f299-121">フェデレーションとパブリック IM 接続の場合、SIP を使用します。</span><span class="sxs-lookup"><span data-stu-id="7f299-121">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f299-122">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7f299-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7f299-123">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f299-123">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="7f299-124">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="7f299-124">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="7f299-125">フェデレーションとパブリック IM 接続の場合、SIP を使用します。</span><span class="sxs-lookup"><span data-stu-id="7f299-125">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f299-126">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7f299-126">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7f299-127">クライアント</span><span class="sxs-lookup"><span data-stu-id="7f299-127">Clients</span></span></p></td>
<td><p><span data-ttu-id="7f299-128">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f299-128">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="7f299-129">外部ユーザーアクセス用のクライアントからサーバーへの SIP トラフィック。</span><span class="sxs-lookup"><span data-stu-id="7f299-129">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f299-130">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="7f299-130">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7f299-131">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f299-131">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="7f299-132">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="7f299-132">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="7f299-133">パブリック IM 接続が構成されている場合に、Windows Live Messenger との音声ビデオ セッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7f299-133">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f299-134">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7f299-134">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7f299-135">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f299-135">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="7f299-136">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="7f299-136">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="7f299-137">Windows Live Messenger とのパブリック IM 接続に必要です。</span><span class="sxs-lookup"><span data-stu-id="7f299-137">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f299-138">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7f299-138">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7f299-139">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="7f299-139">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="7f299-140">エッジサーバーアクセスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f299-140">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="7f299-141">Windows Live Messenger とのパブリック IM 接続に必要です。</span><span class="sxs-lookup"><span data-stu-id="7f299-141">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f299-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f299-142">See Also</span></span>


[<span data-ttu-id="7f299-143">Lync Server 2013 での外部ユーザーアクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="7f299-143">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="7f299-144">Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="7f299-144">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

