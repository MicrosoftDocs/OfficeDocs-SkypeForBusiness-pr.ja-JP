---
title: 'Lync Server 2013: ポートの概要-DNS と HLB 負荷分散'
description: 'Lync Server 2013: ポートの概要-DNS と HLB 負荷分散。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be2e8204e792fd9c4718cb9171e90784af2d0104
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543133"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="b371e-103">ポートの概要-Lync Server 2013 での DNS および HLB の負荷分散</span><span class="sxs-lookup"><span data-stu-id="b371e-103">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b371e-104">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b371e-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b371e-105">単一ディレクターのファイアウォールポート要件は、内部インターフェイスまたはリバースプロキシの内部接続ネットワークからディレクターとの通信を確立するために使用されるポートで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b371e-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="b371e-106">Microsoft Lync Server 2013 既定では、ポート HTTP/TCP 8080 および HTTPS/TCP 4443 を、フロントエンドプールおよびフロントエンドサーバーに加えて、ディレクターへのリバースプロキシから開くことが想定されています。</span><span class="sxs-lookup"><span data-stu-id="b371e-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="b371e-107">さらに、エッジサーバーの内部インターフェイスから、ディレクターおよびフロントエンドプールおよびフロントエンドサーバーへのセッション開始プロトコル (SIP) 通信が必要です。</span><span class="sxs-lookup"><span data-stu-id="b371e-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="b371e-108">SIP プロトコルは、エッジサーバーの SIP/MTLS/TCP 5061 を使用して、フロントエンドプールおよびフロントエンドサーバーに対して使用します。</span><span class="sxs-lookup"><span data-stu-id="b371e-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="b371e-109">ディレクター、フロントエンドプールおよびフロントエンドサーバーからエッジサーバーの内部インターフェイスへの SIP/MTLS/TCP 5061 通信を許可するルールも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b371e-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="b371e-110">ファイアウォール定義用の単一ディレクターポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="b371e-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b371e-111">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="b371e-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b371e-112">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b371e-112">Source IP address</span></span></th>
<th><span data-ttu-id="b371e-113">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b371e-113">Destination IP address</span></span></th>
<th><span data-ttu-id="b371e-114">Notes</span><span class="sxs-lookup"><span data-stu-id="b371e-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b371e-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="b371e-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="b371e-116">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b371e-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="b371e-117">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="b371e-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="b371e-118">リバースプロキシの外部側で最初に受信された通信は、ディレクター HLB VIP およびフロントエンドサーバー web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b371e-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b371e-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="b371e-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="b371e-120">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b371e-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="b371e-121">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="b371e-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="b371e-122">リバースプロキシの外部側で最初に受信された通信は、ディレクター HLB VIP およびフロントエンドサーバー web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b371e-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b371e-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="b371e-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="b371e-124">ディレクター</span><span class="sxs-lookup"><span data-stu-id="b371e-124">Director</span></span></p></td>
<td><p><span data-ttu-id="b371e-125">フロントエンドプールまたはフロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="b371e-125">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="b371e-126">ディレクター HLB VIP とフロントエンドサーバーまたはフロントエンドサーバーとの間のサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="b371e-126">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b371e-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="b371e-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="b371e-128">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="b371e-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="b371e-129">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="b371e-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="b371e-130">ディレクターは、内部および外部クライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b371e-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b371e-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="b371e-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="b371e-132">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="b371e-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="b371e-133">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="b371e-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="b371e-134">ディレクターは、内部および外部クライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b371e-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b371e-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="b371e-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="b371e-136">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b371e-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b371e-137">ディレクター</span><span class="sxs-lookup"><span data-stu-id="b371e-137">Director</span></span></p></td>
<td><p><span data-ttu-id="b371e-138">フロントエンドサーバーに加えて、エッジサーバーからディレクターへの SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="b371e-138">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b371e-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="b371e-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="b371e-140">任意</span><span class="sxs-lookup"><span data-stu-id="b371e-140">Any</span></span></p></td>
<td><p><span data-ttu-id="b371e-141">ディレクター</span><span class="sxs-lookup"><span data-stu-id="b371e-141">Director</span></span></p></td>
<td><p><span data-ttu-id="b371e-142">集中ログサービスコントローラー (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="b371e-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b371e-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="b371e-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="b371e-144">任意</span><span class="sxs-lookup"><span data-stu-id="b371e-144">Any</span></span></p></td>
<td><p><span data-ttu-id="b371e-145">ディレクター</span><span class="sxs-lookup"><span data-stu-id="b371e-145">Director</span></span></p></td>
<td><p><span data-ttu-id="b371e-146">集中ログサービスコントローラー (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="b371e-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b371e-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="b371e-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="b371e-148">任意</span><span class="sxs-lookup"><span data-stu-id="b371e-148">Any</span></span></p></td>
<td><p><span data-ttu-id="b371e-149">ディレクター</span><span class="sxs-lookup"><span data-stu-id="b371e-149">Director</span></span></p></td>
<td><p><span data-ttu-id="b371e-150">集中ログサービスコントローラー (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="b371e-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

