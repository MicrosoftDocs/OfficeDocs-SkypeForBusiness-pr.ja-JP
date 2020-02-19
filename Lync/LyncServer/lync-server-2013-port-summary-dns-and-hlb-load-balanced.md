---
title: 'Lync Server 2013: ポートの概要-DNS と HLB 負荷分散'
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
ms.openlocfilehash: b6c58a9b2e4932087945322db0bd8980191c7c5a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="10079-102">ポートの概要-Lync Server 2013 での DNS および HLB の負荷分散</span><span class="sxs-lookup"><span data-stu-id="10079-102">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10079-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="10079-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="10079-104">単一ディレクターのファイアウォールポート要件は、内部インターフェイスまたはリバースプロキシの内部接続ネットワークからディレクターとの通信を確立するために使用されるポートで構成されます。</span><span class="sxs-lookup"><span data-stu-id="10079-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="10079-105">Microsoft Lync Server 2013 既定では、ポート HTTP/TCP 8080 および HTTPS/TCP 4443 を、フロントエンドプールおよびフロントエンドサーバーに加えて、ディレクターへのリバースプロキシから開くことが想定されています。</span><span class="sxs-lookup"><span data-stu-id="10079-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="10079-106">さらに、エッジサーバーの内部インターフェイスから、ディレクターおよびフロントエンドプールおよびフロントエンドサーバーへのセッション開始プロトコル (SIP) 通信が必要です。</span><span class="sxs-lookup"><span data-stu-id="10079-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="10079-107">SIP プロトコルは、エッジサーバーの SIP/MTLS/TCP 5061 を使用して、フロントエンドプールおよびフロントエンドサーバーに対して使用します。</span><span class="sxs-lookup"><span data-stu-id="10079-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="10079-108">ディレクター、フロントエンドプールおよびフロントエンドサーバーからエッジサーバーの内部インターフェイスへの SIP/MTLS/TCP 5061 通信を許可するルールも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10079-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="10079-109">ファイアウォール定義用の単一ディレクターポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="10079-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10079-110">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="10079-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="10079-111">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="10079-111">Source IP address</span></span></th>
<th><span data-ttu-id="10079-112">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="10079-112">Destination IP address</span></span></th>
<th><span data-ttu-id="10079-113">メモ</span><span class="sxs-lookup"><span data-stu-id="10079-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10079-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="10079-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="10079-115">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10079-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="10079-116">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="10079-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="10079-117">リバースプロキシの外部側で最初に受信された通信は、ディレクター HLB VIP およびフロントエンドサーバー web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="10079-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10079-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="10079-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="10079-119">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10079-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="10079-120">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="10079-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="10079-121">リバースプロキシの外部側で最初に受信された通信は、ディレクター HLB VIP およびフロントエンドサーバー web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="10079-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10079-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="10079-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="10079-123">ディレクター</span><span class="sxs-lookup"><span data-stu-id="10079-123">Director</span></span></p></td>
<td><p><span data-ttu-id="10079-124">フロントエンドプールまたはフロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="10079-124">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="10079-125">ディレクター HLB VIP とフロントエンドサーバーまたはフロントエンドサーバーとの間のサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="10079-125">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10079-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="10079-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="10079-127">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="10079-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="10079-128">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="10079-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="10079-129">ディレクターは、内部および外部クライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="10079-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10079-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="10079-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="10079-131">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="10079-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="10079-132">ディレクターハードウェアロードバランサーの VIP</span><span class="sxs-lookup"><span data-stu-id="10079-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="10079-133">ディレクターは、内部および外部クライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="10079-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10079-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="10079-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="10079-135">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10079-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="10079-136">ディレクター</span><span class="sxs-lookup"><span data-stu-id="10079-136">Director</span></span></p></td>
<td><p><span data-ttu-id="10079-137">フロントエンドサーバーに加えて、エッジサーバーからディレクターへの SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="10079-137">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10079-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="10079-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="10079-139">任意</span><span class="sxs-lookup"><span data-stu-id="10079-139">Any</span></span></p></td>
<td><p><span data-ttu-id="10079-140">ディレクター</span><span class="sxs-lookup"><span data-stu-id="10079-140">Director</span></span></p></td>
<td><p><span data-ttu-id="10079-141">集中ログサービスコントローラー (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="10079-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10079-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="10079-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="10079-143">任意</span><span class="sxs-lookup"><span data-stu-id="10079-143">Any</span></span></p></td>
<td><p><span data-ttu-id="10079-144">ディレクター</span><span class="sxs-lookup"><span data-stu-id="10079-144">Director</span></span></p></td>
<td><p><span data-ttu-id="10079-145">集中ログサービスコントローラー (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="10079-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10079-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="10079-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="10079-147">任意</span><span class="sxs-lookup"><span data-stu-id="10079-147">Any</span></span></p></td>
<td><p><span data-ttu-id="10079-148">ディレクター</span><span class="sxs-lookup"><span data-stu-id="10079-148">Director</span></span></p></td>
<td><p><span data-ttu-id="10079-149">集中ログサービスコントローラー (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="10079-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

