---
title: 'Lync Server 2013: ポートの概要 - 拡張ディレクター プール、ハードウェア ロード バランサー'
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
ms.openlocfilehash: fdf054ee603f2c0917e35bdd2f19d108094c7c78
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="9f53c-102">ポートの概要 - Lync Server 2013 の拡張ディレクター プール、ハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="9f53c-102">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f53c-103">_**最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="9f53c-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="9f53c-104">ディレクタープールのファイアウォールポート要件は、エッジサーバーまたはリバースプロキシの内部インターフェイスからディレクターとの通信を確立するために使用されるポートで構成されています。</span><span class="sxs-lookup"><span data-stu-id="9f53c-104">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="9f53c-105">Microsoft Lync Server 2013 は、既定では、ポート HTTP/TCP 8080 と HTTPS/TCP 4443 が、リバースプロキシからディレクターまで、およびフロントエンドプールとフロントエンドサーバーによって開かれることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="9f53c-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="9f53c-106">さらに、エッジサーバーの内部インターフェイスからディレクターへのセッション開始プロトコル (SIP) 通信と、フロントエンドプールとフロントエンドサーバーへの通信が必要です。</span><span class="sxs-lookup"><span data-stu-id="9f53c-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="9f53c-107">SIP プロトコルは、SIP/MTLS/TCP 5061 をエッジサーバーからフロントエンドプールとフロントエンドサーバーに使用します。</span><span class="sxs-lookup"><span data-stu-id="9f53c-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="9f53c-108">SIP/MTLS/TCP 5061 によるディレクター、フロントエンドプール、フロントエンドサーバーからエッジサーバーの内部インターフェイスへの通信を可能にするルールも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f53c-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="9f53c-109">ファイアウォールの定義用のディレクターポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="9f53c-109">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f53c-110">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="9f53c-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9f53c-111">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="9f53c-111">Source IP address</span></span></th>
<th><span data-ttu-id="9f53c-112">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="9f53c-112">Destination IP address</span></span></th>
<th><span data-ttu-id="9f53c-113">メモ</span><span class="sxs-lookup"><span data-stu-id="9f53c-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f53c-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="9f53c-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="9f53c-115">リバースプロキシ内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f53c-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="9f53c-116">ディレクターハードウェアロードバランサー VIP</span><span class="sxs-lookup"><span data-stu-id="9f53c-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="9f53c-117">リバースプロキシの外部で最初に受信した通信は、ディレクター HLB VIP とフロントエンドサーバー web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="9f53c-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f53c-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="9f53c-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="9f53c-119">リバースプロキシ内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f53c-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="9f53c-120">ディレクターハードウェアロードバランサー VIP</span><span class="sxs-lookup"><span data-stu-id="9f53c-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="9f53c-121">リバースプロキシの外部で最初に受信した通信は、ディレクター HLB VIP とフロントエンドサーバー web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="9f53c-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f53c-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="9f53c-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="9f53c-123">ディレクター</span><span class="sxs-lookup"><span data-stu-id="9f53c-123">Director</span></span></p></td>
<td><p><span data-ttu-id="9f53c-124">フロントエンドサーバーまたはフロントエンドプール</span><span class="sxs-lookup"><span data-stu-id="9f53c-124">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="9f53c-125">ディレクター HLB VIP とフロントエンドサーバー間のサーバー間通信</span><span class="sxs-lookup"><span data-stu-id="9f53c-125">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f53c-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="9f53c-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="9f53c-127">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="9f53c-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="9f53c-128">ディレクターハードウェアロードバランサー VIP</span><span class="sxs-lookup"><span data-stu-id="9f53c-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="9f53c-129">ディレクターは、内部および外部クライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9f53c-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f53c-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="9f53c-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="9f53c-131">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="9f53c-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="9f53c-132">ディレクターハードウェアロードバランサー VIP</span><span class="sxs-lookup"><span data-stu-id="9f53c-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="9f53c-133">ディレクターは、内部および外部クライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9f53c-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f53c-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="9f53c-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="9f53c-135">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f53c-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9f53c-136">ディレクターハードウェアロードバランサー VIP</span><span class="sxs-lookup"><span data-stu-id="9f53c-136">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="9f53c-137">エッジサーバーからディレクターへの SIP 通信と、フロントエンドサーバー。</span><span class="sxs-lookup"><span data-stu-id="9f53c-137">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f53c-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="9f53c-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="9f53c-139">任意</span><span class="sxs-lookup"><span data-stu-id="9f53c-139">Any</span></span></p></td>
<td><p><span data-ttu-id="9f53c-140">ディレクター</span><span class="sxs-lookup"><span data-stu-id="9f53c-140">Director</span></span></p></td>
<td><p><span data-ttu-id="9f53c-141">一元管理サービスコントローラー (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="9f53c-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f53c-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="9f53c-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="9f53c-143">任意</span><span class="sxs-lookup"><span data-stu-id="9f53c-143">Any</span></span></p></td>
<td><p><span data-ttu-id="9f53c-144">ディレクター</span><span class="sxs-lookup"><span data-stu-id="9f53c-144">Director</span></span></p></td>
<td><p><span data-ttu-id="9f53c-145">一元管理サービスコントローラー (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="9f53c-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f53c-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="9f53c-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="9f53c-147">任意</span><span class="sxs-lookup"><span data-stu-id="9f53c-147">Any</span></span></p></td>
<td><p><span data-ttu-id="9f53c-148">ディレクター</span><span class="sxs-lookup"><span data-stu-id="9f53c-148">Director</span></span></p></td>
<td><p><span data-ttu-id="9f53c-149">一元管理サービスコントローラー (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="9f53c-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

