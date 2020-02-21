---
title: 'Lync Server 2013: ポートの概要-拡張ディレクタープール、ハードウェアロードバランサー'
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
ms.openlocfilehash: e8cb9d4d75eca59ee3749197de8b373a33b4515d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="e242a-102">ポートの概要-Lync Server 2013 の拡張ディレクタープール、ハードウェアロードバランサー</span><span class="sxs-lookup"><span data-stu-id="e242a-102">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e242a-103">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="e242a-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="e242a-104">ディレクタープールのファイアウォールポート要件は、エッジサーバーの内部インターフェイスまたはリバースプロキシの内部インターフェイスからディレクターとの通信を確立するために使用されるポートで構成されています。</span><span class="sxs-lookup"><span data-stu-id="e242a-104">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="e242a-105">Microsoft Lync Server 2013 既定では、ポート HTTP/TCP 8080 および HTTPS/TCP 4443 を、フロントエンドプールおよびフロントエンドサーバーに加えて、ディレクターへのリバースプロキシから開くことが想定されています。</span><span class="sxs-lookup"><span data-stu-id="e242a-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="e242a-106">さらに、エッジサーバーの内部インターフェイスから、ディレクターおよびフロントエンドプールおよびフロントエンドサーバーへのセッション開始プロトコル (SIP) 通信が必要です。</span><span class="sxs-lookup"><span data-stu-id="e242a-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="e242a-107">SIP プロトコルは、エッジサーバーの SIP/MTLS/TCP 5061 を使用して、フロントエンドプールおよびフロントエンドサーバーに対して使用します。</span><span class="sxs-lookup"><span data-stu-id="e242a-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="e242a-108">ディレクター、フロントエンドプールおよびフロントエンドサーバーからエッジサーバーの内部インターフェイスへの SIP/MTLS/TCP 5061 通信を許可するルールも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e242a-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="e242a-109">ファイアウォール定義用のディレクター ポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="e242a-109">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e242a-110">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="e242a-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e242a-111">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e242a-111">Source IP address</span></span></th>
<th><span data-ttu-id="e242a-112">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e242a-112">Destination IP address</span></span></th>
<th><span data-ttu-id="e242a-113">メモ</span><span class="sxs-lookup"><span data-stu-id="e242a-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e242a-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="e242a-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="e242a-115">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e242a-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="e242a-116">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="e242a-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e242a-117">リバースプロキシの外部側で最初に受信された通信は、ディレクター HLB VIP およびフロントエンドサーバー web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="e242a-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e242a-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="e242a-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="e242a-119">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e242a-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="e242a-120">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="e242a-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e242a-121">リバースプロキシの外部側で最初に受信された通信は、ディレクター HLB VIP およびフロントエンドサーバー web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="e242a-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e242a-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="e242a-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="e242a-123">ディレクター</span><span class="sxs-lookup"><span data-stu-id="e242a-123">Director</span></span></p></td>
<td><p><span data-ttu-id="e242a-124">フロントエンドサーバーまたはフロントエンドプール</span><span class="sxs-lookup"><span data-stu-id="e242a-124">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="e242a-125">ディレクター HLB VIP とフロントエンドサーバー間のサーバー間通信</span><span class="sxs-lookup"><span data-stu-id="e242a-125">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e242a-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="e242a-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="e242a-127">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="e242a-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="e242a-128">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="e242a-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e242a-129">ディレクターは、内部および外部クライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e242a-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e242a-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="e242a-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="e242a-131">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="e242a-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="e242a-132">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="e242a-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e242a-133">ディレクターは、内部および外部クライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e242a-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e242a-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="e242a-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="e242a-135">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e242a-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e242a-136">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="e242a-136">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e242a-137">エッジサーバーからディレクター、フロントエンドサーバーへの SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="e242a-137">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e242a-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="e242a-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="e242a-139">任意</span><span class="sxs-lookup"><span data-stu-id="e242a-139">Any</span></span></p></td>
<td><p><span data-ttu-id="e242a-140">ディレクター</span><span class="sxs-lookup"><span data-stu-id="e242a-140">Director</span></span></p></td>
<td><p><span data-ttu-id="e242a-141">集中ログサービスコントローラー (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="e242a-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e242a-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="e242a-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="e242a-143">任意</span><span class="sxs-lookup"><span data-stu-id="e242a-143">Any</span></span></p></td>
<td><p><span data-ttu-id="e242a-144">ディレクター</span><span class="sxs-lookup"><span data-stu-id="e242a-144">Director</span></span></p></td>
<td><p><span data-ttu-id="e242a-145">集中ログサービスコントローラー (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="e242a-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e242a-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="e242a-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="e242a-147">任意</span><span class="sxs-lookup"><span data-stu-id="e242a-147">Any</span></span></p></td>
<td><p><span data-ttu-id="e242a-148">ディレクター</span><span class="sxs-lookup"><span data-stu-id="e242a-148">Director</span></span></p></td>
<td><p><span data-ttu-id="e242a-149">集中ログサービスコントローラー (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="e242a-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

