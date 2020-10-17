---
title: 'Lync Server 2013: ポートの概要-拡張ディレクタープール、ハードウェアロードバランサー'
description: 'Lync Server 2013: ポートの概要-拡張ディレクタープール、ハードウェアロードバランサー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10bfb3a3ad3a38b6cb0e46414bf22deecc71d7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564553"
---
# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="b2915-103">ポートの概要-Lync Server 2013 の拡張ディレクタープール、ハードウェアロードバランサー</span><span class="sxs-lookup"><span data-stu-id="b2915-103">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2915-104">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="b2915-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="b2915-105">ディレクタープールのファイアウォールポート要件は、エッジサーバーの内部インターフェイスまたはリバースプロキシの内部インターフェイスからディレクターとの通信を確立するために使用されるポートで構成されています。</span><span class="sxs-lookup"><span data-stu-id="b2915-105">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="b2915-106">Microsoft Lync Server 2013 既定では、ポート HTTP/TCP 8080 および HTTPS/TCP 4443 を、フロントエンドプールおよびフロントエンドサーバーに加えて、ディレクターへのリバースプロキシから開くことが想定されています。</span><span class="sxs-lookup"><span data-stu-id="b2915-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="b2915-107">さらに、エッジサーバーの内部インターフェイスから、ディレクターおよびフロントエンドプールおよびフロントエンドサーバーへのセッション開始プロトコル (SIP) 通信が必要です。</span><span class="sxs-lookup"><span data-stu-id="b2915-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="b2915-108">SIP プロトコルは、エッジサーバーの SIP/MTLS/TCP 5061 を使用して、フロントエンドプールおよびフロントエンドサーバーに対して使用します。</span><span class="sxs-lookup"><span data-stu-id="b2915-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="b2915-109">ディレクター、フロントエンドプールおよびフロントエンドサーバーからエッジサーバーの内部インターフェイスへの SIP/MTLS/TCP 5061 通信を許可するルールも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2915-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="b2915-110">ファイアウォール定義用のディレクター ポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="b2915-110">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2915-111">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="b2915-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b2915-112">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b2915-112">Source IP address</span></span></th>
<th><span data-ttu-id="b2915-113">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b2915-113">Destination IP address</span></span></th>
<th><span data-ttu-id="b2915-114">Notes</span><span class="sxs-lookup"><span data-stu-id="b2915-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2915-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="b2915-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="b2915-116">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2915-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="b2915-117">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="b2915-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="b2915-118">リバースプロキシの外部側で最初に受信された通信は、ディレクター HLB VIP およびフロントエンドサーバー web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b2915-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2915-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="b2915-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="b2915-120">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2915-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="b2915-121">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="b2915-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="b2915-122">リバースプロキシの外部側で最初に受信された通信は、ディレクター HLB VIP およびフロントエンドサーバー web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b2915-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2915-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="b2915-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="b2915-124">ディレクター</span><span class="sxs-lookup"><span data-stu-id="b2915-124">Director</span></span></p></td>
<td><p><span data-ttu-id="b2915-125">フロントエンドサーバーまたはフロントエンドプール</span><span class="sxs-lookup"><span data-stu-id="b2915-125">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="b2915-126">ディレクター HLB VIP とフロントエンドサーバー間のサーバー間通信</span><span class="sxs-lookup"><span data-stu-id="b2915-126">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2915-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="b2915-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="b2915-128">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="b2915-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="b2915-129">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="b2915-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="b2915-130">ディレクターは、内部および外部クライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b2915-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2915-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="b2915-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="b2915-132">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="b2915-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="b2915-133">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="b2915-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="b2915-134">ディレクターは、内部および外部クライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b2915-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2915-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="b2915-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="b2915-136">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2915-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b2915-137">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="b2915-137">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="b2915-138">エッジサーバーからディレクター、フロントエンドサーバーへの SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="b2915-138">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2915-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="b2915-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="b2915-140">任意</span><span class="sxs-lookup"><span data-stu-id="b2915-140">Any</span></span></p></td>
<td><p><span data-ttu-id="b2915-141">ディレクター</span><span class="sxs-lookup"><span data-stu-id="b2915-141">Director</span></span></p></td>
<td><p><span data-ttu-id="b2915-142">集中ログサービスコントローラー (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="b2915-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2915-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="b2915-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="b2915-144">任意</span><span class="sxs-lookup"><span data-stu-id="b2915-144">Any</span></span></p></td>
<td><p><span data-ttu-id="b2915-145">ディレクター</span><span class="sxs-lookup"><span data-stu-id="b2915-145">Director</span></span></p></td>
<td><p><span data-ttu-id="b2915-146">集中ログサービスコントローラー (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="b2915-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2915-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="b2915-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="b2915-148">任意</span><span class="sxs-lookup"><span data-stu-id="b2915-148">Any</span></span></p></td>
<td><p><span data-ttu-id="b2915-149">ディレクター</span><span class="sxs-lookup"><span data-stu-id="b2915-149">Director</span></span></p></td>
<td><p><span data-ttu-id="b2915-150">集中ログサービスコントローラー (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="b2915-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

